# Findings: what we measured, compared and learned

A running record of real results from building and using Hivemind. Every number here comes from Hivemind's own logs
(job events, checks, usage records) on the date shown. New findings are added at the top of each section.

## 1. Worker results (measured)

### 14 Nov 2026: success rate per worker, all jobs so far
"Success" = the job's own check passed (tests or build), not just "the model replied".

| Worker / model | Tries | Passed | Typical time when passed | Main failure |
|---|---|---|---|---|
| Codex | 62 | 69% | ~3 min | check failed |
| opencode, free GLM model | 44 | 25% | ~10 min | stalled, check failed, limits |
| Antigravity (Gemini) | 15 | 27% | ~6 min | no reply in time |
| opencode, free DeepSeek model | 21 | 10% | ~6 min | stalled |
| NVIDIA-hosted free models | 40+ | ~0% | - | rate limits |
| Script workers (git commit, Android build) | 57 | 96-100% | seconds | - |

What we did: reordered every fallback chain by these numbers (best first). Since 14 Nov the relay does this by itself:
it ranks backups by their pass rate over the last 14 days (new models get a fair start), and pauses a provider, a login
or a single model that keeps failing, then retries it later.

Lesson: a router succeeds when the task succeeds, not when the cheapest model answers. Free models are worth keeping
in the chain, but only behind a check that proves the work.

## 2. Problems found and how they were fixed

| Date | What happened | Cause | Fix |
|---|---|---|---|
| 15 Nov | Every new job failed a size check | Changes were measured against the last commit, so unsaved earlier work counted | Each job is measured against a snapshot taken when it starts |
| 15 Nov | A big feature job stopped half done | One job asked for too much at once | Split into a small tested part and a hook-up part; both passed |
| 15 Nov | A cancelled task could still show as running | Two parts of the server wrote its status file at the same time | Saves take turns |
| 14 Nov | The task-list guard also undid the lead's own edits made during a job | It restored the list to the copy taken at job start | The lead marks its edits; the relay takes a fresh copy before restoring |
| 14 Nov | A finished job was reported as failed | The job's check named the wrong test file (one needing network access the worker's sandbox blocks) | Every job's check names the exact new test file |
| 14 Nov | App code downloaded as one 1.2 MB file | Every screen was bundled together | Screens load on demand; largest piece now 402 KB |
| 14 Nov | A worker could not install a package | One worker's sandbox has no internet | Package installs are a one-line owner step; the worker writes the code |
| 14 Nov | Claude usage showed as 0 | Claude records were filed under "Other" | Mapped to Anthropic, with a test |
| 14 Nov | Jobs "running" for 30+ minutes with no output | The stall timer counted a model's progress spinner as work | Only real output or file changes count; a test proves a spinner-only job is stopped |
| 14 Nov | A finished job stayed "running" for 25 minutes | One AI tool sometimes keeps its process open after its final answer | The relay ends it 60 s after the final answer |
| 14 Nov | Task list edits disappeared | A worker and the lead saved the same file at the same time | Workers may not edit the task list; the relay snapshots it before each job and restores it after, keeping any attempted change in a separate file |
| 14 Nov | A job ran on the wrong model | A reused file name delivered an older copy of the job | Every job is written under a new name and the worker is confirmed in the log right after sending |
| 14 Nov | The job summary said "no files changed" when files had changed | A cached file status was read too early | The final summary reads fresh status |
| 14 Nov | Sign-in window stayed blank | The terminal started before its window existed and dropped early output | It waits for the window and loads missed output |
| 14 Nov | A search job could have shown private app data to a cloud model | The job asked a model to read app data folders | Searches of private folders run as local scripts that print only names and counts; planned sandbox limits workers to the project folder |
| 14 Nov | Whole project looked changed to git | Windows and Linux line endings | One git setting; no files changed |

## 3. Comparisons

### OmniRoute (open-source AI gateway), reviewed 14 Nov 2026
OmniRoute puts one endpoint in front of many AI providers and switches between them. Hivemind runs AI agents on real
jobs and checks the results. Different jobs, so we borrowed ideas, not code.
- Adopted: three layers of fallback (whole provider, one login, one model) and scored routing (pass rate, speed,
  free first, quota left).
- Maybe later, after our own test: prompt compression (claimed 15-95% savings, not verified); OmniRoute as an optional
  extra provider.
- Not adopted: traffic disguise, intercepting secure connections, sharing consumer logins (terms of service and ban
  risk), and open-by-default network settings. Hivemind stays on your own computer with an access code.

### Rewrite in Rust or Go? (14 Nov 2026)
The slow part of starting the app is starting Linux (WSL), the local server and the browser window, not the language.
A rewrite would cost weeks and free AI workers are far more reliable in Python and React. Plan: measure startup first,
keep the engine warm, and wrap the app in a small Rust shell (Tauri) for a real installer and tray icon.
A later finding in the same spirit: the app's code downloaded as one 1.2 MB file; splitting it so each screen loads
on demand is cheaper than any rewrite.

## 4. Design choices and why

- Every "done" needs a check. A model's claim is not proof.
- Free and local models first; the one paid seat plans and reviews.
- Workers never edit the plan or task list; the lead does, after a job passes.
- Token use is recorded locally, numbers only, never prompt text.
- Cloud chats leave no local token records, so the app shows the provider's plan meter for them and counts only
  what it can measure. No estimates.

## 5. Ideas for videos
- "30 minutes stuck vs 6 minutes": the stall-timer bug and the fix, shown on the live Jobs screen.
- "Which free model actually finishes the job?": the success table above, re-measured each month.
- "One task, five main agents": the same task run with different lead models (planned benchmark).
- "How Hivemind protects your plan from its own workers": the task-list snapshot and restore.
- "Why we didn't rewrite it in Rust": measure first, change the slow part only.
