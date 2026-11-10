# Java OOP – Complete Notes with Programs

**Learning:** Core Java – Object-Oriented Programming (OOP)
**Purpose:** Infosys Systems Engineer Training & Coding Assessments
**Language:** Java

> Note: Each program is independent. Run each program separately using `Main.java` or an online Java compiler.

---

## Table of Contents

1. Class
2. Object
3. Fields and Methods
4. Constructor
5. Default Constructor
6. Parameterized Constructor
7. `this` Keyword
8. Constructor Overloading
9. `static` Keyword
10. Single Inheritance
11. Multilevel Inheritance
12. Hierarchical Inheritance
13. Method Overriding
14. Method Overloading
15. Encapsulation
16. Abstraction
17. Interface
18. Multiple Inheritance Using Interfaces
19. Multiple Implementations of an Interface
20. Runtime Polymorphism
21. Abstract Class vs Interface
22. Important OOP Keywords
23. Quick Revision

---

# 1. Class

### Definition

A class is a blueprint or template used to create objects.

### Syntax

```java
class ClassName {
    // Variables
    // Methods
}
```

### Example: Student Class

```java
class Student {
    String name;
    int rollNo;
    double marks;

    public static void main(String[] args) {
        Student s = new Student();

        s.name = "Lalitha";
        s.rollNo = 101;
        s.marks = 85.5;

        System.out.println("Name: " + s.name);
        System.out.println("Roll No: " + s.rollNo);
        System.out.println("Marks: " + s.marks);
    }
}
```

### Output

```text
Name: Lalitha
Roll No: 101
Marks: 85.5
```

**Remember:** Class = Blueprint.

---

# 2. Object

### Definition

An object is an instance of a class. It is created using the `new` keyword.

### Syntax

```java
ClassName objectName = new ClassName();
```

### Example: Create Three Student Objects

```java
class Student {
    String name;
    int rollNo;
    double marks;

    public static void main(String[] args) {

        Student s1 = new Student();
        s1.name = "Lalitha";
        s1.rollNo = 101;
        s1.marks = 85.5;

        Student s2 = new Student();
        s2.name = "Ravi";
        s2.rollNo = 102;
        s2.marks = 90.5;

        Student s3 = new Student();
        s3.name = "Priya";
        s3.rollNo = 103;
        s3.marks = 95.5;

        System.out.println(s1.name + " " + s1.rollNo);
        System.out.println(s2.name + " " + s2.rollNo);
        System.out.println(s3.name + " " + s3.rollNo);
    }
}
```

### Output

```text
Lalitha 101
Ravi 102
Priya 103
```

**Remember:**

- Class = Blueprint.
- Object = Instance of a class.
- `new` = Creates an object.

---

# 3. Fields and Methods

### Definition

- Fields are variables declared inside a class.
- Methods are blocks of code that perform specific tasks.

### Example: Car

```java
class Car {

    String brand;
    String color;

    void start() {
        System.out.println("Car started");
    }

    void stop() {
        System.out.println("Car stopped");
    }

    void display() {
        System.out.println("Brand: " + brand);
        System.out.println("Color: " + color);
    }

    public static void main(String[] args) {

        Car c = new Car();

        c.brand = "Toyota";
        c.color = "Black";

        c.display();
        c.start();
        c.stop();
    }
}
```

### Output

```text
Brand: Toyota
Color: Black
Car started
Car stopped
```

**Remember:**

- `brand`, `color` = Fields.
- `start()`, `stop()`, `display()` = Methods.

---

# 4. Constructor

### Definition

A constructor is a special block used to initialize an object.

### Rules

1. Constructor name must match the class name.
2. It does not have a return type.
3. It executes automatically when an object is created.

### Example

```java
class Employee {

    String name;
    int id;
    double salary;

    Employee(String n, int i, double s) {
        name = n;
        id = i;
        salary = s;
    }

    public static void main(String[] args) {

        Employee e = new Employee("Lalitha", 101, 25000);

        System.out.println(e.name);
        System.out.println(e.id);
        System.out.println(e.salary);
    }
}
```

### Output

```text
Lalitha
101
25000.0
```

**Remember:** A constructor initializes an object automatically during object creation.

