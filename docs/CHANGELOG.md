# What's new

## 2026.11.26.2 — November 26, 2026

- **New:** Parallel isolated workspaces — background jobs touching different files in the same project can now run side by side safely and merge in order, with automatic subdirectory and `node_modules` support.
- **New:** Built-in Ollama and LM Studio support alongside Local AI — Hivemind automatically detects running local models and uses them for quick tasks, falling back to cloud models immediately when offline.
- **New:** Cross-vendor Plan Council vetting — high-impact plans can now be checked by a zero-cost linter and vetted read-only by a second AI vendor with strict security-blocker protection before jobs run.
- **Improved:** Live Hive Map now includes an Active-only filter, Local model badges, and recent pass/fail and skill details when inspecting any model node.

## 2026.11.26.1 — November 26, 2026

- **New:** Live Hive Map in Jobs — watch active leads, queued tasks, AI models, fallbacks, and checks live in real time, with an opt-in Demo simulation mode and a Dashboard shortcut.
- **New:** Cross-model skill injection — worker models across all connected providers now receive concise, task-matched skill rules automatically.
- **New:** Isolated workspace mode for background jobs — opt-in temporary copies merge passing work cleanly and discard failed attempts without touching your live project folder.
- **Improved:** Cleaner, faster UI across the app — Usage now opens with a multi-lead summary, clearly labeled pass rates, and tabbed analytics; Project chats use compact action menus; Chat shows the active main agent and fits phone screens cleanly; Jobs shows real lead models and token costs with fewer tabs; Save & update hides technical Git details in a toggle.
- **Improved:** Unified local tracking records token usage and costs locally for all connected workers and main agents.
- **Fixed:** Resolved background worker issues that could falsely reject small edits to larger files, truncate checks containing commas, lose events across log chunks, or ignore a job's chosen provider and model.

## 2026.11.25.1 — November 25, 2026

- **New:** Chats can use Antigravity's top models (Gemini 4 Neon, Claude Opus 5.5) as the main agent for planning, next to Claude and Codex.
- **Improved:** 3D models, shaders, rigs, effects and SVG art go to Gemini 4 Neon first.
- **Fixed:** Local AI starts and answers on Windows: it finds the model list, the full PC memory and shows the real speed.
- **Fixed:** "Update model order" no longer breaks the settings file or puts free models ahead of better ones.
- **Fixed:** A job that names a model now always tries that model first.
- **Fixed:** Two free OpenCode models that were withdrawn are replaced with working ones.
- **Improved:** Saves and pushes verified work.
- **Improved:** Each AI model gets its own time for a job, so one stuck model can no longer use up the time of the next one.

## 2026.11.24.3 — November 24, 2026

- **Improved:** Setup is rebuilt: four summary tiles, one line per AI account with a plain reason and one button, and only the PC checks that need you. Rarely used tools moved under Advanced.
- **Improved:** Providers you never set up are listed under "More providers you can add" instead of showing as errors.
- **Fixed:** Local AI finds the graphics card and full memory of Windows PCs.
- **Fixed:** Local AI works with models you already downloaded: point it at the folder and it reuses the files and the engine found there.
- **Fixed:** Local AI uses the tested speed settings for each model and connects correctly from Hivemind's background service on Windows.
- **Fixed:** AI model checks no longer show "Unknown alias" for OpenCode Go and NVIDIA models.
- **Fixed:** A failed background job only undoes its own files, never other work in the same folder.

## 2026.11.24.2 — November 24, 2026

- **New:** Setup > Local AI: check your PC, set up a recommended model with one click, then start, stop or pause it. Hivemind installs the engine, downloads the model, keeps memory free for your other apps and restarts it after a crash.
- **New:** Use models you already downloaded: point Local AI at the folder and it uses them without downloading again.
- **Fixed:** Patch notes no longer include internal job lines.

## 2026.11.24.1 — November 24, 2026

- **Improved:** The installed Hivemind version is always shown at the bottom of the sidebar.
- **Fixed:** Turning on the usage overlay no longer shows a false "did not write its start line" error.
- **Fixed:** Updating no longer stops when the app site folder was left half-way through an earlier update.
- **Improved:** Hivemind checks AI sign-ins every hour while idle and tells you once before jobs are skipped.
- **Improved:** When an AI model stops before doing the work, the relay nudges it once and then tries the next model.
- **Improved:** If Codex fails, jobs move to OpenCode Go models first; a rejected key moves the job to the next model.
- **Improved:** The keys file has separate, labelled lines for the OpenCode Zen and OpenCode Go keys.
- **Improved:** Groundwork for local AI models (PC check, downloads, engine install, crash recovery); the setup screen comes next.

