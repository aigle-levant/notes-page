---
layout: post
title: JS - Strings
categories: [JS]
---

Let's handle strings in JavaScript...

* Table of content
{:toc}

## Strings

We can wrap our strings in either double quotes [""], single quotes [''] or backticks [``].

```js
let one = "One";
let two = 'Two';
let three = `Three`;
```

Strings declared using backticks [or grave keys] are called template literals. You can declare them in multiple lines.

```js
let text = `Take me to church 
I shall worship like a dog 
At the shrine of your lies 
I'll tell you my sins 
So you can sharpen your knife 
Offer me that deathless death 
Good God, let me give you my life `;
```

> Strings are immutable; they can't be changed, only be replaced.

### Including quotes in strings

We can't normally include quotes like this in JS :

```js
let quote = ""The Artist is the creator of beautiful things..." was a quote by Oscar Wilde.";
```

Notice how the highlighting goes off? This is because the language's getting confused as to how to highlight stuff out. A solution to this is use the other variety of quotes :

```js
let quote = '"The Artist is the creator of beautiful things..." was a quote by Oscar Wilde.';

let quote = `"The Artist is the creator of beautiful things..." was a quote by Oscar Wilde.`;
```

Another solution would be to use escape characters to escape the problem :

```js
let quote = "\"The Artist is the creator of beautiful things...\" was a quote by Oscar Wilde.";
```

### Type conversion

Type conversion is as easy as breathing in JS. You define a variable and use the suitable type converting function for it.

```js
let stringIsStrung = "123456";

console.log(typeof stringIsStrung); //string

stringIsStrung = Number(stringIsStrung);
console.log(typeof stringIsStrung); //number

stringIsStrung = String(stringIsStrung);
console.log(typeof stringIsStrung); //string
```

You can even convert types that are unlikely to be that type. Just that, if you decide to return it the output will be `NaN` as type is incompatible.

```js
let stringIsStrung = "What";

stringIsStrung = Number(stringIsStrung);
console.log(typeof stringIsStrung); //number
console.log(stringIsStrung); //NaN
```

### String operations

#### Length of a string

Let's try finding out the length of the lyrics.

```js
console.log(text + '\n\nLength of the string is: ' + text.length);
//Length of the string is: 187
```

#### Retrieving characters

We use `charAt()` to retrieve a character [a single letter or some other symbol] from our string.

```js
let text = `Gotta slow up, gotta shake this high
Gotta take a minute just to ease my mind
'Cause if I don't walk, then I get caught out
And I'll be falling all the way down`;

console.log(text.charAt(23)); //a
console.log(text.charAt(34)); //g
```

We have another similar method : `at()`. The difference is this method allows negative index unlike `charAt()`.

```js
let a = "Don't leave me hangin'";
let b = "I'm coming for you, I'm coming for you";

console.log(a.charAt(-5));
//doesn't return anything
console.log(a.at(-5) + a.at(-10));
//nm
```

If we still wanted to use `charAt()` with negative index, we use a workaround :

```js
console.log(a.charAt(a.length-5)); //n
```

Still, this is cumbersome and I'd rather recommend you use `at()` directly.

#### Retrieving parts of a string

We use `slice()` to extract some parts of our string [aka sub-string]. We've to specify two things in this function :

* `start` : Where to begin; if not specified, slicing starts from the beginning of the string
* `end` : Where to stop; if not specified, slicing continues until end of the string.

```js
let text = 'Hanana, Banana, Janana';

console.log(text.slice(3,10)); //ana, Ba
console.log(text.slice(3)); //ana, Banana, Janana
```

#### Trimming whitespace

`trim()` lets you remove whitespaces from a string :

```js
let message = "      are you there?    ";

console.log("Before trimming:\n", message);
//      are you there?    
console.log("After trimming:\n", message.trim());
//are you there?
```

If we'd like to remove only the start and end of a string, we use `trimStart()` and `trimEnd()` :

```js
let a = "  Watching through my fingers";
let b = "Watching through my fingers  ";

console.log(a.trimStart() + '\n' + b.trimEnd());
/*
Watching through my fingers
Watching through my fingers
*/
```

#### Repeating strings

If, in any case, we need to repeat a string, we use `repeat()` :

```js
let a = "I'll go with you\n";
console.log(a.repeat(4));
/*
I'll go with you
I'll go with you
I'll go with you
I'll go with you
*/
```

Note that the method joins the repeated strings, so if I removed the `\n` character, we'd get this awkward string : ``I'll go with youI'll go with youI'll go with youI'll go with you``.

#### Mini-project

**Objective** : Reverse a string after converting it into lowercase

```js
let message = "Et Tu Brute?";
message = message.toLowerCase();
let text = "";

for (let i=message.length; i>=0; i--)
{
    text += message.charAt(i);
}

console.log(text);
//?eturb ut te
```

### Embedding JS in JS

You can embed JS variables or expressions inside template literals using `${}` [like you would do in C].

```js
let song = "Weight of Living";
let artist = "Bastille";
let spotify = `Now playing : ${song} by ${artist}`;

console.log(spotify);
//Now playing : Weight of Living by Bastille
```

```js
let song = "Take Me to Church";
let artist = "Hozier";
let score = 7.5;
const total = 10;
const output = `I have listened to ${song} by ${artist}. I give it a score of ${(score/total)*100}%`;

console.log(output);
//I have listened to Take Me to Church by Hozier. I give it a score of 75%
```

## Prompting users

Sometimes you'll need to ask user for input and produce output accordingly. For this, you would use `prompt()`.
