
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

## 41)What is the use of preventDefault method?
- The preventDefault() method cancels the event if it is cancelable, meaning that the default action or behaviour that belongs to the event will not occur. For example, prevent form submission when clicking on submit button and prevent opening the page URL when clicking on hyperlink are some common use cases.
```bash
document.getElementById("link").addEventListener("click", function(event){
event.preventDefault();
});
  
```
## 42) What is the use of stopPropagation method?
- The stopPropagation method is used to stop the event from bubbling up the event chain. For example, the below nested divs with stopPropagation method prevents default event propagation when clicking on nested div(Div1)

```bash
<p>Click DIV1 Element</p>
<div onclick="secondFunc()">DIV 2
<div onclick="firstFunc(event)">DIV 1</div>
</div>
<script>
function firstFunc(event) {
alert("DIV 1");
event.stopPropagation();
}
function secondFunc() {
alert("DIV 2");
}
</script>
```

## 43What is BOM?
- The Browser Object Model (BOM) allows JavaScript to "talk to" the browser. It consists of the objects navigator, history, screen, location and document which are children of the window. The Browser Object Model is not standardized and can change based on different browsers.
## 44) What is the use of setTimeout?

- The setTimeout() method is used to call a function or evaluate an expression after a specified number of milliseconds. For example, let's log a message after 2 seconds using setTimeout method,

```bash
setTimeout(function(){ console.log("Good morning"); }, 2000); 
```


## 45)What is the use of setInterval?
- The setInterval() method is used to call a function or evaluate an expression at specified intervals (in milliseconds). For example, let's log a message after 2 seconds using setInterval method,

```bash
setInterval(function(){ console.log("Good morning"); }, 2000);
```

## 46)Why is JavaScript treated as Single threaded?
- JavaScript is a single-threaded language. Because the language specification does not allow the programmer to write code so that the interpreter can run parts of it in parallel in multiple threads or processes. Whereas languages like java, go, C++ can make multi-threaded and multi-process programs.

## 47) What is an event delegation?
- Event delegation is a technique for listening to events where you delegate a parent element as the listener for all of the events that happen inside it. For example, if you wanted to detect field changes in inside a specific form, you can use event delegation technique,
```bash
var form = document.querySelector('#registration-form');
// Listen for changes to fields inside the form
form.addEventListener('input', function (event) {
// Log the field that was changed
console.log(event.target);
}, false);
```
## 48)What is JSON?
- JSON (JavaScript Object Notation) is a lightweight format that is used for data interchanging. It is based on a subset of JavaScript language in the way objects are built in JavaScript.


## 49)What is the purpose JSON stringify?
- When sending data to a web server, the data has to be in a string format. You can achieve this by converting JSON object into a string using stringify() method.

```bash
var userJSON = {'name': 'John', age: 31}
var userString = JSON.stringify(user);
console.log(userString); //"{"name":"John","age":31}"
```
## 50)How do you parse JSON string?
- When receiving the data from a web server, the data is always in a string format. But you can convert this string value to a javascript object using parse() method.

```bash
var userString = '{"name":"John","age":31}';
var userJSON = JSON.parse(userString);
console.log(userJSON);// {name: "John", age: 31}
```

## 51)Why do you need JSON?
- When exchanging data between a browser and a server, the data can only be text. Since JSON is text only, it can easily be sent to and from a server, and used as a data format by any programming language.
## 52)  What is the purpose of clearInterval method?
- The clearInterval() function is used in javascript to clear the interval which has been set by setInterval() function. i.e, The return value returned by setInterval() function is stored in a variable and it’s passed into the clearInterval() function to clear the interval. For example, the below setInterval method is used to display the message for every 3 seconds. This interval can be cleared by the clearInterval() method.


```bash
<script>
var msg;
function greeting() {
alert('Good morning');
}
function start() {
msg = setInterval(greeting, 3000);
}
function stop() {
clearInterval(msg);
}
</script>

```

