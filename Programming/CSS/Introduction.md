Introduction

# CSS Tutorial

CSS is the key presentational technology that is used in website design.

CSS stands for Cascading Style Sheets. CSS is a standard style sheet language used for describing the presentation (i.e. the layout and formatting) of the web pages.

Prior to CSS, nearly all of the presentational attributes of HTML documents were contained within the HTML markup (specifically inside the HTML tags); all the font colors, background styles, element alignments, borders and sizes had to be explicitly described within the HTML.

As a result, development of the large websites became a long and expensive process, since the style information were repeatedly added to every single page of the website.

To solve this problem CSS was introduced in 1996 by the World Wide Web Consortium (W3C), which also maintains its standard. CSS was designed to enable the separation of presentation and content. Now web designers can move the formatting information of the web pages to a separate style sheet which results in considerably simpler HTML markup, and better maintainability.

CSS3 is the latest version of the CSS specification. CSS3 adds several new styling features and improvements to enhance the web presentation capabilities.

**Note:** Our CSS tutorial will help you to learn the fundamentals of the latest CSS3 language, from the basic to advanced topics step-by-step. If you're a beginner, start with the basic section and gradually move forward by learning a little bit every day.

* * *

## What You Can Do with CSS

There are lot more things you can do with CSS.

*   You can easily apply same style rules on multiple elements.
*   You can control the presentation of multiple pages of a website with a single style sheet.
*   You can present the same page differently on different devices.
*   You can style dynamic states of elements such as hover, focus, etc. that isn't possible otherwise.
*   You can change the position of an element on a web page without changing the markup.
*   You can alter the display of existing HTML elements.
*   You can transform elements like scale, rotate, skew, etc. in 2D or 3D space.
*   You can create animations and transitions effects without using any JavaScript.
*   You can create print friendly version of your web pages.

The list does not end here, there are many other interesting things that you can do with CSS. You will learn about all of them in detail in upcoming chapters.

* * *

## Advantages of Using CSS

The biggest advantage of CSS is that it allows the separation of style and layout from the content of the document. Here are some more advantages, why one should start using CSS?

*   **CSS Save Lots of Time** — CSS gives lots of flexibility to set the style properties of an element. You can write CSS once; and then the same code can be applied to the groups of HTML elements, and can also be reused in multiple HTML pages.
*   **Easy Maintenance** — CSS provides an easy means to update the formatting of the documents, and to maintain the consistency across multiple documents. Because the content of the entire set of web pages can be easily controlled using one or more style sheets.
*   **Pages Load Faster** — CSS enables multiple pages to share the formatting information, which reduces complexity and repetition in the structural contents of the documents. It significantly reduces the file transfer size, which results in a faster page loading.
*   **Superior Styles to HTML** — CSS has much wider presentation capabilities than HTML and provide much better control over the layout of your web pages. So you can give far better look to your web pages in comparison to the HTML presentational elements and attributes.
*   **Multiple Device Compatibility** — CSS also allows web pages to be optimized for more than one type of device or media. Using CSS the same HTML document can be presented in different viewing styles for different rendering devices such as desktop, cell phones, etc.

**Tip:** Now most of the [HTML attributes](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-attributes.php) are being deprecated and it's not recommended to use. So it's a good idea to use as much CSS as possible to increase the adaptability your website and make them compatible to future browsers, as well.

* * *

## What This Tutorial Covers

This CSS tutorial series covers all the fundamentals of CSS, including the idea of selectors, methods of setting colors and backgrounds, way of formatting fonts and text, styling UI elements such as hyperlinks, lists, tables, etc. as well as the concept of CSS box model, and so on.

Once you're comfortable with the basics, you'll move on to next level that explains the way of setting dimension and alignment of elements, methods for positioning elements on a web page, using image sprites, as well as the concept of relative and absolute units, visual formatting model, display and visibility, layers, pseudo classes and elements, media dependent style sheets, and so on.

Finally, you'll explore some advanced features introduced in CSS3 like gradient colors, drop shadow effect, 2D and 3D transforms, alpha transparency, as well as the method of creating transition and animation effect, flex layouts, filter effect, the concept of media queries, and more.

**Tip:** Every chapter in this tutorial contains lots of real-world examples that you can try and test using an online editor. These examples will help you to better understand the concept or topic. It also contains smart workarounds as well as useful tips and important notes.

* * *

## Getting Started with CSS

In this tutorial you'll learn how easy it is to add style and formatting information to the web pages using CSS. But, before we begin, make sure that you have some working knowledge of HTML.

If you're just starting out in the world of web development, start learning from here » [INDEX HTML](:/d5fda4c2591c4cfcb875dfadfc9dfe3f)

## Including CSS in HTML Documents

CSS can either be attached as a separate document or embedded in the HTML document itself. There are three methods of including CSS in an HTML document:

*   **Inline styles** — Using the `style` attribute in the HTML start tag.
*   **Embedded styles** — Using the `<style>` element in the head section of a document.
*   **External style sheets** — Using the `<link>` element, pointing to an external CSS file.

In this tutorial we will cover all these three methods for inserting CSS one by one.

**Note:** The inline styles have the highest priority, and the external style sheets have the lowest. It means if you specify styles for an element in both _embedded_ and _external_ style sheets, the conflicting style rules in the embedded style sheet would override the external style sheet.

## Inline Styles

Inline styles are used to apply the unique style rules to an element by putting the CSS rules directly into the start tag. It can be attached to an element using the `style` attribute.

The `style` attribute includes a series of CSS property and value pairs. Each `"property: value"` pair is separated by a semicolon (`;`), just as you would write into an embedded or external style sheets. But it needs to be all in one line i.e. no line break after the semicolon, as shown here:

#### Example

