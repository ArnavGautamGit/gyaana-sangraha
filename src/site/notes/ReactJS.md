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

A "Hook" is regarded as a Special Feature for functional components.
Hooks let us use different React features from our components like State, Life Cycle Methods, Side Effects etc.

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

Now, we learn the basics of how to pass HTML and CSS via Props in ReactJS:
```JSX
//Inside App.jsx
import User from "./User.jsx"
function App(){
	return {
		<div>
			<h1>Props in ReactJS</h1>
			<User name="Arnav Gautam"/>
		</div>
	}
}

//Inside User.jsx
function User(name = "New User"){ // default value = "New User"
	return{
		<div>
			<h1>User Component</h1>
			<h3>Hi, {name}</h3>
		</div>
	}
}
```

To pass proper JSX through the props. we showcase the example with a new component called "Wrapper":
```JSX
// Inside Wrapper.jsx
function Wrapper(children) {
	return {
		<div>
			{children}
		</div>
	}
}

//Inside App.jsx
import User from "./User.jsx"
function App(){
	return {
		<div>
			<h1>Props in ReactJS</h1>
			<Wrapper>
				<h1>Hello Everyone</h1>
			</Wrapper>
		</div>
	}
}
```

### Input Field Operations
In the tutorials, there is an example usecase where there exists an input field whose contents should show outside the input textbox on the line below
```JSX
//Inside App.jsx
import User from "./User.jsx";
import { useState } from "react";

function App(){
	const [val,setVal] = useState;
	return {
		<div>
		<h1>Props in ReactJS</h1>
		<input type="text" onChange={(event) => setVal(event.target.value)} placeholder="Enter User Name"/>
		<h2>{val}</h2>
		<button onClick={()=>setVal("")}> Clear Value </button>
		</div>
	}
}

export default App;
```

### Controlled Components
A controlled component is a form whose input value is controlled by React's `useState` Hook.

Here's how it works:
- Store input field value in state
- Use `onChange` handler with input field
- Value attribute attached with State

Benefits:
- Validation and Manipulation before submit.
- Dynamically update values.
- Single Source of Information i.e., single source of variable value.

```JSX
// I am going to skip directly to inside App Function.
// Saves time and space. no point repeating boiler plate code.

function App (){
	const [name, setName] = useState('');
	const [password, setPassword] = useState('');
	const [email, setEmail] = useState('');
	
	return {
	<div>
	<h1> Controller Component</h1>
	<form action="" method="get">
		<input type="text" value={name} placeholder="Enter Name"/>
		<br/><br/>
		<input type="password" value={password} placeholder="Enter Password"/>
		<input type="text" value={email} placeholder="Enter Email"/>
		<br/><br/>
		<button>Submit</button>
		<button>Clear</button>
		<h3>{name}</h3>
		<h3>{password}</h3>
		<h3>{email}</h3>
	</form>
	</div>
	}
}

export default App;
```

Apart from this,
In an uncontrolled document, the data is passed through the DOM without using States or Hooks. This is more often used in Form Handling. It is to be noted that Controlled Components are preferred instead.

### Handling Checkboxes in States
Handling checkbox is slightly different since it has a boolean value as opposed to a string value.
- Make Checkbox
- Define State for Checkbox
- Remove the attribute from view by unchecking

```JSX
//Skills.jsx
function Skills(){
	const [skills, setSkills] = useState([]);
	const handleSkills=(event)=>{
		console.log(event.target.value, event.target.checked);
		if(event.target.checked){
			setSkills([...skills,event.target.value]);
			//"..." is spread operator
			// It allows an array to be written
		} 
		else {
			setSkills([...skills.filter((item)=>item!=event.target.value)])
		}
	}
	return {
	<div>
		<h3> Select Skills </h3>
		<input onChange={handleSkills} type="checkbox" id="Python" value="Python"/>
		<label htmlFor="Python">Python</label>
		<br /><br />
		<input onChange={handleSkills} type="checkbox" id="CPP" value="CPP"/>
		<label htmlFor="CPP">C++</label>
		<br /><br />
		<input onChange={handleSkills} type="checkbox" id="Java" value="Java"/>
		<label htmlFor="Java">Python</label>
				
	</div>
	}
}


//App.jsx
function App(){
	
	return {
	<div>
	<h1> Handle Checkbox in ReactJS</h1>
	<Skills />
	</div>
	}
}
```

### Handling Radio Buttons & Dropdowns
Similar to Checkboxes, we may also have to manage Radio Buttons or Dropdowns in forms. We first showcase how to manage them outside the form tag.

```JSX
//App.jsx
import { useState } from "react";

function App(){
	const [gender, setGender] = useState();
	const [city, setCity]=useState();
	return {
		<div>
		<h1>Handle Radio and Dropdown</h1>
		<h3> Select Gender </h3>
		<input onChange= {(event)=>setGender(event.target.value)} type="radio" name="gender" checked={gender=="female"} id="male" value={"male"}/>
		<label htmlFor="male">Male</label>
		<input onChange={(event)=>setGender(event.target.value)} type="radio" name="gender" checked={gender=="female"} id="female" value={"female"} />
		<label htmlFor="female">Female</label>
		<br /><br /><br />
		<h3>Select City</h3>
		<select onChange={(event)=>setCity(event.target.value)} defaultValue={"City"}>
		<option value="City">City</option>
		<option value="Noida">Noida</option>
		<option value="Delhi">Delhi</option>
		<option value="Gurugram">Gurugram</option>
		</select>
		</div>
	}
}

export default App;
```

