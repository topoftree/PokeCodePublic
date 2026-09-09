# Pokecode

Pokecode is an Android workspace for organizing notes and projects, preparing structured prompts, and working with Chat and an embedded terminal on your phone.

## Overview

Keep written material in Notes, organize it into Blocks and Subblocks, and group work into Projects. Use Launcher and Time Capsule to manage submissions and revisit their saved history. Chat and Terminal bring command-line workflows into the same workspace.

This is Pokecode's public distribution and documentation repository. APK downloads belong in GitHub Releases; application source and development configuration are maintained privately.

## Main features

- Notes with editable Blocks and Subblocks, pinning, and search.
- Project workspaces and reusable custom prompt templates.
- Launcher for preparing linked content for sessions.
- Time Capsule for browsing saved submission snapshots by date.
- Trash with restoration of deleted Notes and Blocks.
- Export Notes as Word documents (`.docx`), UTF-8 text, or PDF.
- Chat sessions with attachments, streamed responses, and task controls.
- An embedded terminal and an Ubuntu installation workflow.
- Local HTML previews, light and dark themes, and session progress notifications.

External services, accounts, downloaded tools, and model availability can affect individual workflows. Ubuntu and external AI services require separate setup; they are not provided by this repository.

## Screenshots

Screenshots will be added here after review. Planned views: Notes and Blocks, Project workspaces, Chat, and Terminal. No screenshots containing private notes, conversations, account information, or credentials are published.

## Download

Visit [Pokecode Releases](https://github.com/topoftree/PokeCodePublic/releases) for official APKs, release notes, SHA-256 checksums, and accompanying third-party materials.

Download [Pokecode-v0.1.6.2.15.apk](https://github.com/topoftree/PokeCodePublic/releases/download/v0.1.6.2.15/Pokecode-v0.1.6.2.15.apk) and [SHA256SUMS.txt](https://github.com/topoftree/PokeCodePublic/releases/download/v0.1.6.2.15/SHA256SUMS.txt) from the latest release. Review its known limitations and outstanding licensing issues before use. GitHub's automatically generated source-code archives contain this documentation repository, not the application or its complete third-party corresponding source.

## Latest release

The latest release is [**Pokecode 0.1.6.2.15**](https://github.com/topoftree/PokeCodePublic/releases/tag/v0.1.6.2.15) (Android version code **259**). The [Releases page](https://github.com/topoftree/PokeCodePublic/releases) is the authoritative record of available versions.

This release optimizes opening large Notes and expands the bundled third-party notices. The release notes also document the unresolved redistribution review and a known terminal utility limitation.

## Installation instructions

1. Open its release page and download `Pokecode-vX.Y.Z.apk` and `SHA256SUMS.txt`.
2. Verify the APK checksum as described below.
3. Open the APK using Android's file manager or your browser's download list.
4. If Android requests it, allow that browser or file manager to install unknown apps, then return to the installer.
5. Install and open Pokecode. You can turn off that installation permission afterward.

Installation screens vary by manufacturer. If Android refuses the installation, check your Android version and CPU architecture before reporting the error. Do not disable Android's security checks to force an incompatible installation.

## Android requirements

| Requirement | Current release |
| --- | --- |
| Minimum Android version | Android 13 (API 33) |
| Target Android version | Android 16 (API 36) |
| CPU architecture | ARM64 (`arm64-v8a`) |
| Application ID | `com.claude.note` |
| Distribution build | Signed release APK |

Internet access is needed for external services and runtime downloads. Some features depend on capabilities available on the device. Downloaded Ubuntu environments need additional storage beyond the APK.

## Updating Pokecode

Download the newer APK from Releases, verify its checksum, and install it over your existing installation. Updates must have the same application ID and a compatible signing certificate. Android rejects updates signed with an unrelated key.

Export important Notes before updating. Avoid uninstalling to work around a signature error: uninstalling can remove application data. Report the error and the versions involved instead.

## Security and APK verification

Release 0.1.6.2.15 provides a `SHA256SUMS.txt` entry for the exact APK. In Termux or another shell with `sha256sum`, place the two downloaded files in the same directory and run:

```sh
sha256sum -c SHA256SUMS.txt
```

The result should say `OK` for the APK. A matching checksum confirms that the file matches the published bytes. It does not independently establish the publisher's identity; obtain both files from the official release page. Android also verifies the APK's signature during installation.

## Bug reports

Search [existing issues](https://github.com/topoftree/PokeCodePublic/issues) before [opening a bug report](https://github.com/topoftree/PokeCodePublic/issues/new).

Include the Pokecode version, Android version, device model, steps to reproduce, and expected and actual behavior. Attach a redacted screenshot or error message when useful. Issues are public: remove passwords, tokens, account details, private notes, conversations, and other personal information before posting.

## Feature requests

[Open an issue](https://github.com/topoftree/PokeCodePublic/issues/new) describing the task you want to accomplish, the current limitation, and the behavior you would find useful. Suggestions do not imply a delivery commitment.

## Project status

Pokecode is under active development. This repository is its official public distribution channel. Release availability, changes, and known limitations are documented in GitHub Releases. Publication does not imply that the outstanding licensing review has been completed.

## Source code availability

Pokecode is proprietary software. This repository is provided for application distribution, documentation, release notes, and issue tracking. The application source code is not publicly available.

A public GitHub repository does not make Pokecode open source. No MIT, Apache, GPL, or other open-source license is granted for Pokecode itself by this repository. Third-party components retain their own licenses and recipient rights, including any applicable rights to their sources, modifications, and reverse engineering for debugging library modifications.

## Third-party open-source software

Pokecode uses third-party software under several licenses, including components that require source distribution. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and [third_party_licenses/](third_party_licenses/) for component-specific notices and license texts.

The terminal runtime includes GPL, LGPL, and other copyleft components. The source-delivery and redistribution review remains incomplete: a complete corresponding-source package has not been published with this release, and LGPL replacement, execution-time notices, and SDK obligations remain unresolved. Publication does not establish compliance or remove those obligations. Required third-party source materials are distinct from Pokecode's private application source.

Google SDKs are covered by their own terms, rather than being presumed open source. ML Kit may send API performance and usage metrics to Google; see the [SDK notice](SDK_NOTICE.md). This notice describes those SDKs and is not a complete application privacy policy.

Pokecode is not affiliated with or endorsed by the projects or services mentioned here. Names and trademarks belong to their respective owners.

This product includes software developed by the University of California, Berkeley and its contributors.

## Copyright

Copyright © 2026 Pokecode. All rights reserved.

This notice applies to Pokecode's own material. It does not replace or restrict the licenses of the identified third-party components.
