# Day 2 Notes – Type Casting, Constants and Type Promotion

## 1. What is type casting?
Type casting means converting a value from one data type to another.

## 2. Widening casting (automatic)
A smaller compatible type is converted to a larger type automatically.

```java
int number = 25;
double result = number;
```
The value becomes `25.0`. Widening generally does not lose information.

Common direction: `byte → short → int → long → float → double` (also `char → int`).

## 3. Narrowing casting (manual)
A larger type is converted to a smaller type using an explicit cast.

```java
double price = 56.89;
int result = (int) price; // 56
```
The fractional part is discarded; this is not rounding. Narrowing can lose information.

## 4. The final keyword
Use `final` when a variable must not be reassigned.

```java
final double PI = 3.14159;
```
After initialization, assigning another value to `PI` causes a compilation error.

## 5. Type promotion
In arithmetic expressions, `byte`, `short` and `char` are generally promoted to `int`.

```java
byte a = 10;
byte b = 20;
int sum = a + b;
```
The expression `a + b` has type `int`, so assigning it directly to a `byte` is not allowed without a cast.

## 6. Remember
- Widening: automatic conversion to a wider compatible type.
- Narrowing: explicit conversion; data may be lost.
- Casting `double` to `int` truncates the decimal part.
- `final` prevents reassignment.
- Arithmetic with `byte`, `short` and `char` usually produces an `int`.
- `int / int` performs integer division. Use `double` if you need a decimal result.
