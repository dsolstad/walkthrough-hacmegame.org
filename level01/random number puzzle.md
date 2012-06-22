#### Level 01 - Random number puzzle

Here we need to get the current sum equal to the objective sum. Let's edit the html again and find:
```html
<select id="addition" name="addition">
    <option value="775">775</option>
    <option value="926">926</option>
    <option value="205">205</option>
</select>
```

For me the objective sum is 2282. So change the html to:
```html
<select id="addition" name="addition">
    <option value="2282">2282</option>
    <option value="926">926</option>
    <option value="205">205</option>
</select>
```

You also need to change the subtraction form or else it will subtract 570 from it, and we end up with 2282 - 570. 
So we simply make the first value to 0.
```html
<select id="subtraction" name="subtraction">
    <option value="0">0</option>
    <option value="177">177</option>
    <option value="891">891</option>
</select>
```

Hit submit and you are done.