# Zen Terminal

- slug: zen-terminal
- date: 2012-11-01
- tags: gnu-linux, tech, cli

-------------------------

![GNU/Linux Terminal](/media/zen-terminal.png)

If you'd like to have terminal as on the picture above, then simply edit
your `~/.bashrc` file, and insert following code around line 60 (or just at the end):

````bash
PS1='\n${debian_chroot:+($debian_chroot)}\[\033[01;30m\](\[\033[00m\]\[\033[00;37m\]\w\[\033[00m\]\[\033[01;30m\])\[\033[00m\]\n\[\033[01;30m\]➜\[\033[00m\] '
````