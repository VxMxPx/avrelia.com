# Display Settings With xrandr

- slug: display-settings-with-xrandr
- date: 2012-10-31
- tags: gnu-linux

--------------

Wanna set gamma, brightness, position, ... of display?

````bash
xrandr --output LVDS1 --gamma 0.9:0.9:0.9 --brightness 1
````
Above example will set gamma and brightness.<br>
To get the display name (LVDS1), run:

````bash
xrandr
````
To see all options available run:

````bash
xrandr --help
````