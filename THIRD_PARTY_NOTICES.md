# Third-party notices for Pokecode

Release: **0.1.6.9**. Original inventory review: **2026-09-09**; release changes reviewed **2026-09-15**.

**Redistribution review remains incomplete.** This release retains the previously documented unresolved source-delivery, copyleft integration, and SDK obligations. This notice inventory is not a finding of legal compliance. Publishing the APK does not resolve or waive those obligations.

Pokecode itself is proprietary. These licenses apply only to their identified third-party components. They do not license Pokecode's application source. Any Pokecode terms must preserve the rights granted by the third-party licenses, including applicable source, modification and reverse-engineering rights.

## Scope and evidence

The review covers 15 distinct external production dependency declarations and 116 resolved external Android artifacts (including those direct dependencies), 63 embedded runtime package records, four additional native libraries bundled inside Python, copied terminal modules, and non-code assets. Test/debug dependencies, the Compose BOM, the complete Gradle distribution, compilers and other build-only tools are not listed as APK components merely because the project uses them. The newly bundled Gradle Wrapper fixture is covered below.

In the original v0.1.6.2.15 review, all 116 cached Android artifacts matched the SHA-256 of the corresponding publisher download, and R8 mapping showed original classes from 71 artifacts. Class absence does not prove that all inlined code or resources were removed. The inventory therefore conservatively includes the release inputs, with versions and original notices. It is not a claim that every class in each artifact is redistributed.

The component rows below link to publisher sources and preserved notices. Some upstream copyright files cover more files than are present in the APK; preserving those files does not mean that every described upstream program is distributed.

### Changes in v0.1.6.9 (since v0.1.6.8.16)

