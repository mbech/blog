---
layout: post
title:  "Game of Life in Javascript"
date:   2014-10-25 20:00:00
categories: jekyll 
---
![GoLJS](/blog/assets/posts/GoLJS-strip.png)

###**What are we talking about?**
I coded up a fairly well known mathematical "cellular automata" in Javascript, HTML, and CSS.  Here's a link to the running site:

[Game of Life - Javascript](mbech.net/Game-of-life-JS.html)

This post is about the creation of that page along with some code snippets and my thoughts.  The code is all public on GitHub, here's a link to the repository:

[GoLJS Source Code](https://github.com/mbech/GoLJS)

###**Description of the "Game"**
[Conway's Game of Life](http://en.wikipedia.org/wiki/Conway's_Game_of_Life) is a
mathmatical grid-based "game" in which cells on the grid can exist in two
states: alive or dead.  After an initial input (settin some cells as alive), the
game proceeds to the next state by applying rules on a cell-by-cell basis.  For
example, one rule states that:

* Any live cell with two or three live neighbours lives on to the next generation.

EXAMPLE - Cell Living On:

![cell rule example - live](/blog/assets/posts/GoLJS-cell-layout-live.png)


*The live center cell, with two living neighbors, will be alive next round*


While another rule states:

* Any live cell with more than three live neighbours dies, as if by overcrowding.

EXAMPLE - Doomed Cell:

![cell rule example - die](/blog/assets/posts/GoLJS-cell-layout-die.png)


*The same live center cell, now with four neighbors, will be dead next round due to 'overcrowding'*

By combining these with a few other rules, the next state of any cell is determined by
the current state of its 8 surrounding neighbors.  It's really more of a mathmateical 
progression from a predefined starting arrangement of cells than a true "game".

###**'Ok' on what, but why?**
I chose to start this project a few months ago. At that time, producing a simple game in javascript seemed like a
great way to get more experience coding in JS and doing a lot of DOM
manipulation with JQuery.  Soon after starting, I ended shelving the project for a few
months during which I read up on JS (the oft-recommended [Javascript the Good
Parts](http://www.amazon.com/JavaScript-Good-Parts-Douglas-Crockford/dp/0596517742)
 along with 
[Javascript Enlightment](http://www.amazon.com/JavaScript-Enlightenment-Cody-Lindley/dp/1449342884)).
Feeling more confident in my JS knowledge and looking for somewhere to appy it,
I decided to pick Game of Live (GoL) back up and run with it.  

1. **OL**

* UL 

###**Closing thought**
Text


section ideas:
why GoL? as intro

using JQuery, may redo without to see difference, using normalize.css

complication of cell next state rules, discuss how it's buggy, wonder if better
solution exists (maybe due to 1-D array)?

game logic - handling boundary behavior bug/issue

use of setInterval with pair of functions, activation flag to create looping
refresh




