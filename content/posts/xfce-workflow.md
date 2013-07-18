# Xfce Workflow

- slug: xfce-workflow
- date: 2013-05-12
- category: tech
- tags: gnu-linux
- source: http://www.xfce.org/
       || https://wiki.archlinux.org/index.php/Xfce
       || https://wiki.archlinux.org/index.php/GDM
       || http://tools.suckless.org/dmenu/

-----------------

Xfce is a lightweight desktop environment for UNIX-like operating systems. It aims to be fast and low on system resources, while still being visually appealing and user friendly.

We can install it with:

````bash
sudo pacman -S xfce4 xfce4-goodies
````
I'm using GDM as a display manager:

````bash
sudo pacman -S gdm
````

## Tiling WM (Pytyle3 + Patch)

Xfce is a floating window manager, but since I like tiles sometimes, I've installed pytyle3:

````bash
yaourt pytyle3
````

There's a bug though, when you press `MOD+L` or `MOD+K` or `MOD+Enter`, pytyle will crush.

I've patched this bug, <del datetime="2013-07-13T22:00:00Z">you can apply the patch by executing:</del><br />
<ins datetime="2013-05-15T08:00:00Z">Actually this was merged with upstream, so I suppose you can ignore the steps bellow.</ins>

````bash
sudo su

curl https://raw.github.com/VxMxPx/pytyle3/master/pt3/layouts/layout_vert_horz.py > /usr/lib/python2.7/site-packages/pt3/layouts/layout_vert_horz.py
````
You can _diff_ it first, to see there's nothing evil in it (there should be only one _if statement_ added):

````bash
curl https://raw.github.com/VxMxPx/pytyle3/master/pt3/layouts/layout_vert_horz.py | diff /usr/lib/python2.7/site-packages/pt3/layouts/layout_vert_horz.py -
````

## Launcher (dmenu - patched)

As a launcher I'm using (patched version of) dmenu. Dmenu is a fast and lightweight dynamic menu for X. It reads arbitrary text from stdin, and creates a menu with one item for each line.

Install it with:

````bash
sudo pacman -S dmenu
````

If you want xmms-like pattern matching, then you need to install a patched version:

````bash
yaourt dmenu-tok-patch
````
Please read on to see how to attach the `dmenu_run` command to a keystroke combination.

## Other

For music I'm using [Ncmpcpp](/r/tech/2013/listen-to-music-with-ncmpcpp.html) and for my Skyping [Finch](/r/tech/2013/skype-in-cli.html).

I've added only one panel to Xfce, on the top of the screen, and set _Row Size_ to be _18px_. I've also added a little bit of style to it (create file `~/.gtkrc-2.0`) with following content:

````css
style "panel"
{
  bg[NORMAL]   = "#414140"
  fg[NORMAL]   = "#cccccc"
  font_name    = "PT Sans 9"
}

widget_class "*Panel*"      style "panel"
widget "*Panel*"            style "panel"
class "*Panel*"             style "panel"
````
I'm using _Numix_ style, _Faenza-Dark_ icons, _DejaVu Sans Book/9_ font, _Litestyle_ theme, _PT Sans/9_ as a title font.

I've created five workspaces, four are present all the time and the fifth I add only when I need it. I've named them:

````
1: Ground # Everyday: Browser + 2 Terminals
2: Air    # IM: Finch
3: Water  # Music: Ncmpcpp
4: Fire   # Work: Sublime Text 2, etc...
5: Chaos  # Various things
````

## Keyboard Shortcuts

### Audio

````
XF86AudioLoweVolume   amixer set Master 5%-
XF86AudioRaiseVolume  amixer set Master 5%+
XF86AudioMute         amixer set Master toggle
XF86AudioNext         ncmpcpp next
XF86AudioPrev         ncmpcpp prev
XF86AudioStop         ncmpcpp stop
XF86AudioPlay         ncmpcpp toggle
````

### IM

For Finch, create a file `~/.gntrc` with the following content:

````ini
[GntWM::binding]
a-n = window-next
a-p = window-prev
a-c = window-close
a-w = window-list
a-c-d = dump-screen
a-, = shift-left
a-. = shift-right
a-e = action-list
a-R = start-move
a-r = start-resize
a-q = wa-quit
a-l = refresh-screen
a-s = workspace-list
a-t = window-tag
a-T = place-tagged
a-C = toggle-clipboard
a-/ = help-for-widget
a-c-j = window-scroll-down
a-c-k = window-scroll-up
# The following action is still incomplete, and doesn't have a default binding
# switch-window-n
# Other actions: window-next-urgent, window-prev-urgent

# For the sample custom window manager
[GntS::binding]
a-b = toggle-buddylist

# For the irssi window manager
[Irssi::binding]
a-L = move-right
a-H = move-left
a-J = move-down
a-K = move-up
````

### Launcher

````
Alt+t  xfce4-terminal

# Special command for dmenu, parameters set background and text colors
Alt+d  dmenu_run -t -nb "#414140" -nf "#cccccc" -sb "#dd5555" -sf "#ffffff"
````

### WM, Tiling

````
Alt+Tab        Cycle windows
Alt+F4         Close window
Alt+F10        Maximize window
Alt+F11        Toggle fullscreen
Primary+Alt+1  Move window to workspace 1
Primary+Alt+2  Move window to workspace 2
...
Alt+1          Workspace 1
Alt+2          Workspace 2
...
Alt+Up         Tile window to the top
Alt+Down       Tile window to the bottom
Alt+Left       Tile window to the left
Alt+Right      Tile window to the right
Alt+Insert     Add workspace
Alt+Delete     Delete last workspace
````

Add a file `~/.config/pytyle3/keybind.py` with the following content:

````python
import state
import tile

bindings = {
    'Mod1-a':       tile.cmd('tile'),
    'Mod1-u':       tile.cmd('untile'),
    'Mod1-h':       tile.cmd('decrease_master'),
    'Mod1-l':       tile.cmd('increase_master'),
    'Mod1-j':       tile.cmd('prev_client'),
    'Mod1-k':       tile.cmd('next_client'),
    'Mod1-Shift-j': tile.cmd('switch_prev_client'),
    'Mod1-Shift-k': tile.cmd('switch_next_client'),
    'Mod1-Shift-period': tile.cmd('remove_master'),
    'Mod1-period':  tile.cmd('add_master'),
    'Mod1-Return':  tile.cmd('make_master'),
    'Mod1-m':       tile.cmd('focus_master'),
    'Mod1-z':       tile.cmd('cycle'),

    'Mod1-q':       tile.debug_state,
    'Mod1-Shift-q': state.quit,
}
````
