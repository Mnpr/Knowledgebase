Event Propagation 

# Event Propagation

In this tutorial you will learn how events propagate in the DOM tree in JavaScript.

## Understanding the Event Propagation

Event propagation is a mechanism that defines how events propagate or travel through the DOM tree to arrives at its target and what happens to it afterward.

Let's understand this with the help of an example, suppose you have assigned a click [event handler](https://www.tutorialrepublic.com/javascript-tutorial/javascript-events.php) on a hyperlink (i.e. [`<a>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-a-tag.php) element) which is nested inside a paragraph (i.e. [`<p>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-p-tag.php) element). Now if you click on that link, the handler will be executed. But, instead of link, if you assign the click event handler to the paragraph containing the link, then even in this case, clicking the link will still trigger the handler. That's because events don't just affect the target element that generated the event—they travel up and down through the DOM tree to reach their target. This is known as event propagation

In modern browser event propagation proceeds in two phases: **_capturing_**, and **_bubbling_** phase. Before we proceed further, take a look at the following illustration:

<img width="620" height="310" src="../../../../_resources/020ba338e09c4385a674747d4462e5be.png"/>

Above image demonstrates how event travels in the DOM tree during different phases of the event propagation when an event is fired on an element that has parent elements.

The concept of event propagation was introduced to deal with the situations in which multiple elements in the DOM hierarchy with a parent-child relationship have event handlers for the same event, such as a mouse click. Now, the question is which element's click event will be handled first when the user clicks on the inner element—the click event of the outer element, or the inner element.

In the following sections of this chapter we will discuss each phases of the event propagation in greater detail and find out the answer of this question.

**Note:** Formally there are 3 phases, _capture_, _target_ and _bubble_ phase. But, the 2nd phase i.e. the target phase (occurs when the event arrives at the target element that has generated the event) is not handled separately in modern browsers, handlers registered for both _capturing_ and _bubbling_ phases are executed in this phase.

## The Capturing Phase

