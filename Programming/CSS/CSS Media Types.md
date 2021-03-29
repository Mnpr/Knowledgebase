CSS Media Types

# CSS Media Types

CSS media types allow you to format your documents to be presented correctly on various types of media such as screen, print, an aural browser, etc.

## Introduction to Media Types

One of the most important features of style sheets is that, you can specify separate style sheets for different media types. This is one of the best ways to build printer friendly Web pages — Just assign a different style sheet for the "print" media type.

Some CSS properties are only designed for certain media. For example, the [`page-break-after`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-page-break-after-property.php) property only applies to paged media. However there are several properties that may be shared by different media types, but may require different values for that property. The [`font-size`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-font-size-property.php) property for example can be used for both screen and print media, but possibly with different values.

A document usually needs a larger font on a computer screen as compared to the paper for better readability, also sans-serif fonts are considered easier to read on the screen, while serif fonts are popular for printing. Therefore it is necessary to specify that a style sheet, or a set of style rules, applies to certain media types.

## Creating Media Dependent Style Sheets

Three methods are commonly used to specify the media dependencies for style sheets:

## Method 1: Using the `@media` At-rules

The `@media` rule is used to define different style rules for different media types in a single style sheet. It is usually followed by a comma-separated list of media types and the CSS declarations block containing the styles rules for target media.

The style declaration in the example below tells the browser to display body content in 14 pixels Arial font on the screen, but in case of printing it will be in a 12 points Times font. However the value of [`line-height`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-line-height-property.php) property is set to 1.2 for both of them:

#### Example

```css
@media screen{
    body {
        color: #32cd32;
        font-family: Arial, sans-serif;
        font-size: 14px;
    }
}
@media print {
    body {
        color: #ff6347;
        font-family: Times, serif;
        font-size: 12pt;
    }
}
@media screen, print {
    body {
        line-height: 1.2;
    }
}
```

**Note:** Style rules outside of [`@media`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-media-rule.php) rules apply to all media types that the style sheet applies to. At-rules inside `@media` are invalid in CSS2.1.

* * *

## Method 2: Using the `@import` At-rules

The `@import` rule is another way of setting style information for a specific target media — Just specify the comma-separated media types after the URL of the imported style sheets.

#### Example

```css
@import url("css/screen.css") screen;
@import url("css/print.css") print;
body {
    background: #f5f5f5;
    line-height: 1.2;
}
```

The `print` media type in the `@import` statement instructs the browser to load an external style sheet (print.css) and use its styles only for print media.

**Note:** All [`@import`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-import-rule.php) statements must occur at the beginning of a style sheet, before any declarations. Any style rule specified in the style sheet itself override the conflicting style rules in the imported style sheets.

* * *

## Method 3: Using the `<link>` element

The `media` attribute on the [`<link>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-link-tag.php) element is used to specify the target media for an external style sheet within the HTML document.

#### Example

```markup
<link rel="stylesheet" media="all" href="css/common.css">
<link rel="stylesheet" media="screen" href="css/screen.css">
<link rel="stylesheet" media="print" href="css/print.css">
```

In this example the `media` attribute instructs the browser to load an external style sheet "screen.css" and use its styles only for screen while "print.css" for printing purpose.

**Tip:** You can also specify multiple media types (each separated with comma e.g. `media="screen, print"`) as well as media quires to the `<link>` element.

* * *

## Different Media Types

The following table lists the various media types that may used to target different types of devices such as printers, handheld devices, computer screens etc.

| Media Type | Description |
| --- | --- |
| `all` | Used for all media type devices. |
| `aural` | Used for speech and sound synthesizers. |
| `braille` | Used for braille tactile feedback devices. |
| `embossed` | Used for paged braille printers. |
| `handheld` | Used for small or handheld devices — usually small screen devices such as mobile phones or PDAs. |
| `print` | Used for printers. |
| `projection` | Used for projected presentations, for example projectors. |
| `screen` | Used primarily for color computer screens. |
| `tty` | Used for media using a fixed-pitch character grid — such as teletypes, terminals, or portable devices with limited display capabilities. |
| `tv` | Used for television-type devices — low resolution, color, limited-scrollability screens, sound available. |

**Warning:** However there are several media types to choose from but most of the browser only support `all`, `screen` and `print` media types.

* * *