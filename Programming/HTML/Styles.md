HTML Styles

# HTML Styles

In this tutorial you will learn how to apply style rules to HTML elements.

## Styling HTML Elements

HTML is quite limited when it comes to the presentation of a web page. It was originally designed as a simple way of presenting information. [CSS (Cascading Style Sheets)](https://www.tutorialrepublic.com/css-tutorial/) was introduced in December 1996 by the [World Wide Web Consortium (W3C)](https://en.wikipedia.org/wiki/World_Wide_Web_Consortium) to provide a better way to style HTML elements.

With CSS, it becomes very easy to specify the things like, size and typeface for the fonts, colors for the text and backgrounds, alignment of the text and images, amount of space between the elements, border and outlines for the elements, and lots of other styling properties.

## Adding Styles to HTML Elements

Style information can either be attached as a separate document or embedded in the HTML document itself. These are the three methods of implementing styling information to an HTML document.

*   **Inline styles** — Using the `style` attribute in the HTML start tag.
*   **Embedded style** — Using the [`<style>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-style-tag.php) element in the head section of the document.
*   **External style sheet** — Using the [`<link>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-link-tag.php) element, pointing to an external CSS files.

In this tutorial we will cover all these different types of style sheet one by one.

**Note:** The inline styles have the highest priority, and the external style sheets have the lowest. It means if you specify styles for your paragraphs in both _embedded_ and _external_ style sheets, the conflicting style rules in the embedded style sheet would override the external style sheet.

## Inline Styles

Inline styles are used to apply the unique style rules to an element, by putting the CSS rules directly into the start tag. It can be attached to an element using the `style` attribute.

The style attribute includes a series of CSS property and value pairs. Each `property: value` pair is separated by a semicolon (`;`), just as you would write into an embedded or external style sheet. But it needs to be all in one line i.e. no line break after the semicolon.

The following example demonstrates how to set the [`color`](https://www.tutorialrepublic.com/html-tutorial/../css-reference/css-color-property.php) and [`font-size`](https://www.tutorialrepublic.com/html-tutorial/../css-reference/css-font-size-property.php) of the text:

#### Example

```markup
<h1 style="color:red; font-size:30px;">This is a heading</h1>
<p style="color:green; font-size:18px;">This is a paragraph.</p>
<div style="color:green; font-size:18px;">This is some text.</div>
```

Using the inline styles are generally considered as a bad practice. Because style rules are embedded directly inside the html tag, it causes the presentation to become mixed with the content of the document, which makes updating or maintaining a website very difficult.

To learn about the various CSS properties in detail, please check out [CSS tutorial](https://www.tutorialrepublic.com/css-tutorial/) section.

**Note:** It's become impossible to style [pseudo-elements](https://www.tutorialrepublic.com/html-tutorial/../css-tutorial/css-pseudo-elements.php) and [pseudo-classes](https://www.tutorialrepublic.com/html-tutorial/../css-tutorial/css-pseudo-classes.php) with inline styles. You should, therefore, avoid the use of `style` attributes in your markup. Using [external style sheet](#external-style-sheet) is the preferred way to add style information to an HTML document.

* * *

## Embedded Style Sheets

Embedded or internal style sheets only affect the document they are embedded in.

Embedded style sheets are defined in the [`<head>`](https://www.tutorialrepublic.com/html-tutorial/../html-tutorial/html-head.php) section of an HTML document using the `<style>` tag. You can define any number of `<style>` elements inside the `<head>` section.

The following example demonstrates how style rules are embedded inside a web page.

#### Example

```markup
<head>
    <style>
        body { background-color: YellowGreen; }
		h1 { color: blue; }
        p { color: red; }
    </style>
</head>
```

* * *

## External Style Sheets

An external style sheet is ideal when the style is applied to many pages.

An external style sheet holds all the style rules in a separate document that you can link from any HTML document on your site. External style sheets are the most flexible because with an external style sheet, you can change the look of an entire website by updating just one file.

You can attach external style sheets in two ways — _linking_ and _importing_:

## Linking External Style Sheets

An external style sheet can be linked to an HTML document using the [`<link>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-link-tag.php) tag.

The `<link>` tag goes inside the [`<head>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-head-tag.php) section, as shown here:

#### Example

```markup
<head>
    <link rel="stylesheet" href="css/style.css">
</head>
```

## Importing External Style Sheets

The `@import` rule is another way of loading an external style sheet. The `@import` statement instructs the browser to load an external style sheet and use its styles.

You can use it in two ways. The simplest way is to use it within the [`<style>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-style-tag.php) element in your `<head>` section. Note that, other CSS rules may still be included in the `<style>` element.

#### Example


```markup
<style>
    @import url("css/style.css");
    p {
        color: blue;
        font-size: 16px;
    }
</style>
```

Similarly, you can use the `@import` rule to import a style sheet within another style sheet.

#### Example

```css
@import url("css/layout.css");
@import url("css/color.css");
body {
    color: blue;
    font-size: 14px;
}
```

**Note:** All `[@import](https://www.tutorialrepublic.com/html-tutorial/../css-reference/css-import-rule.php)` rules must occur at the start of the style sheet. Any style rule defined in the style sheet itself override conflicting rule in the imported style sheets. The `@import` rule may cause performance issues, you should generally avoid importing style sheets.

* * *