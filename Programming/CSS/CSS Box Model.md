CSS Box Model 

# CSS Box Model

CSS box model describes how elements are visually laid out on the web pages.

## What is Box Model

Every element that can be displayed is comprised of one or more rectangular boxes. CSS box model typically describes how these rectangular boxes are laid out on a web page. These boxes can have different properties and can interact with each other in different ways, but every box has a content area and optional surrounding margin, padding, and border.

The following diagram demonstrates how the margin, padding, and border CSS properties determines how much space an element can take on a web page.

![CSS Box Model](../../../../_resources/bf63f4c7b2b54a47950b738350810591.jpg)

* * *

## Width and Height of Elements

Usually when you set the width and height of an element using the CSS [`width`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-width-property.php) and [`height`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-width-property.php) properties, in reality you are only setting the width and height of the content area of an element. The actual width and height of the element's box depend on several factors.

The actual space that an element's box might take is calculated like this:

| Box Size | CSS Properties |
| --- | --- |
| Total Width | `width` \+ `padding-left` \+ `padding-right` \+ `border-left` \+ `border-right` \+ `margin-left` \+ `margin-right` |
| Total Height | `height` \+ `padding-top` \+ `padding-bottom` \+ `border-top` \+ `border-bottom` \+ `margin-top` \+ `margin-bottom` |

Explanation of the different properties given in the upcoming chapters.

**Note:** In CSS box model; content area of the element's box is the area, where text, images, lists, tables, forms, videos, etc. appears.

* * *

# CSS Margin

Margin clears an area around the border that separates it from other boxes.

## CSS Margin Properties

The CSS margin properties allow you to set the margins around the sides of an element's box. The margins does not have a [`background-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-color-property.php), it is completely transparent.

## Setting Margins for Individual Sides

You can easily specify the different margins for the different sides of an element such as top, right, bottom or left side using the CSS individual margin property.

#### Example

```css
h1 {
    margin-bottom: 20px;
}
p {
    margin-left: 10px;
    margin-right: 30px;
}
```

* * *

## The margin Shorthand Property

The `margin` property is a shorthand property to avoid setting margin of each side separately: `margin-top`, `margin-right`, `margin-bottom` and `margin-left`.

#### Example

```css
h1 {
    margin: 0 10px;
}
p {
    margin: 25px 50px 75px 100px;
}
```

This shorthand notation can take one, two, three, or four whitespace separated values.

*   If _one value_ is set, this is applied to all the four sides.
*   If _two values_ are specified, the first value is applied to the top and bottom, and the second value is applied to the right and left side.
*   If _three values_ are specified, the first value is applied to the top, second value is applied to left and right side and the last value is applied to the bottom.
*   If _four values_ are specified, they are applied to the top, right, bottom and the left side respectively in the specified order.

* * *
# CSS Padding

The padding area is the space between the content of the element and its border.

## CSS Padding Properties

The CSS padding properties allow you to set the padding area for an element that separates its border from its content. The padding is affected by the [`background-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-color-property.php) of the box.

## Define Paddings for Individual Sides

You can easily specify the different paddings for the different sides of an element such as top, right, bottom or left side using the CSS individual padding property.

#### Example

```css
h1 {
    padding-bottom: 10px;
}
p {
    padding-top: 20px;
    padding-left: 50px;
}
```

* * *

## The padding Shorthand Property

The `padding` property is a shorthand property to avoid setting padding for each side of an element separately i.e. [`padding-top`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-padding-top-property.php), [`padding-right`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-padding-right-property.php), [`padding-bottom`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-padding-bottom-property.php), [`padding-left`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-padding-left-property.php).

#### Example

```css
h1 {
    padding: 10px 20px;
}
p {
    padding: 10px 15px 20px 25px;
}
```

**Note:** Unlike CSS `[margin](https://www.tutorialrepublic.com/css-tutorial/css-margin.php)` properties, values for padding properties cannot be negative. Like margin properties, percentage values for padding properties refer to the width of the generated box's containing block.

The `padding` property can take one, two, three, or four whitespace separated values.

*   If _one value_ is set, this is applied to all the four sides.
*   If _two values_ are specified, the first value is applied to the top and bottom, and the second value is applied to the right and left side.
*   If _three values_ are specified, the first value is applied to the top, second value is applied to left and right side and the last value is applied to the bottom.
*   If _four values_ are specified, they are applied to the top, right, bottom and the left side respectively in the specified order.

* * *

# CSS Border

Border of an element goes around the padding and content.

## CSS Border Properties

The CSS border properties allow you to define the border area of a box. The border can either be a predefined style like, solid line, double line, dotted line, etc. or [it can be an image](https://www.tutorialrepublic.com/css-tutorial/css3-border.php). The following section will describe you how to set the various properties defining the style (`border-style`), color (`border-color`), and thickness (`border-width`) of the border.

## The border-width Property

The [`border-width`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-width-property.php) property specifies the width of the border area. It is a shorthand property for setting the thickness of all the four sides of an element's border at the same time.

#### Example

```css
p {
    border-width: medium 10px thick 15px;
}
```

**Note:** If the value for the `border-width` property is missing or not specified, the default value (`medium`) of the `border-width` will be used instead.

* * *

## The border-style Property

The [`border-style`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-style-property.php) property sets the style of a box's border such as: `solid`, `dotted`, etc. It is a shorthand property for setting the line style for all four sides of the elements border.

The `border-style` property may take one of the following values: `none`, `hidden`, `dashed`, `dotted`, `double`, `groove`, `inset`, `outset`, `ridge` and `solid`.

`none:` Defines no border.

`hidden:` Defines hidden border.

`dotted:` Defines a dotted border

`dashed:` Defines a dashed border

`solid:` Defines a solid border

`double:` Defines two borders. The width of the two borders are same as the border-width value

`groove:` Defines a 3D grooved border. The effect depends on the border-color value

`ridge:` Defines a 3D ridged border. The effect depends on the border-color value

`inset:` Defines a 3D inset border. The effect depends on the border-color value

`outset:` Defines a 3D outset border. The effect depends on the border-color value

#### Example

```css
p {
    border-style: dotted;
}
```

* * *

## The border-color Property

The [`border-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-color-property.php) property specify the [`color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-color-property.php) of a box's border. This is also a shorthand property for setting the color of all the four sides of an element's border.

#### Example

```css
p {
    border-style: solid;
    border-color: #ff0000;
}
```

**Note:** The `border-color` property does not work if it is used alone. Use the `border-style` property to set the border first.

* * *

## The border Shorthand Property

The [`border`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-property.php) CSS property is a shorthand property for setting one or more of the individual border properties `border-style`, `border-width` and `border-color` in a single rule.

#### Example

```css
p {
    border: 5px solid #ff4500;
}
```

If the value for an individual border property is omitted or not specified while setting the border shorthand property, the default value for that property will be used instead, if any.

**Note:** If the value for the [`border-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-color-property.php) property is missing or not specified when setting the borders for an element (e.g. `border: 5px solid;`) the element's [`color`](https://www.tutorialrepublic.com/css-tutorial/css-color.php) property will be used as the value for the `border-color`.

In this example, the border will be a solid black line of 5px width:

#### Example

```css
p {
    color: black;
    border: 5px solid;
}
```

But, in the case of `border-style`, omitting the value will cause no border to show at all, because the default value for `border-style` property is `none`.

In the example below, there will be no border:

#### Example

```css
p {
    border: 5px #00ff00;
}
```

* * *