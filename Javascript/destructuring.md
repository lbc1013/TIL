## Destructuring

> ES6 provides a new feature called destructing assignment that allows you to destructure properties of an object or elements of an array into individual variables.
> Destructuring assignment allows for instantly mapping an object or array onto many variables.

# Array destructuring

````javascript
function getScores() {
  return [70, 80];
}

let [x, y, z] = getScores();

console.log(x); // 70
console.log(y); // 80
console.log(z); // undefined

````
# Object destructuring

````javascript
1.

let options = {
  title: 'example',
  width: 100,
  height: 200
};

let {title, width, height} = options;

alert(title);  // 'example'
alert(width);  // 100
alert(height); // 200

2.

let options = {
  title: "example",
  width: 100,
  height: 200
};

// { sourceProperty: targetVariable }
let {width: w, height: h, title} = options;

// width -> w
// height -> h
// title -> title

alert(title);  // 'example'
alert(w);      // 100
alert(h);      // 200

````
