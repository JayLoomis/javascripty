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
