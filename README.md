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
- filter
- find
- every
- some
- reduce
