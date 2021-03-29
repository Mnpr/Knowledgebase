CSS3 Miscellaneous

# CSS3 Miscellaneous

In this tutorial we'll learn about few more interesting CSS3 features.

## Extending User Interface with CSS3

In this chapter we'll discuss about some interesting user interface related CSS3 properties like [`resize`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-resize-property.php), [`outline-offset`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-outline-offset-property.php), etc. that you can use to enhance your web pages.

## Resizing Elements

You can make an element resizable horizontally, vertically or on both directions with the CSS3 `resize` property. However, this property is typically used to remove the default resizable behavior form the [`<textarea>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-textarea-tag.php) form control.

#### Example

```css
p, div, textarea {
    width: 300px;
    min-height: 100px;
    overflow: auto;
    border: 1px solid black;
}
p {
   resize: horizontal; 
}
div {
    resize: both;
}
textarea {
    resize: none;
}
```

* * *

## Setting Outline Offset

In the previous section you've learnt how to set different properties for outlines like width, color and styles. However, CSS3 offer one more property `outline-offset` for setting the space between an outline and the border edge of an element. This property can accepts negative value that means you can also place outline inside an element.

#### Example

```css
p, div {
    margin: 50px;
    height: 100px;
    background: #000;
    outline: 2px solid red;
}
p {
    outline-offset: 10px;
}
div {
    outline-offset: -15px;
}
```
* * *