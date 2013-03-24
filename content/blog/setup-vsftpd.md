# Setup VSFTPD

- slug: setup-vsftpd
- date: 2012-11-06
- tags: www-dev, gnu-linux
- source: http://www.techrepublic.com/blog/smbit/how-to-create-an-ftp-server-on-an-ubuntu-1204-virtual-machine/355

-----------------

Install VSFTPD

	apt-get install vsftpd

Change the config file for vsftpd

	nano /etc/vsftpd.conf

Make at least the following changes

	local_enable=YES<br />write_enable=YES<br />chroot_local_user=YES

Restart the vsftpd service

	service vsftpd restart

Create a local user so people can authenticate when trying to connect to the FTP server

	useradd username<br /><span>passwd username</span>

Add user's directory to /home and chmod it to

	chmod a-w /home/user-dir

If you want users to be able to upload files and create folders use following commands

	chmod g-w /home/user-dir<br />chown root:username /home/user-dir