---

# 5. Default Constructor

### Definition

A constructor without parameters is called a no-argument constructor.

### Example

```java
class Student {

    String name;
    int age;

    Student() {
        name = "Lalitha";
        age = 22;
    }

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println(s.name);
        System.out.println(s.age);
    }
}
```

### Output

```text
Lalitha
22
```

**Important:**

- A compiler-provided default constructor is supplied only when you do not declare any constructor.
- The `Student()` constructor above is explicitly written by us.

---

# 6. Parameterized Constructor

### Definition

A constructor that accepts parameters is called a parameterized constructor.

### Example: Bank Account

```java
class BankAccount {

    String accountHolder;
    long accountNumber;
    double balance;

    BankAccount(String name, long number, double amount) {
        accountHolder = name;
        accountNumber = number;
        balance = amount;
    }

    public static void main(String[] args) {

        BankAccount b = new BankAccount(
            "Lalitha", 1234567890L, 50000
        );

        System.out.println(b.accountHolder);
        System.out.println(b.accountNumber);
        System.out.println(b.balance);
    }
}
```

### Output

```text
Lalitha
1234567890
50000.0
```

**Remember:** Parameters allow us to initialize objects with different values.

---

# 7. `this` Keyword

### Definition

`this` refers to the current object.

It is commonly used when instance variable names and constructor parameter names are the same.

### Example: Three Employee Objects

```java
class Employee {

    String name;
    int id;
    double salary;

    Employee(String name, int id, double salary) {

        this.name = name;
        this.id = id;
        this.salary = salary;
    }

    void display() {
        System.out.println(name + " " + id + " " + salary);
    }

    public static void main(String[] args) {

        Employee e1 = new Employee("Lalitha", 101, 25000);
        Employee e2 = new Employee("Ravi", 102, 30000);
        Employee e3 = new Employee("Priya", 103, 35000);

        e1.display();
        e2.display();
        e3.display();
    }
}
```

### Output

```text
Lalitha 101 25000.0
Ravi 102 30000.0
Priya 103 35000.0
```

### Understand this statement

```java
this.name = name;
```

- `this.name` = Instance variable.
- `name` = Constructor parameter.
- `=` assigns the parameter value to the instance variable.

---

# 8. Constructor Overloading

### Definition

Creating multiple constructors in the same class with different parameter lists is called constructor overloading.

### Example

```java
class Person {

    String name;
    int age;

    Person() {
        name = "Unknown";
        age = 0;
    }

    Person(String name) {
        this.name = name;
    }

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void display() {
        System.out.println(name + " " + age);
    }

    public static void main(String[] args) {

        Person p1 = new Person();
        Person p2 = new Person("Lalitha");
        Person p3 = new Person("Ravi", 23);

        p1.display();
        p2.display();
        p3.display();
    }
}
```

### Output

```text
Unknown 0
Lalitha 0
Ravi 23
```

**Remember:** Same constructor name, different parameters.

---

# 9. `static` Keyword

### Definition

The `static` keyword makes a variable or method belong to the class rather than individual objects.

A static variable is shared by all objects of that class.

### Example: Count Objects

```java
class Student {

    String name;

    static int count = 0;

    Student(String name) {
        this.name = name;
        count++;
    }

    public static void main(String[] args) {

        Student s1 = new Student("Lalitha");
        Student s2 = new Student("Ravi");
        Student s3 = new Student("Priya");

        System.out.println(s1.name);
        System.out.println(s2.name);
        System.out.println(s3.name);

        System.out.println("Total objects: " + Student.count);
    }
}
```

### Output

```text
Lalitha
Ravi
Priya
Total objects: 3
```

**Remember:**

- Static variable = Shared by all objects.
- Static method = Can be called using the class name.
- `Student.count` = Accessing a static variable using the class name.

---

# 10. Single Inheritance

### Definition

When one child class inherits from one parent class, it is called single inheritance.

### Syntax

```java
class Child extends Parent {
}
```

### Example

```java
class Person {

    String name = "Lalitha";

    void display() {
        System.out.println("Name: " + name);
    }
}

class Student extends Person {

    int rollNo = 101;

    public static void main(String[] args) {

        Student s = new Student();

        s.display();

        System.out.println("Roll No: " + s.rollNo);
    }
}
```

### Output

```text
Name: Lalitha
Roll No: 101
```

**Remember:** `extends` is used for class inheritance.

---

# 11. Multilevel Inheritance

### Definition

When a class inherits from another child class, forming multiple levels, it is called multilevel inheritance.

### Example

```java
class Animal {

    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {

    void bark() {
        System.out.println("Dog barks");
    }
}

class Puppy extends Dog {

    void weep() {
        System.out.println("Puppy weeps");
    }

    public static void main(String[] args) {

        Puppy p = new Puppy();

        p.eat();
        p.bark();
        p.weep();
    }
}
```

### Output

```text
Animal eats
Dog barks
Puppy weeps
```

**Remember:**

`Animal → Dog → Puppy`

Puppy can access methods from both Dog and Animal.

---

# 12. Hierarchical Inheritance

### Definition

When multiple child classes inherit from the same parent class, it is called hierarchical inheritance.

### Example

```java
class Animal {

    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {

    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {

    void sound() {
        System.out.println("Cat meows");
    }
}

class Main {

    public static void main(String[] args) {

        Dog d = new Dog();
        Cat c = new Cat();

        d.eat();
        d.sound();

        c.eat();
        c.sound();
    }
}
```

### Output

```text
Animal eats
Dog barks
Animal eats
Cat meows
```

**Remember:** One parent, multiple child classes.

---

# 13. Method Overriding

### Definition

When a child class provides its own implementation of a method already defined in the parent class, it is called method overriding.

### Example

```java
class Animal {

    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {

    @Override
    void sound() {
        System.out.println("Dog barks");
    }

    public static void main(String[] args) {

        Dog d = new Dog();

        d.sound();
    }
}
```

### Output

```text
Dog barks
```

**Remember:**

- Same method name.
- Same parameter list.
- Parent-child relationship.
- Child provides a new implementation.

`@Override` is an annotation that helps the compiler check that the method is actually overriding a parent method.

---

# 14. Method Overloading

### Definition

When multiple methods have the same name but different parameter lists, it is called method overloading.

### Example: Calculator

```java
class Calculator {

    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {

        Calculator c = new Calculator();

        System.out.println(c.add(10, 20));
        System.out.println(c.add(10, 20, 30));
        System.out.println(c.add(10.5, 20.5));
    }
}
```

### Output

```text
30
60
31.0
```

**Remember:**

- Same method name.
- Different number, type, or order of parameters.
- Return type alone cannot distinguish overloaded methods.

---

# 15. Encapsulation

### Definition

Encapsulation means wrapping data and methods together in a class and restricting direct access to data.

It is commonly achieved using:

- `private` variables.
- `public` getter methods.
- `public` setter methods.

### Example: Bank Account

```java
class BankAccount {

    private double balance = 5000;

    // Getter: Read balance
    public double getBalance() {
        return balance;
    }

    // Setter: Change balance
    public void setBalance(double amount) {

        if (amount >= 0) {
            balance = amount;
        }
    }

    public static void main(String[] args) {

        BankAccount account = new BankAccount();

        System.out.println("Old Balance: " + account.getBalance());

        account.setBalance(10000);

        System.out.println("New Balance: " + account.getBalance());
    }
}
```

### Output

```text
Old Balance: 5000.0
New Balance: 10000.0
```

### Understand the flow

**Step 1:**

```java
private double balance = 5000;
```

The balance is private. It cannot be accessed directly from outside the class.

**Step 2:**

```java
public double getBalance() {
    return balance;
}
```

Getter reads the private variable and returns its value.

**Step 3:**

```java
public void setBalance(double amount) {
    if (amount >= 0) {
        balance = amount;
    }
}
```

Setter receives a new value and changes the private variable after validation.

**Step 4:**

```java
account.setBalance(10000);
```

The setter changes the balance from 5000 to 10000.

**Remember:**

| Keyword / Method | Purpose               |
| ---------------- | --------------------- |
| `private`        | Protects the variable |
| Getter           | Reads the value       |
| Setter           | Changes the value     |
| `return`         | Sends a value back    |

---

# 16. Abstraction

### Definition

Abstraction means hiding implementation details and showing only essential functionality.

It can be achieved using abstract classes and interfaces.

### Example: Vehicle

```java
abstract class Vehicle {

    abstract void start();

}

class Car extends Vehicle {

    @Override
    void start() {
        System.out.println("Car starts with a key");
    }

    public static void main(String[] args) {

        Car c = new Car();

        c.start();
    }
}
```

### Output

```text
Car starts with a key
```

### Understand the flow

1. `abstract class Vehicle` creates an abstract parent class.
2. `abstract void start();` declares a method without implementation.
3. `class Car extends Vehicle` inherits the parent class.
4. `Car` provides the implementation of `start()`.
5. `c.start()` executes the Car implementation.

**Remember:**

- An abstract class cannot be instantiated directly.
- An abstract method has no body.
- A concrete child class must implement inherited abstract methods.

---

# 17. Interface

### Definition

An interface defines a contract that implementing classes agree to follow.

### Example

```java
interface Vehicle {

    void start();

}

class Car implements Vehicle {

    public void start() {
        System.out.println("Car starts with a key");
    }

    public static void main(String[] args) {

        Car c = new Car();

        c.start();
    }
}
```

### Output

```text
Car starts with a key
```

**Remember:**

- `interface` creates an interface.
- `implements` connects a class with an interface.
- Interface abstract methods are implicitly `public abstract`.
- Implemented methods must be `public`.

---

# 18. Multiple Inheritance Using Interfaces

### Definition

Java does not support multiple inheritance through classes, but a class can implement multiple interfaces.

### Example: Smartphone

```java
interface Camera {

    void takePhoto();

}

interface MusicPlayer {

    void playMusic();

}

class SmartPhone implements Camera, MusicPlayer {

    public void takePhoto() {
        System.out.println("Taking photo");
    }

    public void playMusic() {
        System.out.println("Playing music");
    }

    public static void main(String[] args) {

        SmartPhone s = new SmartPhone();

        s.takePhoto();
        s.playMusic();
    }
}
```

### Output

```text
Taking photo
Playing music
```

**Remember:**

```java
class SmartPhone implements Camera, MusicPlayer
```

One class implements two interfaces.

---

# 19. Multiple Implementations of an Interface

### Definition

Different classes can implement the same interface and provide different implementations of its methods.

### Example: Payment

```java
interface Payment {

    void pay();

}

class GooglePay implements Payment {

    public void pay() {
        System.out.println("Paid using Google Pay");
    }
}

class PhonePe implements Payment {

    public void pay() {
        System.out.println("Paid using PhonePe");
    }
}

class Main {

    public static void main(String[] args) {

        GooglePay g = new GooglePay();
        PhonePe p = new PhonePe();

        g.pay();
        p.pay();
    }
}
```

### Output

```text
Paid using Google Pay
Paid using PhonePe
```

**Remember:** Same interface, different class implementations.

---

# 20. Runtime Polymorphism

### Definition

Runtime polymorphism occurs when an overridden method is selected at runtime based on the actual object.

It is achieved through method overriding and parent-class references.

### Example: Animal

```java
class Animal {

    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {

    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {

    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

class Main {

    public static void main(String[] args) {

        Animal a;

        a = new Dog();
        a.sound();

        a = new Cat();
        a.sound();
    }
}
```

### Output

```text
Dog barks
Cat meows
```

### Understand these statements

```java
Animal a;
```

Creates a parent-class reference variable.

```java
a = new Dog();
```

The reference points to a Dog object.

```java
a.sound();
```

Java executes the Dog version of `sound()`.

Then:

```java
a = new Cat();
a.sound();
```

Java executes the Cat version.

**Remember:** The actual object determines which overridden method runs.

---

# 21. Abstract Class vs Interface

Both are used to achieve abstraction, but they have different features.

### Abstract Class

An abstract class can contain:

- Abstract methods.
- Normal methods.
- Instance variables.
- Constructors.
- Static methods.

### Example

```java
abstract class Animal {

    abstract void sound();

    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {

    void sound() {
        System.out.println("Dog barks");
    }

    public static void main(String[] args) {

        Dog d = new Dog();

        d.sound();
        d.eat();
    }
}
```

