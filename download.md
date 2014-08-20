---
layout: page
title: Download
permalink: /download/
---

## Latest - 1.5.0

<div class="section">
        <div class="col span_2_of_12">
            <h3 class="color">Installers</h3>
        </div>
        <div class="col span_9_of_12">
        	<a href="https://dl.dropboxusercontent.com/u/5104407/slides.sikuli.org/download/sikuli-slides_windows-x64_1_5_0.exe" 
			onClick="_gaq.push(['_trackEvent', 'Downloads', 'Download', 'sikuli-slides_windows-x64_1_5_0.exe'])"
        	class="button"><i class="icon-windows" style="font-size:100%;"></i> Windows (64bits)</a>
			<a href="https://dl.dropboxusercontent.com/u/5104407/slides.sikuli.org/download/sikuli-slides_windows_1_5_0.exe" 
			onClick="_gaq.push(['_trackEvent', 'Downloads', 'Download', 'sikuli-slides_windows_1_5_0.exe'])"
			class="button"><i class="icon-windows" style="font-size:100%;"> </i> Windows (32bits)</a> 
        	<a href="https://dl.dropboxusercontent.com/u/5104407/slides.sikuli.org/download/sikuli-slides_macos_1_5_0.dmg" 
        	onClick="_gaq.push(['_trackEvent', 'Downloads', 'Download', 'sikuli-slides_macos_1_5_0.dmg'])"
        	class="button"><i class="icon-apple" style="font-size:100%;"></i> Mac (64bit)</a>
        </div>
</div>

<div class="section">
        <div class="col span_2_of_12">
            <h3 class="color">Java</h3>
        </div>
        <div class="col span_9_of_12">
        	<a href="https://dl.dropboxusercontent.com/u/5104407/slides.sikuli.org/download/sikuli-slides-1.5.0.jar" 
			onClick="_gaq.push(['_trackEvent', 'Downloads', 'Download', 'sikuli-slides-1.5.0.jar'])"
        	class="button">Executable Jar</a>
        	<a href="https://dl.dropboxusercontent.com/u/5104407/slides.sikuli.org/download/sikuli-slides-api-1.5.0.jar" 
        	onClick="_gaq.push(['_trackEvent', 'Downloads', 'Download', 'sikuli-slides-api-1.5.0.jar'])"
        	class="button">API (without dependency)</a>        	
        </div>
</div>


<div class="section">
        <div class="col span_2_of_12">
            <h3 class="color">Maven</h3>
        </div>
        <div class="col span_9_of_12">
{% highlight html %}

<dependency>
	<groupId>org.sikuli</groupId>
	<artifactId>sikuli-slides-api</artifactId>
	<version>{{site.slides.version}}</version>
</dependency>

{% endhighlight %}
        </div>
</div>

### Requirements
* **Windows and Mac OS X**: Java Runtime Environment (JRE) version 1.6 or newer.
* **Linux**: Oracle Java Runtime Environment (JRE) version 1.7.

---

## 1.4.0

* [Execute via GUI](/docs/gui). Once you've installed Sikuli Slides on your systems, you can open `.pptx` files the Windows Explorer or the Finder to execute them. Installers are created by ![install4j](/img/install4j.png).
* [Parameters](/docs/parameters). You can add parameters to actions and provide the values for these parameters at the execution time, for example, using 
a parameter to control what password to type dynamically.
* [Control tags](/docs/controls) `Skip`, `Optional`, `Bookmark`, and `Tag`. You can use them to control the flow of execution.
* [Recorder](/docs/recorder). You can record a sequence of clicks and automatically produce a sequence of slides that can then be executed by Sikuli Slides.
* [Sikuli Slides Java API](/docs/api). You can integrate Sikuli Slides' features into your own applications or testing frameworks.
* [Code Generation](/docs/code). You can make slides and have them automatically converted into Java code, which you can then customize further to fit your needs. Other target languages (e.g., python, ruby) will be available in the next release.


## 1.3.0

* New GUI.
* Three running modes: automation, help, and tutorial mode.
* Execute remote presentation slides. This includes the ability to execute Google Presentation stored in your Google Drive (formerly known as Google Docs), and .pptx files in DropBox.
* Added multiple monitors support.
* New delay action. The wait time unit can be in microseconds, milliseconds, seconds, minutes, hours, or even days. This can be used to make delay interval between two slides.
* Store user settings persistently in user preferences.
* Play .wav audio files.
* Display Caption/Label on the screen using any shape in a yellow background.
* Added Linux 32 and 64 bit support.
* Many bug fixes.

## 1.2.0

* New syntax: Use any shape as a target image and text box as an input action. You can specify the user input action in a separate text box and the target images using any shape, so there is no need to memorize the meaning of each shape. This makes sikuli-slides more easy and customizable so users can customize the meaning of each shape.
* Add multiple targets per slide support but with one input action per slide. For example, you can perform left click action on multiple targets in one slide.
* Set the order of performing input actions. If you have multiple targets on the screen, you can specify the order in which the action is executed by inserting the numeric order into the shape.
* Sound support: Play sound while running your visual automation. This allows you to add more informative and interactive experience for your automation as well as to test voice recognition applications.
* Text annotation: Display an overlay text on the screen. This can be an effective way to display informative text on the screen.
* Add new visual testing operations that can be used to know whether something is visible on the screen or not.
* Exist: check whether the target image is visible on the screen.
* Not Exist: check whether the target image is invisible on the screen.

## 1.1.0

* Detect identical targets on the screen: added new algorithm that uniquely identifies a target among identical targets on the screen such as checkboxes, radio buttons, etc.
* Added double click action using frame shape.
* Bug fixes.