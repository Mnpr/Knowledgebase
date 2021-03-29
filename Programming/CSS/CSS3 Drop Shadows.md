CSS3 Drop Shadows

# CSS3 Drop Shadows

With CSS3, you can apply drop shadow to an element.

## Using CSS3 Drop Shadows

The CSS3 gives you ability to add drop shadow effects to the elements like you do in Photoshop without using any images. Prior to CSS3, sliced images are used for creating the shadows around the elements that was quite annoying.

The following section will describe you how to apply the shadow on text and elements.

## CSS3 `box-shadow` Property

The `box-shadow` property can be used to add shadow to the element's boxes. You can even apply more than one shadow effects using a comma-separated list of shadows. The basic syntax of creating a box shadow can be given with:

box-shadow: offset-x offset-y blur-radius color;

The components of the `box-shadow` property have the following meaning:

*   **offset-x** — Sets the horizontal offset of the shadow.
*   **offset-y** — Sets the vertical offset of the shadow.
*   **blur-radius** — Sets the blur radius. The larger the value, the bigger the blur and more the shadow's edge will be blurred. Negative values are not allowed.
*   **color** — Sets the color of the shadow. If the color value is omitted or not specified, it takes the value of the [color](https://www.tutorialrepublic.com/css-tutorial/css-color.php) property.

See the CSS3 `box-shadow` property to learn more about the other possible values.

#### Example

```css
.box{
    width: 200px;
    height: 150px;
    background: #ccc;
    box-shadow: 5px 5px 10px #999;
}
```

**Note:** When adding the `box-shadow`, if the value for the blur-radius component is not specified, or set to zero (0), the edges of the shadow will be sharp.

Similarly, you can add the multiple box shadow using a comma-separated list:

#### Example

```css
.box{
    width: 200px;
    height: 150px;
    background: #000;
    box-shadow: 5px 5px 10px red, 10px 10px 20px yellow;
}
```

* * *

## CSS3 `text-shadow` Property

You can use the `text-shadow` property to apply the shadow effects on text. You can also apply multiple shadows to text using the same notation as `box-shadow`.

#### Example

```css
h1 {
    text-shadow: 5px 5px 10px #666;
}
h2 {
    text-shadow: 5px 5px 10px red, 10px 10px 20px yellow;
}
```
* * *