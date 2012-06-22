#### Level 4: Ship some pets far out

Open Firebug. Inspect the HTML, and you will find that there are some JavaScript files being included.
Let's take a look at those.

```javascript
function validatePetshopAddress(){
    if (document.getElementById('name').value == "") {
        msg("input_error", "error", "Please enter your name");
        return false;
    } else if (zipCodeToCity() === false) {
        msg("input_error", "error", "We don't deliver here");
        return false;
    } else {
        insert();
        return true;
    }
}

function insert() {
    var objForm = document.getElementById("val");
    var objInput = document.createElement("input");
    objInput.setAttribute('type','hidden');
    objInput.setAttribute('name','val');
    objInput.setAttribute('value','af883cadbe96b8a16ac8340e264b9f7526b9e5a9e2f249e4d4c641934aae05b5');
    objForm.insertBefore(objInput, objForm.firstChild);
}
```

So what is basicly going on here is that if the address is valid, the insert() function is executed, and the insert function creates an hidden input with a value. So let's take a short cut and just create that hidden input manualy. 
Just copy whats inside insert() (between the braces {}) and paste in inside the JavaScript console in your browser.

Now changed the HTML...

Remove the onsubmit:
```html
<form id="val" method="post" action="/hacmegame/challenges/ChallengeS11.html" onsubmit="return validatePetshopAddress()">
```

It should loook like this:
```html
<form id="val" method="post" action="/hacmegame/challenges/ChallengeS11.html">
```

Then find:
```html
<select onchange="return zipCodeToCity()" id="zipcode" name="zipcode">
    <option value="0"> </option>
    <option value="7003">7003</option>
    <option value="7007">7007</option>
    <option value="7056">7056</option>
    <option value="7092">7092</option>
    <option value="7080">7080</option>
    <option value="7082">7082</option>
    <option value="7098">7098</option>
</select>
```

Remove the onchange and add another <option> to it:
```html
<select id="zipcode" name="zipcode">
    <option value="0"> </option>
    <option value="7003">7003</option>
    <option value="7007">7007</option>
    <option value="7056">7056</option>
    <option value="7092">7092</option>
    <option value="7080">7080</option>
    <option value="7082">7082</option>
    <option value="7098">7098</option>
    <option value="1337">1337</option>
</select>
```

Now we need to make the city input writeable:

Replace:
```html
<input name="city" id="city" size="15" readonly="true" type="text">
```

with:
```html
<input name="city" id="city" size="15" type="text">
```

Select 99 "real midget sheeps", write a random name, select 1337 as the ZIP code, and write something random for city. Hit the submit button and win!