## 2026.11.23.3 — November 23, 2026

- **Improved:** Providers that need a second value (like an account ID) now ask for it when you add the key.
- **Improved:** When an AI account needs signing in again, its jobs now wait and you get one note, instead of failing.
- **Improved:** Usage now counts tokens for every AI worker, including Gemini and quick-answer providers.
- **Fixed:** The usage overlay switch starts the overlay window reliably again.
- **Improved:** The free APIs library now also covers free tools, services, open-source projects and assets.
- **Improved:** Background AI workers can work in any folder you allowed, not just the Hivemind folder.
- **Improved:** Quick-answer AI models can now write files too: their answer is checked and saved by Hivemind.
- **Improved:** AI models list is sorted best and connected first, with a search box and a clear "why" line for each model.
- **Improved:** Cancelled jobs look different from failed ones, and the app shows when the lead AI will check in next.
- **Improved:** Jobs stopped by an install, restart or your cancel no longer count as failures; interrupted ones restart on their own.
- **Fixed:** Cancelling a waiting job now really stops it from starting.
- **Improved:** Hivemind can use AI models running on your own PC, and local models download in the background.
- **Improved:** The lead AI can save and push your work by itself when nothing else is running, and its own work now shows in Jobs > Lead.
- **Improved:** OpenCode Go and OpenCode Zen have separate keys, and Hivemind checks the Go sign-in before using Go models.
- **Improved:** The relay picks the AI model for each job from how well it did on its last 10 similar jobs.
- **Fixed:** The size safety check only counts what the job itself changed, so check-only jobs and builds no longer fail on log and build files.
- **Fixed:** AI workers are now told exactly which files they may edit, so fewer jobs fail for being out of scope.
- **Fixed:** Free and Go OpenCode models can read the files they need outside the job folder (allowed folders only).
- **Fixed:** Saving and publishing no longer shows a false error, and the app site catches up with GitHub by itself.
- **Improved:** UI polish: cleaner Jobs table with quick retry and cancel buttons, tidier Setup and Usage screens, a smaller idle task tray, and better phone layouts.

## 2026.11.20.3 — November 20, 2026

- **Improved:** The app stays signed in after an update, and the Jobs list no longer shows internal files as failed jobs.
- **Improved:** New AI providers you add a key for are found automatically, checked, and shown in the app; the model check now tests models correctly.
- **Improved:** Usage data uses one name per provider everywhere and is saved at start, every 10 minutes and at shutdown, so Claude and others always show.
- **Improved:** Work is spread across all your connected AI providers by task type, and new providers get tried automatically.
- **Improved:** Setup and AI models show one row per provider with its models folded inside, separate free and paid OpenCode slots, and what each provider is used for.
- **Improved:** Screenshots for the website use sample data only, never your own projects or files.
- **New:** New AI providers you add a key for are found, checked and put to work automatically.
- **New:** Work is spread across your providers by task type (building, reviews, research, images, quick answers).
- **Improved:** Setup and AI models show one row per provider, with separate free and paid OpenCode slots.
- **Improved:** Usage data uses one name per provider and is saved at start, every 10 minutes and at shutdown.
- **Fixed:** The app stays signed in after an update; model checks test the right models.
- **Improved:** Setup shows one line per provider that needs attention, AI models lists connected providers first, and checks rerun after each update.
- **Improved:** New charts for token history and daily cost and success, with clear legends and tooltips.
- **Improved:** Setup lists one line per provider that needs attention; AI models shows connected providers first.
- **New:** A built-in list of 2,500 free public APIs that apps and games can draw on.
- **Fixed:** Claude now appears in every usage breakdown.
- **Improved:** Demo mode shows every screen correctly, and one broken panel can no longer blank the whole app.
- **Improved:** Usage and AI models screens no longer break when some data is missing.
- **Improved:** Website screenshots look like a real, well-used app with consistent sample data.
- **Improved:** Many screen fixes from a design review: phone chat bar, consistent colours in light mode, readable send button, aligned job actions, no cut-off rows, better empty states.
- **Improved:** Sample data for website screenshots is consistent across all screens.

## 2026.11.18.5 — November 19, 2026

