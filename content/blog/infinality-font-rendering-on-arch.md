# Infinality font rendering on Arch

- slug: infinality-font-rendering-on-arch
- date: 2013-02-02
- source: https://wiki.archlinux.org/index.php/Font_Configuration#Infinality
- tags: gnu-linux, arch

--------------------

The infinality patchset aims to greatly improve freetype2 font rendering.<br>
Install it with `yaourt`:

````bash
yaourt freetype2-infinality
yaourt fontconfig-infinality
````

... and set style:

````bash
infctl setstyle [linux|osx|osx2|win7]
````