
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


## 21)What is a Cookie?
-   A cookie is a piece of data that is stored on your computer to be accessed by your browser.Cookies are saved as key/value pairs. For example, you can create a cookie named username as below,
```bash
 document.cookie = "username=John";  
```
## 22) Why do you need a Cookie?
-  Cookies are used to remember information about the user profile(such as username). It basically involves two steps,
- i. When a user visits a web page, the user profile can be stored in a cookie.
-  ii. Next time the user visits the page, the cookie remembers the user profile.
## 23)How do you delete a cookie?
-  You can delete a cookie by setting the expiry date as a passed date. You don't need to specify a cookie value in this case. For example, you can delete a username cookie in the current page as below.
```bash
 document.cookie = "username=; expires=Fri, 07 Jun 2019 00:00:00 UTC; path=/;";
 ```
 - Note: You should define the cookie path option to ensure that you delete the right cookie. Some browsers doesn't allow to delete a cookie unless you specify a path parameter.

## 24)What are the differences between cookie, local storage and session storage?
|  Feature   | Cookie |  Local storage|    Session storage   |
|----------|----------|----|---
|   Accessed on client or server side    |  Both server-side & client side  | client-side only | client-side only |
|   Lifetime    |  As configured using Expires option  | until deleted|  until tab is closed |
|  SSL support   | Supported |  Not supported | Not supported |
|   Maximum data size    |  4KB | 5MB | 5MB |


## 25)How do you access web storage?
-   The Window object implements the WindowLocalStorage and WindowSessionStorage objects which has localStorage (window.localStorage) and sessionStorage (window.sessionStorage) properties respectively. These properties create an instance of the Storage object, through which data items can be set, retrieved and removed for a specific domain and storage type (session or local). For example, you can read and write on local storage objects as below
```bash
localStorage.setItem('logo', document.getElementById('logo').value); 
localStorage.getItem('logo'); 
```


## 26)Why do you need web storage?
-  Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance. Also, the information is never transferred to the server. Hence this is a more recommended approach than Cookies.
## 27) What is a promise?
- A promise is an object that may produce a single value some time in the future with either a resolved value or a reason that it’s not resolved(for example, network error). It will be in one of the 3 possible states: fulfilled, rejected, or pending.

- The syntax of Promise creation looks like below,
```bash
const promise = new Promise(function(resolve, reject) { 
// promise description 
}) 
```
-  The usage of a promise would be as below,
```bash
const promise = new Promise(resolve => { 
setTimeout(() => { 
resolve("I'm a Promise!"); 
}, 5000); 
}, reject => { 
}); 
promise.then(value => console.log(value));
```


## 28) Why do you need a promise?
-  Promises are used to handle asynchronous operations. They provide an alternative approach for callbacks by reducing the callback hell and writing the cleaner code.
## 29)What is a callback function?
- A callback function is a function passed into another function as an argument. This function is invoked inside the outer function to complete an action. Let's take a simple example of how to use callback function:
```bash
function callbackFunction(name) { 
console.log('Hello ' + name); 
} 
function outerFunction(callback) { 
let name = prompt('Please enter your name.'); 
callback(name); 
} 
outerFunction(callbackFunction); 
```
## 30)Why do we need callbacks?
- The callbacks are needed because javascript is an event driven language. That means instead of waiting for a response javascript will keep executing while listening for other events. Let's take an example with the first function invoking an API call(simulated by setTimeout) and the next function which logs the message.

```bash
function firstFunction(){ 
  // Simulate a code delay 
  setTimeout( function(){ 
    console.log('First function called'); 
  }, 1000 ); 
} 
function secondFunction(){ 
  console.log('Second function called'); 
} 
firstFunction(); 
secondFunction(); 
Output 
// Second function called 
// First function called 
```
- As observed from the output, javascript didn't wait for the response of the first function and the remaining code block got executed. So callbacks are used in a way to make sure that certain code doesn’t execute until the other code finishes execution.



## 31)What is a callback hell?
- Callback Hell is an anti-pattern with multiple nested callbacks which makes code hard to read and debug when dealing with asynchronous logic. The callback hell looks like below,
```bash
async1(function(){ 
    async2(function(){ 
        async3(function(){ 
            async4(function(){ 
                .... 
            }); 
        }); 
    }); 
}); ;  
```
## 32) What are server-sent events?
- Server-sent events (SSE) is a server push technology enabling a browser to receive automatic updates from a server via HTTP connection without resorting to polling. These are a one way  communications channel - events flow from server to client only. This has been used in Facebook/Twitter updates, stock price updates, news feeds etc.

## 33)What is callback in callback?
-   You can nest one callback inside in another callback to execute the actions sequentially one by one. This is known as callbacks in callbacks.
```bash
loadScript('/script1.js', function(script) { 
   console.log('first script is loaded'); 
  loadScript('/script2.js', function(script) { 
    console.log('second script is loaded'); 
    loadScript('/script3.js', function(script) { 
        console.log('third script is loaded'); 
      // after all scripts are loaded 
    }); 
  }) 
});
 ```
 

## 34) What is promise chaining?

- The process of executing a sequence of asynchronous tasks one after another using promises is known as Promise chaining. Let's take an example of promise chaining for calculating the final result,
```bash
new Promise(function(resolve, reject) { 
  setTimeout(() => resolve(1), 1000); 
}).then(function(result) { 
  console.log(result); // 1 
  return result * 2; 
}).then(function(result) { 
  console.log(result); // 2 
  return result * 3; 
}).then(function(result) { 
  console.log(result); // 6 
  return result * 4; 
}); 
```


## 35)Why do you need strict mode?
-   Strict mode is useful to write "secure" JavaScript by notifying "bad syntax" into real errors. For example, it eliminates accidentally creating a global variable by throwing an error and also throws an error for assignment to a non-writable property, a getter-only property, a non-existing property, a non-existing variable, or a non-existing object


## 36) How do you declare strict mode?
-  The strict mode is declared by adding "use strict"; to the beginning of a script or a function. If declared at the beginning of a script, it has global scope.
```bash
 "use strict"; 
x = 3.14; // This will cause an error because x is not declared 
and if you declare inside a function, it has local scope
 x = 3.14;       
myFunction(); 
// This will not cause an error. 
function myFunction() { 
"use strict"; 
y = 3.14;   // This will cause an error 
} 
```
## 37) What is the difference between window and document?
|  Window   | Document | |      
|----------|----------|-
|  It is the root level element in any web page    | It is the direct child of the window object. This is also known as Document Object Model(DOM) | 
|By default window object is available implicitly in the page | You can access it via window.document or document.
   | 
|It has methods like alert(), confirm() and properties like document, location|It provides methods like getElementById,getElementByTagName, createElement etc|

## 38) What are the differences between undeclared and undefined variables?
|  undeclared   | undefined | |      
|----------|----------|-
|These variables do not exist in a program and are not declared   |These variables declared in the program but have not assigned any value
| 
|If you try to read the value of an undeclared variable, then a runtime error is encountered | If you try to read the value of an undefined variable, an undefined value is returned
   | 


## 39)What is event bubbling?
- Event bubbling is a type of event propagation where the event first triggers on the innermost target element, and then successively triggers on the ancestors (parents) of the target element in the same nesting hierarchy till it reaches the outermost DOM element.
## 40)What is same-origin policy?
- The same-origin policy is a policy that prevents JavaScript from making requests across domain boundaries. An origin is defined as a combination of URI scheme, hostname, and port number. If you enable this policy then it prevents a malicious script on one page from obtaining access to sensitive data on another web page using Document Object Model(DOM).
