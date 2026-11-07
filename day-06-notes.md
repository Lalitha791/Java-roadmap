# Day 6 – Java Loops              Core Java · Week 1

## 1. What is a loop?

A loop is used to execute a block of code repeatedly until a specified condition becomes false.

Why use loops?

- Avoid writing repetitive code.
- Reduce code duplication.
- Automate repeated tasks.
- Useful in number problems, arrays, patterns and DSA.

## 2. Types of loops in Java

Java has three main loops:

| Loop       | When to use                           |
| ---------- | ------------------------------------- |
| `for`      | When number of iterations is known    |
| `while`    | When iterations depend on a condition |
| `do-while` | When code must execute at least once  |

## 3. For loop

Definition: Executes statements repeatedly while the condition is true.

Syntax:

```
for(initialization; condition; update) {
    // statements
}
```

Execution order:

1. Initialization – executes once.
2. Condition – checks before every iteration.
3. Body – executes if condition is true.
4. Update – changes the variable.
5. Repeats until condition becomes false.

## 4. While loop

Definition: Executes statements as long as the condition is true.

Syntax:

```
while(condition) {
    // statements
}
```

- Entry-controlled loop.
- Condition is checked before execution.
- May execute zero times.
- Initialization and update are handled separately.

## 5. Do-while loop

Definition: Executes the code first and checks the condition afterward.

Syntax:

```
do {
    // statements
} while(condition);
```

- Exit-controlled loop.
- Executes at least once.
- Semicolon after `while(condition)` is compulsory.

## 6. Difference between loops

| Feature           | For               | While               | Do-while               |
| ----------------- | ----------------- | ------------------- | ---------------------- |
| Type              | Entry-controlled  | Entry-controlled    | Exit-controlled        |
| Condition         | Before            | Before              | After                  |
| Minimum execution | 0                 | 0                   | 1                      |
| Initialization    | In loop header    | Before loop         | Before loop            |
| Best for          | Known repetitions | Unknown repetitions | At least one execution |

## 7. Nested loops

A loop inside another loop is called a nested loop.

- Outer loop controls rows.
- Inner loop controls columns.
- Inner loop completes all iterations for each outer iteration.

Example applications:

- Star patterns.
- Number patterns.
- Matrix operations.
- 2D arrays.

## 8. Break statement

`break` terminates the nearest enclosing loop immediately.

Use: Stop execution when a particular condition is satisfied.

## 9. Continue statement

`continue` skips the remaining statements in the current iteration and moves to the next iteration.

Use: Skip specific values without terminating the loop.

## 10. Important loop concepts

| Concept        | Meaning                                   |
| -------------- | ----------------------------------------- |
| Initialization | Starting value                            |
| Condition      | Determines whether loop executes          |
| Update         | Changes loop variable                     |
| Iteration      | One complete execution of loop body       |
| Infinite loop  | Loop that never terminates                |
| Counter        | Variable used to count iterations         |
| Accumulator    | Variable used to calculate running totals |
| Nested loop    | Loop inside another loop                  |

## 11. Important formulas and operators

| Operator | Meaning        |
| -------- | -------------- |
| `i++`    | Increment by 1 |
| `i--`    | Decrement by 1 |
| `i += 2` | Increase by 2  |
| `%`      | Remainder      |
| `/`      | Division       |
| `*`      | Multiplication |

Common applications:

- Sum of numbers: `sum = sum + i`
- Product: `fact = fact * i`
- Even number: `i % 2 == 0`
- Odd number: `i % 2 != 0`
- Reverse counting: `i--`

## 12. Time complexity of loops

| Loop structure                     | Time complexity |
| ---------------------------------- | --------------- |
| Single loop N times                | O(n)            |
| Two nested loops N times each      | O(n²)           |
| Three nested loops N times each    | O(n³)           |
| Loop dividing value by 2 each time | O(log n)        |

## 13. Common interview questions

1. What is a loop in Java?
2. What are the three types of loops?
3. What is an entry-controlled loop?
4. What is an exit-controlled loop?
5. Difference between `for` and `while`?
6. Why does do-while execute at least once?
7. What is an infinite loop?
8. What is a nested loop?
9. Difference between break and continue?
10. Can we omit initialization in a for loop?
11. Can we write a for loop without a condition?
12. What is the time complexity of nested loops?

## 14. Complete Java code – All loop concepts

One program covering `for`, `while`, `do-while`, nested loops, `break` and `continue`.

```
public class Main {
    public static void main(String[] args) {

        // 1. FOR LOOP
        System.out.println("For Loop:");
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }

        // 2. WHILE LOOP
        System.out.println("While Loop:");
        int j = 1;
        while (j <= 5) {
            System.out.println(j);
            j++;
        }

        // 3. DO-WHILE LOOP
        System.out.println("Do-While Loop:");
        int k = 1;
        do {
            System.out.println(k);
            k++;
        } while (k <= 5);

        // 4. NESTED LOOP
        System.out.println("Nested Loop:");
        for (int i = 1; i <= 3; i++) {
            for (int m = 1; m <= 3; m++) {
                System.out.print("* ");
            }
            System.out.println();
        }

        // 5. BREAK
        System.out.println("Break:");
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                break;
            }
            System.out.println(i);
        }

        // 6. CONTINUE
        System.out.println("Continue:");
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                continue;
            }
            System.out.println(i);
        }
    }
}
```

## Day 6 – Revision checklist

- Understand all three loops.
- Understand execution flow.
- Learn nested loops.
- Understand break and continue.
- Practise dry runs.
- Solve 8–10 loop coding problems.
- Revise time complexity.

