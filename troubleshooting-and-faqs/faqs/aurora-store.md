# Aurora Store

### General

**Why the name "Aurora" Store?**

Initially, Aurora Store was named Galaxy Store. Some people thought we were trying to clickbait by using Samsung's "Galaxy" likeness (False, btw). Because of this we have decided to drop the Galaxy name in place of Aurora.

**What is the difference between Aurora Store and Google's Play store?**

Unlike Google's Play Store, Aurora Store doesn't track your downloads or the apps you use. We respect your privacy. Aurora Store is also unaffected by Google marking your device as _uncertified_ or lacking of necessary Google apps. Play Protect is not present, as this is a Play Store only feature.

**Is Aurora Store a fork of YalpStore?**

Technically, no. Aurora Store v3 is written from scratch, and Aurora Store v4 is a rewrite of v3 in Kotlin, but it does share some code from YalpStore.

**Do I need Google Play Services to use Aurora Store?**

No. Aurora Store was built to access the Google Play store without any kind of Google services. It doesn't matter if you use it with or without Google Play Services/MicroG.

**What is the FakeStore?**

Some poorly-designed apps detect if Google Play is missing and punish the user by misbehaving. The FakeStore is a stub that disguises itself as the Play store: FakeStore shares the same package name as the Play store `com.android.vending`. This prevents some apps from crashing.

**Is it safe to use Aurora store?**

Aurora Store is fully open-source and verified by F-Droid. If you're asking about the safety of the apps in the store, those are the exact same ones the Play Store would load and display. A lot of dangerous stuff seems to sneak past Google though, so as a rule of thumb, don't download anything which you're unsure about.

**Why are some features from v3 not present in v4?**

Similar to Aurora Store v3, version 4 of Aurora Store is rewritten from scratch, but now in Kotlin language. This means that each and every feature and UI elements needs to be implemented accordingly. With new features, bugs come popping up every now and then, bit & pieces to improve while keeping it as stable as possible. As you can see, this takes time and effort so please have some patience!

{% hint style="info" %}
**Tip:** You can check out the [Roadmap ](../../our-apps/aurora-store/roadmap/)page to know more about what has changed, removed and added to the newest version of Aurora Store!
{% endhint %}

**Why do I need to accept the Terms Of Service for Aurora Store?**

We deem this necessary, because it is to ensure a minimum safety for AuroraOSS, in case some individual or group wants to harm us in any way by using Aurora Store as leverage. It's also a way to ask users to be aware what they're signing up for, so we urge and encourage you to read it to inform yourselves of what Aurora Store is capable of doing and . If you find anything useful for or strange in our [Terms Of Service](../../our-apps/aurora-store/terms-of-service.md), don't hesitate to contact us on [auroraoss.dev@gmail.com](mailto:auroraoss.dev@gmail.com) or our [Telegram Group](https://t.me/AuroraSupport).

**What data does Aurora Store send to Google?**

Aurora Store does its best to send the least amount of information possible.

To provide basic functionalities, the following is sent:

* a list of package names of your installed apps (for fetching updates). You can select apps to be blacklisted in order to avoid sending package info to Google.
* your search queries and your downloads for obvious reasons.
* your IP address for network requests (this is a requirement for any app that requires internet access!)

For anonymous logins, following data is sent to Aurora Dispenser Server:

* a GET request to obtain an authentication token. This token is generated server side so no user data is leaked. Requests upon creating sessions are made and sent to Google from the dispenser server's IP.
* AuroraOSS follows a strict policy of no-logging, so no sensitive data except IP addresses (only if the rate-limiter on our server deems the IP as rate-limit-worthy or ban-worthy, as well as requests with mailicous intent) are stored on the dispenser server for security purposes.

{% hint style="info" %}
**Tip:** For more info on anonymous logins read​ [Anonymous Logins](../../references/anonymous-logins.md) and [Policy](../../our-apps/aurora-store/privacy-policy.md) to know more on what we require from you for Aurora Store to work.
{% endhint %}

#### **What are nightly autobuilds?**

