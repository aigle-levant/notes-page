---
layout: post
title: CSS - Flex-box
categories: [CSS]
---

``display: flex`` is a frequently used property in CSS. Here's how we learn to use it...

* Table of content
{:toc}

## Flex-box

> Refer -> [Flexbox - Interneting Is Hard](https://internetingishard.netlify.app/html-and-css/flexbox/index.html)

It is a way to arrange items into rows and columns that **flex** based on certain rules.

![alt text](..\images\img11.png)

> Flex : Growing or shrinking

It is a plethora of properties that you use to arrange things. These properties thus go in 2 places :

![alt text](..\images\img13.png)

* **Flex container** : Element with ``display: flex`` property in it
* **Flex item** : Element inside a flex container

An element can be both a flex container and a flex item at the same time.
{:.note}

So, you can have a parent element as a flex container then use its children as flex items. If we want to make changes in the flex items, we'd simply use our flex container.

![alt text](..\images\img10.png)

### Manipulating the flex-box

![alt text](..\images\img12.png)

We have rules to modify our flex container :

#### flex-direction

Sets direction of flex container

* ``row`` : Content is arranged as a row
* ``column`` : Content is arranged as a column
* ``row-reverse`` : Content is arranged as row and reversed
* ``column-reverse`` : Content is arranged as column and reversed

#### order

Sets the order in which the item appears in row or column

#### flex-wrap

* **``wrap``** : Renders flex items as a grid from top to bottom; they won't go out of a grid
* **``wrap-reverse``** : Reverse of ``wrap``; items are wrapped bottom to top.
* **``no-wrap``** : All flex items will be on a single line.

#### Shorthand flex

**``flex``** is actually a shorthand for the following properties :

* ``flex-grow`` : Grow a certain amount from base size
* ``flex-shrink`` : Shrink a certain amount from base size
* ``flex-basis`` : Base size

When we say ``flex: 1;``, we actually mean ``flex: 1 1 0;``. 1 here means the items are handled evenly.

> ``flex-auto`` stands for ``flex: 1 1 auto``.

#### Alignment

**``justify-content``** and **``align-items``** take care of content alignment.

* ``flex-start`` : Content goes to left-end
* ``flex-end`` : Content goes to right-end
* ``center`` : Content is centered; very similar to ``margin: 0 auto``
* ``space-around`` : Content is separated from other content using spaces; doesn't touch the very border of box
* ``space-between`` : Content is separated from other content using spaces; will touch border of box

> **``flex-start``** and **``flex-end``** have different meanings in ``justify-content`` and ``align-items``.The former means content goes to upper-end while the latter means content goes to lower-end.

``gap`` : Adds space between flex items
