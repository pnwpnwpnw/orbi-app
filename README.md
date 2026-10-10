# Orbi

A small white bot that lives in the corner of your Mac's screen, so you can chat with [Claude Code](https://docs.claude.com/en/docs/claude-code) without opening a terminal.

**Download:** [latest release](../../releases/latest)

## What it does
- **Click Orbi** to ask Claude something. A speech bubble shows what Claude is doing, and short replies appear right there.
- **Drag a file or photo onto Orbi** and it eats it. The file goes along with your next message.
- **Control + Command + Space** opens the full chat from any app.
- Pick the model (Fable, Opus, Sonnet, Haiku) from the label next to the input.
- Orbi walks around your screen. Click it and use the Move / Stay pill to turn that off.
- **Send to the Claude app (experimental, version 0.3.0 and newer).** Type into a conversation open in the Claude desktop app, and pick which one. See [below](#send-messages-to-the-claude-app-experimental).
- Right-click the menu-bar icon for the settings and to quit.

## Install
1. Download `Orbi-…-macOS-arm64.zip` from the [latest release](../../releases/latest) and unzip it.
2. Move `Claude Bridge.app` to `/Applications`.
3. The first time, **right-click the app, choose Open**, and click **Open**. If macOS still refuses, open System Settings > Privacy & Security and click **Open Anyway**. (The app isn't signed by an Apple developer account, so macOS asks once.)

## Send messages to the Claude app (experimental)

From version 0.3.0, Orbi can also type your message into the **Claude desktop app**, so it lands in a conversation you already have open there, as if you had typed it yourself. Replies show up in the Claude app, not in Orbi.

**Set it up (once)**
1. Install Orbi in your **Applications** folder and open it, and make sure the **Claude app** is installed and running.
2. Right-click Orbi's menu-bar icon and choose **Send messages to the Claude app (experimental)**. A dialog explains the permission; click **Open the permission prompt**.
3. macOS opens **System Settings > Privacy & Security > Accessibility**. Switch **Claude Bridge** on. If it isn't in the list yet, click **"+"**, choose **Claude Bridge** in your Applications folder and switch it on. macOS may ask for your password.
4. In the Claude app, open the conversation you want to talk to and leave its window open (not minimized).
5. **Test it:** click Orbi, type "hello from Orbi" and press Enter. The Claude app flashes to the front, the message appears in the conversation, and you land back where you were.

If step 5 says Orbi isn't allowed to control other apps even though the switch looks on, see "Good to know" below.

**Use it**
- Click Orbi. The box now says "Send to the Claude app…", and a button shows where your message will go, like **"→ GitHub repo access ▾"**.
- Click that button to pick a different conversation from your recent ones. Orbi reads the titles from the Claude app's own session files and never changes them.
- Type your message and press Enter. Orbi brings the Claude app to the front, pastes the message, presses Return and takes you back to what you were doing. It takes about a second, so don't click or type in that moment. Your clipboard is put back afterwards.
- Dropped files are added to the message as file paths.

**Safe by design**
- If you picked a conversation and the Claude app isn't showing it, Orbi types **nothing** and tells you why.
- Orbi only types the messages you send it, and only into the Claude app.
- Switching to another conversation uses the Claude app's own link and may not work in every version. If it doesn't, Orbi stops and sends nothing.

**Good to know**
- The Claude app has to be running. Orbi doesn't open it for you.
- If macOS says Orbi isn't allowed to control other apps, even though the switch looks on, the permission belongs to an older copy of the app. Select **Claude Bridge** in the Accessibility list, press **"−"** to remove it, then add it again. This can be needed after an update.
- It works by controlling a window, so a future change to the Claude app's layout could break it. **Save Claude app layout** in the menu writes a description of the window that makes such a break easy to diagnose.

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
