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

###**Why make this?**
I chose to start this project a few months ago. At that time, producing a simple game in javascript seemed like a
great way to get more experience coding in JS and doing a lot of DOM
manipulation with JQuery.  Soon after starting, I ended shelving the project for a few
months to do some freelance web dev work.  I read some books on JS, most notably the oft-recommended [Javascript the Good
Parts](http://www.amazon.com/JavaScript-Good-Parts-Douglas-Crockford/dp/0596517742)
 along with 
[Javascript Enlightment](http://www.amazon.com/JavaScript-Enlightenment-Cody-Lindley/dp/1449342884).

Feeling more confident in my JS knowledge and looking for somewhere to appy it,
I decided to revive Game of Live - Javascript (*GoLJS*) and attempt to complete it.  

###**Mostly Pure HTML/CSS/JS, with a sprinkling of...**
* [JQuery](http://jquery.com/) - The ubiquitous and versatile JS library.  I'd included this when originally starting the project, but ended up only using it for basic DOM binding and manipulation. I may take it out and use vanilla JS later on as an exercise.
* [normalize.css](http://necolas.github.io/normalize.css/) - "A modern, HTML5-ready alternative to CSS resets", I included this to minimize cross-browser styling headaches and focus on the actual GoL implementation.

This is a small project, so I opted to use pure css rather than my go-to Sass/SCSS preprocessor (which I definitely missed as the number of elements to style grew).  

###**Code organization**
Here's the current file structure:

		GoLJS
		├── css
		│   └── main.css
		├── index.html
		├── js
		│   ├── automater.js
		│   ├── bindings.js
		│   ├── controller.js
		│   ├── game_board.js
		│   └── view.js
		├── README.md
		└── todo.txt

		2 directories, 9 files		

*Directory list created by [tree](http://mama.indstate.edu/users/ice/tree/), a recursive directory display for linux*

Pretty straightforward. I tried to keep the JS modular, with each file containing functions to handle its specific domain:

* automater.js handles the time-step advance of the board state (more about this further below)
* bindings.js contains all of the event (e.g. on click) bindings
* controller.js simply calls to initialize the board/bindings and sets up the demo cell pattern on page load
* game_board.js stores a board object, with all sorts of functions to deal with current and future cell states
* view.js is responsible for rereshing visual elements on the page following a board state-change

###**Automating board updates with setInterval()**



###**Closing thought**
Text


section ideas:

complication of cell next state rules, discuss how it's buggy, wonder if better
solution exists (maybe due to 1-D array)?

game logic - handling boundary behavior bug/issue

use of setInterval with pair of functions, activation flag to create looping
refresh




