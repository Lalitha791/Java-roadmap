
Detailed Notes: Object-Oriented Programming in Java (OOP 1 — Fundamentals & Core Concepts)

1. Motivation: Why Object-Oriented Programming?

In procedural programming, data is represented using primitive data types such as int, float, char, and boolean, or basic collections like arrays. While primitives work well for simple scalar values, software applications frequently model complex real-world entities that combine multiple related properties of varying data types into a single unit.

The Limitations of Primitive Arrays

Consider a scenario where a program must manage records for five students, where each student record contains a roll number, a name, and a marks percentage.

Using standard primitive arrays requires creating three separate, unlinked data structures:

// Storing 5 roll numbers
int[] rno = new int[5];

// Storing 5 names
String[] name = new String[5];

// Storing 5 marks
float[] marks = new float[5];


While index 0 across all three arrays refers conceptually to the first student, Java treats these three arrays as entirely independent objects in memory. There is no single variable or data structure that encapsulates a student's roll number, name, and marks together.

Array	Index 0	Index 1	Index 2
rno (int[])	101	102	103
name (String[])	"Alice"	"Bob"	"Charlie"
marks (float[])	92.5f	88.0f	95.4f

Problem: Managing multi-attribute entities via disjoint arrays forces programmers to maintain loose parallel index conventions manually, leading to error-prone code.

The OOP Solution: Custom Data Types via Classes

Object-Oriented Programming (OOP) addresses this limitation by allowing developers to construct custom, user-defined data types that combine properties and functions into a single entity.

Instead of three independent arrays, OOP allows declaring a single array of a custom Student type:

Student[] students = new Student[5];


Every single element in this Student array holds a complete student record containing a roll number, a name, and a marks percentage bound together.

2. Classes and Objects: Conceptual Foundations

The distinction between a Class and an Object forms the structural foundation of Object-Oriented Programming.

2.1 What is a Class?

A Class is a named group of properties (variables) and functions (methods). It serves as a logical construct, template, or blueprint that defines what properties and behaviors instances of that class will possess.

* Logical Construct: A class defines structure and rules but does not occupy physical space in heap memory during runtime.
* Naming Convention: Class names in Java are written in PascalCase (e.g., Student, Car, BankAccount).

class Student {
    int rno;
    String name;
    float marks;
}


Real-World Conceptual Analogies

* Car Blueprint vs. Physical Cars: A manufacturing specification for a car specifies that every car must have an engine type, a price, and a seating capacity. The specification itself is a logical template that cannot be driven on a road. Physical cars built according to this specification—such as a specific Maruti, Ferrari, or Audi—are the actual physical objects.
* Human Specification vs. Individual Humans: The general concept of "Human" defines shared structural rules (two hands, two legs, a name) and behaviors (walking, speaking). Specific individuals are physical instances of the Human specification.

2.2 What is an Object?

An Object is a physical instance of a class. It represents a real-world entity created according to the template defined by its class and occupies actual memory space in heap memory during program execution.

Key Rule: A class is a logical template that exists in code structure; an object is a physical entity created in memory at runtime.

2.3 Three Characteristics of an Object

Every object in Java is characterized by three defining properties:

Characteristic	Description	Example in Student Object
State	The data or values stored in the object's instance variables at any given time.	rno = 13, name = "Kunal", marks = 88.5f
Behavior	The actions or functions that the object can perform (defined by class methods).	greeting(), changeName("Rahul")
Identity	A unique value or memory reference that distinguishes one object from another in heap memory, even if their states are identical.	The distinct heap memory location allocated to the object instance.

3. Declaring and Instantiating Objects

Creating an object in Java involves declaring a reference variable and instantiating the object dynamically in memory.

3.1 Object Creation Syntax

Student kunal = new Student();


This single statement performs two distinct operations across Stack and Heap memory:

// Step 1: Declaration (Stack Memory)
Student kunal;

// Step 2: Instantiation & Initialization (Heap Memory)
kunal = new Student();


1. Declaration (Student kunal;): Declares a reference variable named kunal of type Student. At this stage, the variable is allocated on the Stack and contains no reference to an object (evaluates to null if uninitialized).
2. Instantiation (new Student()): The new operator dynamically allocates memory for a new Student object in Heap memory at runtime, invokes the constructor to initialize its state, and assigns the memory reference to kunal.

3.2 Accessing Instance Variables: The Dot Operator

Instance variables are variables declared inside a class but outside any method or constructor. They define the state of an object instance.

To access or modify an object's instance variables, Java uses the dot operator (.):

// Instantiating an object
Student kunal = new Student();

