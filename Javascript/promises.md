# Promises

> - Promises are used to handle asynchronous operations like server requests in javascript.

> - Before promises, callbacks were used to handle asynchronous operations. But due to limited functionality of callback, using multiple callbacks to handle asynchronous code can lead to unmanageable code.

> - A promise is created using the Promise constructor which takes in a callback function with two parameters, resolve and reject respectively.

###### * resolve is a function that will be called, when the async operation has been successfully completed.

###### * reject is a function that will be called, when the async operation fails or if some error occurs.


````javascript
function sumOfThreeElements(...elements){
  return new Promise((resolve,reject)=>{
    if(elements.length > 3 ){
      reject("Only three elements or less are allowed");
    }
    else{
      let sum = 0;
      let i = 0;
      while(i < elements.length){
        sum += elements[i];
        i++;
      }
      resolve("Sum has been calculated: "+sum);
    }
  })
}
````

- then() method is used to access the result when the promise is fulfilled.
- catch() method is used to access the result/error when the promise is rejected.

````javascript
sumOfThreeElements(4, 5, 6)
.then(result=> console.log(result))
.catch(error=> console.log(error));
// In the code above, the promise is fulfilled so the then() method gets executed

sumOfThreeElements(7, 0, 33, 41)
.then(result => console.log(result))
.catch(error=> console.log(error));
// In the code above, the promise is rejected hence the catch() method gets executed
````
