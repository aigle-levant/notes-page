---
layout: post
title: JS - Operators
categories: [JS]
---

How about we make an illusion of choice in JS...

* Table of content
{:toc}

## Operators

Just like every other language, JS has operators that deal with operands during an operation.

### Comparison operators

These operators return either `true` or `false` when dealing with operands.

```js
let a = "True";
let b = "False";
let c = "true" == "True";

console.log(2>1); //true
console.log(a>b); //true
console.log(c); //false
```

The third output is the reason why programs, websites, etc. often have measures to deal with uppercase or lowercase input.

#### String comparison

While comparing 2 strings, JS pulls out a dictionary [actually called the lexicographical order] to check out their Unicode [previously ASCII] values letter-by-letter.

* If one string is longer than the other, that string is treated as the greater one.
* If both the strings have the same letters and are of equal length, they're equal.

For instance, let's compare 'True' and 'true' :

```md
T -> 84, t -> 116
> First letter of 'true' greater than 'True'
> Lengths are the same

> 'true' is greater than 'True'
```

#### Comparing different types

When encountering operands of different types, JS converts the values to numbers :

```js
console.log("The Nights" > 1); //false
console.log("21">20); //true
```

In the first example, the first letter 'T' is compared with the number. We find out that its position is lesser than 1 and return `false`.

Let's try Boolean values...

```js
console.log(true == 1); //true
console.log(false == 1); //false
console.log(false == 0); //true
```

So `true` is 1 and `false` is 0. It makes sense if you think of them in terms of binary; like the lights in a transistor that flicker on or off to show a value.

Now let me compare the number 0 with boolean `true` and `false` :

```js
console.log(false == 0); //true
console.log(true == 0); //false
console.log(false == ""); //true
```

We have a problem at hand - the operator doesn't differentiate the number 0 [and the empty string] from its boolean equivalent `false`.

#### JS' special operator `===`

JS uses another variety of equality to deal with this problem; it's called the strict equality operator `===` and it checks equality and type of operands.

```js
console.log(0===false); //false
console.log(""===false); //false
```

Now that it checks equality as well as type, both return false.

The similar equivalent of `!=` is `!==`

```js
console.log(0!==true); //true
```

#### Comparing `null` and `undefined`

`null` and `undefined`, when compared using other operators, are converted to 0 and `NaN` respectively before comparison. Obviously, they return false :

```js
console.log(null>undefined); //false
```

Same goes for the triple equality :

```js
console.log(null===undefined); //false
```

But when we use `==`, we get a strange result :

```js
console.log(null==undefined); //true
```

They are weird in the sense, they are equal only if we use equality operator on them. Never otherwise.

Now let's experiment using `null` and `undefined`

#### Comparing `null` and 0

When we compare `null` and 0, we get even stranger results :

```js
console.log(null==0); //false
console.log(null<=0); //true
console.log(null>0); //false
```

Remember that `null` will always be equal to `undefined` alone and nothing else. Hence it fails the equality check.

In the other operators, `null` is converted to the number 0 and treated as such. Hence the 2nd one returns true.

#### Comparing `undefined` and 0

```js
console.log(undefined==0); //false
console.log(undefined<=0); //false
console.log(undefined>0); //false
```

Like we said before, `undefined` is equal to only `null`; it fails the equality check.

During comparison, `undefined` is converted to the number `NaN` [ironically it means Not a Number]. This number returns false for anything it's compared with and so, we get that result.

### Logical operators

These allows us to test multiple conditions at the same time without writing a lot of `if` statements.

There are 3 logical operators :

#### AND

It's represented by `&&` and returns true only if all the expressions chained by it evaluate to true :

```js
const a = ["Live in the Moment", "My Type"];

if (a.includes("My Type") && a.includes("Paint My Soul"))
{
    console.log("Yes");
}
else
{
    console.log("No");
}
//No
```

#### OR

It's represented by `||` and returns true if either of the expressions evaluate to true :

```js
if (a.includes("My Type") || a.includes("Paint My Soul"))
{
    console.log("Yes");
}
//Yes
```

#### NOT

It's represented by `!`. It converts the expression to a boolean value and inverts it :

```js
//this means array a doesn't include "My Type"
if (!(a.includes("My Type")))
{
    console.log("Yes");
}
else
{
    console.log("No");
}
//No
```

A double NOT `!!` simply converts the expression to a boolean value; no reversion or anything.
