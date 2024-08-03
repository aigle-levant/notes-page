---
layout: post
title: CSS - Box Model
categories: [CSS, Programming Languages, Web dev]
---

Box model is one of the most fundamental topics in CSS. Let's learn it...

* Table of content
{:toc}

## Box

> Refer -> [Learn CSS Box Model In 8 Minutes - Web Dev Simplified](https://youtu.be/rIO5326FgPE?si=7jBRMTdA_08FZGIH)

Everything in a website is a **box**. Sometimes they have boxes nested in them and at times they sit next to each other.

![alt text](/images/img4.png)

A box has three parts : content, padding, margin. The border of a box plays a major role here.

![alt text](/images/img5.png)

* **Content** is simply the stuff inside the box.
* **Padding** is the space between content and box's borders.
* **Margin** is the space between the box's borders and the borders of adjacent boxes.

To increase the space between the margin and padding, we simply increase the border.

If there are 2 box margins right next to each other, the **largest margin will have priority**. This is because the smaller margin collapses into the larger one.
{:.note}

### Manipulating the box

We can set the height and width of our element using ``height`` and ``width`` properties.

``inline-size`` and ``block-size`` properties are the other names of ``width`` and ``height``
{:.note}

A thing to note is that padding and border account into the height and width of the element. So if our box has the proportions 100px x 100px and our padding is at 20 px, it calculates it like this :

> Height : 100 px + 10 [padding top] + 10 [padding bottom] + 40 px [border] = 160 px
> 
> Width : 100 px + 10 [padding left] + 10 [padding right] + 40 px [border] = 160 px

So our element's dimensions are actually 160px x 160px.

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

### Display types of a box

Boxes have an inner display type as well as an outer display type. We can set it using ``display`` property.

* Outer type determines the element's position in flow layout
* Inner type sets the layout of child elements

`display: block;` : Arranges the elements like blocks in a row.

![alt text](/images/img6.png)

The box breaks into a new line; width and height properties are now respected.

``display: inline-block`` : The parent element hugs the children elements

![alt text](/images/img7.png)

Padding, borders and margins will apply. However, only the left and right portions will cause other inline boxes to move away.

``display: flex`` : A famous display layout that has many modifications.

![alt text](/images/img8.png)

``display: grid`` : Arranges elements like a stack

![alt text](/images/img9.png)
