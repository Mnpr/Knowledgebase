CSS Cursor

# CSS Cursors

CSS cursor property used to define cursor type (i.e. mouse pointer) when the mouse moves over a certain area or, over a link on the webpage.

## Changing the Look of Cursor

The browsers typically display the mouse pointer over any blank part of a web page, the gloved hand over any linked or clickable item and the edit cursor over any text or text field. With CSS you can redefine those properties to display a variety of different cursors.

#### Example

```css
h1 {
    cursor: move;
}
p {
    cursor: text;
}
```

The table below demonstrates the different cursors that most browsers will accept. Place your mouse pointer over the "TEST" link in the output column to reveal that cursor.

| Look | Values | Example | Output |
| --- | --- | --- | --- |
| ![Default Cursor](../../../../_resources/b63a3b971d7c4910987bbf5a01305b6d.gif) | `default` | `a:hover{cursor:default;}` | TEST |
| ![Pointer Cursor](../../../../_resources/2e4e5e15d50443d8878ec989c48349b4.gif) | `pointer` | `a:hover{cursor:pointer;}` | TEST |
| ![Text Cursor](../../../../_resources/beea9c80da2641709c13a1902b8a6c28.gif) | `text` | `a:hover{cursor:text;}` | TEST |
| ![Wait Cursor](../../../../_resources/6359782433514c4f8d6d2095b659f672.gif) | `wait` | `a:hover{cursor:wait;}` | TEST |
| ![Help Cursor](../../../../_resources/9ed07d5390f248118fdcde2b4705246a.gif) | `help` | `a:hover{cursor:help;}` | TEST |
| ![Progress Cursor](../../../../_resources/a26b55a45bb84ca3991cf4a17f6382cf.gif) | `progress` | `a:hover{cursor:progress;}` | TEST |
| ![Crosshair Cursor](../../../../_resources/e19598199d1743d3a248de72b3cee987.gif) | `crosshair` | `a:hover{cursor:crosshair;}` | TEST |
| ![Move Cursor](../../../../_resources/50269a31de1349ae88cd1a7e95f7d4fa.gif) | `move` | `a:hover{cursor:move;}` | TEST |
| ![Custom Cursor](../../../../_resources/b8d2adca72654eaf9aff9427d5e650a2.gif) | `url()` | `a:hover{cursor:url("custom.cur"), default;}` | TEST |

Check out [more cursors »](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-cursor-property.php)

* * *

## Creating a Customized Cursor

It is also possible to have completely customized cursors.

The cursor property handles a comma-separated list of user-defined cursors values followed by the _generic cursor_. If the first cursor is specified incorrectly or can't be found, the next cursor in the comma-separated list will be used, and so on until a usable cursor is found.

If none of the user-defined cursors is valid or supported by the browser, the generic cursor at the end of the list will be used instead.

**Tip:** The standard format that can be used for cursors is the `.cur` format. However, you can convert images such as `.jpg` and `.gif` into `.cur` format using the image converter software freely available online.

#### Example

```css
a {
    cursor: url("custom.gif"), url("custom.cur"), default;
}
```

In the above example `custom.gif` and `custom.cur` is the custom cursor file, uploaded to your server space, and `default` is the generic cursor that will be used if the custom cursor is missing, or isn't supported by the viewer's browser.

**Warning:** If you are declaring a custom cursor, you must define a _generic cursor_ at the end of the list, otherwise the custom cursor will not render correctly.

Here is a live demonstration of a custom cursor.

Hover your mouse pointer over this link to reveal the custom cursor

**Note:** IE9 and earlier versions only support URL values of the type `.cur` for static cursor, and `.ani` for animated cursor. However, browsers such as Firefox, Chrome and Safari have support for `.cur`, `.png`, `.gif` and `.jpg` but not `.ani`.
***