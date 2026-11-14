# Questions and fixes

**It says "Open Hivemind Control from its launcher".**
The window lost its sign-in because the app restarted. Open it again from the shortcut.

**The app doesn't open.**
Run Setup > Check everything. The details are in the `logs` folder of your kit.

**Save & update fails at the upload step.**
Install Git for Windows: `winget install --id Git.Git -e`, then try again.

**A job failed. What now?**
Open it in Jobs to see each try, the check result and why it stopped. Limits and sign-in problems move the job to the next model by itself.

**How do I use it from my phone?**
Settings (top right) > Phone access. Install Tailscale on the PC and the phone with the same account, press Turn on phone access and scan the QR code.
Only the PC can turn sharing on or make a new link. New link signs the old phone out.

**Is my data sent anywhere?**
No. The app runs on your computer. Phone access goes through your private Tailscale network only.

**Still stuck?**
Use "Copy diagnostics" on the error and send it to your assistant.
