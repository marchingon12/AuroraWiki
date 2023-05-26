# Aurora Droid

### General

**What is Aurora Droid?**

Aurora Droid is an unofficial, FOSS client to F-Droid and F-Droid compatible repositories with an elegant design. Not only does Aurora Store download, update, and search for apps like the Official F-Droid client, it also empowers the user with new features.

**How can I report a bug or suggest something?**

You can do it in the Aurora Store support group, Aurora Official support group or by opening an issue on GitLab with the issue template. Before anything, please check our [Bugs & Suggestions](https://t.me/aurorabugsandsuggestions) channel to see if your findings or suggestions have been reported and remember to use `/bug` and `/suggestion` at the start of your message so that our bot picks up your message and forwards it to our channel. If urgent, you may tag [@whyorean](https://t.me/whyorean).

**Why does this even need the camera permissions?**

Many repositories provide a QR code for their links, and Aurora Droid can scan them directly. If you don't want to use this feature, you don't need to give it permissions. You can always add links manually.

**Why is there WhatsApp / Skype / some miscellaneous proprietary app in the apps list? This is blasphemy!**

Why do you think? Many repos (including [Haagch](https://haagch.frickel.club/files/fdroid/repo/) and [IzzyOnDroid](https://apt.izzysoft.de/fdroid/)) are known to include proprietary/non-free applications. All of them are disabled at start, so it's on you if you enable them without knowing them.

### Installations

**How does Aurora Droid install apps?**

Aurora Droid can install apps in 4 ways:

* **Session** (Recommended) - Works similarly to [SAI](https://github.com/Aefyr/SAI). There are 2 ways session installer can be used. If you have Aurora Droid installed as a system application, this will have the same effect as if you were to install [Aurora Services](https://github.com/aurora-website/website\_v1/blob/source/src/faq/README.md#aurora-services) as a system application. However, you will need an unlocked bootloader with a custom recovery similar to TWRP installed.
* **Native** - Whenever an app is downloaded, it will open the native android installer screen. This doesn't require root or system permissions, but does _not_ support split apk installations.
* **Root** - By giving Aurora Droid root or system permissions, it will automatically install apps in the background as soon as they are downloaded. If you have root, use this method.
* **Aurora Services** - By installing Aurora Services as a system app, Aurora Droid can automatically install apps in background after the download complete.

**How to add a new Repository in Aurora Droid ?**

To add a new repository, use "Repositories" button given in left side menu. Choose `Add new repository`, after that, type name of repo in 1st section, then paste the repository URL in second section & repository fingerprint (if available) in last section.

Example:

{% hint style="success" %}
Adding the F-Droid Repo\
\
**Repo Name**: F-Droid

**Repo URL**: [https://f-droid.org/repo](https://f-droid.org/repo)

**Repo Fingerprint (Optional)**:

\
`43238D512C1E5EB2D6569F4A3AFBF552`

`3418B82E0A3ED1552770ABB9A9C9CCAB`


{% endhint %}
