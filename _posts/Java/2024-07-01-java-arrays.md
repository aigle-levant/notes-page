---
layout: post
title: Java - Arrays
categories: [Java]
---

Java arrays are the ancestors of ArrayLists...

* Table of content
{:toc}

## Arrays

Unlike the newer and younger ArrayLists, arrays come with Java by default. You don't have to take the trouble of importing, creating object and then getting it work!

> Refer [OOP](/_posts/2024-06-17-oop.md) if you don't know what's an object.

## Creating an array

We can create an array by two ways :

* We create it with the elements
* We specify the datatype and size to add them later.

```java
String[] brands = {"espresso", "java", "latte"};

String[] brands = new String[2];
```

## Array operations

We usually use the array's index to add, access, modify and delete elements.

```java
//adding elements
brands[0] = "espresso";
brands[1] = "java";

//modifying elements
brands[0] = "latte";

//accessing elements
System.out.println(array[0]);
System.out.println(array[1]);
```

Sometimes, we'd want to access the end of the list. We can already do this in ``ArrayList`` using ``IndexOf()``, but now we want to do it with arrays.

### Negative indices with Java

Let's try using negative indices like we do with Python...

```java
public class neg
{
    public static void main(String[] args)
    {
        String[] brands = {"espresso", "java", "latte"};
        System.out.println(brands[-1]);
    }
}
```

![alt text](..\images\image.png)

Why did we get an exception when all's going well? Oh well, all's *not* going well, it seems.

**Java doesn't support negative indices.**

It's because arrays in Java [and also C, C++, etc.] are stored in contiguous [unbroken, continuous] blocks of memory.

When we access array elements, the language uses pointer arithmetic to calculate the memory address of the element [thus locating it].

If we access an element using a negative index, the language will try to access memory before the array even begins! This leads to a sweet struggle before a likely runtime error.

> Source -> [Quora](https://www.quora.com/Can-you-use-negative-numbers-as-array-indexes)

Now to access the last element in a java-proper manner, we use this workaround :

```java
int index = brands.length - 1;
```

`length` is not a method call. Don't use it like `length()`.
{:.note}
