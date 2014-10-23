---
layout: post
title:  "EGR eBook Analytics Dashboard"
date:   2014-10-23 18:00:00
categories: jekyll 
---
###**Project Intro**
This post is a summary and overview of a freelance web development project I undertook for eGlobalReader, a language-learning eBook startup.  The goal was to create a responsive (in the sense of both screen-size and load speed), easy to use, and attractive dashboard for readers to review their eBook-usage statistics.

The eventual site isn't live at the moment (and will require login once up and running), so here's a sticked-together screenshot of the lastest version:

![Top Half of Dashboard](/blog/assets/posts/EGR-analytics-top-half.jpg)
![Bottom Half of Dashboard](/blog/assets/posts/EGR-analytics-bottom-half.jpg)

###**Frameworks, Libraries, and Other**
Created entirely on the front-end with Javascript, CSS, and HTML, the following libraries/frameworks were a huge help.

* [Bootstrap](http://getbootstrap.com/) The infamous front-end framework made a great basis for the site design, providing a wide range of standard elements (buttons, dropdowns, etc.) with which to construct the page. Certain aspects of the page (mostly the reading log history table) required quite a bit of fighting against or otherwise circumventing the Boostrap defaults, but overall it was a massive win in development time.


* [JQuery](http://jquery.com/) While not strictly necessary, this JS library offers a lot of convenience and a simpler syntax (in some cases) than vanilla JS for DOM manipulation.  I used it exstensively for all the event bindings throughout the page.


* [NVD3](http://nvd3.org/) Reuseable SVG chart JS library (powered by d3.js).  As a large graph was the most prominent part of the design, selecting the right JS graphing library was key.  I checked out [Raphaël](http://raphaeljs.com/) and [rickshaw](http://code.shutterstock.com/rickshaw/) as alternate free charting options, but default configurations of NVD3 won out.  NVD3 certainly takes some getting used to, and with essentially no documentation almost all configuration options need to be discovered from example snippets and comments around the web.  "Free of charge" was a requirement at this stage of development, otherwise [Highcharts](http://www.highcharts.com/) would have been a great option.

* [Sass/SCSS](http://sass-lang.com/) CSS-generating extension that preprocesses SCSS files.  Adds a bunch of great functionality to keep styling more concise and easy to maintain.  I mostly made use of the variables functionality, which allows you to declare a value and reuse it throughout your SCSS.  For example, with colors:  
{% highlight sass %}
// color bank
//--------------------------------------------------
  $bgDefault      : #fefdfd;
  $bgHighlight    : #EAE9E9;
  $colDefault     : #000000;
  $colHighlight   : #ffb122;
  $egrTeal        : #208A9E;
{% endhighlight %}


###**Visual Design**
The visual design and styling I coded up were based upon pdf mark-ups provided by one of EGR's founders.  Making fairly liberal use of built-in Bootstrap components, with a few adjustments or work-arounds as needed to provide non-standard functionality.  The scrollable table at the bottom was one such case  


###**Analytics Page Functionality Overview**



1. 

2.

3. **As a personal technical journal, to document things I've learned or thought about, and make it available to others who are learning the same things**

This feels like it covers most of it.  Essentially 2 parts self-improvement to 1 part self-documentation.


While typing up the above 'reasons', I started thinking about what else I should keep in mind as I approach this ongoing project.  The result:

###**Rules of the road, or, things I will try to keep in mind**
* I will try to write regularly, ideally at least one post per week.  
* They don't have to be strictly code-focused, but should generally deal with my experiences as a developer.
* Don't be too concerned with perfection, simply try to be straightforward, reasonably accurate, and honest in your handling of the chosen topic.
* Addendum to the above, generally leave posts alone once they're published, unless correcting technical inaccuracies.
* Lastly, focus on the writing over presentation.


###**Closing thought**
Time to add this to my posts, make sure everything works correctly, update a few of the layouts, and post.  




