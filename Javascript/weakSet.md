# WeakSet

> - In javascript, Set is a collection of unique and ordered elements.

> - Just like Set, WeakSet is also a collection of unique and ordered elements with some key differences:
1. Weakset contains only objects and no other type.
2. An object inside the weakset is referenced weakly. This means, if the object inside the weakset does not have a reference, it will be garbage collected.
3. Unlike Set, WeakSet only has three methods, add() , delete() and has() .

````javascript
const newSet = new Set([4, 5, 6, 7]);
console.log(newSet);// Outputs Set {4,5,6,7}

const newSet2 = new WeakSet([3, 4, 5]); //Throws an error


let obj1 = {message:"Hello world"};
const newSet3 = new WeakSet([obj1]);
console.log(newSet3.has(obj1)); // true
````
