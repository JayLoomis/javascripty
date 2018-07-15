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

## Methods

Methods are just properties that are set to functions. In theory, you can use arrow functions,
the function operator, or new-style method declaration. In practice, it's easiest to use new-style
method declaration for anything new.

### Getters and setters

Use new-style method declaration, but put the get or set keyword in front of it. Common practice is
to name the functionthe property name you want users to use. The actual data member is the same name
prepended with an underscore.

```javascript
const circle = {
  _radius: 0,
  
  // This method uses 'arrow notation'.

  circumference: () => {
    // Have to use circle, not this to get the _radius, because of the arrow notation and scope.
    return (circle._radius * Math.PI * 2) ;
  },      
  
  // This method uses the function operator (anonymous function).
  diameter: function() {
    return this._radius * 2;
  },
  
  // This function uses the modern method syntax.
  area() {
    return Math.PI * (this.radius ** 2);
  },
  
  set radius(newRadius) {
    if(typeof newRadius === 'number') {
      this._radius = newRadius;
    } else {
      console.log('Radius must be set to a number.')
    }
  },
  
  get radius() {
    return this._radius;
  }
};
```

## Classes

Classes are object templates.

```javascript
class Character {
  constructor(name, player) {
    this._name = name;
    this._player = player;
  }
  
  get name() {
    return this._name;
  }
  
  get player() {
    retirn this._player;
  }
}
```

Notice how the class definition differs from object definition:
-   Because you don't assign the object to a variable, there's no semicolon ending the definition.
-   You don't need commas between the members of the class.
