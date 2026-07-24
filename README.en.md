# MediaSlim

[简体中文](README.md) · **English**

**Smaller images. Your privacy stays on your Mac.**

MediaSlim is a local image compression app for macOS that reduces PNG and JPEG
file sizes while preserving visual quality. Nothing is uploaded—just drag in
images or folders to get started.

[Download the latest version](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest) · [View the changelog](CHANGELOG.md)

## Features

- Supports PNG, JPG, and JPEG, with multiple images in a single batch.
- Accepts entire folders and automatically finds compressible images inside.
- **All processing happens locally; your images are never uploaded.**
- Never modifies or overwrites originals; a copy is created only when the compressed result is smaller.
- Shows live progress, before-and-after file sizes, and savings.
- Lets you cancel a batch at any time and quickly reveal output files in Finder.
- Supports Simplified Chinese and English interfaces, plus in-app automatic updates.

## Compression results: MediaSlim vs TinyPNG

We compared MediaSlim and TinyPNG image by image on a mixed public and
real-world corpus of 79 PNG and 94 JPEG files, using SSIMULACRA2, SSIM, PSNR,
and controlled human blind tests:

- **JPEG:** MediaSlim guarantees a perceptual quality floor for every image (SSIMULACRA2 ≥ 72) and produces files **15% smaller** than TinyPNG at the same quality floor on the public corpus.
- **PNG:** After excluding the 9 images that TinyPNG returned untouched, output sizes are effectively on par (MediaSlim +1.9%), while MediaSlim has a slightly better paired-quality median and a stronger worst-5% quality floor.
- **Privacy:** MediaSlim processes everything locally and works offline; TinyPNG uploads images to the cloud.
- **Known weakness:** MediaSlim trails TinyPNG slightly on text/UI PNG screenshots.

The full reports include the methodology, enlarged visual comparisons, and
per-image CSV data:
**[中文版](docs/comparison-vs-tinypng.zh-CN.md)** · **[English](docs/comparison-vs-tinypng.en.md)**

## System requirements

- macOS 13 Ventura or later.

## Installation and usage

1. Go to [Releases](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases/latest) and download the latest DMG.
2. Open the DMG and drag MediaSlim into the Applications folder.
3. Launch the app, then drag in images or folders; you can also add them from the File menu.
4. When compression finishes, click “Show in Finder” to view the results.

MediaSlim creates a `Compressed` folder next to each original image. If a file
with the same name already exists, the app chooses a new filename to avoid
overwriting it. If compression does not reduce the file size, the original is
kept and no unnecessary copy is created.

## Privacy and security

### Images stay on your Mac

**MediaSlim never uploads images to a remote server.** Reading, compression,
and writing all happen on your Mac, so your original images never leave the
device.

### Verified by Apple security checks

Official DMGs and apps are signed with an Apple Developer ID and notarized by
Apple. Release packages are scanned for known malware; during installation and
first launch, macOS Gatekeeper also verifies the developer identity, code
signature, and file integrity. In-app updates are additionally verified with a
Sparkle signature to ensure that update packages come from a trusted source
and have not been modified.

## Updates

MediaSlim uses Sparkle to check for stable releases. You can also choose
“Check for Updates…” from the app menu or visit
[Releases](https://github.com/jojoTechWorkshop/MediaCompressRelease/releases).
See [CHANGELOG.md](CHANGELOG.md) for the full version history.

## About this repository

This repository distributes MediaSlim installers, release notes, and in-app
updates. It does not contain the application's source code.
