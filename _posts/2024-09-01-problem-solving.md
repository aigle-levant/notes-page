---
layout: post
title: Problem Solving in Programming
categories: [CS]
---

Here we learn how to solve a problem effectively...

* Table of content
{:toc}

## Problem solving

We have heard of the phrase - 'To think like a programmer'. Often, it means 'to solve a problem logically'. Quite handy for many situations, but how do we get there?

### Understanding a problem

There's a technique used by the programming community called 'rubber-duck debugging' that involves the programmer describing how their program works to a rubber duck.

When they do this, they naturally come to light of the flaws in their program and move on to the next step of problem solving.

> Try [this bot](https://www.masswerk.at/elizabot/) to simulate rubber-duck debugging

Everything starts when you understand a problem and are able to convey it in your own words.

### Planning

If you've played any RPG or MMORPG games, they require some planning and putting out strategies to win. Similarly, your program is a battlefield and you are to plan your way ahead.

Analyse the problem instead of getting to the keyboard straight away. Comments, scratch pads, etc. are good tools to use while doing this.

### Divide and conquer

You are an army general in charge of a mediocre-sized army. Will you go straight ahead to attack the bigger enemy army, or will you take down troops one after another?

Doing the second enables your troops to live to tell the tale.

Break the problem into several pieces. Tackle each sub-problem and their solutions will automatically solve the bigger problem.

This method is used in the technique called recursion and the feature, modularity.

#### Example

Given a problem statement...

> Write a program that reads ten numbers and figure out which number is the third highest.

You may wonder for a while on how to tackle this problem. Fret not, the problem is extremely simple :

```md
1. Read the numbers
2. Find out the largest number out of list
3. Find out the 2nd largest number out of list
4. Find out the 3rd largest number out of list
5. Return this number
```

Still too tough?

```md
1. Read the numbers
2. Begin for loop : compare one number with another and set the larger number as greatest until end of list
3. Exclude the largest number and repeat step 2 to get the 2nd largest number
4. Exclude the numbers obtained in step 2 and 3; repeat step 2 to obtain the 3rd largest number
5. Return this number
```

See, it wasn't tough.

### Always have a template of your program

### What if my problem isn't solved still yet?

* **Debug** : Go through your solution step-by-step and look for any pot-holes in it.
* **Reassess** : Look at the problem from another perspective.
* **Research** : Look up Google for solutions of your sub-problems, not your main problem.
* **Start anew** : Just do your solution fresh. No regrets.

### Pseudocode

> Refer [Pseudocode - Builtin](https://builtin.com/data-science/pseudocode)

Pseudocode [false code] is a way to describe the algorithm of a program which will be translated to a programming language soon after.
