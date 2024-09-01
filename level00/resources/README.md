## Get all files with user flag00
find / -user flag00 2>/dev/null

-> /usr/sbin/john
-> /rofs/usr/sbin/john

## show the encrypted flag00 password inside the file /usr/sbin/john
cat /usr/sbin/john

-> cdiiddwpgswtgt

## Decrypt the encrypted password using ROT11
I use this [website](https://www.useotools.com/es/rot13) to apply ROT11 in the encrypted password
cdiiddwpgswtgt - ROT11 -> nottoohardhere


## Access to user flag00 and get the password for user level01
su flag00 (password : nottoohardhere)
getflag
-> x24ti5gi3x0ol2eh4esiuxias