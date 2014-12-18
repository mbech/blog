---
layout: post
title:  "A Simple Overview of CSS Psuedo-Elements"
date:   2014-12-16 20:00:00
categories: jekyll 
---
###**What are psuedo-elements?**

Psuedo-elements are a way to add additional "elements" to HTML without explicitly including them in your HTML markup. Psuedo-elements are added onto normal CSS selectors (such as "#my-id", ".my-class") using colon (or with CSS3, double-colon, though more on this later) syntax.  

There are currently 5 available psuedo-elements with varying levels of legacy browser support:

* :after
* :before
* :first-letter
* :first-line
* :selection

I'll be focusing on ":before" and ":after", but check out the [MDN dev page](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) for more specifics on each of them.

It's easy to include psuedo-elements in your CSS:

```css
.my-class::after {
	content: "";
        //property: value;
        //etc...
}
```

The above style would effectively insert an inline HTML element directly in front of the content of elements assigned class="my-class".  You can then use regular css properties (such as "display: block;", or "postion: absolute;") to style and place the psuedo-element as you like.

**Note: the content: ""; property is required when using :after and :before psuedo-elements, even if it's an empty string.**  These psuedo-elements will not render if it's absent.  This property can contain text, urls, or counter/counters, but first check out the next section.

###**When should I use them, and what are the good for?**
The value of psuedo-elements is that they help keep style-specific markup out of your HTML.  Rather than adding an extra tag in your HTML markup purely as a target for some styling, you can pull them out and achieve the same effect using only CSS.  

**Basically, it's just another way to further separate CSS *styling* from HTML *content*.**

When using the "content" property on :before and :after elements, be careful to not go too far the other way and place content into your CSS that belongs in your HTML.

###**How are they different from psuedo-classes?**
As explained in greater detail on the [MDN dev page](https://developer.mozilla.org/en-US/docs/Web/CSS/pseudo-classes), psuedo-classes use the same syntax as psuedo-elements but are used to style certain states of the selection (":hover", ":active", etc.) as opposed to injecting styles into certain parts the selection (":before", ":after").

###**Should I use the double or single colon notation?**
While the double-colon is the most recent CSS3 implementation (intended to differentiate it from psuedo-classes), the standard calls for full backwards compatability with the single-colon syntax for psuedo-elements.  As such, it seems like most web devs see no reason to adopt a double-colon style and potentially lose support in older browsers.

**TLDR: stick with single-colon for now.**

###**Example: using :before and :after to draw style elements to a page**

[Here's an example code snippet](http://codepen.io/anon/pen/PwzwZW?editors=110) for creating a two-piece overlay (semi-circle and carat shapes) using :before and :after psuedo-elements on a class.  

####Here's the HTML:

```html
<div class="top-bar"></div>
``` 

####And the CSS:

General styling for the header portion of the page (note: position: relative; so
that the absolute positioning of the psuedo-elements is 'relative' to the
containing parent rather than the window).

```css
.top-bar {
  position: relative; 
  width: 100%;
  height: 200px;
  background-color: grey;
  }
```

:after psuedo-element to create a semi-circle.

```css
 .top-bar:after {
    content: "";
    background-color: white;
    border-top-right-radius: 2em;
    border-top-left-radius: 2em;
    bottom: 0;
    display: block;
    height: 2em;
    left: 50%;
    margin-left: -2em;
    position: absolute;
    width: 4em;
  }
```

:before psuedo-element to create a carat.

```css
 .top-bar:before {
    content: "";
    border-color: blue;
    border-style: solid;
    border-width: 0 .5em .5em 0;
    bottom: .2em;
    display: block;
    height: 1em;
    left: 50%;
    margin-left: -.75em;
    position: absolute;
    transform: rotate(45deg);
    width: 1em;
    z-index: 1;
  }
```

The psuedo-elements respositions nicely with changing window widths, and the result scales well with different font-sizes.  As it's purely a stylistic element, it's great to be able to represent this purely in CSS, without having to clutter up the HTML with style-only elements.
