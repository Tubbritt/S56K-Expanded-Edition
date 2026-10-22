# Installing S56K Expanded Edition

[Home](../README.md) · [Release notes](../releases/v1.md) · [Compatibility](COMPATIBILITY.md) · [Flashing disclaimer](../DISCLAIMER.md)

The firmware image is **S56K-EX.bin**, shared by the AKAI S5000 and S6000. The boot screen selects the correct model graphic automatically and displays **EXPANDED EDITION v1**. The underlying AKAI operating-system identity remains **2.14**.

Read the [flashing disclaimer](../DISCLAIMER.md) before proceeding. Permanent installation carries a risk of an unusable sampler and possible repair costs. The instructions and compatibility notes supplied with your exact download take precedence over this general guide.

## Before you begin

- Obtain the firmware attachment and its SHA-256 checksum from the project's [release area](../releases/README.md). GitHub's automatic “Source code” archives contain documentation, not the OS.
- Confirm that the release supports your sampler and follow its installation notes. If the firmware, checksum or instructions are missing, stop rather than substituting another file.
- Back up your programs and samples to separate storage. Keep a known working OS file and readable disk; these do not guarantee recovery after a failed flash.
- Verify the BIN's SHA-256 checksum against the checksum published with that exact release.
- Use a known readable floppy disk, a reliable drive and a stable power supply. Copy **S56K-EX.bin** to the disk with no other OS BIN files present. Where possible, read the file back on the computer and verify its checksum again.

## 1. Load temporarily from floppy

1. Insert the prepared floppy and switch on the sampler.
2. Allow it to read the OS. At **Write Flash OS**, select **NO** to continue without permanently installing it.
3. Check the model-specific EX graphic, the **EXPANDED EDITION v1** caption and normal startup.
4. Open an empty test program, then **Program Tools → Auto Sample**. Make a short capture, audition it and check the controls you intend to use. Save wanted work using the normal **SAVE** page.

If the expected artwork or feature is absent, or anything behaves unexpectedly, stop and check the disk and exact file before considering installation. A temporary boot leaves the existing installed OS in flash; it does not prove that a flash write will succeed.

## 2. Install permanently from floppy

Proceed only when the temporary load and checks have succeeded and you have accepted the installation risk.

1. Boot again using the same verified floppy and firmware file.
2. At **Write Flash OS**, choose **YES** when ready to install.
3. Allow writing and verification to finish. **Do not switch off, reset or remove media during the update.** Follow the sampler's completion instructions.
4. Remove the floppy and restart when the update has completed. Confirm the EX boot artwork appears without the disk, then check ordinary operation and a short Auto Sample capture.

An update that reports an error is not a successful installation. Record the exact message and consult the instructions for that release; do not assume a repeated update or a retained backup will recover every failure.

## USB and ak.Sys

USB is not required for Auto Sample or floppy installation. Windows/ak.Sys installation has not been verified on physical hardware for the documented version, so this guide does not provide a USB installation procedure. Temporary USB boot without writing flash is not an advertised feature.

See [Compatibility](COMPATIBILITY.md) for the distinction between software checks, earlier device results and the exact version's hardware evidence.
