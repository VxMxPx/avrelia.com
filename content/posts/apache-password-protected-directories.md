# Apache Password Protected Directories

- slug: apache-password-protected-directories
- date: 2012-10-30
- tags: apache, gnu-linux, www-dev, tech, server
- source: http://www.aaronsw.com/2002/howto/passwords

--------------------

Generate file containing all users, in our example this file will be stored
inside `.apache2` directory, not publicly accessible:

````bash
htpasswd -c .htpasswd username
````

Where username is the username you want to require. It will then ask you
for the password you want to require. If you want to add another account,
say for new_user, do this:

````bash
htpasswd .htpasswd new_user
````

Now edit `.conf` file and add to the directory tag (the one you want to password
protect), the following lines:

	AuthUserFile /full/path/to/example.dev/.apache/.htpasswd
	AuthGroupFile /dev/null
	AuthName "Please enter username and password to continue..."
	AuthType Basic require valid-user