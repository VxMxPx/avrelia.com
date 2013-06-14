# Convert .bin to .iso without .cue

- slug: convert-bin-to-iso-without-cue
- date: 2013-06-14
- tags: gnu-linux

-----------------

If you don't have .cue file then you can use the following command to create it:

````bash
bin2iso file.cue -c file.bin
````

To convert .bin/.cue file to .iso you can use `bchunk`:

````bash
 bchunk file.bin file.cue file.iso
````

To mount newly created iso file you can use `mount`:

````bash
mount -o loop -t iso9660 file.iso /media/cdrom
````