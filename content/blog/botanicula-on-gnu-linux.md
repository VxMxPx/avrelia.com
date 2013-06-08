# Botanicula on GNU/Linux

- slug: botanicula-on-gnu-linux
- date: 2013-06-08
- tags: gnu-linux, games
- source: http://appdb.winehq.org/objectManager.php?sClass=version&iId=25119

-----------------

Botanicula is a point'n'click exploration game created by Jaromír Plachý and Amanita Design. This is not an ordinary game. It is far from it. Everything about it is curiously unique and very surreal, and that alone makes it worth checking out.

I've bought it on [GOG](http://www.gog.com/gamecard/botanicula).

It works flawlessly on GNU/Linux, I just needed to install [Adobe Air](http://get.adobe.com/air/).
Air installation initially failed with the message: _"This application needs a version of Adobe AIR that can't be found. [...]"_.

Luckily this problem can easily be fixed by installing 32-bit version of _liblcms_.

````bash
sudo pacman -S lib32-lcms
````

![Botanicula](/media/botanicula-on-gnu-linux.jpg)