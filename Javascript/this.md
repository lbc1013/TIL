## 'this' keyword

> The 'this' keyword refers to the object that the function is a property of.

> The value of 'this' keyword will always depened on the object that is invoking the function.

````javascript
example 1)
function test () {
  console.log(this);
}

test();
````
=> In this case, the value of this will be the global object, since the function is invoked in the global context and the function is a property of the global object.

````javascript
example 2)
function obj () {
  fruit: 'apple',
  getFruitName: function() {
    console.log(this.fruit);
  }
}

obj.getFruitName();
````
=> The value of 'this' keyword will be 'apple'. The getFrunitName is a property of the object obj, therefore, the 'this' keyword will refer to the object obj.

````javascript
example 3)
function obj () {
  fruit: 'apple',
  getFruitName: function() {
    console.log(this.fruit);
  }
}

var getFruitName = obj.getFruitName;
var obj2 = {fruit: 'banana', getFruitName}

obj2.getFruitName();
````
==> The output will be 'banana'.

Although the getFruitName function is declared inside the object obj , at the time of invocation, getFruitName() is a property of obj2 , therefore the “this” keyword will refer to obj2 .


