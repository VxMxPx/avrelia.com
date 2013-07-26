# Listen to music with Ncmpcpp

- slug: listen-to-music-with-ncmpcpp
- date: 2013-05-09
- tags: gnu-linux, cli, music, tech
- source: https://wiki.archlinux.org/index.php/Ncmpcpp ||
          https://wiki.archlinux.org/index.php/Music_Player_Daemon

-----------------

Ncmpcpp is a MPD client, which runs in a terminal.

![Ncmpcpp](/media/listen-to-music-with-ncmpcpp.png)

## Setup MPD

First we need to install MPD (music player daemon):

````bash
sudo pacman -S mpd
````

MPD can be configured per user (rather than the typical method of configuring MPD globally). To setup:

````bash
mkdir -p ~/.mpd/playlists
cp /usr/share/doc/mpd/mpdconf.example ~/.mpd/mpd.conf
touch ~/.mpd/{database,log,state}
````

Edit `~/.mpd/mpd.conf` and specify the requisite files:

````bash
music_directory    "~/music"          # Can keep commented if XDG music dir.
playlist_directory "~/.mpd/playlists"
db_file            "~/.mpd/database"
log_file           "~/.mpd/log"
pid_file           "~/.mpd/pid"
state_file         "~/.mpd/state"
````

When (if) I need it, I start MPD manually by opening terminal and typing in `mpd` (no sudo!).

## Setup Ncmpcpp

Install Ncmpcpp:

````bash
sudo pacman -S ncmpcpp
````

If after installation `~/.ncmpcpp/config` file is missing copy it from `/usr/share/doc/ncmpcpp/config` and edit at the very least the following three configuration options:

````bash
mpd_host # the host on which mpd resides; either "localhost" or "127.0.0.1" if on the same machine
mpd_port # unless you've changed the defaults of mpd, this should be "6600"
mpd_music_dir # the same directory value as specified in "music_directory" in mpd.conf
````