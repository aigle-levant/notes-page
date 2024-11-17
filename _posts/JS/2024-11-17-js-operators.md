---
layout: post
title: JS - Operators
categories: [JS]
---

Let's learn about operators...

* Table of content
{:toc}

## Addition operator

If we use the addition operation on a number and a string, they get concatenated :

```js
let x = 10;
let strung = "Hello";

console.log(x + strung); //10Hello
```

### JS is a weakly typed language

It allows implicit type-conversion [as seen here with concatenation of number and string] when we have an operation with different types.

And yes, no `TypeError`s are involved.

```js
let x = 10;
let y = 10;
let strung = "Hello";

console.log(x + y + strung); //20Hello, not 1010Hello
console.log(strung + x + y); //Hello1010, not 20Hello
```

In the second example, we get this unusual predicament. This happens because the compiler, after encountering a string, assumes the rest of the operands as string as well.

If you ask me why, this is how JS works. Quite a quirky language, this one.

```js
let x = -2;
let y = '10';

console.log(x + y); //-210
```

```js
let x = -2;
let y = '10';

console.log(x - y); //-12
console.log(y - x); //12, because -(-2) = +2
```

Except for addition operator, the rest of the arithmetic operators will convert their operands to numbers before operation.

### Unary +

JS also has the unary version of + operator.

```js
console.log(+true); //1
console.log(+""); //0
```

The second one's 0 as the string is empty [as in, empty strings are false] and false equals 0.

## Converting strings to numbers

Very often, we receive string input from HTMl forms. We'll need to convert them to numbers in order to return the correct output.

```js
let ride = "21";
let or = "22";
let die = "23";

console.log(+ride + +die + +or); //66
```

Adding a + symbol before the string variable converts it into a number.

Now let's change values and see what output we get :

```js
let ride = "ladies and gentlemen"; //NaN
let or = "2.3"; //47.3
let die = 23; //66
let ride = "21 Pilots"; //no output
```

In the 1st example, we get `NaN` when we try to convert an actual string to number. This is because we *cannot* convert it into an actual number by normal means.

Same goes for the last example. It returns no output as the compiler's confused at whether to treat it as a string or number.

There's an alternate way to convert :

```js
console.log(Number(ride) + Number(or) + Number(die));
```

> If you try ``console.log(Number(ride+or+die));`` instead, it returns the concatenated version of the variables

```js
let x = 1;
let y = 2;

let z = 77 / (x = y + 2 - 1);
//77 / 3

console.log(z); //25.666666666666668
```

## Comma operator

Consider the following code :

```js
let a = (1 + 2, 3 + 4);

console.log(a); //7
console.log(1 + 2, 3 + 4); //3, 7
```

## Comparison operators

The program returns only the 2nd expression. This is because when we use the comma operator, only the result of the last expression is returned [which, in this case, is the 2nd one].

JS has a special comparison operator `===`. It's used to evaluate if two operands have the same value and same type. Its opposite is `!==`.

```js
let a = 10;
let b = "Bye!";
let c = 20;

console.log(a===b); //false
console.log(a===c); //true
console.log(c!==b); //false
```