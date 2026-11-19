<p align="center">
  <img alt="Hivemind Control" src="assets/logo-512.png" width="112">
</p>

<h1 align="center">Hivemind Control</h1>

<p align="center"><b>A whole AI team on your PC, run from one window.</b><br>
One lead AI plans. Free and low-cost AIs do the typing. Scripts check every result. You stay in charge.</p>

<p align="center"><img alt="How Hivemind works" src="assets/how-it-works.svg" width="900"></p>

## Why it costs less
Premium AI time is the scarce part. Hivemind spends it on planning and judging, and hands the building to free models and plain scripts.
From our own logs, 10-19 Nov 2026 (421 jobs):

| | Jobs | Passed its check |
|---|---|---|
| Codex on a free ChatGPT sign-in | 178 | 79% |
| OpenCode free models | 67 | 52% |
| Antigravity (Gemini) | 13 | 54% |
| Script workers (git, Android builds, screenshots, files) | 81 | 78% |

A job only counts as done when its test passes; a model saying "done" is not enough. Failed tries move to the next model automatically.
A measured side-by-side against a single premium agent is in progress and will be published with its method.

## What you get
| | |
|---|---|
| **Chats and projects** | Chat with your lead AI in any project folder, plan or act, attach files; each project keeps its chats, files and tasks. |
| **The worker engine** | Jobs run in the background on the best free model for each task: building, reviews, research, image checks, image generation, quick answers. New providers you add a key for are found and used automatically. |
| **Checks that decide** | Every job carries a test. Fresh-eyes reviews check job instructions before work starts, and screenshots of every screen catch layout bugs. |
| **Usage and cost** | Limits for every provider, day-by-day tokens, cost and success rate per model, kept on your PC. |
| **AI models and setup** | One row per provider: sign in, add a key, see what it is used for. Checks with one fix button per problem. |
| **Phone access** | Use it from your phone privately through Tailscale (free). Nothing is opened to the internet. |
| **Save and update** | One click saves your work and installs new versions, with patch notes. |

Screenshots: [docs/SCREENSHOTS.md](docs/SCREENSHOTS.md) (sample data, never real projects).

## Case study: one UI rebuild, start to finish
The Usage, AI models and Jobs screens were rebuilt in one session: 6 planned jobs, 13 runs and 14 model tries in 52 minutes of
worker time. 7 runs passed on the first check; the rest were caught by the checks (wrong expectations, a broken plan file) and
re-run, with no bad change shipped. The lead AI wrote the plan and reviewed results; it typed almost none of the code.

## Get it
Hivemind Control comes with the Hivemind kit. Open `windows\Hivemind Control.bat` (Mac/Linux: `mac-linux/Hivemind Control.command`),
then in **Setup** choose **Make Hivemind Control an app**.

- [Requirements](docs/REQUIREMENTS.md) · [Questions and fixes](docs/FAQ.md) · [What's new](docs/CHANGELOG.md)

## Licence
Free for personal and other noncommercial use under the PolyForm Noncommercial License 1.0.0 ([LICENSE](LICENSE)).
Copyright (c) 2026 Sakib Hasan.
