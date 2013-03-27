# A Complete GNOME 3 Desktop in Ubuntu 12.10

- tags: gnome, gnu-linux
- source: http://www.webupd8.org/2012/10/how-to-get-complete-gnome-3-desktop-in.html
- date: 2012-10-30
- slug: a-complete-gnome3-desktop-in-ubuntu-12-10
- author: marko

--------------------

Install GNOME Shell along with the GNOME3 core applications:

````bash
sudo apt-get install ubuntu-gnome-desktop ubuntu-gnome-default-settings
````

When prompted, select GDM as the default display manager.<br />
If you already had GDM installed and the package manager didn't prompt you to
choose between LightDM and GDM or you've selected LightDM by mistake, you can run the following command:

````bash
sudo dpkg-reconfigure gdm
````

You can use LightDM with GNOME Shell, but you won't get the complete
GNOME 3 experience - for instance, GNOME Shell won't use the new GNOME 3.6 lock screen.
It is also a good idea to remove the "ubuntu-settings" package:

````bash
sudo apt-get remove ubuntu-settings
````

Note that removing this package, the "ubuntu-desktop" package will be
removed as well. This is just a meta package and your system shouldn't be affected by it.
The "ubuntu-settings" package is used to set various Ubuntu defaults,
like the window button order, which Rhythmbox plugins are enabled by default and so on.