## 53) What are the various url properties of location object?
- The below Location object properties can be used to access URL components of the page,
-  href - The entire URL
- protocol - The protocol of the URL
- host - The hostname and port of the URL
- hostname - The hostname of the URL
- port - The port number in the URL
- pathname - The path name of the URL
- search - The query portion of the URL
- hash - The anchor portion of the URL
## 54) What is a polyfill?

- A polyfill is a piece of JS code used to provide modern functionality on older browsers that do not natively support it. For example, Silverlight plugin polyfill can be used to mimic the functionality of an HTML Canvas element on Microsoft Internet Explorer 7


## 55) What is tree shaking?
- Tree shaking is a form of dead code elimination. It means that unused modules will not be included in the bundle during the build process and for that it relies on the static structure of ES2015 module syntax,( i.e. import and export). Initially this has been popularized by the ES2015 module bundler rollup .

## 56)What is the need of tree shaking?
- Tree Shaking can significantly reduce the code size in any application. i.e, The less code we send over the wire the more performant the application will be. For example, if we just want to create a “Hello World” Application using SPA frameworks then it will take around a few MBs, but by tree shaking it can bring down the size to just a few hundred KBs. Tree shaking is implemented in Rollup and Webpack bundlers.

## 57) What is a Regular Expression?
- A regular expression is a sequence of characters that forms a search pattern. You can use this search pattern for searching data in a text. These can be used to perform all types of text search and text replace operations. Let's see the syntax format now,
```bash
/pattern/modifiers;
```
- For example, the regular expression or search pattern with case-insensitive username would be,
```bash
/John/i
```
## 58)How do you make synchronous HTTP request?
- Browsers provide an XMLHttpRequest object which can be used to make synchronous HTTP requests from JavaScript
```bash
function httpGet(theUrl)
{
var xmlHttpReq = new XMLHttpRequest();
xmlHttpReq.open( "GET", theUrl, false ); // false for synchronous request
xmlHttpReq.send( null );
return xmlHttpReq.responseText;
}
```

## 59) How do you make asynchronous HTTP request?
- Browsers provide an XMLHttpRequest object which can be used to make asynchronous HTTP requests from JavaScript by passing the 3rd parameter as true.


```bash
function httpGetAsync(theUrl, callback)
{
var xmlHttpReq = new XMLHttpRequest();
xmlHttpReq.onreadystatechange = function() {
if (xmlHttpReq.readyState == 4 && xmlHttpReq.status == 200)
callback(xmlHttpReq.responseText);
}
xmlHttp.open("GET", theUrl, true); // true for asynchronous
xmlHttp.send(null);
}
```
## 60)What is a conditional operator in javascript?
- The conditional (ternary) operator is the only JavaScript operator that takes three operands which acts as a shortcut for if statements.
```bash
var isAuthenticated = false;
console.log(isAuthenticated ? 'Hello, welcome' : 'Sorry, you are not authenticated'); 
```


## 61) Can you apply chaining on conditional operator?
- Yes, you can apply chaining on conditional operators similar to if … else if … else if … else chain.The syntax is going to be as below,
```bash
function traceValue(someParam) {
return condition1 ? value1
: condition2 ? value2
: condition3 ? value3
: value4;
}
// The above conditional operator is equivalent to:
function traceValue(someParam) {
if (condition1) { return value1; }
else if (condition2) { return value2; }
else if (condition3) { return value3; }
else { return value4; }
}
```


## 62) What are the ways to execute javascript after page load?
- You can execute javascript after page load in many different ways,
### i. window.onload:
```bash
window.onload = function ...
```

### ii. document.onload:
```bash
document.onload = function ...
```

### iii. body onload:
```bash
<body onload="script();">
```

