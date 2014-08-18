---
layout: docs
title: JRuby
prev_section: api
next_section: code
permalink: /docs/jruby/
---

You can execute Sikuli Slides using JRuby. The *helloworld* program only takes two lines:

{% highlight ruby %}
# helloworld.rb
require 'sikuli-slides'
Sikuli::Slides.execute "helloworld.pptx"
{% endhighlight %}

## Installation

You must first install [JRuby](http://jruby.org/download) and [RubyGems](http://rubygems.org/) on your system. Then, you can do the following to install Sikuli Slides and run the *helloworld* program.

Install the Sikuli Slides Gem. It will download and install everything you need.   
{% highlight bash %}
$ jruby -S gem install sikuli-slides
{% endhighlight %}
    
Tell JRuby to run in the 1.9 mode
{% highlight bash %}
$ export JRUBY_OPTS=--1.9
{% endhighlight %}

Run *helloworld.rb*
{% highlight bash %}
$ jruby helloworld.rb
{% endhighlight %}

## Parameters

`Sikuli::Slides.execute` is the main entry point of Sikuli Slides's JRuby API. You can provide extra hash arguments to control various aspects of the execution.

{% highlight ruby %}

# Execute with the parameter <user>'s value set to "Sikuli"
Sikuli::Slides.execute "hellouser.pptx", :params => {:user => "Sikuli"}

# Execute on another screen (id = 1)
Sikuli::Slides.execute "10steps.pptx", :screen => 1

# Execute starting from slide number 5 (one-based)
Sikuli::Slides.execute "10steps.pptx", :start => 5

# Execute starting from the slide that has the bookmark 'foo'
Sikuli::Slides.execute "10steps.pptx", :start => "foo"

# Execute with the minimum similarity score set to 0.9
Sikuli::Slides.execute "10steps.pptx", :minScore => 0.9

# Execute with the time to wait for the next target to 3000ms
Sikuli::Slides.execute "10steps.pptx", :waitTime => 3000

# Execute with the log level set to OFF
# other options are: (ALL, TRACE, DEBUG, INFO, WARN, ERROR, OFF)
Sikuli::Slides.execute "10steps.pptx", :logLevel => 'OFF'

{% endhighlight %}

## Example: Currency Conversion

### Code
{% highlight ruby %}
require 'sikuli-slides'

# location to the online currency converter
Sikuli::API.browse "http://www.xe.com/currencyconverter/#converter"

# location to download slides
slidesUrl = "http://slides.sikuli.org/examples/player/xe/convert.pptx"

# execute the slides 10 times
10.times do 
  # each time, a random number between 1 and 1000 is generated
  x = (1..1000).to_a.sample

  # this number is given as a parameter to the slides
  Sikuli::Slides.execute slidesUrl, :params => {:amount => x}
end
{% endhighlight %}

### Slides
<div class="section portfolio">
  {% for x in (1..4) %}
  <div class="work">
    <img src="/examples/player/xe/convert/Slide{{x}}.png" alt=""> 
    <div class="mask">
    Slide {{ x }}
    </div>
  </div>
  {% endfor %}
</div>

## Example: Hello Adam, Ben, Cindy

### Code
{% highlight ruby %}
hellouser.pptx
["Adam","Ben","Cindy"].each do |name|
  Sikuli::Slides.execute "hellouser.pptx", :params => {:user => name}
end
{% endhighlight %}

### Slides
<div class="section">
<img src="/img/hellouser.jpg" class="col span_5_of_12 img-polaroid">
</div>

<!-- ### Dictionary Attack

<div class="section">
<img src="/img/dictattack1.jpg"  class="col span_3_of_12 img-polaroid"/>
<img src="/img/dictattack2.jpg"  class="col span_3_of_12 img-polaroid"/>
<img src="/img/dictattack3.jpg"  class="col span_3_of_12 img-polaroid"/>
<img src="/img/dictattack4.jpg"  class="col span_3_of_12 img-polaroid"/>
</div>


{% highlight ruby%}
# login.pptx
# dictionary is an array of words
dictionary.each do |word|
  begin
    # execute the login steps as the admin and a word in the dictionary as the guessed password
    Sikuli::Slides.execute "login.pptx", :params => {:user => "admin", :password => word}
    # the "success" message is found. No exception was raised.
    puts "Dictionary attack is successful!"
    return
  rescue TargetNotFound => e    
	# an exception was raised because the "success" message is not found.
  end
end
{% endhighlight %} -->

