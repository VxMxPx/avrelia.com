# Remove Unused Packages (Arch)

- slug: remove-unused-packages
- date: 2013-08-29
- tags: arch, gnu-linux, tech
- source: http://bbs.archbang.org/viewtopic.php?id=2557

-----------------

To list all packages no longer required as dependencies (orphans):

````bash
pacman -Qdt
````

Pacman saves important configuration files when removing certain applications and names them with the extension: `.pacsave`. To prevent the creation of these backup files use the `-n` option:

````bash
pacman -Rn <package_name>
````

Remove all package and all dependencies:

````bash
pacman -Rs <package_name>
````

If you want to remove package, dependencies and prevent the creation of backup files:

````bash
pacman -Rns <package_name>
````

Remove all no longer required dependencies (careful!):

````bash
pacman -Rns $(pacman -Qqtd)
````