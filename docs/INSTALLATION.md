# Installing S56K Expanded Edition V1.1

[Home](../README.md) · [Downloads](../releases/README.md) · [USB updater guide](USB-UPDATER.md) · [Compatibility](COMPATIBILITY.md) · [Flashing disclaimer](../DISCLAIMER.md)

The firmware image is **S56K-EX.bin**, shared by the AKAI S5000 and S6000. The boot screen selects the correct model graphic automatically and displays **EXPANDED EDITION V1.1**. The underlying AKAI operating-system identity remains **2.14**.

**[Download V1.1 — S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.1/releases/firmware/v1.1/S56K-EX.bin)** · **[SHA256SUMS.txt](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.1/releases/firmware/v1.1/SHA256SUMS.txt)** · **[What changed](../releases/v1.1.md)**

**Use floppy for V1.1.** The existing Windows Firmware Updater **1.0 RC1 does not accept V1.1**. It recognises only the original Expanded Edition v1 and factory Akai v2.14 images. Its USB instructions remain available for those files; changing the filename does not add support for V1.1.

| Route | V1.1 support | What you need |
| --- | --- | --- |
| **Temporary floppy load** | Runs V1.1 for that session without replacing the installed OS. | A readable floppy containing the verified BIN. |
| **Floppy flash installation** | Permanently installs V1.1. | A verified floppy and stable power. |
| **Windows updater 1.0 RC1** | **Does not accept V1.1.** | See the [USB guide](USB-UPDATER.md) for its supported older images. |

USB is not needed for Auto Sample. The project owner reported successful V1.1 flashing on **2 November 2026**, following the supplied floppy test instructions. The report did not restate the sampler model or individual reboot checks; see the [compatibility record](COMPATIBILITY.md).

Read the [flashing disclaimer](../DISCLAIMER.md) before proceeding. Permanent installation carries a risk of an unusable sampler and possible repair costs.

## Before you begin

- Download the named firmware BIN and its checksum. Use **S56K-EX.bin**, not GitHub's automatic “Source code” archive of the entire repository.
- Back up your programs and samples to separate storage, and note customised settings. Flash installation can replace stored settings.
- Keep a known-working OS file and readable recovery disk. These do not guarantee recovery after a failed flash.
- Verify the BIN's SHA-256 checksum. The **1,048,576-byte V1.1** image is:

  `cc3f6c056e0fb032303ee61f2e16c419c22708377cf888f0c1737be74321df93`

  In Windows PowerShell, use `Get-FileHash .\S56K-EX.bin -Algorithm SHA256`.

- Use a known-readable floppy, a reliable drive and stable power. Copy **S56K-EX.bin** to the disk with no other OS BIN files present. This is a file copy, not a raw disk image. Read the copied file back on the computer and verify its checksum again. Stop if it cannot be read or its checksum differs.
- Close ak.Sys, the Editor and other sampler USB tools. Disconnect computer USB for this floppy installation; the instrument's MIDI and audio connections can remain connected.

## 1. Load temporarily from floppy

1. Insert the prepared floppy and switch on the sampler.
2. Allow it to read the OS. Confirm **EXPANDED EDITION V1.1** appears on the boot screen. At **Write Flash OS**, select **NO** to continue without permanently installing it.
3. Check normal navigation. Open an empty test program, then **Program Tools → Auto Sample**. Make a short capture, audition it and check the controls you intend to use.
4. Save wanted work using the normal **SAVE** page before restarting.

If the V1.1 caption is absent or anything behaves unexpectedly, check the disk and exact file before considering installation. Choosing NO only dismisses the installation prompt; it does not load the BIN. The V1.1 caption confirms that the new image has already booted. A temporary boot leaves the existing installed OS in flash and does not prove that a flash write will succeed.

## 2. Install permanently from floppy

Proceed when the temporary load and checks have succeeded and you have accepted the installation risk.

1. Boot again using the same verified floppy and firmware file.
2. **On this boot, confirm EXPANDED EDITION V1.1 appears before selecting YES at Write Flash OS.** If the caption is absent or shows an older version, choose NO and stop. A flash prompt alone is insufficient: an older installed OS can also discover a BIN after a fallback boot. A successful temporary boot on the previous attempt does not confirm this boot's identity.
3. Allow writing and verification to finish. **Do not switch off, reset or remove media during the update.** Follow the sampler's completion instructions.
4. After successful completion, remove the floppy, switch off and restart. Confirm **EXPANDED EDITION V1.1** appears without the disk. This checks the OS stored in flash.
5. Check ordinary navigation and a short Auto Sample capture. Audition the attack, loop and release; save the program with its samples and reload it to check playback.

An update that reports an error is not a successful installation. Record the exact message before further action; do not assume a repeated update or a retained backup will recover every failure.

The normal Utilities **SAVE SETTINGS / SAVE TO FLASH** function stores settings. It does not install the OS. Use the boot-time **Write Flash OS** prompt above.

## 3. Windows USB installation compatibility

**V1.1 is not supported by Firmware Updater 1.0 RC1.** The app rejects its unlisted checksum before installation. Do not bypass the file checks or use a renamed file to try to enable it. Use the floppy procedure for this release.

The unchanged updater remains available for the original **Expanded Edition v1** and **Akai v2.14** images. Its historical successful USB round-trip used v1 on the established S6000 / Windows 11 Pro 25H2 setup. That result does not establish V1.1 USB installation, S5000 USB installation or installation through ak.Sys.

**[Supported USB files, driver setup and updater instructions →](USB-UPDATER.md)**

The official **2.14** version number remains the same across these images. Verify V1.1 by its full **EXPANDED EDITION V1.1** boot caption after restarting **without an OS floppy**.
