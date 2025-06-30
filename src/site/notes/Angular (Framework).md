---
{"dg-publish":true,"permalink":"/Angular (Framework)/","tags":["coding"]}
---


---
# Angular (Framework)
> Web Application Framework like [[ReactJS\|ReactJS]] to create a Single Page Applications (SPA) built by Google.

It slightly launched before [[ReactJS\|ReactJS]] and utilises [[JavaScript\|JavaScript]] and [[TypeScript\|TypeScript]] Knowledge. Many Google apps use Angular and it has a huge community which some would say is smaller than React but big enough to get Coding Tutorials on YouTube.

### Pre-requisites
- HTML/CSS
- [[JavaScript\|JavaScript]]
- [[Git and GitHub\|Git and GitHub]]
- [[Object Oriented Programming\|Object Oriented Programming]] concepts like Variables, Loops, Functions, Conditionals etc.
- VS Code
- Angular CLI
- Angular Language Server Extension on VS Code

### Benefits
- Faster Development
- Faster Code Generation using CLI
- Unit-tests ready
- Opinionated
	- Makes it easy to switch companies and teams.
- Code Reusability using Components, Pipes, etc.

### Angular vs React
- Angular is a framework, with built-in CLI, tools & packages included for small to medium scale apps.
- React is a Library, does not have a CLI, requires you to install additional packages even for small scale apps.

### Angular Myths
- It is not hard to learn
- Does not change at every update (major update every 6 months)
	- They provide docs on changes introdced
- Angular v18 is just as fast as [[ReactJS\|ReactJS]] and [[VueJS\|VueJS]].

### Creating an Angular App
On your VS Code Terminal use the following command:
```bash
npm install -g @angular/cli
```

for if you want to learn a specific version of Angular, use the folowing command:
```bash
npm install -g @angular/cli@13
```


Confirm the version with the following command
```bash
ng --version
```


Create the app with the command given below:
```bash
ng new <project-name> # optionally use --dry-run
# --dry-run will not actually save the files to memory.
```


IF you want some additional configuration use:
```bash
ng new <project-name> --inline-style --inline-template
```


> [!info] INFO: What if I don't want inline CSS afterwards?
> If you have inline style and want to remove it later, you can go into the `angular.json` files and remove the lines marking these two vars as true in the `schematics` value of the file.

### Running your project locally
When your downloads and setup is finished, we can run the new project simply by first using the `cd` command on the terminal to go inside the folder of the application just made:
```bash
cd <project-name>
```

and then go with one singular command:
```bash
npm start
```

In older versions of Angular such as version 13,
you may need to run a different command:
```bash
ng serve --open # -o is also fine
```

If you encounter any problems, use:
```bash
ng new -help
```

### Code Structure
The first thing that loads is `index.html`
The top level component is called `<app-root>` is the component where we instruct the main.ts to render the root component at the top.

### Angular Components
There can be multiple components that you can create, some for the page, then another for a header or date picker etc.

Each component has the following syntax:
```TypeScript
// import statements
import { RouterOutlet } from 'angular/router';

@Component({
	selector: 'app-root',
	standalone: true,
	imports: [RouterOutlet],
	template: `
		<h1> Welcome to {{title}}! </h1>
		<router-outlet />
	`,
	styles:[`
		Add any styles here in backticks (``)
	`]
})

export class AppComponent {
	title = 'first-ng-app';
}
```

Explaination:
The `@Component` is a decorator which contains additional information about the component. The `selector` inside it tells Angular to load the `Welcome to {{title}}` line when the AppComponent is called in the `main.ts` file and renders the `template` inside the Components.

One can also use the `templateUrl` where you can designate a path to the template. SImilarly one can also do the same for style which can be a path as described in `styleUrl`. 

It is recommended to get the Angular Dev Tools on the browser for extra information and help when we use the Inspect option on the browser to access the code and access the console.

To create a component in a particular folder use:
```bash
ng g c component/header
# g = generate, c = component
# full forms can also be used
# creates a component folder inside src & creates header folder and other surrounding files inside it automtically.
```

If full path is not needed, we can use:
```bash
ng g c header
# creates it inside src folder
```

### Data-Binding with Signals
The Process of passing data from one component to the next in Angular is called "Data-Binding". It can be done with or without signals. Signals are a new thing introduced after Angular 16, CPA works on Angular 13.

