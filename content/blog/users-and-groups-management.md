# Users and Groups Management

- slug: users-and-groups-management
- date: 2012-11-06
- tags: gnu-linux

-------------------

List users

	lastlog

List user's groups

	groups

Add user to a specific group

	usermod -G group_name -a username

List groups

	cat /etc/group

Create user

	adduser username<br />passwd username

Delete user

	userdel username

Delete user and user's home directory

	userdel -r username

Create group

	groupadd group_name

Delete group

	groupdel group_name