```markup
<h1 style="color:red; font-size:30px;">This is a heading</h1>
<p style="color:green; font-size:22px;">This is a paragraph.</p>
<div style="color:blue; font-size:14px;">This is some text content.</div>
```

Using the inline styles are generally considered as a bad practice. As style rules are embedded directly inside the HTML tag, it causes the presentation to become mixed with the content of the document; which makes the code hard to maintain and negates the purpose of using CSS.

**Note:** It's become impossible to style [pseudo-elements](https://www.tutorialrepublic.com/css-tutorial/../css-tutorial/css-pseudo-elements.php) and [pseudo-classes](https://www.tutorialrepublic.com/css-tutorial/../css-tutorial/css-pseudo-classes.php) with inline styles. You should, therefore, avoid the use of style attributes in your code. Using [external style sheets](#external-style-sheet) is the preferred way to add styles to the HTML documents.

* * *

## Embedded Style Sheets

Embedded or internal style sheets only affect the document they are embedded in.

Embedded style sheets are defined in the [`<head>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-head.php) section of an HTML document using the [`<style>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-style-tag.php) element. You can define any number of `<style>` elements in an HTML document but they must appear between the `<head>` and `</head>` tags. Let's take a look at an example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My HTML Document</title>
    <style>
        body { background-color: YellowGreen; }
        p { color: #fff; }
    </style>
</head>
<body>
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</body>
</html>
```

**Tip:** The `type` attribute of the `<style>` and `<link>` tag (i.e. `type="text/css"`) defines the language of the style sheet. This attribute is purely informative. You can omit this since CSS is the standard and default style sheet language in HTML5.

* * *

## External Style Sheets

An external style sheet is ideal when the style is applied to many pages of the website.

An external style sheet holds all the style rules in a separate document that you can link from any HTML file on your site. External style sheets are the most flexible because with an external style sheet, you can change the look of an entire website by changing just one file.

You can attach external style sheets in two ways — _linking_ and _importing_.

### Linking External Style Sheets

Before linking, we need to create a style sheet first. Let's open your favorite code editor and create a new file. Now type the following CSS code inside this file and save it as "style.css".

#### Example

Try this code »

```css
body {
    background: lightyellow;
    font: 18px Arial, sans-serif;
}
h1 {
    color: orange;
}
```

An external style sheet can be linked to an HTML document using the [`<link>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-link-tag.php) tag. The `<link>` tag goes inside the [`<head>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-head-tag.php) section, as you can see in the following example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My HTML Document</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</body>
</html>
```

**Tip:** Among all the three methods, using external style sheet is the best method for defining and applying styles to the HTML documents. As you can clearly see with external style sheets, the affected HTML file require minimal changes in the markup.

### Importing External Style Sheets

The `@import` rule is another way of loading an external style sheet. The `@import` statement instructs the browser to load an external style sheet and use its styles.

You can use it in two ways. The simplest is within the header of your document. Note that, other CSS rules may still be included in the [`<style>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-style-tag.php) element. Here's an example:

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

**Note:** All [`@import`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-import-rule.php) rules must occur at the start of the style sheet. Any style rule defined in the style sheet itself override the conflicting rules in the imported style sheets. However, importing a style sheet within another style sheet is not recommended due to performance issue.
* * *

## Understanding CSS Syntax

A CSS stylesheet consists of a set of rules that are interpreted by the web browser and then applied to the corresponding elements such as paragraphs, headings, etc. in the document.

A CSS rule have two main parts, a selector and one or more declarations:

![CSS Selector Syntax Illustration](../../../../_resources/874a04d42cc34db599acd1d006dcfc1e.png)

The selector specifies which element or elements in the HTML page the CSS rule applies to.

Whereas, the declarations within the block determines how the elements are formatted on a webpage. Each declaration consists of a property and a value separated by a colon (`:`) and ending with a semicolon (`;`), and the declaration groups are surrounded by curly braces `{}`.

The property is the style attribute you want to change; they could be font, color, background, etc. Each property has a value, for example color property can have value either `blue` or `#0000FF` etc.

h1 {color:blue; text-align:center;}

To make the CSS more readable, you can put one declaration on each line, like this:

#### Example

```css
h1 {
    color: blue;
    text-align: center;
}
```

In the example above `h1` is a selector, `color` and `text-align` are the CSS properties, and the given `blue` and `center` are the corresponding values of these properties.

**Note:** A CSS declaration always ends with a semicolon "`;`", and the declaration groups are always surrounded by the curly brackets "`{}`".

* * *

## Writing Comments in CSS

Comments are usually added with the purpose of making the source code easier to understand. It may help other developer (or you in the future when you edit the source code) to understand what you were trying to do with the CSS. Comments are significant to programmers but ignored by browsers.

A CSS comment begins with `/*`, and ends with `*/`, as shown in the example below:

#### Example

```css
/* This is a CSS comment */
h1 {
    color: blue;
    text-align: center;
}
/* This is a multi-line CSS comment 
that spans across more than one line */
p {
    font-size: 18px;
    text-transform: uppercase;
}
```

You can also comment out part of your CSS code for debugging purpose, as shown here:

#### Example

```css

h1 {
    color: blue;
    text-align: center;
}
/*
p {
    font-size: 18px;
    text-transform: uppercase;
}
*/
```

* * *

## Case Sensitivity in CSS

CSS property names and many values are not case-sensitive. Whereas, CSS selectors are usually case-sensitive, for instance, the class selector `.maincontent` is not the same as `.mainContent`.

Therefore, to be on safer side, you should assume that all components of CSS rules are case-sensitive.

You will learn about the various types of CSS selectors in the [next chapter](https://www.tutorialrepublic.com/css-tutorial/css-selectors.php).
* * *