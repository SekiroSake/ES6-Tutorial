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

*Hint:*

*Remember that you can access a property on an object by using square bracket notation. For example...*
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
Example
```
products=[{"name":"apple",
          "type":"fruit"},
          {name":"celery",
          "type":"vegetable"}];
       
products.filter(function(product){
    return product.type === "fruit";      
});

       
```
## Hard question for filter
### Challenging! Implementing 'reject'.

This is a hard one!  Create a function called 'reject'.  Reject should work in the opposite way of 'filter' - if a function returns 'true', the item should *not* be included in the new array.  Hint: you can reuse filter.


- For example:
```
var numbers = [10, 20, 30];
var lessThanFifteen = reject(numbers, function(number){
  return number > 15;
}); 
```
- solution
```
function reject(array, iteratorFunction) {
  var firstArray = array.filter(arrayItem =>{
      return iteratorFunction(arrayItem);
  });

  
 return array.filter(arrayItem => {
     console.log("arrayItem: " + arrayItem);
     for(var i = 0; i <= firstArray.length; i++){
           
         if(firstArray[i] === arrayItem){
           
              return false;
         }
        
     }
  return true;});
 
}
```
lessThanFifteen // [ 10 ];
- find
- every
- some
- reduce
