# Running Two Firefox Profiles in Parallel

- slug: running-two-firefox-profiles-in-parallel
- date: 2013-07-17
- category: tech
- tags: gnu-linux

-----------------

I'm using two profiles in Firefox with different Add-ons and configurations.
I have one profile for _casual_ browsing and another for development purposes
and both can run in parallel.

First thing I've done I added the second profile.
I've run Firefox with following command, to display profile manager:

````bash
firefox -P
````

Through GUI I've added the second profile, named it `Developer` and saved it to the suggested location.
I've also renamed the default profile from `default` to `Default` (I've just capitalized it).

Finally I've added shortcuts, that wasn't hard since I'm using [dmenu](/r/tech/2013/xfce-workflow.html#toc_1):

I've created _developer_ script in `/usr/bin` ...

````bash
sudo nano /usr/bin/ffdev
````
... with following content:

````bash
firefox -no-remote -P "Developer"
````

I've made it executable:

````bash
sudo chmod +x /usr/bin/ffdev
````

Second, I've created _default_ script, by copying _developer_:

````bash
cp /usr/bin/ffdev /usr/bin/ffdef
````

Finally I've edited `ffdef` with `nano` and changed its content to:

````bash
firefox -no-remote -P "Default"
````