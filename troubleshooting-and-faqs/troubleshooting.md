---
description: Try shooting your problems with these easy steps!
---

# Troubleshooting

## Aurora Store

### Miscellaneous

#### **Installing/updating Google Chrome or Google/Android System WebView responds with "Incompatible app"!**

If you are using Android 10+ (Q and above), neither of these apps are easy to install/update. Basically, Google messed things up and gave Android users more work to do.

> Chrome is no longer used as a WebView implementation in Q+. We've moved to a new model for sharing common code between Chrome and WebView (called "Trichrome") which gives the same benefits of reduced download and install size while having fewer special cases and bugs.
>
> \~ Source: [androidpolice.com](https://www.androidpolice.com/2019/10/24/android-10-no-longer-uses-chrome-app-to-render-pages-inside-apps/)

The trichrome library is split into 4 variants, just like Google Chrome: Stable, Beta, Dev, Canary.

To install Chrome and WebView variants, follow the steps below:

1. Firstly, download the trichrome library apk variant that you plan to install.
2. Install the apk onto your device.
3. Try updating your Chrome/WebView with Aurora Store again.

You can download the stable Trichrome library from [apkmirror](https://www.apkmirror.com/apk/google-inc/trichrome-library/#variants).

Read more about Trichrome on the Chromium Shared Libraries [documentation](https://chromium.googlesource.com/chromium/src.git/+/master/docs/android\_native\_libraries.md).

#### **Why do I have two Aurora Store apps after installing the new builds?**

This might be due to the fact that you have sub-versions of Aurora Store (Alpha, Beta & Nightly) installed instead of Aurora Store version 4 **Stable**, which all come with corresponding package names. You can uninstall those or keep them if you want.

### Login Problems

*   **"BadRequest"** → I have a Huawei device and I can't log in!

    Chances are that you have a device running Android that was originally shipped without Google support. To the best of our knowledge, this includes:

    * Huawei Mate 30 series
    * Huawei Mate 40 Series
    * Huawei P40 series
    * Huawei P Smart S
    * Huawei Mate Xs
    * Huawei Y5p, Y6p, Y7p, Y8p
    * Huawei Nova 7i, 7 SE
    * Huawei Matepad T8, Pro 5g

    Simply spoofing to another device configuration with the same architecture (e.g. arm64-v8a, armeabi-v7a, armeabi) and better yet, same Target Android Runtime APIs (API30: Android 11, API29: Android 10, API28: Android 9, etc.) should help solve this problem.
*   **"Timeout"** → I can't login because of internet connection.

    When network connection is either blocked or network speed is too slow (Aurora Store only waits for 20 sec for an authentication request). If there is no response from Google's servers, then there will be multiple timeouts.
*   **"Oops! You have been rate-limited!"** → I clicked on Anonymous button too many times!

    You are rate-limited after trying to sign in anonymously after 20 concurrent retries within an hour. Rate-limiting lasts for an hour. Going over the 20 request per hour limit means an additional hour will be added for every additional 20 requests (20r/h: 1h, 40r/h: 2h, 60r/h: 3h, etc.). If you are rate-limited, wait for an hour before logging in again.

    Our current rate looks like this:in

| Requests/time (r/t) | Rate-limited | Banned |
| :-----------------: | :----------: | :----: |
|      > 20 r/min     |      yes     |   no   |
|      > 50 r/min     |      no      |   yes  |

### Installation Problems

Bundled apps (split APKs) can't be installed on OEM ROMs, i.e. MIUI, Oppo, due to shameless mods like VirusCheck, Tracker Stats, etc.

Pick **one** of these workarounds:

1. Turn off vendor optimizations (like MIUI Optimizations, _not_ battery optimizations).
2. Use the Aurora Services installation method.
3. Use the root installation method.
4. Install the original Android Package installer and try again.

For the fourth workaround, you might need to install it as a system app for it to be able to use session installer, and removing MIUI's package installer might help further. The problem with MIUI is that it only allows installations through Google Play Store and Xioami GetApps. You can get the Android Package installer from [apkmirror](https://www.apkmirror.com/apk/google-inc/package-installer/).

{% hint style="warning" %}
You may not be able to disable MIUI Optimizations through developer options anymore after MIUI 12 on EU versions because MIUI is just being MIUI.
{% endhint %}

### **"Getting Metadata - Downloads failed, could not fetch files"**

*   **Check that you have a strong Wi-Fi or mobile data connection**

    First, make sure you have a strong internet connection. It’s best if you can connect to a Wi-Fi network. If you don’t have access to Wi-Fi, make sure you have a strong mobile data connection. Then try your download again.

    Get more help with connection problems on Android devices.
*   **Clear the cache & data of the Aurora Store**

    This gives the app a fresh start and can help fix issues.

    1. Open your device's Settings app.
    2. Tap **Apps & notifications** → **See all apps**.
    3. Scroll down and tap Aurora Store.
    4. Tap **Storage** → **Clear Cache**.
    5. Next, tap **Clear data**.
    6. Re-open the Aurora Store & try your download again.
*   **Restart your device**

    If you still can’t download after you clear the cache & data of Aurora Store, restart your device.

    1. Press and hold the **Power** button until the menu pops up.
    2. Tap **Power off** or **Restart** if that is an option.
    3. If needed, press and hold the **Power** button until your device turns on again.

#### **"Download Failed - Session expired"**

This means that the session has expired, and you need to relogin again. Best wait a few minutes before signing in so that the session gets refreshed.

#### **"Installation failed"**

If your installation method is set to **Root** and your **Android version** is **11 (R)**, then you may experience problems with installing apps. A quick 'fix' that works occasionally is to force clear all downloads in the downloads page within Aurora Store and try installing it again. Hope you win the gamble!

#### **"INSTALL\_FAILED\_NO\_MATCHING\_ABIS: Failed to extract native libraries, res=-113"**

Most likely you chose a device config unsuited for your device CPU architecture (e.g. arm64-v8a, armeabi-v7a, armeabi). The device config should contain the same arch as the one your device arch has, otherwise you will get this error upon installation process. To fix this, spoof your device to the correct device config, logout & login, restart Aurora Store and try installing the app again.

### Can't find apps!

There are a few scenarios where you might not find the app you want in Aurora Store. These can include being invited to a beta app through an app developer, an app being geographically restricted, or an app being device/OS specific.

### **Invited to beta app**

Some beta apps can be accessed by using the Beta sign-up button on apps that have beta programmes. Beta apps that require a special invite through a developer will obviously require your own account with the email address the developer invited you with. However, this is not possible yet.

### **Geo-locked app**

There is a high possibility that the app you are looking for is geo-locked, meaning it is not accessible either in your country or because the anonymous account you are using has its locale setting to any country other than yours. Read the **Spoofing** > **Location** section under the Aurora Store FAQ page.

{% content-ref url="faqs/aurora-store.md" %}
[aurora-store.md](faqs/aurora-store.md)
{% endcontent-ref %}

### **Device-specific app**

The app you are searching for could be hardware specific or OS specific. For example, Google Camera is only available for Pixel devices and OnePlus Launcher for OnePlus devices can only run with native libs or flags. You can't install these on other devices even with Google Play Store, so forget using Aurora Store.

### Not Working Whatsoever

Check if you are using the latest Stable build or Nightly builds. Some users have reported issues while installing older versions of Aurora Store from third-party sources like Softonic and Uptodown.

Please download all latest AuroraOSS apps from any of the below-mentioned sources only:

1. F-Droid: [https://f-droid.org/en/packages/com.aurora.store/](https://f-droid.org/en/packages/com.aurora.store/)
2. AuroraOSS Website: [https://files.auroraoss.com/](https://files.auroraoss.com/)
3. Official Telegram Channel: [@AuroraOfficial](https://t.me/AuroraOfficial)
4. GitLab: [https://gitlab.com/AuroraOSS/AuroraStore/-/releases](https://gitlab.com/AuroraOSS/AuroraStore/-/releases)

If you still can't figure out why, consult us on our Telegram Group chat or open an issue on GitLab if you must.

