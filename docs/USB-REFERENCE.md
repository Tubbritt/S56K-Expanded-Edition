# USB firmware updates · reference

[Visual walkthrough](USB-UPDATER.md) · [Compatibility](COMPATIBILITY.md) · [Disclaimer](../DISCLAIMER.md)

## About this version

The app is **1.0 RC1** and is unsigned. Windows may show an unknown-publisher or SmartScreen warning; check the download source and checksum rather than disabling Windows security or driver-signature enforcement. The reported physical test used an S6000 and Windows 11 Pro 25H2; see [compatibility](COMPATIBILITY.md) for coverage.

The unchanged tested ZIP includes its original `START_HERE.html`, packaged before the subsequent successful hardware round-trip. The visual guide and compatibility page give current instructions and test status. Windows on ARM and other Windows versions have not been verified.

## Driver fallback: WinUSB unavailable or no registered interface

Some Windows configurations need an additional interface registration. Use this fallback only when the Device Manager method is unavailable or leaves the app reporting no registered interface.

1. Download **Zadig** from **[zadig.akeo.ie](https://zadig.akeo.ie/)** and run it. Driver installation normally requires administrator approval.
2. Choose **Options → List All Devices**, select the Akai sampler and confirm **USB ID `09E8 005E`**. Do not select a keyboard, mouse, hub or another device.
3. Choose **WinUSB** as the target driver and click **Install Driver** or **Replace Driver**. Do not choose libusb-win32 or libusbK for this app.
4. Close Zadig, reconnect USB and try **Refresh → Connect** again in the updater.

Both methods assign Microsoft's WinUSB to the sampler; Zadig is an optional setup helper, not a new driver requirement. See [Microsoft's WinUSB installation documentation](https://learn.microsoft.com/en-us/windows-hardware/drivers/usbcon/winusb-installation) for interface-registration details.

**What this changes:** the Windows driver association, not the sampler's firmware. The updater itself does not install drivers or edit their registry settings. You do not need to disable driver-signature enforcement. Assigning WinUSB does not make unmodified ak.Sys work; ak.Sys requires its separate compatibility setup and may stop recognising a device previously using its legacy driver. This updater needs neither ak.Sys nor its shim.


## Supported files

Both firmware files are **1,048,576 bytes**. Renaming a recognised file is fine; editing it or using a different revision causes rejection. The published Expanded BIN is the same tested image, with EX artwork revision 2.

| Firmware | SHA-256 |
| --- | --- |
| **Expanded Edition v1 — `S56K-EX.bin`** | `5b2559d3137f29516130572c754c5cf1be45058a25d70cff5fbbc221944e7f2a` |
| **Original Akai v2.14 — `s56v214.bin`** | `05e466a7a19e5abde1e53660e0069bf2fb34bb33f705841185883a78b5369402` |

The factory BIN is recognised for restoration but is not included in these downloads. Retain your original Akai image if you need that option. Other firmware revisions require an updater that explicitly supports them; do not bypass the file checks.

To check a download in PowerShell, run `Get-FileHash .\S56K-EX.bin -Algorithm SHA256` and compare the result with the table or the release's `SHA256SUMS.txt`. The updater ZIP's SHA-256 is:

`bcb49f0354e3a9b5eaf043ed17b8a346bb5acf6a35193d3ec9cef33f0566375c`

**Updating from factory OS:** the running sampler OS performs the flash write. Factory v2.14 has weaker memory-allocation and final-byte verification checks than Expanded Edition. Selecting Expanded on the PC cannot apply those fixes before the new OS is running. The successful stock-to-Expanded hardware test establishes that route works on the tested setup; it does not remove those older checks' limitations. Always start with a freshly booted, unloaded sampler.

## Troubleshooting

| What you see | What to do |
| --- | --- |
| **No sampler listed** | Check power, the IB-S56USB card, USB cable and direct PC port. Confirm the Akai hardware IDs in Device Manager, then click Refresh. |
| **Driver missing / WinUSB not assigned** | Use the Device Manager steps in the [visual guide](USB-UPDATER.md) for `09E8:005E` only. |
| **No usable interface registered** | Use Zadig to install a device-specific WinUSB association, reconnect USB and refresh. |
| **Cannot open / access denied / connection busy** | Close ak.Sys and other sampler USB tools. Reconnect USB and try Connect again before installation. |
| **Timeout during Connect** | Save the report. Check cable and power; close competing tools. If needed, save sampler work and restart it before trying again. This advice applies before an update, not during flash writing. |
| **BIN rejected** | Download the exact supported BIN and check its SHA-256. Do not use an older test build, ZIP file or GitHub “Source code” archive. |
| **Install disabled after a completed update** | This is intentional. Close and reopen the app for a new session. |

**If an update fails after erasure may have started:** leave the sampler powered on initially, save the report and note its display. The OS in flash may be incomplete. Do not repeatedly retry or assume a power-cycle will fix it. Share the error with the project owner before further attempts; recovery may require the established floppy procedure. The updater cannot repair a sampler whose application cannot start USB services, and preserving the boot block does not guarantee recovery.

Use **Save report** to export the session. The app also attempts to save logs under `%LOCALAPPDATA%\S56K\FirmwareUpdater\Logs`. Reports contain device identifiers, file paths, firmware hashes and status; review them for personal paths before posting publicly. Nothing is uploaded automatically.

[Download releases](../releases/README.md) · [Full compatibility notes](COMPATIBILITY.md) · [Report an issue](https://github.com/Tubbritt/S56K-Expanded-Edition/issues)
