CSS Lists



# CSS Lists

The list properties used to control the presentation of list item markers.

## Types of HTML Lists

There are three different types of list in HTML:

*   **Unordered lists** — A list of items, where every list items are marked with bullets.
*   **Ordered lists** — A list of items, where each list items are marked with numbers.
*   **Definition list** — A list of items, with a description of each item.

To know more about lists, please check out the tutorial on [HTML lists](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-lists.php).

* * *

## Styling Lists with CSS

CSS provides the several properties for styling the most commonly used unordered and ordered lists. These CSS list properties typically allow you to:

*   Control the shape or appearance of the marker.
*   Specify an image for the marker rather than a bullet point or number.
*   Set the distance between a marker and the text in the list.
*   Specify whether the marker or bullet would appear inside or outside of the box containing the unordered or ordered list items.

In the following section we'll discuss about the properties that can be used to style lists.

## List Style Type

By default, items in an [ordered list](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-lists.php#ordered-lists) are numbered with Arabic numerals (1, 2, 3, etc.), whereas in an [unordered list](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-lists.php#unordered-lists), items are marked with round bullets. But, you can change this default list marker type to any other type such as circle, square, roman numerals, latin letters, and so on using the `list-style-type` property.

#### Example

[Try this code »](https://www.tutorialrepublic.com/css-tutorial/../codelab.php?topic=css&file=list-01 "Try this code using online Editor")

```css
ul {
    list-style-type: square;
}
ol {
    list-style-type: upper-roman;
}
```

* * *

## Changing the Position of List Markers

The list markers are positioned outside of the list item's boxes, by default. However, you can use the `list-style-position` property to specify whether the markers or bullet points appear inside or outside of the list item's principal block boxes.

This property takes the value `inside` or `outside`, with `outside` being the default. If the value `inside` is used, the lines will wrap under the marker instead of being indented.

#### Example

[Try this code »](https://www.tutorialrepublic.com/css-tutorial/../codelab.php?topic=css&file=list-02 "Try this code using online Editor")

```css
ul.in li {
    list-style-position: inside;
}
ul.out li {
    list-style-position: outside;
}
```

* * *

## Using Images as List Markers

You can also set an image as a list marker using the `list-style-image` property.

The style rule in the following example assigns a transparent PNG image "arrow.png" as the list marker for all the items in the unordered list.

#### Example

[Try this code »](https://www.tutorialrepublic.com/css-tutorial/../codelab.php?topic=css&file=list-03 "Try this code using online Editor")

```css
ul li {
    list-style-image: url("arrow.png");
}
```

The example above does not produce the same output in all browsers. Internet Explorer and Opera will display the image-marker slightly higher than Firefox, Chrome, and Safari. See below, for the cross browser solution of this problem.

* * *

## Cross Browser Solution for Image Marker

When using an image as bullet using the `list-style-image` property, the bullets does not line up to the text accurately across the browsers. As a work-around, you can properly align bullet images via the [`background-image`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-image-property.php) CSS property. First, set the list to have no bullets. Then, define a non-repeating background image for the list element.

The following example displays the image markers equally in all browsers:

#### Example

[Try this code »](https://www.tutorialrepublic.com/css-tutorial/../codelab.php?topic=css&file=list-04 "Try this code using online Editor")

```css
ul {
    list-style-type: none;
}
ul li {
    background-image: url("arrow.png");
    background-position: 0px 5px;    /* X-pos Y-pos (from top-left) */
    background-repeat: no-repeat;
    padding-left: 20px;
}
```

* * *

## The list-style Shorthand property

The `list-style` property is a shorthand property for defining all the three properties `list-style-type`, `list-style-image`, and `list-style-position` of a list in one place.

This style rule set the list marker for the ordered list items to be uppercase Latin letters that appear inside the list item's principal block boxes:

#### Example

[Try this code »](https://www.tutorialrepublic.com/css-tutorial/../codelab.php?topic=css&file=list-05 "Try this code using online Editor")

```css
ol {
    list-style: upper-latin inside;
}
```

**Note:** When using the shorthand property, the orders of the values are: `list-style-type` | `list-style-position` | `list-style-image`. It doesn't matter if one of the values above is missing, as long as the rest are in the specified order.

[Previous Page](https://www.tutorialrepublic.com/css-tutorial/css-links.php) [Next Page](https://www.tutorialrepublic.com/css-tutorial/css-tables.php)

[![Bootstrap UI Design Templates](../../../../_resources/eba26253c5b14816b50b15c523425f2d.png)](https://www.tutorialrepublic.com/snippets/gallery.php)

Is this website helpful to you? Please give us a [like](https://www.tutorialrepublic.com/like.php), or share your [feedback](#feedback) _to help us improve_. Connect with us on [Facebook](https://www.facebook.com/tutorialrepublic) and [Twitter](https://twitter.com/tutrepublic) for the latest updates.

#### About Us

[Our Story](https://www.tutorialrepublic.com/about-us.php) [Terms of Use](https://www.tutorialrepublic.com/terms-of-use.php) [Privacy Policy](https://www.tutorialrepublic.com/privacy-policy.php)

#### Contact

[Contact Us](https://www.tutorialrepublic.com/contact-us.php) [Report Error](#feedback) [Advertise](https://www.tutorialrepublic.com/advertise-with-us.php)

#### Interactive Tools

[Font Awesome Icon Search Utility](https://www.tutorialrepublic.com/font-awesome-icons.php) [HTML Formatter](https://www.tutorialrepublic.com/html-formatter.php) [Title & Meta Length Calculator](https://www.tutorialrepublic.com/faq/what-is-the-maximum-length-of-title-and-meta-description-tag.php) [HTML Color Picker](https://www.tutorialrepublic.com/html-reference/html-color-picker.php) [Bootstrap Button Generator](https://www.tutorialrepublic.com/twitter-bootstrap-button-generator.php) [HTML Editor](https://www.tutorialrepublic.com/codelab.php?topic=html&file=hello-world) [SQL Playground](https://www.tutorialrepublic.com/codelab.php?topic=sql&file=select-all)

<img width="317" height="46" src="../../../../_resources/f958a6b2e20a4dd7b364a007a0668643.svg"/>

Copyright © 2019 Tutorial Republic. All Rights Reserved.

_Share This:_[](https://facebook.com/sharer.php?u=https://www.tutorialrepublic.com%2Fcss-tutorial%2Fcss-lists.php "Facebook")<a id="tweet-btn"></a>[](https://twitter.com/share?text=Formatting%20Unordered%20and%20Ordered%20Lists%20Using%20CSS%20-%20&url=https://www.tutorialrepublic.com%2Fcss-tutorial%2Fcss-lists.php "Twitter")<a id="email-btn"></a>[](https://mail.google.com/mail/?view=cm&fs=1&su=Formatting%20Unordered%20and%20Ordered%20Lists%20Using%20CSS%20&body=https://www.tutorialrepublic.com%2Fcss-tutorial%2Fcss-lists.php "Gmail")

3

Carbon Ads

Google Adsense

Google Tag Manager