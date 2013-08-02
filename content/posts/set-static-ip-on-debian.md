# Set Static IP on Debian

- slug: set-static-ip-on-debian
- date: 2013-08-02
- tags: tech, debian, cli, server
- source: http://www.massimilianomarini.com/28/05/2011/how-setup-static-ip-address-debian-6-squeeze

-----------------

In `/etc/network/interfaces` find interface for which you want to set static IP and
edit it like in the example bellow.

If you're unsure what to enter, you can check you current settings with: `/sbin/ifconfig` and to find your gateway address `ip route show` (see the first line where is written _via_).

````bash
iface [interface] inet static # <-- Change DHCP to static here!
address 192.168.1.100         # <-- Your new static IP address
gateway 192.168.1.1           # <-- Your gateway address
netmask 255.255.255.0         # <-- Net mask (Mask)
network 192.168.1.0           # <-- Network usually ends with .0
broadcast 192.168.1.255       # <-- Broadcast (Bcast)
````

If you need to modify your name server(s), you can edit the `/etc/resolve.conf` file, and enter servers one by line, like in the example bellow (in my case this was already set):

````bash
nameserver 192.168.1.2
nameserver 192.168.1.3
````

Finally restart networking with following command:

````bash
sudo ifdown eth0 && sudo ifup eth0
````