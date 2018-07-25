# Modules

Everything you need to know about JavaScript code modules.

## What's a module?

As in many other languages, a module is a source code file that contains things you want
to make available to other programs. It's essentially a library.

## How to define a module

I'm not 100% sure yet, but it seems like the pattern is to wrap the contents of a module
in an object, and then expose that object _as_ the module by using `module.exports`.
Like this:

```javascript
let Car = {};

Car.make = 'Mazda';
Car.model = 'Protege';
Car.year = '1999';
Car.drive = 'front';

module.exports = Car;
```

## How to include a module in another code file

You can use the `require` function to include your module in another JavaScript file:

```javascript
const Car = require('./car.js');

console.log('The car is a ' + Car.year + ' ' + Car.make + ' ' + Car.model + ' with ' +
            Car.drive + '-wheel drive.';
```
