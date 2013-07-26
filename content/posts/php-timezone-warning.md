# PHP Timezone Warning

- slug: php-timezone-warning
- date: 2012-11-14
- tags: php, apache, tech, server, www-dev

----------------------------

After upgrade to PHP 5.4 you might come across following error:

	PHP Warning: date(): It is not safe to rely on the system's timezone settings. You are *required* to use the date.timezone setting or the date_default_timezone_set() function. In case you used any of those methods and you are still getting this warning, you most likely misspelled the timezone identifier. We selected the timezone 'UTC' for now, but please set date.timezone to select your timezone.

To fix it edit following files:

````bash
sudo nano /etc/php5/apache2/php.ini
sudo nano /etc/php5/cli/php.ini
````

Find the `date.timezone` key and correct it to be as on the example bellow:<br>
_Don't forget to remove the semicolon in front of it!_

````ini
[Date]
; Defines the default timezone used by the date functions
; http://php.net/date.timezone
date.timezone = YOUR_TIMEZONE_HERE
````

You can find list of valid timezones on: http://php.net/manual/en/timezones.php