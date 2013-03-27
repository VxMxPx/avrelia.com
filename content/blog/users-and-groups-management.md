# Users and Groups Management

- slug: users-and-groups-management
- date: 2012-11-06
- tags: gnu-linux

-------------------

List users

````bash
lastlog
````

List user's groups

````bash
groups
````

Add user to a specific group

````bash
usermod -G group_name -a username
````

List groups

````bash
cat /etc/group
````

Create user

````bash
adduser username
passwd username
````

Delete user

````bash
userdel username
````

Delete user and user's home directory

````bash
userdel -r username
````

Create group

````bash
groupadd group_name
````

Delete group

````bash
groupdel group_name
````
