---
{"dg-publish":true,"permalink":"/ReactJS/","tags":["coding"]}
---


---
# ReactJS
> A library for [[JavaScript\|JavaScript]] used to create the Frontend of any application or website.

React is one of the most used libraries in Front End JavaScript development.
The reason it is preferred is because it can create Single Page Applications which do not load when switching tabs - making the apps faster.

Learning curve of ReactJS is actually now pretty flat & easy. It is made by Facebook (Meta) so there is a good amount of people that are using the library and there exists a community - making debugging a lot simpler.
One only needs basic knowledge in HTML, CSS and JS to get started.

### Basic Code Flow
`Index.html` loads first followed by `main.jsx` and all of your code will be inside the `div` with `id = "root"`. Then the `main.jsx` file will call or load the `App.jsx` component.

The `main.jsx` file only does the is add `App.jsx` between the `root div`.

React differentiates between components and HTML tags by the use of capitalisation of the first letter since the rest of the syntax is the same. This is why `App.jsx` starts with a capital A.

Each component needs a wrapper (components need to be wrapped in a div)
```JSX
function App(){
	return (
		<div> <!--> Wrapper Starts <-->
			<h1>Hello World</h1>
		</div> <!--> Wrapper Ends <-->
	)
}

export default App
```

General convention is that the component function is named the same as the component file i.e., the function would be named `App` for a file named `App.jsx` & vice versa although the functions and component name may be different.

### File Structure
Keep Code in `src` and photos or publically viewable stuff in `public` folder while the private or inaccessible photos go into the `assets` folder inside `src`.

Only the `.config` files and things of that nature lie open outside any folder.  Your `git` files such as `.gitignore` is also present here.

### JavaScript inside JSX
JavaScript can be used inside JSX with the use of Curly Brackets (`{}`) and just typing the function's name inside (nothing else) calls the function when it is needed or asked for.

if we use `{function_name()}` instead of `{function_name}`, it will automatically call the function regardless of it is needed or not.

If the function of the same name is present inside and outside the same function, then priority is given to functions inside before the functions outside.

```JSX
function sum(a,b){
	return a+b
}

function App(){
	return (
		<div> <!--> Wrapper Starts <-->
			<h1>The Sum is: {sum(10,20)}</h1>
			<!--> {sum} calls the sum function <-->
			<!--> (10,20) passes the value of a & b <-->
			<h1>The Sum is: {sum?sum:"no sum found"}</h1>
			<!--> calls the sum function if a & b exist <-->
			<!--> if either is undefined, it returns string <-->
		</div> <!--> Wrapper Ends <-->
	)
}

export default App
```

To pass parameters onClick:
```JSX
<button onClick={()=>fruit("banana"))}>Banana</button>
<!--> fruit function passes an alert of fruit name passed <-->
```

### Creating a New Component
1. Create a new `.jsx` file inside `src` folder.
2. Create a [[JavaScript#Functions (Methods)\|JavaScript Function]] inside it of the same name.
	1. This JS function will act as the main function
3. Add any other functionality with additional JS functions as needed.
4. Format it similar to the code block given in [[ReactJS#Basic Code Flow\|Basic Code Flow]]...
5. Code the component in between the headers
6. Export the function using [[JavaScript#Import & Export Files in JS\|JavaScript Export]] after the function has finished
7. Import the Function in `App.jsx`.
8. Save & Enjoy.

### States & Hooks in ReactJS
ReactJS saves the state of the component and does not change it unless the component is re-rendered. In simpler words, the values of variables are not made to be dynamic in React. One has to use 'State' instead.

Variables store data but react is not as responsive for updating said data since it does not reload any components since components are supposed to be static & reduce rendering time.

State are like containers which store data and hence may store variables inside them but these are meant for dynamic components whose values change regularly AND the new value needs to be rendered over & over again regularly.

Example of States in Code:
```JSX
import {useState} from "react";
function App() {
	const [fruit,setFruit] = useState("Apple");
	const handleFruit=()=>{
		setFruit("Banana")
	}
		return {
			<div>
				<h1> setFruit is State </h1>
				<h1>fruit</h1>
				<button onClick={handleFruit}> Change Name </button>
			</div>
		}
}

export default App
```

Counter & Reverse Counter Updating Button Example for States
```JSX 
import {useState} from "react";

const Counter = () => {
	const [count, setCount] = useState(0);
	const [rCount, setRCount] = useState(10);
	return {
		<div>
		<h1>Counter</h1>
		<h2>reverse Counter : {rCount}<h2>
		<button onClick={()=>setCount(count+1)}>Update Count</button>
		<button onClick={()=>setCount(rCount-1)}>Update rCount</button>
		</div>
	}
}
```

"Hook" is regarded as a Special Feature for functional components.  Hooks let us use different React features from our components like State, Life Cycle Methods, Side Effects etc.

When we see `use` as a prefix in front of any functionality's name in its import statement such as `useState` or `useID`, we know they are possible only through Hooks i.e., these functionalities are a hook like states are also hooks.

### Conditional Statements
Using Conditionals is often useful to define conditional rendering i.e., rendering objects or components only when certain conditions are met.
```JSX
import {useState} from "react";

function App() {
	const [count, setCount] = useState(1);
	return {
		<div>
		<h1>{count}</h1>
		<button onClick={()=>setCount(count+1)}>Update Count</button>
		{
			count==0?<h1>Condition 0</h1>
			:count==1?<h1>Condition 1</h1>
			:count==2?<h1>Condition 2</h1>
			:count==3?<h1>Condition 3</h1>
			:<h1>Other Condition</h1>
		}
		</div>
	}
}

export default App
```

### Props in ReactJS
Used when we need to pass content from one component to another.

Code Example:
```JSX
// App.jsx
import User from "./user";

function App(){
	let userObject={
		name: "Arnav Gautam",
		age: "22",
		email: "arnavgautam2003@gmail.com"
	}
	return {
		<div>
		<h1>Props in ReactJS</h1>
		<User user={userObject}/>
		</div>
	}
}
```

```JSX
// User.jsx
// Data from App.jsx is moved through here. No one will know.
function User({name, age, email}) {
	
	return {
		<div>
		<h2>Name: {user.name}</h2>
		<h2>Age: {user.age}</h2>
		<h2>Email: {user.email}</h2>
		</div>
	}
}

export default User;
```

### 

---
# Footnotes