- **New:** Film and anime directing guide: story checks, shot lists, continuity locks and render fixes.
- **Improved:** More natural voices, clear pauses between speakers and scenes, and sound effects that stay off the dialogue.
- **Improved:** Dialogue timing between speakers and scenes now follows clear rules, and the mix is checked automatically.
- **Improved:** Shot lists for films and animations are checked automatically for continuity mistakes before rendering.
- **Improved:** The engine no longer reports a job as done when no AI model actually ran it.
- **Improved:** The Models screen shows real success rates and history for every AI model, from the engine's own job log.
- **Improved:** Usage keeps a history of every provider's limits, Claude included, so past days never go missing.
- **Improved:** Usage and job history on each PC are protected and never overwritten by syncing.
- **Improved:** Pop-ups and menus are checked automatically so they can never open behind other parts of the screen.
- **Improved:** The app tells you when an update is ready and installs it with one click.
- **New:** Success rates and history for every AI model, from real job results.
- **New:** Usage history for every provider, Claude included, with charts.
- **New:** One-click "Update ready - Install" in the app.
- **Improved:** Syncing never overwrites this PC's usage and job history.
- **Fixed:** A job is never shown as done when no AI model actually ran it.
- **New:** Day-by-day usage record: tokens, cost and success rate for every provider and model.
- **Improved:** Usage keeps a day-by-day record of tokens, cost and success rate for every provider and model.
- **Improved:** Cleaner screens: update pill in the top bar, collapsible sections, compact provider cards and model table, Jobs and Activity in one tab, file search.
- **Fixed:** Notification tray background, usage overlay switch, update notice that never cleared, and the error page while the app starts.
- **Improved:** Cleaner layout: updates show as a small pill in the top bar, sections can be collapsed, and loading animations fill their space.
- **Improved:** Usage and Models screens are compact: one card per provider and one table for model success, with small inline charts.
- **Improved:** Jobs and Activity are one tab, and Files has search.
- **Improved:** Usage screen redesigned: compact provider cards, a clear day-by-day table with sorting, and small charts that make sense.
- **Improved:** Models are grouped under the right provider everywhere, and clicking a provider opens its sign-in or key.
- **Improved:** AI models and Setup are easier: long sections start collapsed, failing models are named with a fix button, and DeepSeek is not marked broken before a key is added.
- **Improved:** Jobs table fits the screen, and chats show a thinking animation while waiting for a reply.
- **Improved:** One crashed attempt no longer blocks the best AI model for an hour.
- **Improved:** Usage redesigned: compact provider cards, a sortable day-by-day table and clear small charts.
- **Improved:** AI models and Setup: long sections start collapsed, failing models are named with a fix, and clicking a provider opens its sign-in or key.
- **Improved:** Jobs table fits the screen; chats show a thinking animation while waiting.
- **Fixed:** Jobs that changed nothing are no longer marked done; one crashed try no longer blocks a model for an hour.
- **Improved:** A job that changed nothing is flagged for review instead of counted as done.

## 2026.11.17.8 — November 17, 2026

- **Improved:** Patch notes are drafted for you when the app site is behind, and the field says when there is nothing to publish.

## 2026.11.17.7 — November 17, 2026

- **Improved:** Saving never waits for patch notes; publishing the app site is its own step, with notes drafted for you.
- **Fixed:** The notification tray opens above everything; the patch notes field can be edited.

## 2026.11.17.5 — 2026-11-17
- **New:** Notification center: one bell, one item per problem, and items clear themselves once fixed.
- **New:** Usage screen shows every provider, with a Refresh button and old readings marked.
- **Improved:** Usage numbers refresh by themselves every 10 minutes.
- **Improved:** Simple jobs go to free AI models first, saving paid quota.
- **Improved:** Save & update keeps the app site in step and says clearly when it could not.
- **Fixed:** The save message fills in again after an earlier save.

## 2026.11.17.2 — 2026-11-17
- **New:** Delete chats and projects safely; deleted folders go to the Recycle Bin.
- **New:** First-run guide, plus a banner when setup needs a re-check.
- **New:** Side panel with media previews, and an effort picker for chats.
- **New:** Check each AI model on its own, and add keys right where they are needed.
- **Improved:** Background work recovers by itself more often and explains failures in plain words.
- **Improved:** Usage chart fills gaps on quiet days; model limits show on the Models screen.
- **Fixed:** Blank sign-in window on the Providers screen, and other stability fixes.

## 2026.11.13.5 — 2026-11-13
- **New:** Project screen with chats, files and a Tasks tab (task list, progress note, jobs) and "Start chat from this task".
- **New:** A warning when two chats edit the same project at the same time.
- **Improved:** Deleting a project or chat moves it to a trash folder; nothing is removed for good.
- **Fixed:** A terminal error when reopening some screens.
- **Fixed:** Folder paths on Windows network drives.
