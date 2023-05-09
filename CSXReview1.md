# Functions and Execution Context
- string dose have property `length `.
- `arr.push()`: adds to the "end" and returns "the new length".
- `arr.pop()`: removes the "last" and returns "that array".
- `arr.unshift()`: adds to the "beginning" and returns "the new length".
- `arr.shift()`: removes the "first" and returns "that array".
- `arr.map()`: returns "a new array".
## Challenge: disemvowel
- my solution: using `str.replaceAll()` replace vowels with empty string.
  - `str.replaceAll()`: "returns" a new string.
- CSX solution: using `for` loop and checking every letter.
  - when define the if statement, you can use `Object` with square bracket or `Array` with `includes()`.

&nbsp;  

# Callbacks & Higher-order Functions
## Challenge: forEach
```js
function forEach(arr, callback){
  // iterate arr and invoke callback
  for(let el of arr){
    callback(el);
  }
  // only return undefine
}

function map(arr, callback){
  // since map will return an arr, declare first
  const result = [];
  // because my forEach() only return undefine, we need to declare a new function to get what we want
  // and save it in local memory
  forEach(arr, (arg)=>{
    result.push(callback(arg))
  })
  return result;
}

console.log(typeof forEach); // should log: 'function'
forEach(['a','b','c'], i => console.log(i)); // should log: 'a', 'b', 'c'
console.log(typeof map); // should log: 'function'
console.log(map([3,4,5], n => n - 2)); // should log: [1, 2, 3]
```

## Challenge: reduce
- `typeof` syntax: `typeof(expression)` or `typeof value`
- terms: "initial"

## Challenge: union
- remember `push()` returns "the new length".

## Challenge: countBy
Conditional (ternary) operator
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator