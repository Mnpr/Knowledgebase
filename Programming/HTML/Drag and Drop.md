Drag and Drop


# HTML5 Drag and Drop

## Drag and Drop an Element

The HTML5 drag and drop feature allows the user to drag and drop an element to another location. The drop location may be a different application. While dragging an element a translucent representation of the element is follow the mouse pointer.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Using Drag and Drop</title>
<script>
    function dragStart(e) {
        // Sets the operation allowed for a drag source
        e.dataTransfer.effectAllowed = "move";
    
        // Sets the value and type of the dragged data
        e.dataTransfer.setData("Text", e.target.getAttribute("id"));
    }
    function dragOver(e) {
        // Prevent the browser default handling of the data
        e.preventDefault();
        e.stopPropagation();
    }
    function drop(e) {
        // Cancel this event for everyone else
        e.stopPropagation();
        e.preventDefault();
    
        // Retrieve the dragged data by type
        var data = e.dataTransfer.getData("Text");
    
        // Append image to the drop box
        e.target.appendChild(document.getElementById(data));
    }
</script>
<style>
    #dropBox {
        width: 300px;
        height: 300px;
        border: 5px dashed gray;
        background: lightyellow;
        text-align: center;
        margin: 20px 0;
        color: orange;
    }
    #dropBox img {
        margin: 25px;
    }
</style>
</head>
<body>
    <h2>Drag and Drop Demo</h2>
    <p>Drag and drop the image into the drop box:</p>
    <div id="dropBox" ondragover="dragOver(event);" ondrop="drop(event);">
        <!--Dropped image will be inserted here-->
    </div>
    <img src="../images/kites.jpg" id="dragA" draggable="true" ondragstart="dragStart(event);" width="250" height="250" alt="Flying Kites">
</body>
</html>
```

**Tip:** You can make an element draggable by setting the draggable attribute to true, like `draggable="true"`. However, in most web browsers, text selections, images, and anchor elements with an `href` attribute are draggable by default.

* * *

## Drag and Drop Events

A number of events are fired during the various stages of the drag and drop operation. But mouse events such as mousemove are not fired during a drag operation.

The following table provides you a brief overview of all the drag and drop events.

| Event | Description |
| --- | --- |
| `ondragstart` | Fires when the user starts dragging an element. |
| `ondragenter` | Fires when a draggable element is first moved into a drop listener. |
| `ondragover` | Fires when the user drags an element over a drop listener. |
| `ondreagleave` | Fires when the user drags an element out of drop listener. |
| `ondrag` | Fires when the user drags an element anywhere; fires constantly but can give X and Y coordinates of the mouse cursor. |
| `ondrop` | Fires when the user drops an element into a drop listener successfully. |
| `ondragend` | Fires when the drag action is complete, whether it was successful or not. This event is not fired when dragging a file to the browser from the desktop. |

**Note:** The HTML5's drag and drop feature is supported in all major modern browsers like Firefox, Chrome, Opera, Safari and Internet Explorer 9 and above.

* * *