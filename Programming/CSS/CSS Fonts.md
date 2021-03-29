CSS Fonts

# CSS Fonts

The CSS font properties allows you to set various styles for fonts likes font family, size and boldness, variant, etc. of a text.

## Font Properties

The CSS provide several properties for styling fonts of the text content, like: `font-family`, `font-style`, `font-variant`, `font-weight` and `font-size`. The following section will describe you each one of these properties one by one.

## Font Family

The `font-family` CSS property allows you to set a prioritized list of font family name and/or generic family name for the text content of a selected element.

The `font-family` property can hold several font names as a _fallback_ system. List the font that you want first, then any fonts that might fill in for the first if it is not available. You should end the list with a generic font family which are five — `serif`, `sans-serif`, `monospace`, `cursive` and `fantasy`. A font family declaration might look like this:

#### Example

```css
p {
    font-family: "Times New Roman", Times, serif;
}
```

**Note:** If the name of a font family is more than one word, it must be in quotation marks, like `"Times New Roman"`, `"Courier New"`, `"Trebuchet MS"` etc.

To learn more about commonly used font combinations; please check out [web safe fonts](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-web-safe-fonts.php).

* * *

## Font Style

The `font-style` property sets the font style for the text content of an element.

The possible values for this property are: `normal`, `italic` or `oblique`.

#### Example

```css
p.one {
    font-style: normal;
}
p.two {
    font-style: italic;
}
p.three {
    font-style: oblique;
}
```

**Note:** At first glance both oblique and italic styles appear the same thing, but there is difference. The `italic` style uses an _italic version_ of the font while `oblique` text on the other hand is simply a _slanted version_ of the normal font.

* * *

## Font Size

The `font-size` property sets the size of font for the text content of an element.

There are several ways to specify the font size values e.g. with keywords, pixels or ems.

## Setting Font Size with Keywords

By setting a keyword font size on the body element, you can set relative font-sizing everywhere else on the page, giving you the ability to easily scale the font up or down on the entire page accordingly. An absolute size is specified using one of the following keywords: `xx-small`, `x-small`, `small`, `medium`, `large`, `x-large`, `xx-large`.

A relative size is specified using one of the following keywords: `smaller`, `larger`.

#### Example

```css
body {
    font-size: large;
}
h1 {
    font-size: larger;
}
p {
    font-size: smaller;
}
```

* * *

## Setting Font Size with Pixels

Setting the font size in pixel values (e.g. 12px, 16px, etc.) is a good choice when you need the pixel accuracy. However, the results may vary to some extent across the browsers, since they use different algorithms to achieve the similar effect.

#### Example

```css
h1 {
    font-size: 24px;
}
p {
    font-size: 14px;
}
```

Defining the font sizes in pixel is not very accessible, because a user cannot change the font size from the browser settings. For instance, users with limited vision may wish to set the font size larger than the size specified by you. Therefore, you should avoid using the pixels values for font sizes if you wish to create an inclusive design.

**Tip:** The text can be resized in all browsers using the _zoom tool_. However, this feature resizes the entire page, not just the text.

* * *

## Setting Font Size with Em

The `em` unit refers to the font size of the parent element.

The size of an `em` value is dynamic. When defining the `font-size` property, an `em` is equal to the size of the font that applies to the parent of the element.

If you set a `font-size` of 20px on the body element, then `1em = 20px` and `2em = 40px`.

If you haven't set the font size anywhere on the page, then it is the browser default, which is probably 16px. So, by default `1em = 16px`, and `2em = 32px`.

#### Example

```css
h1 {
    font-size: 2em;    /* 32px/16px=2em */
}
p {
    font-size: 0.875em;    /* 14px/16px=0.875em */
}
```

**Warning:** IE6 and IE7 unacceptably exaggerate the smallness and largeness of the resized text. (Test it Before Publishing).

* * *

## Using the Combination of Percentage and Em

The solution to achieve the similar effect in all browsers is to set a default `font-size` in percentage for the body element. A popular technique is to set the `font-size` for the body to `62.5%` (that is 62.5% of the default 16px), which equates to 10px, or 0.625em.

Now you can set the `font-size` for any elements using em units, with an easy-to-remember conversion, by dividing the `px` value by 10. This way `10px = 1em`, `12px = 1.2em`, `14px = 1.4em`, `16px = 1.6em`, and so on. See the example below:

#### Example

```css
body {
    font-size: 62.5%;    /* font-size 1em = 10px */
}
p {
    font-size: 1.6em;    /* 1.6em = 16px */
}
```

**Tip:** The [World Wide Web consortium's (W3C)](http://www.w3.org/Style/CSS/Overview.en.html) recommends using the em or percentage (%) values in order to create more robust and scalable layouts.

* * *

## Font Weight

The `font-weight` property specifies the weight or boldness of the font.

The possible values of font-style property are: `normal`, `bold`, `bolder`, `lighter`, `100`, `200`, `300`, `400`, `500`, `600`, `700`, `800`, `900` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

*   The numeric values `100`-`900` specify the font weights, where each number represents a weight darker than its predecessor. `400` is same as `normal` & `700` is same as `bold`.
*   The `bolder` and `lighter` values are relative to the inherited font weight, while the other values are absolute font weights.

#### Example

```css
p {
    font-weight: bold;
}
```

Since most of the fonts are only available in a limited number of weights; often they are available only in _normal_ and _bold_. If the font isn't available in the specified weight, an alternate will be chosen that is the closest available weight.

* * *

## Font Variant

The `font-variant` property allows the text to be displayed in a special small-caps variation.

Small-caps or _small capital letters_ are slightly different to normal capital letters, in which lowercase letters appear as smaller versions of the corresponding uppercase letters.

The possible values for the `font-variant` property are `normal`, `small-caps` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

#### Example

```css
p {
    font-variant: small-caps;
}
```
* * *