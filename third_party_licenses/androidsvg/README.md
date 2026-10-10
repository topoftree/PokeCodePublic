# AndroidSVG 1.4

Component: `com.caverock:androidsvg-aar:1.4`, used for plugin SVG icons.
License: **Apache-2.0**, preserved in [LICENSE](LICENSE).

- Upstream: [AndroidSVG Release_1.4](https://github.com/BigBadaboom/androidsvg/tree/9490d751d91033051efc6a4a9835ceff6082e9ff).
- Publisher [AAR](https://repo.maven.apache.org/maven2/com/caverock/androidsvg-aar/1.4/androidsvg-aar-1.4.aar), [POM](https://repo.maven.apache.org/maven2/com/caverock/androidsvg-aar/1.4/androidsvg-aar-1.4.pom) and [source archive](https://repo.maven.apache.org/maven2/com/caverock/androidsvg-aar/1.4/androidsvg-aar-1.4-sources.jar).
- AAR SHA-256: `02a5b08a2b35d2d58eb2eaca9d84ac00fb341da725fdbd653ea3ed130437e95a`.
- The release input is byte-identical to the publisher AAR. Pokecode does not patch AndroidSVG sources; normal R8 optimization applies to the APK.

Upstream license copyright: **Copyright 2013–2018 Cave Rock Software Ltd**.
Source headers credit **Paul LeBeau, Cave Rock Software Ltd.** in 2013, 2014 and 2018.
The publisher POM and tagged project license identify Apache-2.0; the inspected
source archive and tagged root contain no separate upstream `NOTICE` file.

`SVGAndroidRenderer` identifies its elliptical-arc implementation as partly
borrowed from **Apache Batik**, under Apache-2.0. Original rights remain with
the Apache Software Foundation and its contributors. That attribution is
retained here; no additional license is granted for Pokecode's own code.
