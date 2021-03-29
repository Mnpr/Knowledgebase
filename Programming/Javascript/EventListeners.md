Event Listeners

# Event Listeners

## Understanding Event Listeners

The event listeners are just like [event handlers](https://www.tutorialrepublic.com/javascript-tutorial/javascript-events.php), except that you can assign as many event listeners as you like to a particular event on particular element.

To understand how event listeners actually works let's check out a simple example. Suppose that you've created two functions and you try to execute both of them on click of the button using the `onclick` event handler, as shown in the following example:

#### Example

```markup
<button id="myBtn">Click Me</button>
 
<script>
// Defining custom functions
function firstFunction() {
    alert("The first function executed successfully!");
}
 
function secondFunction() {
    alert("The second function executed successfully");
}
 
// Selecting button element
var btn = document.getElementById("myBtn");
 
// Assigning event handlers to the button
btn.onclick = firstFunction;
btn.onclick = secondFunction; // This one overwrite the first
</script>
```

If you run the above example and click the button element, only `secondFunction()` will be executed, because assigning the second event handler overwrites the first.

This is the main shortcoming of this classic event model—you can only assign one event handler to a particular event on a particular element i.e. a single function per event per element. To deal with this problem W3C introduced more flexible event-model called _event listeners_.

Any HTML element can have multiple event listeners, therefore you can assign multiple functions to the same event for the same element, as demonstrated in following example:

#### Example

```markup
<button id="myBtn">Click Me</button>
 
<script>
// Defining custom functions
function firstFunction() {
    alert("The first function executed successfully!");
}
 
function secondFunction() {
    alert("The second function executed successfully");
}
 
// Selecting button element
var btn = document.getElementById("myBtn");
 
// Assigning event listeners to the button
btn.addEventListener("click", firstFunction);
btn.addEventListener("click", secondFunction);
</script>
```

Now, if you run the above example and click the button, both functions will be executed.

In addition to the event `type` and `listener` function parameter the `addEventListener()` accepts one more Boolean parameter `useCapture`. This is an optional parameter which specifies whether to use `event bubbling` or `event capturing`. Its basic syntax is:

`target.addEventListener(_event_, _function_, _useCapture_);`

Event bubbling and capturing are two ways of propagating events. We will learn about [event propagation](https://www.tutorialrepublic.com/javascript-tutorial/javascript-event-propagation.php) in detail in the upcoming chapter.

* * *

## Adding Event Listeners for Different Event Types

Like event handler, you can assign different event listeners to different event types on the same element. The following example will assign different event-listener functions to the "click", "mouseover", and "mouseout" events of a button element.

#### Example

```markup
<button id="myBtn">Click Me</button>
 
<script>
// Selecting button element
var btn = document.getElementById("myBtn");
 
// Defining custom functions
function sayHello() {
    alert("Hi, how are you doing?");
}
 
function setHoverColor() {
    btn.style.background = "yellow";
}
 
function setNormalColor() {
    btn.style.background = "";
}
 
// Assigning event listeners to the button
btn.addEventListener("click", sayHello);
btn.addEventListener("mouseover", setHoverColor);
btn.addEventListener("mouseout", setNormalColor);
</script>
```

* * *

## Adding Event Listeners to Window Object

The `addEventListener()` method allows you to add event listeners to any HTML DOM elements, the document object, the window object, or any other object that support events, e.g, `XMLHttpRequest` object. Here's an example that attaches an event listener to the window "resize" event:

#### Example

```markup
<div id="result"></div>
 
<script>
// Defining event listener function
function displayWindowSize() {
    var w = window.innerWidth;
    var h = window.innerHeight;
    var size = "Width: " + w + ", " + "Height: " + h;
    document.getElementById("result").innerHTML = size;
}
 
// Attaching the event listener function to window's resize event
window.addEventListener("resize", displayWindowSize);
</script>
```

* * *

## Removing Event Listeners

You can use the `removeEventListener()` method to remove an event listener that have been previously attached with the `addEventListener()`. Here's an example:

#### Example

```markup
<button id="myBtn">Click Me</button>
 
<script> 
// Defining function
function greetWorld() {
    alert("Hello World!");
}
 
// Selecting button element
var btn = document.getElementById("myBtn");
 
// Attaching event listener
btn.addEventListener("click", greetWorld);
 
// Removing event listener
btn.removeEventListener("click", greetWorld);
</script>
```

**Note:** The `addEventListener()` and `removeEventListener()` methods supported in all major browsers. Not supported in IE 8 and earlier, and Opera 6.0 and earlier versions.
* * *
