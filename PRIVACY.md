# Privacy Policy

_Last updated: April 22, 2026_

Cliply is an open-source desktop video downloader. We respect your privacy and keep data collection to an absolute minimum. This page explains exactly what we collect, why, and how you can opt out.

## TL;DR

- We do **not** collect your name, email, IP address, or any account information.
- We do **not** track browsing, see the videos you download, or scan your files.
- We **do** collect anonymous crash and usage stats so we can fix bugs and keep the app working.
- Everything happens on your device. Downloads go directly from the source to your disk — nothing passes through our servers.

## What we collect

When the app is running, Cliply sends a small amount of anonymous telemetry to [Aptabase](https://aptabase.com) (an open-source, privacy-friendly analytics service hosted in the EU). Specifically:

### `download_completed` event
- Type of download (`combined`, `audio`)
- Platform (`youtube`, `pinterest`, `tiktok`)
- Video title (truncated, from the public metadata of the video you downloaded)
- Selected format/quality (e.g. `1080p`)
- File size in MB

### `download_failed` event
- Same fields as above, plus:
- The raw error message returned by yt-dlp or FFmpeg, with your user folder replaced by `~` before it leaves your machine (so `C:\Users\Jane Smith\...` becomes `C:\Users\~\...`).

### Automatic metadata added by Aptabase
- App version (e.g. `1.4.2`)
- Operating system and version (e.g. `macOS 14.5`)
- System locale (e.g. `en-IN`)
- A random anonymous session ID that resets every few hours
- Country, derived from your IP. **Your IP address itself is never stored.**

That's the complete list. No other telemetry is emitted by the app.

## What we do NOT collect

- Your name, email, or any login credentials (there are no accounts in Cliply).
- The URLs you paste into the app.
- The contents of your downloads folder.
- Your IP address.
- Any browsing activity outside of Cliply.
- Any data from your browser cookies except when you explicitly enable the "Import cookies" feature — in which case the cookies are used **locally on your machine** to authenticate with YouTube and are never transmitted to us.

## How downloads work

When you paste a URL and hit download, the request goes **directly from your machine to the video platform** (YouTube, Pinterest, TikTok, etc.). The video file lands in your chosen folder. None of this traffic passes through any Cliply server. We don't run one.

## Where the data is stored

Anonymous analytics events are sent to Aptabase's EU infrastructure. Aptabase is GDPR-compliant and does not use cookies or cross-site tracking. You can read their privacy stance at <https://aptabase.com/legal/privacy>.

## How to opt out

Cliply is open source. If you'd like to run a build with telemetry fully disabled, set `ANALYTICS_CONFIG.ENABLED` to `false` in [`src/main/utils/constants.js`](src/main/utils/constants.js) and build from source:

```bash
npm run dist:mac   # or dist:win / dist:linux
```

A settings toggle for this is on the roadmap.

## Data retention

Analytics events are kept by Aptabase for up to 12 months for trend analysis, then deleted.

## Your rights

Because we don't collect any personal identifiers, there's nothing tied to you that we could look up, export, or delete. If you still have a question, open an issue on GitHub or reach out via [cliply.space/hey](https://cliply.space/hey).

## Changes to this policy

If we change what the app collects, we'll update this file and note the date at the top. Since Cliply is open source, every change to telemetry is visible in the commit history.

## Contact

Questions? Open an issue at <https://github.com/cliplydotspace/cliply> or contact us via [cliply.space/hey](https://cliply.space/hey).
