# Variables and friends

All you need to know about variables in JavaScript.

## Declaration

### Using `var` for global variables

When you decalre a variable with the `var` keyword, its scope is global.

```
var myString = 'Foo';
```

JavaScript doesn't handle name collisions very elegantly, which can lead to confusion.

In the following example, you might think that the second `var` defines a new variable
scoped to the block it's in:

```
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

```
let myString = 'Foo';
```

If you use the same code used in the `var` example, but use `let` instead, you'll get
different results:

```
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

###
