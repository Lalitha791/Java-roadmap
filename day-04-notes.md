# Day 4 – Java Conditional Statements

Today we’ll learn how to make Java programs take decisions using conditions. This is an important topic for Infosys assessments and coding problems.

Day 4

Core Java

Today's learning order:

1. `if` statement
2. `if-else` statement
3. `else-if` ladder
4. Nested `if`
5. Ternary operator revision
6. Coding practice and assessment questions

## 1. What are conditional statements?

Imagine a program that checks whether a person is eligible to vote.

- If age is 18 or above → Eligible.
- Otherwise → Not eligible.

Java uses conditional statements to execute different blocks of code depending on whether a condition is `true` or `false`.

## 2. The `if` statement

Use `if` when you want to execute code only when a condition is true.

Syntax

```
if (condition) {
    // Executes only if condition is true
}
```

Example

```
public class Main {
    public static void main(String[] args) {
        int age = 20;

        if (age >= 18) {
            System.out.println("Eligible to vote");
        }
    }
}
```

How it works:

1. `age` contains `20`.
2. Java checks `age >= 18`.
3. The condition is `true`.
4. Java executes the print statement.

Output:

```
Eligible to vote
```

If age is 15, the condition is false, so nothing is printed.

## 3. The `if-else` statement

Use `if-else` when you have two possible outcomes.

Syntax

```
if (condition) {
    // Executes if true
} else {
    // Executes if false
}
```

Example: Even or Odd

```
public class Main {
    public static void main(String[] args) {
        int number = 7;

        if (number % 2 == 0) {
            System.out.println("Even");
        } else {
            System.out.println("Odd");
        }
    }
}
```

Output:

```
Odd
```

Understand the logic:

- `%` gives the remainder.
- An even number divided by 2 has remainder `0`.
- An odd number divided by 2 has remainder `1` or `-1`.

## 4. The `else-if` ladder

Use this when you need to check multiple conditions.

Example: Student Grade

```
public class Main {
    public static void main(String[] args) {
        int marks = 85;

        if (marks >= 90) {
            System.out.println("Grade A");
        } else if (marks >= 80) {
            System.out.println("Grade B");
        } else if (marks >= 70) {
            System.out.println("Grade C");
        } else if (marks >= 50) {
            System.out.println("Grade D");
        } else {
            System.out.println("Fail");
        }
    }
}
```

Output:

```
Grade B
```

Important: Java checks conditions from top to bottom. Once it finds the first true condition, it executes that block and skips the remaining conditions.

For marks `85`:

- `85 >= 90` → false
- `85 >= 80` → true → prints Grade B
- Remaining conditions are skipped.

## 5. Nested `if`

An `if` statement inside another `if` statement is called a nested `if`.

Example: Login validation

```
public class Main {
    public static void main(String[] args) {
        boolean usernameCorrect = true;
        boolean passwordCorrect = true;

        if (usernameCorrect) {
            if (passwordCorrect) {
                System.out.println("Login successful");
            } else {
                System.out.println("Incorrect password");
            }
        } else {
            System.out.println("Incorrect username");
        }
    }
}
```

Output:

```
Login successful
```

The inner `if` is checked only when the outer `if` condition is true.

## 6. Difference between conditional statements

| Statement   | When to use it                       |
| ----------- | ------------------------------------ |
| `if`        | One condition                        |
| `if-else`   | Two possible outcomes                |
| `else-if`   | Multiple conditions                  |
| Nested `if` | A condition inside another condition |

## 7. Common mistakes to avoid

Mistake 1: Using `=` instead of `==`

```
int number = 10;

if (number == 10) {  // Correct: comparison
    System.out.println("Ten");
}
```

`=` assigns a value. `==` compares two values.

Mistake 2: Adding a semicolon after `if`

```
if (age >= 18); {  // Incorrect
    System.out.println("Eligible");
}
```

The semicolon ends the `if` statement. Don't add it after the condition.

Mistake 3: Wrong order in grade conditions