// Assigning values to instance variables
kunal.rno = 13;
kunal.name = "Kunal Kushwaha";
kunal.marks = 88.5f;

// Accessing values
System.out.println(kunal.rno);   // Outputs: 13
System.out.println(kunal.name);  // Outputs: Kunal Kushwaha
System.out.println(kunal.marks); // Outputs: 88.5


Language Specification Note: While commonly called the "dot operator", the Java Language Specification formally categorizes . as a dot separator. It links a reference variable to an instance field or method.

3.3 Default Values of Instance Variables

When an object is instantiated using new Student(), Java automatically assigns default values to its fields if they are not explicitly initialized.

Student student = new Student();
System.out.println(student.rno);   // 0
System.out.println(student.name);  // null
System.out.println(student.marks); // 0.0


Field Data Type	Default Value
byte, short, int, long	0
float, double	0.0 / 0.0f
boolean	false
char	'\u0000' (null character)
Object References (String, custom classes)	null

4. Memory Management: Stack vs. Heap Mechanics

Understanding Java's memory allocation model is critical for mastering Object-Oriented Programming.

4.1 Memory Allocation Breakdown

Java divides runtime memory primarily into Stack Memory and Heap Memory:

* Stack Memory: Stores local variables, primitive data values, and object reference variables. Method execution frames are pushed and popped here. Stack allocation is static and managed during program execution flow.
* Heap Memory: Stores all objects created in Java. Memory allocation in Heap occurs dynamically at runtime via the new keyword.

Memory Structure	Stored Elements	Lifecycle / Allocation
Stack Memory	Primitive local variables, Object reference variables (kunal, s1)	Managed automatically during method call stack execution.
Heap Memory	Actual Object instances (Student object data, instance fields)	Dynamically allocated at runtime via new; reclaimed by Garbage Collector.

4.2 Dynamic Memory Allocation & The new Operator

In Java, all objects are dynamically allocated in Heap memory.

* Compile Time: The compiler checks type validity, syntax, and reference declarations (Student kunal).
* Runtime: Executing new Student() allocates memory space in the Heap dynamically while the program is running.

Key Rule: Java does not support manual pointer manipulation or static stack-allocated objects. Every object instance lives in Heap memory.

4.3 Reference Assignments and Alias Behavior

Assigning one object reference variable to another does not create a copy of the object in Heap memory. Instead, both variables point to the exact same object address.

Student s1 = new Student();
s1.rno = 13;
s1.name = "Kunal";

// Assigning s1 reference to s2
Student s2 = s1;

System.out.println(s2.name); // Outputs: Kunal

// Modifying object state through s2
s2.name = "Rahul";

// Change is visible through s1
System.out.println(s1.name); // Outputs: Rahul


Both s1 and s2 are reference variables residing in Stack memory that store the memory address of the exact same Student object in Heap memory.

5. Constructors: Object Initialization Framework

A Constructor is a special block of code inside a class that is automatically executed when an object is created using the new keyword. Its primary purpose is to initialize the state of the newly instantiated object.

5.1 Properties of Constructors

1. Name: Must have the exact same name as the class.
2. No Return Type: Does not specify any return type, not even void.
3. Execution: Called implicitly during new ClassName() execution.

5.2 Types of Constructors

1. Default (No-Argument) Constructor

If a class does not define any explicit constructors, the Java compiler automatically inserts a default no-argument constructor. This constructor assigns default values (0, null, false) to instance variables.

class Student {
    int rno;
    String name;
    float marks;

    // Default constructor inserted automatically if no constructors are written:
    // Student() { }
}


2. Parameterized Constructor

A constructor that accepts arguments to initialize instance variables with specific values upon object creation.

class Student {
    int rno;
    String name;
    float marks;

    // Parameterized Constructor
    Student(int roll, String studentName, float studentMarks) {
        rno = roll;
        name = studentName;
        marks = studentMarks;
    }
}


Usage:

Student kunal = new Student(13, "Kunal Kushwaha", 88.5f);


3. Constructor Overloading & Copy Constructors

Java supports defining multiple constructors within the same class, provided they have different parameter signatures.

class Student {
    int rno;
    String name;
    float marks;

    // 1. Default / No-Arg Constructor
    Student() {
        this.rno = 0;
        this.name = "Default Student";
        this.marks = 0.0f;
    }

    // 2. Parameterized Constructor (3 parameters)
    Student(int rno, String name, float marks) {
        this.rno = rno;
        this.name = name;
        this.marks = marks;
    }

