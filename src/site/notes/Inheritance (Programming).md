---
{"dg-publish":true,"permalink":"/Inheritance (Programming)/","tags":["Academics"]}
---


---
# Inheritance (Programming)
> The concept in [[Object Oriented Programming\|Object Oriented Programming]] where certain [[Classes & Objects\|Classes]] inherit attributes as it is from Original Classes.

Where the inheriting classes are called as "Child" Classes while the classes that were used as a template are called "Parent" Classes.

In case the child class has [[Classes & Objects\|Objects]] in it, the base class [[Constructor (Programming)\|Constructor]] is called first, followed by the derived class constructor because children cannot be born without their parents being born first. It is the other way around for [[Destructor (Programming)\|Destructors]].

### Inheritance Structures
Many times, Inheritance works (or is designed to work) in one of the many available structures. 
- Single level: Parent + Child 
- Multi-level: Parent + Child + Grandchild
- Multiple: One child inherits from two parents separated by commas 
- Heirarchal: Two Children inherit from same parent 
- Hybrid: Game of Thrones

### Example
Below is an example of *Multiple* Inheritance due to the single class (*TeachingAssistant*) inheriting from two separate parent classes (*Student* & *Teacher*).

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

The `TeachingAssistant` Class inherits from both because a Teaching Assistant is often a final year student helping oiut the professors in college (similarly in schools) and have both student and techer rights depending upon context.

---
# Footnotes