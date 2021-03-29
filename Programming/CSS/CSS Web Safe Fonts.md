CSS Web Safe Fonts

# CSS Web Safe Fonts

Web-safe fonts are fonts that are extremely common and most likely to be present on a wide range of operating systems like Windows, Mac, Linux etc.

## Why Choose Web Safe Fonts

It may be a situation when the fonts you are trying to use on your web pages are not appeared as it should be, because all fonts are not available on all computer system.

To ensure the exact rendering of your text on most of the browser or operating systems you have to define your fonts very carefully. The `[font-family](https://www.tutorialrepublic.com/css-reference/css-font-family-property.php)` CSS property can hold several font names as a fallback system. Start with the font that you want first, then the fonts you might want to fill in for the first if it is not available.

You should always end the list with a generic font family, which are five: `serif`, `sans-serif`, `monospace`, `cursive` and `fantasy`. The generic font family allows the browser to select a similar font, if no any fonts defined by your are available.

The following table lists the font's combinations that are most safe to use.

| font-family | Normal | Bold |
| --- | --- | --- |
| Arial, Helvetica, sans-serif | This is normal text. | **This is bold text.** |
| "Times New Roman", Times, serif | This is normal text. | **This is bold text.** |
| "Courier New", Courier, monospace | This is normal text. | **This is bold text.** |

The following example shows you how to set the `font-family` property in correct manner.

#### Example

*   `.sans-serif-font {`
*   `    font-family: Arial, Helvetica, sans-serif;`
*   `}`
*   `.serif-font {`
*   `    font-family: "Times New Roman", Times, serif;`
*   `}`
*   `.monospace-font {`
*   `    font-family: "Courier New", Courier, monospace;`
*   `}`

* * *

## Commonly Used Font Combinations

The following table lists some commonly used font combinations, organized by generic family.

### Serif Fonts

| font-family | Normal | Bold |
| --- | --- | --- |
| Georgia, serif | This is normal text. | **This is bold text.** |
| "Times New Roman", Times, serif | This is normal text. | **This is bold text.** |
| "Palatino Linotype", Palatino, "Book Antiqua", serif | This is normal text. | **This is bold text.** |

### Sans-Serif Fonts

| font-family | Normal | Bold |
| --- | --- | --- |
| Arial, Helvetica, sans-serif | This is normal text. | **This is bold text.** |
| "Arial Black", Gadget, sans-serif | This is normal text. | **This is bold text.** |
| Impact, Charcoal, sans-serif | This is normal text. | **This is bold text.** |
| Tahoma, Geneva, sans-serif | This is normal text. | **This is bold text.** |
| "Trebuchet MS", Helvetica, sans-serif | This is normal text. | **This is bold text.** |
| Verdana, Geneva, sans-serif | This is normal text. | **This is bold text.** |

### Monospace Fonts

| font-family | Normal | Bold |
| --- | --- | --- |
| Courier, monospace | This is normal text. | **This is bold text.** |
| "Courier New", Courier, monospace | This is normal text. | **This is bold text.** |
| "Lucida Console", Monaco, monospace | This is normal text. | **This is bold text.** |

### Cursive Fonts

| font-family | Normal | Bold |
| --- | --- | --- |
| "Comic Sans MS", cursive | This is normal text. | **This is bold text.** |
| "Courier New", Courier, monospace | This is normal text. | **This is bold text.** |
| "Lucida Console", Monaco, monospace | This is normal text. | **This is bold text.** |

### Fantasy Fonts

There are no fantasy fonts that have good availability across browsers and operating systems.

**Warning:** The fonts (Verdana, Georgia, "Comic Sans MS", "Trebuchet MS", "Arial Black", Impact) are work on Windows and MacOS but not Unix+X.
* * *