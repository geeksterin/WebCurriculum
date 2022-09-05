- [Day 1](#day-1)
	- [Document Object Model (DOM) - Day 1](#document-object-model-dom---day-1)
		- [Getting Element](#getting-element)
			- [Getting elements by tag name](#getting-elements-by-tag-name)
			- [Getting elements by class name](#getting-elements-by-class-name)
			- [Getting an element by id](#getting-an-element-by-id)
			- [Getting elements by using querySelector methods](#getting-elements-by-using-queryselector-methods)
		- [Adding attribute](#adding-attribute)
			- [Adding attribute using setAttribute](#adding-attribute-using-setattribute)
			- [Adding attribute without setAttribute](#adding-attribute-without-setattribute)
			- [Adding class using classList](#adding-class-using-classlist)
			- [Removing class using remove](#removing-class-using-remove)
		- [Adding Text to HTML element](#adding-text-to-html-element)
			- [Adding Text content using textContent](#adding-text-content-using-textcontent)
			- [Adding Text Content using innerHTML](#adding-text-content-using-innerhtml)
				- [Text Content](#text-content)
				- [Inner HTML](#inner-html)
		- [Adding style](#adding-style)
			- [Adding Style Color](#adding-style-color)
			- [Adding Style Background Color](#adding-style-background-color)
			- [Adding Style Font Size](#adding-style-font-size)
	- [Exercises](#exercises)
	
  # Day 1

## Document Object Model (DOM) - Day 1
An application programming interface (API) for HTML and XML documents is called the Document Object Model (DOM). It specifies how a document is accessed and handled, as well as its logical structure.
When a web page is loaded, the browser creates a Document Object Model of the page.
### Getting Element

We can access already created element or elements using JavaScript. To access or get elements we use different methods. The code below has four _h1_ elements. Let us see the different methods to access the _h1_ elements.

```html
<!DOCTYPE html>
  <html lang="en">
    <head>
      <title>Document Object Model</title>
    </head>
    <body>

     <h1 class='title' id='first-title'>First Title</h1>
     <h1 class='title' id='second-title'>Second Title</h1>
     <h1 class='title' id='third-title'>Third Title</h1>
     <h1></h1>

    </body>
  </html>
```

#### Getting elements by tag name

The Element. getElementsByTagName() method returns a live HTMLCollection of elements with the given tag name. All descendants of the specified element are searched, but not the element itself. The returned list is live, which means it updates itself with the DOM tree automatically.

```js
// syntax
document.getElementsByTagName('tagname')
```

```js
const allTitles = document.getElementsByTagName('h1')

console.log(allTitles) //HTMLCollections
console.log(allTitles.length) // 4

for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i]) // prints each elements in the HTMLCollection
}
```
#### Getting elements by class name
Can we get element by class name?
The JavaScript getElementsByClassName is used to get all the elements that belong to a particular class. When the JavaScript get element by class name method is called on the document object, it searches the complete document, including the root nodes, and returns an array containing all the elements
```js
//syntax
document.getElementsByClassName('classname')
```

```js
const allTitles = document.getElementsByClassName('title')

console.log(allTitles) //HTMLCollections
console.log(allTitles.length) // 4

for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i]) // prints each elements in the HTMLCollection
}
```
#### Getting an element by id

The element with the supplied value is returned by the getElementById() function. If the element is absent, the getElementById() function returns null. One of the most often used methods in the HTML DOM is getElementById().

```js
//syntax
document.getElementById('id')
```

```js
let firstTitle = document.getElementById('first-title')
console.log(firstTitle) // <h1>First Title</h1>
```
#### Getting elements by using querySelector methods
The Document method querySelector() returns the first Element within the document that matches the specified selector, or group of selectors. If no matches are found, null is returned.
can be used to select HTML element by its tag name, id or class. If the tag name is used it selects only the first element.

```js
let firstTitle = document.querySelector('h1') // select the first available h1 element
let firstTitle = document.querySelector('#first-title') // select id with first-title
let firstTitle = document.querySelector('.title') // select the first available element with class title
```

**_querySelectorAll_**: can be used to select html elements by its tag name or class. It returns a nodeList which is an array like object which supports array methods. We can use **_for loop_** or **_forEach_** to loop through each nodeList elements.

```js
const allTitles = document.querySelectorAll('h1') # selects all the available h1 elements in the page

console.log(allTitles.length) // 4
for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i])
}

allTitles.forEach(title => console.log(title))
const allTitles = document.querySelectorAll('.title') // the same goes for selecting using class
```
### Adding attribute
HTML's opening tag now includes an attribute that adds further details about the element. Id, class, src, style, href, disabled, title, and alt are typical HTML attributes. For the fourth title, let's add an id and a class.

```js
const titles = document.querySelectorAll('h1')
titles[3].className = 'title'
titles[3].id = 'fourth-title'
```
#### Adding attribute using setAttribute
Sets the value of an attribute on the specified element. If the attribute already exists, the value is updated; otherwise a new attribute is added with the specified name and value.

To get the current value of an attribute, use getAttribute(); to remove an attribute, call removeAttribute().
Let's add class and id attribute for the fourth title.

```js
const titles = document.querySelectorAll('h1')
titles[3].setAttribute('class', 'title')
titles[3].setAttribute('id', 'fourth-title')
```
#### Adding attribute without setAttribute
We can use normal object setting method to set an attribute but this can not work for all elements. Some attributes are DOM object property and they can be set directly. For instance id and class

```js
//another way to setting an attribute
titles[3].className = 'title'
titles[3].id = 'fourth-title'
```
#### Adding class using classList

The class list method is a good method to append additional class. It does not override the original class if a class exists rather it adds additional class for the element.

```js
//another way to setting an attribute: append the class, doesn't over ride
titles[3].classList.add('title', 'header-title')
```

#### Removing class using remove

Similar to adding we can also remove class from an element. We can remove a specific class from an element.

```js
//another way to setting an attribute: append the class, doesn't over ride
titles[3].classList.remove('title', 'header-title')
```

### Adding Text to HTML element

An HTML is a build block of an opening tag, a closing tag and a text content. We can add a text content using the property _textContent_ or \*innerHTML.

#### Adding Text content using textContent

The _textContent_ property is used to add text to an HTML element.

```js
const titles = document.querySelectorAll('h1')
titles[3].textContent = 'Fourth Title'
```

#### Adding Text Content using innerHTML

Most people get confused between _textContent_ and _innerHTML_. _textContent_ is meant to add text to an HTML element, however innerHTML can add a text or HTML element or elements as a child.

##### Text Content

We assign *textContent* HTML object property to a text

```js
const titles = document.querySelectorAll('h1')
titles[3].textContent = 'Fourth Title'
```
##### Inner HTML

We use innerHTML property when we like to replace or a completely new children content to a parent element.
It value we assign is going to be a string of HTML elements.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Geekster course of Advance Javascript</title>
</head>
<body>
    <div class="wrapper">
        <h1>Hello Geeks!</h1>
        <h2>Keep calm and code with Geekster</h2>
        <ul></ul>
    </div>
</body>
</html>
<script>
    const lists = `
            <li>list item-1</li>
            <li>list item-2</li>
            <li>list item-3</li>
            <li>list item-4</li>
            <li>list item-5</li>
           `
  const ul = document.querySelector('ul')
  ul.innerHTML = lists
    </script>
  </body>
</html>
```
The innerHTML property can allow us also to remove all the children of a parent element. Instead of using removeChild() I would recommend the following method.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Geekster course of Advance Javascript</title>
</head>
<body>
    <div class="wrapper">
        <h1>Hello Geeks!</h1>
        <h2>Keep calm and code with Geekster</h2>
        <ul>
            <li>list item-1</li>
            <li>list item-2</li>
            <li>list item-3</li>
            <li>list item-4</li>
            <li>list item-5</li>
        </ul>
    </div>
</body>
</html>
<script>
    const ul = document.querySelector('ul')
    ul.innerHTML = ''
      </script> 
  </body>
</html>
```
### Adding style

#### Adding Style Color

Let us add some style to our titles. If the element has even index we give it green color else red.
Setting the style of an HTML element, can be done with the style attribute.

Let us add some style to our titles. If the element has even index we give it green color else red.

```js
const titles = document.querySelectorAll('h1')
titles.forEach((title, i) => {
  title.style.fontSize = '24px' // all titles will have 24px font size
  if (i % 2 === 0) {
    title.style.color = 'green'
  } else {
    title.style.color = 'red'
  }
})
```

#### Adding Style Background Color

Let us add some style to our titles. If the element has even index we give it green color else red.

```js
const titles = document.querySelectorAll('h1')
titles.forEach((title, i) => {
  title.style.fontSize = '24px' // all titles will have 24px font size
  if (i % 2 === 0) {
    title.style.backgroundColor = 'green'
  } else {
    title.style.backgroundColor = 'red'
  }
})
```

#### Adding Style Font Size

Let us add some style to our titles. If the element has even index we give it 20px else 30px

```js
const titles = document.querySelectorAll('h1')
titles.forEach((title, i) => {
  title.style.fontSize = '24px' // all titles will have 24px font size
  if (i % 2 === 0) {
    title.style.fontSize = '20px'
  } else {
    title.style.fontSize = '30px'
  }
})
```
## Exercises
