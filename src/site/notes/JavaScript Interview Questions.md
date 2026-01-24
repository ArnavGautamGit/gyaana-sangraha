---
{"dg-publish":true,"permalink":"/JavaScript Interview Questions/","tags":["coding"]}
---


---
# JavaScript Interview Questions
> A note that notes down the questions & answers to popular [[JavaScript\|JavaScript]] questions asked in the interview.

The Note starts with Basic Questions and increases the levels of the same as we go further down the note.

### What are Variables in JavaScript?
Variables are a store of value where the same value can be operated upon by [[Functions in Programming\|Functions]], [[Classes & Objects\|Objects]] and operators such as addition (+), subtraction (-) etc. In JavaScript, Variables can be defined in 3 ways: `var`, `let` and `const`.

Variabes defined by anyone of the 3 methods can hold the same data types but there are a few differences among them due to which one may choose one over the other.

### What is the difference between `var`, `let` and `const`?
Firstly, `var` has always been there since the very beginning of JS while `let` & `const` were added in ES6 version of JS to fix the problems introduced by the scope of `var`. Newer versions of JS warn users against using `var` since it might get deprecated soon.

Secondly, while `var` has a global scope, `let` & `const` have limited (block) scope. This means that a variable defined using `var` in one function, can be accessed & edited by any other [[Functions in Programming\|function]]. Having a limited scope means that `let` or `const` variables cannot be accessed by other blocks/functions - introducing the concept of shadowing (using the same variable name in different blocks).

Thirdly, while the values of variables defined using `let` can be updated, the values of variables defined using `const` cannot be since it is a way of declaring static or constant variables i.e., their values cannot be changed once defined.

Fourthly, while variables using `let` can be declared without a value, `const` cannot be.
```JS
let a; // ok
var b; // ok
const c; // error
```

Finally, variables using `var` are hoisted globally while the variables using `let` are hoisted in the temporal dead zone of the code (between the creation & initialisation of the code).
```JS
// what you write:
console.log(count);
var count = 1;

// what the compiler sees:
var count;
console.log(count); //breakpoint here will give 
count = 1;

// output: undefined

// because at the time of creation/build of the code, it stores the declared 
// variables separately. If you insert a breakpoint at console.log() command,
// you would see the console.log() has been initialised but not the variable.
```

In case of `let` variables,
```JS
//what you write:
console.log(count);
var count = 1;
let count2 = 2;

// if you insert a breakpoint at the console.log(count) command...
// you would see the console.log() has been initialised but not the variables.
// var has function scope, so it can be printed as is, let cannot be operated upon before it is initialised. 
```


> [!tip] TIP: Blocks are defined by curly bracket pairs
> Blocks are often synonymous with functions since curly brackets are used to define the boundaries of a function as well as a block but this is an important distinction in cases when [[Functions in Programming\|Functions]] are nested or when conditional statements like If-Else are used in the functions.
> 
> technically you can use the same variable name for two different variables in two separate blocks, this is called Shadowing. A variable defined using `var` can be shadowed using `let` but NOT the other way around since the scope of `var` is larger. Think of it as the programming equivalent of the [[Russian Marushka Doll\|Russian Marushka Doll]] where a smaller doll (`let`) can fit inside (shadow) a larger doll (`var`) but a larger doll cannot fit in a smaller doll.
> 
> ```JS
> // suppose this is a function
> function(test){
> 	let a = "hello";
> 	if(true){
> 		let a = "Hi";
> 		console.log(a);
> 	}
> 	console.log (a);
> }
> ```
> 
> ```JS
> OUTPUT:
> Hi // from inside the loop
> hello // from outside the loop
> ```

### What is the difference between a Function Declaration and a Function Expression?
A Function declaration is writing out the entire function (excluding the line that calls said function) but a function expression is storing an anonymous function or callback with no name as a variable.

Function Declaration:
```JS
function square (num) {
	return num*num;
}
```

Function Expression:
```JS
const square = (num) => {
	return num*num;
}
```

### What is a Closure in JavaScript?
It is defined as a situation where an inner function nested in an outer one gets the variables it needs from the outer function but performs all the actions using inner functions. It is not a special syntax, it happens automatically.

A popular usecase is to create private variables which cannot be accesssed directly (like salaries and other such private info)
```JS
function createUser(name){
	let _name = name;
	
	return {
		getName(){ return _name },
		setName(newName){ _name = newName },
		sayHi(){ console.log(`Hi, ${_name}`) }
	};
}

const user = createUser("Arnav")

user.sayHi(); // Output: "Hi, Arnav"
user.setName("Max Verstappen"); // name is now Max Verstappen
user.sayHi(); // Output: "Hi, Max Verstappen"
```

Normally the variable `_name` is gone from memory but since the inner ones like `getName()` require the variable, it is kept alive by JavaScript. This is a closure.

### What are the different ways to define an array in JavaScript?
Arrays can be defined in many ways in JavaScript.
One of the most direct methods is via an Array Literal, where we directly define the array:
```JS
const array = ["Zero", 1, 2, "Arnav"];
```

There is also the Array Constructor that could be used to create an array in JavaScript. It is used since it can provide a simple way to create arrays that easily work for different outcomes.
For example:
```JS
const numbers = new Array(1, 2, 3, 4, 5);
```

| ***DESIRED OUTCOME***                          | ***CODE EXAMPLE***                    |
| ---------------------------------------------- | ------------------------------------- |
| normal array with values                       | `const arr = [1, 2, 3];`              |
| empty array                                    | `const arr = [];`                     |
| empty array of specific length (eg: 10)        | `Array.from({ length: 10 });`         |
| array of defined length filled with same value | `Array(length).fill(value);`          |
| array from a string/NodeList                   | `Array.from("hello");`                |
| array of a number sequence                     | `Array.from({length: n}, (_,i) => i)` |

