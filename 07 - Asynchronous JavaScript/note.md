# JSHP: Promises, Async & the Event Loop workshop
JavaScript is a single-threaded language.
synchronous executed: each line run in order the code appears.

## in ES5: callback
```js
// 1. declare a function printHello in global memory
function printHello(){
    console.log("Hello");
}
// 2. invoke setTimeout, open a new execution context, push a new stack frame, pair paras and args
setTimeout(printHello, 1000);
// setTimeout will push printHello and 1000 to Web Browser API
// 3. log "Me first!"
console.log("Me first!");
// if there is more code, js will run through all of it.
// 4. a loop checking callback queue (event loop)
// 5. when time's up in Web Browser API, it push printHello to callback queue
// 6. event loop found printHello in callback queue, push printHello to call stack
// 7. log Hello
```
All synchronous code execute first, then other things.

- Additional resources:  
Stacks, Queues, & Lists  
https://thenumb.at/cpp-course/ds/03/03.html  

&nbsp;  

## in ES6: Promises
Promise is a standard built-in objects (like Array).  
It has several internal properties:  
1. PromiseStatus: pending(initial state), resolved(completed), rejected(failed)  
2. PromiseValue: return value from fulfilled or rejected the operation  
You can chained callback function to Promise by the methods then(), catch(), and finally()  
These will take PromiseValue as a argument
1. then(callback1, callback2): when resolved, push the callback1 microtask queue. when rejected, push the callback2.
2. catch(callback): only when rejected , push the callback to microtask queue.
3. finally(callback): push the callback after then() and catch().

```js
function display(data) {
    console.log(data)
}

const futureData = fetch("https://twitter.com/"); // fetch will return a promise object and do things in Web Browser API
futureData.then(display); // chained display to futureData
// after things finish in Web Browser API, it return value to PromiseValue and change PromiseStatus to resolved or rejected
// depend on what chained to Promise, push callback to microtask queue (a queue similar to callback queue)
// microtask queue is prior to callback queue
console.log("Me first!");
// after all synchronous code execute, then checking queues
```

- Additional resources:  
Using promises  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises  
Promise  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise  
Promise(chinese)  
https://www.casper.tw/development/2020/02/16/all-new-promise/  

&nbsp;  

# Challenge: runInOrder
my solution (with setTimeout): using callback hell.
CSX solution: declare a variable accumulate times, so next callback need to wait longer.

&nbsp;  

# Additional Learning Resources
MDN: Asynchronous JavaScript  
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous  
Eloquent Javascript: Asynchronous Programming  
https://eloquentjavascript.net/11_async.html  
freeCodeCamp: Synchronous vs Asynchronous JavaScript  
https://www.freecodecamp.org/news/synchronous-vs-asynchronous-in-javascript/  