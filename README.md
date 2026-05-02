# Artifacts of European MCT Summits

This folder contains materials related to the presentations at (European) MCT Summits: Slides, Code samples etcetera

You find more information at the website **[mctsummit.eu](https://mctsummit.eu)**, that serves as a central hub and archive for **M**icrosoft **C**ertified **T**rainers. 

This repo is likely incomplete. If you've given a presentation at a previous summit, you might want to add your material to this repo.

## Contribute

If you **spoke at a summit**, you can add slides, demo code, or a short `README.md` (title and abstract) so other MCTs can find them. Everything is organized **by event year** (folder names like `2026-sarajevo-ba`), then **by speaker and session**. If you are not sure where your folder should sit, open an issue on this repo or ask an organizer; they can point you to the right path.

Target layout (example): `2026-sarajevo-ba/your-name/session-topic/README.md` plus your files next to it.

All changes go through **GitHub** into the **`MCTSummitEU/Artifacts`** repository. You never commit directly to `main` on the org repo: you **fork** (your copy), add files, then open a **Pull request** so maintainers can review and merge.

### Using the GitHub website

1. **Sign in** at [github.com](https://github.com).
2. Open **[github.com/MCTSummitEU/Artifacts](https://github.com/MCTSummitEU/Artifacts)** and click **Fork** (creates your own copy under your account).
3. In **your fork**, browse to the summit folder (e.g. `2026-sarajevo-ba`), then your speaker folder and session folder. If the path does not exist yet, use **Add file → Create new file**, type the full path (e.g. `2026-sarajevo-ba/jane-doe/my-topic/README.md`); GitHub creates the missing folders when you save.
4. Upload or paste content. Use **Commit changes** with a short message (e.g. “Add slides for Jane Doe – My session”).
5. On your fork, click **Contribute → Open pull request**, add a short description, and submit. Maintainers will review and merge into the main Artifacts repo.

### Using Git on your PC

You need **Git for Windows** installed and a **GitHub** account. Replace the example URLs and paths with your fork and summit folders.

```powershell
## Clone your fork (use your GitHub username, not MCTSummitEU)
Set-Location -Path $HOME\Documents
git clone https://github.com/YourGitHubUser/Artifacts.git
Set-Location -Path .\Artifacts

## Create a branch for your materials
git checkout -b add-my-session-material

## Add files under the correct summit and session folder, then:
git status
git add --all
git commit -m 'Add session materials for Your Name'
git push -u origin add-my-session-material
```

After the push, open your fork on GitHub and use **Compare & pull request** to send the changes to **MCTSummitEU/Artifacts**.

**Rights:** Only upload material you are allowed to distribute (your own slides/code, or content cleared for sharing). Do not commit secrets, passwords, or large personal datasets.

**More detail for maintainers:** per-summit naming and automation notes live in each year folder’s **`ARTIFACTS_AI.md`** (not required reading for a one-off speaker upload).
