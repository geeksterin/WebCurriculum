#  Object Oriented Programming concepts and their use in JavaScript.
<hr>

# Exercise 1

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
<h4>
Create a method inside object to get the user's first
 and last name console it using the object literal.
</h4>


<br>
<hr>

# Exercise 2

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
 <h4>
	Create an object 'obj' with function() 'check' to get output as given:
My name is Robert and I am learning JS.
</h4>

<br>
<hr>

# Exercise 3

```js
var Person = function() {};

Person.prototype.initialize = function(name, age)
{
    this.name = name;
    this.age = age;
}

// TODO: create the class Teacher and a method teach

var him = new Teacher();

him.initialize("Adam", 45);
him.teach("Inheritance");
```

<h4>Create an object called Teacher derived from the Person class, and implement a method 
called teach which receives a string called subject, and prints out:
	[teacher's name] is now teaching [subject] </h4>

