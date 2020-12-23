---
description: Try shooting your problems with these easy steps!
---

# Troubleshooting 🔫

#### **Installing/updating Google Chrome or Google/Android System WebView responds with "incompatible app"!**

If you are using Android 10+ \(Q and above\), both of these apps are not easy to install/update. Basically, Google messed things up and gave Android users more work to do.

> Chrome is no longer used as a WebView implementation in Q+. We've moved to a new model for sharing common code between Chrome and WebView \(called "Trichrome"\) which gives the same benefits of reduced download and install size while having fewer weird special cases and bugs. ~ Source: [androidpolice.com](https://www.androidpolice.com/2019/10/24/android-10-no-longer-uses-chrome-app-to-render-pages-inside-apps/)

The trichrome library is split into 4 variants, just like Google Chrome: Stable, Beat, Dev, Canary.

To install Chrome and WebView variants, follow the steps below:

1. Firstly, download the trichrome library apk variant according to the Chrome/WebView version you have/to the one you want to update to.
2. Install the apk onto your device.
3. Try updating your Chrome/WebView with Aurora Store again.

You can download the stable Trichrome library from apkmirror [here](https://www.apkmirror.com/apk/google-inc/trichrome-library/#variants).

Read more about Trichrome on the Chromium Shared Libraries [documentation](https://chromium.googlesource.com/chromium/src.git/+/master/docs/android_native_libraries.md).

#### **My exported device info won't work in spoofing!**

Most likely the platforms property in the export file is missing. This sometimes happens while exporting on some devices. The only way to fix this is to manually input a new line with the content below:

```java
Platforms = arm64-v8a, armeabi-v7a, armeabi
```

Remember to check what architecture your device supports! You can easily check it with either of these apps: [CPU-Z](https://play.google.com/store/apps/details?id=com.cpuid.cpu_z&hl=en&gl=US), [DevCheck](https://play.google.com/store/apps/details?id=flar2.devcheck&hl=en&gl=US), [Castro](https://play.google.com/store/apps/details?id=com.itemstudio.castro&hl=en&gl=US) or just search for your device on [GSMArena](https://www.gsmarena.com/). DO NOT just copy-paste the line above and blame us if it doesn't work.

#### **I have a Huawei device and I can't log in!**

Chances are that you have a device running Android that was originally shipped without Google support. To the best of our knowledge, this includes:

* Huawei Mate 30 series
* Huawei Mate 40 Series
* Huawei P40 series
* Huawei P Smart S
* Huawei Mate Xs
* Huawei Y5p, Y6p, Y7p, Y8p
* Huawei Nova 7i, 7 SE
* Huawei Matepad T8, Pro 5g

Simply spoofing to another device configuration should help solve this problem.

#### **Installation fails without warning post downloads.**

Bundled apps can't be installed on OEM ROMs due to shameless mods like \(VirusCheck, Tracker Stats, etc.\).

Workarounds:

1. Turn off vendor optimizations \(like MIUI Optimizations\) \[OR\]
2. Enable "Enforce Native Installer" from Aurora-&gt;Settings-&gt;Installations. \[OR\]
3. Use root installation method

#### **Problems with downloading apps**

This problem may be due to your download path. Sometimes Android has issues with allowing read/write permissions for apps when external storage gets involved and this can affect Aurora Store as well. To fix this, you can toggle 'Download apps in internal storage' in Settings &gt; Downloads.

#### **Updates tab doesn't show apps but searching the app shows update.**

\[Will write once info is confirmed\]

#### **Unable to export device info.**

\[Will write once info is confirmed\]

#### **Why do I have two** _**Aurora Store**_ **apps after installing the new builds?**

This might be due to the fact that you have older versions of Aurora Store installed instead of version 3, which is a completely new rewrite that comes with a new package name. You can uninstall the older one or keep it if you want.

#### **The categories tab shows "No apps blacklisted".**

This is a bug in `v.3.2.9` that has been noted. For some people it works, for some it doesn't.

#### **Not working whatsoever.**

Check if you are using the latest Stable build `v.3.2.9` or Nightly builds. For some reason some people have reported issues while installing `v.2.0.5` from third-party sources like Softonic and Uptodown.

Please download all latest AuroraOSS apps from any of the below mentioned sources only:

1. F-Droid:  [https://f-droid.org/en/packages/com.aurora.store/](https://f-droid.org/en/packages/com.aurora.store/)
2. AuroraOSS Website:  [https://auroraoss.com/downloads.php](https://auroraoss.com/downloads.php)
3. Official Telegram Channel:  [@AuroraOfficial](https://t.me/AuroraOfficial)
4. GitLab:  [https://gitlab.com/AuroraOSS/AuroraStore/-/releases](https://gitlab.com/AuroraOSS/AuroraStore/-/releases)

