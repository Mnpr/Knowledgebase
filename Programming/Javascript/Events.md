Events 


# JavaScript Events

## Understanding Events and Event Handlers

An event is something that happens when user interact with the web page, such as when he clicked a link or button, entered text into an input box or textarea, made selection in a select box, pressed key on the keyboard, moved the mouse pointer, submits a form, etc. In some cases, the Browser itself can trigger the events, such as the page load and unload events.

When an event occur, you can use a JavaScript event handler (or an event listener) to detect them and perform specific task or set of tasks. By convention, the names for event handlers always begin with the word "on", so an event handler for the click event is called `onclick`, similarly an event handler for the load event is called `onload`, event handler for the blur event is called `onblur`, and so on.

There are several ways to assign an event handler. The simplest way is to add them directly to the start tag of the HTML elements using the special event-handler attributes. For example, to assign a click handler for a button element, we can use `onclick` attribute, like this:

#### Example

```markup
<button type="button" onclick="alert('Hello World!')">Click Me</button>
```

However, to keep the JavaScript seperate from HTML, you can set up the event handler in an external JavaScript file or within the `<script>` and `</script>` tags, like this:

#### Example

```markup
<button type="button" id="myBtn">Click Me</button>
<script>
    function sayHello() {
        alert('Hello World!');
    }
    document.getElementById("myBtn").onclick = sayHello;
</script>
```

**Note:** Since HTML attributes are case-insensitive so `onclick` may also be written as `onClick`, `OnClick` or `ONCLICK`. But its _value_ is case-sensitive.

