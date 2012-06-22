#### Level 03 - Text analysis was your favorite subject at school

So we get this text:

```
jf cdo vjonuhogv lgofgavdl fkdf ogrgadu jqyhaxdu zsf vjagnf nhqfdnfo kdrg zggq xdvg cjfk bhujfjndu agbagogqfdfjrgo hy fkg rjgf nhqm jq xhonhc - uhm jq cjfk bdoochav dyydja fh agdv fkg vgfdjuo
```

This is the challenge I used the most time on. It's a slow process, which makes you try and replace each char with another. I ended up with this script:

```php
<?php
$string = 'yf cbo syodhwoas uaofamsbu fvbf oakambh ygrwmqbh tzf symadf dwgfbdfo vbka taag qbsa cyfv jwhyfydbh majmaoagfbfykao wr fva kyaf dwge yg qwodwc - hwe yg cyfv jboocwms tbffamu fw mabs fva safbyho';

$x = array('a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z', ' ');
$y = array('e','a','w','c','e','t','n','l','i','p','v','l','r','n','s','p','m','r','d','b','y','h','o','x','i','z', ' ');

$string_arr = str_split($string);
$newstring = '';

foreach($string_arr as $val) {
    $newstring .= $y[array_search($val, $x)];
}

print $newstring;
?>
```

Here is some of the process:
```
user@ubuntu:~/Desktop$ php sadf.php
it cas sisdhwsas uastamsau tvat sakamah igrwmqah tzt simadt dwgtadts vaka taag qasa citv pwhitidah mapmasagtatikas wr tva kiat dwge ig qwsdwc a hwe ig citv passcwms tattamu tw maas tva sataihs
user@ubuntu:~/Desktop$ php sadf.php 
it was sisdhosas uastamsau tvat sakamah igromqah tzt simadt dogtadts vaka taag qasa witv pohitidah mapmasagtatikas or tva kiat doge ig qosdow a hoe ig witv passwoms tattamu to maas tva sataihs
user@ubuntu:~/Desktop$ php sadf.php 
it was disdhosad uastardau tvat sakarah igrorqah tzt diradt dogtadts vaka taag qada witv pohitidah raprasagtatikas or tva kiat doge ig qosdow a hoe ig witv password tattaru to raad tva dataihs
user@ubuntu:~/Desktop$ php sadf.php 
it was disdhosad uastardau that sakarah igrorqah tzt diradt dogtadts haka taag qada with pohitidah raprasagtatikas or tha kiat doge ig qosdow a hoe ig with password tattaru to raad tha dataihs
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosad uastardau that sakaral igrorqal tzt diract cogtacts haka taag qada with political raprasagtatikas or tha kiat coge ig qoscow a loe ig with password tattaru to raad tha datails
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosad uastardau that sakaral inrorqal tzt diract contacts haka taan qada with political raprasantatikas or tha kiat cone in qoscow a loe in with password tattaru to raad tha datails
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosed uesterdau that sekeral inrorqal tzt direct contacts hake teen qade with political representatikes or the kiet cone in qoscow e loe in with password tatteru to read the details
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosed uesterdau that several inrorqal tzt direct contacts have teen qade with political representatives or the viet cone in qoscow e loe in with password tatteru to read the details
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosed uesterdau that several inrorqal bzt direct contacts have been qade with political representatives or the viet cone in qoscow e loe in with password batteru to read the details
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosed uesterdau that several inrormal bzt direct contacts have been made with political representatives or the viet cone in moscow e loe in with password batteru to read the details
user@ubuntu:~/Desktop$ php sadf.php 
it was disclosed yesterday that several inrormal bzt direct contacts have been made with political representatives or the viet cone in moscow e loe in with password battery to read the details
```

Didn't need to decrypt further :-)
A little weird that the password was used before...