---
layout: docs
title: Basic Usage
prev_section: installation
next_section: editors
permalink: /docs/usage/
---

Here is our Hello World example to demonstrate Sikuli Slides' basic usage.
This example has two slides, made using the Google Presentation. When executed, a robot will
1. Open the browser and go to the United Nations' website [http://www.un.org/en](http://www.un.org/en).
2. Find and click the logo of the United Nations.

<iframe src="https://docs.google.com/presentation/d/1w48gExh5oLIT0J8xYXR1RxpqTrZTXJC8OR4UXxShTQ8/embed?start=false&amp;loop=false&amp;delayms=3000" frameborder="0" width="400" height="300" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true">
</iframe>

There are two methods to open the slides and execute them on your own computer.

**Method 1:** Download, Open, and Execute

1. Download the slides from this link:
[helloworld.pptx](https://docs.google.com/feeds/download/presentations/Export?id=1w48gExh5oLIT0J8xYXR1RxpqTrZTXJC8OR4UXxShTQ8&&exportFormat=pptx)

2. Open and execute the slides

{% highlight bash %}
$ {{site.slides.executable}} execute helloworld.pptx 
{% endhighlight %}


**Method 2:** Open and execute from an URL

{% highlight bash %}
$ {{site.slides.executable}} execute https://docs.google.com/presentation/d/1w48gExh5oLIT0J8xYXR1RxpqTrZTXJC8OR4UXxShTQ8/edit?usp=sharing
{% endhighlight %}
