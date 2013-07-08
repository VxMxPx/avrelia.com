# Skype in CLI

- slug: skype-in-cli
- date: 2013-05-10
- category: tech
- tags: gnu-linux

-----------------

Finch - A Pimpin' Penguin console frontend to libpurple. Instant Messaging client, which runs in a terminal.

![Skype in CLI](/media/skype-in-cli.png)

Install finch:

````bash
sudo pacman -S finch
````

In order to use it with Skype, we must install Skype plugin for Finch:

````bash
yaourt finch skype # select aur/skype4finch
````
**Please note, Skype must be running in the background in order for Finch to work.**