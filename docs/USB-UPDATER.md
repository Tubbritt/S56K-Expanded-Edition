# USB firmware updates on Windows

[Home](../README.md) · [Downloads](../releases/README.md) · [Floppy installation](INSTALLATION.md) · [Compatibility](COMPATIBILITY.md) · [Disclaimer](../DISCLAIMER.md)

**S56K Firmware Updater** installs a supported OS directly from your Windows PC. It works independently of ak.Sys: connect the sampler, choose the BIN, then install. This writes the sampler's flash memory; it is not a temporary USB boot or a remote editor.

**[Download Firmware Updater 1.0 RC1 for Windows x64](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip)** · **[Download Expanded Edition v1 firmware](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1/releases/firmware/v1/S56K-EX.bin)**

The app and firmware are separate downloads. Extract the entire updater ZIP to a folder before opening `S56K-Firmware-Updater.exe`. Use the named BIN and updater ZIP links. GitHub's automatic “Source code” archives are whole-repository snapshots, not the individual files to select in the updater.

## What you need

| Item | Requirement |
| --- | --- |
| **Computer** | Intel/AMD 64-bit Windows 11. The reported hardware test used Windows 11 Pro 25H2. Windows on ARM and other Windows versions have not been verified. |
| **Sampler** | AKAI S5000 or S6000 fitted with the **IB-S56USB expansion card**, running an OS that can communicate over USB. |
| **Driver** | Microsoft's **WinUSB** associated with the Akai USB device. The old 32-bit Akai driver is not used by this app. |
| **Firmware** | One of the two exact BIN images accepted by this release; see [Supported files](#supported-files). |

The owner reported a successful **Expanded → original Akai v2.14 → Expanded** USB round-trip on the established S6000 test setup, including the supplied reboot-verification procedure. S5000 USB flashing has not been separately confirmed. The app remains labelled **1.0 RC1** and is unsigned. Windows may show an unknown-publisher or SmartScreen warning; check the download source and checksum rather than disabling Windows security.

The unchanged RC1 ZIP contains its original pre-test `START_HERE.html`. This online guide and the [compatibility page](COMPATIBILITY.md) include the subsequent hardware result.

## 1. Set up the USB driver

If the updater already connects successfully, keep your working driver and continue to [Prepare the sampler](#2-prepare-the-sampler).

1. Power on the sampler and connect its USB expansion to your PC with a reliable USB cable. Close ak.Sys, S56K USB Connection Check and any other sampler USB tools.
2. Open **Device Manager**. Find the Akai sampler, which may appear under **Other devices** if its driver is missing. Open **Properties → Details → Hardware Ids**.
3. Confirm the device has **`USB\VID_09E8&PID_005E`**. These are the Akai USB identifiers. If they do not match, do not change that device's driver.
4. Download **Zadig** from **[zadig.akeo.ie](https://zadig.akeo.ie/)** and run it. Driver installation normally requires administrator approval.
5. In Zadig, select **Options → List All Devices**, then select the Akai sampler. Check that **USB ID is `09E8 005E`**. Never select your keyboard, mouse, USB hub or another unrelated device.
6. In the target-driver box, choose **WinUSB**. Click **Install Driver** or **Replace Driver**, depending on what Zadig displays, and wait for completion. Do not choose libusb-win32 or libusbK for this app.
7. Close Zadig. If needed, disconnect and reconnect the sampler's USB cable, then open the updater and click **Refresh**. Select the sampler and click **Connect**.

A successful connection reads the sampler's USB identity and current display. **Connect does not flash the OS.** No test flash is needed to check whether the driver works.

Some Windows installations offer **Device Manager → Update driver → Browse my computer → Let me pick → Universal Serial Bus devices → WinUsb Device**. This is an alternative if available, but it may not register the interface the updater needs. If the device uses WinUSB yet the app reports no usable interface, use the device-specific Zadig procedure above. See [Microsoft's WinUSB installation documentation](https://learn.microsoft.com/en-us/windows-hardware/drivers/usbcon/winusb-installation) for background.

**What this changes:** the Windows driver association, not the sampler's firmware. The updater itself does not install drivers or edit their registry settings. You do not need to disable driver-signature enforcement. Assigning WinUSB does not make unmodified ak.Sys work; ak.Sys requires its separate compatibility setup and may stop recognising a device previously using its legacy driver. This updater needs neither ak.Sys nor its shim.

## 2. Prepare the sampler

- Save programs and samples to disk. Back up or note customised settings: the update writes the OS **and stored settings**.
- Start with a fresh sampler boot and do not load sample libraries. Confirm it is operating normally.
- Keep a known-working OS and readable recovery floppy available. Recovery after a failed update is not guaranteed.
- Use stable power and a reliable USB connection, preferably directly to the PC. Keep the PC awake and a laptop connected to power; close other sampler USB applications.
- Read the [flashing disclaimer](../DISCLAIMER.md) before proceeding. There is no safe cancellation once erasure starts.

## 3. Choose the firmware and install

1. Open **S56K Firmware Updater**, select your sampler and click **Connect**. Check the detected model.
2. Click **Choose BIN…** and select `S56K-EX.bin`. The app checks the entire file and only accepts the exact supported builds. It keeps a fixed copy in memory for the update.
3. Review the selected firmware, file and checksum. Click **Install firmware**, then review the confirmation. The default answer is **No**; confirming starts a permanent flash update.
4. Wait through the erase, transfer and programming stages. **Do not switch off, unplug USB, restart the computer or force-close the app.** The updater blocks its own Close action during installation and asks Windows to stay awake, but cannot prevent every interruption.
5. Wait for **“Transfer complete — sampler reported success.”** Save the report. The app does not restart the sampler automatically.
6. Once the update is complete and the sampler is idle, **remove any firmware floppy**, then restart the sampler. A floppy-loaded OS could otherwise hide which OS is actually in flash.
7. Confirm the model-specific **S5000 EX / S6000 EX** artwork and **EXPANDED EDITION v1** caption. Create an empty test program, open **Program Tools → Auto Sample**, and check normal operation.

The official version field remains **2.14** in both factory and Expanded firmware; it cannot distinguish them. Use the artwork and Auto Sample menu after booting without an OS floppy.

The app permits one update per session. **Close and reopen it before another installation**, then reconnect. A completed transfer means the sampler acknowledged the update; your reboot and operating checks confirm the result on the machine.

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
| **Driver missing / WinUSB not assigned** | Complete the driver procedure above for `09E8:005E` only. |
| **No usable interface registered** | Use Zadig to install a device-specific WinUSB association, reconnect USB and refresh. |
| **Cannot open / access denied / connection busy** | Close ak.Sys and other sampler USB tools. Reconnect USB and try Connect again before installation. |
| **Timeout during Connect** | Save the report. Check cable and power; close competing tools. If needed, save sampler work and restart it before trying again. This advice applies before an update, not during flash writing. |
| **BIN rejected** | Download the exact supported BIN and check its SHA-256. Do not use an older test build, ZIP file or GitHub “Source code” archive. |
| **Install disabled after a completed update** | This is intentional. Close and reopen the app for a new session. |

**If an update fails after erasure may have started:** leave the sampler powered on initially, save the report and note its display. The OS in flash may be incomplete. Do not repeatedly retry or assume a power-cycle will fix it. Share the error with the project maintainer before further attempts; recovery may require the established floppy procedure. The updater cannot repair a sampler whose application cannot start USB services, and preserving the boot block does not guarantee recovery.

Use **Save report** to export the session. The app also attempts to save logs under `%LOCALAPPDATA%\S56K\FirmwareUpdater\Logs`. Reports contain device identifiers, file paths, firmware hashes and status; review them for personal paths before posting publicly. Nothing is uploaded automatically.

[Download releases](../releases/README.md) · [Full compatibility notes](COMPATIBILITY.md) · [Report an issue](https://github.com/Tubbritt/S56K-Expanded-Edition/issues)
