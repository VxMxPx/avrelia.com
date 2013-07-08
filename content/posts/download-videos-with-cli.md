# Download Videos with CLI

- slug: download-videos-with-cli
- date: 2013-07-08
- category: tech
- tags: gnu-linux

-----------------

We can use a small command-line program called `youtube-dl` for this purpose. The program is able to download videos (individual and whole playlists) from YouTube and [many other websites](http://rg3.github.io/youtube-dl/documentation.html#d4).

But first of all, **why would you actually need this?** Here's couple of (probably not all of) reasons:

- the YouTube UX [ain't exactly the best](/r/opinion/2013/the-terrible-youtube-ux.html),
- traveling to no-internet areas,
- care about your privacy (conditionally),
- don't wanna use non-free software.

Install _youtube-dl_ with:

````bash
yaourt youtube-dl
````

See available options:

````bash
youtube-dl -h
````

Download a video:

````bash
youtube-dl -f [FORMAT] http://VIDEO_URL
# Example
youtube-dl -f 44 http://www.youtube.com/watch?v=swSn7d_kHQA
````

To see the available formats:

````bash
youtube-dl -F http://VIDEO_URL
# Example
youtube-ld -F http://www.youtube.com/watch?v=swSn7d_kHQA
````