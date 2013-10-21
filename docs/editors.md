---
layout: docs
title: Editors
prev_section: usage
next_section: actions
permalink: /docs/editors/
---

Sikuli Slides can understand slides made by Microsoft Powerpoint or Google Presentation. You can use either editing tool to make your slides.  Chances are you are already familiar with these tools. This is one of the  advantages of Sikuli Slides. There is no need to learn a new programming editor or IDE! Just make slides as you did before. Just make sure you save your slides in the `.pptx` format.

### Online Editor: Google Presentation 

1. Open the helloworld example in the Google Presentation editor. Use the following link: [helloworld](https://docs.google.com/presentation/d/1w48gExh5oLIT0J8xYXR1RxpqTrZTXJC8OR4UXxShTQ8/edit?usp=sharing).	
2. Make a copy so you can edit.
3. On Slide 1, change the URL to the URL of your own website.

   <img src="/img/gdrive_slide1.png"  class="half img-polaroid"/>
   <img src="/img/gdrive_change_url.png"  class="half img-polaroid"/>

4. On Slide 2, change the screenshot to one of your own website. 

   <img src="/img/gdrive_slide2.png"  class="half img-polaroid"/>
   <img src="/img/gdrive_change_screenshot.png"  class="half img-polaroid"/>

5. Adjust the location and size of the red rectangle to cover the target
   to click, in this case, the "Contact" tab.

   <img src="/img/gdrive_change_screenshot.png"  class="half img-polaroid"/>
   <img src="/img/gdrive_adjust_box.png"  class="half img-polaroid"/>

6. Change the Sharing setting to "Anyone who has the link can access. No sign-in required." and locate the "Link to Share" URL.

   <img src="/img/gdrive_link_to_share.png"  class="half img-polaroid"/>

7. Execute your slides from the command line. Use the "Link to Share" URL as the argument.

{% highlight bash %}
$ {{site.slides.executable}} execute https://docs.google.com/presentation/d/1bODdu4SOD49Z_i9Sq7qJpwmxbnnMx6ULvgNc3wQGYfw/edit?usp=sharing
{% endhighlight %}


### Offline Editor: Microsoft Powerpoint

If you wish to edit the slides offline, you can use Microsoft Powerpoint.

1. Download the helloworld example slides as a .pptx file: [helloworld.pptx](https://docs.google.com/feeds/download/presentations/Export?id=1w48gExh5oLIT0J8xYXR1RxpqTrZTXJC8OR4UXxShTQ8&&exportFormat=pptx)
2. Open the file in Microsoft PowerPoint. It must be a version that supports the `.pptx` format.
3. On Slide 1, change the URL to your the URL of your own website.

   <img class="half img-polaroid" src="/img/powerpoint_slide1.png"/>
   <img class="half img-polaroid" src="/img/powerpoint_change_url.png"/>

4. On Slide 2, change the screenshot to one of your own website. 

   <img class="half img-polaroid" src="/img/powerpoint_slide2.png"/>
   <img class="half img-polaroid" src="/img/powerpoint_change_screenshot.png"/>

5. Adjust the location and size of the red rectangle to cover the target
   to click, in this case, the "Contact" tab.

   <img class="half img-polaroid" src="/img/powerpoint_change_screenshot.png"/>
   <img class="half img-polaroid" src="/img/powerpoint_adjust_box.png"/>

6. Execute your slides from the command line. Use the .pptx file name as the argument.

{% highlight bash %}
$ {{site.slides.executable}} execute helloworld.pptx 
{% endhighlight %}


