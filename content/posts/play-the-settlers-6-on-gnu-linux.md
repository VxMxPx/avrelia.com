# Play The Settlers 6 on GNU/Linux

- slug: play-the-settlers-6-on-gnu-linux
- date: 2013-09-22
- tags: games, gnu-linux, tech
- source: http://appdb.winehq.org/objectManager.php?sClass=application&iId=5643
          || http://www.codeweavers.com/compatibility/browse/name/?app_id=3944;tips=1

-----------------

Beside part two, the settlers 6 are my favorite settlers game. To run them on GNU/Linux it's a little bit tricky. As a matter of fact, to this point I was sure it's impossible, as I was experiencing heavy problems with texture rendering, making the game pretty much unplayable.

Today I somehow randomly found a solution for this problem. Here's what you need to do:

1. Install the game from your DVD
2. Edit (or add to) the registry (use `regedit`): `CURRENT_USER\Software\Wine\AppDefaults\Settlers6.exe\Direct3D` set:
  - `"OffscreenRenderingMode"="fbo"`
  - `"VideoMemorySize"="256"`
3. Allow game to be updated to the version 1.7.1
4. Download and apply NO-DVD fix, **for version 1.5.4**

_For me, so far everything looks good and running smooth with all graphics options set to high._

![](/media/settlers-6-on-gnu-linux.jpg)