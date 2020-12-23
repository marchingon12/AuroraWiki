---
description: 'Frequently Asked Questions: Get reading!'
---

# FAQs 💬

#### **Why the name "Aurora" Store?**

Initially, Aurora Store was named Galaxy Store. Some people thought we were trying to clickbait by using Samsung's "Galaxy" likeness \(False, btw\). Because of this we have decided to drop the Galaxy name in place of Aurora.

#### **What is the difference between Aurora Store and Google's Play store?**

Unlike Google's Play Store, _Aurora Store_ doesn't track your downloads or the apps you use. We respect your privacy. Aurora is also unaffected by Google marking your device as _uncertified_ or lacking of necessary Google apps. Play Protect is not present, as this is a Play Store feature.

#### **Is** _**Aurora Store**_ **a fork of YalpStore?**

Technically, no. _Aurora Store_ v3 is written from scratch, but it does share some code from YalpStore.

#### **Do I need Google Play Services to use** _**Aurora Store**_**?**

No. _Aurora Store_ was built to access the Google Play store without any kind of Google services. It doesn't matter if you use it with or without Google Play Services/MicroG.

#### **What is the FakeStore?**

Some poorly-designed apps detect if Google Play is missing and punish the user by misbehaving. The FakeStore is a stub that disguises itself as the Play store: FakeStore shares the same package name as the Play store **\(**com.android.vending\). This prevents some apps from crashing.

#### **Is it safe to use Aurora store?**

Aurora is fully open-source and verified by F-Droid. If you're asking about the safety of the apps in the store, those are parsed from the same place the Play Store would parse from. A lot of dangerous stuff seems to sneak past Google though, so as a rule of thumb, don't download anything which you're unsure about.

#### **What data does** _**Aurora Store**_ **send to Google?**

_Aurora Store_ does its best to send the least amount of information possible.

To provide basic functionalities, the following is sent:

* a list of package names of your installed apps \(for fetching updates\). You can select apps to be blacklisted in order to avoid sending package info to Google.
* your search queries and your downloads for obvious reasons.

For anonymous logins, following data is sent to Aurora Dispenser Server:

* a GET request to obtain a authentication token. This token is generated server side so no user data is leaked. All the requests are made to Google from the Dispenser Server's IP.
* Aurora OSS follows a strict policy of no-logging, so no data is stored on the Dispenser Server.

{% hint style="info" %}
\*\*\*\*👀 **Tip:** For more info read​ Anonymous Logins.
{% endhint %}

{% page-ref page="../references/anonymous-logins.md" %}

#### **Do I need to use my own Google account to log in?**

Nope. _Aurora Store_ can log you in with a dummy account that is stored in the token dispenser so that nothing gets linked to your own account.

#### **What is the token dispenser?**

