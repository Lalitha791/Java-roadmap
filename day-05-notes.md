# Day 5 – Java Switch Statement                                              Day 5  Core Java  2 hours

Today's topic is `switch`, `case`, `break`, and `default`. This is important for Java coding assessments and output-prediction questions.

## 1. What is a switch statement?

A `switch` statement is used when we need to select one option from multiple possible choices.

Example: Suppose a user enters a number from 1 to 7, and the program prints the corresponding day.

Instead of writing many `if-else` conditions, we can use `switch`.

## 2. Switch syntax

```
switch (expression) {
    case value1:
        // Statements
        break;

    case value2:
        // Statements
        break;

    default:
        // If no case matches
}
```

Understand each keyword:

| Keyword   | Meaning                       |
| --------- | ----------------------------- |
| `switch`  | Checks the expression         |
| `case`    | Matches a particular value    |
| `break`   | Exits the switch              |
| `default` | Executes when no case matches |

## 3. First Java program – Day of the week

```
public class Main {
    public static void main(String[] args) {

        int day = 3;

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;

            case 2:
                System.out.println("Tuesday");
                break;

            case 3:
                System.out.println("Wednesday");
                break;

            case 4:
                System.out.println("Thursday");
                break;

            default:
                System.out.println("Invalid day");
        }
    }
}
```

Output:

```
Wednesday
```

Execution flow:

1. `day = 3`.
2. Java checks each case.
3. `case 3` matches.
4. Prints `Wednesday`.
5. `break` exits the switch.

## 4. Why do we use break?

`break` stops execution of the switch statement.

Example without `break`:

```
int number = 2;

switch (number) {
    case 1:
        System.out.println("One");

    case 2:
        System.out.println("Two");

    case 3:
        System.out.println("Three");

    default:
        System.out.println("Default");
}
```

Output:

```
Two
Three
Default
```

Why?

Because without `break`, Java continues executing the statements in the following cases. This is called fall-through.

With `break` after `case 2`, only `Two` would be printed.

## 5. Default case

The `default` block executes when none of the cases match.

```
int number = 10;

switch (number) {
    case 1:
        System.out.println("One");
        break;

    case 2:
        System.out.println("Two");
        break;

    default:
        System.out.println("Invalid number");
}
```

Output:

```
Invalid number
```

Remember: `default` is optional, but it is good practice to include it.

## 6. Switch with Scanner

Let's take input from the user.

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int number = sc.nextInt();

        switch (number) {
            case 1:
                System.out.println("One");
                break;

            case 2:
                System.out.println("Two");
                break;

            case 3:
                System.out.println("Three");
                break;

            default:
                System.out.println("Invalid number");
        }

        sc.close();
    }
}
```

Input:

```
2
```

Output:

```
Two
```

## 7. Multiple cases with the same output

You can group multiple cases when they should execute the same statement.

```
int day = 6;

switch (day) {
    case 1:
    case 7:
        System.out.println("Weekend");
        break;

    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
        System.out.println("Weekday");
        break;

    default:
        System.out.println("Invalid day");
}
```

Output:

```
Weekday
```

Notice that cases 2–6 share the same output.

## 8. Switch with String

Java also supports String values in switch statements.

```
String name = "Java";

switch (name) {
    case "Java":
        System.out.println("Programming language");
        break;

    case "Python":
        System.out.println("Python language");
        break;

    default:
        System.out.println("Unknown language");
}
```

Output:

```
Programming language
```

## 9. Switch vs if-else

| Switch                            | If-else                                         |
| --------------------------------- | ----------------------------------------------- |
| Best for matching specific values | Best for checking ranges and complex conditions |
| Uses `case`                       | Uses conditions                                 |
| Supports `break`                  | Does not need `break`                           |
| Has `default`                     | Has `else`                                      |

Important: Traditional Java switch supports `byte`, `short`, `char`, `int`, their wrapper types, `String`, and enums. It does not directly support `long`, `float`, `double`, or `boolean`.

## 10. Day 5 coding assignments

Try these in your Java compiler.

| No. | Problem                                      | Level      |
| --- | -------------------------------------------- | ---------- |
| 1   | Print day name using number 1–7              | Easy       |
| 2   | Print month name using number 1–12           | Easy       |
| 3   | Create a calculator using `+`, `-`, `*`, `/` | Easy       |
| 4   | Check vowel using switch                     | Easy       |
| 5   | Create a menu-driven area calculator         | Medium     |
| 6   | Display weekday or weekend                   | Medium     |
| 7   | Create a simple ATM menu                     | Medium     |
| 8   | Create a food ordering menu                  | Assessment |

### Example: Calculator using switch

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int a = sc.nextInt();

        System.out.print("Enter second number: ");
        int b = sc.nextInt();

        System.out.print("Enter operator: ");
        char op = sc.next().charAt(0);

        switch (op) {
            case '+':
                System.out.println(a + b);
                break;

            case '-':
                System.out.println(a - b);
                break;

            case '*':
                System.out.println(a * b);
                break;

            case '/':
                if (b != 0) {
                    System.out.println(a / b);
                } else {
                    System.out.println("Cannot divide by zero");
                }
                break;

            default:
                System.out.println("Invalid operator");
        }

        sc.close();
    }
}
```

## 11. Infosys-style assessment questions

Q1. What happens if we don't use `break` in a switch statement?

Answer: Execution falls through to the following cases until a break or the end of the switch is reached.

Q2. Is default mandatory in switch?

Answer: No, default is optional.

Q3. Can we use String in switch?

Answer: Yes, Java supports String in switch statements.

Q4. Can we use duplicate case values?

Answer: No, duplicate case values are not allowed.

Q5. Can switch work with double?

Answer: No, traditional Java switch does not support double.

## 12. Your Day 5 practice checklist

- Understand `switch` and `case`.
- Understand `break` and `default`.
- Understand fall-through.
- Practice multiple cases.
- Write the calculator program.
- Solve at least 5 assignments.

