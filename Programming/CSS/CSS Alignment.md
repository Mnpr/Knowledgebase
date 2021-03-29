CSS Alignment

# CSS Alignment

CSS has several properties that can be used to align elements on web pages.

## Text Alignment

Text inside the [block-level](https://www.tutorialrepublic.com/css-tutorial/css-visual-formatting.php#block-level) elements can aligned by setting the [text-align](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-align-property.php) properly.

#### Example

```css
h1 {
    text-align: center;
}
p {
    text-align: left;
}
```

See tutorial on [CSS Text](https://www.tutorialrepublic.com/css-tutorial/css-text.php) to learn more about text formatting.

* * *

## Center Alignment Using the margin Property

Center alignment of a [block-level](https://www.tutorialrepublic.com/css-tutorial/css-visual-formatting.php#block-level) element is one of the most important implications of the CSS [`margin`](https://www.tutorialrepublic.com/css-tutorial/css-margin.php) property. For example, the [`<div>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-div-tag.php) container can be aligned horizontally center by setting the left and right margins to `auto`.

#### Example

```css
div {
    width: 50%;
    margin: 0 auto;
}
```

The style rules in the above example center align the [`<div>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-div-tag.php) element horizontally.

**Note:** The value `auto` for the `margin` property will not work in Internet Explorer 8 and earlier versions, unless a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) is specified.

* * *

## Aligning Elements Using the position Property

The CSS [`position`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-position-property.php) in conjunction with the `left`, `right`, `top` and `bottom` property can be used to align elements with respect to the document's viewport or containing parent element.

#### Example

```css
.up {
    position: absolute;
    top: 0;
}
.down {
    position: absolute;
    bottom: 0;
}
```

To learn more about positioning elements, see the tutorial on [CSS positioning](https://www.tutorialrepublic.com/css-tutorial/css-position.php).

* * *

## Left and Right Alignment Using the float Property

The [`float`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-float-property.php) CSS property can be used to align an element to the left or right of its containing block in such a way that other content may flow along its side.

Hence, if an element is floated to the left, content will flow along its right side. Conversely, if the element is floated to the right, content will flow along its left side.

#### Example

```css
div {
    width: 200px;
    float: left;
}
```

* * *

## Clearing Floats

One of the most confusing things about working with the float-based layouts is the collapsing parent. The parent element doesn't stretch up automatically to accommodate the floated elements. Though, this isn't always obvious if the parent doesn't contain any visually noticeable background or borders, but it is important to be aware of and must dealt with to prevent strange layout and cross-browser problem. See the illustration below:

![CSS Collapsed Parent](../../../../_resources/945972b5f07641909187fddda21971c1.jpg)

You can see the [`<div>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-div-tag.php) element doesn't stretch up automatically to accommodate the floated images. This problem can be fixed by clearing the float after the floated elements in the container but before the closing tag of the container element.

* * *

## Fixing the Collapsed Parent

There are several ways to fix the CSS collapsing parent issue. The following section will describe you these solutions along with the live examples.

### Solution 1: Float the Container

The easiest way to fix this problem is to float the containing parent element.

#### Example

```css
.container {
    float: left;
    background: #f2f2f2;
}
```

**Warning:** This fix will only work in a limited number of circumstances, since floating the parent may produce unexpected results.

### Solution 2: Using the Empty Div

This is an old fashioned way but is an easy solution and works across every browser.

#### Example

```markup
.clearfix {
    clear: both;
}
/* html code snippet */
<div class="clearfix"> </div>
```

You could also do this by means of a [`<br>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-br-tag.php) tag. But this method is not recommended since it adds nonsemantic code to your markup.

### Solution 3: Using the :after Pseudo-Element

The `:after` [pseudo-element](https://www.tutorialrepublic.com/css-tutorial/css-pseudo-elements.php) in conjunction with the [`content`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-content-property.php) property has been used quite extensively to resolve float-clearing issues.

#### Example

```css
.clearfix:after {
    content: ".";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
}
```

The class `.clearfix` is applied to any container that has floating children.

**Warning:** Internet Explorer up IE7 does not support the `:after` [pseudo-element](https://www.tutorialrepublic.com/css-tutorial/css-pseudo-elements.php). However IE8 supported, but require a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) to be declared.
* * *