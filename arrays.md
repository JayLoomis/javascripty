# Arrays

```javascript
let myArray = [1, 2, 3, 4, 5];
```

```javascript
let daysOfWeek = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'];

// Arrays are zero-based.
console.log('The third day of the week is ' + daysOfWeek[2]);
```

```javascript
// Print every item in the array.
myArray.forEach(function(item){
  console.log(item);
});
```

```javascript
let transformedArray = myArray.map(function(item) {
  return item * 7;
});  
```

```javascript
let numbers = [548, 589, 305, 250, 963, 98, 650, 357, 583, 547,
               189, 448, 31, 733, 294, 846, 803, 190, 640, 561];

let bigNumbers = numbers.filter(function(number) {
  return number >= 500;
});
```
