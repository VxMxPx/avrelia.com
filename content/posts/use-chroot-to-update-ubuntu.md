# Use chroot to update Ubuntu

- source: https://help.ubuntu.com/community/LiveCdRecovery ||
          http://www.tuxgarage.com/2011/07/creating-chroot-ubuntu.html
- slug: use-chroot-to-update-ubuntu
- date: 2013-03-26
- category: tech
- tags: ubuntu, gnu-linux

---------------------------------

## Why would you do this?

If there was an update that made your system non-bootable and they have fixed it
in the repositories, you can use the Live CD to run apt-get to get the new files to fix your system.

In my case, wireless was functional before (and during) the installation, but was
not working on installed system, so I had to (connect to the internet) and
install bunch of things to get it working.

## How to do it

Boot the Ubuntu Live CD (or USB Stick), press Ctrl-Alt-F1:

````bash
sudo mount /dev/hda1 /mnt
sudo chroot /mnt
apt-get update
apt-get upgrade
# Other things you need to do
exit
sudo umount /mnt
````

## Alternative way

First, you need to figure the partition notation for your '/' drive
which looks like 'sda1', 'sda2' etc:

````bash
sudo fdisk -l
````

For creating the Chroot, you need to run commands written bellow one-by-one
**Note: 'sdXY' is your '/' partition.**

````bash
sudo mkdir /mnt/temp
sudo mount /dev/sdXY /mnt/temp
for i in /dev /dev/pts /proc /sys; do sudo mount -B $i /mnt/temp$i; done
sudo cp /etc/resolv.conf /mnt/temp/etc/resolv.conf
sudo chroot /mnt/temp
````

After you've finished working type 'exit' in the Terminal to exit the Chroot.
Then un-mount the previously mounted locations by running this command:

````bash
for i in /dev/pts /dev /proc /sys; do sudo umount /mnt/temp$i ; done
````