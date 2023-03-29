# Introduction to Functions and Execution Context video
what happens when javascript executes (runs) code:
```js
// 1. as soon as it start running, it create a global execution context, push golobal() in callstack
//   include thread of execution and global memory
// 2. declaring a constant variable called num assign value 3 => save in global memory num(lable): 3(value)
const num = 3;
// 3. a function declaration call multiplyBy2 => save in memory multiplyBy2 : {...}
function multiplyBy2 (inputNumber){
    // not call the function yet
    // 6. creat a local execution context for function
    // 7. creat parameter(placeholder) with value from argument => save in local memory
    // 8. declaring result => save in local memory
    const result = inputNumber*2;
    // 9. return the value of result back to output in global memory and exit function
    //   pop out multiplyBy2(4) from call stack
    return result;
}
// 4. declaring a constant variable call name => save in global memory
const name = "Will";
// 5. declaring a constant variable name output (value undefine yet)
//   and run/call/invoke the function multiplyBy2 with argument 4
//   push multiplyBy2(4) in call stack
const output = multiplyBy2(4);
// 10. declaring a constant variable name newOutput (value undefine yet)
//   push multiplyBy2(10) in call stack
//   and do the similary from step 6 to step 9
const newOutput = multiplyBy2(10);
```

call stack: a mechanism for an interpreter to keep track of its place in a script that calls multiple functions. last in first out.  
https://developer.mozilla.org/en-US/docs/Glossary/Call_stack

# Intro to JavaScript: Functions and Objects workshop video
## Functions
similar to last video
## Object
```js
const person = {
    name: "Dan"; // key-value pairs called properties
    greeting: function(){
        return "Hello";
    }
}

console.log(person.function); // => f (){...}
console.log(pperson.function()); // => "Hello"
console.log(person["function"]); // => f (){...}
console.log(pperson["function"]()); // => "Hello"
```

&nbsp;  

# Challenge: Using forEach

```js
const array1 = ['a', 'b', 'c'];

array1.forEach(element => console.log(element));

// Expected output:
// "a"
// "b"
// "c"
```
- Additional resources:  
Array.prototype.forEach()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach


&nbsp;  

# Challenge: Control Flow - if statements and the Math object
```js
Math.abs(-7) // 7,  absolute value of number
Math.ceil(1.4) // 2, smallest integer greater than or equal to number
Math.floor(1.6) // 1 , largest integer less than or equal to number
Math.max(5,10); // 10, largest of numbers
Math.min(5,10); // 5, smallest of numbers
Math.pow(4,3); // 64 , 4 to the power of 3, 4**3
Math.random(); // 0.0 ~ 1.0, random number between 0 and 1
Math.round(2.49); // 2, nearest integer
Math.trunc(8.76); // 8, integer portion of number
```
- Additional resources:  
Math  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math  

# Challenge: disemvowel
checking multiple element in string/array approach
```js
// creat a object that include element to be checked
let arr = [ "a", "b", "c", "d" ]
let obj = {
    "a": true;
    "e": true;
}
// iterate element in array
for ( let i in array){
    let element = array[i]
    // if element in array is also key in obj
    if(obj[element]){
        console.log( element + " is in obj")
    }else{
        console.log( element + " is not in obj")
    }
}
```
- Additional resources:  
String.prototype.match()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match  
String.prototype.replace()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace  
RegExp  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp  


&nbsp;  

# Challenge: Functions - Function Expression
```js
const getRectArea = function(width, height) {
  return width * height;
};

console.log(getRectArea(3, 4));
// Expected output: 12
```
- Additional resources:  
Function expression  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function

&nbsp;  

# Challenge: Functions - ES6 (arrow function)
```js
// Traditional anonymous function
(function (a, b) {
  return a + b + 100;
});
// Arrow function
(a, b) => a + b + 100;


// Traditional anonymous function (no parameters)
(function () {
  return a + b + 100;
});
// Arrow function (no parameters)
() => a + b + 100;


// Traditional Function
function bob(a) {
  return a + 100;
}
// Arrow Function
const bob2 = (a) => a + 100;
```
- Additional resources:  
Arrow function expressions  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions
