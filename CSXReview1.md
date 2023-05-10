# Functions and Execution Context
- string dose have property `length `.
- `arr.push()`: adds to the "end" and returns "the new length".
- `arr.pop()`: removes the "last" and returns "that element".
- `arr.unshift()`: adds to the "beginning" and returns "the new length".
- `arr.shift()`: removes the "first" and returns "that element".
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
- Conditional (ternary) operator  
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator


# Closure
## Challenge: once
- using `...args` as parameter when buile the constructer you not sure what callback is invoke.

## Challenge: hobbyTracker
- using `arr.reduce()` to convert array to object.

## Challenge: dateStamp
- `date.toDateString()`: returns the date portion of a Date object.
- watch out where to initial the variable.


&nbsp;  

# Recursion
- tail recursion  
  https://dev.to/hi_iam_chris/recursion-and-tail-recursion-with-javascript-2fdg
## Challenge: getLength
- an empty array is `true`.
- try using `array.slice(1)`.
## Challenge: cascade
- my solution without string manipulation:  
```js
function cascade(number, digit=1, goDown=true) {
	// Your code here!
  if(!number) return;
  // console.log("digit", digit);
  if(number/digit < 1){
    goDown=false;
    digit /= 100;
  }
  if(goDown){
    console.log(Math.floor(number/digit));
    return cascade (number, digit*10, goDown)
  }
  if(digit < 1) return;
  console.log(Math.floor(number/digit));
  return cascade (number, digit/10, goDown)
}
```


&nbsp;  

# OOP
## Challenge: DeveloperClass
- my solution with Class inheritance (using extends, super()):  
```js
class PersonClass {
	constructor(name) {
    this.name = name;
	}

	greet() {
    console.log('hello');
  }
}

// add code here
class PersonClass extends PersonClass {
  constructor(name, age) {
    super(name);
    this.age = age;
  }

  introduce() {
  	console.log(`Hello World, my name is ${this.name}`)
	}
}
```

## Challenge: Chain Stores
- my solution (using arr.findIndex(), arr.splice()):
```js
class Chain {
	// add code here
  constructor(name){
    this.name = name;
    this.totalStores = 0;
    this.locations = [];
  }
  
  openStore(owner, city) {
    const newStore = new Franchise(owner, city);
    this.locations.push(newStore);
    this.totalStores++;
  }
  
  closeStore(city) {
    const cityIndex = this.locations.findIndex((el)=>{
      return el.city === city;
    })
    if(cityIndex !== -1) {
      console.log(`${this.name} closed the store in ${this.locations[cityIndex].city}!`)
      this.locations.splice(cityIndex, 1);
      this.totalStores--;
    }else {
      console.log(`${this.name} doesn't have a store in ${city}.`)
    }
  }
}

class Franchise {
  //add code here
  constructor(owner, city){
    this.owner = owner;
    this.city = city;
  }
}

const buenoBell = new Chain('Bueno Bell');

// Uncomment these lines to check your work!
buenoBell.openStore('Will', 'Phoenix');
buenoBell.openStore('Kyle', 'Austin');
buenoBell.openStore('Allison', 'Wichita');

console.log(buenoBell.totalStores); //should log 3
console.log(buenoBell.locations[0].owner) //should log 'Will'

buenoBell.closeStore('Austin'); // Should log 'Bueno Bell closed the store in Austin.'
buenoBell.closeStore('Maui'); // Should log 'Bueno Bell doesn't have a store in Maui.'
```