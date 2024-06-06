
# 🔥Crack Javascript Interview (Best Explanation)
## 1) What is the purpose of the array slice method?
-  The slice() method returns the selected elements in an array as a new array object. It selects the elements starting at the given start argument, and ends at the given optional end argument without including the last element. If you omit the second argument then it selects till the end.
###  Some of the examples of this method are:

 ```bash
 let arrayIntegers = [1, 2, 3, 4, 5]; 
let arrayIntegers1 = arrayIntegers.slice(0,2); // returns [1,2]
 let arrayIntegers2 = arrayIntegers.slice(2,3); // returns [3] 
let arrayIntegers3 = arrayIntegers.slice(4); //returns [5] 
```
### Note: Slice method won't mutate the original array but it returns the subset as a new array
## 2) What is the purpose of the array splice method?
-  The splice() method is used either adds/removes items to/from an array, and then returns the removed item. The first argument specifies the array position for insertion or deletion whereas the option second argument indicates the number of elements to be deleted. Each additional argument is added to the array.
###  Some of the examples of this method are:

 ```bash
 let arrayIntegersOriginal1 = [1, 2, 3, 4, 5]; 
let arrayIntegersOriginal2 = [1, 2, 3, 4, 5]; 
let arrayIntegersOriginal3 = [1, 2, 3, 4, 5]; 
let arrayIntegers1 = arrayIntegersOriginal1.splice(0,2); // returns [1, 2]; original array becomes [ 3, 4, 5 ];
 let arrayIntegers2 = arrayIntegersOriginal2.splice(3); // returns [4, 5]; original array becomes [ 1, 2, 3 ] 
let arrayIntegers3 = arrayIntegersOriginal3.splice(3, 1, "a", "b", "c"); //returns [4]; original array becomes[1,2,3,'a','b','c',5]
```
### Note: Splice method modifies the original array and returns the deleted array.

## 3) What is the difference between slice and splice?
###  Some of the major difference in a tabular form:

|  Slice   | Splice | |      
|----------|----------|-
|  Doesn't modify the original array(immutable)    |  Modifies the original array(mutable)  | 
|Returns the subset of original array  | Returns the deleted elements as array   | 
|Used to pick the elements from array|Used to insert or delete elements to/fromarray|

## 4)What is Hoisting?
-  Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. Remember that JavaScript only hoists declarations, not initialisation.
###  Let's take a simple example of variable hoisting:

```bash
console.log(message); //output : undefined 
var message = 'The variable Has been hoisted';
```
### The above code looks like as below to the interpreter,
```bash
var message; 
console.log(message);
message = 'The variable Has been hoisted'; 
```
## 5)  What is memoization?
-   Memoization is a programming technique which attempts to increase a function’s performance by caching its previously computed results. Each time a memoized function is called, its parameters are used to index the cache. If the data is present, then it can be returned, without executing the entire function. Otherwise the function is executed and then the result is added to the cache. 
###  Let's take an example of adding function with memoization:

```bash
const memoizAddition = () => { 
let cache = {}; 
return (value) => { 
if (value in cache) { 
console.log('Fetching from cache'); 
return cache[value]; 
 } 
else { 
console.log('Calculating result'); 
let result = value + 20; 
cache[value] = result; 
return result; 
} 
} 
} 
// returned function from memoizAddition 
const addition = memoizAddition(); 
console.log(addition(20)); //output: 40 calculated 
console.log(addition(20)); //output: 40 cached 
```

## 6)What is scope in javascript?
-  Scope is the accessibility of variables, functions, and objects in some particular part of your code during runtime. In other words, scope determines the visibility of variables and other resources in areas of your code.
## 7)What is a prototype chain?
-  Prototype chaining is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.The prototype on object instance is available through Object.getPrototypeOf(object) or proto property whereas prototype on constructors function is available through Object.prototype.
## 8)What is the difference between Call, Apply and Bind?
-  Call: The call() method invokes a function with a given this value and arguments provided one by one.
```bash
var employee1 = {firstName: 'John', lastName: 'Rodson'}; 
var employee2 = {firstName: 'Jimmy', lastName: 'Baily'}; 
function invite(greeting1, greeting2) { 
console.log(greeting1 + ' ' + this.firstName + ' ' + this.lastName+ ', '+ greeting2); 
} 
invite.call(employee1, 'Hello', 'How are you?'); // Hello John Rodson, How are you? 
invite.call(employee2, 'Hello', 'How are you?'); // Hello Jimmy Baily, How are you? 
```
- Apply: Invokes the function with a given this value and allows you to pass in arguments as an array.
```bash
 var employee1 = {firstName: 'John', lastName: 'Rodson'}; 
var employee2 = {firstName: 'Jimmy', lastName: 'Baily'}; 
function invite(greeting1, greeting2) { 
console.log(greeting1 + ' ' + this.firstName + ' ' + this.lastName+ ', '+ greeting2); 
}
 invite.apply(employee1, ['Hello', 'How are you?']); // Hello John Rodson, How are you?
 invite.apply(employee2, ['Hello', 'How are you?']); // Hello Jimmy Baily, How are you?
```
- Bind: returns a new function, allowing you to pass any number of arguments

``` bash
var employee1 = {firstName: 'John', lastName: 'Rodson'}; 
var employee2 = {firstName: 'Jimmy', lastName: 'Baily'}; 
function invite(greeting1, greeting2) { 
console.log(greeting1 + ' ' + this.firstName + ' ' + this.lastName+ ', '+ greeting2); 
} 
var inviteEmployee1 = invite.bind(employee1); 
var inviteEmployee2 = invite.bind(employee2); 
inviteEmployee1('Hello', 'How are you?'); // Hello John Rodson, How are you? 
inviteEmployee2('Hello', 'How are you?'); // Hello Jimmy Baily, How are you? 
```
- Call and apply are pretty interchangeable. Both execute the current function immediately. You need to decide whether it’s easier to send in an array or a comma separated list of arguments.You can remember by treating Call is for comma (separated list)and Apply is for Array.
- Whereas Bind creates a new function that will have this set to the first parameter passed to bind().

