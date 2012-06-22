#### Level 07 - Farm Automagical Systems INC

Looks like another sql injection case, and we need to keep in mind to escape quotes.

The standard injection didn't work in the input fields: `\' or \'1\'=\'1`

Need to think of something else... Hmm, a cookie named sessionID.
Tried to change the value. And I got the error message: "Illegal session id." from the site.

I bought some hints, which gave me nothing at all:

* The login fields them self are secured.
* How does the system identify users?
* A simple injection is all that's needed
* What rhymes with rookie (except your name)?

Then I tried to use the injection on the cookie, and it worked!

So just change the value of the cookie to: `\' or \'1\'=\'1`