    // 3. Copy Constructor (takes another Student object as parameter)
    Student(Student other) {
        this.rno = other.rno;
        this.name = other.name;
        this.marks = other.marks;
    }
}


Usage:

Student s1 = new Student();                             // Invokes No-Arg Constructor
Student s2 = new Student(14, "Rahul", 91.2f);           // Invokes Parameterized Constructor
Student s3 = new Student(s2);                            // Invokes Copy Constructor


6. The this Keyword Mechanics

The this keyword is a reference variable in Java that points directly to the current object instance executing the method or constructor.

6.1 Disambiguating Field Names

When parameter names in a constructor or method match instance variable names, local parameters shadow instance variables. The this keyword resolves this ambiguity by explicitly referencing the instance variable of the current object.

class Student {
    int rno;
    String name;
    float marks;

    // Parameter names match instance field names
    Student(int rno, String name, float marks) {
        // Without 'this', 'rno = rno' assigns local parameter to itself!
        this.rno = rno;   // 'this.rno' refers to the instance variable of current object
        this.name = name;
        this.marks = marks;
    }
}


During execution of new Student(13, "Kunal", 88.5f) assigned to reference kunal, Java internally evaluates this.rno as kunal.rno.

6.2 Method Invocation via this

Inside class methods, this can be used to reference instance fields or call other methods of the current object:

class Student {
    String name;

    void greeting() {
        System.out.println("Hello, my name is " + this.name);
    }
}


6.3 Constructor Chaining using this()

Java allows calling one constructor from another constructor within the same class using this(...). This pattern is called constructor chaining.

class Student {
    int rno;
    String name;
    float marks;

    // Primary Parameterized Constructor
    Student(int rno, String name, float marks) {
        this.rno = rno;
        this.name = name;
        this.marks = marks;
    }

    // Default Constructor chaining to Primary Constructor
    Student() {
        // Invokes Student(13, "Default Person", 100.0f)
        this(13, "Default Person", 100.0f);
    }
}


Syntax Requirement: When using this(...) to chain constructors, the statement must be the very first line of code inside the calling constructor body.

7. Primitives vs. Wrapper Classes and Pass-by-Value Semantics

7.1 Why Java Primitives Are Not Objects

In some languages (such as Python), all variables including numbers are objects. Java retains primitive data types (int, float, char, double, boolean, byte, short, long) to maximize performance.

Primitives are stored directly on the Stack frame, eliminating the memory overhead of heap headers and pointer dereferencing.

7.2 Wrapper Classes

To allow primitives to be used where objects are required (such as in Java Collections Framework), Java provides Wrapper Classes in java.lang:

Primitive Type	Wrapper Class
int	Integer
float	Float
double	Double
char	Character
boolean	Boolean

Example declaration:

// Autoboxing primitive 45 into Integer object
Integer num = 45; 


7.3 Pass-by-Value Semantics in Java

A fundamental rule in Java is that Java is strictly Pass-by-Value. There is no pass-by-reference mechanism in Java.

1. Passing Primitives: The value of the primitive variable is copied. Changes inside the method do not affect the caller's variable.

void swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}
// Calling swap(x, y) does NOT alter x and y in main().


1. Passing Object References: When an object reference is passed to a method, a copy of the reference address is passed by value. Both the caller's reference and the method parameter reference point to the same object in Heap memory.

class Student {
    String name;
    Student(String name) { this.name = name; }
}

void changeName(Student s) {
    s.name = "Modified Name"; // Modifies the object in Heap
}


Why Swapping Integer Objects Fails

Attempting to swap two Integer wrapper objects inside a helper method does not modify the original variables:

void swap(Integer a, Integer b) {
    Integer temp = a;
    a = b;
    b = temp;
}

public static void main(String[] args) {
    Integer a = 10;
    Integer b = 20;
    swap(a, b);
    System.out.println(a + " " + b); // Outputs: 10 20
}


Reasons:

1. Passing a and b copies their reference addresses by value. Reassigning a = b inside swap() alters local reference copies only.
2. The Integer class in Java is final and immutable. The underlying primitive value stored inside an Integer instance cannot be changed after instantiation.

8. The final Keyword in Depth

The final keyword in Java is used to enforce immutability across variables, methods, and classes.

8.1 final with Primitive Variables

When applied to a primitive variable, final creates a constant whose value cannot be modified after assignment.

final int INCREASE = 2;
// INCREASE = 3; // Compile Error: cannot assign a value to final variable INCREASE


Best Practice: Primitive final constants are named in ALL_CAPS by convention. final variables must be initialized during declaration or within class constructors.

8.2 final with Object References

