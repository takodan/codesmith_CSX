# Introduction to Closure, Scope and Execution Context from CS prep
```js
function once(callback) {
    let hasBeenRun = false;
    let firstValue;

    return function Fn1(...callbackArgs) { // rest operator
        if( !hasBeenRun) {
            firstValue = callback(...callbackArgs); // spread operator
            hasBeenRun = true;
        }

        return firstValue;
    }
}
const multiplyBy3 = num => num * 3;
const multiplyByTreeOnce = once(multiplyBy3); // invoke once() to return a new Fn1
// this new Fn1 will include a closure in function scope point to variable function related
// they are callback, hasBeenRun and firstValue
const run1 = multiplyByTreeOnce(10)
// after invoke multiplyByTreeOnce(10)
// firstValue = 10 * 3
// hasBeenRun = true
const run2 = multiplyByTreeOnce(8)
// when invoke multiplyByTreeOnce(8)
// because if statement is false, return firstValue
// that is 30
const run3 = multiplyByTreeOnce(108)
// same as run2
console.log(run1, run2, run3) // 30 30 30
```

- Additional resources: 
the Three Dots Operator in JS  
https://www.freecodecamp.org/news/three-dots-operator-in-javascript/  
  1. Spread Operator: to expand an iterable
  2. Rest Operator: to combine any number of arguments into an array

&nbsp;  

# Challenge: Scoping
```js
function outer (){
    let counter = 0;
    function incrementCounter (){
        counter++;
        console.log(counter);
    }
    return incrementCounter;
}
// declare a constant counter1 = return of outer() = incrementCounter
const counter1 = outer()
const counter2 = outer()
counter1(); // 1
counter1(); // 2
counter2(); // 1
counter1(); // 3
counter2(); // 2
```

&nbsp;  

# Challenge: delay
- Additional resources:  
setTimeout()  
https://developer.mozilla.org/en-US/docs/Web/API/setTimeout  

&nbsp;  

# Challenge: cycleIterator
```js
let counter = 0;
function fn1 (array){
    counter++;
    return array[counter-1];
}

// same as
function fn1 (array){
    return array[counter++];
}

```

&nbsp;  

# Challenge: dateStamp
- Additional resources:  
Date()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date
https://www.w3schools.com/js/js_dates.asp

&nbsp;  

# Additional Learning Resources
MDN: Closures  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures  
W3 Schools: JavaScript Closures  
https://www.w3schools.com/js/js_function_closures.asp  
freeCodeCamp: How to Use Closures in JavaScript – A Beginner's Guide  
https://www.freecodecamp.org/news/closures-in-javascript/  