# STM Desktop Listener downloads

Download the latest precompiled STM Desktop Listener release for Apple silicon Macs running macOS 14 or later.

[Download the latest release](https://github.com/demetre19/STM-Desktop-Listener-Releases/releases/latest)

Each release provides a versioned DMG, ZIP, and `SHA256SUMS.txt`. Users do not need Xcode, Command Line Tools, Git, or the private source repository.

Initial packages are ad hoc signed and are not Apple-notarized. Installation remains a manual user action. Verify the downloaded package before opening it:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

STM Desktop Listener checks this public release channel for stable and prerelease updates. Draft releases are ignored. The app can download and verify a DMG, but it never installs or replaces itself.

## What's new in v0.2.9

- **Repeat Last Screenshot** (default `Cmd+Shift+5`): recaptures the exact region of your previous screenshot without drawing the selection again.
- **Word substitutions**: teach STM your vocabulary in Settings > Voice AI (or the Word Substitutions button on the popover's Dictation card). One `heard phrase = replacement` pair per line, applied to every dictation before punctuation.
- **Cleaner dictation output**: the guarded punctuation pass now reverts invented mid-sentence capitals, drops stray commas away from clause boundaries, merges bogus one-word sentence splits, and always capitalizes the pronoun "i".
- **Settings cog**: a white gear icon next to the popover's quit button opens Settings in one click.

## Dictation engines

- **Cloudflare Worker (default and preferred):** fast, accurate transcription through your configured Worker credentials.
- **Qwen3-ASR 0.6B local backup (optional):** choose **Settings > Voice AI > Qwen3-ASR 0.6B (local)** to download and install the pinned 8-bit model. Cloudflare credentials are not required while the local engine is selected. Every download is verified by exact size and SHA-256 before installation, the model runs entirely on your Mac, and transcripts still pass through the bundled guarded punctuation and capitalization model.

Every dictation, cloud or local, uses the bundled local Edge-Punct-Casing model afterward. STM accepts its punctuation and capitalization only when the recognized word sequence is unchanged, so the transcript is never rewritten by a general chat model.

## Requirements

- Apple silicon (arm64) Mac. Intel Macs are not supported by the current precompiled packages.
- macOS 14 or later.
- Cloudflare Worker credentials only for cloud dictation and Private Drive features; the local Qwen backup works without them.
- Brave or Chrome plus the STM extension is needed only for scrolling-capture and image-optimiser bridge workflows.
