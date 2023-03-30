# Introduction to Callbacks and Higher Order Functions video
generalized function: add parameter
```js
// 1. global() pushed in callstack and creat a global execution context
// 2. declare the function copyArrayAndManipulatesave in global memory
// 7. call copyArrayAndManipulate() pushed in callstack and creat a local execution context
// 8. assign parameter value with myArray and multiplyBy2 in local memory
function copyArrayAndManipulate(array, instructions){
  // 9. declare the variable output and value [] in local memory
  let outpot = [];
  // 10. declare the variable i = 0 in local memory
  // 11. check if i < array.length
  for (let i = 0; i < array.length; i++){
    // 12. invoke method .push and function instructions(as same as multiplyBy2()) with argument array[i]
    // ( what .push method do refer to Additional resources below )
    // ( step13 is under step3 )
    output.push(instructions(array[i]));
    // 16. i = i + 1
    // 17. loop the loop( step11 to step16 ) until i is not less then array.length
  }
  // 18. return value to result( step6 ) and pop out copyArrayAndManipulate()
  return output
}
// 3. declare the function multiplyBy2 save in global memory
// 13. call instructions() pushed in callstack and creat another local execution context in last local
// ( instructions() is as same as multiplyBy2() so i put the step here, but it is actually calling instructions() )
// 14. assign parameter value with array in local...local memory
function multiplyBy2(input){
  // 15. return value to .push and pop out instructions()
  return input * 2;
}
// 4. declare the constant myArray and value [1, 2, 3] in global memory
const myArray = [1, 2, 3];
// 5. declare the constant myArray and value undefined in global memory
// 6. invoke function copyArrayAndManipulate with arguments myArray and multiplyBy2 ( step7 is under step2 )
let result = copyArrayAndManipulate( myArray, multiplyBy2);
// 19. end the global execution context
```
- Note:  
These step just general thoughts about how these code run.  
I might miss some ideas(like pointer?) since I don't have CS degree  
  
- Additional resources:  
Array.prototype.push and specifications  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push  
https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.push  

&nbsp;  

# JavaScript The Hard Parts: Callbacks and Higher Order Functions workshop video
I deleted the old note since it is similar to last video

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