```TS
import { Component, signal } from '@angular/core';

@Component ({
	...,
	template: `
		<p>Here's my var's value: {{myVar()}}</p>
	`
})

class MyComponent {
	myVar = signal('some value');
}
```

The line `{{myVar()}}` calls the myVar like a function and calls its value. As long as you have provided a templateUrl, you can even call this in the template html page.

The html page must have this in it:
```html
<html>
<p>Here's my var's value: {{myVar()}}</p>
</html>
```

In the TypeScript file, we can just simply pass a `templateUrl` instead and it works the same way as before.

> [!tip] TIP: Signals cannot be reassigned without function
> Signals are treated almost as a datatype.
> You cannot assign the myVar's value to a `signal(0);` and then in the next line, use `myVar = 1;` since that will throw an error. Similar to how you can say that "Volkswagon Polo is a car owned by XYZ" but you cannot then say that the "Volkswagon Polo is ABC now", that won't be gramatically correct - it should be "Volkswagon Polo is a car owned by ABC now"
> 
> Similarly, `myVar = 1;` is not syntactically correct, you have to use `myVar.set(1);` or `myVar.update((val) => val + 1);`

### Data-Binding without Signals
If you don't use signals or if you are on Legacy Angular (like CPA)

We can use the following traditional method instead:
```TS
import { Component, signal } from '@angular/core';

@Component ({
	...,
	template: `
		<p>Here's my var's value: {{ myVar }}</p>
	`
})

class MyComponent {
	myVar = 'some value';
}
```

Notice the change, the text in the class is not being parsed through a signal function and instead of being `{{ myVar() }}` it is `{{ myVar }}` i.e., no parenthesis are used inside.

> [!tip] TIP: Signals are going to be the new default
> In projects utilising modern Angular beyond Angular V16, it is recommended one learns how to use a Signal because that is going to be the default way of passing data through.

### Event Listeners
Things that listen for a particular event to occur from the user side.

For example, if the programmer wants a specific event (like a log) to occur when the user does something (like pressing a key in the input field), they can do that in the following way:

HTML Template File
```html
<!-- call a function on key up event -->
<input type="text" (keyup)="KeyUpHandler()">
```

Component's TS file:
```TS
class MyComponent {
	keyUpHandler(){
		console.log('user typed something in the input')
	}
}
```

Now, if want to specify the event that needs to take place, do this:
1. Add a specific event type to Handler Function in the TS file: `keyUpHandler(event: KeyboardEvent)`
2. Add a `$event` to the function call in the HTML file like: `<input type="text" (keyup)="KeyUpHandler($event)"`.
3. Change the log statement to: `console.log('user pressed the $(event.key) key');`

In Totality, it will look like the following:

HTML Template file:
```html
<!-- call a function on key up event -->
<input type="text" (keyup)="KeyUpHandler($event)">
```

Component's TS file:
```TS
class MyComponent {
	keyUpHandler(event: KeyboardEvent){
		console.log('user pressed the $(event.key) key')
	}
}
```

### Routing in Angular
Routing allows you define multiple pages despite Angular being used to create a [[Single-Page Application (SPA)\|Single-Page Application (SPA)]]. Routing is often used for Navbars, Headers and Footers containing links.

For example: if one needs to create a separate page which leads the user to a separate page which showcases todo, so we can create a new component using the CLI commands. It will be created inside src by default.

```TS
import { Routes } from '@angular/router';

export const routes: Routes = [{
	path = '',
	patchMatch: 'full',
	loadComponent: () => {
		return import('./home/home.component').then((m)=>m.HomeComponent);
		// memorise above line, no logic can help explain this.
	}, 
}]
```

On the App Component, we go to the section on the template which is listing all the components and add a `<router-outlet />` tag.

Note that we don't need to specify as a part of `imports: ` in the `@Component` decorater. or load in in the `template: ` section.

We need to import `<li routerLink='/todos'>Todos</li>` as a list element inside the `<nav>` tag.

### Angular Services
Used to encapsulate data, make HTTP calls or performing tasks not data-rendering related. Example: Loading stuff from a Database is a good thing to use it as a service that triggers just once.

```bash
ng g service services/service_name
```

For Angular Diredctives, use the given video by skipping to the correct section: [[Angular (Framework)#^1\|Sources > 1]].
I could not finish Angular Services and Directives here since it is a quite big topic that is hard to study and learn.

---
# Sources
1. Learn Angular in 90 Minutes: https://youtu.be/oUmVFHlwZsI?feature=shared
{ #1}

2. 