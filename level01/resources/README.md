## Check users info inside passwd file
cat /etc/passwd

->flag01:42hDRfypTqqnw:3001:3001::/home/flag/flag01:/bin/bash

## save the hash password in a file 
echo "42hDRfypTqqnw" > encripted_pass.txt

## use john to crac the encryption
#### to install john the ripper cracker -> apt install jhon
#### link to download [rockyou wordlist](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt)
john encripted_pass.txt --wordlist=rockyou.txt

Loaded 1 password hash (descrypt, traditional crypt(3) [DES 128/128 SSE2-16])
Press 'q' or Ctrl-C to abort, almost any other key for status
abcdefg          (?) <----------
1g 0:00:00:00 100% 100.0g/s 64000p/s 64000c/s 64000C/s hockey..pebbles
Use the "--show" option to display all of the cracked passwords reliably
Session completed

## Access to user flag01 and get the password for user level02
su flag02 (password : abcdefg)
getflag

-> f2av5il02puano7naaf6adaaf