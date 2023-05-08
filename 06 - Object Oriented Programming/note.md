# JSHP: OOP Pt. 1
programming paradigm
## Functional programming
using pure function
pure function:
1. Same inputs always return same outputs
2. No side-effects
- Additional resources:  
https://www.freecodecamp.org/news/what-is-a-pure-function-in-javascript-acb887375dfe/  

&nbsp;  

## Object oriented programming
functionality is next to data
1. easy to add features
2. efficient in terms of memory
3. a clear structure

&nbsp;  

## create Object
1. declare an object with properties in it
2. declare an emptry object and add properties with dot notation
3. using brackets notation
4. using method Object.create

&nbsp;  

## some solution to generate Objects
1. using function to generate objects
2. using Object.create
3. `new` keyword
4. `class` keyword with `new` keyword

&nbsp;  

## the Prototype chain 
`__proto__` : dunder proto
`[[Prototype]]`: an internal property labeld Prototype

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain

&nbsp;  

## soluation 1: using function to generate objects
this soliation will create too many same function in different object
```js
function userCreator(name,score){
    const newUser = {};
    newUser.name = name;
    newUser.score = score;
    newUser.increment = function(){
        newUser.score++;
    }
    return newUser;
}

// declare "user1" with return object, include "increment" function inside
const user1 = userCreator("Will", 3);
// declare "user2" with return object, include another same "increment" function inside
const user2 = userCreator("Tim", 5);
user1.increment();
```

&nbsp;  

## Inheritance
- Additional resources:  
Inheritance and the prototype chain
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain


&nbsp;  

## soluation 2: using Object.create()
using Object.create() with a argument object create a new object will make new object have a bond with the  argument object ( lead DUNDER proto point to argument object ).
```js
function userCreator (name, score) {
    const newUser = Object.create(userFunctionStore);
    newUser.name = name;
    newUser.score = score;
    return newUser;
};
const userFunctionStore = {
    increment: function(){this.score++}
}

// these objects don't have "increment" function, they have dunder proto point to userFunctionStore instead
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);

// "this" in function "increment" will point to the object who invoke it which is "user1"
user1.increment();
```

&nbsp;  

# JSHP: OOP Pt. 2
## "new" keyword (soluation 3)
```js
// 1. declare a function in global memory
// this function "OBJECT" also have a object PROPERTIES call "prototype"
function UserCreator(name, score){
    // 5. after invoke
    // declare "name" and "score" in local memory
    // declare "this" object in local memory
    // this object have a __proto__ ( DUNDER proto )  point to "UserCreator.prototype"
    // 6. declare "this.name" and "this.score" with "name" and "score" value
    this.name = name;
    this.score = score;
    // 7. return "this" to "user1" ( step8 is under step4 )
}

// 2. declare a function in global memory
// add "increment" METHOD to "prototype" PROPERTIES
UserCreator.prototype.increment = function(){
    this.score++;
}
// 3. add another METHOD to "prototype" PROPERTIES
UserCreator.prototype.loging = function(){
    console.log("loging")
}

// 4. invoke "UserCreator()" with "new" keyword ( step5 is under step1 )
const user1 = new UserCreator("Eva", 9);
// 8. "user1" value is a object and have a "DUNDER" proto point to "UserCreator.prototype", so "user1" can asscss METHOD in "UserCreator.prototype" 
// 9. invoke "increment()"
// "this" in the function is equal to the obj who invoke the function, which is "user1"
// user1.score++;
user1.increment();
```

## "class" keyword (soluation 4)
same as creating a function and use "new" keyword, just different syntax.
```js
classUserCreator {
    // variables
    constructor (name, score){
        this.name = name;
        this.score = score
    }
    // methods
    increment (){
        this.score++;
    }
    login (){
        console.log("login");
    }
}

const user1 = new UserCreator("Eva", 9);

user1.increment();
```

- Additional resources:  
new operator  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new  

# Challenge: DeveloperClass
- Additional resources:  
JavaScript Class Inheritance  
https://www.w3schools.com/js/js_class_inheritance.asp  
super()  
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super  

&nbsp;  

# Additional Learning Resources
MDN: Object-oriented JavaScript for beginners  
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Classes_in_JavaScript  
freeCodeCamp: Object Oriented Programming in JavaScript  
https://www.freecodecamp.org/news/how-javascript-implements-oop/  
Eloquent Javascript: The Secret Life of Objects  
https://eloquentjavascript.net/06_object.html  