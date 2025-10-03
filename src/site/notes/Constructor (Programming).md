---
{"dg-publish":true,"permalink":"/Constructor (Programming)/","tags":["Academics"]}
---


---
# Constructor (Programming)
> Public [[Functions in Programming\|Function]] in a [[Constructor (Programming)#Classes\|class]] which is automatically called whenever a new object is initialised. It has the same name as the class while it does not have a return type. 

Default constructor is called by the compiler in case it is not specified. It cannot be called independently.

### Main Types
Non-Parameterised Constructor does not take input in parenthesis
Parameterised Constructor directly takes in any values inside the parenthesis.
```CPP
class Teacher {// if employee class exists use ": public Employee"
	// properties or attributes
	private:
	double salary; // sensitive data hidden
	public: // access modifier, 'private' by default
	string name;
	string dept;
	string subject;
	
	Teacher(){ // Non-Parameterised Constructor
		// displays all teachers
	}
	
	Teacher(string name, string subject){ // Parameterised Constructor
		// displays specific teachers who have the same name & subject
	}
};

int main() {
Teacher t1;
t1.name = "Arnav"
t1.dept = 'C++'
// and so on
}
```

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

The default shallow copy made by the default [[Constructor (Programming)#Copy Constructor\|Copy Constructor]] copies all the member attributes and values from the existing object to new object. It works perfectly fine unless we are using words like "new" or we are using pointers or other features that require [[Dynamic Memory Allocation (DMA)\|Dynamic Memory Allocation (DMA)]].

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



---
# Footnotes