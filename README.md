# AntiAFKPresser — AFK Key Presser & Anti-Idle Keep-Alive for Windows

![AntiAFKPresser — screenshot](AntiAFKPresser.png)

**A tiny Windows utility that keeps your PC and apps looking active while you step away.** Set an interval, choose an invisible key, and AntiAFKPresser quietly taps it so your session never goes idle. No ads, no telemetry — a small `.msi` installer.

If you have been searching for an **afk key presser download**, this is the simple, ban-safe answer: a clean keep-alive tool that presses a chosen key at a fixed interval and, optionally, nudges the mouse and blocks sleep. It lives in the system tray and stays out of your way.

## Why AntiAFKPresser

Idle timers are everywhere — screensavers, auto-lock, "away" status in chat apps, sleep and display timeouts. AntiAFKPresser sends a single, invisible keystroke on a timer so the system keeps seeing genuine activity. By default it presses **F13**, a real keyboard key that virtually nothing is mapped to, so the keep-alive tap has no visible effect on your documents, terminals or games.

- **Invisible by default** — presses **F13** (or **F15**, or any custom key) through the Windows `SendInput` API with hardware scan codes, so it registers as real input everywhere, including remote-desktop and full-screen sessions.
- **Simple interval** — "Press every N minutes", adjustable from **30 seconds to 60 minutes**.
- **Optional 1px mouse nudge** — a net-zero micro-move (right 1px, back 1px) for apps that watch the pointer as well as the keyboard.
- **Keep Windows awake** — an optional wake-lock (`SetThreadExecutionState`) that blocks sleep, display-off and the screensaver while it runs.
- **One-click presets** — **Office**, **MMO** and **Corp PC** set a sensible key + interval instantly.
- **Tray-first** — starts and stays in the system tray; closing the window keeps it running. Right-click the tray icon to toggle or exit.
- **Big ON/OFF indicator** — a clear status panel with a green dot when the keep-alive is active.
- **Remembers your setup** — settings are saved to `profiles.json` and restored on the next launch.
- **Simple install** — a small `.msi` package, runs on Windows 10 / 11 (.NET Framework 4.8, preinstalled).

## Anti afk software for Windows — how it works

AntiAFKPresser is a straightforward **anti afk software windows** helper. On each interval it:

1. Injects one key **down** + key **up** for your chosen key via `SendInput` (scan-code mode).
2. Optionally moves the mouse **+1px then −1px** so the cursor position is unchanged.
3. Optionally re-asserts the "keep awake" wake-lock so the machine will not sleep or dim.

Nothing is injected into other programs and nothing reads another program's memory — the tool only generates ordinary keyboard and mouse input, exactly as if you had tapped the key yourself.

## Keep PC awake tool — presets

| Preset | Key | Interval | Mouse ±1px | Keep awake | Good for |
|---|---|---|---|---|---|
| **Office** | F13 | 4 min | off | off | staying "available" in chat / staying signed in |
| **MMO** | F13 | 3 min | off | off | multi-game sessions and idle-sensitive clients |
| **Corp PC** | F13 | 2 min | on | on | a locked-down **keep pc awake tool** for managed machines |

## Download

1. Download `AntiAFKPresser.zip`
2. Unzip it anywhere
3. Run `AntiAFKPresser.msi` and follow the installer

## Quick start

1. **Pick a key** — leave it on **F13 (invisible)** for a no-effect keep-alive, or choose **F15** / **Custom**.
2. **Set the interval** — e.g. `Press every: 5 minutes`.
3. *(Optional)* tick **Also move mouse ±1px** and/or **Keep Windows awake**.
4. **Turn ON.** The dot turns green and the app drops to the tray. Turn OFF any time.

## Settings & storage

Your last configuration (key, interval, options, preset) is written to:

```
%LOCALAPPDATA%\AntiAFKPresser\profiles.json
```

Delete that file to reset to defaults.

## Safety & transparency

- Uses only the standard, documented Windows input APIs (`SendInput`, `SetThreadExecutionState`).
- No bundled services, no network access, no telemetry.
- Uninstall any time from Windows Settings ▸ Apps.
- Open-source under the MIT License (see `LICENSE`).

## Disclaimer

This is a general-purpose keyboard utility. Not affiliated with any game. Use it in line with the terms of service of any software you run it alongside, and only on machines you own or are authorized to use.

## License

MIT — see [LICENSE](LICENSE).
