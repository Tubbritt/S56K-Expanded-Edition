# Downloads & releases

[Home](../README.md) · [Release history](../CHANGELOG.md) · [Installation](../docs/INSTALLATION.md) · [Windows USB guide](../docs/USB-UPDATER.md) · [Freeware licence](../LICENSE.md) · [Disclaimer](../DISCLAIMER.md)

## Choose your download

The operating system runs on your sampler. **Download V1.1 and install from floppy.** The optional Windows updater is unchanged: version 1.0 RC1 accepts original Akai v2.14 and the previous Expanded V1, and **rejects V1.1**.

| Release | Download | Instructions |
| --- | --- | --- |
| **Expanded Edition V1.1** · S5000 / S6000 | [S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.1/releases/firmware/v1.1/S56K-EX.bin) · 1 MiB | [Release notes](v1.1.md) · [Install](../docs/INSTALLATION.md) |
| **Firmware Updater 1.0 RC1** · Windows 11 x64 | [Windows ZIP](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip) · 1,001,521 bytes | [Release notes](updater-1.0-rc1.md) · [Driver setup & use](../docs/USB-UPDATER.md) |
| **Illustrated manual** | [PDF user guide](../docs/S56K-Expanded-Edition-User-Guide.pdf) | Sampling, looping, floppy installation and USB driver/update instructions |

The updater is a release candidate and is unsigned. Its user-confirmed S6000 / Windows 11 Pro 25H2 USB round-trip used Expanded V1, not V1.1. The owner has now reported successful V1.1 flashing after receiving the floppy procedure; model-specific and USB coverage are described in the compatibility record. An IB-S56USB card and WinUSB driver are required; USB is not needed for the firmware's sampling features. See [compatibility](../docs/COMPATIBILITY.md).

## Check your download

The V1.1 release links its **[SHA256SUMS.txt](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.1/releases/firmware/v1.1/SHA256SUMS.txt)** in the tagged versioned download folder. The updater checksum remains with its existing tagged download. The primary files are identified by these SHA-256 values:

**S56K-EX.bin** — 1,048,576 bytes

```text
cc3f6c056e0fb032303ee61f2e16c419c22708377cf888f0c1737be74321df93
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

- The **V1.1 firmware release** links the shared OS BIN and checksum from the immutable `expanded-v1.1` tag in `releases/firmware/v1.1/`, plus the current PDF manual and notices. Use those named download links; the release has no separate binary attachments.
- The **updater release** links the unchanged tested Windows app ZIP and its checksums in `releases/updater/1.0-rc1/`, plus the PDF manual. Extract the ZIP before running the app. Firmware is downloaded separately.
- The tested ZIP's bundled `START_HERE.html` predates the successful hardware test. The [current USB guide](../docs/USB-UPDATER.md), PDF and release notes include the updated status.

[All GitHub Releases →](https://github.com/Tubbritt/S56K-Expanded-Edition/releases)

## About this repository

The [release history](../CHANGELOG.md) tracks the firmware and updater separately, with features, dates and links to each version's detailed notes. Previous versions remain identifiable by their tags and checksums. Documentation and licensing updates do not change the released binaries. See [Preparing the next release](../docs/RELEASE-PROCESS.md) for the publication checklist.

This repository distributes compiled downloads, documentation and artwork. Firmware and app source code, build tools and reverse-engineering material are maintained elsewhere. Firmware and updater downloads use immutable tagged copies in versioned **releases/** folders, linked from their GitHub Releases. The previous firmware BIN has been removed from the current repository files; its original tag and historical release remain intact.

GitHub automatically adds **“Source code” ZIP/TAR** links to releases. These are whole-repository snapshots containing documentation and compiled downloads; they do not contain firmware or app development source. Use the explicitly named BIN or updater ZIP above to get the correct file directly.

Read the [installation guide](../docs/INSTALLATION.md), [compatibility notes](../docs/COMPATIBILITY.md) and [disclaimer](../DISCLAIMER.md) before installing.

Use and unchanged sharing of the project's own material are covered by the [Freeware Licence](../LICENSE.md). Keep that licence, the [third-party notices](../THIRD-PARTY-NOTICES.md) and the disclaimer with redistributed copies. Original Akai software and other third-party components retain their own rights and terms. The project's own firmware and app source code will not be published or included in releases.
