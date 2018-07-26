# Modules

Everything you need to know about JavaScript code modules.

## What's a module?

As in many other languages, a module is a source code file that contains things you want
to make available to other programs. It's essentially a library.

## How to define a module

New syntax for module definition was introduced in ES6. Both the old and new styles are
desribed in the following sections.

### The old way

The old (<ES6) pattern is to wrap the contents of a module in an object, and then expose
that object _as_ the module by using `module.exports`.Like this:

```javascript
let Car = {};

Car.make = 'Mazda';
Car.model = 'Protege';
Car.year = '1999';
Car.drive = 'front';

module.exports = Car;
```

You can also export an anonymous object full of random stuff (it shouldn't be _random_,
but it needn't be as tightly related as a well-designed object). Here's an example:

```javascript
let Car = {}; // Not sure if/why this is still needed.

module.exports = {
  engineSize: 1.6,
  topSpeed: 165  
};
```

### The new way

To use the old paradigm, which is one module (object) per file, you can use the new, more
intuitive syntax:

```javascript
let Car = {};

Car.make = 'Mazda';
Car.model = 'Protege';
Car.year = '1999';
Car.drive = 'front';

export default Car;
```

More importantly, you can now export individual pieces of the file:

```javascript
let make = 'Mazda';
let model = 'Protege';
let year = '1999';
let drive = 'front';

export {make, model, year, drive};
```

You can even export variables as you define them:

```javascript
export let make = 'Mazda';
export let model = 'Protege';
export let year = '1999';
export let drive = 'front';
```

## How to include a module in another code file

As with defining modules, ES6 introduced new ways to import modules. The old and new are
described in the following sections.

### The old way

You can use the `require` function to include your module in another JavaScript file:

```javascript
const Car = require('./car.js');

console.log('The car is a ' + Car.year + ' ' + Car.make + ' ' + Car.model + ' with ' +
            Car.drive + '-wheel drive.';
```

### The new way

Because you can define more than one module in a file, you can nowimport specific modules.

You can import a single item from a file:

```javascript
import Car from './car'; // Note that you don't need the file extension (.js is implied).
```

You can also import multiple items (remember that everything is an object at some level,
so even if you export/import a variable, it's an object):

```javascript
import {make, model, year} from './car'; // This would work with one of the versions of
                                         //  the module definition that define variales
                                         //  outside of an object.
```
