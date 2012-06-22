#### Level 03 - Lottery lothario

Edit the html with Firefox's Web Developer (Misc -> Edit HTML)

Find the code:
```html
<select id="tickets" onchange="return process()">
	<option value="0">0</option>
	<option value="1">1</option>
	<option value="2">2</option>
	<option value="3">3</option>
	<option value="4">4</option>
	<option value="5">5</option>
</select>
```

And change to:

```html
<select id="tickets">
	<option value="0">0</option>
	<option value="1">1</option>
	<option value="2">2</option>
	<option value="3">3</option>
	<option value="4">4</option>
	<option value="2147483647">5</option>
</select>
```

Notice we change the value and removed the JavaScript function.

Then find:
```html
<input id="num" name="num" value="5" type="hidden">
```

And change to:
```html
<input id="num" name="num" value="2147483647" type="hidden">
```

Then select 5 in the select box and hit buy. Done.