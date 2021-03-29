CSS3 Backgrounds

# CSS3 Background

With CSS3, you can apply multiple backgrounds to elements.

## Using CSS3 Backgrounds

The CSS3 provides several new properties to manipulate the background of an element like background clipping, multiple backgrounds, and the option to adjust the background size.

The following section will describe you all the new background features of CSS3, for other background related properties please check out the [CSS background](https://www.tutorialrepublic.com/css-tutorial/css-background.php) tutorial.

## CSS3 `background-size` Property

The `background-size` property can be used to specify the size of the background images.  Prior to CSS3, the size of the background images was determined by the actual size of the images. The background image size can be specified using the pixels or percentage values as well as the keywords `auto`, `contain`, and `cover`. Negative values are not allowed.

#### Example

```css
.box {
    width: 250px;
    height: 150px;
    background: url("images/sky.jpg") no-repeat;
    background-size: contain;
    border: 6px solid #333;
}
```

**Tip:** The `background-size` property is typically used to create full size background images that scale according to the size of viewport or witdh of the browser.

* * *

## CSS3 `background-clip` Property

The `background-clip` property can be used to specify whether an element's background extends into the border or not. The `background-clip` property can take the three values: `border-box`, `padding-box`, `content-box`.

#### Example

```css
.box {
    width: 250px;
    height: 150px;
    padding: 10px;
    border: 6px dashed #333;
    background: orange;
    background-clip: content-box;
}
```

See the tutorial on [CSS box model](https://www.tutorialrepublic.com/css-tutorial/css-box-model.php) to learn more about element's boxes.

* * *

## CSS3 `background-origin` Property

The `background-origin` property can be used to specify the positioning area of the background images. It can take the same values as `background-clip` property: `border-box`, `padding-box`, `content-box`.

#### Example

```css
.box {
    width: 250px;
    height: 150px;
    padding: 10px;
    border: 6px dashed #333;
    background: url("images/sky.jpg") no-repeat;
    background-size: contain;
    background-origin: content-box;
}
```

**Note:** The `background-origin` property is ignored if the value of [`background-attachment`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-attachment-property.php) property is specified as `'fixed'`.

* * *

## CSS3 Multiple Backgrounds

CSS3 gives you ability to add multiple backgrounds to a single element. The backgrounds are layered on the top of one another. The number of layers is determined by the number of comma-separated values in the [`background-image`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-image-property.php) or [`background`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-property.php) shorthand property.

#### Example

```css
.box {
    width: 100%;
    height: 500px;
    background: url("images/birds.png") no-repeat center,  url("images/clouds.png")  no-repeat center, lightblue;
}
```

The first value in the comma-separated list of backgrounds i.e. the [`background-image`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-image-property.php) 'birds.png' will appear on the top and the last value i.e. the 'lightblue' color will appear at the bottom. Only the last background can include a [`background-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-color-property.php).
***