Ajax


# JavaScript Ajax

## What is Ajax?

Ajax stands for **A**synchronous **J**avascript **A**nd **X**ml. Ajax is just a means of loading data from the server and selectively updating parts of a web page without reloading the whole page.

Basically, what Ajax does is make use of the browser's built-in `XMLHttpRequest` (XHR) object to send and receive information to and from a web server asynchronously, in the background, without blocking the page or interfering with the user's experience.

Ajax has become so popular that you hardly find an application that doesn't use Ajax to some extent. The example of some large-scale Ajax-driven online applications are: Gmail, Google Maps, Google Docs, YouTube, Facebook, Flickr, and so many other applications.

**Note:** Ajax is not a new technology, in fact, Ajax is not even really a technology at all. Ajax is just a term to describe the process of exchanging data from a web server asynchronously through JavaScript, without refreshing the page.

**Tip:** Don't get confused by the term **X** (i.e. **XML**) in AJAX. It is only there for historical reasons. Other data exchange format such as JSON, HTML, or plain text can be used instead of XML.
* * *
## Understanding How Ajax Works

To perform Ajax communication JavaScript uses a special object built into the browser—an `XMLHttpRequest` (XHR) object—to make HTTP requests to the server and receive data in response.

All modern browsers (Chrome, Firefox, IE7+, Safari, Opera) support the `XMLHttpRequest` object.

The following illustrations demonstrate how Ajax communication works:

![Ajax Illustration](../../../../_resources/f6d4934685354d729d5341716c36dfa1.png)

Since Ajax requests are usually asynchronous, execution of the script continues as soon as the Ajax request is sent, i.e. the browser will not halt the script execution until the server response comes back.

In the following section we'll discuss each step involved in this process one by one:
* * *
## Sending Request and Retrieving the Response

Before you perform Ajax communication between client and server, the first thing you must do is to instantiate an `XMLHttpRequest` object, as shown below:

var request = new XMLHttpRequest();

Now, the next step in sending the request to the server is to instantiating the newly-created request object using the `open()` method of the XMLHttpRequest object.

The `open()` method typically accepts two parameters— the HTTP request method to use, such as "GET", "POST", etc., and the URL to send the request to, like this:

request.open("GET", "info.txt"); -Or- request.open("POST", "add-user.php");

**Tip:** The file can be of any kind, like `.txt` or `.xml`, or server-side scripting files, like `.php` or `.asp`, which can perform some actions on the server (e.g. inserting or reading data from database) before sending the response back to the client.

And finally send the request to the server using the `send()` method of the XMLHttpRequest object.

request.send(); -Or- request.send(_body_);

**Note:** The `send()` method accepts an optional `_body_` parameter which allow us to specify the request's body. This is primarily used for HTTP POST requests, since the HTTP GET request doesn't have a request body, just request headers.

The GET method is generally used to send small amount of data to the server. Whereas, the POST method is used to send large amount of data, such as form data.

In GET method, the data is sent as URL parameters. But, in POST method, the data is sent to the server as a part of the HTTP request body. Data sent through POST method will not visible in the URL.

