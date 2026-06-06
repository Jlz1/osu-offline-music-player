# osu! Offline Music Player

A lightweight, single-file web app that turns your **osu!lazer** song library into an offline music player — like Spotify, but for the maps you already have.

![status](https://img.shields.io/badge/offline-100%25-1ed760) ![client](https://img.shields.io/badge/osu!-lazer-ff6ba9)

## Features

- 🎵 **Offline playback** straight from osu!lazer's own storage
- 🔄 **Auto-updates** — reads osu!'s live database each time you open it. Add maps in osu!, hit **Refresh**, and they appear
- 💾 **Zero duplication** — never copies your songs; streams them directly from osu!'s `files/` folder
- 🚫 **Ad-free** — no ads, no tracking, no telemetry, ever
- 🔎 **Search** by title, artist, or source
- 🎨 **Cover art** pulled from each beatmap's background
- ⏯️ Play/pause, next/previous, shuffle, repeat (all/one), seek, volume
- ⌨️ Keyboard shortcuts — `Space` = play/pause, `Ctrl + ← / →` = previous/next
- 📦 One self-contained HTML file (~22 KB) — no install, no dependencies

## How it works

osu!lazer doesn't store songs in normal folders — it uses a content-addressed `files/` store plus a Realm database (`client.realm`). This app includes a **from-scratch JavaScript reader for the Realm file format**: it parses the database to map each song to its audio and cover files, reads metadata from the `.osu` beatmap files, and plays the audio directly. Everything runs locally in your browser.

## Get it

**Just want to use it (no coding):**

1. On the repo page, click the green **Code** button → **Download ZIP**.
2. Unzip it anywhere (your Desktop is fine).
3. Double-click **`osu-music-player.html`** — it opens in your browser. That's it.

> Prefer a single file? Open `osu-music-player.html` in the repo and click the download (⬇) button to grab just that file.

**For developers — clone with Git:**

```bash
git clone https://github.com/Jlz1/osu-offline-music-player.git
cd osu-offline-music-player
```

Then open **`osu-music-player.html`** in Chrome or Edge — double-click it, or on Windows run `start osu-music-player.html`. There's no build step and no dependencies; it's a single static HTML file.

## Usage

1. Open `osu-music-player.html` in **Google Chrome** or **Microsoft Edge**.
2. Click **Open osu! folder** and select your osu!lazer data folder — usually `C:\Users\<you>\AppData\Roaming\osu` (the folder containing `client.realm` and the `files` folder).
3. When the browser asks to *"Upload"* the folder, confirm. Nothing is uploaded anywhere — that's just Chrome's wording for local read access.
4. Your library appears. Click any track to play.

> **Tip:** After adding new maps in osu!, just click **Refresh** to update the library.

## Requirements

- **osu!lazer** (not osu! *stable*). This app reads the lazer `client.realm` format; the legacy stable client stores songs differently.
- A Chromium-based browser (Chrome / Edge) for the offline folder picker.

## Privacy

100% offline and **completely ad-free**. No data ever leaves your computer — no servers, no telemetry, no network calls, and no advertisements anywhere in the app. It only reads your local osu! files.

## Credits

Built by **Jeremy ([@Jlz1](https://github.com/Jlz1))**, co-authored with **Claude** (Anthropic).

## Disclaimer

This is an unofficial, fan-made tool and is **not affiliated with, endorsed by, or connected to osu! or ppy Pty Ltd.** "osu!" is a trademark of its respective owner.

The app ships with no game code, beatmaps, or audio — it only reads files already on your own computer. You're free to use, modify, and share **the app itself** under the MIT license. Please **do not redistribute the songs/audio** played through it; those belong to their respective copyright holders.

## License

[MIT](LICENSE)
