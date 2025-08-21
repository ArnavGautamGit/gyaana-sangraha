---
{"dg-publish":true,"permalink":"/Object Oriented Programming/","tags":["Academics","coding"]}
---


---
# Object Oriented Programming
> Concept which aids in efficiently converting natural language into code by using Classes and Objects to reduce/remove repetition in the code.

Object Oriented Programming is only possible in languages that support it, like C++, Python, Java etc.
Here we will use C++ for OOP concepts

---
# Chapter 1: Classes & Objects
## Classes
Defined as a specific classification of a certain kind of objects. Sometimes also defined as a group of objects. Similar to an actual class of students where each indicidual student is an Object.

Classes have a name based on what it signifies (like Car) are associated with a group of attributes which define it. Like a Car has 4 wheels, completely covered passenger bay etc. These attributes are also called Properties.

## Member Functions
Classes may also contain specifc functions inside them to avoid repetition of theirs. These functions usually operate on the objects or properties of their class which is why they are included IN the class to avoid repetition. These Functions are called "Methods" or "Member Functions"

## Objects
Individual Entities in the real world like individual kids in a class of students in school or college. Each Object can be assigned individual properties

## Access Modifiers
Specific keywords which decide whether the data in the form of attributes and variables whose access needs to be decidied whether they need to be private (visible only to THIS class), public (visible to all) and protected (private but [[Object Oriented Programming#Inheritance\|inheritable]]).

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
## Constructor
Public Function in a [[Object Oriented Programming#Classes\|class]] which is automatically called whenever a new object is initialised. It has the same name as the class while it does not have a return type (see [[Object Oriented Programming#Example of OOPs in School\|#Example of OOPs in School]]). Default constructor is called by the compiler in case it is not specified. It cannot be called independently.

### Classification on Parameterisation
Non-Parameterised Constructor does not take input like a function in parenthesis
While Parameterised Constructor is a type of Constructor which directly takes in any values inside the parenthesis.

### Copy Constructor
Parameterised Constructor which creates a new object which is a copy of another by taking the existing object as a parameter. It has a default constructor in case coder does not add it manually.

```CPP
class Student {
	public:
	string name;
	string cgpa;
	
	Student (Student &obj){ //manual shallow copy constructor
	this->name = obj.name;
	this->cgpa = obj.cgpa;
	}
};
```

The default shallow copy made by the default [[Object Oriented Programming#Copy Constructor\|Copy Constructor]] copies all the member attributes and values from the existing object to new object. It works perfectly fine unless we are using words like "new" or we are using pointers or other features that require [[Dynamic Memory Allocation (DMA)\|Dynamic Memory Allocation (DMA)]].

```CPP
new int[5]
// assign me new memory worth 5 integers 
```

how is this a problem? if two students in a school have the same name, the compiler may update the wrong student's data since both pointers are pointing to the same value.

Deep Copies need to be made manually. Since it does not copy the pointer, it creates a new variable by the same name in a new address.
```CPP
class Student {
	public:
	string name;
	double* cgpaPtr;
	
	Student (Student &obj){ //manual deep copy constructor
	this->name = obj.name;
	cgpaPtr = new double; // asks for new memory of same size
	*cgpaPtr = *obj.cgpaPtr; //creates new attribute with same value
	// allows the two attributes to be edited independently
	}
};
```

### Constructor Overloading
Process of creating multiple constructors of the same name in the same class to accept any different combination of parameters depending upon the situation's context - the number of variables, the types of variables called etc.

## Destructor
Opposite of [[Object Oriented Programming#Constructor\|Constructor]].
Default Entity that is automatically called to deallocate memory.
Not having destructors creates a problem where people forget to deallocate memory that was allocated using the "new" keyword in [[Dynamic Memory Allocation (DMA)\|Dynamic Memory Allocation (DMA)]] or Deep Copy Constructors. This is why compiler uses a default destructor.

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
# Chapter 2: Pillars of OOP
The Pillars which support OOP and their definitions are always asked in interviews. These four pillars are: Encapsulation, Abstraction, Inheritance and Polymorphism.

## Encapsulation
Wrapping attributes, member functions in a single unit known as a "[[Object Oriented Programming#Classes\|class]]".
This pillar is extensively helpful to protect [[Data Privacy\|Data Privacy]] on the coding level.

## Inheritance
Child (Derived) [[Object Oriented Programming#Classes\|class]] inherits attributes from Parent (Base) Class as it is.

In case the child class has an [[Object Oriented Programming#Objects\|object]] in it, the base class [[Object Oriented Programming#Constructor\|constructor]] is called first, followed by the derived class constructor because children cannot be born without their parents being born first. It is the other way around for [[Object Oriented Programming#Destructor\|destructors]].

```CPP
class Teacher {
	public:
	string name;
	double salary;
};

class Student {
	public:
	string name;
	int roll;
};

class TeachingAssistant : public Student, public Teacher {
	public:
	string subject
}
```

There are many different types of Inheritance possible on the basis of the structure formed by the number of parent & child classes and their relationships.
1. Single level: Parent + Child
2. Multi-level: Parent + Child + Grandchild
3. Multiple: One child inherits from two parents separated by commas
4. Heirarchal: Two Children inherit from same parent
5. Hybrid: game of thrones

## Abstraction
Hiding unnecessary details and showing only the important parts
Example: [[Object Oriented Programming#Access Modifiers\|Access Mods]] and Abstract Classes (meant to be used as a base class to define an interface for other derived classes, cannot create their own objects)

```CPP
class shape { // Abstract Class
	virtual void draw() = 0; // virtual function ki value zero
	//zero value virtual function is a PURE virtual function.
}

// A class with a pure virtual function is always an abstract class
```

## Polymorphism
Ability of objects to take multiple forms depending upon context.
Best example is [[Object Oriented Programming#Constructor Overloading\|Constructor Overloading]].

Polymorphism can be subdivided on the basis of when it occurs in the code's running cycle.
It can also be described as whether the Polymorphism is Static or Dynamic.
1. ***Compile-Time:*** [[Object Oriented Programming#Constructor Overloading\|Constructor Overloading]], [[Object Oriented Programming#Function Overloading\|Function Overloading]], [[Operator Overloading\|Operator Overloading]]
2. ***Run-Time (Dynamic):*** [[Object Oriented Programming#Function Overriding\|Function Overriding]]. 

### Function Overloading
Creating two or more functions of different number or typr of input parameters & return distinct output. The compiler differentiates dependent on context defined by parameter type & number.

### Function Overriding
Creating a new version of the function in child class which was originally used in a parent class. If the child's function is called, it overrides the parent's version of the function to ship its own.

### Virtual Functions
A member function which can be expected to be redefined in a derived class.
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

---
# Footnotes
1. Source: First Sem Notes + [Apni College OOPs Tutorial in One Shot](https://youtu.be/mlIUKyZIUUU?feature=shared)
2. 