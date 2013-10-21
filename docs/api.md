---
layout: docs
title: API
prev_section: gui
next_section: jruby
permalink: /docs/api/
---

Sikuli Slides API allows you to execute Sikuli Slides directly from your own Java programs. 

## Installation

* You can download the standalone jar from the [Download](\download\) page. Simply include this jar in the classpath of your project.
* Or if you use Maven, you can include the dependency statement below in the `pom.xml` of your project.

{% highlight html %}

<dependency>
	<groupId>org.sikuli</groupId>
	<artifactId>sikuli-slides-api</artifactId>
	<version>{{site.slides.version}}</version>
</dependency>

{% endhighlight %}



## Hello World
Suppose you have created a slide like below and saved it as [helloworld.pptx](/pptx/helloworld.pptx).

<img src="/img/helloworld.jpg" class="half img-polaroid">

Below is a simple program to execute this file. When executed, the program reads the content of the file and displays the message "Hello World" in the center of the screen.

{% highlight java %}
public class HelloWorld {
	public static void main(String[] arg) throws SlideExecutionException {		
		Slides.execute(new File("helloworld.pptx"));
	}
}
{% endhighlight %}

## Using Parameters

You can use parameters to control certain behaviors of a slide's execution without needing to change the slide's content. Suppose you have created a slide like below and saved it as [hellouser.pptx](/pptx/hellouser.pptx). 

<img src="/img/hellouser.jpg" class="half img-polaroid">

Note that this is similar to the Hello World example above, except that the second word in the message is parameterized as `<user>`. To define a parameter, simply enclose the name of the parameter by `<` and `>`. 

You can use a `Context` object to provide values for the parameters while executing the slides. Below is the example code for using a context object to provide parameter values.
{% highlight java %}
Context context = new Context();
context.addParameter("name", "Sikuli");		
		
Slides.execute(new File("hellouser.pptx"), context);
{% endhighlight %}


Here is another example that takes a username and a password as parameters to fill in a login form automatically.
The presentation file is [login.pptx](/pptx/login.pptx). Its content is shown below.

<img src="/img/login_username.jpg" class="half img-polaroid">
<img src="/img/login_password.jpg" class="half img-polaroid">

The code to execute this file with parameter values is shown below.

{% highlight java %}
Context context = new Context();
context.addParameter("username", "user2142");
context.addParameter("password", "cdads2ev");
		
Slides.execute(new File("login.pptx"), context);

{% endhighlight %}


## Selecting Certain Slides to Execute

By default, `Slides.execute` executes all the slides in a given .pptx file. Often times you may want the flexibility to choose which slides to execute. For instance, you may have a long series of 20 slides and you may want to execute slide 10 to 12. There are several ways to accomplish this.

1. **Copy&Paste** Use a presentation editor to create a new presentation file. Copy slide 10 to 12 from the original file to this new file. Execute this file instead.

2. **Filter** Create an object that implements the `ExecutionFilter` interface. Assign this selector object to a `Context` object. Execute the file under this context object.

{% highlight java %}

Context context = new Context();
context.setExecutionFilter(new ExecutionFilter(){
	@Override
	public boolean accept(ExecutionEvent event) {
		Slide slide = event.getSlide();
		// accept only slides 10 to 12
		return slide.getNumber() >= 10 && slide.getNumber() <= 12;
	}
});
Slides.execute(new File("20_slides.pptx"), context);
{% endhighlight %}

Note that `slide.getNumber()` returns the slide's number in the order of presentation. This number is one-based.

## Handling Exceptions

Execution of slides does not always succeed. A `SlideExecutionException` is thrown when Sikuli Slides is unable to perform an action defined on a particular slide. The most common error is when a target marked on the slide can not be found. Other errors are possible. The code below gives an example of how one may catch and print out useful information about this exception, such as the slide number and the failed action.

{% highlight java %}
try {
	Slides.execute(new File("login.pptx"));
}catch (SlideExecutionException e) {
	System.err.println("Failed to execute slide no. " + e.getSlide().getNumber());
	System.err.println(" because " + e.getMessage());			
	System.err.println(" action: " + e.getAction());
}
{% endhighlight %}

## Executing on Another Monitor

If you have the luxury of working with multiple monitors, sometimes you may wish to choose a monitor to execute slides. To do so, you will create a `Context` object and set it to use a `DesktopScreenRegion` on the monitor of your choice. The code below shows how to set the execution context to use the entire screen region on the secondary monitor (screen id = 1). When executed, the "Hello World" message will be displayed on your secondary monitor.

{% highlight java %}
ScreenRegion anotherScreen = new DesktopScreenRegion(1);		
Context context = new Context();
context.setScreenRegion(anotherScreen);
Slides.execute(new File("helloworld.pptx"), context);		
{% endhighlight %}