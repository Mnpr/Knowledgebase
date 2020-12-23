Headings and Paragraphs

# HTML Headings

In this tutorial you will learn how to create headings in HTML.

## Organizing Content with Headings

Headings help in defining the hierarchy and the structure of the web page content.

HTML offers six levels of heading tags, `<h1>` through `<h6>`; the higher the heading level number, the greater its importance — therefore `<h1>` tag defines the most important heading, whereas the `<h6>` tag defines the least important heading in the document.

By default, browsers display headings in larger and bolder font than normal text. Also, `<h1>` headings are displayed in largest font, whereas `<h6>` headings are displayed in smallest font.

#### Example

```markup
<h1>Heading level 1</h1>
<h2>Heading level 2</h2>
<h3>Heading level 3</h3>
<h4>Heading level 4</h4>
<h5>Heading level 5</h5>
<h6>Heading level 6</h6>
```

— The output of the above example will look something like this:

[![HTML Headings](../../../../_resources/a98af3ad6ae3419ea2e40fb6e0010c59.png)](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=headings)

**Note:** Each time you place a heading tag on a web page, the web browser built-in style sheets automatically create some empty space (called margin) before and after each heading. You can use the CSS `[margin](https://www.tutorialrepublic.com/html-tutorial/../css-reference/css-margin-property.php)` property to override the browser's default style sheet.

**Tip:** You can easily customize the appearance of HTML heading tags such as their font size, boldness, typeface, etc. using the CSS [font](https://www.tutorialrepublic.com/css-reference/css-font-property.php) properties.

* * *

## Importance of Headings

*   HTML headings provide valuable information by highlighting important topics and the structure of the document, so optimize them carefully to improve user engagement.
*   Don't use headings to make your text look BIG or bold. Use them only for highlighting the heading of your document and to show the document structure.
*   Since search engines, such as Google, use headings to index the structure and content of the web pages so use them very wisely in your webpage.
*   Use the `<h1>` headings as main headings of your web page, followed by the `<h2>` headings, then the less important `<h3>` headings, and so on.

**Tip:** Use the `<h1>` tag to mark the most important heading which is usually at the top of the page. An HTML document generally should have exactly one `<h1>` heading, followed by the lower-level headings such as `<h2>`, `<h3>`, `<h4>`, and so on.
* * *
# HTML Paragraphs

In this tutorial you will learn how to create paragraphs in HTML.

## Creating Paragraphs

Paragraph element is used to publish text on the web pages.

Paragraphs are defined with the `<p>` tag. Paragraph tag is a very basic and typically the first tag you will need to publish your text on the web pages. Here's an example:

#### Example

```markup
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

**Note:** Browsers built-in style sheets automatically create some space above and below the content of a paragraph (called [margin](https://www.tutorialrepublic.com/css-reference/css-margin-property.php)), but you can override it using CSS.

* * *

## Closing a Paragraph Element

In HTML 4 and earlier versions, it was enough to initiate a new paragraph using the opening tag. Most browsers will display HTML correctly even if you forget the end tag. For example:

#### Example

```markup
<p>This is a paragraph.
<p>This is another paragraph.
```

The HTML code in the example above will work in most of the web browsers, but don't rely on it. Forgetting the end tag can produce unexpected results or errors.

**Note:** For the purposes of forwards-compatibility and good coding practice, it's advisable to use both the opening and closing tags for the paragraphs.

* * *

## Creating Line Breaks

The `<br>` tag is used to insert a line break on the web page.

Since the `<br>` is an [empty element](https://www.tutorialrepublic.com/html-tutorial/html-elements.php#empty-elements), so there is no need of corresponding `</br>` tag.

#### Example

```markup
<p>This is a paragraph <br> with line break.</p>
<p>This is <br>another paragraph <br> with line breaks.</p>
```

**Note:** Don't use the empty paragraph i.e. `<p></p>` to add extra space in your web pages. The browser may ignore the empty paragraphs since it is logical tag. Use the CSS `[margin](https://www.tutorialrepublic.com/html-tutorial/../css-reference/css-margin-property.php)` property instead to adjust the space around the elements.

* * *

## Creating Horizontal Rules

You can use the `<hr>` tag to create horizontal rules or lines to visually separate content sections on a web page. Like `<br>`, the `<hr>` tag is also an empty element. Here's an example:

#### Example

```markup
<p>This is a paragraph.</p>
<hr>
<p>This is another paragraph.</p>
```

* * *

## Managing White Spaces

Normally the browser will display the multiple spaces created inside the HTML code by pressing the _space-bar key_ or _tab key_ on the keyboard as a single space. Multiple line breaks created inside the HTML code through pressing the enter key is also displayed as a single space.

The following paragraphs will be displayed in a single line without any extra space:

#### Example

```markup
<p>This paragraph contains  multiple   spaces    in the source code.</p>
<p>
    This paragraph
    contains multiple tabs and line breaks
    in the source code.
</p>
```

Insert `&nbsp;` for creating extra consecutive spaces, while insert `<br>` tag for creating line breaks on your web pages, as demonstrated in the following example:

#### Example

```markup
<p>This paragraph has multiple&nbsp;&nbsp;&nbsp;spaces.</p>
<p>This paragraph has multiple<br><br>line<br><br><br>breaks.</p>
```

* * *

## Defining Preformatted Text

Sometimes, using `&nbsp;`, `<br>`, etc. for managing spaces isn't very convenient. Alternatively, you can use the `<pre>` tag to display spaces, tabs, line breaks, etc. exactly as written in the HTML file. It is very helpful in presenting text where spaces and line breaks are important like poem or code.

The following example will display the text in the browser as it is in the source code:

#### Example

```markup
<pre>
    Twinkle, twinkle, little star, 
    How I wonder what you are! 
    Up above the world so high, 
    Like a diamond in the sky.
</pre>
```

**Tip:** Text within the `<pre>` element is typically rendered by the browsers in a monospace or fixed-width font, such as Courier, but you can override this using the CSS [`font`](https://www.tutorialrepublic.com/css-reference/css-font-property.php) property.
* * *