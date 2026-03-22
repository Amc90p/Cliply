### macOS

When opening Cliply for the first time, you might see a security warning because macOS Gatekeeper blocks unsigned apps by default. This is because we haven't added code signing yet. It requires a paid certificate, and as a small project, we're prioritizing what matters most first.

To open the app, you can safely run this command in Terminal to remove the security restriction:

```bash
sudo xattr -rd com.apple.quarantine /Applications/Cliply.app
```

**What this does:** It removes the "downloaded from the internet" flag from Cliply, telling macOS that you trust the app.

**Safety tips:**

* Only run this command on apps from trusted sources, like the official GitHub release.
* Optionally, scan the downloaded file with VirusTotal or similar tools.

For a **detailed, step-by-step explanation of this command and why it's safe**, see this guide: [Google Gemini](https://g.co/gemini/share/14f63c8b12b6)