[HTTP GET vs. POST](https://www.tutorialrepublic.com/php-tutorial/php-get-and-post.php)

* * *
## Performing an Ajax GET Request

The GET request is typically used to get or retrieve some kind of information from the server that doesn't require any manipulation or change in database, for example, fetching search results based on a term, fetching user details based on their id or name, and so on.

#### Example | Ajax GET request in JavaScript.

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>JavaScript Ajax GET Demo</title>
<script>
function displayFullName() {
    // Creating the XMLHttpRequest object
    var request = new XMLHttpRequest();

    // Instantiating the request object
    request.open("GET", "greet.php?fname=John&lname=Clark");

    // Defining event listener for readystatechange event
    request.onreadystatechange = function() {
        // Check if the request is compete and was successful
        if(this.readyState === 4 && this.status === 200) {
            // Inserting the response from server into an HTML element
            document.getElementById("result").innerHTML = this.responseText;
        }
    };

    // Sending the request to the server
    request.send();
}
</script>
</head>
<body>
    <div id="result">
        <p>Content of the result DIV box will be replaced by the server response</p>
    </div>
    <button type="button" onclick="displayFullName()">Display Full Name</button>
</body>
</html>
```

When the request is asynchronous, the `send()` method returns immediately after sending the request. Therefore you must check where the response currently stands in its lifecycle before processing it using the `readyState` property of the `XMLHttpRequest` object.

The `readyState` is an integer that specifies the status of an HTTP request. Also, the function assigned to the `onreadystatechange` event handler called every time the `readyState` property changes. The possible values of the `readyState` property are summarized below.

| Value | State | Description |
| --- | --- | --- |
| `0` | `UNSENT` | An `XMLHttpRequest` object has been created, but the `open()` method hasn't been called yet (i.e. request not initialized). |
| `1` | `OPENED` | The `open()` method has been called (i.e. server connection established). |
| `2` | `HEADERS_RECEIVED` | The `send()` method has been called (i.e. server has received the request). |
| `3` | `LOADING` | The server is processing the request. |
| `4` | `DONE` | The request has been processed and the response is ready. |

**Note:** Theoretically, the `readystatechange` event should be triggered every time the `readyState` property changes. But, most browsers do not fire this event when `readyState` changes to 0 or 1. However, all browsers fire this event when `readyState` changes to 4 .

The `status` property returns the numerical HTTP status code of the XMLHttpRequest's response. Some of the common HTTP status codes are listed below:

*   200 — OK. The server successfully processed the request.
*   404 — Not Found. The server can't find the requested page.
*   503 — Service Unavailable. The server is temporarily unavailable.

Ref : [HTTP status codes](https://www.tutorialrepublic.com/html-reference/http-status-codes.php)

Here's the code from our "greet.php" file that simply creates the full name of a person by joining their first name and last name and outputs a greeting message.

#### Example

[Download](https://www.tutorialrepublic.com/javascript-tutorial/../examples/bin/download-source.php?topic=php&file=greet "Download Source Code")

```php
<?php
if(isset($_GET["fname"]) && isset($_GET["lname"])) {
    $fname = htmlspecialchars($_GET["fname"]);
    $lname = htmlspecialchars($_GET["lname"]);
    
    // Creating full name by joining first and last name
    $fullname = $fname . " " . $lname;

    // Displaying a welcome message
    echo "Hello, $fullname! Welcome to our website.";
} else {
    echo "Hi there! Welcome to our website.";
}
?>
```

* * *

## Performing an Ajax POST Request

The POST method is mainly used to submit a form data to the web server.

Submit form data to the server using Ajax.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>JavaScript Ajax POST Demo</title>
<script>
function postComment() {
    // Creating the XMLHttpRequest object
    var request = new XMLHttpRequest();
    
    // Instantiating the request object
    request.open("POST", "confirmation.php");
    
    // Defining event listener for readystatechange event
    request.onreadystatechange = function() {
        // Check if the request is compete and was successful
        if(this.readyState === 4 && this.status === 200) {
            // Inserting the response from server into an HTML element
            document.getElementById("result").innerHTML = this.responseText;
        }
    };
    
    // Retrieving the form data
    var myForm = document.getElementById("myForm");
    var formData = new FormData(myForm);

    // Sending the request to the server
    request.send(formData);
}
</script>
</head>
<body>
    <form id="myForm">
        <label>Name:</label>
        <div><input type="text" name="name"></div>
        <br>
        <label>Comment:</label>
        <div><textarea name="comment"></textarea></div>
        <p><button type="button" onclick="postComment()">Post Comment</button></p>
    </form>    
    <div id="result">
        <p>Content of the result DIV box will be replaced by the server response</p>
    </div>    
</body>
</html>
```

If you are not using the `FormData` object to send form data, for example, if you're sending the form data to the server in the _query string_ format, i.e. `request.send(key1=value1&key2=value2)` then you need to [explicitly set the request header](https://www.tutorialrepublic.com/javascript-tutorial/../codelab.php?topic=javascript&file=set-request-header) using `setRequestHeader()` method, like this:

request.setRequestHeader("Content-type", "application/x-www-form-urlencoded");

The `setRequestHeader()` method, must be called after calling `open()`, but before calling `send()`.

Some common request headers are: `application/x-www-form-urlencoded`, `multipart/form-data`, `application/json`, `application/xml`, `text/plain`, `text/html`, and so on.

**Note:** The `FormData` object provides an easy way to construct a set of key/value pairs representing form fields and their values which can be sent using `XMLHttpRequest.send()` method. The transmitted data is in the same format that the form's `submit()` method would use to send the data if the form's encoding type were set to `multipart/form-data`.

Here's the code of our "confirmation.php" file that simply outputs the values submitted by the user.

#### Example

[Download](https://www.tutorialrepublic.com/javascript-tutorial/../examples/bin/download-source.php?topic=php&file=confirmation "Download Source Code")

```php
<?php
if($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = htmlspecialchars(trim($_POST["name"]));
    $comment = htmlspecialchars(trim($_POST["comment"]));
    
    // Check if form fields values are empty
    if(!empty($name) && !empty($comment)) {
        echo "<p>Hi, <b>$name</b>. Your comment has been received successfully.<p>";
        echo "<p>Here's the comment that you've entered: <b>$comment</b></p>";
    } else {
        echo "<p>Please fill all the fields in the form!</p>";
    }
} else {
    echo "<p>Something went wrong. Please try again.</p>";
}
?>
```

For security reasons, browsers do not allow you to make cross-domain Ajax requests. This means you can only make Ajax requests to URLs from the same domain as the original page, for example, if your application is running on the domain "mysite.com", you cannot make Ajax request to "othersite.com" or any other domain. This is commonly known as _same origin policy_.

However, you can load images, style sheets, JS files, and other resources from any domain.

**Tip:** Check out the [jQuery Ajax methods](https://www.tutorialrepublic.com/jquery-tutorial/jquery-ajax-get-and-post-requests.php) for quick and seamless Ajax implementation. The jQuery framework provides very convenient methods to implement Ajax functionality.


* * *