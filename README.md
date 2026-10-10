# MCD1 Crossover — Minecraft Dungeons on Mac

Play the **Steam version of Minecraft Dungeons** through CrossOver on an Apple Silicon Mac. MCD1 Crossover starts the game through Windows Steam, prepares the sign-in helper automatically, and opens Microsoft sign-in in a separate Mac window.

**[Download the latest preview →](https://github.com/Wanzho/mcd1-crossover/releases/tag/v0.1.1-preview.2)**

This is preview software. Sign-in can need a second attempt, and closing the external sign-in window can leave the game unresponsive. Follow the steps below.

## Requirements

- An **Apple Silicon Mac** running **macOS 13 or later**.
- **CrossOver**, with Windows Steam and the original **Minecraft Dungeons** installed in a bottle.
- A **Microsoft account** for Xbox sign-in.

The credential repair has been tested against a CrossOver 26.3 code layout. Compatibility is checked using the relevant DLL functions and layout, rather than a whole-file hash or just the version number. Other builds with matching code can pass; different layouts still need adaptation.

This app is for **Minecraft Dungeons 1 on Steam**. Minecraft Launcher and Microsoft Store copies are not supported. For Dungeons II, use [MCD2 Crossover](https://github.com/Wanzho/mcd2-crossover).

## Install and choose your game

1. On the preview release page, download the **arm64 `.dmg`** from **Assets**.
2. Open the DMG and drag **MCD1 Crossover** into **Applications**.
3. Open the app. It is ad-hoc signed and not notarized; if macOS blocks it, use **System Settings → Privacy & Security → Open Anyway** for the copy you downloaded from this repository.
4. Select the CrossOver bottle containing your Windows Steam installation and Minecraft Dungeons. If the game is not found automatically, click **Choose…** and select its installed folder or `Dungeons-Win64-Shipping.exe`.

You do not need to install Python, use Terminal, or attach a helper yourself. Close other Windows games or apps in the selected bottle before starting; Windows Steam may restart during preparation.

## How to enter the game

1. **Open MCD1 Crossover and click Play.**
2. After the game launches, click **Press Any Button** to open the external Microsoft sign-in window. **If the external window does not open**, click the **X in the in-game browser** to close that panel, then click **Press Any Button** again.
3. **Sign in with your Microsoft account** in the external window. If your account is already saved, click **Sign In** to continue.
4. The external window closes and **Let’s Go** appears in the game’s internal browser. **Click Let’s Go** to enter the game.

**The X in step 2 is inside the in-game browser panel.** It is not the red close button on the external Mac sign-in window. Closing the external window may leave the game unresponsive and require a restart; the app asks for confirmation before closing it.

You can also open **How to enter the game…** in the launcher to read these instructions while playing.

Use MCD1 Crossover each time you play so the app can prepare its sign-in helper. Opening the launcher alone does not start the game—you must click **Play**. The launcher stays available while you play.

**Quit through the game’s own Quit menu when finished.** Closing the game window directly has caused problems in testing.

## Account and settings

- **Xbox account** in the launcher shows the last confirmed display name. The external window can also show **Logged in as: …** once that name is available. These are display labels, not proof that the current session is authenticated.
- **Use Another Account** in the external sign-in window lets you start signing in with a different Microsoft account.
- **Prefer Windowed Mode** requests windowed startup. The launcher backs up the game’s display configuration before changing its fullscreen-mode entries.
- **Choose…** lets you select the game copy in the chosen bottle.

The sign-in correction is applied to the running game. It does not replace CrossOver’s credential DLL. Game saves and macOS audio settings are not changed. The external sign-in window keeps its browser session data so a saved account can be reused, but Microsoft may still request authentication.

## Updates

Choose **Check for Updates…** from the app menu. Versions with the built-in updater can download, verify, replace and reopen the app without a manual reinstall. Updates wait for the game and sign-in to finish.

If your older preview has no update menu, download the current DMG and replace the app in Applications.

## Troubleshooting

- **Internal Microsoft browser:** close it using its own **X**, then click **Press Any Button** again. Continue in the external window.
- **External window closed, but you are not in the menu:** look for **Let’s Go** in the in-game browser and click it.
- **External sign-in failed to load:** use **Try Again** in that window. Closing it may leave the game unresponsive.
- **Game ignores input after closing sign-in:** restart the game. The close confirmation is a warning, not a fix for this problem.
- **Internal Error: 1234:** expand **See details…**. It explains what was checked, what was expected, what was found or failed, and what to try next. The [error-code catalog](docs/error-codes.json) lists the stable support codes.
- **Cannot launch or still stuck:** click **Save Logs…** in the launcher and attach the file to an [issue](https://github.com/Wanzho/mcd1-crossover/issues/new). Include the error code, macOS and CrossOver versions, and the step where it failed. Save Logs is available even when Play is disabled.

Launcher logs retain diagnostic events across launches. They are designed to exclude account names, passwords, sign-in URLs and tokens; the game’s network traffic is not recorded. Review any file or screenshot before sharing it publicly.

## Preview status

Earlier builds have reached the game’s main menu through the app’s external Microsoft sign-in flow, including reuse of a saved account and an account-switch test. This does not establish that every launch or every CrossOver build works.

The current changes have passed offline checks for credential compatibility, helper readiness, error handling and diagnostic export. The updated guide does not change the sign-in helper. A fresh end-to-end gameplay test of this preview has not been completed.

Known limits include inconsistent first-attempt sign-in, possible input loss after cancelling or closing sign-in, and incomplete long-session and multiplayer validation. Startup without an available sound output is not fully validated across Macs.

Unofficial project. Not affiliated with Mojang, Microsoft or CodeWeavers.

## Credits

Coded with Codex. Original README by Claude Opus 5.5; updated for the current preview with Codex. App icon made with image generation; source artwork and prompt are in `assets`.

MIT License.
