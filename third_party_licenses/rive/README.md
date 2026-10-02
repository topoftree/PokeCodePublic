# Rive Terminal scene integration

Bundled with Pokecode **0.1.7.7.3.3**; reviewed **2026-10-02**.

The desk and space-cabin scenes use approved generated artwork based on owner
references and independently authored animation vectors. They embed no external
font, audio or asset pack. These notices cover the rendering libraries.

The pinned Maven artifact is `app.rive:rive-android:11.12.1` (MIT), from
https://github.com/rive-app/rive-android/tree/11.12.1 . Its AAR SHA-256 matches
the publisher's Gradle metadata:
`8d3089aac99de679be0f766f525e939356a5d72c2308eca68b6db47eac73d7d3`.

The Android release references Rive Runtime commit
`7db8b61f747b24553bc4783df50cff997610e17c`. Its native build includes the
following components; adjacent files retain their license texts. `SOURCES.txt`
records the exact upstream license locations.

| Component | Version / source reference | License text |
| --- | --- | --- |
| Rive Android | 11.12.1 | RIVE-ANDROID-LICENSE.txt (MIT) |
| Rive Runtime and Renderer | commit above | RIVE-RUNTIME-LICENSE.txt (MIT) |
| HarfBuzz | rive_13.1.1 | HARFBUZZ-COPYING.txt (Old MIT) |
| SheenBidi | 2.6 | SHEENBIDI-LICENSE.txt (Apache-2.0) |
| Yoga | rive_changes_v2_0_1_3_grid | YOGA-LICENSE.txt (MIT) |
| miniaudio | rive_changes_5 | MINIAUDIO-LICENSE.txt (MIT option) |
| Luau | rive_0_734 | LUAU-LICENSE.txt (MIT) |
| libhydrogen | rive_0_2 | LIBHYDROGEN-LICENSE.txt (ISC) |
| Vulkan Memory Allocator | 3.3.0 | VMA-LICENSE.txt (MIT) |
| Vulkan Headers | vulkan-sdk-1.4.321 | VULKAN-LICENSE.md, VULKAN-APACHE-2.0.txt, VULKAN-MIT.txt |
| GLAD generated GLES/EGL loader | 2.0.8 | GLAD-LICENSE.txt (CC0 / Apache-2.0 for generated files) |
| Khronos platform declarations | included by Rive Renderer | KHRONOS-PLATFORM-LICENSE.txt (MIT-style) |
| libc++ shared runtime | Android NDK 27.2.12479018 | LLVM-LICENSE.txt (Apache-2.0 with LLVM exceptions) |

New Java dependencies are Volley 1.2.1 (Copyright Google, Inc.) and ReLinker
1.4.5 (Copyright Keepsafe Software Inc.), both Apache-2.0; their complete texts
are `VOLLEY-LICENSE.txt` and `RELINKER-LICENSE.txt`. AndroidX CustomView resolves
to 1.1.0 and Startup Runtime to 1.2.0, both Apache-2.0, Copyright The Android
Open Source Project; the shared Apache-2.0 text is also packaged at
`third_party_licenses/Apache-2.0.txt`. Existing Compose/Lifecycle versions remain
selected by PokeCode's pinned dependency graph.

The stock AAR contains optional audio/scripting support even though this scene
uses neither. Android's existing ARM64 filter excludes other architectures.
Both new ARM64 shared libraries have 16 KiB ELF LOAD segment alignment. No new
GPL, LGPL or AGPL component was found in this integration. This review does not
resolve the existing obligations in [THIRD_PARTY_NOTICES.md](../../THIRD_PARTY_NOTICES.md).
