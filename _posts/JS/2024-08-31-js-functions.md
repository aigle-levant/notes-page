---
layout: post
title: JS - Functions
categories: [JS]
---

Let's learn about a powerhouse feature of JS...

* Table of content
{:toc}

## Functions

A function in JS has the same syntax like any other language :

```js
function weightOfLiving()
{
    return "under the weight of living";
}

console.log("or " + weightOfLiving());
console.log("you're " + weightOfLiving());
console.log(weightOfLiving());
console.log("you are " + weightOfLiving());

/*
or under the weight of living
you're under the weight of living
under the weight of living
you are under the weight of living
*/
```

Sometimes, it has parameters [arguments that will be passed to a function] and other times it doesn't.

![alt text](../images/img67.png)

If we remove the ``console.log()`` and call the function as it is...

```js
function weightOfLiving()
{
    return "under the weight of living";
}

weightOfLiving(); //no output
```

Nothing happens. This is because the `return` statement 'returns' something and doesn't actually print the value; we have to use ``console.log()`` to print that value.

```js
function weightOfLiving()
{
    console.log("under the weight of living");
}

weightOfLiving(); //under the weight of living
```

```js
const prompt = require("prompt-sync")({sigint:true});

function checkAge(age)
{
    if (age<18)
    {
        console.log("No, kid. You shouldn't be drinking at this age!");
    }
    else
    {
        console.log("Welcome!");
        drinkChoice();
    }
}

function drinkChoice()
{
    const drink = prompt("What may I serve you? ");
    if (drink=="")
    {
        console.log("C'mon, order a glass of water 'least");
        drinkChoice()  
    }
    else
    {
        console.log("Here's a glass of " + drink + "!\nEnjoy!");
    }
}

const age = prompt("Show me your id. What is your age?");
checkAge(age);
```

> A function with an empty or non-existent `return` statement will return `undefined`.

### Arguments and parameters

We can make functions have a certain parameter by default and then enable us to pass parameters to it :

```js
function hey(rel="Brother")
{
    console.log("Hey " + rel);
}

const prompt = require("prompt-sync")({sigint:true});
const opt = prompt("brother or sister?");

if (opt=="sister")
{
    hey("Sister");
}
else
{
    hey();
}
```

This function, by default, has the value 'Brother', and so if we merely call it, it'll use that value.

> Use this ``const prompt = require("prompt-sync")({sigint:true});`` in case `prompt()` doesn't work for you in VSCode.

### Anonymous functions

We call a nameless function an anonymous function :

```js
(
    function()
    {
        console.log("Is anyone there??");
    }
);
```

### Function scope

A function's scope is the area in code reachable by it. It's confined by the mighty curly braces `{}`.

In that, we observe 2 variables : local and global.

Local variables are confined inside a function and can be used only within it.

Global variables, on the other hand, are outside functions and can be accessible from anywhere in the program.

```js
let song = "Hey Brother";

function setSong(song)
{
    console.log(song);
}

setSong(song); //Hey Brother
```

The function uses the already existing global variable as argument and returns the value.

Now let's add in a local variable :

```js
function setSong(song)
{
    let artist = "Avicii";
    console.log(song);
}

console.log(artist); //ReferenceError
```

We get a `ReferenceError` since the variable's out of scope.

### Function expression

It is another way to directly create a function :

```js
let line = function()
{
    console.log("Ge-");
};
let word = "Genius";
console.log(line + word);

/*
function()
{
    console.log("Ge-");
};
*/
```

We don't need the damn code! I'll have to modify this one just a bit...

```js
function genius()
{
    return "Ge-"
}

let line = genius;
let word = "Genius";
console.log((line().repeat(6)) + word);

//Ge-Ge-Ge-Ge-Ge-Ge-Genius
```

### Arrow functions

Now that we've seen function expressions, we wish to make them easier to write. For this, we go for arrow functions.

Consider the following code :

```js
let line = function(song, artist)
{
    return ("Playing : " + song + " by " + artist);
};

const prompt = require("prompt-sync")({sigint:true});

let song = prompt("Song name: ");
let artist = prompt("Artist: ");
console.log(line(song, artist));
```

Looks like we can shrink down a bit of our code using this arrow functions :

```js
let line = (song, artist) => ("Playing : " + song + " by " + artist);
```

`=>` is the arrow equivalent of `return`. We merely pass parameters and the function returns something.

Let's try this out with less than 2 parameters :

```js
let line = song => ("Playing : " + song);

const prompt = require("prompt-sync")({sigint:true});
let song = prompt("Song name: ");
console.log(line(song));
```

We can also have default values for our function :

```js
let line = (song="Bad Blood", artist="Bastille") => ("Playing : " + song + " by " + artist);

console.log(line());

//Playing : Bad Blood by Bastille
```
