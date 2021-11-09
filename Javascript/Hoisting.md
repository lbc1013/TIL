## Hoisting

> Before the JavaScript interpreter runs a program execution, it will "hoist" all var statements as well as all function declarations to the top of the program, making that declaration known to the whole program.
And this is specific to `var` and function declarations `function someFunc() {}`.

> Declaration phase -> Initialization phase -> Assignment phase

###1st example

````javascript
  foo();
  foo2();

  function foo() { // 함수선언문
          console.log("hello");
  }
  var foo2 = function() { // 함수표현식
          console.log("hello2");
  }
````

##2nd example
````javascript
console.log(test(2,3)); // this returns 5
console.log(age); // this returns undefined
console.log(name); // this returns ReferenceError

function test (x,y) {
  return x + y;
}

const name = 'ByungChan';

var age = 30;
````