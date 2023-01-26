# Arithmetic and Relational Operators

## Learning Goals

- Define what an operator is.
- Learn more about the assignment operator.
- Discuss the various arithmetic (math) operators.
- Introduce integer division.
- Explain relational operators.
- Define the order of precedence.

## Introduction

**Operators** are special instructions that allow us to inspect, manipulate and
assign values. As such they can operate on either variables or directly on
values.

These are the types of operators we will cover in this lesson:

- Assignment operators
- Arithmetic (i.e. math) operators
- Relational operators

## Assignment Operators

The **assignment operator** allows us to assign values to variables. As we now
know, variables are used to store values so that they can be used repeatedly
in a program. The way a value gets stored in a variable is with the assignment
operator (`=`). The left operand of the assignment operator is the variable
while the right operand is the value we want to assign to the variable. Note
that the value must be the same data type as the variable.

```java
String example = "this is a sample string"; 
```

In the above example, we are combining the variable definition `String example`
and the assignment `example = "this is a sample string"`. This does not have to
be the case. For example, we could declare the variable earlier in the program
and then initialize it later.

```java
String example; 

// some other code here

example = "another sample value for my string";  
```

## Arithmetic Operators

**Arithmetic operators** help us perform simple mathematical operations. These
operators are very similar to the arithmetic operators we may have learned in
elementary school. Consider the following table of arithmetic operators known
in Java:

| Operator | Description    |
|----------|----------------|
| `+`      | Addition       |
| `-`      | Subtraction    |
| `*`      | Multiplication |
| `/`      | Division       |
| `%`      | Modulus        |

These operators can be applied to numerical data types, like `int` and
`double`. They can also be used on `char` data types, but we will learn more
about that later on. Let's look at the addition operator to learn more on
how operators can be used within Java! But to help us, consider the following
variables when reading about each operator:

```java
int firstNumber = 20;
int secondNumber = 10;
```

- The plus symbol (`+`) is a binary operator that adds the values on
  either side of the operator. Let's look at the "expression"
  `firstNumber + secondNumber`.
    - `firstNumber + secondNumber` is an expression. An **expression** is a
      combination of operators and variables that evaluate to a single value.
    - When the computer evaluates the expression, we tend to say it "returns"
      that value.
    - Once the value is returned, it can then be used in other expressions.
    - Expressions cannot be left on its own line within the source code. If they
      are, then it will result in a compilation error. Expressions aren't a full
      instruction to the computer until its value is assigned to a variable or
      used in another expression.
    - Combining the expression with the assignment operator will provide a full
      statement: `int result = firstNumber + secondNumber;`. This is an
      instruction that the computer can understand and compile.
        - The `firstNumber` variable has the value `20`.
        - The `secondNumber` variable has the value `10`.
        - The code will take `20` and add it to `10` to return the value of `30`.
        - The variable `result` of type `int` is then declared.
        - Finally, the `result` variable is assigned to the value of `30`.
    - Note how the operators all have spaces between them and the variable
      operands. This is common stylistic syntax within Java to have spaces
      between binary operators.

Here is the full list of Java arithmetic operators, including the `+` operator
again, so we have an easy place to look them all up:

- `+` is a binary operator that adds values on either side of the operator:
  `firstNumber + secondNumber` returns `30`.
- `-` is a binary operator that subtracts the right-hand operand from the
  left-hand operand: `firstNumber - secondNumber` returns `10`.
- `*` is a binary operator that multiplies the values on either side of the
  operator: `firstNumber * secondNumber` returns `200`.
- `/` is a binary operator that divides the left-hand operand by the right-hand
  operand: `firstNumber / secondNumber` return `2`.
    - We will talk about integer division shortly.
- `%` is the modulus operator (or mod for short). It is a binary operator that
  returns the remainder value of dividing two numbers:
    - `firstNumber % secondNumber` returns `0` because 20 divided by 10 is an
      even 2 with a remainder of 0.