The token dispenser is a server which provides login credentials to Aurora Store for Anonymous Logins. You can check the current status of the token dispenser servers [here](https://gitlab.com/AuroraOSS/AuroraStore/-/wikis/Server-status) or by using `/status` in the Telegram group.

If due to some reasons primary token dispenser gone DOWN/OFFLINE & you are unable to login, then please enable the secondary token dispenser URL for the time being.

Steps:

1. Go to Settings -&gt; Networks -&gt; Enable custom tokenizer​
2. Enter the following Tokenizer URL:​ http://www.auroraoss.in:8080
3. Now try logging back in as Anonymous 

If you would like to create and host your own token dispenser server, check out the source code [here](https://github.com/whyorean/AuroraDispenser).

#### **Why would I use my own account? Is it safe?**

The main reason would be having the possibility to download apps purchased by yourself or to access your wishlist. Other reasons for using your own account could be having beta updates available, as this isn't possible for dummy accounts, or to reduce the possibility of having issues with Aurora Store when using dummy accounts.

However, you may want to be careful as **Google retains full rights to block any account under their** [**Google Play Terms of Service §4**](https://play.google.com/intl/en-us_us/about/play-terms/index.html), because using Aurora Store clearly violates their terms of services. Being banned means that the very Google account you used to sign in with will be blocked forever. It might be worth using a dummy account for that reason.

If you do happen to get your Google account banned, you can try appealing, which may or may not work. If they reject your appeal then there's nothing much you can do about that account. You can try your luck by filling out their form [here](https://support.google.com/accounts/contact/disabled2).

#### **How do I purchase paid apps without using the Play Store app?**

Purchase the apps from the [Google Play website](https://play.google.com/store), then log in using your own account in _Aurora Store_ to download them.

#### **Can Aurora store verify licenses?**

That, unfortunately, is something tied to Play Store and probably always will be. If you don't want to install the Play Store \(it can work with microG\), all you can do is pester the Devs to remove the verification or at least offer alternative means of verification. In-app purchases \(IAPs\) are similarly tied to Play Store and you will not be able to make or restore IAPs without having it installed.

#### **Can I use Aurora store to get paid apps for free?**

No.

#### **What is the F-Droid filter?**

Since F-Droid signs APKs with its own keys, the Play store variants of apps cannot be installed over them. The F-Droid filter excludes all the apps it finds with FDroid signatures on your device to prevent such conflicts.

#### **What is the spoofing feature?**

Spoofing allows you to pretend to be any other device at any other location in the world in order to download geo-restricted apps. You can use your own custom device configs by dropping the .properties file in the Downloads directory \(Settings -&gt; Downloads -&gt; Download Path\).

#### **How does** _**Aurora Store**_ **install apps?**

_Aurora Store_ can install apps in 3 ways:

* Manual - Whenever an app is downloaded, it will open the manual installation screen. This doesn't require root or system perms.
* Root/System - By giving Aurora Store root or system permissions, it will automatically install apps in the background as soon as they are downloaded.
* _Aurora Services_ - By installing _Aurora Services_ as a system app, _Aurora Store_ can automatically install apps upon download completion in the background.

#### **How do I use** _**Aurora Services**_**?**

1. Install _Aurora Services_ \(preferably to the system\).
2. Open _Aurora Services_ and follow the initial set-up instructions
3. Open _Aurora Services_' settings and choose Aurora Services it as an install method.

You don't need to give _Aurora Store_ system or root permissions; _Aurora Services_ handles all install and uninstall requests in the background, which is why it has to be installed as a system app. Get Aurora Services from [here](https://gitlab.com/AuroraOSS/AuroraServices/-/releases)

#### **How to give** _**Aurora Services**_ **system permissions?**

_Aurora Services_ will NOT work if it is not installed as a system app.

1. If you have Magisk installed then simply download the zip file from [GitLab](https://gitlab.com/AuroraOSS/AuroraServices/-/releases) and flash via Magisk. If magisk is not installed then you can either install the 'magisk-unity' zip file via TWRP \(root access is not needed\) or manually push `AuroraServices.apk` to `/system/priv-app` and `permissions_com.aurora.services.xml` to `/system/etc/permissions/` \(This needs root access!\).
2. Grant the required permissions & whitelist Aurora Store in the services app.
3. Set installation method in the Aurora Store settings to Aurora Services \(Settings &gt; Installations &gt; Installation method &gt; Aurora Services\).

#### **Can Aurora Download and install Split or Bundled APKs?**

Yes, it can install both with or without root.

#### **How can I submit/improve translations?**

Go to [POEditor](https://poeditor.com/join/project/54swaCpFXJ) and inform the developer when done.

{% hint style="info" %}
\*\*\*\*❗ **Note**: The developer typically keeps track of translations progress, but it's possible that I missed a contribution. If you don't receive a reply, please remind him!\)​
{% endhint %}

#### **Why are the versions on F-Droid and XDA labs outdated? When will they be updated?**

Aurora Store is still in a development phase right now; Only infrequent, stable builds will be uploaded there. F-Droid's review & build process is also quite lengthy. You can always grab the latest tests builds either from the [Telegram Group](https://t.me/AuroraSupport) or from [AuroraOSS](https://auroraoss.com/AuroraStore/Nightly/).

#### **"Please add support for F-Droid/Amazon/Yada repositories!"**

No, this is a Play Store client only. Different clients for different services \(^\_~\)

#### **Does Aurora supports downgrading app versions?**

Yes, it supports app version downgrading to some extent. To download older versions, open the page of the desired app, from the three-dot-menu on the top right side, tap on `Manual download`. On the next screen put a valid last octet value of version you want & hit download.

> Example: if the current installed app version is `v.3.1.550` & you want `v.3.1.445`, then on version page just put `445` i.e last octet value of version.

Keep in mind that downloading arbitrary versions of apps is not supported by the Google Play Store. Your success depends on a lucky guess of the version code. Even if you guess right and you get the download to start, you still might get an incompatible APK.

#### **Why do some apps show updates in Aurora Store \(Anonymous mode\) but not in the Play Store \(or vice-versa\)?**

Aurora Store's anonymous mode works by connecting to an random dummy account stored in the token dispenser server. These dummy accounts are created by volunteers from different countries and some by the developer himself. Thus, every account has different locale settings by default according to the location where it was first created.

So next comes the Google Play Update roll-out mechanism. Google doesn't push app updates in one single attempt to all countries users. It's similar to staged updates & needs a lot of server syncing which takes time. Some apps are also blacklisted or restricted in specific countries and for specific devices \(geolocked & device-restricted\).

So while using Anonymous mode user are randomly connected to an Dummy account with different account locales which atlast alters the list of app updates accordingly. Additionally spoof settings can also be able to alter the apps updates list.

#### **How can I report a bug or suggest something?**

You can open issues on GitLab [here](https://gitlab.com/AuroraOSS/AuroraStore/issues), or you can do so by joining our [Telegram Support Group](https://t.me/AuroraSupport). Use `/bug` or `/suggestion` at the start of your message. If urgent, you can tag [@whyorean](https://t.me/whyorean).

#### **How do I join/contribute to** _**Aurora Store**_**?**

For code and UI improvements, do a Merge Request. These will not be looked as often, but if it's something major then we will consider merging.

For feature requests, open an issue with \[Feature Request\] at the start of your title. If in consideration there will be a 'Feature Request' label on your issue.

