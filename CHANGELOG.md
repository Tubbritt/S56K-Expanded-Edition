# Release history

[Home](README.md) · [Downloads](releases/README.md) · [All GitHub Releases](https://github.com/Tubbritt/S56K-Expanded-Edition/releases)

The sampler firmware and Windows updater have separate version numbers. This
page records what each release adds; its detailed release notes describe the
requirements, known limits and testing.

| Product | Current release | Date | Details |
| --- | --- | --- | --- |
| Sampler firmware | **Expanded Edition v1** | 23 October 2026 | [Release notes](releases/v1.md) · [Release & assets](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/tag/expanded-v1) |
| Windows USB app | **Firmware Updater 1.0 RC1** · release candidate | 23 October 2026 | [Release notes](releases/updater-1.0-rc1.md) · [Release & assets](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/tag/updater-v1.0-rc1) |

## Expanded Edition v1 — 23 October 2026

Initial firmware release. Tag: `expanded-v1`.

- **Auto Sample:** capture a range of MIDI notes with one to four velocity
  layers, automatic sample naming and assignment to the current program.
- **Recording controls:** musical note names, MIDI outputs A/B, input levels,
  mono/stereo capture and adjustable recording-start threshold.
- **Auto End:** keep fixed durations, stop a quiet release tail early, or also
  shorten a naturally decaying held note.
- **Auto Loop:** choose percentage positions within the held note, with optional
  Akai Auto Find, crossfade amount/shape and cropping after the loop.
- **Clearer pages:** contextual velocity, recording and loop options, capture
  progress, and cancellation that retains completed assignments in RAM.
- **EX startup artwork:** S5000 EX / S6000 EX logos and EXPANDED EDITION v1.

Saving remains manual through the normal sampler SAVE page. The underlying
Akai OS/settings/protocol version remains **2.14**; the edition label identifies
the added features. The published BIN is the tested EX artwork revision 2 image.

Auto Sample operation was reported on both sampler models during development.
The current image was used in the successful S6000 / Windows 11 USB round-trip;
this does not establish S5000 USB installation coverage. See the
[compatibility record](docs/COMPATIBILITY.md) and [full release notes](releases/v1.md).

## Firmware Updater 1.0 RC1 — 23 October 2026

Initial standalone Windows updater release candidate. Tag: `updater-v1.0-rc1`.

- **Connect, choose BIN, install:** a Windows 11 x64 USB workflow without ak.Sys.
- **Exact firmware checks:** accepts the published Expanded Edition v1 image
  and the recognised original Akai v2.14 image, verified by SHA-256.
- **Installation feedback:** explicit confirmation, progress and sampler status.
- **Local reports:** save connection and update details for troubleshooting.

Requires an IB-S56USB card and WinUSB. The app is unsigned and remains a release
candidate. Installation writes flash and stored settings; it does not provide a
temporary USB boot mode.

The owner confirmed an Expanded → original v2.14 → Expanded round-trip on the
established S6000 / Windows 11 Pro 25H2 setup. Other model/host combinations and
failure recovery have not thereby been verified. See the
[full updater notes](releases/updater-1.0-rc1.md).

## How this history is maintained

Each new binary release gets its own version, Git tag, downloadable assets,
checksums and release-notes page. Previous entries stay available for comparison.
Changed binary files are never silently substituted under an existing version.

Corrections to guides, licensing notices or download presentation do not imply
new firmware or a new updater build. Those edits are recorded in the
[documentation history](https://github.com/Tubbritt/S56K-Expanded-Edition/commits/main/).
Use the file's checksum to identify the exact build.

For maintainers: [Preparing the next release](docs/RELEASE-PROCESS.md).
