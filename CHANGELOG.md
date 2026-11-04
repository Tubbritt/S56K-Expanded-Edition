# Release history

[Home](README.md) · [Downloads](releases/README.md) · [All GitHub Releases](https://github.com/Tubbritt/S56K-Expanded-Edition/releases)

The sampler firmware and Windows updater have separate version numbers. This
page records what each release adds; its detailed release notes describe the
requirements, known limits and testing.

| Product | Current release | Date | Details |
| --- | --- | --- | --- |
| Sampler firmware | **Expanded Edition V1.2** | 4 November 2026 | [Release notes](releases/v1.2.md) · [GitHub Release](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/tag/expanded-v1.2) |
| Windows USB app | **Firmware Updater 1.0 RC1** · release candidate | 23 October 2026 | [Release notes](releases/updater-1.0-rc1.md) · [GitHub Release](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/tag/updater-v1.0-rc1) |

## Expanded Edition V1.2 — 4 November 2026

Tag: `expanded-v1.2`. **[Complete plain-English changes and release notes](releases/v1.2.md).**

- **Record Arm Failed:** fixed Auto Sample stopping when too little recording workspace was immediately available, even though the sampler still showed free sample RAM. It now waits for background cleanup and can organise sample memory before the next recording.
- **Controlled recovery:** after the recorder has been cleaned up, one retry is allowed for the specific recording-memory error. Other recording errors still stop the batch and report the problem.
- **Cancellation and cleanup:** improved cancellation and timeout handling while sample memory is being organised. Another recording cannot start while that cleanup remains unfinished; completed samples stay in RAM.
- **Progress and diagnostics:** added clearer waiting/organising messages, recovery counters and diagnostic information for recording-memory failures.
- **Cropping label:** corrected misleading cropping status text when Crop after loop is OFF. This label fix does not change the underlying sample processing.
- **Startup:** EXPANDED EDITION V1.2 on both model paths, with the native Akai identity still 2.14.
- **Verification:** all 20 software-check suites passed for the exact published BIN, followed by independent review. The owner reported stable operation of the preceding recovery build and confirmed successful flashing of this V1.2 BIN after receiving the floppy flash-and-reboot procedure.

V1.1's release-tail, monitoring and loop/crossfade improvements remain in place. V1.2 reserves **8 KiB more CPU RAM than V1.1**; sample RAM capacity is unchanged. A full sampler can still run out of recording space. Saving remains manual.

**Install V1.2 from floppy. Firmware Updater 1.0 RC1 is unchanged and accepts neither V1.1 nor V1.2.** V1.1's BIN has been removed from the current repository tree; its original tag and release history remain available.

## Expanded Edition V1.1 — 2 November 2026

Tag: `expanded-v1.1`. Superseded by V1.2. **[Complete plain-English changes and release notes](releases/v1.1.md).**

- **Release tails:** fixed Crop OFF discarding the recorded release. It now keeps the attack, held note and complete recorded tail. Crop now defaults OFF; ON still deliberately trims after the loop.
- **Playback mode:** added F6 PLAY MODE in LOOP SETUP. UNTIL RELEASE is the default; IN RELEASE allows looping after key release. Program zones use AS SAMPLE to respect the selected mode.
- **Crossfade:** positive fades can process less closely matched endpoints. With Crop OFF, fades are limited to protect recorded release audio, so the effective fade may be shorter than requested.
- **Input monitoring:** enabled in Auto Sample setup and capture, with proper handover and restoration of previous monitoring preferences. It can pause during processing and between captures.
- **Cancellation:** fixed a recorder-start timing problem when cancelling immediately after START.
- **Error display:** restart-required faults keep their explanation; the inactive Cancel button is removed and Cancel/Exit no longer replaces the error with a stuck STOPPING display.
- **Stop explanations:** preserve the first setup, routing, recording, MIDI or page-navigation cause through cleanup, unless a more serious cleanup fault needs a restart.
- **Loop failures:** confirmed refusals before processing starts keep the original recording, become REVIEW and continue. Uncertain failures stop with a specific error and are not automatically retried or mislabeled as user cancellation.
- **Loop diagnostics:** LAST LOOP can show the affected processing stage and an Akai error code.
- **Startup:** EXPANDED EDITION V1.1 on both model paths; the official Akai identity remains 2.14.
- **Verification:** all 16 software suites passed for the exact published BIN, with independent review. The owner reported successful flashing after receiving the floppy test procedure; the model was not restated and V1.1 USB installation is not established.

Uses **4 KiB more CPU RAM than V1**, with sample RAM capacity unchanged. Saving remains manual. These are confirmed code-path fixes; the original reporter's unexplained STOPPED event was not conclusively reproduced.

**Install V1.1 from floppy. Firmware Updater 1.0 RC1 is unchanged and does not accept V1.1.** The old BIN was removed from the current repository tree; the original V1 tag and release history remain available.

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
The V1 image was used in the successful S6000 / Windows 11 USB round-trip;
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

For the project owner: [Preparing the next release](docs/RELEASE-PROCESS.md).
