CSS Color Values

# CSS Color Values

There are several ways to define a color values in CSS.

## Color keywords

Color keywords are case-insensitive identifiers which represent a specific color, e.g. `red`, `green`, `blue`, `yellow`, `black`, etc.

#### Example

*   `h1 {`
*   `    color: red;`
*   `}`
*   `p {`
*   `    background-color: yellow;`
*   `}`

**Warning:** Support for color keywords varies across browsers so, to be on the safe side, it's better to use the hexadecimal or functional notation.

Complete list of [CSS Color Names ](:/e0260e7dfee447fdb823a7bc25e1ba0a)

* * *

## Transparent Color Keyword

The transparent keyword represents a fully transparent color.

This keyword can be considered a shorthand for transparent black, `rgba(0,0,0,0)`, which is also its computed value.

#### Example


*   `h1 {`
*   `    color: transparent;`
*   `}`
*   `p {`
*   `    background-color: transparent;`
*   `}`

**Note:** CSS 2.1 allowed only two property `[background-color](https://www.tutorialrepublic.com/css-reference/css-background-color-property.php)` and `[border-color](https://www.tutorialrepublic.com/css-reference/css-border-color-property.php)` to accept the transparent keyword. But, CSS3 extends the color value to include the `transparent` keyword to allow its use with all properties that accept a color value.

* * *

## RGB Color Values

RGB (red-green-blue) color model is the most common way to define color values in CSS. Colors can be defined using the RGB model in two ways:

### Hexadecimal Notation

The RGB value in hexadecimal notation is specified with a `#` character immediately followed by either three or six hexadecimal characters (0-9, a-f).

When six-digit notation (`#rrggbb`) is used, the first pair (`rr`) represents the red value, the second pair (`gg`) represents the green value and the last pair (`bb`) represents the blue value.

#### Example


*   `h1 {`
*   `    color: #f80;`
*   `}`
*   `p {`
*   `    background-color: #ff8800;`
*   `}`

**Tip:** The three-digit hexadecimal notation (`#rgb`) can be converted into six-digit form (`#rrggbb`) by replicating digits, but not by adding zeros. For example, `#03f` can be expanded to `#0033ff`, but both values represent the same color.

### Functional Notation

The RGB value in functional notation is specified with: `rgb(red, green, blue)`. Where, each parameter (`red`, `green`, and `blue`) defines the intensity of the color and can be an integer value (from 0 to 255) or a percentage value (from 0% to 100%).

The integer value `255` corresponds to `100%`, and to `f` or `ff` in the hexadecimal notation: For example, `rgb(0,255,255) = rgb(0%,100%,100%) = #0ff`, and all values represents the same color which is aqua. White spaces are allowed around the numerical values.

#### Example

*   `h1 {`
*   `    color: rgb(0,255,255);`
*   `}`
*   `p {`
*   `    background-color: rgb(0%,100%,100%);`
*   `}`

A value of `0` or `0%` represents the absence of a particular color component, while a value of `255`, `100%` and `f` or `ff` represents the full presence of that color component.

**Note:** Values outside the valid range (`0-255` or `0%-100%`) are automatically clipped or changed to fall within the range supported by the device.

Check out the tutorial on [CSS3 color](https://www.tutorialrepublic.com/css-reference/../css-tutorial/css3-color.php) to learn about the new functional notations, like `rgba()`, `hsl()` and `hsla()` for defining the color values.

***