```
if (marks >= 50) {
    System.out.println("Pass");
} else if (marks >= 90) {
    System.out.println("Excellent");
}
```

For 95, Java prints `Pass` because the first condition is already true. Put more specific or higher ranges first.

## 8. Practice programs

Try these yourself before checking solutions.

| No. | Problem                                              | Level      |
| --- | ---------------------------------------------------- | ---------- |
| 1   | Check whether a number is positive or negative       | Easy       |
| 2   | Check whether a number is even or odd                | Easy       |
| 3   | Find the largest of two numbers                      | Easy       |
| 4   | Find the largest of three numbers                    | Easy       |
| 5   | Check voting eligibility using age                   | Easy       |
| 6   | Check whether a year is a leap year                  | Medium     |
| 7   | Assign a grade based on marks                        | Medium     |
| 8   | Check whether a character is a vowel or consonant    | Medium     |
| 9   | Check whether a number is divisible by both 5 and 11 | Medium     |
| 10  | Calculate electricity bill using unit ranges         | Assessment |

### Problem 6: Leap year – understand the logic

A year is a leap year when:

- It is divisible by 400, OR
- It is divisible by 4 but NOT divisible by 100.

```
int year = 2024;

if (year % 400 == 0) {
    System.out.println("Leap Year");
} else if (year % 100 == 0) {
    System.out.println("Not a Leap Year");
} else if (year % 4 == 0) {
    System.out.println("Leap Year");
} else {
    System.out.println("Not a Leap Year");
}
```

Output: `Leap Year`

## 9. Infosys-style assessment quiz

Try answering without running the code first.

5-question quiz

0/5 answered

1\. What is the output?

int x = 10;\
if (x > 5) {\
&#x20;   System.out.println("A");\
} else {\
&#x20;   System.out.println("B");\
}

A

B

A B

No output



2\. What is the output?

int x = 5;\
if (x > 10)\
&#x20;   System.out.println("A");\
else if (x > 3)\
&#x20;   System.out.println("B");\
else\
&#x20;   System.out.println("C");

A

B

C

No output



3\. Which operator checks equality?

\=

\==

!=

<=



4\. What happens after the first true condition in an else-if ladder?

All conditions execute

Only the next condition executes

Its block executes and the rest are skipped

Program stops with an error



5\. Which is the correct leap-year condition?

year % 4 == 0 only

year % 400 == 0 || (year % 4 == 0 && year % 100 != 0)

year % 100 == 0

year % 2 == 0



Submit answers

## 10. Practice links – solve online

These are for solving, not just reading explanations.

1. [HackerRank – Java If-Else](https://www.hackerrank.com/challenges/java-if-else/problem?utm_source=chatgpt.com)
2. [CodingBat – Java Logic Problems](https://codingbat.com/java?utm_source=chatgpt.com)
3. [GeeksforGeeks – Java Programming Practice](https://www.geeksforgeeks.org/explore?page=1\&category=Java\&utm_source=chatgpt.com)
4. [Programiz – Java Online Compiler](https://www.programiz.com/java-programming/online-compiler/?utm_source=chatgpt.com)

## 11. Your Day 4 assignment

Before moving to Day 5, try to complete:

- Understand `if`, `if-else`, `else-if`.
- Understand nested `if`.
- Solve at least 5 of the 10 coding problems.
- Complete the 5-question quiz.
- Run your programs and check their outputs.

Interview questions to prepare:

1. What are conditional statements in Java?
2. Difference between `if-else` and `else-if`?
3. What is nested `if`?
4. Can we write an `if` statement without `else`?
5. What happens if multiple conditions in an `else-if` ladder are true?
6. Difference between `&&` and `||`?
7. When should we use a ternary operator instead of `if-else`?

1\. What happens if multiple conditions in an `else-if` ladder are true?

Only the first true condition is executed. The remaining conditions are skipped.

2\. When should we use a ternary operator instead of `if-else`?

Use a ternary operator for simple conditions when choosing between two values. Use `if-else` for complex conditions or multiple statements.