### Output

```text
Dog barks
Animal eats
```

### Interface

An interface can contain:

- Abstract methods.
- Default methods.
- Static methods.
- Private methods (Java 9+).
- Constants.

### Example

```java
interface Animal {

    void sound();

    void eat();
}

class Dog implements Animal {

    public void sound() {
        System.out.println("Dog barks");
    }

    public void eat() {
        System.out.println("Dog eats");
    }

    public static void main(String[] args) {

        Dog d = new Dog();

        d.sound();
        d.eat();
    }
}
```

### Output

```text
Dog barks
Dog eats
```

### Difference Table

| Feature              | Abstract Class                    | Interface                                   |
| -------------------- | --------------------------------- | ------------------------------------------- |
| Declaration          | `abstract class`                  | `interface`                                 |
| Inheritance keyword  | `extends`                         | `implements`                                |
| Constructors         | Yes                               | No                                          |
| Instance variables   | Yes                               | No                                          |
| Constants            | Can have them                     | Fields are implicitly `public static final` |
| Abstract methods     | Yes                               | Yes                                         |
| Normal methods       | Yes                               | Yes, using default/static/private methods   |
| Multiple inheritance | A class can extend only one class | A class can implement multiple interfaces   |

### Real-Life Example

**Abstract class: Animal**

Different animals share common features such as eating and sleeping, but each animal may make a different sound.

**Interface: Features**

A smartphone can implement multiple capabilities such as Camera, MusicPlayer and GPS.

### Important Interview Point

- Abstract class = Shared foundation and common implementation.
- Interface = Contract or capability.

---

# 22. Important OOP Keywords

| Keyword      | Meaning                                                              |
| ------------ | -------------------------------------------------------------------- |
| `class`      | Creates a class                                                      |
| `new`        | Creates an object                                                    |
| `this`       | Refers to the current object                                         |
| `static`     | Belongs to the class                                                 |
| `extends`    | Inherits a class                                                     |
| `implements` | Implements an interface                                              |
| `super`      | Refers to parent-class members                                       |
| `private`    | Restricts direct access                                              |
| `public`     | Allows access according to Java access rules                         |
| `protected`  | Allows access within the package and through subclass access         |
| `abstract`   | Declares an abstract class or method                                 |
| `final`      | Prevents reassignment, overriding, or inheritance depending on usage |

---

# 23. Quick Revision – Four Main OOP Principles

| Principle     | Meaning                                     | Java feature                |
| ------------- | ------------------------------------------- | --------------------------- |
| Encapsulation | Protecting and controlling data access      | `private`, getters, setters |
| Inheritance   | Reusing parent-class properties and methods | `extends`                   |
| Polymorphism  | One name, different behaviours              | Overloading, overriding     |
| Abstraction   | Hiding implementation details               | Abstract class, interface   |

### Types of Inheritance

1. Single inheritance – One parent, one child.
2. Multilevel inheritance – Parent, child, and grandchild.
3. Hierarchical inheritance – One parent, multiple children.
4. Multiple inheritance – Achieved through interfaces in Java.

### Types of Polymorphism

1. Compile-time polymorphism – Method overloading.
2. Runtime polymorphism – Method overriding.

---

## OOP Completion Checklist

- [ ] Class and Object
- [ ] Fields and Methods
- [ ] Constructors
- [ ] Default Constructor
- [ ] Parameterized Constructor
- [ ] `this` Keyword
- [ ] Constructor Overloading
- [ ] `static` Keyword
- [ ] Single Inheritance
- [ ] Multilevel Inheritance
- [ ] Hierarchical Inheritance
- [ ] Method Overriding
- [ ] Method Overloading
- [ ] Encapsulation
- [ ] Abstraction
- [ ] Interface
- [ ] Multiple Inheritance Using Interfaces
- [ ] Multiple Implementations
- [ ] Runtime Polymorphism
- [ ] Abstract Class vs Interface

**Next Java Topics:** `super` keyword, `final` keyword, upcasting, downcasting, association, aggregation and composition, followed by Exception Handling.

---

**Goal:** Understand each concept, type the code yourself, run it, and practise changing the values and methods. Do not just copy and memorize the programs.

