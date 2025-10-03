---
{"dg-publish":true,"permalink":"/Abstraction (Programming)/","tags":["Academics"]}
---


---
# Abstraction (Programming)
> The concept in [[Object Oriented Programming\|Object Oriented Programming]] which involves hiding unnecessary details and showing only the important parts.

Example: [[Classes & Objects#Access Modifiers\|Access Modifiers]] and Abstract Classes (meant to be used as a base class to define an interface for other derived classes, cannot create their own objects)

```CPP
class shape { // Abstract Class
	virtual void draw() = 0; // virtual function ki value zero
	//zero value virtual function is a PURE virtual function.
}

// A class with a pure virtual function is always an abstract class
```

Abstraction is used to create [[Functions in Programming#Virtual Functions\|Virtual Functions]].


---
# Footnotes