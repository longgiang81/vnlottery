# Logic Lottery

Flutter app (existing) and an incremental native Kotlin Android implementation.

Both native Android modules retain `minSdk 23` and enable core library desugaring for the `java.time` APIs used by license expiry, trial, and history-date handling.

Build and test it from the Android project:

```sh
cd android
./gradlew :nativeApp:testDebugUnitTest :nativeApp:assembleDebug :nativeAdmin:assembleDebug
```

The native calculator APK uses the existing user app ID (`com.longgiang81.lottery_app_flutter`) and reads Flutter's `FlutterSharedPreferences` file and `flutter.`-prefixed keys so saved tickets and settings remain available when replacing the Flutter Android build. Installing it replaces the Flutter user app on the device; Android keeps its app data when the APK is signed with the same signing key. The separate admin APK uses `com.longgiang81.lottery_app_flutter.admin`. The Flutter project remains available for its existing targets; native feature and visual parity work is ongoing.
