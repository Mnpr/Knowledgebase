Colors and Backgrounds

# CSS Color

The CSS color property defines the foreground color for an element.

## Setting Color Property

The `color` property typically defines the color of the text content of an element.

For instance, the `color` property specified in the `body` selector defines the default text color (foreground color in general) for the whole page.

#### Example

[Try this code »](https://www.tutorialrepublic.com/css-tutorial/../codelab.php?topic=css&file=color-01 "Try this code using online Editor")

```css
body {
    color: #000000;
}
```

Colors in CSS most often specified by the following methods:

*   a HEX value - like "#ff0000"
*   an RGB value - like "rgb(255,0,0)"
*   a color name - like "red"

Look at [CSS Color Names](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-color-names.php) for a complete list of possible color names.

* * *

## Affect of Color Property on Borders and Oulines

The `color` property is not just for text content, but for anything in the foreground that takes a color value. For instance, if [`border-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-color-property.php) or [`outline-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-outline-color-property.php) value hasn't been defined explicitly for the element, the color value will be used instead.

#### Example

```css
p.one {
    color: #0000ff;
    border: 2px solid;
}
p.two {
    color: #00ff00;
    outline: 2px solid;
}
```

**Note:** The `color` property normally inherits the color value from their parent element, except the case of [anchor](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-a-tag.php) elements.

* * *

# CSS Background

CSS background properties are used to define background styles for the elements.

## Background Properties

The CSS provide several properties for styling the background of an element, like: `background-color`, `background-image`, `background-repeat`, `background-attachment` and `background-position`. The following section will describe you how to use these properties to set the different styles for the backgrounds one by one.

## Background Color

The `background-color` property is used to set the background color of an element.

The example below demonstrates, how to set the background color of a web page.

#### Example

```css
body {
    background-color: #f0e68c;
}
```

Colors in CSS most often specified by the following methods:

*   a HEX value - like "#ff0000"
*   an RGB value - like "rgb(255,0,0)"
*   a color name - like "red"

Look at [CSS Color Names](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-color-names.php) for a complete list of possible color names.

* * *

## Background Image

The `background-image` property set an image as a background of an HTML element.

See the example below which demonstrates how to set the background image for a page.

#### Example

```css
body {
    background-image: url("leaf.jpg");
}
```

* * *

## Background Repeat

By default the `background-image` property repeats an image both horizontally and vertically.

By using `background-repeat` property you can control how a background image is tiled in the background of an html element. You can set a background image repeat vertically (y-axis), horizontally (x-axis), in both directions, or in neither direction.

See the example below which demonstrates how to set the gradient background for a web page by repeating the sliced image horizontally.

#### Example

```css
body {
    background-image: url("gradient.png");
    background-repeat: repeat-x;
}
```

* * *

## Background Attachment

The `background-attachment` property determines whether the background image is fixed with regard to the viewport or scrolls along with the containing block.

#### Example

```css
body {
    width: 250px;
    height: 200px;
    overflow: scroll;
    background-image: url("recycle.jpg");
    background-attachment: fixed;
}
```

* * *

## Background Position

The `background-position` property is used to control the position of the background image.

If no `background-position` has been specified, the image is placed at the default top-left position of the element i.e. at `(0,0)`. See the example below:

#### Example

```css
body {
    background-image: url("tree.png");
    background-repeat: no-repeat;
}
```

In the following example, the background image is positioned at top-right corner and the position of the image is specified by the `background-position` property.

#### Example

```css
body {
    background-image: url("tree.png");
    background-repeat: no-repeat;
    background-position: 100% top;
}
```

* * *

## The Background Shorthand Property

As you can see from the examples above, there are many properties to consider when dealing with the backgrounds. It is also possible to specify all these properties in one single property, to shorten the code. This is called a shorthand property.

The `background` property is a shorthand property for setting all the individual background properties (i.e., [`background-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-color-property.php), [`background-image`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-image-property.php), [`background-repeat`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-repeat-property.php), [`background-attachment`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-attachment-property.php) and [`background-position`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-position-property.php)) at once. For example:

#### Example

```css
body {
    background-color: #f0e68c;
    background-image: url("smiley.png");
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-position: 250px 25px;
}
```

Using the shorthand notation the above example can be written as:

#### Example

```css
body {
    background: #f0e68c url("smiley.png") no-repeat fixed 250px 25px;
}
```

When using the `background` shorthand property the order of the property values should be.

background: _color_ _image_ _repeat_ _attachment_ _position_;

If the value for an individual background property is missing or not specified while using the shorthand notation, the default value for that property will be used instead, if any.

**Note:** The background properties do not inherit, but the parent element's background will be visible through by default because of the initial (i.e. default) `transparent` value of the `background` CSS property.
* * *