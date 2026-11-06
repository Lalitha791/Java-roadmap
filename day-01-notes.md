# Day 1 – Introduction to Java

## 1. What is Java?
Java is a high-level, class-based, object-oriented programming language used to develop software applications. It was developed at Sun Microsystems and officially released in 1995.

### Key features
| Feature | Meaning |
|---|---|
| Simple | Familiar C-like syntax |
| Object-oriented | Organizes programs around classes and objects |
| Platform independent | Bytecode can run on compatible JVMs |
| Secure | Includes runtime security mechanisms |
| Robust | Exception handling and memory management |
| Multithreaded | Supports multiple threads |
| Portable | Uses a consistent bytecode format |
| High performance | Uses JIT compilation |

**WORA:** Write Once, Run Anywhere. Compile Java source into bytecode, then run that bytecode on a compatible JVM for the target operating system.

### Where Java is used
Banking, enterprise applications, e-commerce, backend services, payment processing and large business applications.

## 2. JDK vs JRE vs JVM

- **JVM (Java Virtual Machine):** Loads, verifies and executes Java bytecode; also manages runtime memory and garbage collection.
- **JRE (Java Runtime Environment):** Runtime components needed to run Java applications; includes the JVM and supporting libraries.
- **JDK (Java Development Kit):** Development tools and runtime components. Includes `javac`, `java`, `javadoc`, `jar` and debugging tools.

| Component | Main purpose | Compiler? |
|---|---|---|
| JDK | Develop and run Java programs | Yes |
| JRE | Run Java programs | No |
| JVM | Execute bytecode | No |

Remember: JDK = development tools; JRE = runtime environment; JVM = bytecode execution.

## 3. Java program structure

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Welcome to Java");
    }
}
```

- `public`: access modifier.
- `class`: declares a class.
- `Main`: class name.
- `{ }`: delimit a block.
- `main()`: standard application entry point.
- `System.out.println()`: displays output.
- `;`: ends a statement.

A public class name must match its filename. `Student` belongs in `Student.java`. Java is case-sensitive: `age`, `Age` and `AGE` are different identifiers.

### Naming conventions
| Element | Convention | Example |
|---|---|---|
| Class | PascalCase | `StudentDetails` |
| Variable | camelCase | `studentAge` |
| Method | camelCase | `calculateTotal()` |
| Constant | UPPER_SNAKE_CASE | `MAX_MARKS` |
| Package | lowercase | `com.example.app` |

## 4. The main() method

```java
public static void main(String[] args)
```

- `public`: accessible to the Java launcher.
- `static`: can be invoked without first creating an object.
- `void`: returns no value.
- `main`: standard entry-point method name.
- `String[] args`: array that receives command-line arguments.

Example of a second static method:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Main method");
        welcomeMessage();
    }

    public static void welcomeMessage() {
        System.out.println("Welcome to Java");
    }
}
```

Common mistakes: writing `Main` instead of `main`, omitting `static` from the standard entry point, or using `String args` instead of `String[] args`.

## 5. Variables and data types

A variable is a named storage location.

```java
int age = 22;
```

- `int`: data type
- `age`: variable name
- `22`: value
- `=`: assignment operator

Declaration: `int age;`  
Initialization: `age = 22;`  
Together: `int age = 22;`

### Naming rules
Valid: `age`, `studentAge`, `_number`, `$price`  
Invalid: `2age`, `student age`, `class` (reserved keyword).

### Eight primitive types
| Type | Size | Example |
|---|---:|---|
| `byte` | 8 bits | `byte age = 22;` |
| `short` | 16 bits | `short year = 2026;` |
| `int` | 32 bits | `int marks = 95;` |
| `long` | 64 bits | `long population = 8000000L;` |
| `float` | 32 bits | `float price = 99.5f;` |
| `double` | 64 bits | `double percentage = 85.75;` |
| `char` | 16 bits | `char grade = 'A';` |
| `boolean` | JVM-dependent representation | `boolean passed = true;` |

Use `L` for long literals when needed. Use `f` or `F` for float literals because decimal literals are `double` by default. `double` offers more precision than `float`.

`char` stores one UTF-16 code unit and uses single quotes. `String` uses double quotes.

### Reference types
Examples include `String`, arrays, classes, interfaces and enums.

```java
String name = "Lalitha";
int[] marks = {80, 90, 95};
```

A primitive variable stores a primitive value; a reference variable stores a reference to an object or array.

### Default values
Instance and static fields receive defaults. Local variables do not.

| Type | Default |
|---|---|
| `int` | `0` |
| `double` | `0.0` |
| `float` | `0.0f` |
| `char` | `\u0000` |
| `boolean` | `false` |
| Reference | `null` |

### Constants
Use `final` to prevent reassignment:

```java
final double PI = 3.14159;
```

## 6. Printing output

- `System.out.print(value)`: prints without automatically moving to the next line.
- `System.out.println(value)`: prints and moves to the next line.
- `System.out.printf(format, values)`: prints formatted output.

Common format specifiers: `%d` integer, `%f` decimal, `%.2f` decimal to two places, `%c` character, `%s` string, `%b` boolean, `%n` newline.

```java
String name = "Lalitha";
int age = 22;
double percentage = 85.567;

System.out.printf("Name: %s%n", name);
System.out.printf("Age: %d%n", age);
System.out.printf("Percentage: %.2f%n", percentage);
```

The `+` operator can concatenate strings and values:
```java
System.out.println("Age: " + age);
```

## 7. Comments
```java
// Single-line comment

/*
 Multi-line comment
*/

/**
 * Documentation comment, usable by javadoc.
 */
```
The compiler ignores comments during normal execution.

