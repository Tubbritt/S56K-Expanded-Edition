# Downloads & releases

[Home](../README.md) · [Installation](../docs/INSTALLATION.md) · [Windows USB guide](../docs/USB-UPDATER.md) · [Disclaimer](../DISCLAIMER.md)

## Choose your download

The operating system runs on your sampler. The optional Windows app installs it over USB. Download both for USB installation, or just the BIN for floppy loading and installation.

| Release | Download | Instructions |
| --- | --- | --- |
| **Expanded Edition v1** · S5000 / S6000 | [S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1/releases/firmware/v1/S56K-EX.bin) · 1 MiB | [Release notes](v1.md) · [Install](../docs/INSTALLATION.md) |
| **Firmware Updater 1.0 RC1** · Windows 11 x64 | [Windows ZIP](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip) · 1,001,521 bytes | [Release notes](updater-1.0-rc1.md) · [Driver setup & use](../docs/USB-UPDATER.md) |
| **Illustrated manual** | [PDF user guide](../docs/S56K-Expanded-Edition-User-Guide.pdf) | Sampling, looping, floppy installation and USB driver/update instructions |

The updater is a release candidate and is unsigned. It has a user-confirmed physical round-trip on the established S6000 / Windows 11 Pro 25H2 setup. An IB-S56USB card and WinUSB driver are required; USB is not needed for the firmware's sampling features. See [compatibility](../docs/COMPATIBILITY.md).

## Check your download

Each versioned download folder includes a **SHA256SUMS.txt** file, linked from its GitHub Release. The primary files are identified by these SHA-256 values:

**S56K-EX.bin** — 1,048,576 bytes

```text
5b2559d3137f29516130572c754c5cf1be45058a25d70cff5fbbc221944e7f2a
```

**S56K-Firmware-Updater-1.0-RC1-win64.zip** — 1,001,521 bytes

```text
bcb49f0354e3a9b5eaf043ed17b8a346bb5acf6a35193d3ec9cef33f0566375c
```

In PowerShell, change to the download folder and run:

```powershell
Get-FileHash .\S56K-EX.bin -Algorithm SHA256
Get-FileHash .\S56K-Firmware-Updater-1.0-RC1-win64.zip -Algorithm SHA256
```

Letter case does not matter when comparing hashes. Stop if any character differs. A matching hash identifies the downloaded file; it is not a guarantee against an interrupted flash or a hardware fault.

## What is included

- The **firmware release** links the shared OS BIN and its checksums in `releases/firmware/v1/`, plus the PDF manual.
- The **updater release** links the unchanged tested Windows app ZIP and its checksums in `releases/updater/1.0-rc1/`, plus the PDF manual. Extract the ZIP before running the app. Firmware is downloaded separately.
- The tested ZIP's bundled `START_HERE.html` predates the successful hardware test. The [current USB guide](../docs/USB-UPDATER.md), PDF and release notes include the updated status.

[All GitHub Releases →](https://github.com/Tubbritt/S56K-Expanded-Edition/releases)

## About this repository

This repository distributes compiled downloads, documentation and artwork. Firmware and app source code, build tools and reverse-engineering material are maintained elsewhere. Binary downloads live in versioned **releases/** folders and are linked from the corresponding GitHub Releases. Each release links to its tagged copy so later documentation edits do not change that download.

GitHub automatically adds **“Source code” ZIP/TAR** links to releases. These are whole-repository snapshots containing documentation and compiled downloads; they do not contain firmware or app development source. Use the explicitly named BIN or updater ZIP above to get the correct file directly.

Read the [installation guide](../docs/INSTALLATION.md), [compatibility notes](../docs/COMPATIBILITY.md) and [disclaimer](../DISCLAIMER.md) before installing.
