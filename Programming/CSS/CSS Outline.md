CSS Outline

# CSS Outline

An outline is a line that is drawn just outside the border edge of the elements such as buttons, active form fields, etc., to make them stand out.

## Outlines Vs Borders

The outlines are generally used to highlight elements. An outline at a glance looks very similar to the border, but it differs from border in the following ways:

*   Outlines do not take up space, because they always placed on top of the box of the element which may cause them to overlap other elements on the page.
*   Unlike borders, outlines won't allow us to set each edge to a different width, or set different colors and styles for each edge. An outline is the same on all sides.
*   Outlines don't have any impact on surrounding elements apart from overlapping.
*   Unlike borders, outlines don't change the size or position of the element.
*   Outlines may be non-rectangular.

**Note:** If you put an outline on an element, it will take up the same amount of space on the web pages as if you didn't have an outline on that element.

* * *

## The outline-width Property

The `outline-width` property specifies the width of the outline to be added on an element. Its value should be, a CSS length (`px`, `pt`, `em`, and so on) or one of the allowed keywords, but percentage or negative values are not allowed. Just like the [`border-width`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-width-property.php) property.

#### Example

```css
p {
    outline-width: thick;
}
```

**Note:** If the value for the `outline-width` is missing or not specified, the default value (`medium`) of the `outline-width` will be will be used instead.

* * *

## The outline-style Property

The `outline-style` property sets the style for an outline such as: `solid`, `dotted`, etc.

This property may take one of the following values: `none`, `hidden`, `dashed`, `dotted`, `double`, `groove`, `inset`, `outset`, `ridge` and `solid`. Just like [`border-style`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-style-property.php) property.

`none:` Defines no outline.

`hidden:` Defines hidden outline.

`dotted:` Defines a dotted outline

`dashed:` Defines a dashed outline

`solid:` Defines a solid outline

`double:` Defines two outlines. The width of the two outlines are same as the outline-width value

`groove:` Defines a 3D grooved outline. The effect depends on the outline-color value

`ridge:` Defines a 3D ridged outline. The effect depends on the outline-color value

`inset:` Defines a 3D inset outline. The effect depends on the outline-color value

`outset:` Defines a 3D outset outline. The effect depends on the outline-color value

#### Example

```css
p {
    outline-style: double;
}
```

* * *

## The outline-color Property

The `outline-color` property sets the color of an outline.

#### Example

```css
p {
    outline-style: solid;
    outline-color: #0000ff;
}
```

You can also set the `outline-color` to `transparent`.

**Note:** The `outline-color` property does not work if it is used alone. Use the `outline-style` property to set the outlines first.

* * *

## The outline Shorthand Property

The `outline` CSS property is a shorthand property for setting one or more of the individual outline properties `outline-style`, `outline-width` and `outline-color` in a single rule.

#### Example

```css
p {
    outline: 5px solid #9acd32;
}
```

If the value for an individual outline property is omitted or not specified while setting the outline shorthand property, the default value for that property will be used instead, if any.

**Note:** If the value for the [`outline-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-outline-color-property.php) property is missing or not specified when setting the outlines for an element (e.g. `outline: 5px solid;`) the element's [`color`](https://www.tutorialrepublic.com/css-tutorial/css-color.php) property will be used as the value for the `outline-color`.

In the example below, the outline will be a solid black line of 5px width:

#### Example

```css
p {
    color: black;
    outline: 5px solid;
}
```

But, in the case of [`outline-style`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-outline-style-property.php), omitting the value will cause no outline to show at all, because the default value for `outline-style` property is `none`.

In the example below, there will be no outline:

#### Example

```css
p {
    outline: 5px #00ff00;
}
```

**Warning:** Internet Explorer 7 and earlier versions don't support the `outline` property. IE8 supports the `outline` property only if a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) is specified.

* * *

## Removing Dotted Line Around Active Links

The `outline` property is widely used to remove the dotted line around active links.

#### Example

```css
a, a:acive, a:focus {
    outline: none; /* Works in Firefox, Chrome, IE8 and above */
}
```

* * *