> A \[...] nightly build is the practice of completing a software build of the latest version of a program, on a daily basis. This is so it can first be compiled to ensure that all required dependencies are present \[...]. The daily build is also often publicly available allowing access to the latest features for feedback.
>
> \~ Source: [Wikipedia](https://en.wikipedia.org/wiki/Daily\_build)

There are two versions of Aurora Store that we make available to all users.

* **Stable**: Stable versions with everything functioning, with minor to no bugs.
* **Nightly**: Daily versions built by a script to include the latest dependencies and commits on the Aurora Store repo. Can contain a few bugs and features the Stable version doesn't have.

You can download the latest nightlies via the [website](https://files.auroraoss.com/?folder=AuroraStore/Nightly).

**Why are the versions on F-Droid and the XDA Thread outdated? When will they be updated?**

Aurora Store is in a constant development phase; Only infrequent, stable builds will be uploaded to those platforms. F-Droid's review & build process is also quite lengthy. You can always grab the latest builds either from the [Telegram Group](https://t.me/AuroraSupport) or from [AuroraOSS](https://files.auroraoss.com/?folder=AuroraStore).

**"Please add support for F-Droid/Amazon/Yada repositories!"**

No, this is a Play Store client only. Different clients for different services (^\_\~)

**Why do some apps show updates in Aurora Store (Anonymous mode) but not in the Play Store (or vice-versa)?**

Aurora Store's anonymous mode works by connecting to a random dummy account stored in the token dispenser server. These dummy accounts are created by volunteers from different countries and some by the developer himself. Thus, every account has different locale settings by default according to the location where it was first created.

So next comes the Google Play Update roll-out mechanism. Google doesn't push app updates in one single attempt to all countries users. It's similar to staged updates & needs a lot of server syncing which takes time. Some apps are also blacklisted or restricted in specific countries and for specific devices (geolocked & device-restricted).

So while using Anonymous mode user are randomly connected to an Dummy account with different account locales which alas alters the list of app updates accordingly. Additionally spoof settings can also be able to alter the apps updates list.

**How can I report a bug or suggest something?**

You can open issues on GitLab [here](https://gitlab.com/AuroraOSS/AuroraStore/issues), or you can do so by joining our [Telegram Support Group](https://t.me/AuroraSupport). Use `/bug` or `/suggestion` at the start of your message. If urgent, you can tag [@whyorean](https://t.me/whyorean).

### Accounts

**Do I need to use my own Google account to log in?**

Nope. Aurora Store can log you in with a dummy (anonymous) account that is stored in the token dispenser so that nothing gets linked to your own account.

However, it is recommended to use **your own Google account**, or at the very least a throwaway one which you will not have to worry about if it gets banned. This ensures better stability and gives you the full potential with the features available in Aurora Store.

**What is the token dispenser?**

The token dispenser is a server which provides login credentials to Aurora Store for Anonymous Logins. You can check the current status of the token dispenser servers [here](https://github.com/aurora-website/website\_v1/blob/source/guides/server-status) or by using `/status` in the Telegram group.

If you would like to create and host your own token dispenser server, check out the source code [here](https://github.com/whyorean/AuroraDispenser).

**Why would I use my own account? Is it safe?**

The main reason would be having the possibility to download apps purchased by yourself or to access your wishlist. Other reasons for using your own account could be having beta updates available, as this isn't possible for dummy accounts, or to reduce the possibility of having issues with Aurora Store when using dummy accounts.

However, you may want to be careful as **Google retains full rights to block any account under their** [**Google Play Terms of Service §4**](https://play.google.com/intl/en-us\_us/about/play-terms/index.html), because using Aurora Store clearly violates their terms of services. Being banned means that the very Google account you used to sign in with will be blocked forever. It might be worth using a dummy account for that reason.

If you do happen to get your Google account banned, you can try appealing, which may or may not work. If they reject your appeal then there's nothing much you can do about that account. You can try your luck by filling out their form [here](https://support.google.com/accounts/contact/disabled2).

**How do I purchase paid apps without using the Play Store app?**

Purchase the apps from the [Google Play website](https://play.google.com/store), then log in using your own account in Aurora Store to download and install them.

**Can Aurora store verify licenses?**

That, unfortunately, is something tied to Play Store and probably always will be. If you don't want to install the Play Store (it could work with microG), all you can do is pester the Devs to remove the verification or at least offer alternative means of verification. In-App Purchases (IAPs) are similarly tied to Play Store and you will not be able to make or restore IAPs without having it installed.

**Can I use Aurora Store to get paid apps for free?**

Not unless they are on discount or made free.

### Filters

**What is the F-Droid filter?**

Since F-Droid signs APKs with its own keys, the Play store variants of apps cannot be installed over them. The F-Droid filter excludes all the apps it finds with F-Droid signatures on your device to prevent such conflicts.

**What is the Google filter?**

By enabling this filter, you can remove all Google Apps from your search query results and from categories. This is pretty useful for those ungoogled people out there.

### Downloads & Installation

**Where can I find downloaded .apk files from Aurora Store?**

By default, Aurora Store utilizes the root storage space created for Aurora Store.

Default path: `/data/data/com.aurora.store/files/Download`

If you prefer to download the apk files to internal storage instead, you can choose to do so by enabling the User external storage toggle under **Settings** → **Downloads**.

The path will then be **Internal Storage** → **Aurora** → **Store** → **Downloads** → **packageName** → **versionNumber** → **apkFile**.

**How does Aurora Store install apps?**

Aurora Store can install apps in 4 ways:

* **Session** (Recommended) - Works in a similar way to [SAI](https://github.com/Aefyr/SAI). There are 2 ways session installer can be used. If you have Aurora Store installed as a system application, this will have the same effect as if you were to install Aurora Services as a system application. However, you will need an unlocked bootloader with a custom recovery similar to TWRP installed.
* **Native** - Whenever an app is downloaded, it will open the native android installer screen. This doesn't require root or system permissions, but does _not_ support split apk installations.
* **Root** - By giving Aurora Store root or system permissions, it will automatically install apps in the background as soon as they are downloaded.
* **Aurora Services** - By installing Aurora Services as a system app, Aurora Store can automatically install apps in background after the download complet

### Aurora Services

**How do I use Aurora Services?**

1. Install Aurora Services as a system app.
2. Open Aurora Services and follow the initial set-up instructions.
3. Open Aurora Services settings and choose Aurora Services it as an installation method.

You don't need to give Aurora Store system or root permissions; Aurora Services handles all install and uninstall requests in the background, which is why it has to be installed as a system app. Get Aurora Services on [GitLab](https://gitlab.com/AuroraOSS/AuroraServices/-/releases).

**How to give Aurora Services system permissions?**

Aurora Services will _not_ work if it is not installed as a system app. You _must_ have an unlocked bootloader for the following to work.

1. If you have Magisk installed then simply download the zip file from [GitLab](https://gitlab.com/AuroraOSS/AuroraServices/-/releases) and flash via Magisk. If Magisk is present then you can:
   * either flash the 'magisk-unity' zip file via TWRP
   * or unzip the zip file and manually push `AuroraServices.apk` to `/system/priv-app` and `permissions_com.aurora.services.xml` to `/system/etc/permissions/` (check How-To below)
2. Grant the required permissions.
3. Set installation method in the Aurora Store settings to Aurora Services (**Settings** → **Installations** → **Installation method** → **Aurora Services**).

{% hint style="danger" %}
Be careful! Make sure to follow every step through if you want to manually push files to system. You may end up breaking things if you aren't careful. Linux knowledge would come in handy.
{% endhint %}

{% hint style="warning" %}
**Note:** Aurora Services is **deprecated** since the release of Aurora Store 4.&#x20;
{% endhint %}

{% hint style="info" %}
#### How to push files to /system with TWRP



1. Go to **Mount** and tick 'System'.
2. Go back and go to **Advanced** → **Terminal**.
3. Find the directory where AuroraServices.apk and privapp-permissions-auroraservices.xml are located (most likely **Internal Storage** → **Download**).
4. Copy both the files and paste it in your device's system partition like this:

{% code lineNumbers="true" fullWidth="false" %}
```bash
install -D filename -m644 /path/to/target/directory/filename
# Copy AuroraServices.apk to /system/priv-app/AuroraServices/:
install -D /sdcard/Download/AuroraServices/AuroraServices.apk -m644 /system/priv-app/AuroraServices/AuroraServices.apk
# Copy privapp-permissions-auroraservices.xml to /system/etc/permissions/:
install -D /sdcard/Download/privapp-permissions-auroraservices.xml -m644 /system/etc/permissions/privapp-permissions-auroraservices.xml
```
{% endcode %}
{% endhint %}

**Can Aurora Download and install Split or Bundled APKs?**

Yes, it can install both with or without root.

### Spoofing

#### **Device**

To spoof your device config, go to the **Spoofing** menu located at the sidebar and select your desired device config. Make sure to select one with the same architecture (e.g. arm64-v8a, armeabi-v7a, armeabi) and better yet, same Target Android Runtime APIs (API30: Android 11, API29: Android 10, API28: Android 9, etc.), otherwise you will experience problems with installing.

#### **Language**

Language spoofing allow you to change the content language displayed on Aurora Store. This does not mean the app language, rather the actual content like app titles, description, reviews & more. However, some strings are tied to your Google account if you are using your own account to log in, e.g. the Editor Choice section will be displayed in the language your account is set to (i.e. if your account country is set to Germany, the language displayed will be German).

#### **Location**

This is how Google determines the location of your account:

> An IP address (also called Internet address) is assigned to your device by your Internet Service Provider, and is a requirement to use the Internet. IP addresses are used to make the connection between your device and the websites and services that you use. IP addresses are roughly based on geography. This means that any website that you use, including google.com, may get some information about your general area.
>
> \~ Source: [Google Policies](https://policies.google.com/technologies/location-data?hl=en-GB)

By default, all anonymous sessions are generated via our server, so only our server's IP and the account locale will be shown to Google. If you would like to use your own IP, you can do so by enabling the 'Insecure anoynmous session' mode in Aurora Store **Settings** → **Networking**.

If you would like to spoof to another country other than your own IP, using a VPN is sufficient. Simply use a VPN client of your choice to connect to IP then open Aurora Store and login (if Aurora Store was not started anew, please restart it after connecting to the VPN server).
