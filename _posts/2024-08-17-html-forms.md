---
layout: post
title: HTML - Forms
categories: [HTML]
---

Let's learn how form content works in HTML...

* Table of content
{:toc}

## Forms in HTML

We've seen a variety of web forms in the form of newsletters, signing up, etc.

These allow users to enter information, which will be stored in a web server for processing and storage or for updating the UI.

A web form is made up of form controls [aka widgets] and other elements [known as HTML forms] to structure it.

Form controls are created using the `<input>` tag.

### Creating a form

A form is created using the container tag `<form>`. This tag has the following attributes :

* `action` : Defines the URL where the form's collected data is sent
* `method` : Defines which HTTP method to send data with.

```html
<form action="/some-url" method="get">

</form>
```

Now let's add the form controls to get user input.

```html
<form>
    <label for="name">Username: </label>
    <input id="name" type="name" name="username">
    <label for="password">Password: </label>
    <input id="password" type="password" name="password">
    <label for="message"> Write your comment</label>
    <textarea>
        Write something
    </textarea>
</form>
```

![alt text](../images/img39.png)

The `<label>` tag is there to let us known what input is being asked by the field.

We also have a `for` attribute that takes the id of the `<input>` as its value. It helps us associate the label with the form control.

The `type` attribute in `<input>` defines the way it behaves.

After that, we've the `<textarea>` element which lets the user write a message in the field.
