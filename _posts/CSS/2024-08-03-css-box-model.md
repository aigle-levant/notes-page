---
layout: post
title: CSS - Box Model
categories: [CSS]
---

Box model is one of the most fundamental topics in CSS. Let's learn it...

* Table of content
{:toc}

## Box

> Refer -> [Learn CSS Box Model In 8 Minutes - Web Dev Simplified](https://youtu.be/rIO5326FgPE?si=7jBRMTdA_08FZGIH)

Everything in a website is a **box**. Sometimes they have boxes nested in them and at times they sit next to each other.

![alt text](..\images\img4.png)

A box has three parts : content, padding, margin. The border of a box plays a major role here.

![alt text](..\images\img5.png)

* **Content** is simply the stuff inside the box.
* **Padding** is the space between content and box's borders.
* **Margin** is the space between the box's borders and the borders of adjacent boxes.

To increase the space between the margin and padding, we simply increase the border.

If there are 2 box margins right next to each other, the **largest margin will have priority**. This is because the smaller margin collapses into the larger one.

### `display` property

This property decides two things :

* Whether an element will be treated as a block or inline block.
* The layout that'll used for its children.

#### Outer and inner display types

Let's say we have a paragraph tag and an `a` tag with borders :

![alt text](..\images\img14.png)

Let's try using our ``display: box``...

![alt text](..\images\img15.png)

...and ``display: inline-block``.

![alt text](..\images\img16.png)

Notice how the second block is stretched to the length of the first one in the first example. And, in the second one, the two of them are arranged next to each other.

You'd often see items arranged like this when a page's using ``display: inline-block`` :

![alt text](..\images\img17.png)
[Image credit : https://www.shecodes.io/]

Now we have two more types :

``display: flex`` : A famous display layout that has many modifications.

![alt text](..\images\img8.png)

``display: grid`` : Arranges elements like a stack

![alt text](..\images\img9.png)

### Manipulating the box

We can set the height and width of our element using ``height`` and ``width`` properties.

Properties that also affect content are ``inline-size`` and ``block-size``. These let us do horizontal and vertical text blocks.

> ``inline-size`` and ``block-size`` properties are the other names of ``width`` and ``height``

A thing to note is that padding and border account into the height and width of the element. So if our box has the proportions 100px x 100px and our padding is at 20 px, it calculates it like this :

> Height : 100 px + 10 [padding top] + 10 [padding bottom] + 40 px [border] = 160 px
> 
> Width : 100 px + 10 [padding left] + 10 [padding right] + 40 px [border] = 160 px

So our element's dimensions are actually 160px x 160px.

#### Margin collapsing

Sometimes, when we've two elements *really* close to each other, we'd see various results based on their margins :

![alt text](..\images\img18.png)

If margins of both the elements are **positive**, they merge into a single margin. The size of this common margin is equal to the largest individual margin.

![alt text](..\images\img19.png)

If margins of both the elements are **negative**, they collapse and only the smallest margin value remains.

![alt text](..\images\img20.png)

If we've a **positive margin and a negative margin**, the value of negative margin's subtracted from that of positive margin.

#### Alternate box model

When we use ``box-sizing: border-box``, the actual dimensions of the content is subtracted out from border and padding. Let's illustrate this using the calculation below :

> Height = 100 px
> 
> Padding = 20 px
> 
> Border = 40 px
> 
>Actual height of element : 100 - 60 = 40 px
>
> Width = 100 px
> 
> Actual width of element : 100 - 60 = 40 px
