#### Level 05 - Breaking the barrier

In the source we see that a javascript file is included with the name:
```
['\x6A\x73\x2F\x74\x6F\x70\x73\x65\x63\x72\x65\x74\x73\x75\x70\x65\x72\x64\x75\x70\x65\x72\x2E\x6A\x73'][0x0]
```

Let us find out the name in plain text...

In a new tab enter:
```javascript
javascript:alert("['\x6A\x73\x2F\x74\x6F\x70\x73\x65\x63\x72\x65\x74\x73\x75\x70\x65\x72\x64\x75\x70\x65\x72\x2E\x6A\x73'][0x0]");
```

Result: `['js/topsecretsuperduper.js'][0x0]`

Here it is: http://www.hacmegame.org/hacmegame/js/topsecretsuperduper.js

Now take a look at this script:
```javascript
function validate_form(thisform) {
	with (thisform) {
		if (validate_required(inputfield, "input_error") == false) {
			inputfield.focus();
			return false;
		} else {
			insert();
			return true;
		}
	}
}

function insert() {
	var objForm = document.getElementById("val");
	var objInput = document.createElement("input");
	objInput.setAttribute('type','hidden');
	objInput.setAttribute('name','val');
	objInput.setAttribute('value','0fc826d06103c0e423e9bac849b36e91c05506a5708dd8b9bd1f596e1ef93c9a');
	objForm.insertBefore(objInput, objForm.firstChild);
}
```

Run that insert() command in the javascript console or in Firebug.

Now edit the HTML. Replace this:
```html
<form id="val" method="post" action="/hacmegame/challenges/ChallengeS42.html?hs=1" onsubmit="return validate_form(this);">
```

with this: 
```html
<form id="val" method="post" action="/hacmegame/challenges/ChallengeS42.html?hs=1">
```

Then write <script> in the input and then submit.