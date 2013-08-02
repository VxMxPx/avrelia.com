# About Facebook (Application on Android)

- slug: about-facebook-application-on-android
- date: 2013-07-19
- tags: social-networks, privacy, critique, android, tech, mobile
- source: http://androidforums.com/android-applications/36936-android-permissions-explained-security-tips-avoiding-malware.html

-----------------

The fact that I'm writing about Facebook doesn't mean that other applications are much better.
Most of them require permissions which I can't imagine why they would need.

However, still among applications which I've installed, Facebook absolutely is the worst example.

Here's the list of Facebook's requests:

**Your personal information**
<br /><small>_read contact data, write contact data_</small>
<br />Allows an application to read and write the user's contacts data. I'd imagine this is needed for merging your Facebook contacts with your phone contacts.
Additionally to that, it might be used for collecting information about existing  users and [non-users of Facebook](http://www.dailymail.co.uk/sciencetech/article-2052500/Facebook-building-shadow-profiles-non-users-claims-privacy-watchdog.html).

**Services that cost you money**
<br /><small>_directly call phone numbers_</small>
<br />Allows an application to initiate a phone call without going through the Dialer user interface for the user to confirm the call being placed. I'm not sure where (if at all) in Facebook application this is implemented.

**Your location**
<br /><small>_coarse (network-based) location, fine (GPS) location_</small>
<br />This might be used for advertisement and/or _check in_ functionality which Facebook offers. Additional to that it's also possible that Facebook is tracking your location, just to expand the amount of information they already have about you; as we know they're [planning](http://www.dailymail.co.uk/sciencetech/article-2274954/Facebook-developing-app-track--s-turned-off.html) [to do this](http://www.bloomberg.com/news/2013-02-04/facebook-is-said-to-create-mobile-location-tracking-app.html) [in near future](http://www.forbes.com/sites/mattmiller/2013/02/05/facebook-know-where-you-are/) more professionally.

**Network communication**
<br /><small>_full Internet access, download files without notification, Google Play billing service, receive data from Internet, view network state, view Wi-Fi state_</small>
<br />Google Play billing service allows an application to bill you directly for services through Google Play. I guess this has to do with the fact that you can pay for things through Facebook. The second thing worth noticing is _download files without notification_, the reasoning behind it supposed to be the usage of DownloadManager component for handling downloads. Again, I'm not sure where Facebook is handling downloads. Other applications like: YouTube, Firefox, Skype, Dropbox **doesn't** require this permission.

**Your accounts**
<br /><small>_act as an account authenticator, manage the accounts list, discover known accounts, read Google service configuration_</small>
<br />Used for manging Facebook account; this is the account you can see in _Settings > Acounts and Sync_. Additionally this permission can be used so that Facebook can (for example) post on your behave on other services like Twitter, etc... In other words, it might impersonate you. Of course, you'd be asked (once) if you allow this.

**Storage**
<br /><small>_modify/delete USB storage contents_</small>
<br />Pretty much self explanatory, this allows Facebook to save (and delete) files from your SD card. Pretty much any application you install will require this.


**Phone call**
<br /><small>_read phone state and identity_</small>
<br />Among more common things, like seeing if you're on a call, this permission allows Facebook to get:

* unique device ID, for example, the **IMEI**,
* software version number for the device, for example, the IMEI/SV,
* numeric name (MCC+MNC) of current registered operator,
* a constant indicating the radio technology (network type),
* the serial number of the SIM, if applicable,
* the unique subscriber ID, for example, the IMSI for a GSM phone,
* if the device is considered roaming on the current network,
* [and the list goes on](http://developer.android.com/reference/android/telephony/TelephonyManager.html).

**Hardware controls**
<br /><small>_record audio, take pictures and videos, control vibrator_</small>
<br />Recording audio has legitimate uses such as note taking or voice search applications. While this permission is not typically dangerous, it is a potential tool for eavesdropping. The same goes for the _take pictures and videos_ permission, which in theory might also be used maliciously, for example to snap unsuspecting photos, however this is rather unlikely in case of Facebook*. It's worth mentioning that Tweeter application require only access to vibrator, YouTube application require only _pictures and videos_ (but not recording audio).

<small>\* With a little bit of [(paranoid) imagination](https://duckduckgo.com/?q=NSA+spying), however, we can imagine how <del>Facebook</del> <ins>NSA</ins> is recording all our phone calls. But I guess that's crazy assumption, they don't need such primitive methods [to achieve the same](http://www.webpronews.com/nsa-is-writing-security-code-for-android-2013-07).</small>

**System tools**
<br /><small>_display system-level alerts, prevent phone from sleeping, reorder running applications, retrieve running applications, write sync settings, automatically start at boot, install shortcuts, read Home settings and shortcuts, read sync settings_</small>
<br />It will allow an application to find out what other applications are running on your phone. Typical legitimate applications that require this permission include: task killers and battery history widgets. Why does Facebook need it? It's social network application, it's not task manager. Well, introduction of _Facebook Home_ [is supposed to be the reason](https://news.ycombinator.com/item?id=5543583); the second reason (perhaps even prevailing) is probably [Facebook's creepy hunger for information about you](http://techcrunch.com/2013/06/24/creepy-facebook/).

**Conclusion**
<br />The tragedy is, that the Facebook application itself doesn't offer much of functionality (or improved UX) compared to the browser's version. In fact, it's slow, buggy and offers pretty much the same interface. So why really bother with it? It seems the main purpose of it is just to collect as much of personal information as possible. So if you're using Facebook, why not use just browser's version of it? And finally, even better, why not [just stop using Facebook all together](http://en.wikipedia.org/wiki/Criticism_of_Facebook)?