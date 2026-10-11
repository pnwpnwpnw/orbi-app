# Orbi

A small white bot that lives in the corner of your Mac's screen, so you can chat with [Claude Code](https://docs.claude.com/en/docs/claude-code) without opening a terminal.

**Download:** [latest release](../../releases/latest)

## What it does
- **Control + Command + Space** opens a small quick-ask bar from any app: Orbi, an input box, the model and the folder. Type, press Return, and the answer shows in Orbi's speech bubble. The small chat button in the bar lets you choose which chat the message goes to: a new one, or one of your 5 latest. You can change the shortcut in Settings.
- **Click Orbi** to ask Claude something from the desktop. A speech bubble shows what Claude is doing, and short replies appear right there.
- **Click the menu-bar icon** to open the full chat window, with your saved conversations, a light or dark look that follows your Mac, and replies that appear as Claude writes them, formatted (bold, lists, code blocks, links). The steps Claude takes ("Read Sessions.swift") stay in the chat as small pills. Hover a chat in the title menu and click its trash icon to delete it. Click anywhere else and the window goes away.
- **Orbi acts out what Claude is doing:** it scans while reading, taps while editing, peers around while searching, hunkers down while running a command and bounces while writing the reply.
- **Drag a file or photo onto Orbi** and it eats it. The file goes along with your next message.
- Pick the model (Fable, Opus, Sonnet, Haiku) from the label next to the input.
- Orbi walks around your screen. Click it and use the Move / Stay pill to turn that off.
- **Right-click Orbi** and a fan of quick settings swings out beside it, three pills at a time (scroll with a trackpad, mouse wheel or the arrow keys for the rest; the pill you click glides to the middle): **Send to Claude app**, **Show name**, **Token bar**, **Watch Claude app**, **Permission alerts**, **Sounds**, **Auto updates** (click to switch on or off; orange is on for the Claude ones, white for the rest), **Model** (click to step through the models) and **Full settings…**. Each pill has a small icon, and Orbi glances toward them while they are open. In **Settings → Quick settings** you choose which pills show.
- **Usage meter (version 0.4.6 and newer).** A thin bar with a percentage sits above Orbi's name tag. By default it shows your Claude **session limit**, the same number as in the Claude app; click **Token bar** in the right-click fan and small pills fan out of it: **Show number**, **Show bar**, and a pill that cycles between **Session limit**, **Weekly limit** and the **conversation's context**. The bar turns orange from 70% and red from 90%. Orbi gets the limits by asking Claude itself (`claude -p "/usage"`, about every five minutes), so it never sees your login. It needs a Claude subscription (Pro or Max); the context option works for everyone who has **Watch Claude app** on.
- **Watch the Claude app (optional, version 0.4.5 and newer).** Switch on **Watch Claude app** and Orbi acts out what Claude is doing in your Claude app conversations: all the active ones, or only the one you pick in Settings, even with several working at once. The bubble shows the latest step, there is a hop and a chime when one finishes, and a click on the bubble jumps to that conversation. Orbi only reads each conversation's own log; it never writes to it.
- **Permission alerts (optional, version 0.4.5 and newer).** Orbi can speak up the moment Claude asks for your permission, with a chime, a bounce and what it wants to do, until you answer. Turn it on with the **Permission alerts** pill or in Settings. It asks first, then adds a small note to Claude's settings that only passes the request to Orbi; it can't approve, deny or delay anything, and your other settings are kept (a backup is saved next to the file). Turn it off any time.
- **Sound effects (version 0.4.5 and newer).** Soft sounds for clicks, the quick-ask bar, sending, replies, errors, the right-click fan and eating. They are made inside the app, kept quiet, and switched off with the **Sounds** pill or in Settings.
- **Settings:** right-click the menu-bar icon and choose **Settings…**, or use **Full settings…** in the right-click fan (version 0.3.0 and newer; a new dark look in 0.4.5). Pick where Orbi parks, how fast it walks, its name, the shortcut, the folder new chats start in, sounds, watching the Claude app, permission alerts, which right-click pills show, and rename or delete saved conversations.
- **Send to the Claude app (experimental, version 0.3.0 and newer).** Type into a conversation open in the Claude desktop app, and pick which one. See [below](#send-messages-to-the-claude-app-experimental).

## Install
1. Download `Orbi-…-macOS-arm64.zip` from the [latest release](../../releases/latest) and unzip it.
2. Move `Orbi.app` to `/Applications`.
3. The first time, **right-click the app, choose Open**, and click **Open**. If macOS still refuses, open System Settings > Privacy & Security and click **Open Anyway**. (The app isn't signed by an Apple developer account, so macOS asks once.)

## Send messages to the Claude app (experimental)

From version 0.3.0, Orbi can also type your message into the **Claude desktop app**, so it lands in a conversation you already have open there, as if you had typed it yourself. Replies show up in the Claude app, not in Orbi.

**Set it up (once)**
1. Install Orbi in your **Applications** folder and open it, and make sure the **Claude app** is installed and running.
2. Right-click Orbi itself and click the **Send to Claude app** pill, so it turns orange. (The same switch is in **Settings…**.) A dialog explains the permission; click **Open the permission prompt**.
3. macOS opens **System Settings > Privacy & Security > Accessibility**. Switch **Orbi** on. If it isn't in the list yet, click **"+"**, choose **Orbi** in your Applications folder and switch it on. macOS may ask for your password.
4. In the Claude app, open the conversation you want to talk to and leave its window open (not minimized).
5. **Test it:** press Control + Command + Space (or click Orbi), type "hello from Orbi" and press Enter. The Claude app flashes to the front, the message appears in the conversation, and you land back where you were.

If step 5 says Orbi isn't allowed to control other apps even though the switch looks on, see "Good to know" below.

**Use it**
- Click Orbi (or press the shortcut). The box now says "Send to the Claude app…", and a button shows where your message will go, like **"→ GitHub repo access ▾"**. Right-click Orbi and click the pill again to switch it off.
- Click that button to pick a different conversation from your recent ones. Orbi reads the titles from the Claude app's own session files and never changes them.
- Type your message and press Enter. Orbi brings the Claude app to the front, pastes the message, presses Return and takes you back to what you were doing. It takes about a second, so don't click or type in that moment. Your clipboard is put back afterwards.
- Dropped files are added to the message as file paths.

**Safe by design**
- If you picked a conversation and the Claude app isn't showing it, Orbi types **nothing** and tells you why.
- Orbi only types the messages you send it, and only into the Claude app.
- Switching to another conversation uses the Claude app's own link. It worked in testing, but a future version of the app could change that. If switching fails, Orbi stops and sends nothing.

**Good to know**
- The Claude app has to be running. Orbi doesn't open it for you.
- Orbi's Enter works like your own: if Claude is in the middle of an answer when you send, that answer is **interrupted** and your new message is handled instead. Wait for Claude to finish if you don't want that.
- If macOS says Orbi isn't allowed to control other apps, even though the switch looks on, the permission belongs to an older copy of the app. Select **Orbi** (or **Claude Bridge**, its old name) in the Accessibility list, press **"−"** to remove it, then add it again. From version 0.4.0 Orbi is signed the same way every time, so this should only be needed once, when you update from an older version.
- It works by controlling a window, so a future change to the Claude app's layout could break it. **Save Claude app layout** in **Settings…** writes a description of the window that makes such a break easy to diagnose.

## You need
- A Mac with Apple silicon (M1 or newer) and macOS 14 or later. It does not run on Intel Macs.
- The `claude` command line tool, installed and logged in (`claude /login`). Orbi finds it on your PATH, in `~/.local/bin`, or in the Claude desktop app's bundled copy (which has to be logged in once).

## Updates
From version 0.2.0 on, Orbi updates itself. About once a day it checks this page; when there is a newer version, Orbi says so in its speech bubble ("Orbi 0.2.1 is out. Click to update"). Click Orbi and it downloads the update, checks it, restarts and opens the new version. You can also use **Check now…** in **Settings…** (right-click the menu-bar icon), or switch the automatic check off there.

If you have version 0.1.0, install the latest release by hand once; it can't update itself. Your conversations and settings are kept.

## Privacy
No servers, no accounts, no tracking. Everything goes through the `claude` tool on your own Mac. The only thing Orbi contacts itself is GitHub, about once a day, to see whether a newer version exists. The usage meter asks the `claude` tool on your Mac for your limits. Watching the Claude app and permission alerts stay on your Mac: Orbi reads the conversation logs Claude Code already keeps there, and the optional permission note is a small file in `~/Library/Application Support/ClaudeBridge/`. Conversations are saved only on your Mac, in `~/Library/Application Support/ClaudeBridge/`.

## License
Orbi is free to use and to share. It is **not open source**: the source code is not published. Provided as is, without warranty.

Inspired by [Coucou](https://github.com/Louis-CFM/coucou), a notch companion for coding agents. Orbi shares none of its code, artwork or sounds.