## 63) What is a freeze method?
- The freeze() method is used to freeze an object. Freezing an object does not allow adding new properties to an object,prevents from removing and prevents changing the enumerability, configurability, or writability of existing properties. i.e, It returns the passed object and does not create a frozen copy.
```bash
const obj = {
prop: 100
};
Object.freeze(obj);
obj.prop = 200; // Throws an error in strict mode
console.log(obj.prop); //100
```
## 64) How do you detect a browser language preference?
- You can use navigator object to detect a browser language preference as below
```bash
var language = navigator.languages && navigator.languages[0] || // Chrome / Firefox
navigator.language || // All browsers
navigator.userLanguage; // IE <= 10
console.log(language);
```


## 65)  How do you detect javascript disabled in the page?
- You can use the <noscript> tag to detect javascript disabled or not. The code block inside <noscript> gets executed when JavaScript is disabled, and is typically used to display alternative content when the page generated in JavaScript.
```bash
<script type="javascript">
// JS related code goes here
</script>
<noscript>
<a href="next_page.html?noJS=true">JavaScript is disabled in the page. Please click Ne
</noscript>
```

## 66)What is a rest parameter?
- Rest parameter is an improved way to handle function parameters which allows us to represent an indefinite number of arguments as an array. The syntax would be as below,
```bash
function f(a, b, ...theArgs) {
// ...
}
```
- For example, let's take a sum example to calculate on dynamic number of parameters,
```bash
function total(…args){
let sum = 0;
for(let i of args){
sum+=i;
}
return sum;
}
console.log(fun(1,2)); //3
console.log(fun(1,2,3)); //6
console.log(fun(1,2,3,4)); //13
console.log(fun(1,2,3,4,5)); //15
```


## 67) What is a spread operator?
- Spread operator allows iterables( arrays / objects / strings ) to be expanded into single arguments/elements. Let's take an example to see this behavior,
```bash
function calculateSum(x, y, z) {
return x + y + z;
}
const numbers = [1, 2, 3];
console.log(calculateSum(...numbers)); // 6

```
## 68)What is the purpose of using object is method?
### Some of the applications of Object's is method are follows,
- i. It is used for comparison of two strings.
- ii. It is used for comparison of two numbers.
- iii. It is used for comparing the polarity of two numbers.
- iv. It is used for comparison of two objects.


## 69) How do you copy properties from one object to other?
- You can use the Object.assign() method which is used to copy the values and properties from one or more source objects to a target object. It returns the target object which has properties and values copied from the target object. The syntax would be as below
```bash
Object.assign(target, ...sources)

```
- Let's take example with one source and one target object,

```bash
const target = { a: 1, b: 2 };
const source = { b: 3, c: 4 };
const returnedTarget = Object.assign(target, source);
console.log(target); // { a: 1, b: 3, c: 4 }
console.log(returnedTarget); // { a: 1, b: 3, c: 4 }
```
## 70)What is a proxy object?
- The Proxy object is used to define custom behavior for fundamental operations such as property lookup, assignment, enumeration, function invocation, etc. The syntax would be as follows,
```bash
 var p = new Proxy(target, handler);
 ```
 - Let's take an example of proxy object,

```bash
var handler = {
get: function(obj, prop) {
return prop in obj ?
obj[prop] :
100;
}
};
var p = new Proxy({}, handler);
p.a = 10;
p.b = null;
console.log(p.a, p.b); // 10, null
console.log('c' in p, p.c); // false, 100

```

## 71) How can you get the list of keys of any object?
- You can use the Object.keys() method which is used to return an array of a given object's own property names, in the same order as we get with a normal loop. For example, you can get the keys of a user object,

```bash
const user = {
name: 'John',
gender: 'male',
age: 40
};
console.log(Object.keys(user)); //['name', 'gender', 'age']

```


## 72) How do you create an object with prototype?
- The Object.create() method is used to create a new object with the specified prototype object and properties. i.e, It uses an existing object as the prototype of the newly created object. It returns a new object with the specified prototype object and properties.
```bash
const user = {
name: 'John',
printInfo: function () {
console.log(`My name is ${this.name}.`);
}
};
const admin = Object.create(user);
admin.name = "Nick"; // Remember that "name" is a property set on "admin" but not on "use
admin.printInfo(); // My name is Nick

```

