#  Object Oriented Programming concepts and their use in JavaScript.

### Exercise 1

```js
//Defining object
let person = {
	first_name:'Tony',
	last_name: 'Stark',


	// create a method here 
	
	// object within object
	phone_number : {
		mobile:'1234567890'
	}
}

```
<h2>
Create a method inside object to get the user's first
 and last name console it using the object literal.
</h2>

<br>
<br>

### Exercise 2

```js
const details = {
	learningJS : false,
	learningCreate : function(){
		console.log(`My name is ${this.name} and I am ${this.check(this.learningJS) }.`)
	},
	check : // create a function here to get the expected O/P
}

// create an object 'obj' using create() method


obj.learningCreate();
 ```
 <h2>
	Create an object 'obj' with function() 'check' to get output as given:
My name is Robert and I am learning JS.
</h2>
