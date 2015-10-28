##Using js to change elements and css

When I was first starting out with js, I was a huge fan of the [js Docs] (http://api.js.com/). It is a great resource to fmore about functions, how to use them, parameters available, etc. 

However, there was one problem. I did not know where to start. I knew what I wanted to do but it would take several search queries to just find it. Then it would involve reading the resource and applying. I could of saved a ton of time if everything was presented right then and there with a quick description and example.

So here is an ongoing compilation of useful js functions. Simple functions to manipulate html elements and css using js. 

###Basic js function

If you're a beginner this is the starting foundation. You want to run your js after the page has loaded to avoid any errors.

{% highlight js %}
$(document).ready(function {
	
});
{% endhighlight %}

###Manipulate by class

{% highlight js linenos %}

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

Note: js starts with index 0

{% highlight js %}

(".target:even").addClass("animated shake");

{% endhighlight %}


###FUN - target the body tag and use animated hinge

{% highlight js %}

("body").addClass("animated hinge");

{% endhighlight %}
