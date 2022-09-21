- [Flexbox](#flexbox)
- [CSS Flex Items](#css-flex-items)
- [The order Property](#the-order-property)
- [The flex-grow Property](#the-flex-grow-property)
- [The flex-shrink Property](#the-flex-shrink-property)
- [The flex-basis Property](#the-flex-basis-property)
- [The flex Property](#the-flex-property)
- [The align-self Property](#the-align-self-property)
- [The CSS Flexbox Items Properties](#the-css-flexbox-items-properties)
- [TO-DO](#to-do)

# Flexbox

# CSS Flex Items
Child Elements (Items)
The direct child elements of a flex container automatically becomes flexible (flex) items.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .flex-container {
  display: flex;
  background-color: #f1f1f1;
}
.flex-container > div {
  background-color: red;
  color: white;
  width: 100px;
  margin: 10px;
  text-align: center;
  line-height: 75px;
  font-size: 30px;
}

    </style>
</head>
<body>
    <div class="flex-container">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </div>
</body>
</html>
```

![](./Images/first.png)

# The order Property
The order property specifies the order of the flex items.

<!-- minor change in body of above hmtl code -->
```html
<body>
    <div class="flex-container">
        <div style="order: 3">1</div>
        <div style="order: 2">2</div>
        <div style="order: 4">3</div>
        <div style="order: 1">4</div>
      </div>
</body>
```

![](./Images/order.png)

# The flex-grow Property
The flex-grow property specifies how much a flex item will grow relative to the rest of the flex items.
The value must be a number, default value is 0.



```html
<!-- minor change in body of above hmtl code -->
<body>
    <div class="flex-container">
        <div style="flex-grow: 1">1</div>
        <div style="flex-grow: 1">2</div>
        <div style="flex-grow: 8">3</div>
      </div>
</body>
```

![](./Images/grow.png)

# The flex-shrink Property
The flex-shrink property specifies how much a flex item will shrink relative to the rest of the flex items.
The value must be a number, default value is 1.

```html
<!-- minor change in body of above hmtl code -->
<body>
    <div class="flex-container">
        <div>1</div>
        <div>2</div>
        <div style="flex-shrink: 0">3</div>
        <div>4</div>
        <div>5</div>
        <div>6</div>
        <div>7</div>
        <div>8</div>
        <div>9</div>
        <div>10</div>
      </div>
</body>
```


# The flex-basis Property
The flex-basis property specifies the initial length of a flex item.

```html
<!-- minor change in body of above hmtl code -->
<body>
    <div class="flex-container">
        <div>1</div>
        <div>2</div>
        <div style="flex-basis: 200px">3</div>
        <div>4</div>
      </div>
</body>
```

![](./Images/basis.png)

# The flex Property
The flex property is a shorthand property for the flex-grow, flex-shrink, and flex-basis properties.
**Example**
Make the third flex item not growable (0), not shrinkable (0), and with an initial length of 200 pixels:

```html
<body>
    <div class="flex-container">
        <div>1</div>
        <div>2</div>
        <div style="flex: 0 0 200px">3</div>
        <div>4</div>
      </div>
</body>
```

![](./Images/4.png)

# The align-self Property
The align-self property specifies the alignment for the selected item inside the flexible container.

The align-self property overrides the default alignment set by the container's align-items property.

In these examples we use a 200 pixels high container, to better demonstrate the align-self property:

**Example**
Align the third flex item in the middle of the container:

![](./Images/align.png)

# The CSS Flexbox Items Properties
The following table lists all the CSS Flexbox Items properties:


|Property|	Description|
|--|--|
|align-self|	Specifies the alignment for a flex item (overrides the flex container's align-items property)|
|flex|	A shorthand property for the flex-grow, flex-shrink, and the flex-basis properties|
|flex-basis|	Specifies the initial length of a flex item|
|flex-grow	|Specifies how much a flex item will grow relative to the rest of the flex items inside the same |container
|flex-shrink	|Specifies how much a flex item will shrink relative to the rest of the flex items inside the same |container
|order	|Specifies the order of the flex items inside the same container|

# TO-DO

[Photo Gallery App](https://www.freecodecamp.org/learn/2022/responsive-web-design/learn-css-flexbox-by-building-a-photo-gallery)