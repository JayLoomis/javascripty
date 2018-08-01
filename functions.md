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


