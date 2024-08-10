---
layout: post
title: HTML - Tables
categories: [HTML]
---

You want to learn how to organise data in a table? You've come to the right place!

* Table of content
{:toc}

## Tables in HTML

Tables are easily created in HTML using this format :

```html
<table>
    <caption>Title goes here</caption>
    <thead>
        <tr>
            <th scope="col">Col1</th>
            <th scope="col">Col2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
          <th scope="row">Row, row, row a boat</th>
          <td>Gently down the stream...</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
          <th scope="row" colspan="2">Main stats</th>
          <td colspan="2">Some number goes here</td>
        </tr>
    </tfoot>
</table>
```

Okay, okay, now that's a *lot* of things to take in. Let's simplify it [along with a step-by-step guide to do it practically, I promise!].

We create a table using the tag ``<table>``. This table can have a ``<caption>`` tag that works as a title for the table.

```html
<table>
    <caption>My Spotify Playlist</caption>
</table>
```

The table headers are created using ``<thead>`` tag and it's where we have our column names. After this tag, we use ``<tr>`` to create a row, then use ``<th>`` to create each header 'cell'.

```html
<table>
    <caption>My Spotify Playlist</caption>
    <thead>
        <tr>
            <th scope="col">Song</th>
            <th scope="col">Album</th>
            <th scope="col">Artist</th>
        </tr>
    </thead>
</table>
```
