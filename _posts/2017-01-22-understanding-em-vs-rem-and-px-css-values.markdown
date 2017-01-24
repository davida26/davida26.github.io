---
layout: post
title: Understanding em vs rem and px Values
category: CSS
description: Understanding the difference between em, rem and px values. How to use em and rem, translating to pixel values, advantages and when to use em or rem.
---

## Introduction
Lately, I have been seeing more and more developers shift from using the traditional px unit to em's and rem's. So what is the difference? Why should we use these and when are these better to use. Let's dig in. 

## Our Foundation the *px* (pixel)
We use these all the time in our css files to determine the size of an element or its position. Whatever we define the px value to be is rendered on the screen. The px value stays consistent throughout devices - in its simplest form (not accounting for media queries, etc).

## *em*'s - scalable units
The main attraction of using ems is because they are a scalable unit. They provide greater flexibility to our px values. 

### How these work

- An *em* is equal to the current font size of the <strong>document</strong>. 

<strong>Example 1:</strong>
Document Definition for Font Size: 12pt
Converting 12pt to px = 16px
Using the definition, 16px = 1em* 

- Since *em*s are scalable we can increase/decrease by modifying its value.

<strong>Example 2:</strong>
So if we have an element with font-size: 1em and we want to make another 2x larger we can do the following:

```css

font-size: 2em;

```
This will cause the font-size to convert to 32px.

<span class="footnote">*this can be modified to a base, [presented here](http://clagnut.com/blog/348/).</span>


### Problems with *em*s

So these are great due to their scabalibility, unfortunately they have a compounding effect.
The compounding effect is created because em's are relative to the font-size fo the parent.

<strong>Here is an example:</strong>

```html
<div class="parent">
	<p class="child">Hello World</p>
</div>
```

```css
.parent{
	font-size: 2em;
}
.child{
	font-size: 1.5em;
}
```

Using traditional px you would expect the child element to be smaller than the parent. However, since we are using ems this is what occurs:

```tex
2 (em) x 16px (default doc font size) = 32px = parent

2 (em) x 1.5 (em) x 16px (default doc font size) = 48px = child
```

Well that is definitely not what you intended! Now, imagine the parent div was a child of another parent div with *em*s specified there as well? The result would be much much larger than you expected.

## *rem*'s -  a better alternative to *em*s
Thanks to CSS3 the <strong>rem</strong> was introduced. It simply means the "root" em and solves this compounding effect problem.

<strong>*rem*s can be defined as follows:</strong>

```css
html{
	font-size: 62.5% /* we are using the baseline (see note above) to convert 16px to 10px */
}
h1{
	font-size: 1.4rem /* 14px */
}
p{
	font-size: 1rem /* 10px */
}
```

Notice how the behavior is now what we want. We want the `<p>` element to be smaller than the `<h1>`. 

In today's modern browsers rems are supported. [Full Browser Support Here.](http://caniuse.com/#feat=rem) 


 