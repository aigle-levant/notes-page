---
layout: post
title: CSS - Selectors
categories: [CSS]
---

Let's advance to the next level of CSS selecting...

* Table of content
{:toc}

## Parent-child-sibling selectors

Let's say we've the following HTML code :

```html
<div class="container">
    <div class="header">
        <h1 class="main-heading"></h1>
    <div class="main">
        <article class="content"></article>
    </div>
    <div class="footer">
        <p class="para"></p>
    </div>
</div>
```

If we want to select only the child or grand-child elements of `.container` class, we'd do this :

```css
/* parent -> child */
.container > div 
{
    /* styles go home */
}
/* parent -> child -> grandchild */
.container > div > div
{
    /* again some styles */
}
```

To select the adjacent element, we'd do this :

```css
/* <div class="footer"> is selected */
.main + div
{
    /* content */
}
/* same as above */
.header + div + div
{
    /* same content */
}
```

If we want to select the siblings of child elements, we do this :

```css
/* .header, .main, .footer are selected */
.header ~ div
{
    /* csss shtyles go here! */
}
```

### Pseudo-selectors

`:focus` -> Element that's currently selected by the user

`:hover` -> Mouse is currently over this element

`:active` -> Element is being clicked.

`:link` -> Unvisited site

`:visited` -> Visited site

`:first-child` -> First child element of the container

`:last-child` -> Last child element of the container

`:empty` -> Elements with no children

`:only-child` -> Elements that don't have sibling elements

`::marker` -> Styling `<li>` elements

`className:nth-child(number)` -> Selects the nth element with className

`::first-letter` / `::first-line` -> Special styling to first letter or line of a text

`::selection` -> Styling the highlighting when user selects text

`::before` & `::after` -> Extra elements that are added using CSS.
