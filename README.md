# ES6-Tutorial
## Array Helper Methods(The goal is to stay away from for loops)
- forEach
```
var images = [
  { height: 10, width: 30 },
  { height: 20, width: 90 },
  { height: 54, width: 32 }
];
var areas = [];

images.forEach(image => {
    areas.push(image.height * image.width);
})
```
- map
  - By far the most common helper function for front end web developers
  - Remember to use return keyword in each pass
```
var images = [
  { height: '34px', width: '39px' },
  { height: '54px', width: '19px' },
  { height: '83px', width: '75px' },
];

var heights= images.map(image => {
    return image.height;
})
```
speed calculation prac
```
var trips = [
  { distance: 34, time: 10 },
  { distance: 90, time: 50 },
  { distance: 59, time: 25 }
];

var speeds = trips.map( trip => {
    return trip.distance / trip.time;
});
```

## Really Hard - Implementing 'Pluck'

This is a hard one!
Implement a 'pluck' function.  Pluck should accept an array and a string representing a property name and return an  array containing that property from each object. 

Example: 
```
var paints = [ { color: 'red' }, { color: 'blue' }, { color: 'yellow' }];
pluck(paints, 'color'); // returns ['red', 'yellow', 'blue'];
```

*Hint:

*Remember that you can access a property on an object by using square bracket notation. For example...
```
var person = { name: 'Bill' };
person['name'] // returns 'Bill'
```
### My solution
```
function pluck(array, property) {
      return array.map(arrayItem =>{
        return arrayItem[property];
    });
}
```
- filter
- find
- every
- some
- reduce
