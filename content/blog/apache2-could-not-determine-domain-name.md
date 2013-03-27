# Apache2: Could not determine domain name

- slug: apache2-could-not-determine-domain-name
- date: 2012-11-16
- source: http://xubuntugeek.blogspot.ie/2012/07/solved-apache2-could-not-reliably.html
- tags: apache, gnu-linux

-------------------------------

If you get this error message when starting apache:

	* Starting web server apache2
	apache2: Could not reliably determine the server's fully qualified domain name, using 127.0.1.1 for ServerName

Use following command:

````bash
	sudo gedit apache2.conf
````

Append to the end of the file:

	ServerName localhost
