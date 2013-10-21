---
layout: docs
title: Command Line
prev_section: recorder
next_section: gui
permalink: /docs/cmd/
---

To execute slides (e.g., [helloworld.pptx](/pptx/helloworld.pptx)), type the following in the command line:

{% highlight bash %}
$ {{site.slides.executable}} execute helloworld.pptx 
{% endhighlight %}

## Executing Remote Files

If the file is hosted on a remote web server, you can execute it by supplying the URL to that remote file as an argument. Sikuli Slides will try to download the file for you and executing it. For instance, suppose helloworld.pptx is hosted at the URL  [http://silides.sikuli.org/helloworld.pptx](http://silides.sikuli.org/helloworld.pptx), you can execute this remote file as follows:

{% highlight bash %}
$ {{site.slides.executable}} execute http://slides.sikuli.org/helloworld.pptx 
{% endhighlight %}

If the file is a Google Presentation hosted on Google Drive, you can execute it by supplying its public sharing link. Make sure you have already set the file's sharing setting as "Anyone who has the link can **view**". This enables Sikuli Slides to download the file for you.

{% highlight bash %}
$ {{site.slides.executable}} execute https://docs.google.com/presentation/d/1w48gExh5oLIT0J8xYXR1RxpqTrZTXJC8OR4UXxShTQ8/edit?usp=sharing
{% endhighlight %}


## Options

There are several command line options that can be set to control the execution behavior of Sikuli Slides.

<table>
  <thead>
    <tr>
      <th>Option</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>-minscore</code></p></td>
      <td><p>The minimum similarity score for a target to be considered as a match. 
	It's a 10-point scale where 1 is the least precise search and 10 is the most precise search (default is 7).</p></td>
    </tr>
    <tr>
      <td><p><code>-screen</code></p></td>
      <td><p>The id of the connected screen/monitor (default is 0).</p></td>
    </tr>
    <tr>
      <td><p><code>-wait</code></p></td>
      <td><p>The maximum time to wait in milliseconds to find a target on the screen ( 
                              default is 5000).</p></td>
    </tr>
    <tr>
      <td><p><code>-parameters</code></p></td>
      <td><p>Parameters as name=value pairs joined by semi-colons. See 
                              <a href="/docs/parameters/">Parameters</a> for more details.</p></td>
    </tr>
    <tr>
      <td><p><code>-range</code></p></td>
      <td><p>The range of the slide(s) to execute. For instance,</p>
	<ul>
		<li><code>-range 1</code><p> executes only slide 1</p></li>
		<li><code>-range 2-4</code><p> executes slide 2 to 4</p></li>
		<li><code>-range 2-</code><p> executes slide 2 till the end</p></li>
	</ul>
		<p>Note that the slide number is 1-based.</p>
	</td>
    </tr>
    <tr>
      <td><p><code>-bookmark</code></p></td>
      <td><p>The bookmark from which to start executing.</p></td>
    </tr>
    <tr>
      <td><p><code>-log</code></p></td>
      <td><p>The level of log messages to print to the console. Choices are ALL, TRACE, DEBUG, INFO, WARN, ERROR, OFF (default: INFO).</p></td>
    </tr>
  </tbody>
</table>