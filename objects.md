# Objects

Getting oriented to JavaScript objects.

## Basic facts

JavaScript objects:

-   Contain data and functions.
-   Are mutable&mdash;you can add things to them dynamically.
-   Are unordered&mdash;the only way to access members is by name.
-   Use dot notation to access their members.

## Defining an object

Here's an example of an object:

```javascript
let car = {
  make: 'Honda',
  model: 'CRV',
  color: 'Red'
}
```

## Accessing members

You have two choices: dot notation, and bracket notation.

### Dot notation

```
console.out(car.make);
```

### Bracket notation

```
console.out(car['make']);
```

The primary advantage of bracket notation is that you can use a string variable to specify the
member at runtime.
