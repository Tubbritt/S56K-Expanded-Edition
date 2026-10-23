# Feedback & documentation

S56K Expanded Edition's repository is home to firmware and updater downloads, release information, user guides and visual assets. Firmware and app development source, build tools, disassembly and research material are maintained separately.

## Report an issue

Documentation corrections and clear device observations are welcome through [Issues](https://github.com/Tubbritt/S56K-Expanded-Edition/issues). Include:

- Sampler model and the exact firmware version or file checksum.
- How it was loaded or installed: temporary floppy boot, permanent floppy flash or the Windows USB updater.
- For a USB issue, include the updater version, Windows version, driver name, and the saved update report after reviewing it for personal information such as local file paths.
- Relevant settings, what you expected and what happened.
- A screen photograph where it helps explain the issue.

Do not post private information or proprietary sample libraries. For an update failure, preserve the exact displayed message and avoid describing an untested recovery procedure as a guaranteed fix.

## Repository contents

Keep committed files to documentation, images and PDF guides. The ignore rules exclude executable files, firmware, archives and development code. Approved firmware BINs and compiled updater ZIPs are distributed through separate GitHub Releases with checksums and release notes. Do not commit app source, firmware source, research tools or executable payloads to the repository tree.

Read the [flashing disclaimer](DISCLAIMER.md) and [compatibility notes](docs/COMPATIBILITY.md) before using a firmware image. Reporting a successful installation helps document that result; it does not establish safety on every device or for a different BIN.
