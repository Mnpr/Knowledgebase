Web Workers

# HTML5 Web Workers

In this tutorial you will learn how to use HTML5 web worker to run JavaScript code in the background.

## What is Web Worker?

If you try to do intensive task with JavaScript that is time-consuming and require hefty calculations browser will freeze up the web page and prevent the user from doing anything until the job is completed. It happens because JavaScript code always runs in the foreground.

HTML5 introduces a new technology called _web worker_ that is specifically designed to do background work independently of other user-interface scripts, without affecting the performance of the page. Unlike normal JavaScript operations, web worker doesn't interrupt the user and the web page remains responsive because they are running the tasks in the background.

**Tip:** The HTML5's web worker feature is supported in all major modern web browsers like Firefox, Chrome, Opera, Safari and Internet Explorer 10 and above.

* * *

## Create a Web Worker File

The simplest use of web workers is for performing a time-consuming task. So here we are going to create a simple JavaScript task that counts from zero to 100,000.

Let's create an external JavaScript file named "worker.js" and type the following code.

#### Example

[Download](https://www.tutorialrepublic.com/html-tutorial/../examples/downloads/html5-web-worker-file.zip "Download Source Code")

```javascript
var i = 0;
function countNumbers() {
    if(i < 100000) {
        i = i + 1;
        postMessage(i);
    }
 
    // Wait for sometime before running this script again
    setTimeout("countNumbers()", 500);
}
countNumbers();
```

**Note:** Web workers have no access to the DOM. That means you can't access any DOM elements in the JavaScript code that you intend to run using web workers.

**Tip:** The worker object's `postMessage()` method is used to send a message (like the numbers in the example above) back to the web page from the web worker file.

* * *

## Doing Work in the Background with Web Worker

Now that we have created our web worker file. In this section we are going to initiate the web worker from an HTML document that runs the code inside the file named "worker.js" in the background and progressively displays the result on the web page. Let's see how it works:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Using Web Worker</title>
<script>
    if(window.Worker) {
        // Create a new web worker
        var worker = new Worker("worker.js");
        
        // Fire onMessage event handler
        worker.onmessage = function(event) {
            document.getElementById("result").innerHTML = event.data;
        };
    } else {
        alert("Sorry, your browser do not support web worker.");
    }
</script>
</head>
<body>
    <div id="result">
        <!--Received messages will be inserted here-->
    </div>
</body>
</html>
```

### Example explained:

The JavaScript code in the above example has the following meaning:

*   The statement **var worker = new Worker("worker.js");** creates a new web worker object, which is used to communicate with the web worker.
*   When the worker posts a message, it fires the **onmessage** event handler (_line no-14_) that allows the code to receive messages from the web worker.
*   The **event.data** element contains the message sent from the web worker.

**Note:** The code that a worker runs is always stored in a separate JavaScript file. This is to prevent web developer from writing the web worker code that attempts to use global variables or directly access the elements on the web page.

* * *

## Terminate a Web Worker

So far you have learnt how to create worker and start receiving messages. However, you can also terminate a running worker in the middle of the execution.

The following example will show you how to start and stop worker from a web page through clicking the HTML buttons. It utilizes the same JavaScript file 'worker.js' what we have used in the previous example to count the numbers from zero to 100000. Let's try it out:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Start/Stop Web Worker</title>
<script>
    // Set up global variable
    var worker;
    
    function startWorker() {
        // Initialize web worker
        worker = new Worker("worker.js");
        
        // Run update function, when we get a message from worker
        worker.onmessage = update;
        
        // Tell worker to get started
        worker.postMessage("start");
    }
    
    function update(event) {
        // Update the page with current message from worker
        document.getElementById("result").innerHTML = event.data;
    }
    
    function stopWorker() {
        // Stop the worker
        worker.terminate();
    }
</script>
</head>
<body>
    <h1>Web Worker Demo</h1>
    <button onclick="startWorker();" type="button">Start web worker</button>
    <button type="button" onclick="stopWorker();">Stop web worker</button>
    <div id="result">
        <!--Received messages will be inserted here-->
    </div>
</body>
</html>
```

**Tip:** Use the web workers for performing only heavy-weight JavaScript tasks that do not interrupt the user-interface scripts (i.e. scripts that respond to clicks or other user interactions). It's not recommended to use web workers for short tasks.

 * * *