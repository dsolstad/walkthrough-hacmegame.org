#### Level 01 -  A slightly more interesting challenge

Same as before, view the source and find
```html
<!-- Password: 38:39:47:7a:55:4f -->
```

This looks like a MAC-address, which contains hex. Let's convert it to decimal and then again to ASCII and see what happens:

```php
<?php
$x = array('38','39','47','7a','55','4f'); 
$a = array_map('hexdec', $x); 
$b = array_map('chr', $a); 
print join('',$b);
?>
```

The code returns 89GzUO which is the password (your password could be different)