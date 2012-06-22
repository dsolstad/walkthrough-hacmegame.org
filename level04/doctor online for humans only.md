#### Level 4: Doctor Online for humans only

View cookie information with Web Developer and find the cookie named "cptch". Mine has the value 31:46:64:58:38.
Then we can see what happens when we turn this into ASCII.

```php
<?php
print chr(31).chr(46).chr(64).chr(58).chr(38);
?>
```

Result:
```
.@:&
```

That didn't look right. Let's assume it's hex and make it decimal before we turn it into ASCII:
```php
<?php
print chr(hexdec(31)).chr(hexdec(46)).chr(hexdec(64)).chr(hexdec(58)).chr(hexdec(38));
?>
```

Result:
```
1FdX8
```

Yep, it worked.