# android-youtube-player
YouTube Player library for Android, stable and customizable.
Forked from [here](https://github.com/PierfrancescoSoffritti/android-youtube-player) with the intention of customization and further feature enhancements for specific use cases.

For information on the technical mechanisms of the Android YouTube player, read the README in the original project linked above.

1. Building
Build locally with Android Studio or by running `./gradlew assemble` in the project root.

2. Running locally
After building, an AAR library file (basically, the Android version of a JAR) will be available in release and debug flavours at `core/build/outputs/aar`
Import this into your existing Android application by using the Android Studio wizard located at File -> New -> New Module -> Import an .AAR module. 

After it is available in your project, you need to add it as a Dependency to whichever module depends on it by editing your module's build.gradle file.
Add the line `implementation project(:core-release)` to the implementation section of that particular module's build.gradle, and you're all set. 

3. Deploying changes
This library uses novoda's (bintray-release)[https://github.com/novoda/bintray-release] plugin for publishing to bintray/JCenter.
The command `./gradlew clean build bintrayUpload -PbintrayUser=BINTRAY_USERNAME -PbintrayKey=BINTRAY_KEY -PdryRun=false` should publish it to your bintray user account, but there are more instructions available on their README if you encounter issues.
