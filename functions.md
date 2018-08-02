# Functions

Putting the fun in JavaScript functions.

## Simple functions

Use the `function` keyword to make a function:

```javascript
function addTwoNumbers(n1, n2) {
  return n1 + n2;
}
```

### Return values

If you don't return a value from a function, it returns `undefined`.

### Parameters

-   Parameters aren't explicitly typed.
-   Parameters must be given in the correct order.
-   Numbers and strings are passed by value.
-   Objects and arrays are passed by reference.
-   You can omit parameters, in which case, they are passed intot he function as `undefined`.
-   You can't skip a parameter if you're providing a later parameter--you must explicitly pass `null`
    or some other value that makes sense.
-   There are no default values for parameters. You can implement the same behavior by using the 
    assignment form of the OR operator.
-   There are no variable length arguments. You can implement the same functionality by passing an array
    or object.

## Examples

```javascript
// A function with default parameter values
function createRect(upperLeftX, upperLeftY, lowerRightX, lowerRightY) {
  upperLeftX = upperLeftX || 0;
  upperLeftY = upperLeftY || 0;
  lowerRightX = lowerRightX || 100;
  lowerRightY = lowerRightY || 100;
  ...
}
```

The previous example works well if you want to specify the origin coordinates and sometimes use default
width and height:

```javascript
createRect(0, 0, 640, 480);

// This is fine. It creates a rectangle with these coordinates: 0, 0, 100, 100.
createRect(100, 200);

// This is fine, but kind of a pain.
createRect(null, null, 640, 480);
```

An easier way to allow multiple configurations of parameters is to pass in an object:

```javascript
function createRect(rectParams) {
  if(rectParams.upperLeftX) {
    if(rectParams.upperLeftY) {
      // Use the origin coordinates.
    } else {
      // Error condition: if you pass one coordinate for a point, you have to pass the other.
    }
  } else {
    // Do whatever you're going to when the origin point is omitted.
  }
  
  if(rectParams.lowerRightX) {
    if(rectParams.lowerRightY) {
      // Use the extent coordinates.
    } else {
      // Error condition: if you pass one coordinate for a point, you have to pass the other.
    }
  } else {
    // Do whatever you're going to when the extent point is omitted.
  }
  
  // To be complete, there should be checks for the Y coordinates to handle the case where a
  //  Y is passed without the corresponding X. It's the same error condition used above.
}
```
