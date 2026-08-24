# STM Desktop Listener downloads

Download the latest precompiled STM Desktop Listener release for Apple silicon Macs running macOS 14 or later.

[Download the latest release](https://github.com/demetre19/STM-Desktop-Listener-Releases/releases/latest)

Each release provides a versioned DMG, ZIP, and `SHA256SUMS.txt`. Users do not need Xcode, Command Line Tools, Git, or the private source repository.

Initial packages are ad hoc signed and are not Apple-notarized. Installation remains a manual user action. Verify the downloaded package before opening it:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

STM Desktop Listener checks this public release channel for stable and prerelease updates. Draft releases are ignored. The app can download and verify a DMG, but it never installs or replaces itself.