## 9) What is JSON and its common operations?
- JSON is a text-based data format following JavaScript object syntax, which was popularized by Douglas Crockford . It is useful when you want to transmit data across a network and it is basically just a text file with an extension of .json, and a MIME type of application/json.
#### Parsing: Converting a string to a native object
``` bash
 JSON.parse(text)
 ```
#### Stringification: Converting a native object to a string so it can be transmitted across the network
```bash
JSON.stringify(object)
```
## 10)What is the difference between let and var?
|  var  | let | |      
|----------|----------|-
|  It is been available from the beginning of JavaScript    |  Introduced as part of ES6  | 
| It has function scope |  It has block scope   | 
|Variables will be hoisted |Hoisted but not initialized|

- Let's take an example to see the difference,
```bash
 function userDetails(username) { 
if(username) { 
Hoisted but not initialized
 console.log(salary); // undefined due to hoisting 
console.log(age); // ReferenceError: Cannot access 'age' before initialization 
let age = 30; 
var salary = 10000; 
} 
 console.log(salary); //10000 (accessible to due function scope) 
   console.log(age); //error: age is not defined(due to block scope) 
} 
userDetails('John');
```

## 11)How do you redeclare variables in switch block without an error?
-  If you try to redeclare variables in a switch block then it will cause errors because there is only one block. For example, the below code block throws a syntax error as below,
```bash
let counter = 1; 
switch(x) { 
  case 0: 
    let name; 
    break; 
  case 1: 
    let name; // SyntaxError for redeclaration. 
    break; 
} 
```
- To avoid this error, you can create a nested block inside a case clause and create a new block scoped lexical environment.
```bash
let counter = 1; 
    switch(x) { 
      case 0: { 
        let name; 
        break; 
      } 
      case 1: { 
        let name; // No SyntaxError for redeclaration. 
        break; 
      } 
    } 
```

## 12) What is the Temporal Dead Zone?
-  The Temporal Dead Zone is a behavior in JavaScript that occurs when declaring a variable with the let and const keywords, but not with var. In ECMAScript 6, accessing a let or const variable before its declaration (within its scope) causes a ReferenceError. The time span when  that happens, between the creation of a variable’s binding and its declaration, is called the temporal dead zone.
-  Let's see this behavior with an example,
```bash
function somemethod() { 
  console.log(counter1); // undefined 
  console.log(counter2); // ReferenceError 
  var counter1 = 1; 
  let counter2 = 2; 
}
```
## 13)What is the benefit of using modules?
-  There are a lot of benefits to using modules in favour of a sprawling. Some of the benefits are,
 i. Maintainability
 ii. Reusability
 iii. Namespacing
## 14)What are classes in ES6?
- In ES6, Javascript classes are primarily syntactic sugar over JavaScript’s existing prototype-based inheritance. For example, the prototype based inheritance written in function expression as below,
```bash
function Bike(model,color) { 
this.model = model; 
this.color = color; 
} 
Bike.prototype.getDetails = function() { 
return this.model + ' bike has' + this.color + ' color'; 
}; 
```
- Whereas ES6 classes can be defined as an alternative
```bash
class Bike{ 
constructor(color, model) { 
this.color= color; 
this.model= model; 
} 
getDetails() { 
return this.model + ' bike has' + this.color + ' color'; 
} 
}
```
## 15)What are closures?
-  A closure is the combination of a function and the lexical environment within which that function was declared. i.e, It is an inner function that has access to the outer or enclosing function’s variables. The closure has three scope chains:
-  i. Own scope where variables defined between its curly brackets ii. Outer function’s variables iii. Global variables
-  Let's take an example of closure concept,
```bash
function Welcome(name){ 
var greetingInfo = function(message){ 
console.log(message+' '+name); 
} 
return greetingInfo; 
} 
var myFunction = Welcome('John'); 
myFunction('Welcome '); //Output: Welcome John 
myFunction('Hello Mr.'); //output: Hello Mr.John 
```
- As per the above code, the inner function(i.e, greetingInfo) has access to the variables in the outer function scope(i.e, Welcome) even after the outer function has returned.

## 16)What are modules?
-  Modules refer to small units of independent, reusable code and also act as the foundation of many JavaScript design patterns. Most of the JavaScript modules export an object literal, a function, or a constructor
## 17) Why do you need modules?
- Below are the list of benefits using modules in javascript ecosystem

-  i. Maintainability  ii. Reusability iii. Namespacing
## 18)What is scope in javascript?
-  Scope is the accessibility of variables, functions, and objects in some particular part of your code during runtime. In other words, scope determines the visibility of variables and other resources in areas of your code.
## 19)What is web storage?
-  Web storage is an API that provides a mechanism by which browsers can store key/value pairs locally within the user's browser, in a much more intuitive fashion than using cookies. The web storage provides two mechanisms for storing data on the client
-  i. Local storage: It stores data for current origin with no expiration date.
- ii. Session storage: It stores data for one session and the data is lost when the browser tab is closed.
## 20)What is a post message?
-  Post message is a method that enables cross-origin communication between Window objects.(i.e, between a page and a pop-up that it spawned, or between a page and an iframe embedded within it). Generally, scripts on different pages are allowed to access each other if and only if the pages follow same-origin policy(i.e, pages share the same protocol, port number, and host).
```