## Day 1 recap
Be able to explain Java, WORA, JDK/JRE/JVM, class and `main()`, variables, primitive/reference types, field default values versus local variables, `final`, and the three output methods.




 Difference between .java and .class?
.java	.class
Source code file	Compiled bytecode file
Written by programmer	Generated by compiler
Human-readable	Not directly human-readable
Contains Java code	Contains JVM bytecode




# Day 1 – All 15 Java Problems with Practice Links

Here are individual practice links for each problem. I've selected beginner-friendly resources where possible. Some are direct online compilers or exercise pages where you can write and run the exact program.

## Level 1 – Basic Java programs

| No. | Problem                                    | Practice link                                                                               |
| --- | ------------------------------------------ | ------------------------------------------------------------------------------------------- |
| 1   | Print Hello World                          | [Solve](https://www.programiz.com/java-programming/online-compiler/?utm_source=chatgpt.com) |
| 2   | Print your name                            | [Learn & solve](https://www.w3schools.com/java/java_output.asp?utm_source=chatgpt.com)      |
| 3   | Print name, age and city on separate lines | [Solve](https://www.programiz.com/java-programming/online-compiler/?utm_source=chatgpt.com) |
| 4   | Print Java three times using `print()`     | [Learn & solve](https://www.w3schools.com/java/java_output.asp?utm_source=chatgpt.com)      |
| 5   | Print student profile using `println()`    | [Solve](https://www.programiz.com/java-programming/online-compiler/?utm_source=chatgpt.com) |

## Level 2 – Variables and data types

| No. | Problem                               | Practice link                                                                                                     |
| --- | ------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| 6   | Declare and print integer age         | [Learn & solve](https://www.w3schools.com/java/java_variables.asp?utm_source=chatgpt.com)                         |
| 7   | Store percentage using double         | [Learn & solve](https://www.w3schools.com/java/java_data_types.asp?utm_source=chatgpt.com)                        |
| 8   | Store grade using char                | [Learn & solve](https://www.programiz.com/java-programming/variables-primitive-data-types?utm_source=chatgpt.com) |
| 9   | Store graduation status using boolean | [Learn & solve](https://www.w3schools.com/java/java_data_types.asp?utm_source=chatgpt.com)                        |
| 10  | Print multiple data types together    | [Solve](https://www.programiz.com/java-programming/online-compiler/?utm_source=chatgpt.com)                       |

## Level 3 – Static, final and methods

| No. | Problem                                 | Practice link                                                                                                     |
| --- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| 11  | Create and call static `welcome()`      | [Learn & solve](https://www.w3schools.com/java/java_class_methods.asp?utm_source=chatgpt.com)                     |
| 12  | Declare final variable PI               | [Learn & solve](https://www.w3schools.com/java/java_modifiers.asp?utm_source=chatgpt.com)                         |
| 13  | Create static `displayName()`           | [Learn & solve](https://www.programiz.com/java-programming/methods?utm_source=chatgpt.com)                        |
| 14  | Create addition and subtraction methods | [Learn & solve](https://www.programiz.com/java-programming/methods?utm_source=chatgpt.com)                        |
| 15  | Use an uninitialized local variable     | [Learn & solve](https://www.programiz.com/java-programming/variables-primitive-data-types?utm_source=chatgpt.com) |

## Best platforms to use

[CODING BCA.: 2016](https://images.openai.com/static-rsc-4/Ru09XGyLNImOS685hKCelwRp-EU4jHYcfcMF-WiiV2ofjj2ROExN3bVSfRweQnJtMQU8i_b9Wir2-T56Qz_9cV_KPtSFwWuWq5s-P7OV6-NMKQuW1RRKh1m_Xd19PC1F0orRa-yZAZq4haQYGzAefQcHbk5k0AHWIy9z7CmCiDc?purpose=inline)

1\. HackerRank

Recommended for coding practice

[Java coding challenges](https://www.hackerrank.com/domains/java?utm_source=chatgpt.com)

[Programiz Logo PNG,  Vector (AI, EPS, CDR, PDF, SVG) - iconLogoVector](https://images.openai.com/static-rsc-4/wlxfnrikn6CiB6tJdsJiAYKifk1jSrpyPkSxv6tTGDwph3Wvdqabxxlxpg943nfEgrWaPZ_YnYP-c5VfnWZxyrJUgTqdtBebJoWx396kIzOnVKoXyUSExvGf7RMRluO-SX_-DnDpmZAKmYJVGfL7YmjsvLF4uIP9NolKYTY0eJA?purpose=inline)

2\. Programiz

Best for running your first programs.

[Online Java compiler](https://www.programiz.com/java-programming/online-compiler/?utm_source=chatgpt.com)

[File:W3Schools logo.svg - Wikimedia Commons](https://images.openai.com/static-rsc-4/A-PkBbppdhGP9MPWITzjdxoCXTe8KiY2u76MJfRyzNDgFXQ77txQcpxcbV-QuWWd7CXvsXSrgSxvzBPIwpgPyvdWmq9u6XVlx0Tff4VSqhUgSth1h2rrECRO6p4vNs3uIb2t5jSKG-d0ormtPOYKHJEm4dTB16nA645_G30t1Qg?purpose=inline)

3\. W3Schools

Best for learning syntax and basic exercises.

[Java exercises](https://www.w3schools.com/java/java_exercises.asp?utm_source=chatgpt.com)

Important: Problems 1–15 are custom practice exercises, not necessarily exact questions hosted on those websites. Use the links to learn the relevant concept and write the specified program in the online compiler.

My recommendation for your Infosys preparation:

- Day 1–7: Java fundamentals.
- Day 8–15: Conditional statements and loops.
- Day 16–25: Arrays and strings.
- Day 26 onwards: OOP and DSA.

Start with Problems 1–5.