In the capturing phase, events propagate from the [Window](https://www.tutorialrepublic.com/javascript-tutorial/javascript-window.php) down through the DOM tree to the target node. For example, if the user clicks a hyperlink, that click event would pass through the [`<html>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-html-tag.php) element, the [`<body>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-body-tag.php) element, and the [`<p>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-p-tag.php) element containing the link.

Also if any ancestor (i.e. parent, grandparent, etc.) of the target element and the target itself has a specially registered **capturing event listener** for that type of event, those listeners are executed during this phase. Let's check out the following example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Event Capturing Demo</title>
<style type="text/css">
    div, p, a{
        padding: 15px 30px;
        display: block;
        border: 2px solid #000;
        background: #fff;
    }
</style>
</head>
<body>
<div id="wrap">DIV
    <p class="hint">P
        <a href="#">A</a>
    </p>
</div>

<script>
    function showTagName() {
        alert("Capturing: "+ this.tagName);
    }
    
    var elems = document.querySelectorAll("div, p, a");
    for(let elem of elems) {
        elem.addEventListener("click", showTagName, true);
    }
</script>
</body>
</html>
```

Here is a simple demonstration that we've created utilizing the above example to show you how event capturing works. Click on any element and observe in which order alert pop-ups appears.

&lt;div id="wrap"&gt;

&lt;p class="hint"&gt; &lt;a href="#"&gt;Click Me&lt;/a&gt; &lt;/p&gt;

&lt;/div&gt;

Event capturing is not supported in all browsers and rarely used. For instance, Internet Explorer prior to version 9.0 does not support event capturing.

Also, event capturing only works with event handlers registered with the `addEventListener()` method when the third argument is set to `true`. The traditional method of assigning event handlers, like using `onclick`, `onmouseover`, etc. won't work here. Please check out the [JavaScript event listeners](https://www.tutorialrepublic.com/javascript-tutorial/javascript-event-listeners.php) chapter to learn more about event listeners.

* * *

## The Bubbling Phase

In the bubbling phase, the exact opposite occurs. In this phase event propagates or bubbles back up the DOM tree, from the target element up to the [Window](https://www.tutorialrepublic.com/javascript-tutorial/javascript-window.php), visiting all of the ancestors of the target element one by one. For example, if the user clicks a hyperlink, that click event would pass through the `<p>` element containing the link, the `<body>` element, the `<html>` element, and the `document` node.

Also, if any ancestor of the target element and the target itself has event handlers assigned for that type of event, those handlers are executed during this phase. In modern browsers, all event handlers are registered in the bubbling phase, by default. Let's check out an example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Event Bubbling Demo</title>
<style type="text/css">
    div, p, a{
        padding: 15px 30px;
        display: block;
        border: 2px solid #000;
        background: #fff;
    }
</style>
</head>
<body>
<div onclick="alert('Bubbling: ' + this.tagName)">DIV
    <p onclick="alert('Bubbling: ' + this.tagName)">P
        <a href="#" onclick="alert('Bubbling: ' + this.tagName)">A</a>
    </p>
</div>
</body>
</html>
```

Here is a simple demonstration that we've created utilizing the above example to show you how event bubbling works. Click on any element and observe in which order alert pop-ups appears.

&lt;div id="wrap"&gt;

&lt;p class="hint"&gt; &lt;a href="#"&gt;Click Me&lt;/a&gt; &lt;/p&gt;

&lt;/div&gt;

Event bubbling is supported in all browsers, and it works for all handlers, regardless of how they are registered e.g. using `onclick` or `addEventListener()` (unless they are registered as [capturing event listener](https://www.tutorialrepublic.com/javascript-tutorial/javascript-event-listeners.php)). That's why the term event propagation is often used as a synonym of event bubbling.

* * *

## Accessing the Target Element

The target element is the [DOM node](https://www.tutorialrepublic.com/javascript-tutorial/javascript-dom-nodes.php) that has generated the event. For example, if the user clicks a hyperlink, the target element is the hyperlink.

The target element is accessible as `event.target`, it doesn't change through the event propagation phases. Additionally, the `this` keyword represents the current element (i.e. the element that has a currently running handler attached to it). Let's check out an example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Event Target Demo</title>
<style type="text/css">
    div, p, a{
        padding: 15px 30px;			
        display: block;
        border: 2px solid #000;
        background: #fff;
    }
</style>
</head>
<body>
<div id="wrap">DIV
    <p class="hint">P
        <a href="#">A</a>
    </p>
</div>

<script>
    // Selecting the div element
    var div = document.getElementById("wrap");

    // Attaching an onclick event handler
    div.onclick = function(event) {
        event.target.style.backgroundColor = "lightblue";

        // Let the browser finish rendering of background color before showing alert
        setTimeout(() => {
            alert("target = " + event.target.tagName + ", this = " + this.tagName);
            event.target.style.backgroundColor = ''
        }, 0);
    }
</script>
</body> 
</html>
```

Here is a simple demonstration that we've created utilizing the above example. Click on any element and it will show you the tag name of the target element and the current element.

&lt;div id="wrap"&gt;

&lt;p class="hint"&gt; &lt;a href="#"&gt;Click Me&lt;/a&gt; &lt;/p&gt;

&lt;/div&gt;

The fat arrow (`=>`) sign we've used in the example above is an arrow function expression. It has a shorter syntax than a function expression, and it would make the `this` keyword behave properly. Please check out the tutorial on [ES6 features](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php) to learn more about arrow function.

* * *

## Stopping the Event Propagation

You can also stop event propagation in the middle if you want to prevent any ancestor element's event handlers from being notified about the event.

For example, suppose you have nested elements and each element has `onclick` event handler that displays an alert dialog box. Normally, when you click on the inner element all handlers will be executed at once, since event bubble up to the DOM tree.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Event Propagation Demo</title>
<style type="text/css">
    div, p, a{
        padding: 15px 30px;
        display: block;
        border: 2px solid #000;
        background: #fff;
    }
</style>
</head>
<body>
<div id="wrap">DIV
    <p class="hint">P
        <a href="#">A</a>
    </p>
</div>

<script>
    function showAlert() {
        alert("You clicked: "+ this.tagName);
    }

    var elems = document.querySelectorAll("div, p, a");
    for(let elem of elems) {
        elem.addEventListener("click", showAlert);
    }
</script>
</body>
</html>
```

Here's a simple demonstration that we've created utilizing the above example. If you click on any child element, event handler on parent elements are also executed and you may see multiple alert boxes.

&lt;div id="wrap"&gt;

&lt;p class="hint"&gt; &lt;a href="#"&gt;Click Me&lt;/a&gt; &lt;/p&gt;

&lt;/div&gt;

To prevent this situation you can stop event from bubbling up the DOM tree using the `event.stopPropagation()` method. In the following example click event listener on the parent elements will not execute if you click on the child elements.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Stop Event Propagation Demo</title>
<style type="text/css">
    div, p, a{
        padding: 15px 30px;
        display: block;
        border: 2px solid #000;
        background: #fff;
    }
</style>
</head>
<body>
<div id="wrap">DIV
    <p class="hint">P
        <a href="#">A</a>
    </p>
</div>

<script>
    function showAlert(event) {
        alert("You clicked: "+ this.tagName);
        event.stopPropagation();
    }

    var elems = document.querySelectorAll("div, p, a");
    for(let elem of elems) {
        elem.addEventListener("click", showAlert);
    }
</script>
</body>
</html>
```

Here's is the updated demonstration. Now if you click on any child element only one alert will appear.

&lt;div id="wrap"&gt;

&lt;p class="hint"&gt; &lt;a href="#"&gt;Click Me&lt;/a&gt; &lt;/p&gt;

&lt;/div&gt;

Additionally, you can even prevent any other listeners attached to the same element for the same event type from being executed using the `stopImmediatePropagation()` method.

In the following example we've attached multiple listeners to the hyperlink, but only one listener for the hyperlink will execute when you click the link, and you will see only one alert.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Stop Immediate Propagation Demo</title>
<style type="text/css">
    div, p, a{
        padding: 15px 30px;
        display: block;
        border: 2px solid #000;
        background: #fff;
    }
</style>
</head>
<body>
<div onclick="alert('You clicked: ' + this.tagName)">DIV
    <p onclick="alert('You clicked: ' + this.tagName)">P
        <a href="#" id="link">A</a>
    </p>
</div>

<script>
    function sayHi() {
        alert("Hi, there!");
        event.stopImmediatePropagation();
    }
    function sayHello() {
        alert("Hello World!");
    }
    
    // Attaching multiple event handlers to hyperlink
    var link = document.getElementById("link");
    link.addEventListener("click", sayHi);  
    link.addEventListener("click", sayHello);
</script>
</body>
</html>
```

**Note:** If several listeners are attached to the same element for the same event type, they are executed in order in which they have been added. But, if any listener calls the `event.stopImmediatePropagation()` method, no remaining listeners will be executed.

* * *

## Preventing the Default Action

Some events have a default action associated with them. For example, if you click on a link browser takes you to the link's target, when you click on a form submit button browser submit the form, etc. You can prevent such default actions with the `preventDefault()` method of the event object.

However, preventing the default actions does not stop event propagation; the event continues to propagate to the DOM tree as usual. Here's is an example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Prevent Default Demo</title>
</head>
<body>
<form action="/examples/html/action.php" method="post" id="users">
    <label>First Name:</label>
    <input type="text" name="first-name" id="firstName">
    <input type="submit" value="Submit" id="submitBtn">
</form>

<script>
    var btn = document.getElementById("submitBtn");
    
    btn.addEventListener("click", function(event) {
        var name = document.getElementById("firstName").value;
        alert("Sorry, " + name + ". The preventDefault() won't let you submit this form!");
        event.preventDefault(); // Prevent form submission
    });
</script>
</body>
</html>
```
* * *