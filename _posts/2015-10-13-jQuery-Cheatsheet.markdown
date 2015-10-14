---
layout: post
title: Using jQuery to Change Elements and CSS
---


##Using jQuery to change elements and css

When I was first starting out with jQuery, I was a huge fan of the [jQuery Docs] (http://api.jquery.com/). It is a great resource to learn more about functions, how to use them, parameters available, etc. 

However, there was one problem. I did not know where to start. I knew what I wanted to do but it would take several search queries just to find it. Then it would involve reading the resource and applying it. I could of saved a ton of time if I had everything presented right then and there with a quick description and example.

So here is an ongoing compilation of useful jQuery functions. Simple functions to manipulate html elements and css using jQuery. 

###Basic jQuery function

If you're a beginner this is the starting foundation. You want to run your jQuery after the page has loaded to avoid any errors.

{% highlight js %}
$(document).ready(function {
	
});
{% endhighlight %}

###Manipulate by adding a class or CSS

{% highlight js %}

$("#id").addClass("className"); /* add a class to Ids */
$(".class").addClass("className"); /* add a class to Classes */
$("button").addClass("className"); /* add a class to Elements */
$("button").removeClass("className"); /* remove class from elements */
$("#target").css("background-color", "red"); /* Add a CSS property to a target */

{% endhighlight %}

###Disable/Remove an element

{% highlight js %}

$("#target1").prop("disabled", true); /* set state to disabled */
$("#target").remove() /* remove the target */

{% endhighlight %}

###Move elements from one container to another

{% highlight js %}

$("#target2").appendTo("#right-well");

{% endhighlight %}

###Daisy Chaining Functions

{% highlight js %}

("#target").clone().appendTo("#targeLocation"); /* aka join functions, in this case copy or clone the target and move it to the new location */

{% endhighlight %}

###Modifying parent/child elements

{% highlight js %}

("#target").parent().css("background-color", "red"); /* modify the parent of the target */
("#target").children().css("background-color", "red"); /* modify the child of the target */

{% endhighlight %}

###Target the nth-child(n) css selector

{% highlight js %}

(".target:nth-child(2)").addClass("animated bounce"); /* bounce the 2nd element with class target */

{% endhighlight %}

###Target the odd/even elements

Note: jQuery starts with index 0

{% highlight js %}

(".target:even").addClass("animated shake");

{% endhighlight %}

