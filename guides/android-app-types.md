---
description: Learn about the different types of app packaging there are for Android.
---

# Android App Types

### What is an APK?

To understand the context of the following text under this section, you require some knowledge about APKs and how they function.

APKs or .apk files are **Android App Packages**, which include the logic, images, databases, language files, sound files, etc. are required to be able to install an app on your device. It's a compression package format specially designed for Android, just like `.zip` or `.tar.gz` for universal zip compressions.

### Android Universal App (single APK)

The idea behind a Universal APK is to create a single package that caters to a broad range of Android devices including smartphones, tablets, Android TV, wearables, and other Android-powered devices. It supports various screen sizes, resolutions, and aspect ratios as well as different versions of Android, simplifying app distribution and ensuring compatibility across different platforms. This approach helps developers reach a larger user base without the need to create and manage multiple APKs targeting specific device configurations.

### Split APKs

Split APK is an emerging package format that allows apps to be modularized and distributed as separate APKs. Each split APK contains a specific feature or asset of the app. This approach is used to reduce the app's initial download size and allows users to download only the required features, reducing storage space consumption.

### Android App Bundles (AAB)

Just like APKs, AABs are a type of compression package which include the actual apk file. AAB is a publishing format introduced by Google Play to optimize the distribution of Android apps. Instead of creating a single APK, an app bundle contains modules and resources in a more efficient manner. Google Play dynamically generates APKs optimized for specific devices when users download the app.

#### Application Binary Interface (ABI)

The ABI instructs how the CPU interacts with the system at runtime, and this all depends on the CPU architecture, e.g. arm64 or x86. This

To know more on how ABIs work, read this [guide](https://developer.android.com/ndk/guides/abis).

#### Localization resources (Languages)

Localizing an application essentially means creating different string translations for each language the application should be in. When the application was shipped as a single APK using the old approach, it contained all localizations at once, even though there was hardly a need for that. App bundles optimize this process by delivering only the language resources that match the device’s system locales. However, if the user decides to change the system locale after the app is already installed, resources for missing languages will be automatically downloaded. For some applications, the localization case might go even further and include locale-specific videos or imagery. As a result, those applications will benefit even more from optimized bundle delivery.

#### Screen density resources (DPI)

An Android application should be able to run on a variety of different screen sizes and pixel densities. Android usually performs basic scaling and resizing to adapt a UI to different screens, but to ensure a better UX, additional work must be done.

This usually includes the following:

UI layouts depending on the screen configuration — for example, layouts specifically designed for watch, phone, tablet, or TV.

Bitmaps to match each screen density.

Icon drawables for each screen density if they are too complex for a mipmap drawable.

Again, the older strategy with the single APK would’ve delivered all those resources at once, even though a device would not have had much use for most of them. But app bundles ensure that only those resources that correspond to a device’s screen size and density will be delivered.

For more information about AABs, read the official guide on [Android Developers](https://developer.android.com/guide/app-bundle).

### Differences between AAB and Split APKs

|                                                                                    ABB                                                                                   |                                                                         Split APKs                                                                        |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------: |
|                                            AAB is a publishing format introduced by Google Play to optimize app distribution.                                            |                     Split APKs are a way of modularizing an app into multiple APK files, each containing a specific feature or asset.                     |
|                                         It is a single file that contains all the compiled code, resources, and assets of an app.                                        |       The app's code, resources, and assets are divided into separate APKs, and each split APK represents a different module or feature of the app.       |
| When users download an app from Google Play, the Play Store dynamically generates and delivers optimized APKs tailored to the specific device configuration of the user. |           Split APKs are primarily used to reduce the initial download size of an app and allow users to download only the required components.           |
|     By using AAB, developers can significantly reduce the app's download size on users' devices, as only the necessary resources are included in the generated APKs.     |                         Unlike AAB, which is a single file, split APKs are multiple APK files that need to be managed separately.                         |
|          Google Play's dynamic delivery feature also enables on-demand downloads for specific features or languages, further reducing the initial download size.         | Split APKs are typically used when distributing apps through alternative app stores or when creating custom distribution channels outside of Google Play. |

In summary, AAB is a publishing format that optimizes app distribution by dynamically generating optimized APKs based on device configurations, while Split APKs modularize an app into multiple APKs to reduce the initial download size and allow selective downloading of features or modules. AAB is mainly associated with Google Play, while Split APKs are more commonly used outside of the official app store ecosystem.\
\
Split APKs:

* Split APKs are a way of modularizing an app into multiple APK files, each containing a specific feature or asset.
* The app's code, resources, and assets are divided into separate APKs, and each split APK represents a different module or feature of the app.
* Split APKs are primarily used to reduce the initial download size of an app and allow users to download only the required components.
* Unlike AAB, which is a single file, split APKs are multiple APK files that need to be managed separately.
* Split APKs are typically used when distributing apps through alternative app stores or when creating custom distribution channels outside of Google Play.

In summary, AAB is a publishing format that optimizes app distribution by dynamically generating optimized APKs based on device configurations, while Split APKs modularize an app into multiple APKs to reduce the initial download size and allow selective downloading of features or modules. AAB is mainly associated with Google Play, while Split APKs are more commonly used outside the official app store ecosystem.

### Android Legacy Expansions (XAPKs)

**XAPK (Extended APK)**: XAPK is an alternative package format for Android apps. It combines the APK file and additional **OBB** (Opaque Binary Blob) files, which contain extra assets like graphics, media, or large resource files, used especially in large games. XAPKs are used to overcome the APK's file size limitation of 100MB.

We hope we did our best to break it down for you so that you have understood the fundamentals on how the Android app file packaging structure looks like and how they work.
