# Orbi

A small white bot that lives in the corner of your Mac's screen, so you can chat with [Claude Code](https://docs.claude.com/en/docs/claude-code) without opening a terminal.

**Download:** [latest release](../../releases/latest)

## What it does
- **Click Orbi** to ask Claude something. A speech bubble shows what Claude is doing, and short replies appear right there.
- **Drag a file or photo onto Orbi** and it eats it. The file goes along with your next message.
- **Control + Command + Space** opens the full chat from any app.
- Pick the model (Fable, Opus, Sonnet, Haiku) from the label next to the input.
- Orbi walks around your screen. Click it and use the Move / Stay pill to turn that off.
- Right-click the menu-bar icon for the settings and to quit.

## Install
1. Download `Orbi-…-macOS-arm64.zip` from the [latest release](../../releases/latest) and unzip it.
2. Move `Claude Bridge.app` to `/Applications`.
3. The first time, **right-click the app, choose Open**, and click **Open**. If macOS still refuses, open System Settings > Privacy & Security and click **Open Anyway**. (The app isn't signed by an Apple developer account, so macOS asks once.)

## You need
- A Mac with Apple silicon (M1 or newer) and macOS 14 or later. It does not run on Intel Macs.
- The `claude` command line tool, installed and logged in (`claude /login`). Orbi finds it on your PATH, in `~/.local/bin`, or in the Claude desktop app's bundled copy (which has to be logged in once).

## Updates
From version 0.2.0 on, Orbi updates itself. About once a day it checks this page; when there is a newer version, Orbi says so in its speech bubble ("Orbi 0.2.1 is out. Click to update"). Click Orbi and it downloads the update, checks it, restarts and opens the new version. You can also use **Check for updates…** in the menu-bar icon's right-click menu, or switch the automatic check off there.

If you have version 0.1.0, install the latest release by hand once; it can't update itself. Your conversations and settings are kept.

## Privacy
No servers, no accounts, no tracking. Everything goes through the `claude` tool on your own Mac. The only thing Orbi contacts itself is GitHub, about once a day, to see whether a newer version exists. Conversations are saved only on your Mac, in `~/Library/Application Support/ClaudeBridge/`.

## License
Orbi is free to use and to share. It is **not open source**: the source code is not published. Provided as is, without warranty.

Inspired by [Coucou](https://github.com/Louis-CFM/coucou), a notch companion for coding agents. Orbi shares none of its code, artwork or sounds.
