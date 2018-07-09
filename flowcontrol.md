# Flow control

Everything you ever wanted to know about branching and looping in JavaScript.

## Branching

### If statements

### Switch statements

```javascript
// Assume that we'll get this set to an indeterminate value.
let dayOfWeek = 'monday';

// A string to hold the message for the user.
let message = '';

switch(dayOfWeek) {
  case 'Monday':
    message = 'You can fall apart';
    break;
  case 'Tuesday':
  case 'Wednesday':
    message = 'Break my heart';
    break;
  case 'Thursday':
    message = 'Doesn\'t even start';
    break;
  case 'Friday':
    message = 'I\'m in love';
    break;
  case 'Saturday':
    message = 'Wait';
    break;
  case 'Sunday':
    message = 'Always comes too late';
    break;
}
```

### Ternary operator

JavaScript includes a C-style ternary operator:

```javascript
const COIN_SIDES = ['heads', 'tails'];

// Get a random coin side.
let sideUp = COIN_SIDES[Math.floor(Math.random() * 2)];

let message = sideUp === 'heads' ? 'Heads, I win!' : 'Tales, you lose!';
```
