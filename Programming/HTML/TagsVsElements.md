Tags Vs Elements

# HTML Elements

In this tutorial you will learn about HTML tags and elements.

## HTML Element Syntax

An HTML element is an individual component of an HTML document. It represents semantics, or meaning. For example, the `title` element represents the title of the document.

Most HTML elements are written with a _start tag_ (or opening tag) and an _end tag_ (or closing tag), with content in between. Elements can also contain attributes that defines its additional properties. For example, a paragraph, which is represented by the `p` element, would be written as:

![HTML Element Syntax Illustration](../../../../_resources/f09f34a02b2d4bf09f596f8199246146.png)

We will learn about the HTML attributes in the [next chapter](https://www.tutorialrepublic.com/html-tutorial/html-attributes.php).

**Note:** All elements don't require the end tag or closing tag to be present. These are referred as _empty elements_, _self-closing elements_ or _void elements_.

* * *

## HTML Tags Vs Elements

Technically, an HTML element is the collection of start tag, its attributes, an end tag and everything in between. On the other hand an HTML tag (either opening or closing) is used to mark the start or end of an element, as you can see in the above illustration.

However, in common usage the terms HTML element and HTML tag are interchangeable i.e. a tag is an element is a tag. For simplicity's sake of this website, the terms "tag" and "element" are used to mean the same thing — as it will define something on your web page.

* * *

## Case Insensitivity in HTML Tags and Attributes

In HTML, tag and attribute names are not case-sensitive (but most attribute values are case-sensitive). It means the tag `<P>`, and the tag `<p>` defines the same thing in HTML which is a paragraph.

But in [XHTML](https://www.tutorialrepublic.com/html-tutorial/../xhtml-tutorial.php) they are case-sensitive and the tag `<P>` is different from the tag `<p>`.

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=case-insensitivity "Try this code using online Editor")

```markup
<p>This is a paragraph.</p>
<P>This is also a valid paragraph.</P>
```

**Tip:** We recommend using lowercase for tag and attributing names in HTML, since by doing this you can make your document more compliant for future upgrades.

* * *

## Empty HTML Elements

Empty elements (also called self-closing or void elements) are not container tags — that means, you can not write `<hr>_some content_</hr>` or `<br>_some content_</br>`.

A typical example of an empty element, is the `<br>` element, which represents a line break. Some other common empty elements are `<img>`, `<input>`, `<link>`, `<meta>`, `<hr>`, etc.

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=empty-elements "Try this code using online Editor")

```markup
<p>This paragraph contains <br> a line break.</p>
<img src="images/sky.jpg" alt="Cloudy Sky">
<input type="text" name="username">
```

**Note:** In HTML, a self-closing element is written simply as `[<br>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-br-tag.php)`. In XHTML, a self-closing element requires a space and a trailing slash, such as `<br />`.

* * *

## Nesting HTML Elements

Most HTML elements can contain any number of further elements (except [empty elements](#empty-elements)), which are, in turn, made up of tags, attributes, and content or other elements.

The following example shows some elements nested inside the `<p>` element.

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=nesting-elements "Try this code using online Editor")

```markup
<p>Here is some <b>bold</b> text.</p>
<p>Here is some <em>emphasized</em> text.</p>
<p>Here is some <mark>highlighted</mark> text.</p>
```

**Tip:** Placing one element inside another is called nesting. A nested element, also called a child element, can be a parent element too if other elements are nested within it.

HTML tags should be nested in correct order. They must be closed in the inverse order of how they are defined, that means the last tag opened must be closed first.

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=nesting-order "Try this code using online Editor")

```markup
<p><strong>These tags are nested properly.</strong></p>
<p><strong>These tags are not nested properly.</p></strong>
```

* * *

## Writing Comments in HTML

Comments are usually added with the purpose of making the source code easier to understand. It may help other developer (or you in the future when you edit the source code) to understand what you were trying to do with the HTML. Comments are not displayed in the browser.

An HTML comment begins with `<!--`, and ends with `-->`, as shown in the example below:

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=comment-syntax "Try this code using online Editor")

```markup
<!-- This is an HTML comment -->
<!-- This is a multi-line HTML comment 
     that spans across more than one line -->
<p>This is a normal piece of text.</p>
```

You can also comment out part of your HTML code for debugging purpose, as shown here:

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=commenting-code "Try this code using online Editor")

```markup
<!-- Hiding this image for testing
<img src="images/smiley.png" alt="Smiley">
-->
```

* * *

## HTML Elements Types

Elements can be placed in two distinct groups: _[block level](https://www.tutorialrepublic.com/html-tutorial/../css-tutorial/css-visual-formatting.php#block-level)_ and _[inline level](https://www.tutorialrepublic.com/html-tutorial/../css-tutorial/css-visual-formatting.php#inline-level)_ elements. The former make up the document's structure, while the latter dress up the contents of a block.

Also, a block element occupies 100% of the available width and it is rendered with a line break before and after. Whereas, an inline element will take up only as much space as it needs.

The most commonly used block-level elements are `<div>`, `<p>`, `<h1>` through `<h6>`, `<form>`, `<ol>`, `<ul>`, `<li>`, and so on. Whereas, the commonly used inline-level elements are `<img>`, `<a>`, `<span>`, `<strong>`, `<b>`, `<em>`, `<i>`, `<code>`, `<input>`, `<button>`, etc.

You will learn about these elements in detail in upcoming chapters.

**Note:** The block-level elements should not be placed within inline-level elements. For example, the `<p>` element should not be placed inside the `<b>` element.
