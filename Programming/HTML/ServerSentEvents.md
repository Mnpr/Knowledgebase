Server-Sent Events

# HTML5 Server-Sent Events

In this tutorial you will learn how to use the HTML5 server-sent events feature to create a unidirectional and persistent connection between a web page and server.

## What is Server-Sent Event?

HTML5 server-sent event is a new way for the web pages to communicating with the web server. It is also possible with the XMLHttpRequest object that lets your JavaScript code make a request to the web server, but it's a one-for-one exchange — that means once the web server provides its response, the communication is over. XMLHttpRequest object is the core of all [Ajax](https://www.tutorialrepublic.com/javascript-tutorial/javascript-ajax.php) operations.

However, there are some situations where web pages require a longer-term connection to the web server. A typical example is stock quotes on finance websites where price updated automatically. Another example is a news ticker running on various media websites.

You can create such things with the HTML5 server-sent events. It allows a web page to hold an open connection to a web server so that the web server can send a new response automatically at any time, there's no need to reconnect, and run the same server script from scratch over and over again.

**Note:** Server-Sent Events (SSE) are unidirectional that means data are delivered in one direction from the server to client. A client typically is a web browser.

**Tip:** The HTML5's server-sent events feature is supported in all major modern web browsers like Firefox, Chrome, Safari and Opera except Internet Explorer.

## Sending Messages with a Server Script

Let's create a PHP file named "server_time.php" and type the following script into it. It will simply report the current time of the web server's built-in clock in regular intervals. We will retrieve this time and update the web page accordingly later in this tutorial.

#### Example

[Download](https://www.tutorialrepublic.com/html-tutorial/../examples/downloads/html5-server-sent-events.zip "Download Source Code")

```php
<?php
header("Content-Type: text/event-stream");
header("Cache-Control: no-cache");
 
// Get the current time on server
$currentTime = date("h:i:s", time());
 
// Send it in a message
echo "data: " . $currentTime . "\n\n";
flush();
?>
```

The first two line of the [PHP script](https://www.tutorialrepublic.com/php-tutorial/) sets two important headers. First, it sets the MIME type to `text/event-stream`, which is required by the server-side event standard. The second line tells the web server to turn off caching otherwise the output of your script may be cached.

Every message send through HTML5 server-sent events must start with the text `data:` followed by the actual message text and the new line character sequence (`\n\n`).

And finally, we have used the PHP `flush()` function to make sure that the data is sent right away, rather than buffered until the PHP code is complete.

* * *

## Processing Messages in a Web Page

The `EventSource` object is used to receive server-sent event messages.

Now let's create an HTML document named "demo\_sse.html" and place it in the same project directory where the "server\_time.php" file is located. This HTML document simply receives the current time reported by the web server and display it to the user.

#### Example

[Download](https://www.tutorialrepublic.com/html-tutorial/../examples/downloads/html5-server-sent-events.zip "Download Source Code")

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<title>Using Server-Sent Events</title>
<script>
    window.onload = function() {
        var source = new EventSource("server_time.php");
        source.onmessage = function(event) {
            document.getElementById("result").innerHTML += "New time received from web server: " + event.data + "<br>";
        };
    };
</script>
</head>
<body>
    <div id="result">
        <!--Server response will be inserted here-->
    </div>
</body>
</html>
```

* * *