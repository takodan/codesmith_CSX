# Introduction to Closure, Scope and Execution Context video
```js
function outer (){
    let counter = 0;
    function incrementCounter (){
        counter++;
        console.log(counter);
    }
    return incrementCounter;
}
// declare a constant myNew = return of outer() = incrementCounter
const myNew = outer()
myNew();
myNew();
```