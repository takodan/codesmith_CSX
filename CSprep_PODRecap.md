I only note portion of code, so they have lots of error.
# Day 1 - Reverse String
```js
// convert string to array, reverse it, then covert it back
const reverseString= (str) => str.split("").reverse().join("");
```


# Day 1 - Draw Stairs
```js
function drawStairs(n) {
    // argument check
    if(n <= 1) throw new Error("Error message")
    // repeat()
    let resultStr = str.repeat("repeatTimes")
}
```


# Day 2 - Adding To X
```js
function addingToX(num){
    // argument check
    if(typeof num != "number") throw new TypeError("Error message")
}
```


# Day 2 - Mode and Mean
```js
function grtMode(array){
    // create cache to count times element occur in the array
}
```
- Additional resources:  
Question Mark (?) Operator  
https://www.freecodecamp.org/news/how-the-question-mark-works-in-javascript/  


# Day 3 - Largest And Smallest
```js
// when finding max or min, using Infinity to initialize the variable
let min = Infinity // max possible number
let max = -Infinity // min possible number
```


# Day 3 - Reverse Number
```js
// num => string => array.reverse() => string => num
let numToString = String(num)
let reversedString = numToString.split("").reverse().join("");
let reversedNum =  Number(reversedString)
```


# Day 5 - Reverse Number with out converting the number to a string
```js
// using Remainder (%), Division (/), and Multiplication (*)
```


# Day 5 - Common Elements
```js 
// using arr.filter(callbackFn)
// using new Set() when result have duplicate element
```
- Additional resources:  
Array.prototype.sort()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set


# Day 6 - Single Number
```js
function singleNumber(arr) {
    // create cache to count times element occur in the array
}
```


# Day 6 - Merge Sorted Arrays
```js
function mergeSortedArrays(array1, array2){
  return array1.concat(array2).sort((a, b) => a - b);
}
// or you can interate arrays
```

- Additional resources:  
Array.prototype.sort()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort  


# Day 7 - Check if Sorted
```js 
// solution 1: checking the array is ascending or decending, then iterate the array
// solution 2: iterate the array checking it is ascending or not, then checking it is decending or not
```