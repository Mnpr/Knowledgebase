HTML Links

# HTML Links

In this tutorial you will learn how to create links to other pages in HTML.

## Creating Links in HTML

A link or hyperlink is a connection from one web resource to another. Links allow users to move seamlessly from one page to another, on any server anywhere in the world.

A link has two ends, called anchors. The link starts at the source anchor and points to the destination anchor, which may be any web resource, for example, an image, an audio or video clip, a PDF file, an HTML document or an element within the document itself, and so on.

By default, links will appear as follow in most of the browsers:

*   An unvisited link is underlined and blue.
*   A visited link is underlined and purple.
*   An active link is underlined and red.

However, you can overwrite this using CSS. Learn more about [styling links](https://www.tutorialrepublic.com/html-tutorial/../css-tutorial/css-links.php).

## HTML Link Syntax

Links are specified in HTML using the `<a>` tag.

A link or hyperlink could be a word, group of words, or image.

<a href="_url_">Link text&lt;/a&gt;

Anything between the opening `<a>` tag and the closing `</a>` tag becomes the part of the link that the user sees and clicks in a browser. Here are some examples of the links:

#### Example

```markup
<a href="https://www.google.com/">Google Search</a>
<a href="https://www.tutorialrepublic.com/">Tutorial Republic</a>
<a href="images/kites.jpg">
    <img src="kites-thumb.jpg" alt="kites">
</a>
```

The `href` attribute specifies the target of the link. Its value can be an absolute or relative URL.

An absolute URL is the URL that includes every part of the URL format, such as protocol, host name, and path of the document, e.g., `https://www.google.com/`, `https://www.example.com/form.php`, etc. While, relative URLs are page-relative paths, e.g., `contact.html`, `images/smiley.png`, and so on. A relative URL never includes the `http://` or `https://` prefix.

* * *

## Setting the Targets for Links

The `target` attribute tells the browser where to open the linked document. There are four defined targets, and each target name starts with an underscore(`_`) character:

*   `_blank` — Opens the linked document in a new window or tab.
*   `_parent` — Opens the linked document in the parent window.
*   `_self` — Opens the linked document in the same window or tab as the source document. This is the default, hence it is not necessary to explicitly specify this value.
*   `_top` — Opens the linked document in the full browser window.

Try out the following example to understand how the link's target basically works:

#### Example

```markup
<a href="/about-us.php" target="_top">About Us</a>
<a href="https://www.google.com/" target="_blank">Google</a>
<a href="images/sky.jpg" target="_parent">
    <img src="sky-thumb.jpg" alt="Cloudy Sky">
</a>
```

**Tip:** If your web page is placed inside an iframe, you can use the `target="_top"` on the links to break out of the iframe and show the target page in full browser window.

* * *

## Creating Bookmark Anchors

You can also create bookmark anchors to allow users to jump to a specific section of a web page. Bookmarks are especially helpful if you have a very long web page.

Creating bookmarks is a two-step process: first add the `id` attribute on the element where you want to jump, then use that `id` attribute value preceded by the hash sign (`#`) as the value of the `href` attribute of the `<a>` tag, as shown in the following example:

#### Example

```markup
<a href="#sectionA">Jump to Section A</a>
<h2 id="sectionA">Section A</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit...</p>
```

**Tip:** You can even jump to a section of another web page by specifying the URL of that page along with the anchor (i.e. `_#elementId_`) in the `href` attribute, for example, `<a href="mypage.html#topicA">Go to TopicA</a>`.

* * *

## Creating Download Links

You can also create the file download link in exactly the same fashion as placing text links. Just point the destination URL to the file you want to be available for download.

In the following example we've created the download links for ZIP, PDF and JPG files.

#### Example

```markup
<a href="downloads/test.zip">Download Zip file</a>
<a href="downloads/masters.pdf">Download PDF file</a>
<a href="downloads/sample.jpg">Download Image file</a>
```

**Note:** When you click a link that points to a PDF or image file, the file is not downloaded to your hard drive directly. It will only open the file in your web browser. Further you can save or download it to your hard drive on a permanent basis.

* * *