#  Object Oriented Programming concepts and their use in JavaScript.
<hr>

 <section class="post-full-content" style="font-size:large;font-family: Lucida Console;">
                    <div class="post-and-sidebar">
                        <section class="post-content ">
                            
<p>JavaScript is not a class-based object-oriented language. But it still has ways of using object oriented programming (OOP).</p>
<p>In this tutorial, I'll explain OOP and show you how to use it.</p>
<p>According to <span href="#">Wikipedia</span>, class-based programming is</p>
<blockquote>
<p>a style of Object-oriented programming (OOP) in which inheritance occurs via defining classes of objects, instead of inheritance occurring via the objects alone</p>
</blockquote>
<p>The most popular model of OOP is class-based.</p>
<p>But as I mentioned, JavaScript isn't a classed-based langauge – it's is a prototype-based langauge.</p>
<p>According to Mozilla's documentaion:</p>
<blockquote>
<p>A prototype-based language has the notion of a prototypical object, an object used as a template from which to get the initial properties for a new object.</p>
</blockquote>
<p>Take a look at this code:</p>
<pre><code class="language-javascript">let names = {
    fname: "Dillion",
    lname: "Megida"
}
console.log(names.fname);
console.log(names.hasOwnProperty("mname"));
// Expected Output
// Dillion
// false
</code></pre>
<p>The object variable <code>names</code> has only two properties -  <code>fname</code> and <code>lname</code> . No methods at all.</p>
<p>So where does <code>hasOwnProperty</code> come from?</p>
<p>Well, it comes from the <code>Object</code> prototype.</p>
<p>Try logging the contents of the variable to the console:</p>
<pre><code class="language-js">console.log(names);
</code></pre>
<p>When you expand the results in the console, you'll get this:</p>
<!--kg-card-end: markdown--><figure class="kg-card kg-image-card kg-card-hascaption"><img src="https://www.freecodecamp.org/news/content/images/2020/02/1-1.png" class="kg-image" alt="1-1" width="600" height="400" loading="lazy"><figcaption>console.log(names)</figcaption></figure><!--kg-card-begin: markdown--><p>Notice the last property - <code>__proto__</code>? Try expanding it:</p>
<!--kg-card-end: markdown--><figure class="kg-card kg-image-card kg-card-hascaption"><img src="https://www.freecodecamp.org/news/content/images/2020/02/2-1.png" class="kg-image" alt="2-1" width="600" height="400" loading="lazy"><figcaption>The __proto__ property of names</figcaption></figure><!--kg-card-begin: markdown--><p>You'll see a set of properties under the  <code>Object</code> constructor. All these properties are coming from the global <code>Object</code> prototype. If you look closely, you'll also notice our hidden <code>hasOwnProperty</code> .</p>
<p>In other words, all objects have access to the <code>Object</code>'s prototype. They do not possess these properties, but are granted access to the properties in the prototype.</p>
<h2 id="the__proto__property">The <code>__proto__</code> property</h2>
<p>This points to the object which is used as a prototype.</p>
<p>This is the property on every object that gives it access to the <code>Object prototype</code> property.</p>
<p>Every object has this property by default, which refers to the <code>Object Protoype</code> except when configured otherwise (that is, when the object's <code>__proto__</code> is pointed to another prototype).</p>
<h3 id="modifyingthe__proto__property">Modifying the <code>__proto__</code> property</h3>
<p>This property can be modified by explicitly stating that it should refer to another prototype. The following methods are used to achieve this:</p>
<h3 id="objectcreate"><code>Object.create()</code></h3>
<pre><code class="language-javascript">function DogObject(name, age) {
    let dog = Object.create(constructorObject);
    dog.name = name;
    dog.age = age;
    return dog;
}
let constructorObject = {
    speak: function(){
        return "I am a dog"
    }
}
let bingo = DogObject("Bingo", 54);
console.log(bingo);
</code></pre>
<p>In the console, this is what you'd have:</p>
<!--kg-card-end: markdown--><figure class="kg-card kg-image-card kg-card-hascaption"><img src="https://www.freecodecamp.org/news/content/images/2020/02/3-1.png" class="kg-image" alt="3-1" width="600" height="400" loading="lazy"><figcaption>console.log(bingo)</figcaption></figure><!--kg-card-begin: markdown--><p>Notice the <code>__proto__</code> property and the <code>speak</code> method?</p>
<p><code>Object.create</code> uses the argument passed to it to become the prototype.</p>
<h3 id="newkeyword"><code>new</code> keyword</h3>
<pre><code class="language-javascript">function DogObject(name, age) {
    this.name = name;
    this.age = age;
}
DogObject.prototype.speak = function() {
    return "I am a dog";
}
let john = new DogObject("John", 45);
</code></pre>
<p><code>john</code>'s <code>__proto__</code> property is directed to <code>DogObject</code>'s prototype. But remember, <code>DogObject</code>'s prototype is an object (<strong>key and value pair</strong>), hence it also has a <code>__proto__</code> property which refers to the global <code>Object</code> protoype.</p>
<p>This technique is referred to as <strong>PROTOTYPE CHAINING</strong>.</p>
<p><strong>Note that:</strong> the <code>new</code> keyword approach does the same thing as <code>Object.create()</code> but only makes it easier as it does some things automatically for you.</p>
<h3 id="andso">And so...</h3>
<p>Every object in Javascript has access to the <code>Object</code>'s prototype by default. If configured to use another prototype, say <code>prototype2</code>, then <code>prototype2</code> would also have access to the Object's prototype by default, and so on.</p>
<h3 id="objectfunctioncombination">Object + Function Combination</h3>
<p>You are probably confused by the fact that <code>DogObject</code> is a function (<code>function DogObject(){}</code>) and it has properties accessed with a <strong>dot notation</strong>. This is referred to as a <strong>function object combination</strong>.</p>
<p>When functions are declared, by default they are given a lot of properties attached to it. Remember that functions are also objects in JavaScript data types.</p>
<h2 id="nowclass">Now, Class</h2>
<p>JavaScript introduced the <code>class</code> keyword in ECMAScript 2015. It makes JavaScript seem like an OOP language. But it is just syntatic sugar over the existing prototyping technique. It continues its prototyping in the background but makes the outer body look like OOP. We'll now look at how that's possible.</p>
<p>The following example is a general usage of a <code>class</code> in JavaScript:</p>
<pre><code class="language-javascript">class Animals {
    constructor(name, specie) {
        this.name = name;
        this.specie = specie;
    }
    sing() {
        return `${this.name} can sing`;
    }
    dance() {
        return `${this.name} can dance`;
    }
}
let bingo = new Animals("Bingo", "Hairy");
console.log(bingo);
</code></pre>
<p>This is the result in the console:</p>
<!--kg-card-end: markdown--><figure class="kg-card kg-image-card kg-card-hascaption"><img src="https://www.freecodecamp.org/news/content/images/2020/02/5-1.png" class="kg-image" alt="5-1" width="600" height="400" loading="lazy"><figcaption>console.log(bingo)</figcaption></figure><!--kg-card-begin: markdown--><p>The <code>__proto__</code> references the <code>Animals</code> prototype (which in turn references the <code>Object</code> prototype).</p>
<p>From this, we can see that the constructor defines the major features while everything outside the constructor (<code>sing()</code> and <code>dance()</code>) are the bonus features (<strong>prototypes</strong>).</p>
<p>In the background, using the <code>new</code> keyword approach, the above translates to:</p>
<pre><code class="language-javascript">function Animals(name, specie) {
    this.name = name;
    this.specie = specie;
}
Animals.prototype.sing = function(){
    return `${this.name} can sing`;
}
Animals.prototype.dance = function() {
    return `${this.name} can dance`;
}
let Bingo = new Animals("Bingo", "Hairy");
</code></pre>
<h2 id="subclassing">Subclassing</h2>
<p>This is a feature in OOP where a class inherits features from a parent class but possesses extra features which the parent doesn't.</p>
<p>The idea here is, for example, say you want to create a <em>cats</em> class. Instead of creating the class from scratch - stating the <em>name</em>, <em>age</em> and <em>species</em> property afresh, you'd inherit those properties from the parent <em>animals</em> class.</p>
<p>This <em>cats</em> class can then have extra properties like <em>color of whiskers</em>.</p>
<p>Let's see how subclasses are done with <code>class</code>.</p>
<p>Here, we need a parent which the subclass inherits from. Examine the following code:</p>
<pre><code class="language-js">class Animals {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    sing() {
        return `${this.name} can sing`;
    }
    dance() {
        return `${this.name} can dance`;
    }
} 
class Cats extends Animals {
    constructor(name, age, whiskerColor) {
        super(name, age);
        this.whiskerColor = whiskerColor;
    }
    whiskers() {
        return `I have ${this.whiskerColor} whiskers`;
    }
}
let clara = new Cats("Clara", 33, "indigo");
</code></pre>
<p>With the above, we get the following outputs:</p>
<pre><code class="language-js">console.log(clara.sing());
console.log(clara.whiskers());
// Expected Output
// "Clara can sing"
// "I have indigo whiskers"
</code></pre>
<p>When you log the contents of clara out in the console, we have:</p>
<!--kg-card-end: markdown--><figure class="kg-card kg-image-card kg-card-hascaption"><img src="https://www.freecodecamp.org/news/content/images/2020/02/6-1.png" class="kg-image" alt="6-1" width="600" height="400" loading="lazy"><figcaption>console.log(clara)</figcaption></figure><!--kg-card-begin: markdown--><p>You'll notice that <code>clara</code> has a <code>__proto__</code> property which references the constructor <code>Cats</code> and gets access to the <code>whiskers()</code> method. This <code>__proto__</code> property also has a <code>__proto__</code> property which references the constructor <code>Animals</code> thereby getting access to <code>sing()</code> and <code>dance()</code>. <code>name</code> and <code>age</code> are properties that exist on every object created from this.</p>
<p>Using the <code>Object.create</code> method approach, the above translates to:</p>
<pre><code class="language-js">function Animals(name, age) {
    let newAnimal = Object.create(animalConstructor);
    newAnimal.name = name;
    newAnimal.age = age;
    return newAnimal;
}
let animalConstructor = {
    sing: function() {
        return `${this.name} can sing`;
    },
    dance: function() {
        return `${this.name} can dance`;
    }
}
function Cats(name, age, whiskerColor) {
    let newCat = Animals(name, age);
    Object.setPrototypeOf(newCat, catConstructor);
    newCat.whiskerColor = whiskerColor;
    return newCat;
}
let catConstructor = {
    whiskers() {
        return `I have ${this.whiskerColor} whiskers`;
    }
}
Object.setPrototypeOf(catConstructor, animalConstructor);
const clara = Cats("Clara", 33, "purple");
clara.sing();
clara.whiskers();
// Expected Output
// "Clara can sing"
// "I have purple whiskers"
</code></pre>
<p><code>Object.setPrototypeOf</code> is a method which takes in two arguments - the object (first argument) and the desired prototype (second argument).</p>
<p>From the above, the <code>Animals</code> function returns an object with the <code>animalConstructor</code> as prototype. The <code>Cats</code> function returns an object with <code>catConstructor</code> as it's prototype. <code>catConstructor</code> on the other hand, is given a prototype of <code>animalConstructor</code>.</p>
<p>Therefore, ordinary animals only have access to the <code>animalConstructor</code> but cats have access to the <code>catConstructor</code> and the <code>animalConstructor</code>.</p>
<h2 id="wrappingup">Wrapping Up</h2>
<p>JavaScript leverages its prototype nature to welcome OOP developers to its ecosystem. It also provides easy ways to creating prototypes and organize related data.</p>
<p>True OOP languages do not perform prototyping in the background - just take note of that.</p>











<br>
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

<br>
<hr>

# Exercise 4

```js
const obj = {
  firstName: "John",
  lastName: "Doe",
  // create a getter fullName to return John Doe
};

console.log(obj.fullName);
```

<h4>Create a getter ```fullName``` to return Full name (John Doe) in console. </h4>
<br>
<hr>

# Exercise 5

```js
var person = {
    firstName : "John",
    lastName : "Smith",
    age : 23
};

function printFullName()
{
   //console Fullname (eg., Tony Stark)
}

function printDetails()
{
   // console Name and age (eg., Tony is 21 years old)
}


// Create boundcopies using bind()

var boundPrintFullName;
var boundPrintDetails;


boundPrintFullName();
boundPrintDetails();

```
<h4>Create the bound copies of printFullName and printDetails using bind() and return the Full name in printFullName() , person name and age in printDetails()</h4>


