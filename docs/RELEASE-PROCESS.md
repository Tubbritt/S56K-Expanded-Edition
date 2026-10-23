# Preparing the next release

[Home](../README.md) · [Release history](../CHANGELOG.md) · [Downloads](../releases/README.md)

This repository distributes compiled firmware, the standalone updater,
documentation and artwork. Development source and build tools are not published
here. The public release record consists of one history page and a detailed
notes page for each version.

## Keep the two release series separate

| Product | Existing example | Tag pattern | Notes page pattern |
| --- | --- | --- | --- |
| Sampler firmware | Expanded Edition v1 | `expanded-v<edition>` | `releases/v<edition>.md` |
| Windows app | Firmware Updater 1.0 RC1 | `updater-v<version>` | `releases/updater-<version>.md` |

These patterns describe naming conventions, not announced future releases.
Firmware and updater versions can advance independently. Changing an edition
label must not silently change the sampler's underlying Akai protocol/settings
version.

## Prepare the files and notes

1. Identify the exact approved BIN or updater ZIP. Record its filename, byte
   count and SHA-256. Check that the file is the same build used for the stated
   tests. Keep existing released files and tags intact.
2. Place the compiled download and `SHA256SUMS.txt` in a new versioned folder
   under `releases/firmware/` or `releases/updater/`. Extend the explicit
   `.gitignore` allowlist for those files only; do not add development source,
   build scripts, research material or unrelated executables.
3. Create a notes page using the appropriate existing page as a guide. Explain
   **Added**, **Changed** and **Fixed** behaviour where applicable, plus known
   issues, requirements, exact supported files and installation instructions.
   Include the release date, version, checksum and byte count. Omit empty
   categories rather than inventing changes.
4. Record the testing that actually occurred: sampler model, relevant expansion
   cards, PC/Windows version, installation route and result. Distinguish software
   checks from reported hardware tests. Keep release candidates marked as such.
5. Confirm firmware/updater compatibility. The current updater recognises exact
   firmware hashes: a changed BIN may require a new updater release. Do not
   imply an older updater accepts a new image without checking it.

The updater's tested ZIP should include the notices required by its applicable
licences. When accompanying notices are supplied separately for an existing
release, retain their links and attach them with that release; do not silently
repack an already released ZIP to add them.

## Publish one identifiable release

1. Update the [release history](../CHANGELOG.md), [download index](../releases/README.md),
   main README and affected guides. Update the PDF manual when instructions or
   features materially change. Keep supported firmware hashes and version names
   consistent across these pages.
2. Commit the distribution files and create a distinct Git tag for this version.
   Draft the GitHub Release from that tag, with an understandable summary and a
   link to the detailed notes. Use absolute GitHub links in release descriptions
   so links work outside repository file views.
3. Attach the named BIN or ZIP and its `SHA256SUMS.txt` directly to the release's
   **Assets** list. Attach applicable licence/notices files and, when useful, the
   manual. Use explicit asset links for the main downloads; retain the tagged
   repository copies as matching records.
4. Download the uploaded binary asset and verify its size and SHA-256 against
   the approved file. Check the release's links and notes, then publish with the
   correct release/prerelease status. Check the public-facing download route.

GitHub adds automatic **Source code** ZIP/TAR links. For this repository those
are snapshots of the distribution files and documentation, not development
source. Direct visitors to the named BIN or updater ZIP.

## Preserve the record

Do not move a published tag or replace a released BIN/ZIP under the same name
and version. A binary change requires a new version, checksum and release entry,
even when its visible interface looks the same. Keep older releases identifiable
so users can report exactly what they installed.

Guide corrections and revised release descriptions can be published without a
new binary version. Record meaningful documentation changes in Git history and
state when the software itself is unchanged. If a manual already attached to a
release needs revision, publish it with a distinct revision filename and explain
the correction rather than silently replacing the old attachment.

If a release is later found unsuitable for use, mark it clearly as withdrawn or
superseded and explain why. Do not hide the affected version or its identity by
substituting different software.
