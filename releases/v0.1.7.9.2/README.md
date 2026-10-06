# Pokecode 0.1.7.9.2 — release preparation

The signed APK and release notes are prepared for manual publication. This page
is release documentation; it is not a saved GitHub Release draft.

[Open the prefilled GitHub Release editor](https://github.com/topoftree/PokeCodePublic/releases/new?tag=v0.1.7.9.2&target=main&title=Pokecode+0.1.7.9.2&body=Signed+production+APK+for+%2A%2AAndroid+13%2B+%2F+ARM64%2A%2A%2C+version+%2A%2A0.1.7.9.2+%2F+code+377%2A%2A.+Original+release+signature%3B+R8+optimization+and+resource+shrinking.%0A%0A%23%23%23+Changes+since+v0.1.7.7.3.3%0A%0A-+Add+Chat+Voice+Mode+with+an+audio-reactive+orb%2C+automatic+Codex+startup%2C+minimization%2C+background+audio+and+notification+mute%2Fclose+controls.+Fix+its+voice+protocol-header+rejection.%0A-+Add+a+focused-composer+Plan+mode+toggle+and+clearer+centered+connection%2Fstopped+status.%0A-+Keep+Chat+conversations+bound+to+independent+sessions.+Add+Project+branch+workspaces%2C+GitHub+import%2Fbinding%2C+explicit+bidirectional+Sync%2C+local+Merge+and+remote+branch+renaming.%0A-+Add+Note+default+branch%2Fsession+and+Agent+choices%2C+individual+Subblock+queues%2C+multi-selection+and+cancellation.+Final+generation+waits+for+every+version-group+input+and+its+completed+task.%0A-+Make+Chat+web%2Ffile+links+actionable+and+retain+final+deliverables+as+attachments.+Add+Time+Capsule+task+summaries%2C+activity%2Fdiff+details+and+PDF%2Ftext%2FWord+history+export.%0A-+Fix+startup+crashes+when+restoring+Git-control+messages%2C+unintended+Codex+restart+attempts+and+shared+conversation+runtimes.+Improve+Preview+compiler+reuse%2Frefresh+selection+and+backup+category+isolation.%0A%0A%23%23%23+Download+and+verify%0A%0ADownload+%60Pokecode-v0.1.7.9.2.apk%60+from+this+release+and+%5BSHA256SUMS.txt%5D%28https%3A%2F%2Fraw.githubusercontent.com%2Ftopoftree%2FPokeCodePublic%2Fv0.1.7.9.2%2Freleases%2Fv0.1.7.9.2%2FSHA256SUMS.txt%29%2C+then+run+%60sha256sum+-c+SHA256SUMS.txt%60.%0A%0AAPK+SHA-256%3A%0A%0A%60%60%60text%0A6ffcd40967d3cd5fea04047b9d6be0fb099067b561ed5fa9492d6374041f32d4%0A%60%60%60%0A%0ARelease+signature%2C+package%2Fversion%2C+ZIP+integrity+and+16+KiB+alignment+passed.+Authenticated+voice+calls%2C+phone+audio%2FBluetooth%2C+background+behavior+and+installed-device+upgrades+still+require+device+validation.+Use+Chat+Voice+Mode+for+Android+audio%3B+the+Terminal+%60%2Fvoice%60+audio-device+path+remains+separate.%0A%0ANew+icon+notices+cover+MIT+and+CC0+assets.+Dependencies+and+packaged+native%2Fruntime+components+retain+their+versions+and+bytes%3B+no+new+or+changed+conflicting+copyleft+dependency+was+found.+Existing+runtime+source-delivery%2Fintegration%2C+ReVanced+AAPT2+license-scope+and+Google+SDK+obligations+remain+unresolved%3B+see+%5Bthird-party+notices%5D%28https%3A%2F%2Fgithub.com%2Ftopoftree%2FPokeCodePublic%2Fblob%2Fmain%2FTHIRD_PARTY_NOTICES.md%29.+Application+source+and+signing+material+remain+private.%0A)

Sign in as the repository maintainer, upload **Pokecode-v0.1.7.9.2.apk**, and
choose **Publish release** when ready. The editor link supplies
`v0.1.7.9.2`, the public `main` target, the title and the release notes below.
Publishing creates the version tag in this public documentation repository. The application source and signing material
remain in the private repository.

Use the newly prepared APK matching [SHA256SUMS.txt](SHA256SUMS.txt); another
build with the same version number can have a different checksum. A copy of the
checksum file can optionally be attached to the release too.

## Release notes

Signed production APK for **Android 13+ / ARM64**, version **0.1.7.9.2 / code 377**. Original release signature; R8 optimization and resource shrinking.

### Changes since v0.1.7.7.3.3

- Add Chat Voice Mode with an audio-reactive orb, automatic Codex startup, minimization, background audio and notification mute/close controls. Fix its voice protocol-header rejection.
- Add a focused-composer Plan mode toggle and clearer centered connection/stopped status.
- Keep Chat conversations bound to independent sessions. Add Project branch workspaces, GitHub import/binding, explicit bidirectional Sync, local Merge and remote branch renaming.
- Add Note default branch/session and Agent choices, individual Subblock queues, multi-selection and cancellation. Final generation waits for every version-group input and its completed task.
- Make Chat web/file links actionable and retain final deliverables as attachments. Add Time Capsule task summaries, activity/diff details and PDF/text/Word history export.
- Fix startup crashes when restoring Git-control messages, unintended Codex restart attempts and shared conversation runtimes. Improve Preview compiler reuse/refresh selection and backup category isolation.

### Download and verify

Download `Pokecode-v0.1.7.9.2.apk` from this release and [SHA256SUMS.txt](https://raw.githubusercontent.com/topoftree/PokeCodePublic/v0.1.7.9.2/releases/v0.1.7.9.2/SHA256SUMS.txt), then run `sha256sum -c SHA256SUMS.txt`.

APK SHA-256:

```text
6ffcd40967d3cd5fea04047b9d6be0fb099067b561ed5fa9492d6374041f32d4
```

Release signature, package/version, ZIP integrity and 16 KiB alignment passed. Authenticated voice calls, phone audio/Bluetooth, background behavior and installed-device upgrades still require device validation. Use Chat Voice Mode for Android audio; the Terminal `/voice` audio-device path remains separate.

New icon notices cover MIT and CC0 assets. Dependencies and packaged native/runtime components retain their versions and bytes; no new or changed conflicting copyleft dependency was found. Existing runtime source-delivery/integration, ReVanced AAPT2 license-scope and Google SDK obligations remain unresolved; see [third-party notices](https://github.com/topoftree/PokeCodePublic/blob/main/THIRD_PARTY_NOTICES.md). Application source and signing material remain private.
