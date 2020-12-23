Text Formatting Tags

# HTML Text Formatting

In this tutorial you will learn how to format the text on the web pages using HTML tags.

## Formatting Text with HTML

HTML provides several tags that you can use to make some text on your web pages to appear differently than normal text, for example, you can use the tag `<b>` to make the text bold, tag `<i>` to make the text italic, tag `<mark>` to highlight the text, tag `<code>` to display a fragment of computer code, tags `<ins>` and `<del>` for marking editorial insertions and deletions, and more.

The following example demonstrates the most commonly used formatting tags in action. Now, let's try this out to understand how these tags basically work:

#### Example

```markup
<p>This is <b>bold text</b>.</p>
<p>This is <strong>strongly important text</strong>.</p>
<p>This is <i>italic text</i>.</p>
<p>This is <em>emphasized text</em>.</p>
<p>This is <mark>highlighted text</mark>.</p>
<p>This is <code>computer code</code>.</p>
<p>This is <small>smaller text</small>.</p>
<p>This is <sub>subscript</sub> and <sup>superscript</sup> text.</p>
<p>This is <del>deleted text</del>.</p>
<p>This is <ins>inserted text</ins>.</p>
```

By default, the `<strong>` tag is typically rendered in the browser as `<b>`, whereas the `<em>` tag is rendered as `<i>`. However, there is a difference in the meaning of these tags.

### Difference between &lt;strong&gt; and &lt;b&gt; tag

Both `<strong>` and `<b>` tags render the enclosed text in a bold typeface by default, but the `<strong>` tag indicates that its contents have strong importance, whereas the `<b>` tag is simply used to draw the reader's attention without conveying any special importance.

#### Example

```markup
<p><strong>WARNING!</strong> Please proceed with caution.</p>
<p>The concert will be held at <b>Hyde Park</b> in London.</p>
```

### Difference between &lt;em&gt; and &lt;i&gt; tag

Similarly, both `<em>` and `<i>` tags render the enclosed text in italic type by default, but the `<em>` tag indicates that its contents have stressed emphasis compared to surrounding text, whereas the `<i>` tag is used for marking up text that is set off from the normal text for readability reasons, such as a technical term, an idiomatic phrase from another language, a thought, etc.

#### Example

```markup
<p>Cats are <em>cute</em> animals.</p>
<p>The <i>Royal Cruise</i> sailed last night.</p>
```

**Note:** Use the [`<em>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-em-tag.php) and [`<strong>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-strong-tag.php) tags when the content of your page requires that certain words or phrases should have strong emphasis or importance. Also, in HTML5 the `<b>` and `<i>` tags have been redefined, earlier they don't have semantic meaning.

* * *

## Formatting Quotations

You can easily format the quotation blocks from other sources with the HTML `<blockquote>` tag.

Blockquotes are generally displayed with indented left and right margins, along with a little extra space added above and below. Let's try an example to see how it works:

#### Example

```markup
<blockquote>
    <p>Learn from yesterday, live for today, hope for tomorrow. The important thing is not to stop questioning.</p>
    <cite>— Albert Einstein</cite>
</blockquote>
```

**Tip:** The [`cite`](https://www.tutorialrepublic.com/html-reference/html-cite-tag.php) tag is used to describe a reference to a creative work. It must include the title of that work or the name of the author (people or organization) or an URL reference.

For short inline quotations, you can use the HTML `<q>` tag. Most browsers display inline quotes by surrounding the text in quotation marks. Here's an example:

#### Example

```markup
<p>According to the World Health Organization (WHO): <q>Health is a state of complete physical, mental, and social well-being.</q></p>
```

* * *

## Showing Abbreviations

An abbreviation is a shortened form of a word, phrase, or name.

You can use the `<abbr>` tag to denote an abbreviation. The `title` attribute is used inside this tag to provide the full expansion of the abbreviation, which is displayed by the browsers as a tooltip when the mouse cursor is hovered over the element. Let's try out an example:

#### Example

```markup
<p>The <abbr title="World Wide Web Consortium">W3C</abbr> is the main international standards organization for the <abbr title="World Wide Web">WWW or W3</abbr>. It was was founded by Tim Berners-Lee.</p>
```

* * *

## Marking Contact Addresses

Web pages often include street or postal addresses. HTML provides a special tag `<address>` to represent contact information (physical and/or digital) for a person, people or organization.

This tag should ideally used to display contact information related to the document itself, such as article's author. Most browsers display an address block in italic. Here's an example:

#### Example

```markup
<address>
Mozilla Foundation<br>
331 E. Evelyn Avenue<br>
Mountain View, CA 94041, USA
</address>
```

Please check out the HTML reference section for a complete list of [HTML formatting tags](https://www.tutorialrepublic.com/html-reference/html5-tags.php#formatting-tags).
* * *