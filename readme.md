# Day-2 Interview Questions

## What is execution context
In JavaScript, an execution context can be defined as the environment in which a piece of code is executed. It contains information about the currently executing code, such as variable values, function calls, and the scope chain.

When JavaScript code is executed, a new execution context is created. This context is responsible for managing the execution of the code within its scope, and it is destroyed once the code execution is completed.

Here's a simple example :

function myFunction() {

  var a = 10;

  console.log(a);

}


myFunction();
<hr>

## What is an event loop and call stack
The call stack is a data structure that keeps track of the function calls in a program. Whenever a function is called, it is added to the top of the call stack, and when the function completes, it is removed from the top of the stack. This allows JavaScript to keep track of where it is in a program's execution and which function to return to after the current one finishes.

Here's an example of a call stack:

function greet(name) {

  console.log("Hello, " + name + "!");

}


function sayHello() {

  const name = "Ajay";

  greet(name);

}

sayHello(); // "Hello, Ajay!"


The event loop is a mechanism that allows JavaScript to handle asynchronous code, such as waiting for user input or network requests. The event loop constantly checks for any events that need to be processed, and when it finds one, it adds it to a queue.

Here's an example of the event loop:

console.log("Start");

setTimeout(function() {

  console.log("First timeout");

}, 1000);


setTimeout(function() {

  console.log("Second timeout");

}, 500);


console.log("End");
<hr>

## What is creation phase and execution phase?
1. Creation Phase:
The creation phase involves the creation of the variable and function declarations, which are then stored in memory. During this phase, JavaScript also sets up the scope chain and the "this" keyword.

Here's an example of variable and function declarations during the creation phase:

function myFunction() {

  var myVariable = 1;

  console.log(myVariable);

}


During the creation phase, the function and variable declarations are stored in memory. The variable "myVariable" is assigned a value of 1.

2. Execution Phase:
The execution phase refers to the moment when the code is actually executed, line by line. During this phase, JavaScript reads and executes each line of code in sequence, using the information stored in memory during the creation phase.

Here's an example of code execution during the execution phase:

myFunction(); // Outputs: 1

function myFunction() {

  var myVariable = 1;

  console.log(myVariable);

}


In this example, the function "myFunction" is called, which triggers the execution phase. During this phase, JavaScript reads and executes the function code, which outputs the value of "myVariable" to the console.

In summary, the creation phase and execution phase in JavaScript refer to the moment when the variable and function declarations are created and stored in memory, and the moment when the code is actually executed, line by line.
<hr>

## What is the spread operator?
The spread operator is a feature in JavaScript that allows an iterable (such as an array or a string) to be expanded into individual elements. The spread operator is denoted by three dots (...) and can be used in several ways in JavaScript.

Here's an example of using the spread operator to concatenate two arrays:

const array1 = [1, 2, 3];

const array2 = [4, 5, 6];

const combinedArray = [...array1, ...array2];

console.log(combinedArray); // [1, 2, 3, 4, 5, 6]
<hr>

## What is the use of setTimeout
setTimeout() is a JavaScript function that allows you to schedule a function to be executed after a certain amount of time has passed. The function takes two parameters: the first is the function you want to execute, and the second is the time delay in milliseconds.

Here's an example code that uses setTimeout():
console.log("Before setTimeout");


setTimeout(function() {

  console.log("Hello, world!");

}, 1000);


console.log("After setTimeout");
<hr>

## What are callbacks?
a callback is a function that is passed as an argument to another function and is executed after some event or task is completed.

function getUserData(userId, callback) {


  const userData = { name: "Ajay", age: 30, email: "Ajay@example.com" };

  callback(userData);

}

// Define a callback function to process the user data

function processUserData(userData) {

  console.log("Name:", userData.name);

  console.log("Age:", userData.age);

  console.log("Email:", userData.email);

}


// Call the getUserData function with the user ID and the callback function

getUserData(123, processUserData);
<hr>

## What is callback hell
Callback hell is a common issue in JavaScript that arises when dealing with multiple asynchronous operations that depend on each other. It occurs when the code becomes nested within multiple callback functions, making it difficult to read and debug.

Here's an example of callback hell:

function getData(callback) {

  setTimeout(function() {

    callback('Data received!');

  }, 2000);

}

function processData(callback) {

  setTimeout(function() {

    callback('Data processed!');

  }, 2000);

}

function saveData(callback) {

  setTimeout(function() {

    callback('Data saved!');

  }, 2000);

}

getData(function(data) {

  console.log(data);

  processData(function(data) {

    console.log(data);

    saveData(function(data) {

      console.log(data);

    });

  });

});
<hr>

## Difference between undefined vs not defined vs NaN
Undefined:
Undefined is a primitive value in JavaScript that is automatically assigned to a variable that has been declared but not initialized. It indicates the absence of a value.

Example:

let x;

console.log(x); // Output: undefined


Not Defined:
A variable that has not been declared or initialized in a program is said to be not defined. Attempting to access such a variable will result in a ReferenceError.

Example:

console.log(y); // Output: ReferenceError: y is not defined


NaN:
NaN stands for "Not a Number". It is a special value in JavaScript that is returned when a mathematical operation fails to produce a meaningful result.

Example:

let x = "Hello";

let y = parseInt(x);

console.log(y); // Output: NaN
<hr>


