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