---
{"dg-publish":true,"permalink":"/JavaScript/","tags":["coding"]}
---


---
# JavaScript
> JavaScript is a Coding Language capable of [[Object Oriented Programming\|Object Oriented Programming]], which is used in [[Full-Stack Development\|Full-Stack Development]] of Websites, Apps or other projects.

This note is for indexing all my JavaScript Coding Knowledge. 
For Interview Preparation, check: [[JavaScript Interview Questions\|JavaScript Interview Questions]]

### Variables & Operators
there are three ways to declare variables in JS
```JavaScript
let a; // limited scope (can only be altered by parent function)
var b; // global scope (can be altered by any function)
const c; // cannot be altered once set.

a++; // increment operator
b--; // decrement operator
c+=; // step-increment operator i.e, c = c + 1
a-=; // step-decrement operator i.e., a = a - 1
```

### Data Types
JavaScript has the `String`, `Number`, `Boolean` and `Object` Data Types.
```JavaScript
// change the comment and types change from number to string

let a = 23; // converting to boolean will give true if a>1
let b;

// a = "Name"; // converted to number gives NaN

// a = false; // converted to number will give 0
// a = true; // converted to number will give 1

// a = String(a); // sets the value of a to string type.

console.log("the value of a is: ", a)
console.log("the type of a is: ", typeof(a))
console.log("b is: ", b) // b is undefined

// if more than 1 lines remain uncommented, 
// then the following value of a will override the previous one
```

### Conditional Statements & Ternary Operators
If-Else Statements and Switch Case Statements which use conditions before switching.

Example for switch case:
```JavaScript
const age = 12; 
// constant variables cannot be changed by other functions or methods.

switch (true) {
	case age>18:
		console.log("you may vote");
		break;
	case age<18:
		console.log("you may not vote");
		break;
	default:
		console.log("invalid age");
		break;
}
```

Example for if-else + switch case:
```JavaScript
var subject_marks = 82 // var has global scope
let subject_grade;

if (subject_marks>=95){
	subject_grade = "A+";
	console.log("Great Job! You got: ", subject_grade);
}
else if (subject_marks>=90){
	subject_grade = "A"
	console.log("Great Job!");
}
else if (subject_marks>=85){
	subject_grade = "B+"
	console.log("Just a bit more & you will get A");
}
else if (subject_marks>=80){
	subject_grade = "B"
	console.log("Just a bit more & you will get A");
}
else if (subject_marks>=75){
	subject_grade = "C+"
	console.log("Just a bit more & you will get A");
}
else if (subject_marks>=70){
	subject_grade = "C"
	console.log("Just a bit more & you will get A");
}
else if (subject_marks>=60){
	subject_grade = "C-"
	console.log("Just a bit more & you will get A");
}
else if (subject_marks>=50){
	subject_grade = "D"
	console.log("Just a bit more & you will get A")
	if (30<subject_marks<40){
		console.log("Narrowly missed failing by <10 marks")
	}
}
else if (subject_marks<30){
	subject_grade = "F"
	console.log("Sorry but you have failed");
}

const subject_result = subject_marks >=30 ? "PASSED" : "FAILED";
```

### Loop Statements
There are three kinds of Loops in JavaScript:
For Loop, While Loop & Do-While Loop  

Example for For Loop:
```JavaScript
for(let index = 0; index < 5; index++){
	console.log("You are in the loop");
}
```

If the loop has more than one condition, it is separated by semi-colons.

Example for While Loop:
```JavaScript
let index = 0;

while(index<5){
	console.log("You are in the loop");
	index += 1;
}
```

We are going to skip `for in` and `for each` loops among other similar lesser known variants. 

```JavaScript
let index = 0;

do{
	console.log("You are in the loop");
	index += 1;
} while(index < 5)

// This runs the loop's iteration once before checking the "while" condition.
```

