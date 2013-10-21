---
layout: docs
title: Controls
prev_section: parameters
next_section: recorder
permalink: /docs/controls/
---

Sikuli Slides is most suited for describing interactions that follow a linear pattern, that is, interactions that have a well-defined sequence of steps. Each slide represents a step. A deck of slides are executed from the beginning to the end. In certain situations, however, one might need to break away from this linear pattern. To support this, Sikuli Slides provides the following set of control tags.

---

## Skip

A `Skip` tag tells Sikuli Slides to skip the action on this slide. This tag is useful when you  want to exclude a slide from execution but you don't want to permanently delete the slide from the file. In programmers' terminology, it is similar to *commenting out* a line of code.

Consider the four slides below. Upon seeing the `Skip` tag on slide 3, Sikuli Slides will simply ignore it and continue to slide 4.

<img src="/img/skip.jpg" class="whole img-polaroid">

---

## Optional

An `Optional` tag indicates that the action on this slide is optional. If the action fails, the execution continues instead of aborting.

Suppose this is the screen you are currently seeing.

<img src="/img/optional_screen.jpg" class="one-third img-polaroid">

Consider the four slides below, designed to test the existence of four icons.
<img src="/img/optional1.jpg" class="whole img-polaroid">
The execution of these slides will succeed on the first two slides but fail on the third slide. The third slide checks whether the *Gmail* icon exists but the icon is not visible on the screen. The execution is aborted because of this failure.

An `Optional` tag will change this abort-on-failure behavior. Let us add it to the third slide.

<img src="/img/optional2.jpg" class="whole img-polaroid">
When executing the third slide, Sikuli Slides will attempt to find the *Gmail* icon like before. But if it fails to find it, it will not stop the execution. Instead, it will continue to the next slide. Why is it useful? Suppose you anticipate that the *Gmail* icon may sometimes go missing. You want the execution to continue to check the other elements rather than giving up. Thus, it makes sense to make the checking of *Gmail* icon on slide 3 optional.

---

## Bookmark

A `Bookmark` tag inserts a bookmark into a slide. Each bookmark is associated with a name. The name of the bookmark should be specified right after the keyword, for instance, `bookmark a`. The name of the bookmark is *not* case-sensitive. Bookmark tags are useful when you wish to jump directly to a particular slide indicated by its bookmark name. 

Consider the four slides below (four.pptx). A tag `BOOKMARK A` is placed on the third slide. By default, the slides are still executed from the start to the end.
<img src="/img/bookmark1.jpg" class="whole img-polaroid">

But now you can tell Sikuli Slides that you want to start executing from the slide with the bookmark, for instance, using the command-line option `bookmark` like below:

{% highlight bash %}
$ {{site.slides.executable}} execute four.pptx -bookmark a
{% endhighlight %}

Sikuli Slides will keep skipping slides until it finds the first slide with the bookmark whose name is *A*.

<img src="/img/bookmark2.jpg" class="whole img-polaroid">


---

## Pause

A `Pause` tag indicates that the execution should pause at the slide *before* the action on the slide is executed. When paused, a button will appear in the lower-right corner of the screen, like below. 

<img src="/img/pause.png" class="half img-polaroid">

To continue, you need to move the mouse cursor over there. This tag is useful if you want to intervene at some point during the execution, such as entering a password yourself or reading the text on the screen. When you are done, you can let the computer take over the control again, by moving the mouse to continue. For programmers, it is similar to adding a *break point* to a slide to stop execution at that point in order to debug.

