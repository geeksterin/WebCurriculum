- [CSS Units](#css-units)
    - [Absolute length units](#absolute-length-units)
    - [Relative length units](#relative-length-units)
    - [Percentages](#percentages)
- [Block and inline boxes](#block-and-inline-boxes)
- [What is the CSS box model?](#what-is-the-css-box-model)
- [Parts of a box](#parts-of-a-box)
    - [The standard CSS box model](#the-standard-css-box-model)
    - [The alternative CSS box model](#the-alternative-css-box-model)
- [CSS Margins](#css-margins)
    - [Margin - Individual Sides](#margin---individual-sides)
    - [Margin - Shorthand Property](#margin---shorthand-property)
- [CSS Padding](#css-padding)
    - [Padding - Individual Sides](#padding---individual-sides)
    - [Padding - Shorthand Property](#padding---shorthand-property)
- [CSS Border Style](#css-border-style)
- [TO-DO](#to-do)
- [Resources](#resources)

# CSS Units

# Absolute length units
The following are all absolute length units — they are not relative to anything else, and are generally considered to always be the same size.

|Unit| Name | Equivalent to |
|--|---|----|
|px	|Pixels	|1px = 1/96th of 1in|

# Relative length units
Relative length units are relative to something else, perhaps the size of the parent element's font, or the size of the viewport. The benefit of using relative units is that with some careful planning you can make it so the size of text or other elements scales relative to everything else on the page. Some of the most useful units for web development are listed in the table below.

|Unit|	Relative to|
|--|---|
|em|	Font size of the parent, in the case of typographical properties like `font-size`, and font size of the element itself, in the case of other properties like `width`.
|rem|	Font size of the root element.
|vw|	1% of the viewport's width.|
|vh|	1% of the viewport's height.|

## Percentages
In a lot of cases, a percentage is treated in the same way as a length. The thing with percentages is that they are always set relative to some other value. For example, if you set an element's font-size as a percentage, it will be a percentage of the font-size of the element's parent. If you use a percentage for a width value, it will be a percentage of the width of the parent.

In the below example the two percentage-sized boxes and the two pixel-sized boxes have the same class names. The sets are 40% and 200px wide respectively.

The difference is that the second set of two boxes is inside a wrapper that is 400 pixels wide. The second 200px wide box is the same width as the first one, but the second 40% box is now 40% of 400px — a lot narrower than the first one!

```css
.wrapper {
  width: 400px;
  border: 5px solid rebeccapurple;
}

.px {
  width: 200px;
}

.percent {
  width: 40%;
}
```
```html
<div class="box px">I am 200px wide</div>
<div class="box percent">I am 40% wide</div>
<div class="wrapper">
  <div class="box px">I am 200px wide</div>
  <div class="box percent">I am 40% wide</div>
</div>
```

![percentage](./Images/percentage.png)

# Block and inline boxes
In CSS we broadly have two types of boxes — block boxes and inline boxes. The type refers to how the box behaves in terms of page flow and in relation to other boxes on the page. Boxes have an inner display type and an outer display type.

In general, you can set various values for the display type using the display property, which can have various values.

# What is the CSS box model?
The CSS box model as a whole applies to block boxes and defines how the different parts of a box — margin, border, padding, and content — work together to create a box that you can see on a page. Inline boxes use just some of the behavior defined in the box model.

To add complexity, there is a standard and an alternate box model. By default, browsers use the standard box model.

# Parts of a box
Making up a block box in CSS we have the:

1. Content box: The area where your content is displayed; size it using properties like inline-size and block-size or width and height.
2. Padding box: The padding sits around the content as white space; size it using padding and related properties.
3. Border box: The border box wraps the content and any padding; size it using border and related properties.

4. Margin box: The margin is the outermost layer, wrapping the content, padding, and border as whitespace between this box and other elements; size it using margin and related properties.


![Box-Model](./Images/box-model.png)


## The standard CSS box model

In the standard box model, if you give a box an inline-size and a block-size (or width and a height) attributes, this defines the inline-size and block-size (width and height in horizontal languages) of the content box. Any padding and border is then added to those dimensions to get the total size taken up by the box

## The alternative CSS box model
In the alternative box model, any width is the width of the visible box on the page. The content area width is that width minus the width for the padding and border (see image below). No need to add up the border and padding to get the real size of the box.


# CSS Margins
The CSS margin properties are used to create space around elements, outside of any defined borders.

With CSS, you have full control over the margins. There are properties for setting the margin for each side of an element (top, right, bottom, and left).

## Margin - Individual Sides
CSS has properties for specifying the margin for each side of an element:

```css
margin-top
margin-right
margin-bottom
margin-left
```

## Margin - Shorthand Property
To shorten the code, it is possible to specify all the margin properties in one property.

1. If the margin property has four values:

```css
margin: 25px 50px 75px 100px;
```
then
```
top margin is 25px
right margin is 50px
bottom margin is 75px
left margin is 100px
```

2. If the margin property has three values:

```css
margin: 25px 50px 75px;
/* then
top margin is 25px
right and left margins are 50px
bottom margin is 75px */
```

3. If the margin property has two values:

```css
margin: 25px 50px;
```
then
```
top and bottom margins are 25px
right and left margins are 50px
```

4. If the margin property has one value:

```css
margin: 25px;
/* all four margins are 25px */
```

5. The auto Value
You can set the margin property to auto to horizontally center the element within its container.

The element will then take up the specified width, and the remaining space will be split equally between the left and right margins.

# CSS Padding
The CSS padding properties are used to generate space around an element's content, inside of any defined borders.

With CSS, you have full control over the padding. There are properties for setting the padding for each side of an element (top, right, bottom, and left).

## Padding - Individual Sides
CSS has properties for specifying the padding for each side of an element:

padding-top
padding-right
padding-bottom
padding-left

## Padding - Shorthand Property
To shorten the code, it is possible to specify all the padding properties in one property.

1. If the padding property has four values:

```css
padding: 25px 50px 75px 100px;
/*then
 top padding is 25px
right padding is 50px
bottom padding is 75px
left padding is 100px */
```

2. If the padding property has three values:

```css
padding: 25px 50px 75px;
/* then
top padding is 25px
right and left paddings are 50px
bottom padding is 75px */
```

3. If the padding property has two values:

```css
padding: 25px 50px;
/* top and bottom paddings are 25px
right and left paddings are 50px */
```

4. If the padding property has one value:

```css
padding: 25px;
/* all four paddings are 25px */
```

# CSS Border Style
The border-style property specifies what kind of border to display.

The following values are allowed:

```
dotted - Defines a dotted border
dashed - Defines a dashed border
solid - Defines a solid border
double - Defines a double border
groove - Defines a 3D grooved border. The effect depends on the border-color value
ridge - Defines a 3D ridged border. The effect depends on the border-color value
inset - Defines a 3D inset border. The effect depends on the border-color value
outset - Defines a 3D outset border. The effect depends on the border-color value
none - Defines no border
hidden - Defines a hidden border
The border-style property can have from one to four values (for the top border, right border, bottom border, and the left border).
```

# TO-DO

[Learn Basic CSS by Building a Cafe Menu](https://www.freecodecamp.org/learn/2022/responsive-web-design/#learn-html-by-building-a-cat-photo-app)

# Resources

[Learn Basic CSS by Building a Cafe Menu](https://www.youtube.com/watch?v=_10PbLzB_bE)