### Break & Continue
`break` & `continue` are two statements used quite a bit in JS.
The difference among them is that `break` stops the parent function on fulfilling the `if` condition whereas `continue` skips to end of the function or loop iteration.

`break` and `continue` are both not allowed outside `if-else`, loops or `switch`.

### Functions (Methods)
Functions are defined by using the term `function` in front of the JS program.
```JS
function whatever(){
	console.log("function")
}
```

Example with sum of 2 numbers:
```JS
function sumOf(a,b){
	const sum = a + b; // variable a and b are defined only in here.
	console.log("result is: ", sum)
}

const a = 12;
const b = 4;
sumOf(a,b); //calls the function
```

Variables can store a Function inside it:
```JS
const square = function (a){ //function in disguise
	return a * a;
};

// another variation: "const square = (num) => num*num;"

console.log(square(4)); // puts the value 4 through the const square
```

Functions can be nested as long as `return` statement is taken care of:
```JS
function addSquares(a, b) {
	const sa = square(a);
	const sb = square(b);
	
	function square(num) {
		return num * num;
	}
	
	return sa + sb;
}

console.log(addSquares(3, 4));
```

### Asynchronous Function
Functions that do not impede on other function's execution.
These functions can execute parallely while other functions are executing, given that the other functions are also asynchronous.

Example of an Asynchronous function is using the `setTimeout` function.
Example of `setTimeout`:
```JS
// executes a block of code over a given portion of time 
// asynchronously.

setTimeout(function() {
	//whatever
}, 3000)

// here 3000 is the number of miliseconds by which to delay the 
// function.
```

### Callback Functions
```JS
function greet(name, callback){
	console.log("Hello! " + name);
	callback();
}

function callMe() {
	console.log("I am callback function")
}

greet("Peter", callMe);
```


> [!warning] WARNING: Beware of the "Callback Hell"
> Callback Hell is a situation where the programmers are using set timeout inside a function and calling for something but the use one or more than one return statements inside.
>
> One must avoid using return statements since they make the program exit the function i.e., they do not wait for the timeout to finish and return "undefined" before the timeout executes. Hence, giving an unexpected result.

### Arrays
Arrays are created by either creating filled Arrays or Array Literals.
```JavaScript
const words = ["Apple", "Banana", "Cherry"];

// You can add strings, objects, numbers and even FUNCTIONS in the same array!
const whatever = ["apple", "samsung", 12, {name: "Anuj"}, function hello(){console.log("hello array!")}];

console.log(words[4]); //prints the (n)th element of given array.
```

A better way to add a function to an array is:
```JavaScript
function hello() {
	console.log("Hello");
}

const arr = ["apple", 'kela', 'cheeku', hello()];
```

if we wish to find a specific element use the following line
```JS
console.log(arr.includes(8)) 
// will check if 8 exists in array arr.
```

Specific array functions can be used in the following way:
```JS
const arr = [12, 7, 8, 3, 0, 47]
// use the syntax of arrayName.functionName()

arr.sort() //sorts the array
arr.pop() // pops the last element from the end.
arr.push() // pushes a new element in at the end.
arr.shift // removes the first element of the array.
arr.unshift // adds an element at the start of the array.
```

```JS
const a = [4, 1, 6, -2, -5, 3, 2, -8, 6, 7];

a.forEach((num, ) => {
	console.log("array num", num);
});
// forEach iterates on each element of an area to perform the same 
// operation repeatedly. It is a pre-programmed variation of for loop.
```

### Higher Order Functions - Maps & Filters
The `filter()` method returns a new array witha all elements that pass the test defined by the given function without changing the original array or executing a callback for each of its elements.
```JS
// Basic Structure
let newArray = oldArray.filter((currentValue, index, array) {
	// Returns element to newArray.
});
```

 Essentially it is used to filter out elements from an array.
