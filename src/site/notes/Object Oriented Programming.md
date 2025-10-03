---
{"dg-publish":true,"permalink":"/Object Oriented Programming/","tags":["Academics","coding"]}
---


---
# Object Oriented Programming
> Concept which aids in efficiently converting natural language into code by using Classes and Objects to reduce/remove repetition in the code.

Object Oriented Programming is only possible in languages that support it, like C++, Python, Java etc. Since C++ is the most popular language for studying [[Data Structures & Algorithms (DSA)\|DSA]], we will use it for studying OOP concepts as well to maintain momentum & connectivity.

### Advantages & Need
OOP concepts make it easier to write code since the programmer does not have to write the same code repeatedly. It allows the programmer to create a template for the same "class" of "objects" and get away with writing the code once and each time generating a new object instead.

### Related Notes
[[Classes & Objects\|Classes & Objects]]
[[Functions in Programming\|Functions]] (subheading on Virtual Functions)
[[Dynamic Memory Allocation (DMA)\|Dynamic Memory Allocation (DMA)]]
[[Constructor (Programming)\|Constructor]]
[[Destructor (Programming)\|Destructor]]
[[Overloading & Overriding\|Overloading & Overriding]]
[[Encapsulation (Programming)\|Encapsulation]]
[[Inheritance (Programming)\|Inheritance]]
[[Abstraction (Programming)\|Abstraction]]
[[Polymorphism (Programming)\|Polymorphism]]

## Example of OOPs in School
```CPP
class Teacher {// if employee class exists use ": public Employee"
	// properties or attributes
	private:
	double salary; // sensitive data hidden
	public: // access modifier, 'private' by default
	string name;
	string dept;
	string subject;
	// methods or member functions
	void changeDept(string newDept){
		dept = newDept;
	}
	void setSalary (double s){
		salary = s;
	}
	
	Teacher(){ //Constructor
	cout << "Hello I am a Constructor!" << endl;
	cout << "Standby as I initialise your object..." << endl;
	}
	
	Teacher(string name, string subject){ // Parameterised Constructor
	cout << "Hello I am a Constructor!" << endl;
	cout << "Standby as I initialise your object..." << endl;
	this->name = name;
	this->subject = subject;
	// what is "this->"?
	// automatically created pointer which points to calling object t1
	// pointers are usually created by adding * before their names
	// similarly '*this' refers to t1.
	// instead of writing "(*this).name", we write "this->name"
	// it enables faster and more legible coding. 
	}
};

int main() {
Teacher t1;
t1.name = "Arnav"
t1.dept = 'C++'
// and so on
}
```


---
# Footnotes
1. Source: First Sem Notes + [Apni College OOPs Tutorial in One Shot](https://youtu.be/mlIUKyZIUUU?feature=shared)
2. 