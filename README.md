![S56K Expanded Edition — Auto Sample and Auto Loop for the AKAI S5000 and S6000](assets/artwork/hero.png)

# S56K Expanded Edition

**Classic hardware. New ways to capture sound.**

Bring an external instrument into your S5000 or S6000 as a playable program. **Auto Sample** records a range of notes and velocity layers, names the samples and maps them for you. **Auto Loop** prepares the sustain with optional Akai Auto Find, crossfade and cropping. You stay in control of the sound—and when it is saved.

**[Downloads](releases/README.md) · [What's new](CHANGELOG.md) · [Get started](docs/QUICK-START.md) · [User guide](docs/USER-GUIDE.md) · [PDF manual](docs/S56K-Expanded-Edition-User-Guide.pdf) · [USB setup](docs/USB-UPDATER.md)**

### Three separate tools, one sampler

| Project | Purpose |
| --- | --- |
| **[S56K Editor](https://github.com/Tubbritt/S56K-Editor)** | Desktop control, file management and library transfers. |
| **S56K Expanded Edition** | Optional sampler firmware with Auto Sample and Auto Loop features. This repository. |
| **[S56K Firmware Updater](https://github.com/Tubbritt/S56K-Expanded-Edition/releases)** | A separate app for installing supported firmware images. |

All three support the **AKAI S5000 and S6000**. Firmware and updater downloads live here; the Editor has its own repository. The Editor works with **stock OS 2.14** as well as Expanded Edition, so it does not require a firmware upgrade. Firmware installation uses the separate updater for its supported images, or floppy. **V1.2 currently requires floppy installation.**

### Download your upgrade

**V1.2 is available.** Auto Sample can now wait for memory cleanup and organise recording space, addressing **Record Arm Failed** stops despite free sample RAM. Completed recordings stay in memory. **[Read the complete changelog →](releases/v1.2.md)**

| For your sampler | For your Windows PC |
| --- | --- |
| **Expanded Edition V1.2** | **Firmware Updater 1.0 RC1** |
| One OS image for the S5000 and S6000. **Install V1.2 from floppy.** | Standalone Windows 11 x64 app for **original Akai v2.14 and Expanded V1**. It does **not** accept V1.1 or V1.2. |
| **[Download S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.2/releases/firmware/v1.2/S56K-EX.bin)** | **[Download Windows updater ZIP](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip)** |
| [V1.2 release notes](releases/v1.2.md) · [Installation](docs/INSTALLATION.md) | [Updater release notes](releases/updater-1.0-rc1.md) · [USB driver & app guide](docs/USB-UPDATER.md) |

The USB updater needs an **IB-S56USB card** and Microsoft's **WinUSB** driver. Its confirmed S6000 USB round-trip used the previous Expanded V1 firmware. The owner has confirmed successful V1.2 flashing after receiving the floppy flash-and-reboot procedure. The preceding recovery test build was reported stable; this does not establish V1.2 USB compatibility. See [compatibility](docs/COMPATIBILITY.md) for the scope of testing and [downloads](releases/README.md) for checksums. Read the [flashing disclaimer](DISCLAIMER.md) before installing.

![Auto Sample: choose notes and velocities, record an external instrument and automatically map the results](assets/artwork/auto-sample.png)

### From a sound to an instrument

Choose a patch, set the note range and spacing, and capture up to **four velocity layers**. MIDI outputs use the familiar **A / B** labels. Notes use musical names, and the recording-count summary tells you the size of the run before you start.

Use **REC LEVELS** to set gain and mono/stereo. Set the start threshold to catch the attack, then let **AUTO END** finish a quiet release early—or shorten a naturally decaying note too. The progress screen follows each capture, and cancellation keeps completed assignments in RAM.

**[Make your first capture →](docs/QUICK-START.md)**

![Auto Loop: percentage positions, optional Akai Auto Find, crossfade and cropping on the native Loop Setup page](assets/artwork/auto-loop.png)

### A sustain worth keeping

Place the loop within the held part of the note. Optional **AKAI AUTO FIND** refines the join locally; **CROSSFADE** offers LINEAR, LOG and SINE shapes. Keep the full recorded release with **CROP AFTER LOOP OFF** (the default), or deliberately crop after the loop. **PLAY MODE** chooses whether looping stops at key release or continues under the envelope. Crossfades protect the retained release tail.

Listen to each result. If loop preparation is unsuccessful, the original recording remains available for review. The ordinary sample editor is there for finishing touches.

The artwork above illustrates a crop-on example. The current V1.2 controls and defaults are shown in the manual.

**[Explore the loop controls →](docs/USER-GUIDE.md#6-loop-the-sustained-part)**

![Create and name an empty program, capture into RAM, then save manually when ready](assets/artwork/workflow.png)

### Built around the sampler

| Feature | What it brings to your workflow |
| --- | --- |
| **Automatic capture** | Musical note names, adjustable spacing, MIDI channel and output A/B. |
| **Velocity layers** | One to four capture velocities with automatic playback-zone mapping. |
| **Recording setup** | Native input meters, gain, mono/stereo and an adjustable start threshold. |
| **Flexible endings** | OFF, TAIL ONLY and NOTE + TAIL, with quiet and minimum-time controls. |
| **Optional loop preparation** | Percentage positions, local Auto Find, crossfade amount/shape, release-preserving cropping choices and playback mode. |
| **Clear progress** | Current note, velocity, layer, completed samples, loop-review counts, memory-recovery messages and failure-stage details. |
| **Recording memory recovery** | Waits for background cleanup and can organise sample memory before the next recording, preserving completed samples. |
| **Focused pages** | Only active velocity rows and applicable recording/loop controls appear. |
| **EX startup artwork** | Model-specific S5000 EX / S6000 EX logos and EXPANDED EDITION V1.2. |

**Saving stays in your hands.** Create and name an empty program first. Auto Sample populates it in RAM; use the normal **SAVE** page to save the program **with its samples** when you are ready.

### A new identity for both models

| S5000 EX | S6000 EX |
| :---: | :---: |
| ![S5000 EX boot screen with EXPANDED EDITION V1.2](assets/screens/boot-s5000.png) | ![S6000 EX boot screen with EXPANDED EDITION V1.2](assets/screens/boot-s6000.png) |

One firmware image selects the right artwork for your sampler. The separate **Operating System VERSION 2.14** field remains unchanged for compatibility.

**[View the screen gallery →](docs/SCREEN-GALLERY.md)**

### Windows updater for earlier firmware

![Illustrated Windows updater screen adapted from the supplied screenshot](assets/updater/ready-to-install.png)

*Illustrated app screen, adapted from the supplied Windows screenshot.*

**Connect → Choose BIN → Install.** The standalone updater checks the connected sampler and exact firmware file before installation, shows progress and saves local reports. **Version 1.0 RC1 accepts Expanded V1 and original Akai v2.14 only. It rejects V1.1 and V1.2.** Use the [floppy instructions](docs/INSTALLATION.md) for the current release.

If Windows cannot find the sampler, the illustrated project manual and [USB guide](docs/USB-UPDATER.md) walk through identifying the Akai device, assigning WinUSB and checking the connection. USB installation writes flash; temporary loading remains available through floppy.

**[Follow the illustrated USB walkthrough →](docs/USB-UPDATER.md)**

### Everything you need to get started

| Guide | Start here for… |
| --- | --- |
| **[Quick start](docs/QUICK-START.md)** | Your first recording, from connecting cables to saving a program. |
| **[Illustrated manual](docs/USER-GUIDE.md)** · **[PDF](docs/S56K-Expanded-Edition-User-Guide.pdf)** | Notes, layers, timing, loops and troubleshooting. |
| **[Installation guide](docs/INSTALLATION.md)** | V1.2 temporary floppy loading and permanent flashing; USB compatibility explained. |
| **[Windows USB guide](docs/USB-UPDATER.md)** | Driver setup, the updater, verification and troubleshooting. |
| **[V1.2 release notes](releases/v1.2.md)** | Features, behavior and practical limits. |
| **[Compatibility](docs/COMPATIBILITY.md)** | Model support and the available software/hardware verification evidence. |
| **[Release area](releases/README.md)** | Firmware and Windows app downloads, release notes and checksums. |
| **[Release history](CHANGELOG.md)** | What each firmware and updater version adds, changes or fixes. |
| **[Feedback](https://github.com/Tubbritt/S56K-Expanded-Edition/issues)** | Share your sampler, settings and observations. |

### Before installing

**Firmware installation is at your own risk.** Flashing can leave a sampler unusable and can cause data loss or repair costs. The project is provided without warranty, and liability is limited to the extent permitted by law. Read the **[full flashing disclaimer](DISCLAIMER.md)** and **[installation guide](docs/INSTALLATION.md)** before proceeding.

---

S56K Expanded Edition is an independent project, not an official AKAI release or an AKAI-endorsed product. AKAI and other product names belong to their respective owners.

**Free to use, including in professional studios and commercial music production.** The [Freeware Licence](LICENSE.md) permits use and unchanged sharing of the material covered by it. Read the [third-party acknowledgements](THIRD-PARTY-NOTICES.md) for the original Akai firmware and Windows runtime components; their respective rights remain with their owners.

This is a closed-source project. The project's own firmware and application source code is private, is not included in the downloads, and will not be published. This repository distributes compiled releases, documentation and artwork.
