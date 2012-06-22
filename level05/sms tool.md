#### Level 05 - SMS tool

The form:
```html
<form id="challenge" method="post" action="/hacmegame/challenges/ChallengeS28.html">
    <h3>Send SMS</h3>

    <!--  } else if(request.getParameter("sms").length()>160 &amp;&amp; !request.getParameter("admin").equals("true")) {  -->
    <span id="*.errors" class="error">The SMS message is too long.</span>
    <p>Free SMS messages left : 0</p>
    <p>Recipient's number: <br><input id="number" name="number" type="text" value="12345678" maxlength="8"/></p>
    <p>
        Message:<br />
        <textarea id="sms" name="sms" onkeyup="displayCharLenght('sms', 'smsLen', 160)" onfocus="displayCharLenght('sms', 'smsLen', 160)"></textarea><br />

        SMS length: <b><span id="smsLen">0</span></b>/160<br />
    </p>
    <p><input type="submit" class="submit" value="Send SMS" /></p>
    
</form>
```

The comment suggests that to become an admin there should be an input named "admin" which needs to be sat.

So simply add `<input name="admin" value="true" />` to the form.

Then change the value of the displayCharlenght() function:
```html
onkeyup="displayCharLenght('sms', 'smsLen', 9999999)" onfocus="displayCharLenght('sms', 'smsLen', 9999)"
```

(I dont think this step is neccessary, since you are an admin, but I did it.)

Enter a large text on the form and submit.