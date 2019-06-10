# JavaScript Events

When running JavaScript in a browser, you get a lot of control and user
user interaction through the browser by way of events.



## The load event
The Load event fires when the browser is finished loading the HTML in a page
and associated content. In some cases, you'll want to wait until load fires to
run your scripts.

```javascript
window.addEventListener('load', function(){
  // Stuff to do on load goes here.
}
```

## Mouse events

```javascript
canvas.addEventListener("mousedown", function(){
  player.isMoving = true;
});

canvas.addEventListener("mouseup", function(){
  player.isMoving = false;
});
```
0---|--10|----|--20|----|--30|----|--40|----|--50|----|--60|----|--70|----|--80|
