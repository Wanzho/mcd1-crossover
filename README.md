# MCD1 Crossover — Minecraft Dungeons on Mac

A Mac launcher for the **Steam version of Minecraft Dungeons** (the original, 2020) through CrossOver on Apple Silicon.

It fixes Steam's audio startup, applies the Xbox sign-in repair at the right moment, and starts the game. Requires an existing Steam copy of the game and a Microsoft account.

> **Preview.** This is an early build. It has reached the main menu with a working Microsoft sign-in, but plenty is still untested. See [Limitations](#limitations).

<!-- screenshot: drag a launcher screenshot into the GitHub editor here -->

**[Download MCD1 Crossover →](https://github.com/Wanzho/mcd1-crossover/releases/tag/v0.1.0-preview.1)**

## You'll need

- A Mac with **Apple Silicon** running **macOS 13** or later
- **CrossOver 26.3**. Other versions are refused rather than patched blindly.
- **Windows Steam** in a CrossOver bottle, with **Minecraft Dungeons** installed

## Install

1. Download **MCD1-Crossover-0.1.0-preview-arm64.dmg** under **Assets** on the download page.
2. Open it and drag **MCD1 Crossover** into **Applications**.
3. Open **MCD1 Crossover**. The app isn't notarized, so if macOS blocks it, go to **System Settings → Privacy & Security** and click **Open Anyway**.
4. Choose your CrossOver bottle and click **Play**.

No Terminal, Python or build tools needed.

## Playing

**Open MCD1 Crossover and click Play every time you play.** Launching straight from Steam skips the sign-in repair.

When you click Play:

1. Steam is prepared in your bottle and may restart. Close any other Windows apps or games in that bottle first.
2. The game starts. Once it has a working window, the sign-in repair is applied automatically.
3. If Microsoft asks you to sign in, a separate window opens saying **Click Sign In to continue.** Click **Sign In** and finish in that window.

The launcher stays open while you play. It remembers your bottle, and opening it on its own never starts the game.

**Quit from the game's own menu.** Closing the game window has crashed CrossOver in testing.

## Xbox account

After you sign in, the sign-in window shows **Logged in as: …** and the launcher shows **Xbox account: …**. This is just a label for which account you used. It doesn't prove you're still signed in, and it's never included in saved logs. Signing in with a different account replaces it.

## Settings

- **Skip Startup Movies** is on by default. Turn it off to see the opening videos. It doesn't change your Steam launch options or the movie files.
- **Windowed mode** is optional. Your display settings are backed up before anything changes.
- **Choose game folder** if the game isn't found automatically.

## What it changes, and what it doesn't

- The sign-in repair only exists inside the running game. CrossOver's own files are never modified.
- Your saves, Microsoft credentials, macOS sound settings and CrossOver settings stay as they are.
- If your Mac has no sound output available, the game starts with sound disabled instead of failing.

## Troubleshooting

- **Window buttons disappeared:** click inside the game and press **Option + Return** once.
- **Steam seems stuck:** the launcher asks Steam to quit normally, then recovers it if it doesn't respond.
- **Anything else:** click **Save Logs…** in the launcher and attach the file to an [issue](https://github.com/Wanzho/mcd1-crossover/issues/new). Logs survive the app quitting, and work even if the game never opened. They contain no account names, sign-in links or tokens, and the game's network traffic is never recorded.

## Tested

Tested on Apple Silicon with **CrossOver 26.3** and the Steam version of the game. One launch from the app was confirmed end to end: the Microsoft sign-in window, then the game's main menu. Startup with sound works, and the sign-in repair attaches without help.

## Limitations

Not yet confirmed:

- Sign-in succeeding on the first try every time
- Staying signed in between sessions
- Long play sessions and multiplayer
- The **Xbox account** label with a real account
- Starting the game muted on a Mac with no sound output

Apple Silicon, macOS 13+ and CrossOver 26.3 only. **Minecraft Dungeons II** isn't supported (use [MCD2 Crossover](https://github.com/Wanzho/mcd2-crossover)), and neither is the Microsoft Store or Minecraft Launcher edition.

The app has an ad-hoc signature and isn't notarized by Apple.

Unofficial project. Not affiliated with Mojang, Microsoft or CodeWeavers.

## Credits

Coded with Codex. README by Claude Opus 5.5. App icon made with image generation; source artwork and prompt are in `assets`.

MIT License.
