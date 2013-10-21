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

You must first install [JRuby](http://jruby.org/download) and [RubyGems](http://rubygems.org/) on your system. Then, you can do the following to install Sikuli Slides and run the *helloworld* program.

1. Install the Sikuli Slides Gem. It will download and install everything you need.   
    {% highlight bash %}
$ jruby -S gem install sikuli-slides
{% endhighlight %}
    
2. Tell JRuby to run in the 1.9 mode
    {% highlight bash %}
$ export JRUBY_OPTS=--1.9
{% endhighlight %}

3. Run *helloworld.rb*
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


## More Examples


### Hello Adam, Ben, Cindy

<img src="/img/hellouser.jpg" class="one-third polaroid">

hellouser.pptx

{% highlight ruby %}
["Adam","Ben","Cindy"].each do |name|
  Sikuli::Slides.execute "hellouser.pptx", :params => {:user => name}
end
{% endhighlight %}


### Dictionary Attack

<img src="/img/dictattack1.jpg"  class="unit one-quarter img-polaroid"/>
<img src="/img/dictattack2.jpg"  class="unit one-quarter img-polaroid"/>
<img src="/img/dictattack3.jpg"  class="unit one-quarter img-polaroid"/>
<img src="/img/dictattack4.jpg"  class="unit one-quarter img-polaroid"/>

login.pptx

{% highlight ruby%}
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
{% endhighlight %}

