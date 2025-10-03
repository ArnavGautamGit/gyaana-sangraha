---
{"dg-publish":true,"permalink":"/Destructor (Programming)/","tags":["Academics"]}
---


---
# Destructor (Programming)
> Opposite of [[Constructor (Programming)\|Constructor]]
> Special Public [[Functions in Programming\|Function]] of a class with the same name as the class automatically called whenever the object needs to be deallocated from [[Computer Memory\|Memory]].

Not having destructors creates a problem where people forget to deallocate memory that was allocated using the "new" keyword in [[Dynamic Memory Allocation (DMA)\|Dynamic Memory Allocation (DMA)]] or Deep Copy Constructors. This is why compiler uses a default destructor and it does not have to be called.

```CPP
class Student {
	//attributes go here
	
	Student (Student &obj){ //manual copy constructor
	this->name = obj.name;
	this->cgpa = obj.cgpa;
	}
	
	~Student (){ // manual destructor
	cout << "hello! I destroy the memory hogged by objects"
	}
};
```


---
# Footnotes