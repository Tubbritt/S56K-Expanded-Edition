# Update your sampler from Windows

[Home](../README.md) · [Download updater](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip) · [Current V1.1 floppy installation](INSTALLATION.md) · [Troubleshooting](USB-REFERENCE.md#troubleshooting)

> **Installing Expanded Edition V1.1? Use [floppy](INSTALLATION.md).** Firmware Updater **1.0 RC1 rejects V1.1** because it is not on the app's supported-file list. This guide covers only the original **Expanded Edition v1** and **factory Akai v2.14** images. The updater and its illustrated screens are unchanged.

**Windows 11 x64 · S5000/S6000 with an IB-S56USB card · Microsoft WinUSB.** Extract the updater ZIP, then open `S56K-Firmware-Updater.exe`. Firmware is a separate download. This is an unsigned **1.0 RC1** app; see [compatibility](COMPATIBILITY.md) for test coverage.

## Driver setup · once only

**Already connects? Skip ahead.** Otherwise, find the Akai device in Device Manager and choose:

**Update driver → Browse my computer → Let me pick → Universal Serial Bus devices → WinUsb Device → Next.**

Check you selected the Akai device (`USB\VID_09E8&PID_005E`). Reconnect USB, then click **Refresh → Connect**. If WinUsb Device is unavailable or no interface is found, see the [optional driver fallback](USB-REFERENCE.md#driver-fallback-winusb-unavailable-or-no-registered-interface).

## 1. Connect and choose your BIN

Select the sampler and click **Connect**, then **Choose BIN…** and select an exact [supported image](USB-REFERENCE.md#supported-files): the original v1 `S56K-EX.bin` or factory `s56v214.bin`. Look for **Connected**, **Exact SHA-256 match** and **Ready to install**. The current V1.1 download will be rejected; this is expected and is not a USB-driver fault.

![Illustrated app screen: connected S6000 with S56K-EX.bin validated and Ready to install](../assets/updater/ready-to-install.png)

*Illustrations adapted from the supplied Windows screenshots of Expanded Edition v1 installation. They do not show V1.1 support.*

## 2. Confirm the installation

Save your programs, samples and settings first. Start with a freshly booted sampler and no loaded libraries. Close ak.Sys and other USB tools. Read the [flashing disclaimer](../DISCLAIMER.md).

Click **Install firmware**, check the sampler and firmware shown, then choose **Yes** when ready.

<img src="../assets/updater/confirm-installation.png" alt="Illustrated confirmation dialog showing the selected S6000 and firmware" width="560">

**This writes flash and stored settings. Keep power and USB connected until it finishes. There is no safe cancellation after erasure starts.**

## 3. Finish, restart and check

Wait for **Transfer complete — sampler reported success**. Save the report.

![Illustrated completion panel showing all 63 blocks accepted and transfer complete at 100 percent](../assets/updater/transfer-complete.png)

When the sampler is idle, **remove any firmware floppy and restart it**. For Expanded Edition v1, check the **EXPANDED EDITION v1** boot caption and **Program Tools → Auto Sample**. For factory restoration, check the original Akai startup and ordinary operation. The underlying version field reads 2.14 in both cases.

Close and reopen the app before another update. If an update reports an error after erasure starts, leave the sampler powered on initially and [follow the failure guidance](USB-REFERENCE.md#troubleshooting).

[Checksums & supported files](USB-REFERENCE.md#supported-files) · [Troubleshooting](USB-REFERENCE.md#troubleshooting) · [Compatibility and test status](COMPATIBILITY.md)