### What is Destructuring in JavaScript? Can you demonstrate destructuring in Arrays & Objects?
Destructuring is a method to unpack the contents of any array or object in order to access or operate upon individual elements or properties contained within an array or object respectively.

```JS
// Array Destructuring
const [a, b, c] = [10, 50, 100]

console.log(a) // Output = 10
console.log(b) // Output = 50
console.log(c) // Output = 100
```

```JS
// Object Destructuring
const user {
	id: 101,
	name: "Arnav Gautam"
	age: 23,
	isActive: true
};

const {id, name, age} = user;
console.log(id);
console.log(name);
console.log(age);
```

A very common real world usecase is given below:
```JS
function greet({ name, age, city = "Unknown" }){
	console.log(`Hello ${name}, you are ${age} from ${city}`); 
}

greet({ name: "Arnav", age: 24 }); // Hello Sara, you are 24 from Unknown
greet({ name: "Interviewer" }); // personal connect with interviewer when you ask age (only if male, else let age go).
```

### Can you reverse a given string?
This is a simple question which can be done in one line in JavaScript.
This is often asked in interviews and you can solve it like so:
```JS
function reverseString(str){
	let str = "Arnav";
	return str.split("").reverse().join("");
	// return [...str].reverse().join(""); is another alternate.
}

reverseString();
```

One can also use the array from a string method discussed above in the string subheading like the following code snippet:
```JS
function reverseString(){
	let str = "Arnav";
	const reversed = Array.from(str).reverse().join("");
	console.log(reversed);
}

reverseString();
```

### What is an Event Loop?
[[JavaScript\|JavaScript]] is single threaded, but an Event Loop is a very clever event scheduler.
It uses Promises to run asynchronus code in JS despite it being a single-threaded language.
For more, please refer to [[Event Loops in JS\|Event Loops in JS]]

### What is the difference between Map, Filter & Reduce?
Map, Filter and Reduce are array functions that can perform transformations or operations on an array. Each may or may not output a new array with the operation/transformation performed. 

`map();` method creates a new array after operating on each element of the array by using a callback function to iterate over all the elements and perform the operation assigned one by one on each element while traversing the array & store the outputs in a new array. 

Syntax:
```JS
const arr = ["x", y, 3]; // take any given or random array
const newArr = arr.map((element, index, array) => {
	// operation to perform
})

console.log(newArr); // prints the new array
```

Example:
```JS
const nums = [1, 2, 3];
const multiplyThree = nums.map((num, i, arr) => {
	return num * 3 + i; // multiplies the element by 3 & adds the index to it.
})

console.log(multiplyThree);
```

On the other hand,
`filter();` creates a new array and adds only those elements to it from the starting array that satisfy the criteria set by one or more conditional statements.

Syntax:
```JS
const arr = ["x", y, 3]; // take any given or random array
const newArr = arr.filter((element, index, array) => {
	// conditional statement like "return element > 2" or similar
})

console.log(newArr);
```

Example:
```JS
const nums = [1, 2, 3];
const moreThanTwo = nums.filter((num, i, arr) => {
	return num > 2; // includes only elements larger than 2 in the output
})

console.log(moreThanTwo); // prints the array with only 3 as the sole element
```

Finally we have,
`reduce();` is the most complex function of the three which reduces the entire array down to one value (not an array). Unlike map & filter, it also takes an initial value with the callback function. In the callback function itself it takes an accumulator and current values in addition to the index & array.

Syntax:
```JS
const arr = ["x", y, 3];
const reducedArr = arr.reduce((accumulator, currentValue, index, array) => {
	// accumulator is the value from previous computation
	// return statement to define criteria of reduction
}, initialValue)

// if initial value is zero, it begins with the zeroth index of the array i.e., accumulator is kept zero.
console.log(reducedArr)
```

Example:
```JS
const nums = [1, 2, 3];
const sum = nums.reduce((acc, curr, i, arr) => {
	return acc + curr;
}, 0)

console.log(sum) // gives 1+2+3 = 6 as the output
```

In conclusion, the differences are that while `map()` and `filter()` give a new array, `reduce()` does not. At the same time, while `map()` actually operates on the array, `filter()` just checks if conditionals are satisfied - if yes, then selects the element for the output array.

### What is the differrence between Map & forEach?
While both can be used for operating on each element of an array one by one & still achieve the same output, it is important to note that while `forEach()` will modify the current array, `map()` would create a new array - leaving the original untouched, free to be used again.

Additionally, while `map()` allows us to chain other functions such as `filter()` and `reduce()`, functions like `forEach()` cannot be chained...

For example, if you are given a list of students:
```JS
let students = [
	{name: "Aaditya Sparsh", roll: 1, marks: 95},
	{name: "Aaryan Bhardwaj", roll: 2, marks: 93},
	{name: "Aditya Raj Singh", roll: 3, marks: 90},
	{name: "Aditya S. Singh", roll: 4, marks: 100},
	{name: "Arnav Gautam", roll: 5, marks: 100},
	{name: "Aryan Shukla", roll: 6, marks: 94},
	{name: "Aviral Jain", roll: 7, marks: 98}
	// and so on
];

const names = students.map((stu) => {stu.name.toUpperCase()});
const topper = students.filter((stu) => {stu.marks > 97})
// these 2 lines would take many pragraphs with for/forEach loops.

console.log(names); // Prints all the student names in capital letters.
console.log(topper); // Prints the names of students who got more than 97.
```


---
# Footnotes