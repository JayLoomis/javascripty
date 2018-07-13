# Flow control

Everything you ever wanted to know about branching and looping in JavaScript.

## Branching

### If statements

```javascript
const MONDAY = 0;
const TUESDAY = 1;
const WEDNESDAY = 2;
const THURSDAY = 3;
const FRIDAY = 4;
const SATURDAY = 5;
const SUNDAY = 6;

if(day >= MONDAY && day <= FRIDAY) {
  alarm = '6:00 am';
} else if(day === SATURDAY) {
  alarm = '7:00 am';
} else if(day === SUNDAY) {
  alarm = '6:30 am';
}
```

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

## Looping

### For loop

C-style.

```javascript
let colors = ['red', 'green', 'blue'];

for(let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}
```

The keywords `break` and `continue` are supported to jump out of the loop and jump to the next iteration
respectively.

### While loop

```javascript
let number = 100;

while(number > 0) {
  console.log(number);
  number--;
}
```

Be careful about infinite loops!

### Iterators

Arrays support a number of iterator methods. They are described with the array information.
