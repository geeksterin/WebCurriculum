- [Day2](#day-2)
  - [DOM(Document Object Model)-Day 2](#domdocument-object-model-day-2)
    - [Creating an Element](#creating-an-element)
    - [Creating elements](#creating-elements)
    - [Appending child to a parent element](#appending-child-to-a-parent-element)
    - [Removing a child element from a parent node](#removing-a-child-element-from-a-parent-node)
  - [Exercises](#exercises)

# Day 2

## DOM(Document Object Model)-Day 2

### Creating an Element
In an HTML document, the document.createElement() method creates the HTML element

```js
// syntax
const element = document.createElement(htmlTag);
```
```html
<!DOCTYPE html>
<html>
<head>
    <title>Welcome to Geekster course of Advance JavaScript</title>
</head>
<body>
    <script>
        let title = document.createElement('h1')
        title.className = 'title'
        title.style.fontSize = '24px'
        title.textContent = 'Creating HTML element DOM Day 2'
        console.log(title)
    </script>
</body>
</html>
```
### Creating elements

To create multiple elements we should use loop. Using loop we can create as many HTML elements as we want.
After we create the element we can assign value to the different properties of the HTML object.

```html
<!DOCTYPE html>
<html>

<head>
    <title>Welcome to Geekster course of Advance JavaScript</title>
</head>

<body>

    <script>
        let title
        for (let i = 0; i < 3; i++) {
            title = document.createElement('h1')
            title.className = 'title'
            title.style.fontSize = '24px'
            title.textContent = i
            console.log(title)
        }
    </script>
</body>

</html>
```
### Appending child to a parent element

The appendChild() is a method of the Node interface. The appendChild() method allows you to add a node to the end of the list of child nodes of a specified parent node.
```html
<!DOCTYPE html>
<html>

<head>
    <title>Welcome to Geekster course of Advance JavaScript</title>
</head>

<body>
    <script>
        // creating multiple elements and appending to parent element
        let title
        for (let i = 0; i < 3; i++) {
            title = document.createElement('h1')
            title.className = 'title'
            title.style.fontSize = '24px'
            title.textContent = i
            document.body.appendChild(title)
        }
    </script>
</body>
</html>
```
### Removing a child element from a parent node
After creating an HTML, we may want to remove element or elements and we can use the *removeChild()* method.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>Document Object Model:30 Days Of JavaScript</title>
</head>

<body>
    <h1>Removing child Node</h1>
    <ul>
       <li>list-1</li>
       <li>list-2</li>
       <li>list-3</li>
       <li>list-4</li>
       <li>list-5</li>
    </ul>

    <script>
        const ul = document.querySelector('ul')
        const lists = document.querySelectorAll('li')
        for (const list of lists) {
            ul.removeChild(list)
        }
    </script>
</body>

</html>
```

If you've made it this far, congratulate yourself🎉🎉.

You are incredible, and you are becoming better every day. 

Now that you were aware of how to remove a DOM element when it was no longer required. You gained knowledge of DOM and can now create and develop applications.

## Exercises
