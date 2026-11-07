# Day 3 Assessment Questions

Try these before checking the notes or running code.

## Output prediction

**Q1**
```java
int a = 10;
int b = 3;
System.out.println(a % b);
```

**Q2**
```java
int x = 5;
System.out.println(x++);
System.out.println(++x);
```

**Q3**
```java
System.out.println(10 + 5 * 2);
```

**Q4**
```java
int a = 10;
a += 5;
a *= 2;
System.out.println(a);
```

**Q5**
```java
System.out.println(true && false);
```

## Concept questions
6. Which operator checks equality?
7. What is the difference between `=` and `==`?
8. What is the difference between `&&` and `||`?
9. What is the difference between prefix and postfix increment?
10. What is the result type of a relational expression?
11. What does `%` return?
12. Why does `10 / 3` produce `3` in Java?
13. What does the ternary operator do?
14. Which has higher precedence: `*` or `+`?
15. What is short-circuit evaluation?

## Answer key
1. `1`
2. `5`, then `7`
3. `20`
4. `30`
5. `false`
6. `==`
7. Assignment versus equality comparison.
8. AND requires both true; OR requires at least one true.
9. Prefix updates before use; postfix uses the old value before updating.
10. `boolean`
11. The remainder.
12. Both operands are integers, so integer division is performed.
13. Selects one of two expressions based on a condition.
14. `*`
15. Evaluation stops when the result is already determined.
