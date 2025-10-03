---
{"dg-publish":true,"permalink":"/Overloading & Overriding/","tags":["Academics"]}
---


---
# Overloading & Overriding
> Overloading means to create multiple versions of the same [[Functions in Programming\|function]]/operator where any particular version can be triggered given the conditions are met.
> 
> Overriding refers to creating a new version of the function or operator inside an [[Inheritance (Programming)\|inherited]] class which overrides the previous one i.e., only the new one will be triggered as long as the object is of the inherited class.

Both of them are used to create different versions/variants of the same functions and operators but differ in implementation.

### Where to use which?
If you want multiple versions of the same function or operator in the SAME class then overloading is the best option but if you require the functions to be split across multiple classes then either they need to have an [[Inheritance (Programming)\|Inheritance-based]] Structure or you will have to write distinct functions of unrelated classes that just seem to have the same name.

### Function Overloading
Creating two or more [[Functions in Programming\|Functions]] of same name but different number or type of input parameters & return distinct output. The compiler differentiates dependent on context defined by parameter type & number.

### Function Overriding
Creating a new version of the function in the [[Inheritance (Programming)\|inherited]] child class which was originally used in a parent class. If the child's function is called, it overrides the parent's version of the function to ship its own.

### Constructor Overloading
Process of creating multiple [[Constructor (Programming)\|Constructor]] of the same name (which is the same as the name of the class) but with tha ability to accept any different combination of parameters depending upon the situation's context - the number of variables, the types of variables called etc.
A [[Destructor (Programming)\|Destructor]] can be overloaded in the same way.
Constructors & Destructors (by definition) are [[Functions in Programming\|Functions]] anyway.

### Operator Overloading
Yet to revise and add to this portion.

---
# Footnotes