This release adds a Gradle Wrapper diagnostic fixture to the APK: the wrapper
JAR, generated POSIX launcher and wrapper properties target Gradle 9.6.1. The JAR
and launcher use [Apache-2.0](https://github.com/gradle/gradle/blob/v9.6.1/LICENSE).
Their [license and attribution](third_party_licenses/gradle-wrapper-9.6.1/) are
preserved here; the APK's wrapper JAR also contains `META-INF/LICENSE` and the
launcher retains its original copyright header. This bundled wrapper is an
exception to the build-only tooling excluded from the original inventory above.
The complete Gradle distribution is downloaded separately when needed.

Initialization and Terminal Update check and can repair the separately installed
JDK used to build Android projects. OpenJDK 17 uses [GPLv2 with the Classpath Exception](https://github.com/openjdk/jdk17u/blob/master/LICENSE).
It is a build tool downloaded separately into Ubuntu and is not distributed
inside the Pokecode APK. This setup change adds no bundled GPL dependency.
Existing source-delivery, copyleft integration and Google SDK obligations remain
as documented below.

The production Android dependency declarations are unchanged, and all 116 cached
external Android artifacts match the existing publisher-verified inventory. The
release APK's native libraries, bootstrap, embedded package repository,
third-party source archives and Maven version markers match v0.1.6.8.16 byte for
byte. No new font, icon collection, image asset, model weight or bundled copyleft
runtime component was identified. Static notification artwork reuses the existing
owner-supplied UFO asset; the updated README screenshot is supplied by the owner.

### Changes in v0.1.6.8.16 (since v0.1.6.8.6)

All 116 resolved external Android runtime artifacts retain the same coordinates and SHA-256 hashes as the previous public release. The new `file-access-ui` module is Pokecode integration code and reuses existing AndroidX dependencies. Packaged Maven version markers, the existing copyleft runtime binaries/packages, third-party source archives, and license text assets are unchanged. No new third-party font, image, model weight, or conflicting copyleft runtime component was identified.

Pokecode modified the existing Apache-2.0 terminal-emulator JNI bridge to close inherited descriptors and apply its Android file-access boundary. The rebuilt `libclaudenote_terminal.so` depends only on Android's system `libc.so`. The new `libpokecode_file_guard.so` is a Pokecode syscall-only executable with no dynamic-library dependencies. The added importer, file-access and Codex interaction helpers are Pokecode integration code; the Storage Helper is a separate APK release.

The native boundary uses Linux userspace API declarations, including [`filter.h`](https://github.com/torvalds/linux/blob/master/include/uapi/linux/filter.h) and [`seccomp.h`](https://github.com/torvalds/linux/blob/master/include/uapi/linux/seccomp.h), marked GPL-2.0 WITH Linux-syscall-note. The [upstream exception](https://github.com/torvalds/linux/blob/master/LICENSES/exceptions/Linux-syscall-note) expressly covers ordinary userspace use of kernel services, allowing non-GPL userspace programs. The [exception text](third_party_licenses/Linux-syscall-note.txt) and existing [GPL-2.0 text](third_party_licenses/GPL-2.0.txt) are retained. This header/API use does not introduce a new GPL program into the APK; it does not resolve the separate, existing runtime obligations below.

New action icons use the already listed Material icon collection. Existing copyright and license texts are retained. The changed JNI module attribution and syscall-exception reference are the notice updates for this release; SDK terms and the other outstanding issues remain unchanged.

### Changes in v0.1.6.8.5 (since v0.1.6.4)

The production dependency declarations and packaged Maven version markers are unchanged. The native shared libraries, bootstrap, embedded package repository, bundled third-party source archives and license text files match the previous public APK byte-for-byte. No new or upgraded copyleft component was identified in the APK delta; existing obligations below remain unresolved.

Pokecode modified the existing Apache-licensed terminal emulator for incremental row revisions and text projection. New UI actions use the already listed Material icon collection. The updated system icon is derived from the existing Pokecode artwork; the Live Notification now uses twelve owner-supplied UFO frames. No new third-party font or model weight was added.

The added authentication, Codex runtime and Preview helpers are Pokecode integration code. GitHub CLI is installed separately during environment setup and has an [MIT license](https://github.com/cli/cli/blob/trunk/LICENSE); it is not embedded in this APK. Downloaded tools and user-installed global packages retain their own terms.

### Changes in v0.1.6.4

The production dependency declarations, packaged Maven version markers, and embedded runtime package versions are unchanged from v0.1.6.2.15. No new third-party font, image asset, or native library was introduced. The sketch action uses the existing Apache-licensed Material icon collection.

The bundled PRoot 5.1.107.89 and libandroid-shmem 0.7 native binaries, bootstrap, Python package, and PRoot-Distro package were modified to use the new `com.pokecode` private paths. Binary path relocation preserves byte offsets; package paths, ownership metadata, and integrity digests were regenerated. The PRoot loader and talloc binary are unchanged. These modifications retain the existing component licenses and do not resolve the outstanding source-delivery or integration requirements below.

## License obligations and outstanding decisions

- **MIT, BSD, ISC, curl and other permissive grants:** retain the applicable copyright, permission terms, disclaimers and no-endorsement clauses. Exact custom grants are preserved rather than replaced by a generic MIT label.
- **Apache-2.0 (Apache License 2.0):** preserve its full text, applicable upstream NOTICE material and attribution; identify changes to covered source. The Apache Commons NOTICE files are retained here. See [Apache section 4](https://www.apache.org/licenses/LICENSE-2.0).
- **GPL:** provide complete corresponding source for the covered programs and modifications, including required build/install scripts, under a valid distribution route. The separate-process architecture is evidence to assess, not an automatic proprietary-distribution exemption. The Android application is not automatically relabeled GPL by this draft.
- **LGPL:** provide the applicable library source and modifications, notices and license texts, and satisfy the applicable relinking/replacement and conditional installation-information requirements. A rebuilt talloc was successfully loaded by an isolated copy of PRoot. This is not proof that recipients can install and operate a modified APK. See [LGPLv3 section 4](https://opensource.org/license/lgpl-3-0).
- **MPL-2.0:** the converted Mozilla certificate store needs its covered source data and notices made available. Its file-level obligations do not, by themselves, require disclosure of unrelated Pokecode files. See [Mozilla's FAQ](https://www.mozilla.org/en-US/MPL/2.0/FAQ/).
- **EUPL-1.2:** the bundled util-linux `coresched` program has this grant; retain the license and supply the covered source. The scope of any derivative-work obligations needs review alongside the other runtime programs.
- **Documentation/data:** preserve the libunistring manual's dual GFDL/GPL grant, the Unicode notices, compiled terminal-description sources, and original certificate notices. The `renice` source contains a Berkeley advertising acknowledgement; it is reproduced below without relying on an unstated waiver.
- **AGPL:** no AGPL-covered executable/component has been confirmed by this review. Generic AGPL license documents inside the runtime's license collection do not establish such a dependency.
- **Google SDKs:** review the separately applicable [SDK terms and privacy notice](SDK_NOTICE.md), including GenAI audience and production-use restrictions. These SDKs are not assumed to be open source.

The proposed source delivery is a versioned third-party source archive beside the APK, at no extra charge, with checksums, patches and build instructions. That archive is being assembled locally and is **not yet complete or published**. Links to upstream projects alone are not being presented as fulfillment of corresponding-source obligations.

## Notices during execution

No reviewed license establishes a universal requirement for a screen named “Open Source Licenses.” Apache notices can be placed in appropriate accompanying notices/documentation. LGPLv3 section 4(c), however, requires library copyright and license references when the combined work displays copyright notices during execution; modified interactive GPL programs can have additional notice requirements. PRoot's `--version` output displays its copyright but currently lacks a talloc reference. The precise runtime notice changes and accessible offline license location remain unresolved. GitHub-only notices have not been established as sufficient for this release, and no unrelated UI redesign has been made.

The signed APK retains its pre-publication notice snapshots. This repository records the current publication status; the outstanding obligations described in those snapshots have not been resolved by publication.

## Android libraries and SDKs

Each coordinate specifies the exact resolved version. Copyright holders remain the original authors; component directories preserve the original notices and source copyright statements where available.

| Component and version | License / terms | Official project or publisher artifact | Preserved notices |
| --- | --- | --- | --- |
| `androidx.activity:activity-compose:1.13.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/activity#1.13.0) | [notices](third_party_licenses/maven/androidx.activity__activity-compose__1.13.0/) |
| `androidx.activity:activity-ktx:1.13.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/activity#1.13.0) | [notices](third_party_licenses/maven/androidx.activity__activity-ktx__1.13.0/) |
| `androidx.activity:activity:1.13.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/activity#1.13.0) | [notices](third_party_licenses/maven/androidx.activity__activity__1.13.0/) |
| `androidx.annotation:annotation-experimental:1.4.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/annotation#1.4.1) | [notices](third_party_licenses/maven/androidx.annotation__annotation-experimental__1.4.1/) |
| `androidx.annotation:annotation-jvm:1.9.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/annotation#1.9.1) | [notices](third_party_licenses/maven/androidx.annotation__annotation-jvm__1.9.1/) |
| `androidx.appcompat:appcompat-resources:1.6.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/appcompat#1.6.1) | [notices](third_party_licenses/maven/androidx.appcompat__appcompat-resources__1.6.1/) |
| `androidx.appcompat:appcompat:1.6.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/appcompat#1.6.1) | [notices](third_party_licenses/maven/androidx.appcompat__appcompat__1.6.1/) |
| `androidx.arch.core:core-common:2.2.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/arch-core#2.2.0) | [notices](third_party_licenses/maven/androidx.arch.core__core-common__2.2.0/) |
| `androidx.arch.core:core-runtime:2.2.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/arch-core#2.2.0) | [notices](third_party_licenses/maven/androidx.arch.core__core-runtime__2.2.0/) |
| `androidx.autofill:autofill:1.0.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx) | [notices](third_party_licenses/maven/androidx.autofill__autofill__1.0.0/) |
| `androidx.collection:collection-jvm:1.5.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/collection#1.5.0) | [notices](third_party_licenses/maven/androidx.collection__collection-jvm__1.5.0/) |
| `androidx.collection:collection-ktx:1.5.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/collection#1.5.0) | [notices](third_party_licenses/maven/androidx.collection__collection-ktx__1.5.0/) |
| `androidx.compose.animation:animation-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-animation#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.animation__animation-android__1.11.3/) |
| `androidx.compose.animation:animation-core-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-animation#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.animation__animation-core-android__1.11.3/) |
| `androidx.compose.foundation:foundation-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-foundation#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.foundation__foundation-android__1.11.3/) |
| `androidx.compose.foundation:foundation-layout-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-foundation#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.foundation__foundation-layout-android__1.11.3/) |
| `androidx.compose.material3:material3-android:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-material3#1.4.0) | [notices](third_party_licenses/maven/androidx.compose.material3__material3-android__1.4.0/) |
| `androidx.compose.material:material-icons-core-android:1.7.8` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-material#1.7.8) | [notices](third_party_licenses/maven/androidx.compose.material__material-icons-core-android__1.7.8/) |
| `androidx.compose.material:material-icons-extended-android:1.7.8` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-material#1.7.8) | [notices](third_party_licenses/maven/androidx.compose.material__material-icons-extended-android__1.7.8/) |
| `androidx.compose.material:material-ripple-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-material#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.material__material-ripple-android__1.11.3/) |
| `androidx.compose.runtime:runtime-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-runtime#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.runtime__runtime-android__1.11.3/) |
| `androidx.compose.runtime:runtime-annotation-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-runtime#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.runtime__runtime-annotation-android__1.11.3/) |
| `androidx.compose.runtime:runtime-retain-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-runtime#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.runtime__runtime-retain-android__1.11.3/) |
| `androidx.compose.runtime:runtime-saveable-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-runtime#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.runtime__runtime-saveable-android__1.11.3/) |
| `androidx.compose.ui:ui-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-android__1.11.3/) |
| `androidx.compose.ui:ui-geometry-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-geometry-android__1.11.3/) |
| `androidx.compose.ui:ui-graphics-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-graphics-android__1.11.3/) |
| `androidx.compose.ui:ui-text-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-text-android__1.11.3/) |
| `androidx.compose.ui:ui-tooling-preview-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-tooling-preview-android__1.11.3/) |
| `androidx.compose.ui:ui-unit-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-unit-android__1.11.3/) |
| `androidx.compose.ui:ui-util-android:1.11.3` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/compose-ui#1.11.3) | [notices](third_party_licenses/maven/androidx.compose.ui__ui-util-android__1.11.3/) |
| `androidx.concurrent:concurrent-futures:1.1.0` | Apache-2.0 | [publisher](https://developer.android.com/topic/libraries/architecture/index.html) | [notices](third_party_licenses/maven/androidx.concurrent__concurrent-futures__1.1.0/) |
| `androidx.core:core-ktx:1.18.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/core#1.18.0) | [notices](third_party_licenses/maven/androidx.core__core-ktx__1.18.0/) |
| `androidx.core:core-viewtree:1.0.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/core#1.0.0) | [notices](third_party_licenses/maven/androidx.core__core-viewtree__1.0.0/) |
| `androidx.core:core:1.18.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/core#1.18.0) | [notices](third_party_licenses/maven/androidx.core__core__1.18.0/) |
| `androidx.cursoradapter:cursoradapter:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.cursoradapter__cursoradapter__1.0.0/) |
| `androidx.customview:customview-poolingcontainer:1.0.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/customview#1.0.0) | [notices](third_party_licenses/maven/androidx.customview__customview-poolingcontainer__1.0.0/) |
| `androidx.customview:customview:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.customview__customview__1.0.0/) |
| `androidx.documentfile:documentfile:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.documentfile__documentfile__1.0.0/) |
| `androidx.drawerlayout:drawerlayout:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.drawerlayout__drawerlayout__1.0.0/) |
| `androidx.dynamicanimation:dynamicanimation:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.dynamicanimation__dynamicanimation__1.0.0/) |
| `androidx.emoji2:emoji2-views-helper:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/emoji2#1.4.0) | [notices](third_party_licenses/maven/androidx.emoji2__emoji2-views-helper__1.4.0/) |
| `androidx.emoji2:emoji2:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/emoji2#1.4.0) | [notices](third_party_licenses/maven/androidx.emoji2__emoji2__1.4.0/) |
| `androidx.fragment:fragment:1.3.6` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/fragment#1.3.6) | [notices](third_party_licenses/maven/androidx.fragment__fragment__1.3.6/) |
| `androidx.graphics:graphics-path:1.0.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/graphics#1.0.1) | [notices](third_party_licenses/maven/androidx.graphics__graphics-path__1.0.1/) |
| `androidx.interpolator:interpolator:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.interpolator__interpolator__1.0.0/) |
| `androidx.legacy:legacy-support-core-utils:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.legacy__legacy-support-core-utils__1.0.0/) |
| `androidx.lifecycle:lifecycle-common-java8:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-common-java8__2.10.0/) |
| `androidx.lifecycle:lifecycle-common-jvm:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-common-jvm__2.10.0/) |
| `androidx.lifecycle:lifecycle-livedata-core-ktx:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-livedata-core-ktx__2.10.0/) |
| `androidx.lifecycle:lifecycle-livedata-core:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-livedata-core__2.10.0/) |
| `androidx.lifecycle:lifecycle-livedata:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-livedata__2.10.0/) |
| `androidx.lifecycle:lifecycle-process:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-process__2.10.0/) |
| `androidx.lifecycle:lifecycle-runtime-android:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-runtime-android__2.10.0/) |
| `androidx.lifecycle:lifecycle-runtime-compose-android:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-runtime-compose-android__2.10.0/) |
| `androidx.lifecycle:lifecycle-runtime-ktx-android:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-runtime-ktx-android__2.10.0/) |
| `androidx.lifecycle:lifecycle-viewmodel-android:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-viewmodel-android__2.10.0/) |
| `androidx.lifecycle:lifecycle-viewmodel-compose-android:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-viewmodel-compose-android__2.10.0/) |
| `androidx.lifecycle:lifecycle-viewmodel-ktx:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-viewmodel-ktx__2.10.0/) |
| `androidx.lifecycle:lifecycle-viewmodel-savedstate-android:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-viewmodel-savedstate-android__2.10.0/) |
| `androidx.lifecycle:lifecycle-viewmodel:2.10.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/lifecycle#2.10.0) | [notices](third_party_licenses/maven/androidx.lifecycle__lifecycle-viewmodel__2.10.0/) |
| `androidx.loader:loader:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.loader__loader__1.0.0/) |
| `androidx.localbroadcastmanager:localbroadcastmanager:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.localbroadcastmanager__localbroadcastmanager__1.0.0/) |
| `androidx.navigationevent:navigationevent-android:1.0.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/navigationevent#1.0.0) | [notices](third_party_licenses/maven/androidx.navigationevent__navigationevent-android__1.0.0/) |
| `androidx.navigationevent:navigationevent-compose-android:1.0.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/navigationevent#1.0.0) | [notices](third_party_licenses/maven/androidx.navigationevent__navigationevent-compose-android__1.0.0/) |
| `androidx.print:print:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.print__print__1.0.0/) |
| `androidx.profileinstaller:profileinstaller:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/profileinstaller#1.4.0) | [notices](third_party_licenses/maven/androidx.profileinstaller__profileinstaller__1.4.0/) |
| `androidx.resourceinspection:resourceinspection-annotation:1.0.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/resourceinspection#1.0.1) | [notices](third_party_licenses/maven/androidx.resourceinspection__resourceinspection-annotation__1.0.1/) |
| `androidx.savedstate:savedstate-android:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/savedstate#1.4.0) | [notices](third_party_licenses/maven/androidx.savedstate__savedstate-android__1.4.0/) |
| `androidx.savedstate:savedstate-compose-android:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/savedstate#1.4.0) | [notices](third_party_licenses/maven/androidx.savedstate__savedstate-compose-android__1.4.0/) |
| `androidx.savedstate:savedstate-ktx:1.4.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/savedstate#1.4.0) | [notices](third_party_licenses/maven/androidx.savedstate__savedstate-ktx__1.4.0/) |
| `androidx.startup:startup-runtime:1.1.1` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/startup#1.1.1) | [notices](third_party_licenses/maven/androidx.startup__startup-runtime__1.1.1/) |
| `androidx.tracing:tracing:1.2.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/tracing#1.2.0) | [notices](third_party_licenses/maven/androidx.tracing__tracing__1.2.0/) |
| `androidx.transition:transition:1.6.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/transition#1.6.0) | [notices](third_party_licenses/maven/androidx.transition__transition__1.6.0/) |
| `androidx.vectordrawable:vectordrawable-animated:1.1.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx) | [notices](third_party_licenses/maven/androidx.vectordrawable__vectordrawable-animated__1.1.0/) |
| `androidx.vectordrawable:vectordrawable:1.1.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx) | [notices](third_party_licenses/maven/androidx.vectordrawable__vectordrawable__1.1.0/) |
| `androidx.versionedparcelable:versionedparcelable:1.1.1` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.versionedparcelable__versionedparcelable__1.1.1/) |
| `androidx.viewpager:viewpager:1.0.0` | Apache-2.0 | [publisher](http://developer.android.com/tools/extras/support-library.html) | [notices](third_party_licenses/maven/androidx.viewpager__viewpager__1.0.0/) |
| `androidx.webkit:webkit:1.16.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/webkit#1.16.0) | [notices](third_party_licenses/maven/androidx.webkit__webkit__1.16.0/) |
| `androidx.window:window-core-android:1.5.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/window#1.5.0) | [notices](third_party_licenses/maven/androidx.window__window-core-android__1.5.0/) |
| `androidx.window:window:1.5.0` | Apache-2.0 | [publisher](https://developer.android.com/jetpack/androidx/releases/window#1.5.0) | [notices](third_party_licenses/maven/androidx.window__window__1.5.0/) |
| `com.google.android.datatransport:transport-api:2.2.1` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/android/datatransport/transport-api/2.2.1/transport-api-2.2.1.aar) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `com.google.android.datatransport:transport-backend-cct:2.3.3` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/android/datatransport/transport-backend-cct/2.3.3/transport-backend-cct-2.3.3.aar) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `com.google.android.datatransport:transport-runtime:2.2.6` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/android/datatransport/transport-runtime/2.2.6/transport-runtime-2.2.6.aar) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `com.google.android.gms:play-services-base:18.5.0` | Google Android SDK terms | [publisher](https://dl.google.com/dl/android/maven2/com/google/android/gms/play-services-base/18.5.0/play-services-base-18.5.0.aar) | [SDK notice](SDK_NOTICE.md) |
| `com.google.android.gms:play-services-basement:18.9.0` | Google Android SDK terms | [publisher](https://dl.google.com/dl/android/maven2/com/google/android/gms/play-services-basement/18.9.0/play-services-basement-18.9.0.aar) | [SDK notice](SDK_NOTICE.md) |
| `com.google.android.gms:play-services-tasks:18.2.0` | Google Android SDK terms | [publisher](https://dl.google.com/dl/android/maven2/com/google/android/gms/play-services-tasks/18.2.0/play-services-tasks-18.2.0.aar) | [SDK notice](SDK_NOTICE.md) |
| `com.google.code.findbugs:jsr305:3.0.2` | Apache-2.0 | [publisher](http://findbugs.sourceforge.net/) | [notices](third_party_licenses/maven/com.google.code.findbugs__jsr305__3.0.2/) |
| `com.google.errorprone:error_prone_annotations:2.7.1` | Apache-2.0 | [publisher](https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_annotations/2.7.1/error_prone_annotations-2.7.1.jar) | [notices](third_party_licenses/maven/com.google.errorprone__error_prone_annotations__2.7.1/) |
| `com.google.firebase:firebase-annotations:16.0.0` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/firebase/firebase-annotations/16.0.0/firebase-annotations-16.0.0.jar) | [notices](third_party_licenses/maven/com.google.firebase__firebase-annotations__16.0.0/) |
| `com.google.firebase:firebase-components:16.1.0` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/firebase/firebase-components/16.1.0/firebase-components-16.1.0.aar) | [notices](third_party_licenses/maven/com.google.firebase__firebase-components__16.1.0/) |
| `com.google.firebase:firebase-encoders-json:17.1.0` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/firebase/firebase-encoders-json/17.1.0/firebase-encoders-json-17.1.0.aar) | [notices](third_party_licenses/maven/com.google.firebase__firebase-encoders-json__17.1.0/) |
| `com.google.firebase:firebase-encoders:16.1.0` | Apache-2.0 | [publisher](https://dl.google.com/dl/android/maven2/com/google/firebase/firebase-encoders/16.1.0/firebase-encoders-16.1.0.jar) | [notices](third_party_licenses/maven/com.google.firebase__firebase-encoders__16.1.0/) |
| `com.google.guava:failureaccess:1.0.1` | Apache-2.0 | [publisher](https://repo.maven.apache.org/maven2/com/google/guava/failureaccess/1.0.1/failureaccess-1.0.1.jar) | [notices](third_party_licenses/maven/com.google.guava__failureaccess__1.0.1/) |
| `com.google.guava:guava:31.0.1-jre` | Apache-2.0 | [publisher](https://github.com/google/guava) | [notices](third_party_licenses/maven/com.google.guava__guava__31.0.1-jre/) |
| `com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava` | Apache-2.0 | [publisher](https://repo.maven.apache.org/maven2/com/google/guava/listenablefuture/9999.0-empty-to-avoid-conflict-with-guava/listenablefuture-9999.0-empty-to-avoid-conflict-with-guava.jar) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `com.google.j2objc:j2objc-annotations:1.3` | Apache-2.0 | [publisher](https://github.com/google/j2objc/) | [notices](third_party_licenses/maven/com.google.j2objc__j2objc-annotations__1.3/) |
| `com.google.mlkit:common:18.11.0` | Google ML Kit terms; GenAI terms where applicable | [publisher](https://dl.google.com/dl/android/maven2/com/google/mlkit/common/18.11.0/common-18.11.0.aar) | [SDK notice](SDK_NOTICE.md) |
| `com.google.mlkit:genai-common:1.0.0-beta3` | Google ML Kit terms; GenAI terms where applicable | [publisher](https://dl.google.com/dl/android/maven2/com/google/mlkit/genai-common/1.0.0-beta3/genai-common-1.0.0-beta3.aar) | [SDK notice](SDK_NOTICE.md) |
| `com.google.mlkit:genai-speech-recognition:1.0.0-alpha1` | Google ML Kit terms; GenAI terms where applicable | [publisher](https://dl.google.com/dl/android/maven2/com/google/mlkit/genai-speech-recognition/1.0.0-alpha1/genai-speech-recognition-1.0.0-alpha1.aar) | [SDK notice](SDK_NOTICE.md) |
| `commons-codec:commons-codec:1.19.0` | Apache-2.0 | [publisher](https://commons.apache.org/proper/commons-codec/) | [notices](third_party_licenses/maven/commons-codec__commons-codec__1.19.0/) |
| `commons-io:commons-io:2.20.0` | Apache-2.0 | [publisher](https://commons.apache.org/proper/commons-io/) | [notices](third_party_licenses/maven/commons-io__commons-io__2.20.0/) |
| `javax.inject:javax.inject:1` | Apache-2.0 | [publisher](https://repo.maven.apache.org/maven2/javax/inject/javax.inject/1/javax.inject-1.jar) | [notices](third_party_licenses/maven/javax.inject__javax.inject__1/) |
| `org.apache.commons:commons-compress:1.28.0` | Apache-2.0 | [publisher](https://commons.apache.org/proper/commons-compress/) | [notices](third_party_licenses/maven/org.apache.commons__commons-compress__1.28.0/) |
| `org.apache.commons:commons-lang3:3.18.0` | Apache-2.0 | [publisher](https://commons.apache.org/proper/commons-lang/) | [notices](third_party_licenses/maven/org.apache.commons__commons-lang3__3.18.0/) |
| `org.checkerframework:checker-qual:3.12.0` | MIT | [publisher](https://checkerframework.org) | [notices](third_party_licenses/maven/org.checkerframework__checker-qual__3.12.0/) |
| `org.jetbrains.kotlin:kotlin-stdlib-jdk7:2.2.20` | Apache-2.0 | [publisher](https://kotlinlang.org/) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `org.jetbrains.kotlin:kotlin-stdlib:2.2.20` | Apache-2.0 | [publisher](https://kotlinlang.org/) | [notices](third_party_licenses/maven/org.jetbrains.kotlin__kotlin-stdlib__2.2.20/) |
| `org.jetbrains.kotlinx:kotlinx-coroutines-android:1.10.2` | Apache-2.0 | [publisher](https://github.com/Kotlin/kotlinx.coroutines) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `org.jetbrains.kotlinx:kotlinx-coroutines-core-jvm:1.10.2` | Apache-2.0 | [publisher](https://github.com/Kotlin/kotlinx.coroutines) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `org.jetbrains.kotlinx:kotlinx-coroutines-guava:1.10.2` | Apache-2.0 | [publisher](https://github.com/Kotlin/kotlinx.coroutines) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `org.jetbrains.kotlinx:kotlinx-coroutines-reactive:1.10.2` | Apache-2.0 | [publisher](https://github.com/Kotlin/kotlinx.coroutines) | [Apache text](third_party_licenses/Apache-2.0.txt) |
| `org.jetbrains.kotlinx:kotlinx-serialization-core-jvm:1.7.3` | Apache-2.0 | [publisher](https://github.com/Kotlin/kotlinx.serialization) | [notices](third_party_licenses/maven/org.jetbrains.kotlinx__kotlinx-serialization-core-jvm__1.7.3/) |
| `org.jetbrains:annotations:23.0.0` | Apache-2.0 | [publisher](https://github.com/JetBrains/java-annotations) | [notices](third_party_licenses/maven/org.jetbrains__annotations__23.0.0/) |
| `org.jspecify:jspecify:1.0.0` | Apache-2.0 | [publisher](http://jspecify.org/) | [notices](third_party_licenses/maven/org.jspecify__jspecify__1.0.0/) |
| `org.reactivestreams:reactive-streams:1.0.3` | CC0-1.0 | [publisher](http://www.reactive-streams.org/) | [CC0 text](third_party_licenses/CC0-1.0.txt) |

`javax.inject:1` has no license declaration in the retrieved POM; its source `Inject.java` explicitly grants Apache-2.0 and credits the JSR-330 Expert Group. The permission was verified from that source rather than guessed.

AndroidX Graphics Path also contains native code and Apache-licensed math headers derived from AOSP/Filament. Source headers were inspected; the artifact is a byte match to the publisher. Exact native-source revision alignment remains a provenance check. Material icons supplied by Compose are covered by their component's Apache license. No standalone third-party font or model-weight file was found in the inspected release assets/runtime.

## Copied terminal modules

The terminal emulator and terminal view derive from Termux app **v0.118.3**, commit `5b657c6adf4304e5198951ce815fe0205dcac29c`. The upstream [license statement](https://github.com/termux/termux-app/blob/v0.118.3/LICENSE.md) expressly places these modules under the Apache-2.0 terminal-emulator exception. The whole Termux application is not being represented as Apache-licensed.

Original copyrights remain with the Android Terminal Emulator, Termux and other named contributors. Pokecode changes include Java package/JNI renaming, integration with its workspace, a PTY string-release correction and an echo-state query. Version 0.1.6.4 also adds light-theme rendering and appearance updates that preserve the terminal session, selection, and viewport. Version 0.1.6.8.5 additionally modifies `TerminalBuffer` and `TerminalRow` for incremental revisions and immutable row projections. Version 0.1.6.8.16 includes the JNI file-access boundary changes described above. The original [module license statement](third_party_licenses/runtime/terminal-emulator/LICENSE.md) and [Apache text](third_party_licenses/Apache-2.0.txt) are preserved. Final copied-file attribution comparison remains part of review.

## Embedded native and command-line runtime

The directly packaged dash 0.5.12-2 shell uses the original BSD-style notice, including the documented GPL generator caveat. Its native path strings were adapted to Android system paths; the original notice is preserved.

These are package records, not an additive count of entirely independent upstream projects. Some packages split one upstream source, and the directly packaged PRoot/talloc/shared-memory objects overlap with the runtime packages. The four Python-bundled libraries at the end were discovered from packaged files and native dependencies, even though they have no independent dpkg package record.

| Package | Distributed version | License evidence / component scope | Copyright project | Source / notices and obligations |
| --- | --- | --- | --- | --- |
| apt | 2.8.1-2 | GPL-2.0-or-later; rsh source has GPL-2.0-only ambiguity | APT contributors, Canonical, SPI | [source](https://packages.debian.org/apt) [notices](third_party_licenses/runtime/apt/). Preserve upstream COPYING with its file-level caveats; source and build review required. |
| attr | 2.6.0 | GPL-2.0-or-later tools; LGPL-2.1-or-later libattr | Andreas Gruenbacher, Silicon Graphics and contributors | [source](http://savannah.nongnu.org/projects/attr/) [notices](third_party_licenses/runtime/attr/). Includes attr/getfattr/setfattr and libattr; provide source and preserve both license families. |
| bash | 5.3.15 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/bash/) [notices](third_party_licenses/runtime/bash/). Provide Bash 5.3 plus patches 001–015 and Android build changes. |
| bzip2 | 1.0.8-8 | bzip2-1.0.6 (BSD-style) | Julian Seward | [source](http://www.bzip.org/). Preserve the exact bzip2 license; modified versions must be identified. |
| ca-certificates | 1:2026.07.16 | MPL-2.0 | Mozilla contributors and certificate issuers | [source](https://curl.se/docs/caextract.html). 2026-07-16 PEM is byte-identical to curl's archive; preserve notices and make the covered source data available. |
| command-not-found | 3.5.0-4 | Apache-2.0 | Termux contributors | [source](https://github.com/termux/command-not-found) [notices](third_party_licenses/runtime/command-not-found/). Preserve Apache text and notices. |
| coreutils | 9.11-1 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/coreutils/) [notices](third_party_licenses/runtime/coreutils/). Provide corresponding source, included gnulib code and build changes. |
| curl | 8.21.0 | curl license (MIT-style) | Daniel Stenberg and contributors | [source](https://curl.se/). Preserve the exact COPYING, including its copyright and no-endorsement terms. |
| dash | 0.5.12-2 | BSD-3-Clause; generator GPL-2.0-or-later caveat | UC Regents, Christos Zoulas, Herbert Xu | [source](http://gondor.apana.org.au/~herbert/dash/) [notices](third_party_licenses/runtime/dash/). Keep complete dash COPYING; it explicitly discusses linked output of mksignames.c. Source and post-link transformations require review. |
| diffutils | 3.12-2 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/diffutils/) [notices](third_party_licenses/runtime/diffutils/). Source, notices and modifications required. |
| dpkg | 1.22.6-5 | GPL-2.0-or-later; file-specific permissive notices | Dpkg authors and contributors | [source](https://packages.debian.org/dpkg) [notices](third_party_licenses/runtime/dpkg/). Pinned source and patches staged; preserve individual grants. |
| findutils | 4.10.0-1 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/findutils/) [notices](third_party_licenses/runtime/findutils/). Source, notices and modifications required. |
| gpgv | 2.5.17 | GPL-3.0-or-later; additional file grants | Werner Koch, g10 Code and contributors | [source](https://www.gnupg.org/). GnuPG source supplies gpgv; keep COPYING.other and relevant source licenses. |
| grep | 3.12-3 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/grep/) [notices](third_party_licenses/runtime/grep/). Source, notices and modifications required. |
| gzip | 1.14-1 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/gzip/) [notices](third_party_licenses/runtime/gzip/). Source, notices and modifications required. |
| less | 704 | Less license OR GPL-3.0-or-later | Mark Nudelman | [source](https://www.greenwoodsoftware.com/less/) [notices](third_party_licenses/runtime/less/). Preserve the custom permissive Less license and original copyright; do not label it standard BSD. |
| libandroid-glob | 0.6-3 | BSD-3-Clause | The NetBSD Foundation and contributors | [source](https://man7.org/linux/man-pages/man3/glob.3.html) [notices](third_party_licenses/runtime/libandroid-glob/). Preserve the bundled grant and copyright. |
| libandroid-posix-semaphore | 0.1-4 | MIT | Termux contributors; named authors in the notice | [source](https://man7.org/linux/man-pages/man7/sem_overview.7.html) [notices](third_party_licenses/runtime/libandroid-posix-semaphore/). Preserve exact MIT copyright and permission notice. |
| libandroid-selinux | 14.0.0.11-1 | Public-domain grant; individual file notices | US National Security Agency and contributors | [source](https://selinuxproject.org) [notices](third_party_licenses/runtime/libandroid-selinux/). Only libselinux is packaged; broader upstream NOTICE covers other parts too. Retained-file mapping needs final review. |
| libandroid-shmem | 0.7 | BSD-3-Clause | Termux contributors; named authors in LICENSE | [source](https://github.com/termux/libandroid-shmem) [notices](third_party_licenses/runtime/libandroid-shmem/). Preserve the exact license and copyright; modified native paths documented separately. |
| libandroid-support | 29-1 | Apache-2.0; MIT; BSD and other file-level notices | AOSP, musl, wcwidth and other contributors | [source](https://github.com/termux/libandroid-support) [notices](third_party_licenses/runtime/libandroid-support/). Includes bundled libc compatibility code; retain complete LICENSE.txt and wcwidth notice. |
| libassuan | 3.0.2-1 | LGPL-2.1-or-later library | Free Software Foundation, g10 Code and contributors | [source](https://www.gnupg.org/related_software/libassuan/) [notices](third_party_licenses/runtime/libassuan/). The package's GPL label does not replace the library's explicit LGPL grant; source and linking review required. |
| libbz2 | 1.0.8-8 | bzip2-1.0.6 (BSD-style) | Julian Seward | [source](http://www.bzip.org/) [notices](third_party_licenses/runtime/libbz2/). Same upstream source and exact grant as bzip2. |
| libc++ | 29 | Apache-2.0 WITH LLVM-exception; associated runtime notices | LLVM, libc++, libc++abi, libunwind contributors | [source](https://libcxx.llvm.org/) [notices](third_party_licenses/runtime/libc++/). NDK r29 runtime; retain supplied NDK notices. The old NCSA recipe label is not a sufficient runtime license inventory. |
| libcap-ng | 2:0.9.3 | LGPL-2.1-or-later library | Steve Grubb, Red Hat and contributors | [source](https://people.redhat.com/sgrubb/libcap-ng/) [notices](third_party_licenses/runtime/libcap-ng/). Provide applicable source and library modification/relinking rights. |
| libcap | 2.69-1 | BSD-3-Clause OR GPL-2.0-only, unless file says otherwise | Andrew G. Morgan and contributors | [source](https://sites.google.com/site/fullycapable/) [notices](third_party_licenses/runtime/libcap/). Retain the full dual-license notice and all file copyright notices. |
| libcurl | 8.21.0 | curl license (MIT-style) | Daniel Stenberg and contributors | [source](https://curl.se/) [notices](third_party_licenses/runtime/libcurl/). Same exact COPYING as curl; linked libraries have their own terms. |
| libgcrypt | 1.12.2 | LGPL-2.1-or-later library; GPL and permissive file grants | g10 Code, FSF and named contributors | [source](https://www.gnu.org/software/libgcrypt/) [notices](third_party_licenses/runtime/libgcrypt/). Preserve LICENSES and applicable source; compiled crypto routines carry additional notices. |
| libgmp | 6.3.0-2 | LGPL-3.0-or-later OR GPL-2.0-or-later | Free Software Foundation and contributors | [source](https://gmplib.org/) [notices](third_party_licenses/runtime/libgmp/). Source and library replacement/relinking obligations; retain both original grants. |
| libgnutls | 3.8.13-1 | LGPL-2.1-or-later library; supplementary file notices | FSF, Nikos Mavrogiannopoulos and contributors | [source](https://www.gnutls.org/) [notices](third_party_licenses/runtime/libgnutls/). Library package, not all GPL command-line utilities from the upstream project; source and linking review required. |
| libgpg-error | 1.61 | LGPL-2.1-or-later; FSFULLR scripts; GPL-3.0-or-later yat2m | g10 Code, FSF and contributors | [source](https://www.gnupg.org/related_software/libgpg-error/) [notices](third_party_licenses/runtime/libgpg-error/). Includes programs/config scripts as well as a library; preserve their separate grants. |
| libiconv | 1.18-1 | LGPL-2.1-or-later library; GPL-3.0-or-later tools | Free Software Foundation and contributors | [source](https://www.gnu.org/software/libiconv/) [notices](third_party_licenses/runtime/libiconv/). Provide both library and distributed utility sources. |
| libidn2 | 2.3.8-1 | LGPL-3.0-or-later OR GPL-2.0-or-later library; GPL-3.0-or-later idn2; Unicode terms | Free Software Foundation, Unicode and contributors | [source](https://www.gnu.org/software/libidn/#libidn2) [notices](third_party_licenses/runtime/libidn2/). The idn2 executable is distributed; keep COPYING.unicode and all corresponding source. |
| liblz4 | 1.10.0-1 | BSD-2-Clause library | Yann Collet and contributors | [source](https://lz4.github.io/lz4/) [notices](third_party_licenses/runtime/liblz4/). Only the library is packaged; upstream CLI GPL terms do not automatically apply to it. |
| liblzma | 5.8.3 | 0BSD library | The XZ Utils authors and contributors | [source](https://tukaani.org/xz/) [notices](third_party_licenses/runtime/liblzma/). Keep attribution and source-level caveats in COPYING; xz helper scripts are listed under xz-utils. |
| libmd | 1.1.0-1 | BSD-2-Clause; BSD-3-Clause; ISC; other grants in COPYING | Colin Plumb, UC Regents, RSA Data Security and others | [source](https://www.hadrons.org/software/libmd/) [notices](third_party_licenses/runtime/libmd/). Preserve complete COPYING; it consolidates per-file notices. |
| libnettle | 4.0+really3.10.2 | LGPL-3.0-or-later OR GPL-2.0-or-later; file-specific notices | Niels Möller and contributors | [source](https://www.lysator.liu.se/~nisse/nettle/) [notices](third_party_licenses/runtime/libnettle/). Source and linking review required; use compatible permitted license choices per combination. |
| libnghttp2 | 1.70.0 | MIT | Tatsuhiro Tsujikawa and contributors | [source](https://nghttp2.org/) [notices](third_party_licenses/runtime/libnghttp2/). Preserve COPYING and copyright. |
| libnpth | 1.6-3 | LGPL-2.1-or-later | g10 Code and contributors | [source](https://www.gnupg.org/related_software/npth/) [notices](third_party_licenses/runtime/libnpth/). Use source grant, not the older LGPL-2.0 package label; source and linking review required. |
| libsmartcols | 2.42.1-4 | LGPL-2.1-or-later; generated parser exception | Karel Zak and util-linux contributors | [source](https://en.wikipedia.org/wiki/Util-linux). Part of util-linux; preserve libsmartcols license and Bison skeleton exception where applicable. |
| libssh2 | 1.11.1-2 | BSD-3-Clause | Daniel Stenberg, Sara Golemon, The Written Word and others | [source](https://www.libssh2.org) [notices](third_party_licenses/runtime/libssh2/). Preserve complete COPYING and named authors. |
| libtalloc | 2.4.3 | LGPL-3.0-or-later | Andrew Tridgell, Stefan Metzmacher and contributors | [source](https://talloc.samba.org/talloc/doc/html/index.html) [notices](third_party_licenses/runtime/libtalloc/). Includes LGPL libreplace. Rebuild/replacement tested in isolation; APK installation/relinking route not yet established. |
| libtasn1 | 4.21.0 | LGPL-2.1-or-later library; GPL-3.0-or-later tools | Free Software Foundation and contributors | [source](https://www.gnu.org/software/libtasn1/) [notices](third_party_licenses/runtime/libtasn1/). Preserve library/tool grants and corresponding source for the packaged subset. |
| libunistring | 1.4.2 | LGPL-3.0-or-later OR GPL-2.0-or-later; manual GFDL-1.2-or-later OR GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/libunistring/) [notices](third_party_licenses/runtime/libunistring/). HTML manual is distributed. Source includes its editable Texinfo form and original documentation grants. |
| ncurses | 6.6.20260307+really6.5.20250830 | MIT-style ncurses license; separate terminal data grants | Thomas E. Dickey, FSF and contributors | [source](https://invisible-island.net/ncurses/) [notices](third_party_licenses/runtime/ncurses/). Additional rxvt-unicode, kitty, alacritty and foot terminal descriptions are listed below. |
| openssl | 1:3.6.3 | Apache-2.0; associated third-party notices | The OpenSSL Project Authors and contributors | [source](https://www.openssl.org/) [notices](third_party_licenses/runtime/openssl/). Preserve LICENSE.txt and incorporated notices; this is OpenSSL 3, not the old OpenSSL license. |
| pcre2 | 10.47 | BSD-3-Clause WITH PCRE2-exception; BSD-2-Clause SLJIT | Philip Hazel, University of Cambridge, Zoltan Herczeg and contributors | [source](https://pcre2project.github.io/pcre2/) [notices](third_party_licenses/runtime/pcre2/). Preserve LICENCE.md plus deps/sljit/LICENSE for the JIT code. |
| proot | 5.1.107.89 | GPL-2.0-or-later | STMicroelectronics and contributors | [source](https://proot-me.github.io/) [notices](third_party_licenses/runtime/proot/). Executed as a separate program; linked to LGPLv3 talloc. Compatible license election, complete source, and program-boundary review remain required. |
| readline | 8.3.3 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://tiswww.case.edu/php/chet/readline/rltop.html) [notices](third_party_licenses/runtime/readline/). Provide Readline 8.3 and patches 001–003; Python also links this component. |
| sed | 4.9-2 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/sed/) [notices](third_party_licenses/runtime/sed/). Source, notices and modifications required. |
| tar | 1.35-3 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org/software/tar/) [notices](third_party_licenses/runtime/tar/). Source, notices and modifications required. |
| termux-core | 0.4.0-1 | MIT | Termux contributors | [source](https://github.com/termux/termux-core-package) [notices](third_party_licenses/runtime/termux-core/). Preserve MIT notices for runtime libraries and scripts actually packaged. |
| termux-exec | 1:2.5.0-1 | Apache-2.0; file-specific MIT notices | Termux contributors | [source](https://github.com/termux/termux-exec-package) [notices](third_party_licenses/runtime/termux-exec/). Retain exact license files and applicable changes; build-time documentation is not another APK dependency. |
| termux-keyring | 3.13 | Apache-2.0 package; public trust-key data | Termux contributors | [source](https://github.com/termux). Public verification keys are distributed trust material, not Pokecode's private signing key. |
| termux-licenses | 2.1 | License-document collection; packaging GPL-3.0-or-later | Termux contributors and license-text authors | [source](https://termux.dev). An AGPL license text in this collection does not establish an AGPL program dependency. |
| termux-tools | 1.46.0+really1.45.0-1 | GPL-3.0-or-later | Termux contributors | [source](https://termux.dev/) [notices](third_party_licenses/runtime/termux-tools/). Retain editable scripts, notices, modifications and required packaging inputs. |
| util-linux | 2.42.1-4 | GPL-2.0-only / GPL-2.0-or-later / GPL-3.0-or-later; LGPL-2.1-or-later; BSD; MIT; EUPL-1.2 | util-linux authors and contributors | [source](https://en.wikipedia.org/wiki/Util-linux) [notices](third_party_licenses/runtime/util-linux/). File-specific licenses apply. coresched is EUPL-1.2; renice preserves BSD-4-Clause-UC. Detailed executable/source mapping still requires review. |
| xxhash | 0.8.3-1 | BSD-2-Clause library; GPL-2.0-or-later xxhsum | Yann Collet and contributors | [source](https://cyan4973.github.io/xxHash/) [notices](third_party_licenses/runtime/xxhash/). xxhsum and aliases are distributed, so source obligations apply in addition to the library's BSD notice. |
| xz-utils | 5.8.3 | 0BSD tools; GPL-2.0-or-later helper scripts; conditional LGPL-2.1-or-later getopt | The XZ Utils authors and contributors | [source](https://tukaani.org/xz/). xzgrep/xzdiff/xzless/xzmore have their own GPL grant. Keep source and COPYING; check the compiled getopt configuration. |
| zlib | 1.3.2 | Zlib | Jean-loup Gailly and Mark Adler | [source](https://www.zlib.net/) [notices](third_party_licenses/runtime/zlib/). Preserve the original notice; modified versions must be identified and origin not misrepresented. |
| zstd | 1.5.7-1 | BSD-3-Clause OR GPL-2.0-only; BSD-2-Clause zstdgrep | Meta Platforms, Yann Collet, Thomas Klausner and contributors | [source](https://github.com/facebook/zstd) [notices](third_party_licenses/runtime/zstd/). Preserve the dual grant and zstdgrep's separate notice. zstdless has no separate GPL header. |
| python | 3.13.13-1+claudenote1 | PSF-2.0 with historical and bundled-component notices; linked GPL libraries | Python Software Foundation and named licensors | [source](https://python.org/) [notices](third_party_licenses/runtime/python/). Keep LICENSE and Doc/license.rst, exact Python 3.13.13 Termux revision 1 sources/patches. Readline and gdbm linking needs combined-runtime review. |
| proot-distro | 5.3.0+claudenote1 | GPLv3; metadata GPL-3.0-only vs source GPL-3.0-or-later | Termux PRoot-Distro contributors | [source](https://github.com/termux/proot-distro) [notices](third_party_licenses/runtime/proot-distro/). The upstream Python client is distributed and modified. Preserve original grants, supply modifications, and resolve metadata discrepancy. |
| gdbm | 1.26-1 | GPL-3.0-or-later | Free Software Foundation and contributors | [source](https://www.gnu.org.ua/software/gdbm/) [notices](third_party_licenses/runtime/gdbm/). Bundled with Python although absent as a separate dpkg package; source and linking review required. |
| libexpat | 2.8.1 | MIT | James Clark, Expat maintainers and contributors | [source](https://libexpat.github.io/) [notices](third_party_licenses/runtime/libexpat/). Version 2.8.1 bundled with Python; retain exact COPYING. |
| libffi | 3.5.2 | MIT | Anthony Green, Red Hat and contributors | [source](https://sourceware.org/libffi/) [notices](third_party_licenses/runtime/libffi/). Version 3.5.2 bundled with Python; retain exact LICENSE. |
| libsqlite | 3.53.2 | Public-domain dedication | SQLite authors | [source](https://sqlite.org/) [notices](third_party_licenses/runtime/libsqlite/). Version 3.53.2 bundled with Python; preserve the public-domain explanation and provenance. |

## Non-code assets and embedded resources

| Resource | Version / provenance | License and required treatment |
| --- | --- | --- |
| Pokecode icon1/icon2 and derived system/adaptive/monochrome icons | Owner confirmed original icon artwork was ChatGPT-generated on 2026-09-09; system variants derive from that artwork | Owner-provided artwork; not assigned a third-party open-source license. This records supplied provenance, not a trademark or third-party-right warranty. |
| Twelve UFO animation frames | Owner-supplied numbered sequence imported for v0.1.6.5.3, with cropping, transparency and scaling | Replaces the earlier six-frame artwork. No third-party open-source license is assigned; the older six-image ChatGPT confirmation is not treated as independent verification of this replacement sequence. |
| Compose Material icons | 1.7.8 release artifacts | Apache-2.0; original component notices retained above. |
| Mozilla/curl certificate store | 2026-07-16 | MPL-2.0; exact published PEM hash matched the bundled file. Preserve source data and notices. |
| rxvt-unicode terminal descriptions | 9.31 | GPL-3.0-or-later per original source; only compiled terminal data is bundled, not the terminal application. Source inputs staged. |
| kitty terminal descriptions | 0.48.2 | GPL-3.0-or-later; same limited data scope. |
| alacritty terminal descriptions | 0.17.0 | Apache-2.0 OR MIT; preserve original notice. |
| foot terminal descriptions | 1.27.0 | MIT; preserve copyright and permission notice. |
| Unicode data in libidn2 and Python-related components | Versions embedded in the corresponding source releases | Preserve their exact Unicode notices and Python's third-party license appendix. |
| libunistring HTML manual | 1.4.2 | GFDL-1.2-or-later OR GPL-3.0-or-later; original grants and editable Texinfo sources are available in its upstream archive. |

See the [terminal data notices](third_party_licenses/terminfo/). License texts accompanying runtime or toolchain source can describe optional, build-only or absent components; their presence is not a claim that all those components ship in Pokecode.

Ubuntu images are downloaded separately after a user requests installation; no Ubuntu root filesystem is included in the APK examined. User-installed packages and external services introduce their own terms. No external AI model weights were found among the packaged release assets.

The following acknowledgement is preserved for the Berkeley-derived runtime material:

> This product includes software developed by the University of California, Berkeley and its contributors.

## Scope of Pokecode's copyright

Copyright © 2026 Pokecode. All rights reserved for Pokecode's own material. Third-party copyrights, licenses, source access and other rights remain with their respective holders and recipients. No endorsement by an upstream project is implied.
