# S56K Expanded Edition · Visual assets

The **artwork/** folder contains the landing-page panels. The studio hero is adapted from the user-supplied image of the S6000 and S5000 using image generation, with project typography composed separately for exact lettering. It is presentation artwork, not a photograph documenting a firmware test. The previous decorative waveform has been replaced.

The **screens/** folder contains native firmware renders. They preserve the original **320 × 240** pixel grid and show the implemented interface. Example program names, settings and progress counts are display fixtures, not captured audio or physical-device test results. The boot images show the correct model-specific EX lettering and **EXPANDED EDITION v1** caption.

The white feature panels place native screens beside concise explanations. Source graphics, typography, layout work and render tooling are maintained outside this documentation repository. No firmware source, app source or image-generation scripts are stored in the repository tree. Approved compiled firmware and updater downloads are stored in versioned release folders and linked from GitHub Releases.

The updater icon in **artwork/updater-icon.png** is the same icon shipped with the tested S56K Firmware Updater 1.0 RC1. It identifies the Windows companion app.

**artwork/social-preview.jpg** is the GitHub link-preview card: **1280 × 640 pixels**, **209,121 bytes**, with the title, feature copy and sampler faces inside the supplied template's safe border. It adapts the approved studio artwork using image generation, then uses a fixed-size export with white padding. To apply it, open repository **Settings → Social preview → Edit → Upload an image** and select this JPEG. Committing the image to this folder does not change that separate GitHub setting.

The **updater/** folder contains three illustrated adaptations of the user's Windows screenshots: Ready to install, the confirmation dialog and the completed-transfer panel. Image editing was used to produce legible guide artwork from the supplied inline images. They are not untouched screen captures or independent hardware-test evidence. Firmware hashes are published as text in the release/checksum files; use those values for verification.