```JS
let students = [
	{ id: "001", name: "Anish", sports: "Cricket"},
	{ id: "002", name: "Sarthak", sports: "Football"},
	{ id: "003", name: "Rahul", sports: "Cricket"},
	{ id: "004", name: "Soham", sports: "Football"}
]

students.filter((curValue, index, array) => {

});

const newArray = students.filter((curValue) => {
	if (curValue.id % 2 == 0) return true;
	else return false;
});

console.log("New Array here....");
console.log(newArray);

// this method is simpler and better than using a for loop to iteratively edit the array with each increment.
```

the `map()` method creates a new array with the results of calling a function for every new element without changing the original array or executing a callback for each of its elements.

```JS
// Basic Structure
let newArray = oldArray.map((currentValue, index, array){
	// Returns element to new Array.
});
```

Example:
```JS
let students = [
	{ id: "001", name: "Anish", sports: "Cricket"},
	{ id: "002", name: "Sarthak", sports: "Football"},
	{ id: "003", name: "Rahul", sports: "Cricket"},
	{ id: "004", name: "Soham", sports: "Football"}
]

const names = students
	.filter(curValue.sports === "Cricket") //filters by sport
	.map((curValue, index, array) => {
	return curValue.name; // prints names according to filter
});

const div = document.getElementById("container")

div.innerHTML = '<ul>$(names.join(""))</ul>';
```

It is necessary to use a `return` statement else compiler thinks that nothing to return & it won't return anything.

### Import & Export Files in JS
How to use the code of one module in another using export and import?
Here we use the example/analogy of importing a function from `utility.js` to `script.js`.

```JS
// utility.js
export function multiply(a,b,c) {
	return a*b*c
}

//script.js
import {multiply} from './utility' //the string is the path
// the path to be provided must be relative to script.js
```

To rename the function in the receiving file, use:
```JS 
// utility.js
export function multiply(a,b,c) {
	return a*b*c
}

//script.js
import {multiply as mul} from './utility'
// now the  function can only be used by the name "mul".
```

If there are too many functions in a given piece of code, it is not fair to expect the coder to add `export` as a prefix to all of them, intead use the following at the end of the page:
```JS
export {
	multiply as mul,
	addition as add,
	subtraction
	// list any other here similarly
}
```

To import all functions from a file, use:
```JS
import * as utility from './utility'
```

similarly you can use variables from other files:
```JS
// utility.js
export const Student_Count = 23;

//script.js
console.log(utility.Student_Count);
```

### Error Handling
Errors can interrupt the program and skip all the important error-free tasks coded right under the error to the very end.

We use a try-catch block to catch any errors that may have arisen. 
It avoids the entire program from being interrupted. 
```JS
// Basic Try-Catch Block
try {
	// body of try
	// contains line with potential error
}
catch (error) {
	// body of catch
	// contains how to handle the error
}
```

If there is an intentional throw of the error that needs to be taken care of. Maybe there are some features that you shouldn't be able to access without premium so we use the block:
```JS 
try{
	const res = prompt('Are you a robot?');
	if (res == 'Y') {
		throw new Error ('Robot Found!')
	}
}
catch (error) {
	// contains how to handle the error
	console.log(error.name, error.message);
}
finally {
	// executes regardless of error being caught.
}
```

### Personal Project Idea
> [!tip] Project Idea: Student Management System
> Management System for managing students, their personal information like name, class, batch, year etc and then using the above block of code to manage subejcts, subject marks etc.
>  
> JavaScript can be used for Frontend ([[ReactJS\|ReactJS]]), Backend ([[NodeJS\|NodeJS]], [[ExpressJS\|ExpressJS]]) and Database Handling ([[MongoDB\|MongoDB]]). 

> [!tip] Contribute to Habitica
> Contribute to Habitica in Code via GitHub.
> Ask and Fork Habitica to add your feature.
> Mention your Habitica ID for unlocking the in-game achievement


---
# Footnotes
[[JavaScript Interview Questions\|JavaScript Interview Questions]]