### Other Popular Hooks in ReactJS
We have already seen the basics in [[ReactJS#States & Hooks in ReactJS\|the section on States]].
Popular hooks include `useState`, `useEffect`, `useContext`, `useRef` and `useReducer` among others.

An important rule of thumb that whenever a functionality starts with the name `use` it generally means the functionality is a Hook.

Custom Hooks can be created on ReactJS.

### useEffect Hook in ReactJS
It is often used as one of the life cycle methods, or to fetch data, or remove a side effect from inside or outside a particular component.

Syntax:
```JSX
useEffect(()=>{
	// stuff to trigger on dependency
}, [dependency])

// "dependency" must be replaced by a pre-defined state.
// Dependency Array, if left empty will cause only 1 call
// Dependency Array, if removed will cause call at every change
```

Multiple Effects can be used in one function. Multiple Functions can be used in the same component.

useEffect can be used for Life Cycle Methods and they can grow
ReactJS components only has 3 stages in their life cycle: Mounting, Updating and Unmounting.

### CSS in ReactJS
There are a few differences between regular CSS and the CSS used in ReactJS. For example, instead of using a hyphen to separate words like `background-color` we use CamelCase version that is `backgroundColor`. Similarly, we use commas instead of semicolons to separate CSS properties

Statements for CSS in React JS need to be presented in brackets for example: `<div style = {{ color: 'red' }}> Text </div>`.

To define CSS in a variable:
```JSX
const cardStyle = ()=> {
	border: "1px solid red",
	width: '200px',
	boxShadow: "1px, 1px, 1px, 1px #ccc"
	margin: "10px"
}
```

If you have defined the CSS as a const, you can use:
`<div style = {style}> Text </div>`

If themes are to be made, one can also define the styling variable as a State:
```JSX
const [cardColor, setCardColor]=useStyle(
	{
	border: "1px solid red",
	width: '200px',
	boxShadow: "1px, 1px, 1px, 1px #ccc",
	margin: "10px"
	}
)

const updateTheme=(bgColor, textColor)=>{
	setCardColor({...cardColor, backgroundColor:bgColor})
	setTextColor({textColor})
}

//inside the function return:
<div>
	<h1>Heading</h1>
	<button onClick={()=>updateTheme('gray', 'red')}>
	Click Here for Gray Theme
	</button>
	<p style={{ color: textColor}}>HEHE</p>
</div>

// On clicking the button, the values: grey and red are passed.
// The updateTheme function gets grey & red.
```

### useRef Hook in ReactJS
Before using the Hook, one needs to import said Hook: 
```JSX
import { useRef } from "react";
```

Then we add the line:
```JSX
const inputRef = useRef(null);
```

Now, we can use the Ref tag on any input field to manage the focus to that field.

### useFormStatus Hook in ReactJS
Does not work on old versions of ReactJS - it is a more recent addition to React. It is one of the shortest way to define whther the form has been submitted or not in a Boolean Value of True or False.

Import Hook:
```JSX
import { useFormStatus } from "react";
```

Using:
```JSX
const {pending} = useFormStatus();

<button disabled={pending}>{pending?"Submitting...":"Submit"}</button>
// The button is disabled until submission is complete
```

### useActionState Hook in ReactJS
Used to handle forms easily in ReactJS. Its internal state updates everytime you complete an action in the form. It can also be used to handle errors and validations.

We continue the example given in the previous section:
```JSX
const [data, action, pending] = useActionState (handleSubmit, undefined);
```

### useID Hook in ReactJS
Simple & Useful Hook used for generating unique IDs that can be passed to accessibility attributes. It generates a unique ID no matter how many times you call it in the same code.

```JSX
import { useID } from "react"

// We skip any function used in component
// saves time, I don't have to repeat myself
const name = useID();
```

### Custom Hooks in ReactJS
When ReactJS does not have a prebuilt Hook for the usecase you want, you can define & create your own custom hook which does what you want to accomplish.

```JSX
import { useState } from "react";

const useToggle = (defaultVal) => {
	const [value, setValue] = useState(defaultVal);
}
```

### React Router & Setup
What is the React Router? How to install it?
React Router is used to make web pages in React.

Run this command to install the library:
```bash
npm i react-router
```
[[Node Package Manager (NPM)\|Node Package Manager (NPM)]] will download the latest version automatically... Note that we download the library, not the framework (when we work with React Router in ReactJS).

An alternate way is to download it via Vite:
```bash
npx create vite
```

you will be prompted to enter a name, choose your library (React-Router), then coding language among JavaScript and TypeScript.

then inside the terminal, we run:
```bash
npm i react-router
```

It is not like webpages cannot be made without React Router, but it makes things easier for us simmilar to how horses made travel faster compared to travelling on foot - this is why horse-riding comprised the major part of human history.

To test the React Router & if it is working properly, use the tag `<BrowserRouter />` as a wrapper over the same page, if it continues working with no errors in the terminal/console then its working perfectly fine.

To link a page use the following syntax:
```JSX
<Routes>
<Route path="#" element ="XYZ.jsx" />
</Routes>
```

### Tailwind CSS Integration
Use Vite for integration from this link: https://tailwindcss.com/docs/guide/vite#react
Make sure you are using the correct tutorial which integrates [[Tailwind CSS\|Tailwind CSS]] into React only.

### Fetch Data from APIs
Using and Fetching data from an [[Application Programming Interface (API)\|Application Programming Interface (API)]]
It fetches, provides and keeps an eye on what kind & volume of data is being asked - if the demand is more than usual, it is also responsible for flagging it.



---
# Footnotes