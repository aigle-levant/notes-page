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

Let's try finding out the length of the lyrics.

```js
console.log(text + '\n\nLength of the string is: ' + text.length);
//Length of the string is: 187
```

We use `charAt()` to retrieve a character [a single letter or some other symbol] from our string.

```js
let text = `Gotta slow up, gotta shake this high
Gotta take a minute just to ease my mind
'Cause if I don't walk, then I get caught out
And I'll be falling all the way down`;

console.log(text.charAt(23)); //a
console.log(text.charAt(34)); //g
```

We use `slice()` to extract some parts of our string [aka sub-string]. We've to specify two things in this function :

* `start` : Where to begin; if not specified, slicing starts from the beginning of the string
* `end` : Where to stop; if not specified, slicing continues until end of the string.

```js
let text = 'Hanana, Banana, Janana';

console.log(text.slice(3,10)); //ana, Ba
console.log(text.slice(3)); //ana, Banana, Janana
```

`trim()` lets you remove whitespaces from a string :

```js
let message = "      are you there?    ";

console.log("Before trimming:\n", message);
//      are you there?    
console.log("After trimming:\n", message.trim());
//are you there?
```

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


