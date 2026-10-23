# S56K Firmware Updater 1.0 RC1

[Home](../README.md) · [Downloads](README.md) · [Release history](../CHANGELOG.md) · [Windows USB guide](../docs/USB-UPDATER.md) · [Compatibility](../docs/COMPATIBILITY.md)

![Illustrated updater ready to install S56K-EX.bin](../assets/updater/ready-to-install.png)

*Illustrated adaptation of the supplied Windows screenshot. [Follow the three-step visual guide →](../docs/USB-UPDATER.md)*

**Install your sampler OS from Windows 11.** A standalone x64 USB updater for the AKAI S5000 and S6000 fitted with an IB-S56USB card. No ak.Sys installation or separate runtime is required.

**23 October 2026 · Release candidate · Unsigned**

**[Download Windows updater ZIP](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip) · [SHA256SUMS.txt](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/SHA256SUMS.txt) · [Driver setup and installation](../docs/USB-UPDATER.md)**

## What it does

- **Connect:** identifies a supported sampler and checks USB communication.
- **Choose BIN:** validates the entire file against the supported firmware hashes and holds a fixed copy for installation.
- **Install:** asks for confirmation, then displays erasing, transfer, checking and programming progress.
- **Save report:** stores useful connection and update details locally. Nothing is uploaded automatically.

The app blocks its own Close action during an update and asks Windows to stay awake. It cannot prevent forced termination, power failure or every interruption. USB installation writes flash and stored settings; it does not temporarily boot an OS into RAM.

## Supported files

RC1 accepts these two exact 1 MiB images:

| Image | SHA-256 |
| --- | --- |
| Expanded Edition v1 / EX artwork revision 2 | `5b2559d3137f29516130572c754c5cf1be45058a25d70cff5fbbc221944e7f2a` |
| Original Akai OS 2.14 | `05e466a7a19e5abde1e53660e0069bf2fb34bb33f705841185883a78b5369402` |

Download the [Expanded BIN separately](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1/releases/firmware/v1/S56K-EX.bin). The factory OS is not bundled in either release. Renaming an approved file is allowed; different revisions or modified files are rejected. The visible OS version remains 2.14 in both images.

## Verification

On 23 October 2026 the user confirmed a complete **Expanded → original Akai v2.14 → Expanded** USB round-trip after following the reboot and visual-check procedure. The established setup is an **S6000 with Windows 11 Pro 25H2**. This is user-reported hardware evidence; it does not establish S5000 USB, ak.Sys, Windows ARM or every PC/USB configuration.

Software checks covered the actual update engine against native firmware updater instructions, malformed transfers and status replies, WinUSB completion/error handling, and app workflows. These complement the physical test without guaranteeing a risk-free update. The app's completion message reports the sampler's acknowledgements; it does not independently read back the complete flash or verify the reboot.

## Package identity

The published ZIP and executable are unchanged from the tested build.

**ZIP** — 1,001,521 bytes

```text
bcb49f0354e3a9b5eaf043ed17b8a346bb5acf6a35193d3ec9cef33f0566375c
```

**S56K-Firmware-Updater.exe** — 3,221,320 bytes

```text
8af852f76ca16c8c1df251396abbb225a7ca8223e14cc18dfe6d1c7f8d51699f
```

The ZIP includes the app, its original setup HTML, icon assets and internal checksums. Its original setup guide says physical verification is pending because it was packaged before the successful test. Use the [current USB guide](../docs/USB-UPDATER.md) or the PDF accompanying this release for current instructions and test status.

## Practical limits

- Windows 11 on Intel/AMD x64; Microsoft WinUSB must be assigned to the correctly identified Akai USB device.
- The executable is not Authenticode-signed. Windows may display an unknown-publisher warning. Do not disable Windows security or driver-signature enforcement.
- The app permits one installation per session. Close and reopen it before a second installation.
- The running sampler OS performs flash programming. When factory v2.14 is running, its older allocation and comparison limitations still apply until the new OS runs.
- After success, remove any firmware floppy before rebooting and check the installed artwork and Auto Sample menu.
- The boot block is excluded, but there is no automatic rollback or guaranteed recovery.
- If an update fails after erasure may have started, leave the sampler powered on initially and save the report before attempting recovery.

Read the [full driver and updater guide](../docs/USB-UPDATER.md) and [disclaimer](../DISCLAIMER.md) before use.

The updater is free for personal and professional use under the [Freeware Licence](../LICENSE.md). Include that licence, the [third-party runtime notices](../THIRD-PARTY-NOTICES.md) and disclaimer when sharing unchanged copies. The project's own application source is private and will not be published. These accompanying notices do not change the tested ZIP or executable.