## 73) What are the differences between WeakMap and Map?
- The main difference is that references to key objects in Map are strong while references to key objects in WeakMap are weak. i.e, A key object in WeakMap can be garbage collected if there is no other reference to it. Other differences are,
- i. Maps can store any key type Whereas WeakMaps can store only collections of key objects
- ii. WeakMap does not have size property unlike Map
- iii. WeakMap does not have methods such as clear, keys, values, entries, forEach.
- iv. WeakMap is not iterable.
## 74) How do you encode an URL?
- The encodeURI() function is used to encode complete URI which has special characters except (, / ? : @ & = + $ #) characters.

```bash
var uri = 'https://mozilla.org/?x=шеллы';
var encoded = encodeURI(uri);
console.log(encoded); // https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B
```


## 75)  How do you decode an URL?
- The decodeURI() function is used to decode a Uniform Resource Identifier (URI) previously created by encodeURI().

```bash
var uri = 'https://mozilla.org/?x=шеллы';
var encoded = encodeURI(uri);
console.log(encoded); // https://mozilla.org/?x=%D1%88%D0%B5%D0%BB%D0%BB%D1%8B
try {
console.log(decodeURI(encoded)); // "https://mozilla.org/?x=шеллы"
} catch(e) { // catches a malformed URI
console.error(e);
}

```

## 76)What is an anonymous function?
- An anonymous function is a function without a name! Anonymous functions are commonly assigned to a variable name or used as a callback function. The syntax would be as below,
```bash
function (optionalParameters) {
//do something
}
const myFunction = function(){ //Anonymous function assigned to a variable
//do something
};
[1, 2, 3].map(function(element){ //Anonymous function used as a callback function
//do something
});
```
- Let's see the above anonymous function in an example,
```bash
var x = function (a, b) {return a * b};
var z = x(5, 10);
console.log(z); // 50
```


## 77) What is a spread operator?
- Spread operator allows iterables( arrays / objects / strings ) to be expanded into single arguments/elements. Let's take an example to see this behavior,
```bash
function calculateSum(x, y, z) {
return x + y + z;
}
const numbers = [1, 2, 3];
console.log(calculateSum(...numbers)); // 6

```
## 78)How do you define property on Object constructor?
- The Object.defineProperty() static method is used to define a new property directly on an object,or modify an existing property on an object, and returns the object. Let's see an example to know how to define property,
```bash
const newObject = {};
Object.defineProperty(newObject, 'newProperty', {
value: 100,
writable: false
});
console.log(newObject.newProperty); // 100
newObject.newProperty = 200; // It throws an error in strict mode due to writable setting

```
## 79) What are the advantages of Getters and Setters?
- Below are the list of benefits of Getters and Setters,
- i. They provide simpler syntax
- ii. They are used for defining computed properties, or accessors in JS.
- iii. Useful to provide equivalence relation between properties and methods
- iv. They can provide better data quality
- v. Useful for doing things behind the scenes with the encapsulated logic.

## 80)What is the purpose of switch-case?
- The switch case statement in JavaScript is used for decision making purposes. In a few cases, using the switch case statement is going to be more convenient than if-else statements. The syntax would be as below
```bash
 switch (expression)
{
case value1:
statement1;
break;
case value2:
statement2;
break;
.
.
case valueN:
statementN;
break;
default:
statementDefault;
}

 ```
- The above multi-way branch statement provides an easy way to dispatch execution to different parts of code based on the value of the expression.


## 81) What are primitive data types?
- A primitive data type is data that has a primitive value (which has no properties or methods).
- There are 7 types of primitive data types.
- i. string
- ii. number
- iii. boolean
- iv. null
- v. undefined
- vi. bigint
- vii. symbol

## 82) What are the different ways to access object properties?
#### There are 3 possible ways for accessing the property of an object.
- i. Dot notation: It uses dot for accessing the properties
```bash
objectName.property
```
- ii. Square brackets notation: It uses square brackets for property access
```bash
objectName["property"]
```
- iii. Expression notation: It uses expression in the square brackets
```bash
objectName[expression]
```


## 83)What are the different error names from error object?
- There are 6 different types of error names returned from error object,
|  Error Name  | Description| |      
|----------|----------|-
|  EvalError   | An error has occurred in the eval() function  | 
| RangeError  |  An error has occurred with a number "out of range"   | 
|ReferenceError |An error due to an illegal reference
|
|SyntaxError |An error due to a syntax error
|
|TypeError |An error due to a type error
|
|URIError|An error due to encodeURI()|

## 84)What are the various statements in error handling?
### Below are the list of statements used in an error handling,
- i. try: This statement is used to test a block of code for errors
- ii. catch: This statement is used to handle the error
- iii. throw: This statement is used to create custom errors.
- iv. finally: This statement is used to execute code after try and catch regardless of the result.

## 85) What is an event loop?
- The Event Loop is a queue of callback functions. When an async function executes, the callback function is pushed into the queue. The JavaScript engine doesn't start processing the event loop until the async function has finished executing the code. Note: It allows Node.js to perform nonblocking I/O operations even though JavaScript is single-threaded.


## 86)What is call stack?
- Call Stack is a data structure for javascript interpreters to keep track of function calls in the program. It has two major actions,
- i. Whenever you call a function for its execution, you are pushing it to the stack.
- ii. Whenever the execution is completed, the function is popped out of the stack.
#### Let's take an example and it's state representation in a diagram format
```bash
function hungry() {
eatFruits();
}
function eatFruits() {
return "I'm eating fruits";
}
// Invoke the `hungry` function
hungry();
```
#### The above code processed in a call stack as below,
- i. Add the hungry() function to the call stack list and execute the code.
- ii. Add the eatFruits() function to the call stack list and execute the code.
- iii. Delete the eatFruits() function from our call stack list.
- iv. Delete the hungry() function from the call stack list since there are no items anymore.

## 87)  How do you reversing an array?
- You can use the reverse() method to reverse the elements in an array. This method is useful to sort an array in descending order. Let's see the usage of reverse() method in an example,

```bash
let numbers = [1, 2, 5, 3, 4];
numbers.sort((a, b) => b - a);
numbers.reverse();
console.log(numbers); // [1, 2, 3, 4 ,5]
```
## 88)How do you find min and max value in an array?
- You can use Math.min and Math.max methods on array variables to find the minimum and maximum elements within an array. Let's create two functions to find the min and max value with in an array,
```bash
var marks = [50, 20, 70, 60, 45, 30];
function findMin(arr) {
return Math.min.apply(null, arr);
}
function findMax(arr) {
return Math.max.apply(null, arr);
}
console.log(findMin(marks));
console.log(findMax(marks));
```
## 89)What are the advantages of typescript over javascript?
####  Below are some of the advantages of typescript over javascript,
- i. TypeScript is able to find compile time errors at the development time only and it makes sure less runtime errors. Whereas javascript is an interpreted language.
- ii. TypeScript is strongly-typed or supports static typing which allows for checking type correctness at compile time. This is not available in javascript.
- iii. TypeScript compiler can compile the .ts files into ES3,ES4 and ES5 unlike ES6 features of javascript which may not be supported in some browsers.
## 90)What is a constructor method?
- The constructor method is a special method for creating and initializing an object created within a class. If you do not specify a constructor method, a default constructor is used. The example usage of constructor would be as below.
```bash
class Employee {
constructor() {
this.name = "John";
}
}
var employeeObject = new Employee();
console.log(employeeObject.name); // John
```

## 91)What happens if you write constructor more than once in a class?
- The "constructor" in a class is a special method and it should be defined only once in a class. i.e,
- If you write a constructor method more than once in a class it will throw a SyntaxError error.

```bash
class Employee {
constructor() {
this.name = "John";
}
constructor() { // Uncaught SyntaxError: A class may only have one constructor
this.age = 30;
}
}
var employeeObject = new Employee();
console.log(employeeObject.name);
```
## 92)How do you call the constructor of a parent class?

- You can use the super keyword to call the constructor of a parent class. Remember that
- super() must be called before using 'this' reference. Otherwise it will cause a reference error.
- Let's the usage of it,
```bash
class Square extends Rectangle {
constructor(length) {
super(length, length);
this.name = 'Square';
}
get area() {
return this.width * this.height;
}
set area(value) {
this.area = value;
}
}
```
## 93)What Is Obfuscation in javascript?
- Obfuscation is the deliberate act of creating obfuscated javascript code(i.e, source or machine code) that is difficult for humans to understand. It is something similar to encryption, but a machine can understand the code and execute it. Let's see the below function before Obfuscation,
```bash
function greeting() {
console.log('Hello, welcome to JS world');
}
```
- And after the code Obfuscation, it would be appeared as below,
```bash
eval(function(p,a,c,k,e,d){e=function(c){return c};if(!''.replace(/^/,String)){while(c--){
```
## 94)Why do you need Obfuscation?
- Below are the few reasons for Obfuscation,
- i. The Code size will be reduced. So data transfers between server and client will be fast.
- ii. It hides the business logic from outside world and protects the code from others
- iii. Reverse engineering is highly difficult
- iv. The download time will be reduced
## 95)How do you perform form validation using javascript?
- JavaScript can be used to perform HTML form validation. For example, if the form field is empty, the function needs to notify, and return false, to prevent the form being submitted. Lets' perform user login in an html form,
```bash
<form name="myForm" onsubmit="return validateForm()" method="post">
User name: <input type="text" name="uname">
<input type="submit" value="Submit">
</form>
And the validation on user login is below,
function validateForm() {
var x = document.forms["myForm"]["uname"].value;
if (x == "") {
alert("The username shouldn't be empty");
return false;
}
}
```
## 96) Is enums feature available in javascript?
- No, javascript does not natively support enums. But there are different kinds of solutions to simulate them even though they may not provide exact equivalents. For example, you can use freeze or seal on object,
```bash
var DaysEnum = Object.freeze({"monday":1, "tuesday":2, "wednesday":3, ...})
```
## 97)What is an enum ?
- An enum is a type restricting variables to one value from a predefined set of constants.
- JavaScript has no enums but typescript provides built-in enum support.
```bash
enum Color {
RED, GREEN, BLUE
}
```
## 98) How do you extend classes?
- The extends keyword is used in class declarations/expressions to create a class which is a child of another class. It can be used to subclass custom classes as well as built-in objects. The syntax would be as below,
```bash
class ChildClass extends ParentClass { ... }
```
- Let's take an example of Square subclass from Polygon parent class,
```bash
class Square extends Rectangle {
constructor(length) {
super(length, length);
this.name = 'Square';
}
get area() {
return this.width * this.height;
}
set area(value) {
this.area = value;
}
}
```
## 99)How to get the value from get parameters?
- The new URL() object accepts the url string and searchParams property of this object can be used to access the get parameters. Remember that you may need to use polyfill orwindow.location to access the URL in older browsers(including IE).
```bash
let urlString = "http://www.some-domain.com/about.html?x=1&y=2&z=3"; //window.location.hre
let url = new URL(urlString);
let parameterZ = url.searchParams.get("z");
console.log(parameterZ); // 3
```
## 100)What is jQuery?
- jQuery is a popular cross-browser JavaScript library that provides Document Object Model(DOM) traversal, event handling, animations and AJAX interactions by minimizing the discrepancies across browsers. It is widely famous with its philosophy of “Write less, do more”.
- For example, you can display welcome message on the page load using jQuery as below,
```bash
$(document).ready(function(){ // It selects the document and apply the function on page lo
alert('Welcome to jQuery world');
});
```
- Note: You can download it from jquery's official site or install it from CDNs, like google
