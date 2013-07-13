# (Too) Many Dictionaries in Firefox

- slug: too-many-dictionaries-in-firefox
- date: 2013-07-13
- category: tech
- tags: gnu-linux
- source: https://wiki.archlinux.org/index.php/Firefox

-----------------

By default, Firefox will try to symlink all your hunspell dictionaries in `/usr/lib/firefox/dictionaries`.
If you want to have less dictionaries offered to you in Firefox, you can remove some of those links. _Be aware that it may not stand an upgrade of Firefox._

In my example, there was whole bunch of English variations displayed, like: English (Australian),
English (British), English (Canadian), English (New Zealand), English (South African), etc...

So, the solution as mentioned above is:

````bash
sudo rm /usr/lib/firefox/dictionaries/*
````

And then go to [https://addons.mozilla.org/en-US/firefox/language-tools/](https://addons.mozilla.org/en-US/firefox/language-tools/) and install
only what you need, in my case that was English (US) and Slovenian.