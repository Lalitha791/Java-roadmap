# Day 3 Notes – Operators in Java

## 1. What is an operator?
An operator is a symbol that performs an operation on one or more values. The values used by an operator are called operands.

```java
int a = 10;
int b = 5;
int sum = a + b;
System.out.println(sum); // 15
```

Here, `a` and `b` are operands and `+` is the operator.

## 2. Arithmetic operators
Arithmetic operators perform mathematical calculations.

| Operator | Meaning | Example (`a = 10`, `b = 3`) | Result |
|---|---|---|---:|
| `+` | Addition | `a + b` | 13 |
| `-` | Subtraction | `a - b` | 7 |
| `*` | Multiplication | `a * b` | 30 |
| `/` | Division | `a / b` | 3 |
| `%` | Remainder | `a % b` | 1 |

**Important:** When both operands are integers, `/` performs integer division and discards the fractional part. `10 / 3` is `3`, while `10.0 / 3` is approximately `3.3333`.

The modulus operator `%` is useful for checking even/odd numbers and divisibility:
```java
int number = 15;
System.out.println(number % 2); // 1
```

## 3. Relational operators
Relational operators compare values. Their result is always `true` or `false`.

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Do not confuse `=` (assignment) with `==` (equality comparison).

## 4. Logical operators
Logical operators combine or reverse boolean conditions.

| Operator | Meaning |
|---|---|
| `&&` | AND: both conditions must be true |
| `||` | OR: at least one condition must be true |
| `!` | NOT: reverses a boolean value |

Java's `&&` and `||` use short-circuit evaluation: the second condition may not be evaluated if the first condition already determines the result.

Example:
```java
int age = 20;
int marks = 75;
boolean eligible = age >= 18 && marks >= 60;
System.out.println(eligible); // true
```

## 5. Assignment operators
Assignment operators store or update a variable's value.

| Operator | Equivalent expression |
|---|---|
| `=` | `a = value` |
| `+=` | `a = a + value` |
| `-=` | `a = a - value` |
| `*=` | `a = a * value` |
| `/=` | `a = a / value` |
| `%=` | `a = a % value` |

Example:
```java
int a = 10;
a += 5; // a is now 15
a *= 2; // a is now 30
```

## 6. Unary operators: increment and decrement
- `++` increases a variable by 1.
- `--` decreases a variable by 1.

**Prefix:** `++a` changes the value first, then the expression uses the new value.

**Postfix:** `a++` uses the current value first, then increments it.

```java
int x = 5;
System.out.println(x++); // 5; x becomes 6
System.out.println(++x); // x becomes 7; prints 7
```

Use these carefully in larger expressions; separate statements are easier to read and debug.

## 7. Ternary operator
The ternary operator is a compact expression for choosing between two values.

Syntax:
```java
condition ? valueIfTrue : valueIfFalse
```

Example:
```java
int age = 20;
String result = age >= 18 ? "Eligible" : "Not eligible";
System.out.println(result);
```

## 8. Operator precedence
Precedence determines which operator is evaluated first. Parentheses can make the intended order explicit.

Example:
```java
int result = 10 + 5 * 2; // 20
int another = (10 + 5) * 2; // 30
```

Simplified order from higher to lower:
1. Parentheses
2. Unary operators (`++`, `--`, `!`, unary `+` and `-`)
3. Multiplication, division, remainder
4. Addition and subtraction
5. Relational operators
6. Equality operators
7. Logical AND (`&&`)
8. Logical OR (`||`)
9. Ternary (`?:`)
10. Assignment operators

When operators have the same precedence, associativity determines the grouping. Use parentheses rather than relying on memory when an expression is complicated.

## 9. Bitwise and shift operators – introduction
These operate on the binary representation of integral values.

- `&` bitwise AND
- `|` bitwise OR
- `^` bitwise XOR
- `~` bitwise complement
- `<<` left shift
- `>>` signed right shift
- `>>>` unsigned right shift

For this beginner lesson, focus on arithmetic, relational, logical, assignment, unary and ternary operators first.

## 10. Common mistakes
- Using `=` when you mean `==`.
- Expecting `10 / 3` to produce a decimal.
- Confusing `a++` with `++a`.
- Forgetting that `%` returns the remainder.
- Writing complex conditions without parentheses.
- Assuming `&&` and `||` always evaluate both sides.

## Quick revision
- Arithmetic: calculate.
- Relational: compare and return boolean.
- Logical: combine boolean conditions.
- Assignment: assign/update.
- Unary: operate on one operand.
- Ternary: choose one of two values.
- Precedence: controls evaluation order.