In general, the events can be categorized into four main groups — [mouse events](#mouse-events), [keyboard events](#keyboard-events), [form events](#form-events) and [document/window events](#document-and-window-events). There are many other events, we will learn about them in later chapters. The following section will give you a brief overview of the most useful events one by one along with the real life practice examples.

## Mouse Events

A mouse event is triggered when the user click some element, move the mouse pointer over an element, etc. Here're some most important mouse events and their event handler.

## The Click Event (onclick)

The click event occurs when a user clicks on an element on a web page. Often, these are form elements and links. You can handle a click event with an `onclick` event handler.

The following example will show you an alert message when you click on the elements.

#### Example

```markup
<button type="button" onclick="alert('You have clicked a button!');">Click Me</button>
<a href="#" onclick="alert('You have clicked a link!');">Click Me</a>
```

## The Contextmenu Event (oncontextmenu)

The contextmenu event occurs when a user clicks the right mouse button on an element to open a context menu. You can handle a contextmenu event with an `oncontextmenu` event handler.

The following example will show an alert message when you right-click on the elements.

#### Example

```markup
<button type="button" oncontextmenu="alert('You have right-clicked a button!');">Right Click on Me</button>
<a href="#" oncontextmenu="alert('You have right-clicked a link!');">Right Click on Me</a>
```

## The Mouseover Event (onmouseover)

The mouseover event occurs when a user moves the mouse pointer over an element.

You can handle the mouseover event with the `onmouseover` event handler. The following example will show you an alert message when you place mouse over the elements.

#### Example

```markup
<button type="button" onmouseover="alert('You have placed mouse pointer over a button!');">Place Mouse Over Me</button>
<a href="#" onmouseover="alert('You have placed mouse pointer over a link!');">Place Mouse Over Me</a>
```

## The Mouseout Event (onmouseout)

The mouseout event occurs when a user moves the mouse pointer outside of an element.

You can handle the mouseout event with the `onmouseout` event handler. The following example will show you an alert message when the mouseout event occurs.

#### Example

```markup
<button type="button" onmouseout="alert('You have moved out of the button!');">Place Mouse Inside Me and Move Out</button>
<a href="#" onmouseout="alert('You have moved out of the link!');">Place Mouse Inside Me and Move Out</a>
```

* * *

## Keyboard Events

A keyboard event is fired when the user press or release a key on the keyboard. Here're some most important keyboard events and their event handler.

## The Keydown Event (onkeydown)

The keydown event occurs when the user presses down a key on the keyboard.

You can handle the keydown event with the `onkeydown` event handler. The following example will show you an alert message when the keydown event occurs.

#### Example

```markup
<input type="text" onkeydown="alert('You have pressed a key inside text input!')">
<textarea onkeydown="alert('You have pressed a key inside textarea!')"></textarea>
```

## The Keyup Event (onkeyup)

The keyup event occurs when the user releases a key on the keyboard.

You can handle the keyup event with the `onkeyup` event handler. The following example will show you an alert message when the keyup event occurs.

#### Example

```markup
<input type="text" onkeyup="alert('You have released a key inside text input!')">
<textarea onkeyup="alert('You have released a key inside textarea!')"></textarea>
```

## The Keypress Event (onkeypress)

The keypress event occurs when a user presses down a key on the keyboard that has a character value associated with it. For example, keys like Ctrl, Shift, Alt, Esc, Arrow keys, etc. will not generate a keypress event, but will generate a keydown and keyup event.

You can handle the keypress event with the `onkeypress` event handler. The following example will show you an alert message when the keypress event occurs.

#### Example

```markup
<input type="text" onkeypress="alert('You have pressed a key inside text input!')">
<textarea onkeypress="alert('You have pressed a key inside textarea!')"></textarea>
```

* * *

## Form Events

A form event is fired when a form control receive or loses focus or when the user modify a form control value such as by typing text in a text input, select any option in a select box etc. Here're some most important form events and their event handler.

## The Focus Event (onfocus)

The focus event occurs when the user gives focus to an element on a web page.

You can handle the focus event with the `onfocus` event handler. The following example will highlight the background of text input in yellow color when it receives the focus.

#### Example

```markup
<script>
    function highlightInput(elm){
        elm.style.background = "yellow";
    }    
</script>
<input type="text" onfocus="highlightInput(this)">
<button type="button">Button</button>
```

**Note:** The value of `this` keyword inside an event handler refers to the element which has the handler on it (i.e. where the event is currently being delivered).

## The Blur Event (onblur)

The blur event occurs when the user takes the focus away from a form element or a window.

You can handle the blur event with the `onblur` event handler. The following example will show you an alert message when the text input element loses focus.

#### Example

```markup
<input type="text" onblur="alert('Text input loses focus!')">
<button type="button">Submit</button>
```

To take the focus away from a form element first click inside of it then press the tab key on the keyboard, give focus on something else, or click outside of it.

## The Change Event (onchange)

The change event occurs when a user changes the value of a form element.

You can handle the change event with the `onchange` event handler. The following example will show you an alert message when you change the option in the select box.

#### Example

```markup
<select onchange="alert('You have changed the selection!');">
    <option>Select</option>
    <option>Male</option>
    <option>Female</option>
</select>
```

## The Submit Event (onsubmit)

The submit event only occurs when the user submits a form on a web page.

You can handle the submit event with the `onsubmit` event handler. The following example will show you an alert message while submitting the form to the server.

#### Example

```markup
<form action="action.php" method="post" onsubmit="alert('Form data will be submitted to the server!');">
    <label>First Name:</label>
    <input type="text" name="first-name" required>
    <input type="submit" value="Submit">
</form>
```

* * *

## Document/Window Events

Events are also triggered in situations when the page has loaded or when user resize the browser window, etc. Here're some most important document/window events and their event handler.

## The Load Event (onload)

The load event occurs when a web page has finished loading in the web browser.

You can handle the load event with the `onload` event handler. The following example will show you an alert message as soon as the page finishes loading.

#### Example

```markup
<body onload="window.alert('Page is loaded successfully!');">
    <h1>This is a heading</h1>
    <p>This is paragraph of text.</p>
</body>
```

## The Unload Event (onunload)

The unload event occurs when a user leaves the current web page.

You can handle the unload event with the `onunload` event handler. The following example will show you an alert message when you try to leave the page.

#### Example

```markup
<body onunload="alert('Are you sure you want to leave this page?');">
    <h1>This is a heading</h1>
    <p>This is paragraph of text.</p>
</body>
```

## The Resize Event (onresize)

The resize event occurs when a user resizes the browser window. The resize event also occurs in situations when the browser window is minimized or maximized.

You can handle the resize event with the `onresize` event handler. The following example will show you an alert message when you resize the browser window to a new width and height.

#### Example

```markup
<p id="result"></p>
<script>
    function displayWindowSize() {
        var w = window.outerWidth;
        var h = window.outerHeight;
        var txt = "Window size: width=" + w + ", height=" + h;
        document.getElementById("result").innerHTML = txt;
    }
    window.onresize = displayWindowSize;
</script>
```
* * *