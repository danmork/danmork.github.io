---
layout: post
title:  Eisenhower Elementary
tags: volunteering hourofcode
---

Today I had the honor of speaking to the 6th grade class at Eisenhower Elementary in Hopkins, MN about code to help them get ready for [Hour of Code](https://hourofcode.com/) next week.

We had a great time talking about code and using [Atom](https://atom.io/) to write code to make a [ThingM blink(1)](https://blink1.thingm.com/) light flash their school colors. I'm really looking forward to going back next week to help them with the Hour of Code tutorials.

The slides are available here:

[An Intro to Code (Apple Keynote)](/files/an-intro-to-code-slides.key)

[An Intro to Code (PDF with Presenter Notes)](/files/an-intro-to-code-slides.pdf)

Here's the code we wrote:

{% highlight JavaScript %}
// index.js
var blink1 = require("node-blink1");
var colors = require("color-name");
var light = new blink1();

function setColor(color) {
  light.setRGB(color[0], color[1], color[2]);
}

var schoolColors = [
  colors.blue,
  colors.gray,
  colors.white
];

var current = 0;

function changeColor() {
  if (current === schoolColors.length - 1) {
    current = 0;
  } else {
    current = current + 1;
  }
  
  setColor(schoolColors[current]);
  setTimeout(changeColor, 500);
}

setTimeout(changeColor, 500);
{% endhighlight %}
