- [Day 03](#day-03)
	- [DOM(Document Object Model)-Day 3](#domdocument-object-model-day-3)
		- [Event Listeners](#event-listeners)
			- [Click](#click)
			- [Double Click](#double-click)
			- [Mouse enter](#mouse-enter)
		- [Getting value from an input element](#getting-value-from-an-input-element)
		- [input value](#input-value)
			- [input event and change](#input-event-and-change)
			- [blur event](#blur-event)
			- [keypress, keydow and keyup](#keypress-keydow-and-keyup)
	- [Exercises](#exercises)

# Day 03

## DOM(Document Object Model)-Day 3

### Event Listeners
An event listener is a procedure in JavaScript that waits for an event to occur. The simple example of an event is a user clicking the mouse or pressing a key on the keyboard.
The JavaScript function addEventListener() takes the event to listen for and a second parameter that will be called whenever the given event occurs. A single element can have any number of additional event handlers added to it without replacing any already present ones.
Common HTML events:onclick, onchange, onmouseover, onmouseout, onkeydown, onkeyup, onload.
```js
selectedElement.addEventListener('eventlistner', function(e) {
  // the activity you want to occur after the event will be in here
})
// or

selectedElement.addEventListener('eventlistner', e => {
  // the activity you want to occur after the event will be in here
})
```
#### Click

Click event handlers are super-common and used all over the place… popups, modals, buttons, animations. Pretty much any time when clicking an element does something on a web page, a click event handler has been used to make the something happen.

##### How does it work?
We won’t get too technical here… we’re just going to look at this from a high level.

- Our JavaScript code tells the browser to pay particular attention to an element (or elements) we specify and listen out for users clicking on that element.

- We can specify the element by using its ID or with a class name if we want to specify multiple elements. We can even specify by element type (e.g. all <button> elements).
  
- When the browser detects a user has clicked on the specified element our JavaScript code tells it to do something. That “something” is stored within a function.
```js
addEventListener('click', (event) => {});

onclick = (event) => { };
```
 #### Double Click
 The dblclick event fires when a pointing device button (such as a mouse's primary button) is double-clicked; that is, when it's rapidly clicked twice on a single element within a very short span of time.

dblclick fires after two click events (and by extension, after two pairs of mousedown and mouseup events).
  
 ```js
addEventListener('dblclick', (event) => {});

ondblclick = (event) => { };
```
 #### Mouse enter
The mouseenter event is fired at an Element when a pointing device (usually a mouse) is initially moved so that its hotspot is within the element at which the event was fired.
  ```js
addEventListener('mouseenter', (event) => {});

onmouseenter = (event) => { };
```
  
  

List of events
Listed here are a few typical HTML events:
- click - when the element clicked
- dblclick - when the element double clicked
- mouseenter - when the mouse point enter to the element
- mouseleave - when the mouse pointer leave the element
- mousemove - when the mouse pointer move on the element
- mouseover - when the mouse pointer move on the element
- mouseout -when the mouse pointer out from the element
- input -when value enter to input field
- change -when value change on input field
- blur -when the element is not focused
- keydown - when a key is down
- keyup - when a key is up
- keypress - when we press any key
- onload - when the browser has finished loading a page
  
### Getting value from an input element

We usually fill forms and forms accept data. Form fields are created using input HTML element. Let us build a small application which allow us to calculate body mas index of a person using two input fields, one button and one p tag.

### input value

```html
<!DOCTYPE html>
<html>
  <head>
  <title>Welcome to Geekster course of Advance JavaScript</title>
  </head>

  <body>
    <h1>Body Mass Index Calculator</h1>

    <input type="text" id="mass" placeholder="Mass in Kilogram" />
    <input type="text" id="height" placeholder="Height in meters" />
    <button>Calculate BMI</button>

    <script>
      const mass = document.querySelector('#mass')
      const height = document.querySelector('#height')
      const button = document.querySelector('button')

      let bmi
      button.addEventListener('click', () => {
        bmi = mass.value / height.value ** 2
        alert(`your bmi is ${bmi.toFixed(2)}`)
        console.log(bmi)
      })
    </script>
  </body>
</html>
```
#### input event and change
 The change event triggers when the element has finished changing.

For text inputs that means that the event occurs when it loses focus.

For instance, while we are typing in the text field below – there’s no event. But when we move the focus somewhere else, for instance, click on a button – there will be a change event:
![](./img-1/change.png)
  
In contrast to _input_ or _change_, the _blur_ event occur when the input field is not on focus.

```js
<!DOCTYPE html>
<html>

<head>
    <title>Welcome to Geekster course of Advance JavaScript</title>
</head>

<body>
    <h1>Giving feedback using blur event</h1>

    <input type="text" id="mass" placeholder="say something" />
    <p></p>

    <script>
        const input = document.querySelector('input')
        const p = document.querySelector('p')

        input.addEventListener('blur', (e) => {
            p.textContent = 'Field is required'
            p.style.color = 'red'

        })
    </script>
</body>

</html>
```

#### keypress, keydow and keyup
  We can access all the key numbers of the keyboard using different event listener types. Let us use keypress and get the keyCode of each keyboard keys.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome to Geekster course of Advance JavaScript</title>
  </head>

  <body>
    <h1>Key events: Press any key</h1>

    <script>
      document.body.addEventListener('keypress', e => {
        alert(e.keyCode)
      })
    </script>
  </body>
</html>
```
You should be proud of yourself if you have read this far🎉🎉.

You are amazing, and each day brings more and more improvement.
	
Don't be afraid to put these exercises into practice to get better at the following topic.
	
## Exercises
