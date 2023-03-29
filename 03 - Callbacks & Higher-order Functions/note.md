# JavaScript The Hard Parts: Callbacks and Higher Order Functions workshop video
functional progtamming
pure functions
same input same output
```js
function tenSquare(){
    return 10 * 10
}

function numSquare(num){
    return num*num
}
```

parameters
argument

gogobal memory
functionName = func defition
myArray = [1, 2, 3]
result = invoke func > callstack

callstack // first in last out
cAAMB2(myArray) // finished local, go to global
global()

local execution
cAAMB2(myArray)
i = 0 , 0 < 3 // array.length
output.push(2) // array[0]*2
i++
i = 1 , 1 < 3
output.push(4) // array[1]*2 , put in to local memory
i++
i = 2 , 2 < 3
output.push(6) // array[2]*2 , put in to local memory
i++


local memory
array = [1, 2, 3] // myArray
output = [2, 4, 6 ]

&nbsp;  

# Challenge: map
```js
const array1 = [1, 4, 9, 16];

// Pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// Expected output: Array [2, 8, 18, 32]
```

- Additional resources:  
Array.prototype.map()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map  

&nbsp;  

# Challenge: forEach
```js
function forEach(arr, callback){
    // iterate thought arr and invoke callback function
    for( let i in arr){
        callback(arr[i]);
    }
    return;
}

function map(arr, callback){
    const result = [];
    // call forEach with anonymous function that push callback function return into result
    // forEach will iterate thought every element in arr
    // element in arr will become argument pass to anonymous function
    forEach(arr, ele => result.push(callback(ele)));
    return result;
}
```

&nbsp;  

# Challenge: reduce
- Additional resources: 
Array.prototype.reduce()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce   
Array.prototype.shift()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift  
Array.prototype.slice()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice  

&nbsp;  

# Challenge: intersection
iterate though array with while approach
```js
let array = [1, 2, 3];
while(array.length){
    const current = array.pop(); // from the last element, use shift() from the first element
    console.log(current);
}
```
if use reduce from previous Challenge  
```js
function reduce(arr, callback, acc){
  for(let i in arr){
    acc = callback( acc, arr[i]);
  }
  return acc
}
function compare(target, item){
  if( target === item){
    return "found";
  }
  return target;
}

function intersection(arrays){
  const firstArr = arrays.shift()
  const result = [];
  console.log(firstArr)
  for ( let el of firstArr){
    // console.log(el);
    let found;
    for ( let array of arrays ){
      found = reduce( array, compare, el);
      // if not found in one of any array break this loop, found stay as el, iterate next el
      if(found !==  "found"){
        break;
      }
      // console.log(found, el);
    }
    // if found in all arrays, found will remain found
    // console.log(found, el);
    if (found === "found"){
      result.push(el);
    }
  }
  return result;
}
// check your work!
const arr1 = [5, 10, 15, 20];
const arr2 = [15, 88, 1, 5, 7];
const arr3 = [1, 10, 15, 5, 20];
console.log(intersection([arr1, arr2, arr3])); // should log: [5, 15]
```
- Additional resources:  
Array.prototype.includes()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes  

&nbsp;  

# Challenge: union
if use built-in Array.prototype.reduce()
```js
function union(arrays){
  let result = arrays.shift();
  for (let array of arrays){
    array.reduce(
      (function(accumulator, currentValue){
        console.log(accumulator, currentValue);
        if(!result.includes(currentValue)){
          result.push(currentValue)
          return result;
        }
      }), result);
  }
  return result;
}

// check your work!
const arr1 = [5, 10, 15];
const arr2 = [15, 88, 1, 5, 7];
const arr3 = [100, 15, 10, 1, 5];
console.log(union([arr1, arr2, arr3])); // should log: [5, 10, 15, 88, 1, 7, 100]
```

&nbsp;  

# Challenge: prioritize
- Additional resources:  
Array.prototype.concat()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat  

&nbsp;  

# Additional Learning Resources
MDN: Callback Function  
https://developer.mozilla.org/en-US/docs/Glossary/Callback_function  
Eloquent Javascript: Higher-Order Functions  
https://eloquentjavascript.net/05_higher_order.html  
Traversy Media: JavaScript Higher Order Functions & Arrays  
https://www.youtube.com/watch?v=rRgD1yVwIvE  