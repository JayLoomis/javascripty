# Variables and friends

All you need to know about variables in JavaScript.

## Declaration

### Using `var` for global variables

When you decalre a variable with the `var` keyword, its scope is global.

```javascript
var myString = 'Foo';
```

JavaScript doesn't handle name collisions very elegantly, which can lead to confusion.

In the following example, you might think that the second `var` defines a new variable
scoped to the block it's in:

```javascript
var x = 1;

if(x === 1) {
  var x = 2;
  console.log(x);
}

console.log(x);
```

However, the output is:

```
2
2
```

Instead of creating a new, scoped variable `x` inside the `if` block, JavaScript
assumes you're talking about the previous example.

### Using `let` for block-scoped variables

When you declare a variable with the `let` keyword, it is scoped to the block that it's
decalred in.

```javascript
let myString = 'Foo';
```

If you use the same code used in the `var` example, but use `let` instead, you'll get
different results:

```javascript
let x = 1;

if(x === 1) {
  let x = 2;
  console.log(x);
}

console.log(x);
```

The output is:

```
2
1
```

In case you're wondering, the scoped variable works the same way even if the outer variable
is defined with `var`.

### Using `const` for constants

You can define a constant the same way you would a variable, but use the `const` keyword.

```javascript
const RED = 0xFF0000;
```

If you try to assign a value to a constant, you'll get a `TypeError`.

## Data types

Variables have types, but they are dynamic, meaning that you can reassign a variable to whatever type
you need without any special syntax.

The supported data types are:
-   [Number](#numbers)
-   [String](#strings)
-   [Boolean](#booleans)
-   [Function](#functions)
-   [Object](#objects)
-   [Undefined](#undefined)
-   [Not a number (NaN)](#not-a-number)

### Numbers

There is only one numeric type in JavaScript: 64-bit floating point, but you can omit the decimal point
and treat them as integers if you like.

#### Numeric literals

