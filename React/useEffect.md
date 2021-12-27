## useEffect

The <b>useEffect</b> is one of React Hooks for side effects.</br>
It takes two parameters. </br>
 - 1st : a function </br>
 - 2nd : array </br>

You can pass a function as the first argument that will run after each render.
In many cases, it's unnecessary to call the effect function after every render, therefore, <b>useEffect</b> takes a second argument of an array of values. If passing in this second argument, the effect function will only run when the values in array change.

````javascript
useEffect(() => console.log('rendered!'));
// The function runs after every render.

useEffect(() => console.log('rendered'), [props.todos]);
// The function runs both on the first render and everytime todos changes .


useEffect(() => console.log('rendered'), []);
// The function only runs once the first render.
````
