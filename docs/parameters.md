---
layout: docs
title: Parameters
prev_section: actions
next_section: controls
permalink: /docs/parameters/
---

Text-related actions such as `type`, `caption`, and `browser` need an extra string to specify what text to type, what message to display, or which URL to open. Sikuli Slides allows you to parameterize the value of this string. To turn a value into a parameter, simply choose a meaningful name for the parameter, say `user`, and write it in the slide as `<user>`. The enclosing `<` and `>` are special markers to indicate that whatever in-between is a parameter. A parameter is like a place holder. Its value will be specified later at the execution time.
	
Here are examples of two slides for displaying a greeting message. 

<div class="grid whole">
	<div class="unit half">
		<img src="/img/helloworld.jpg" class="whole img-polaroid"><br>
		<a href="/pptx/helloworld.pptx">helloworld.pptx</a>
	</div>
	<div class="unit half">
		<img src="/img/hellouser.jpg" class="whole img-polaroid"><br>
		<a href="/pptx/hellouser.pptx">hellouser.pptx</a>
	</div>
</div>

The first slide does not use a parameter. It will always display *Hello World*. The second slide uses a `<user>` parameter to represent the user's name. It will display a different message depending on the value given for the user's name.

To execute slides with specific parameter values, run the command like below:

{% highlight bash %}
$ {{site.slides.executable}} execute -parameters user='John Smith' hellouser.pptx 
{% endhighlight %}

This will print the message *Hello John Smith* on the screen.