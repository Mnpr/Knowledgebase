Special Characters and Entities

# HTML Entities

In this tutorial you will learn how to use HTML entities to display special characters and symbols.

## What is HTML Entity?

Some characters are reserved in HTML, e.g. you cannot use the less than (`<`) or greater than (`>`) signs or angle brackets within your text, because the browser could mistake them for markup, while some characters are not present on the keyboard like copyright symbol ©.

To display these special characters, they must be replaced with the character entities. Character entity references, or entities for short, enable you to use the characters that cannot be expressed in the document's character encoding or that cannot be entered by a keyboard.

## Frequently Used HTML Character Entities

| Result | Description          | Entity Name | Numerical reference |
| ------ | -------------------- | ----------- | ------------------- |
|        | non-breaking space   | &nbsp;      | &#160;              |
| <      | less than            | &lt;        | &#60;               |
| >      | greater than         | &gt;        | &#62;               |
| &      | ampersand            | &amp;       | &#38;               |
| "      | quotation mark       | &quot;      | &#34;               |
| '      | apostrophe           | &apos;      | &#39;               |
| ¢      | cent                 | &cent;      | &#162;              |
| £      | pound                | &pound;     | &#163;              |
| ¥      | yen                  | &yen;       | &#165;              |
| €      | euro                 | &euro;      | &#8364;             |
| ©      | copyright            | &copy;      | &#169;              |
| ®      | registered trademark | &reg;       | &#174;              |
| ™      | trademark            | &trade;     | &#8482;             |

You can use numeric character references, instead of entity names. A key benefit of using numeric character references is that, they have stronger browser support, and can be used to specify any [Unicode character](http://www.unicode.org/charts/), whereas entities are limited to a subset of this.

**Note:** HTML entities names are case-sensitive! Please check out the [HTML character entities](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-character-entities.php) reference for a complete list of character entities of special characters and symbols.

**Tip:** Nonbreaking space (`&nbsp;`) is used to create a blank space between two items that cannot be separated by a line break. They are also used to display multiple spaces since web browsers display only one space if multiple spaces are created using the spacebar key.
