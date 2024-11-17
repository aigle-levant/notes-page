---
layout: post
title: CSS - Function
categories: [CSS]
---

Although CSS doesn't allow functions in the first place, let's see what we can do instead...

* Table of content
{:toc}

## Function

We already know how functions generally work. Although, CSS doesn't let us do functions by itself, it has some built-in functions that you can use.

`rgb()`, `linear-gradient()` are some of them.

### `calc()`

```css
:root {
--header: 3rem;
--footer: 40px;
--main: calc(100vh - calc(var(--header) + var(--footer)));
}
```

The `calc()` here simply means `100vh - (3rem + 40px)`. It helps to separate them like this :

```md
let a = var(--header) = 3rem
then let b = var(--footer) = 40px

then variable = calc(a + b)
[returns sum of those variables]

finally, finalAnswer = calc(100vh - variable)
[returns difference of values]
```

### min()

Sets the smallest value from the given values [we can give more than one value to this one!].

```html
<div class="resize">
    <img id="#image" src="https://i.pinimg.com/enabled/564x/2c/d4/c1/2cd4c13e4bd6b95092b02d5613515f53.jpg" alt="img">
</div>
```

```css
.resize
{
    overflow: auto;
    max-width: 100%;
    max-height: 100%;
    resize: both;
}
```

It gives us this :

![alt text](image.png)

We need to resize this properly, so we use `min()`.

```css
#image
{
    width: min(500px, 100%);
    height: min(500px, 100%);
    box-sizing: border-box;
}
```

![alt text](image-1.png)

There! We're done...

### max()

Works the same as `min()`, but it selects the largest value.

### clamp()

Takes 3 arguments -

- Smallest value
- Ideal value
- Largest value
