# Building a Responsive Grid-View

A responsive grid-view often has 12 columns, and has a total width of 100%, and will shrink and expand as you resize the browser window.

First ensure that all HTML elements have the [box-sizing](https://css-tricks.com/box-sizing/) property set to border-box. This makes sure that the padding and border are included in the total width and height of the elements.

Add the following code in your CSS:

```css
* {
    box-sizing: border-box;
}
```
**Grid:**
* The grid property in CSS is the foundation of Grid Layout. It aims at fixing issues with older layout techniques like float and inline-block, which both have issues and weren't really designed for page layout.
* Method of using a grid concept to lay out content, providing a mechanism for authors to divide available space for lay out into columns and rows using a set of predictable sizing behaviors.
* Along with the fact this method fixes the issues we encounter with older layout techniques, its main benefit is you can display a page in a way which can differ from the flow order.
* An older deprecated version of the spec is implemented in IE10/11. The current version of the spec is present in all other modern browsers (Chrome, Safari, Firefox, and Edge 16+).
* As with inline-block and inline-table, there is also inline-grid.

*More reading:*

[A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

[Grid Garden](http://cssgridgarden.com/)

[CSS Almanac: Display](https://css-tricks.com/almanac/properties/d/display/)

[The Difference Between “Block” and “Inline”](http://www.impressivewebs.com/difference-block-inline-css/)

[Learn CSS Layout: The "display" property](http://learnlayout.com/display.html)

## Floats
* Floated elements are first laid out according to the normal flow, then taken out of the normal flow and sent as far to the right or left (depending on which value is applied) of the parent element.
In other words, they go from stacking on top of each other to sitting next to each other, given that there is enough room in the parent element for each floated element to sit.
* Generally, a floated element should have an explicitly set width (unless it is a replaced element, like an image). This ensures that the float behaves as expected and helps to avoid issues in certain browsers.
* Non-positioned, non-floated, block-level elements act as if the floated element is not there, since the floated element is out of flow in relation to other block elements. When we use a floated image in a paragraph - the text in the paragraph is inline, so it flows around the floated element.
* The clear property has five values available: left, right, both, inherit, and none. Assigning a value of left says the top edge of this element must sit below any element that has the float: left property applied to it.
* A rule that I have found that works nicely for my layouts is float first. That is, in my HTML, I almost always place my floated elements first in the markup, and before any non-floated elements that my float will interact with,
such as the paragraph in the example above. Most of the time, this gives the desired result.
* Collapsing is when a parent element that contains any number of floated elements doesn’t expand to completely surround those elements in the way it would if the elements were not floated.
* There is a method that allows a parent element to clear itself of any floated elements inside it. It uses a CSS property called overflow with a value of hidden.
Note that the overflow property was not intended for this type of use, and could cause some issues such as hiding content or causing unwanted scrollbars to appear.
* **Trick: For clearing floats adding a ‘overflow:auto’ to the parent element also does the trick.**
* Note that overflow: auto doesn't clear floats — it causes the element to contain its floats by way of establishing a new block formatting context for them so that they don't intrude to other elements in the parent context.
That is what forces the parent to stretch to contain them. You can only clear a float if you add a clearing element after the float. A parent element cannot clear its floating children.
* A better way to clear floats is to add a `clearfix` class to the container element with the following styles
  ```css
  .clearfix:after {
    content: "";
    display: table;
    clear: both;
  }
  ```

**9 Rules governing Floats**

1. Floated elements are pushed to the edge of their containers, no further.

2. Any floated element will either appear next to or below a previous floated element. If the elements are floated left, the second element will appear to the right of the first. If they’re floated right, the second element will appear to the left of the first.

3. A left-floating box can't be further right than a right-floating box.

4. Floated elements can't go higher than their container’s top edge (this gets more complicated when collapsing margins are involved, see original rule).

5. A floated element can't be higher than a previous block level or floated element.

6. A floated element can't be higher than a previous line of inline elements.

7. One floated element next to another floated element can’t stick out past the edge of its container.

8. A floating box must be placed as high as possible.

9. A left-floating box must be put as far to the left as possible, a right-floating box as far to the right as possible. A higher position is preferred over one that is further to the left/right.

**Gotchas**
```html
<img src="http://lorempixum.com/200/200/">
<p>Lorem ipsum...</p>
```
```css
img {
  float: right;
  margin: 20px;
}
```

Any margin that we add to the paragraph is being applied way off to the right of the image. This is because the image is actually inside of the paragraph’s box! This is why it doesn’t increase the space between the image and the paragraph.

*More reading:*

[Everything You Never Knew About CSS Floats](http://designshack.net/articles/css/everything-you-never-knew-about-css-floats/)

[CSS Floats 101](http://alistapart.com/article/css-floats-101)

[Clearing Floats](http://www.sitepoint.com/clearing-floats-overview-different-clearfix-methods/)

## Build a responsive webpage using Grid.
![](../../images/grid.png)