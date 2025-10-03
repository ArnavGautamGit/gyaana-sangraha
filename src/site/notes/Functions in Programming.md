---
{"dg-publish":true,"permalink":"/Functions in Programming/","tags":["Academics"]}
---


---
# Functions in Programming
> A set of sequential operations on specific variables that may or may not be present in a class.

Functions hat are present inside a class are called "Member Functions" or "Class Functions".
Whereas, the ones that are neither inside any class nor inside any other function are called "Independent Functions".

### Virtual Functions
A member function which can be expected to be redefined in a derived class after [[Inheritance (Programming)\|Inheritance]].
Naam ke aage virtual lagaado.
```CPP
// in base class
vitual void hehe(){
cout << "redefine me";
}

// in derived class
void hehe() {
cout << "redefined";
}
```

Functions of can be subject to both [[Overloading & Overriding\|Overloading & Overriding]] regardless of whether they are member functions of a class or independent functions.

---
# Footnotes