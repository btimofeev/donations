# Android Donations Lib

Android Donations Lib supports donations by Google Play Store, Flattr, PayPal, and Bitcoin.

**NOTE: Google mailed me to remove PayPal donation capability when publishing on Google Play! Thus, you should build "product flavors" defined by the example: One version with Google Play donation capability and one with Paypal, Flattr, and Bitcoin!**

## How to use

1. Add dependency to your build.gradle: https://jitpack.io/#penn5/donations
2. Instantiate the fragment where you want to use it. Check out the example app for this: [DonationsActivity.java](https://github.com/penn5/donations/blob/master/example/src/main/java/org/penn5/donations/example/DonationsActivity.java)
3. When publishing the app you must create managed in-app products for your app in the Google Play Store that matches the ones you defined in ``private static final String[] GOOGLE_CATALOG``

## Build flavors
1. Keep in mind that Google forbits other payment methods besides Google Play. Thus, in the example, two build flavors are used. Check out [ExampleApp/build.gradle](https://github.com/penn5/donations/blob/master/example/build.gradle). The build script adds ``DONATIONS_GOOGLE`` to the auto generated BuildConfig.java. Alternatively you can check for GSF presence at runtime, but don't check the installer-referrer, as Google will reject the app
2. Add ``<uses-permission android:name="android.permission.INTERNET" />`` to product flavors that use Flattr
3. Add ``<uses-permission android:name="com.android.vending.BILLING" />`` to product flavors that use Google Play In-app billing


## Screenshots

| Product Flavor: Google | Product Flavor: Fdroid |
|------------------------|------------------------|
| ![Screenshot](https://github.com/penn5/donations/raw/master/screenshot-google.png) | ![Screenshot](https://github.com/penn5/donations/raw/master/screenshot-fdroid.png) |

## Translations

Help translating on [PoEditor](https://poeditor.com/join/project/Ol1euLyZSr).

## Build Example App with Gradle

1. Have Android SDK "tools", "platform-tools", and "build-tools" directories in your PATH (http://developer.android.com/sdk/index.html)
2. Export ANDROID_HOME pointing to your Android SDK
3. Download Android Support Repository, and Google Repository using Android SDK Manager
4. Execute ``./gradlew build``

## Contribute

Fork me!
