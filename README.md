# ECMAScript 6
### Constants

**`const` ensures that the value of the variable never changes**
##### Example 1
#
```JavaScript
const PI = 3.141593;
console.log(PI); // 3.141593
```
### Scoping
**At runtime, any variable that is declared using `var` keyword will be hoisted up to the top of the executing context.**

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
**With the `let` keyword, this is now different. `let` keyword not going to hoisted the variable.**
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
**The following example demonstrates how the let operator works inside `for`-loops:**
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