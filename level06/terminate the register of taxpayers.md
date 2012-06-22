#### Level 06 - Terminate the register of taxpayers

The form runs the JavaScript function ff32() when submitted:
```html
<form id="challenge" method="post" action="/hacmegame/challenges/ChallengeS14.html" onsubmit="return ff32();">
```

Remove the onsubmit so it looks like this:
```html
<form id="challenge" method="post" action="/hacmegame/challenges/ChallengeS14.html">
```

The ff32() function are inluded at the header of the html:
```html
<script type="text/javascript" src="/hacmegame/js/taxsearch.js"></script>
```

Let's take a look at the function:
```javascript
function ff32(_0xfc4dx7)
{
	var _0xfc4dx8="";
	_0xfc4dx8+=ff92(document["getElementById"]("fname")["value"]);
	_0xfc4dx8+=ff12(document["getElementById"]("lname")["value"]);
	_0xfc4dx8+=ff88(document["getElementById"]("zipcode")["value"]);
	if(_0xfc4dx8!="")
	{
		alert(_0xfc4dx8);
		return false;
	}
	document["getElementById"]("verification")["value"]=SHA256(navigator["userAgent"]);
	return true;
}
```

On success it sets the value for a hidden input to be SHA256(navigator["userAgent"])

For me, navigator["userAgent"]) returns:
```Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.9.2.13) Gecko/20101206 Ubuntu/10.10 (maverick) Firefox/3.6.13```

and SHA256 of that:
```
c3d865842b6e9c392cbad25ae3e83814edc42c715013deb0599041b43405148f
```

We can set the value for the input manualy by writing this in Firebug or JavaScript console:
```
document["getElementById"]("verification")["value"]=SHA256(navigator["userAgent"]);
```

or just insert the value directly into the html.

Execute it.

Now leave the input fields blank in the form and hit the submit button. Success!