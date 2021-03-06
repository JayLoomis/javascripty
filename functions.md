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
-   You can omit parameters, in which case, they are passed to the function as `undefined`.
-   You can't skip a parameter if you're providing a later parameter--you must explicitly pass `null`
    or some other value that makes sense.
-   There are no default values for parameters. You can implement the same behavior by using the 
    assignment form of the OR operator.
-   There are no variable length arguments. You can implement the same functionality by passing an array
    or object.
    
## Static variables

A static variable is a variable that is allocated once, when the function is declared, and is kept
for the duration of the function's life. This is in contrast to regular local variables defined in
a function, which are allocated each time the function is called.

The practical definition of a static variable is a variable that retains its value across all calls
to the function. The simplest use of a static variable is to accumulate values for every call to the
function.

While JavaScript uses the `static` keyword for static methods in objects, it doesn't support its use
for static variables in functions. However, because functions are objects in JavaScript, you can
define a static varaible as a member variable of the function's class. It's good form to check whether
the static function exists, especially because it gives you a reliable way to initialize it. Here's an
example:

```javascript
function accumulator(num) {
  // The first time the function is called, initialize a static variable.
  if(typeof accumulator.total == 'undefined')
    accumulator.total = 0;
  
  // Every time the function is called, add the number to the total.
  accumulator.total += num;
}
```

## Examples

### Example of default parameters

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

// This is fine. It creates a rectangle with these coordinates: 0, 0, 100, 200.
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

### Example with a varibale number of parameters

The only way to do this is with an array as a parameter:

```javascript
// This function takes an array of any number of numbers and returns their sum.
function variableParams(numbersArray) {
  let sum = 0;

  numbersArray.forEach(function(number) {
    sum += number;
  });
    
  return sum;
}
  
let myNumbers = [1, 2, 3, 4, 5];
  
let total = variableParams(myNumbers);
  
console.log(total); // Should output 15 to the console.
```

While this technique feels most logically appropriate for an indeterminate number of parameters
of the same type, as in the example, there are plenty of cases where mixed types would make sense.
For example, the canonical example of this in C is `printf`, where the first parameter includes
all the information needed to anticipate what follows. Here's a format function like the one in
Python:

```javascript
// This function takes an array of values, where the first is a string template and the rest are
//  items to plug into the template.
// Example:
//   myString = formatString("Last updated {}/{}/{}", 6, 6, 2019);
function formatString(template, args) {
  
}
```
