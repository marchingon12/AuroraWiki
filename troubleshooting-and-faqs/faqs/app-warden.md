# App Warden

### How does it work?

App Warden has a static curated list of known trackers from [Exodus Privacy](https://reports.exodus-privacy.eu.org/en/), the dex file of each app is read to retrieve the class names, which are then matched with the signatures of known trackers & loggers to find them.

A list of currently known [trackers](https://gitlab.com/AuroraOSS/AppWarden/-/blob/master/app/src/main/assets/trackers.json) & [loggers](https://gitlab.com/AuroraOSS/AppWarden/-/blob/master/app/src/main/assets/loggers.json) can be found on GitLab.

Loggers in the context of Warden means all utilities which are used to log user activity on an app or logcat in general. Not all loggers are evil. But a few logging tools like ACRA, xLog are very powerful tools that can send user data to Devs without the user's consent. That's why you should always read the app's Privacy Policy beforehand.

### What features are there?

**Manual App management**

Users can manage their installed apps using the **Apps** tab on main screen. Non-rooted users can manually check trackers/loggers for each installed app on the device.

Devices which have **root** access can perform some advance actions by pressing the icon on app page. Advance actions include: **Hide**, **Uninstall**, **Disable**, **Suspend**, **Clear data**.

**Rooted** users can also manually disable app components of their own choice. App Warden currently uses `su pm` to manage the components.

{% hint style="info" %}
**Note**: By default only user installed apps are shown in app list, to preview system apps enable **Include System Apps** from Settings.&#x20;
{% endhint %}

**Tracker search function**

Warden provides direct access to Exodus Privacy scanned app Database. Use the search function on main home screen & just paste the "package name" (e.g.: `com.whatsapp` for WhatsApp & `com.google.android.youtube` for YouTube) of the app in search bar & hit search button.

If no results are found, try to submit the app manually for analysis on the [Exodus web portal](https://reports.exodus-privacy.eu.org/en/analysis/submit/). After 2–3 minutes from submission time, results will be received in Warden, if successfully scanned by Exodus.

{% hint style="warning" %}
Please keep in mind that not all apps can be scanned by online static analysis. Paid apps & other apps that are geographically restricted cannot be scanned using Exodus Privacy.
{% endhint %}

**Monitor app usage**

Warden also monitors & preview app usage stats of device in graphs. Like which app used recently & for how long time. This data surely helps you to think once about your app usage time 😉.

{% hint style="info" %}
**Note**: **App Usage Access** permission is required to read & generate usage data.&#x20;
{% endhint %}

**Stats for tracker & loggers**

Warden also shows the stats like the current amount of trackers & loggers present on device by scanning all installed apps. This feature only previews data/graphs when the user has scanned all apps using the **Scan Now** button on main screen.

### Warden LAB

Currently, it consists of two features, i.e. [De-bloater](https://github.com/aurora-website/website\_v1/blob/source/src/faq/README.md#de-bloater) & [Nuke it!](https://github.com/aurora-website/website\_v1/blob/source/src/faq/README.md#nuke-it). These features are experimental, but will surely improve with time.

**De-bloater**

Warden provides a profile based de-bloater where a profile is created in a specific JSON file format.

You need to place this profile/your custom profile at **Internal Storage** → **Warden** → **Profiles** to make them appear in app.

Get **De-bloat** scripts made by AuroraOSS [here](https://files.auroraoss.com/?folder=Warden/Scripts).

You can also improve current **De-bloat** scripts or submit your own with the same format by making PR on [GitLab](https://gitlab.com/AuroraOSS/AppWarden) or sending it to our AuroraOSS discussion group!

{% hint style="info" %}
The default action for De-bloating is to 'disable' apps, but you can configure it to 'uninstall' or 'hide' from Settings. Remember that the **De-bloat** function is currently experimental and will surely improve in future releases.
{% endhint %}



**Nuke it!**

**Nuke it!** is another experimental feature that scans all apps on the device and disables all know tracker components for installed apps automatically. It also gives an option to export components\* names per-app basis.

You can revert the Nuke it effects by toggling De-Nuke button from the same section. All apps components will be restored to its original state after De-Nuking.

\*Components: **Activities**, **Services**, **Providers** & **Receivers** of installed apps.
