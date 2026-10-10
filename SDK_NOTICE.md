# Google SDK notice

Pokecode 0.1.8.1.3 uses Google ML Kit for microphone dictation and includes the following Google SDK artifacts, unchanged from the previous public release v0.1.7.9.9.2:

| Component | Version | Publisher terms |
| --- | --- | --- |
| ML Kit common | 18.11.0 | [ML Kit terms](https://developers.google.com/ml-kit/terms) |
| ML Kit GenAI common | 1.0.0-beta3 | [ML Kit terms](https://developers.google.com/ml-kit/terms), [GenAI additional terms](https://developers.google.com/ml-kit/genai-terms) |
| ML Kit GenAI speech recognition | 1.0.0-alpha1 | [ML Kit terms](https://developers.google.com/ml-kit/terms), [GenAI additional terms](https://developers.google.com/ml-kit/genai-terms) |
| Google Play services base | 18.5.0 | [Android SDK terms](https://developer.android.com/studio/terms) referenced by the artifact metadata |
| Google Play services basement | 18.9.0 | [Android SDK terms](https://developer.android.com/studio/terms) referenced by the artifact metadata |
| Google Play services tasks | 18.2.0 | [Android SDK terms](https://developer.android.com/studio/terms) referenced by the artifact metadata |

Copyright Google LLC and applicable licensors. These SDKs are not licensed under Pokecode's third-party open-source license texts merely because they appear in the same dependency graph.

Google states that ML Kit input processing takes place on the device and that ML Kit does not send those inputs or results to Google. The APIs can contact Google for updates and send API performance and usage metrics. This statement is specific to ML Kit, not to Chat providers, command-line tools, or all network activity in Pokecode. See [Google's ML Kit privacy description](https://developers.google.com/ml-kit/terms) and [Google's Privacy Policy](https://policies.google.com/privacy).

Version 0.1.8.1.3 removes the DataTransport backend-discovery, job and alarm components from the merged manifest and cancels surviving telemetry jobs to prevent those components from starting the app in the background. The ML Kit recognition component registry remains present. This change does not remove the SDK's terms or establish that all SDK network activity is disabled. Chat Voice Mode uses the signed-in Codex audio service separately from this dictation SDK.

The publisher must provide an accurate application privacy policy and appropriate user disclosures before distribution. The GenAI terms also require review of age/audience limitations, permitted uses, and the production eligibility of the selected API version. An `alpha` or `beta` artifact name alone is not a definitive interpretation of Google's contractual preview restrictions.

This file records the release's SDKs and outstanding review. Publication does not assert that all publisher obligations have been fulfilled.