When an object reference variable is declared final, the reference address itself cannot be reassigned to point to a different object. However, the internal properties (state) of the object can still be modified.

final Student kunal = new Student(13, "Kunal", 88.5f);

// 1. Modifying object fields IS ALLOWED:
kunal.name = "Kunal Kushwaha"; // Valid!

// 2. Reassigning reference variable IS NOT ALLOWED:
// kunal = new Student(14, "Rahul", 90.0f); 
// Compile Error: cannot assign a value to final variable kunal


Context	final Restriction	Field / Value Mutability
Primitive Variable	Primitive value cannot be changed.	Value is strictly immutable.
Object Reference	Memory reference address cannot be changed.	Object internal state can be modified.

9. Garbage Collection and Object Lifecycle

9.1 Automatic Garbage Collection in Java

In languages like C++, memory allocated dynamically using new must be freed manually using delete. Failing to free unused memory causes memory leaks.

Java automates memory management using the Garbage Collector (GC):

* When an object in Heap memory no longer has any active reference variables pointing to it, it becomes unreachable.
* The Garbage Collector runs periodically in the background to reclaim memory occupied by unreachable objects.

Student s1 = new Student();
Student s2 = new Student();

// Reassigning s1 points it to s2's object.
// The original object created for s1 now has 0 references and becomes eligible for GC.
s1 = s2; 


9.2 The finalize() Method

Programmers cannot force object destruction in Java. However, Java provides a mechanism to execute cleanup operations right before an object is reclaimed by GC via the finalize() method inherited from java.lang.Object.

class Student {
    String name;

    Student(String name) {
        this.name = name;
    }

    @Override
    protected void finalize() throws Throwable {
        System.out.println("Object is being destroyed by Garbage Collector");
    }
}


Important Characteristics of finalize()

1. Invocation: Executed automatically by Garbage Collector prior to reclaiming an unreachable object's memory.
2. Uncertain Timing: Java does not guarantee when GC will execute or when finalize() will be called, as GC triggering depends on runtime memory pressure.
3. Deprecation Context: In modern Java releases, finalize() is deprecated in favor of AutoCloseable resources and Cleaner API, but understanding its lifecycle role remains essential.

10. Summary Reference & Review Exercises

10.1 Key Concept Quick Reference

Term / Keyword	Role & Behavior	Memory & Execution Impact
class	Template / blueprint defining properties and behaviors.	Logical construct; 0 Heap memory allocated.
object	Physical instance created from a class template.	Occupies Heap memory at runtime.
new	Dynamic memory allocation operator.	Allocates Heap space and returns reference address.
this	Reference variable pointing to the current object.	Evaluated as active object reference at runtime.
constructor	Special initialization block matching class name.	Executed implicitly during new instantiation.
final	Prevents primitive modification or reference reassignment.	Locks Stack reference address or primitive value.
finalize()	Callback executed by GC before object destruction.	Invoked prior to Heap memory reclamation.

10.2 Self-Assessment Review Questions & Answers

Question 1: What is the difference between declaring a reference variable and instantiating an object in Java?

Answer: Declaring a reference variable (e.g., Student kunal;) allocates a reference variable on the Stack, which defaults to null if uninitialized. Instantiating an object (e.g., new Student();) uses the new operator to dynamically allocate memory for the object on the Heap at runtime and returns its memory address to the reference variable.

Question 2: Why does modifying an object through one reference variable affect another reference variable assigned to it?

Answer: Assigning reference variables (e.g., Student s2 = s1;) copies the memory reference address from s1 to s2, not the underlying object data. Since both variables point to the exact same object instance in Heap memory, state changes made via s2 are immediately reflected when accessing the object through s1.

Question 3: Can you modify an instance field of a final object reference in Java?

Answer: Yes. Marking an object reference variable final (e.g., final Student s = new Student();) prevents the reference variable s from being reassigned to point to a different object address in memory. However, the internal fields and properties of the object itself remain mutable and can be freely modified (e.g., s.name = "New Name";).

Question 4: How does constructor chaining work using the this keyword?

Answer: Constructor chaining allows one constructor in a class to invoke another constructor in the same class using this(arguments). This avoids code duplication across constructors. The call to this(...) must always be the very first statement inside the calling constructor body.

Question 5: Why are Java primitive data types not objects, and how are wrapper classes used?

Answer: Primitive types (int, float, boolean, etc.) are stored directly on the Stack to optimize execution performance and eliminate heap allocation overhead. Wrapper classes (Integer, Float, Boolean, etc.) wrap primitive values into Heap objects when object representations are required, such as in generic collections.