### Integer Division

Before we move on from arithmetic operators, we want to mention the division
operator again.

We know that not all whole numbers can be divided evenly. For example, 1 / 3 is
an irrational number. Or even 7 / 4 would result in 1.75, or a `double` if
doing the math with pencil and paper. In Java, we now know that `1 / 3` or
`7 / 4` is an expression that cannot exist on its own. It _must_ result in the
assignment to a variable with a data type.

Consider this program:

```java
public class Main {
    public static void main(String[] args) {
        double result = 7 / 4;
        System.out.println(result);
    }
}
```

Now again, we know that 7 / 4 = 1.75. And since we are assigning the result of
this expression to a `double` data type, we may think that the program will
print out `1.75`.

Instead, the program prints out `1.0`. What just happened here?

**Integer division** is division in which the decimal part is discarded or
removed. We can perform integer division when we have two `int` data types being
divided. Just like in this example!

This is sometimes useful; however, what if we wanted 1.75 to be assigned to
`result` instead of 1.0? We can perform real division by making the numbers
`doubles` instead of `ints`:

```java
package org.example;

public class Main {
    public static void main(String[] args) {
        double result = 7.0 / 4.0;
        System.out.println(result);
    }
}
```

Now when we run the program, it will print out `1.75`.

## Relational Operators

Let's say we would like to compare two values to each other. Are there any
operators that exist for that? The answer is yes!

**Relational operators** are operators that are available in Java that allow
us to perform comparisons against two values. Like the arithmetic operators,
these operators will apply to numerical data types and the `char` data type.
Consider the following table of relational operators known in Java:

| Operator | Description           |
|----------|-----------------------|
| `==`     | Equal                 |
| `!=`     | Not Equal             |
| `>`      | Greater Than          |
| `<`      | Less Than             |
| `>=`     | Greater Than or Equal |
| `<=`     | Less Than or Equal    |

We can now use this table of relational operators to help us with comparisons!
Note that all of these operators are binary operators - this means they require
two values on either side of the operator. For example:
`firstNumber > secondNumber`. Relational operators will also always return a
**boolean** value. This means that it will either return a true or false
value. Similarly, expressions that can only evaluate to either true or false
are called **boolean expressions**. So `firstNumber > secondNumber` would be a
boolean expression, and it would return a value of true. We could store the value
in a boolean variable as well:

```java
boolean isLarger = firstNumber > secondNumber;
```

## Combining Operators

Multiple operators can be combined in a single statement:

```java
int firstNumber = 20;
int secondNumber = 10;

int result = firstNumber * 10 + secondNumber * 2; 
```

In this example, `result` will have a value of `(20 * 10) + (10 * 2)`, which is
`220`.

Note the parentheses with the expressions `20 * 10` and `10 * 2`. These were
grouped together with parentheses to show that the multiplication will evaluate
first when the computer executes this statement. This is because Java
follows the order of operations precedence. If no parentheses are specified,
the order of precedence will be the default:

1. Postfix: `++` and `--`
2. Multiplicative: `*`, `/` and `%`
3. Additive: `+` and `-`
4. Assignment: `=`

It is recommended to always be explicit about the precedence desired. It makes
the code more readable and more maintainable:

```java
int result = (firstNumber * 10) + (secondNumber * 2); 
```

## Conclusion

Operators are special instructions that allow us to inspect, manipulate and
assign values. As such they can operate on either variables or directly on
values.

In this lesson, we have discussed several types of operators, how to use them,
and the order of precedence when expressions are combined.

In the next lesson, we'll look at these operators again while also discussing
expressions and statements.

## Resources

- [Wolfram Math World: Integer Division](https://mathworld.wolfram.com/IntegerDivision.html)
- [Integer Division in Java](https://www.cs.umd.edu/~clin/MoreJava/Intro/expr-int-div.html#:~:text=Java%20does%20integer%20division%2C%20which,can%20come%20in%20very%20handy.)
