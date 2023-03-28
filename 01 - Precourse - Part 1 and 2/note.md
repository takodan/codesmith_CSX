# Javascript: What is it?
Modern web architecture is comprised of three key ingredients: HTML, CSS, and JavaScript.  
1. HTML: webpage structure.
2. CSS: webpage looks.
3. JavaScript: interact with HTML and CSS.  

&nbsp;  

# Intro to JS Pt. 1  workshop video
Intro to JavaScript: Variables, Control Flow, and Looping

## Variables
1. variables: store and reference data.
2. control flow: run code base on conditions.
3. looping: repeat code base on conditions. 

```js
// declaring variable , assign value
// keyword->"var", lable->"num", assign->"=", data->"3"
var num= 3;
// shouldn't use var anymore
let name= "csx";
// const cannot be reassigned
// object->"{}"curly brackets, array->"[]"square brackets
const storeOfInfo= {
    // elements->"New York City""Los Angeles"
    home: ["New York City", "Los Angeles"],
};
```
- Additional resources:  
Differences between var, let, and const:  
https://www.freecodecamp.org/news/differences-between-var-let-const-javascript/

goble exectution context include
 - thread of execution(TOE): run code  
 - goble memory: save data  

&nbsp;  

## Control Flow
```js
const myGrade = 42;
if(myGrade <= 70){
    console.log(myGrade + " is failing.");
} else if(myGrade < 80){
    console.log(myGrade + " is passing.");
} else{
    console.log(myGrade + " is excellent.");
}

if(myGrade === 42){
    console.log(Answer to the Ultimate Question);
}
// myGrade is constant so cannot be re-assign
```

## Looping
avoid nesting loop if possible, because of time complex
```js
const myNums = [1, 2, 6 ];
for(let i = 0; i < myNums.length; i++){
    const num1 = myNums[i];
    for (let j = 0; j < myNums.length; j++){
        const num2 = myNums[j];
        console.log("Sum: ", num1 , num2 , num1+num2);
        if ( num1 + num2 === 7){
            console.log("Lucky Seven!");
        }
    }
}
```

- Additional resources: 
Big O notation  
https://www.freecodecamp.org/news/big-o-notation-why-it-matters-and-why-it-doesnt-1674cfa8a23c/  

&nbsp;  

# Variables & Constants reading

## Rules for Naming:
1. camelCased variable names
2. variable names cannot contain symbols
3. variable names cannot begin with a number  

&nbsp;  

# Data Types reading

## Primitive Data Types
1. String
2. Number
3. Boolean
4. Null
5. Undefined
6. Symbol

## Composite Data Types
1. Object
2. Array
- Additional resources:  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures  

&nbsp;  

# Challenge: Strings - Escape Sequences
common escape sequences:  
1. \\ => backslash
2. \n => newline
3. \r => carriage return
4. \t => tab
5. \b => backspace  

&nbsp;  

# Challenge: Template Literal
template literal:  
```js
// use `` and ${}
let x = 3;
let y = 9;
const solution = `The sum of ${x} and ${y} is ${x + y}`;
console.log(solution); // => "The sum of 2 and 5 is 7"
```

&nbsp;  

# Challenge: String Properties & Methods
properties(no parentheses) and methods(with parentheses)
```js
str = "wAAAAAh"
let count = str.length; // => 7
let upper = str.toUpperCase(); // => "WAAAAAH"
let lower = str.toLowerCase(); // => "waaaaah"
```
# Challenge: Bracket Notation for Strings
strings are immutable  

&nbsp;  

# Challenge: Numbers - Multiplication/Division
Floating-point:  
https://en.wikipedia.org/wiki/Floating-point_arithmetic#Accuracy_problems  

&nbsp;  


# Challenge: Numbers - Exponents & Remainders
exponentiation operator (**)
modulus (remainder) operator (%)  

&nbsp;  

# Challenge: Booleans: Comparison Operators
1. ==: is loosely equal to
2. ===: is strictly equal to (must have the same data type)  

&nbsp;  

# Challenge: Type Coercion
```js
console.log(10 + 5); // => 15
console.log("10" + 5); // => 105
```

&nbsp;  

# Challenge: Arrays - Examining Elements
```js
let numbers = [1, 2, 3, 4];

numbers.pop();
console.log(numbers); // => [1, 2, 3]
```
- Additional resources:  
JavaScript Array Methods and Properties  
https://www.w3schools.com/jsref/jsref_obj_array.asp   

&nbsp;  

# Challenge: Objects - Examining Properties
```js
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};
// "a" "b" "c" are keys,'somestring' 42 false are associated values
// Keys are also referred to as properties

console.log(Object.keys(object1));
// Expected output: Array ["a", "b", "c"]

for (const property in object1) {
  console.log(`${property}: ${object1[property]}`);
}
// Expected output:
// "a: 1"
// "b: 2"
// "c: 3"
```
- Additional resources:  
Object.keys()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys  
for...in  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in  
for...of  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of  