# Installing S56K Expanded Edition

[Home](../README.md) · [Downloads](../releases/README.md) · [USB updater guide](USB-UPDATER.md) · [Compatibility](COMPATIBILITY.md) · [Flashing disclaimer](../DISCLAIMER.md)

The firmware image is **S56K-EX.bin**, shared by the AKAI S5000 and S6000. The boot screen selects the correct model graphic automatically and displays **EXPANDED EDITION v1**. The underlying AKAI operating-system identity remains **2.14**.

**[Download Expanded Edition v1 — S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1/releases/firmware/v1/S56K-EX.bin)** · **[Download Windows USB updater](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip)**

| Route | What it does | What you need |
| --- | --- | --- |
| **Temporary floppy load** | Runs the BIN for that session without replacing the installed OS. | A readable floppy containing the BIN. |
| **Floppy flash installation** | Permanently installs the OS. | A verified floppy and stable power. |
| **Windows USB updater** | Permanently installs the OS from your PC. | Windows x64, an IB-S56USB card and the WinUSB driver. Follow the [USB guide](USB-UPDATER.md). |

USB is not needed for Auto Sample. Temporary USB boot without writing flash is not supported by this tool.

Read the [flashing disclaimer](../DISCLAIMER.md) before proceeding. Permanent installation carries a risk of an unusable sampler and possible repair costs. Consult the [compatibility notes](COMPATIBILITY.md) for what has been tested on hardware.

## Before you begin

- Download the named firmware BIN and its checksum from the [release area](../releases/README.md). Use the named BIN download, not GitHub's automatic “Source code” archive of the entire repository.
- Back up your programs and samples to separate storage, and note customised settings. Flash installation can replace stored settings.
- Keep a known-working OS file and readable recovery disk. These do not guarantee recovery after a failed flash.
- Verify the BIN's SHA-256 checksum. The current **1,048,576-byte** image is:

  `5b2559d3137f29516130572c754c5cf1be45058a25d70cff5fbbc221944e7f2a`

  In Windows PowerShell, use `Get-FileHash .\S56K-EX.bin -Algorithm SHA256`.
- For floppy loading, use a known-readable disk, a reliable drive and stable power. Copy **S56K-EX.bin** to the disk with no other OS BIN files present. This is a file copy, not a raw disk image. Where possible, read the file back on the computer and verify its checksum again.

## 1. Load temporarily from floppy

1. Insert the prepared floppy and switch on the sampler.
2. Allow it to read the OS. At **Write Flash OS**, select **NO** to continue without permanently installing it.
3. Check the model-specific EX graphic, the **EXPANDED EDITION v1** caption and normal startup.
4. Open an empty test program, then **Program Tools → Auto Sample**. Make a short capture, audition it and check the controls you intend to use. Save wanted work using the normal **SAVE** page.

If the expected artwork or feature is absent, or anything behaves unexpectedly, check the disk and exact file before considering installation. A temporary boot leaves the existing installed OS in flash; it does not prove that a flash write will succeed.

## 2. Install permanently from floppy

Proceed when the temporary load and checks have succeeded and you have accepted the installation risk.

1. Boot again using the same verified floppy and firmware file.
2. At **Write Flash OS**, choose **YES** when ready to install.
3. Allow writing and verification to finish. **Do not switch off, reset or remove media during the update.** Follow the sampler's completion instructions.
4. Remove the floppy and restart when the update has completed. Confirm the EX boot artwork appears without the disk, then check ordinary operation and a short Auto Sample capture.

An update that reports an error is not a successful installation. Record the exact message and consult the instructions for that release; do not assume a repeated update or a retained backup will recover every failure.

## 3. Install permanently over USB

Use **S56K Firmware Updater 1.0 RC1** on Windows. It operates independently of ak.Sys and checks the exact firmware file before enabling installation.

1. Install or confirm **WinUSB** for the Akai device, USB ID **09E8:005E**.
2. Save work and settings, start with a freshly booted sampler without loaded libraries, and close other sampler USB tools.
3. In the updater, choose **Connect → Choose BIN… → Install firmware**.
4. Wait for the successful completion message. Remove any firmware floppy, restart the sampler and check the EX artwork and Auto Sample menu.

**[Follow the complete USB driver and updater instructions →](USB-UPDATER.md)**

The owner reported successful restoration to factory v2.14 and reinstallation of Expanded Edition using this tool on the established S6000 / Windows 11 Pro 25H2 setup. S5000 USB installation and installation through ak.Sys have not been separately verified. The USB tool writes stored settings as well as the OS; it does not offer a temporary RAM-only load.

The official **2.14** version number remains the same before and after the upgrade. Confirm the edition using the startup artwork and Auto Sample menu after restarting **without an OS floppy**. Close and reopen the updater before performing a second installation.
