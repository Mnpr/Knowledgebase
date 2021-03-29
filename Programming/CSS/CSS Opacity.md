CSS Opacity

# CSS Opacity

The opacity CSS property specifies the transparency of an element.

## Cross Browser Opacity

Opacity is now a part of the CSS3 specifications, but it was present for a long time. However, older browsers have different ways of controlling the opacity or transparency.

## CSS Opacity in Firefox, Safari, Chrome, Opera and IE9

Here is the most up to date syntax for CSS opacity in all current browsers.

#### Example

```css
p {
    opacity: 0.7;
}
```

The above style rule will make the paragraph element 70% opaque (or 30% transparent).

The opacity property takes a value a value from 0.0 to 1.0. A setting of `opacity: 1;` would make the element completely opaque (i.e. 0% transparent), whereas `opacity: 0;` would make the element completely transparent (i.e. 100% transparent).

* * *

## CSS Opacity in Internet Explorer 8 and lower

Internet Explorer 8 and earlier version supports a Microsoft-only property "alpha filter" to control the transparency of an element.

#### Example

```css
p {
    filter: alpha(opacity=50);
    zoom: 1;  /* Fix for IE7 */
}
```

**Note:** Alpha filters in IE accept values from `0` to `100`. The value `0` makes the element completely transparent (i.e. 100% transparent), whereas the value `100` makes the element completely opaque (i.e. 0% transparent).

* * *

## CSS Opacity for All Browser

Combining the both steps above you will get the _opacity for all browsers_.

#### Example

```css
p {
    opacity: 0.5;  /* Opacity for Modern Browsers */
    filter: alpha(opacity=50);  /* Opacity for IE8 and lower */
    zoom: 1;  /* Fix for IE7 */
}
```

**Warning:** Including _alpha filter_ to control transparency in Internet Explorer 8 and lower versions creates invalid code in your style sheet since this is a Microsoft-only property, not a standard CSS property.

* * *

## CSS Image Opacity

You can also make transparent images using CSS Opacity.

The three images in the illustration below are all from the same source image. The only differences between them are the level of their opacity.

|     |     |     |
| --- | --- | --- |
| ![100% Opaque Image](../../../../_resources/1773d4a8bedd464fa4d6ee95a221b538.jpg) | ![50% Opaque Image](../../../../_resources/1773d4a8bedd464fa4d6ee95a221b538.jpg) | ![25% Opaque Image](../../../../_resources/1773d4a8bedd464fa4d6ee95a221b538.jpg) |
| `opacity:1` | `opacity:0.5` | `opacity:0.25` |

* * *

## Change Image Opacity on Mouse Over

The following example demonstrates a common use of CSS image opacity, where the opacity of images changes when the user moves the mouse pointer over an image.

|     |     |     |
| --- | --- | --- |
| ![Snail](../../../../_resources/58e113f27c324ba680d495e216c166c4.png) | ![Tortoise](../../../../_resources/413de5dbe1b04484b0bfb07ed9da969e.png) | ![Octopus](../../../../_resources/181e260ae5534a23b42b42bc9b864e3c.png) |

— Move your mouse pointer over the images to see the effect.

* * *

## Text in Transparent Box

When using opacity on an element not only the background of the element that will have transparency, but all of its child elements become transparent as well. It is making the text inside the transparent element hard to read if the value of opacity becomes higher.

|     |     |     |     |
| --- | --- | --- | --- |
| OPACITY | OPACITY | OPACITY | OPACITY |

To prevent this either you can use transparent PNG images, or put the text block outside of the transparent box and push it visually inside using the negative [margin](https://www.tutorialrepublic.com/css-tutorial/css-margin.php) or [CSS positioning](https://www.tutorialrepublic.com/css-tutorial/css-position.php).

#### Example

```css
div {
    float: left;
    opacity: 0.7;
    border: 1px solid #949781;
}
p {
    float: left;
    position: relative;
    margin-left: -400px;
}
```

* * *

## CSS Transparency Using RGBA

In addition to RGB CSS3 has introduced a new way RGBA to specify a color that includes alpha transparency as part of the color value. RGBA stands for Red Blue Green Alpha.

The RGBA declaration is a very easy way to set transparency for a color.

#### Example

```css
div {
    background: rgba(200, 54, 54, 0.5);
}
p {
    color: rgba(200, 54, 54, 0.25);
}
```

The first three numbers representing the color in RGB values i.e. red (0-255), green (0-255), blue (0-255) and the fourth representing alpha transparency value between 0 to 1 (0 makes the color fully transparent , whereas the value of 1 makes it fully opaque).

One important characteristic to note about the RGBA transparency is that — the ability to control the opacity of individual color. With RGBA, we can make the text color of an element transparent and leave background intact.

|     |     |     |     |
| --- | --- | --- | --- |
| RGBA | RGBA | RGBA | RGBA |

— Or leave the text color alone and change only the transparency of background.

|     |     |     |     |
| --- | --- | --- | --- |
| RGBA | RGBA | RGBA | RGBA |

You can see how easily you can control the opacity of individual colors rather than the entire element using RGBA. However it is always recommended to define a fallback color for the browsers that do not support the RGBA colors.

**Note:** The RGBA transparency doesn't affect the child elements the way the `opacity` property does. The alpha value of RGBA affects the transparency of individual color rather than the entire element.

* * *

## Declaring a Fallback Color

All browsers do not support RGBA colors. However, you can provide an alternative such as solid colors or transparent PNG images for the browsers that don't support it.

#### Example

```css
p {
    /* Fallback for web browsers that doesn't support RGBA */
    background: rgb(0, 0, 0);
    /* RGBa with 0.5 opacity */
    background: rgba(0, 0, 0, 0.5);
}
```

**Warning:** Internet Explorer 8 and earlier versions do not support the RGBA colors. They use the [gradient filter](http://msdn.microsoft.com/en-us/library/ms532997%28VS.85%29.aspx) to achieve the effect of RGBA, which is deprecated.

* * *