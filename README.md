# ECMAScript 6
### Constants

`const` **ensures that the value of the variable never changes. An initializer for a constant is required.**
##### Example 1
```JavaScript
const PI = 3.141593;
console.log(PI); // 3.141593
```
**This declaration creates a constant whose scope can be either global or local to the block in which it is declared.**
##### Example 2
```JavaScript
function test(){
	const a = 1;
	if(true){
		const a = 2;
		console.log(a); // 2
	}
	console.log(a); // 1
}
```
##### Example 3
```javascript
const ARR = [];
ARR.push(1);
console.log(ARR); // [1]
ARR.push(2,3,4);
console.log(ARR); // [1,2,3,4]
ARR = [1]; // TypeError: Assignment to constant variable. (Assignment to the variable throws an error)
```

### Scoping
**At runtime, any variable that is declared using** `var` **keyword will be hoisted up to the top of the executing context.**

```JavaScript
function test(){
	var a = true;
	if(a === true){
		var b = true;
	}
	console.log(a); // true
	console.log(b); // true
}
test();
```
**With the** `let` **keyword, this is now different.** `let` **keyword not going to hoisted the variable.**
```JavaScript
function test(){
	var a = true;
	if(a === true){
		let b = true;
	}
	console.log(a); // true
	console.log(b); // ReferenceError : b is not defined
}
test();
```
**The following example demonstrates how the let operator works inside** `for`**-loops:**
```JavaScript
var cart = [
    {
		id : 1,
		food_name : 'Fried Rice Chicken',
		price : 520
	},
	{
		id : 2,
		food_name : 'Masala Fried Rice',
		price : 520
	}
];
for(let i = 0; i < cart.length; i++){
	console.log('Food Name: ' + cart[i].food_name + ', Price : ' + cart[i].price);
}
Output:
// Food Name: Fried Rice Chicken, Price : 520
// Food Name: Masala Fried Rice, Price : 520
```