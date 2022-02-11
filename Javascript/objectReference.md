# Object References and Copying

> - One of the fundamental differences of objects versus primitives is that objects are stored and copied "by reference", whereas primitive values copied "as a whole value".

## The Primitives Type

````javascript
let message = "Hello";
let phrase = message;
````
=> As a result, each variable stores the string "hello" like storing in the each box.

## Non-Primitives Type (Object)

````javascript
let user = {
  name : "John"
}
// The object is stored somewhere in memory, while the "user" variable has a "reference" to it now.

// When an object variable is copied, the reference is copied, but the object itself is not duplicated.

let admin = user; //=> copy the reference
// Now the two variable stores a "reference" to the same object.

admin.name = 'Peter';
console.log(user.name); //We get "Peter" instead of "John"
````

=> A variable assigned to an object stores not the object itself, but its `"address in memotry"` - in other words a `"reference"` to it.
