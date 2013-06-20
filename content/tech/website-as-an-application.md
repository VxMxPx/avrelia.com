# Website as an Application

- slug: website-as-an-application
- date: 2012-11-11
- category: tech
- tags: gnu-linux, gnome

--------------------------------

Run any website as an regular application, meaning without the browser's
standard tabs, address-bar, etc..
We'll assume you're using Google Chrome, and the entry in the example will be for Twitter.

Create a new file with following content and save it into the folder `~/.local/share/applications`

````ini
#!/usr/bin/env xdg-open
[Desktop Entry]
Version=1.0
Type=Application
Terminal=false
Icon[en]=/usr/share/icons/Faenza/apps/96/twitter.png
Exec=/opt/google/chrome/google-chrome --app=https://twitter.com/
Name[en]=Twitter
Name=Twitter
Icon=/usr/share/icons/Faenza/apps/96/twitter.png
StartupWMClass=twitter.com
````

To get `StartupWMClass` use following command, and click on windows for which class you want to find out:

````bash
xprop WM_CLASS
````

![Example of Application Website](/media/website-as-an-application.png)