CSS Position

# CSS Position

The position property defines how an element will be positioned on a page.

## CSS Positioning Methods

Positioning elements appropriately on the web pages is a necessity for a good layout design. There are several methods in CSS that you can use for positioning elements. The following section will describe you these positioning methods one by one.

## Static Positioning

A static positioned element is always positioned according to the normal flow of the page. HTML elements are positioned static by default. Static positioned elements are not affected by the [`top`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-top-property.php), [`bottom`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-bottom-property.php), [`left`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-left-property.php), [`right`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-right-property.php), and [`z-index`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-z-index-property.php) properties.

#### Example

```css
.box {
    padding: 20px;
    background: #7dc765;
}
```

* * *

## Relative Positioning

A relative positioned element is positioned relative to its normal position.

In the relative positioning scheme the element's box position is calculated according to the normal flow. Then the box is shifted from this normal position according to the properties — `top` or `bottom` and/or `left` or `right`.

#### Example

```css
.box {
    position: relative;
    left: 100px;
}
```

**Note:** A relatively positioned element can be moved and overlap other elements, but it keeps the space originally reserved for it in the normal flow.

* * *

## Absolute Positioning

An absolutely positioned element is positioned relative to the first parent element that has a position other than static. If no such element is found, it will be positioned on a page relative to the 'top-left' corner of the browser window. The box's offsets further can be specified using one or more of the properties `top`, `right`, `bottom`, and `left`.

Absolutely positioned elements are taken out of the normal flow entirely and thus take up no space when placing sibling elements. However, it can overlap other elements depending on the [`z-index`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-z-index-property.php) property value. Also, an absolutely positioned element can have [margins](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-margin-property.php), and they do not collapse with any other margins.

#### Example

```css
.box {
    position: absolute;
    top: 200px;
    left: 100px;
}
```

* * *

## Fixed Positioning

Fixed positioning is a subcategory of absolute positioning.

The only difference is, a fixed positioned element is fixed with respect to the browser's [viewport](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#viewport) and does not move when scrolled.

#### Example

```css
.box {
    position: fixed;
    top: 200px;
    left: 100px;
}
```

**Note:** In case of the [print media](https://www.tutorialrepublic.com/css-tutorial/css-media-types.php) type, the fixed positioned element is rendered on every page, and is fixed with respect to the page box (even in print-preview). IE7 and IE8 support the fixed value only if a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) is specified.

* * *