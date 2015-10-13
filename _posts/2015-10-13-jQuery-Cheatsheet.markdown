##Using jQuery to change elements and css

When I was first starting out with jQuery, I was a huge fan of the [jQuery Docs] (http://api.jquery.com/). It is a great resource to fmore about functions, how to use them, parameters available, etc. 

However, there was one problem. I did not know where to start. I knew what I wanted to do but it would take several search queries to just find it. Then it would involve reading the resource and applying. I could of saved a ton of time if everything was presented right then and there with a quick description and example.

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
#("#target").css("background-color", "red");

{% endhighlight %}

###Disable/Remove an element

{% highlight js %}

$("#target1").prop("disabled", true);
$("#target").remove()

{% endhighlight %}

###Move elements from one container to another

{% highlight js %}

$("#target2").appendTo("#right-well");

{% endhighlight %}

###Daisy Chaining Functions

{% highlight js %}

("#target").clone().appendTo("#targeLocation");

{% endhighlight %}

###Modifying parent/child elements

{% highlight js %}

("#target").parent().css("background-color", "red");
("#target").children().css("background-color", "red");

{% endhighlight %}

###Target the nth-child(n) css selector

{% highlight js %}

(".target:nth-child(2)").addClass("animated bounce"); /* bounce the 2nd element wuth class .target */

{% endhighlight %}

###Target the odd/even elements

Note: jQuery starts with index 0

{% highlight js %}

(".target:even").addClass("animated shake");

{% endhighlight %}


###FUN - target the body tag and use animated hinge

{% highlight js %}

("body").addClass("animated hinge");

{% endhighlight %}
