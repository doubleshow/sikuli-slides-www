---
layout: docs
title: Actions
prev_section: editors
next_section: parameters
permalink: /docs/actions/
---

This page gives a comprehensive overview of all the actions supported by Sikuli Slides.

## Click

Execute a mouse left click action on a target. To define a click action,  write the word `click` in a text box and draw a rectangle around the target. The word is *not* case sensitive. You can style the text box and the rectangle using any font, color, or line width.

<img src="/img/click1.jpg" class="one-third img-polaroid">
<img src="/img/click2.jpg" class="one-third img-polaroid">
<img src="/img/click3.jpg" class="one-third img-polaroid">

---

## Right Click

Execute a mouse right click action on a target. To define a right-click action, write the word `right click` in a text box. You can also write aliases such as `right-click` or `rightclick`. Then, draw a rectangle around the target.

<img src="/img/rightclick1.jpg" class="one-third img-polaroid">
<img src="/img/rightclick2.jpg" class="one-third img-polaroid">
<img src="/img/rightclick3.jpg" class="one-third img-polaroid">

---

## Double Click

Execute a mouse double click action on a target. To define a double-click action, write the word `double click` in a text box. You can also write aliases including `double-click` or `doubleclick`. Then, draw a rectangle around the target.

<img src="/img/doubleclick1.jpg" class="one-third img-polaroid">
<img src="/img/doubleclick2.jpg" class="one-third img-polaroid">
<img src="/img/doubleclick3.jpg" class="one-third img-polaroid">

---

## Type

Type a string in a target. To define a type action, write the word `type` in a text box. In the same text box, write the string that should be typed after the word *type*. Then, draw a rectangle around the input target. Another way to specify what string to type is to write it in another text box, like the third example below.

<img src="/img/type1.jpg" class="one-third img-polaroid">
<img src="/img/type2.jpg" class="one-third img-polaroid">
<img src="/img/type3.jpg" class="one-third img-polaroid">

---

## Drag and Drop

Drag a target and drop it onto another destination target. To define a drag and drop action, create two slides. On the first slide, write the word `drag` in a text box, insert a screenshot, and draw a rectangle around the target to drag. On the second slide, write the word `drop` in a text box, insert a screenshot, and draw a rectangle around the destination target.

<img src="/img/dragdrop1.jpg" class="one-third img-polaroid">
<img src="/img/dragdrop2.jpg" class="one-third img-polaroid">
	
---

## Caption		

Display caption text on the screen. To define a caption action, write the caption text in a text box. As long as the text does not start with one of the other action words, it will be interpreted as a caption. You can place multiple captions on the same slide.

 * **Styling:** You can specify the style of the text box using any font size, color, and background. Sikuli Slides will try to render the caption following the style you've specified as closely as possible.

 * **Relative Positioning:** A caption can be positioned based on its relative location within a slide. For instance, if a caption is placed close to the center of a slide, it will be displayed also close to the center of the screen, like the first example below.

	*Slides*
	
   <img src="/img/caption_pos_slide1.jpg" class="one-third img-polaroid">
   <img src="/img/caption_pos_slide2.jpg" class="one-third img-polaroid">
   <img src="/img/caption_pos_slide3.jpg" class="one-third img-polaroid">

	*Screen during execution*
	
   <img src="/img/caption_pos_screen1.jpg" class="one-third img-polaroid">
   <img src="/img/caption_pos_screen2.jpg" class="one-third img-polaroid">
   <img src="/img/caption_pos_screen3.jpg" class="one-third img-polaroid">


 * **Target Positioning:** A caption can be positioned relative to a target. In the first example below, a caption *UN's LOGO* is placed to the right of a logo on the slide. When the slide is executed, the logo will first be identified on the screen and the caption will be shown in the same relative position to the right of the logo. 

   <img src="/img/caption3.jpg" class="one-third img-polaroid">
   <img src="/img/caption2.jpg" class="one-third img-polaroid">
   <img src="/img/caption1.jpg" class="one-third img-polaroid">

   Sikuli Slides determines whether a caption is associated with a target based on proximity. If a caption is not near any target on a slide, it will be positioned based on its relative location within the slide. In the example below, the caption *WIKI's LOGO* is positioned based on the image of WIKI's logo as a target. On the other hand, the caption *Hello World* is not near a target. It is positioned close to the bottom of the screen.

   <img src="/img/caption_pos_mixed1.jpg" class="half img-polaroid">
   <img src="/img/caption_pos_mixed2.jpg" class="half img-polaroid">


---

## Wait		

Wait for a target to appear before proceeding to the next slide. To define a caption action, write the word `Wait` in a text box, insert a screenshot, and draw a rectangle around a target. By default, it waits for 10 seconds for the target to appear. The wait time can be specified by writing the amount of time following the action word in the same text box. Alternatively, the wait time can be written in another text box.

<img src="/img/wait1.jpg" class="one-third img-polaroid">
<img src="/img/wait2.jpg" class="one-third img-polaroid">
<img src="/img/wait3.jpg" class="one-third img-polaroid">

---

## Browser 
	
Open a web page in the default web browser. To define a browser action, write the word `Browser` in a text box followed by an URL. Alternatively, the URL can be written in a separate text box.

<img src="/img/browser1.jpg" class="one-third img-polaroid">

---

## Delay

Delay the execution by some amount of time. To define a delay action, write the word `Delay` or `Sleep` in a text box followed by the amount and time unit. The time unit can be in milliseconds, seconds, minutes, or hours. If no unit is given explicitly, it is default to seconds.

<img src="/img/delay1.jpg" class="one-third img-polaroid">
<img src="/img/delay2.jpg" class="one-third img-polaroid">
<img src="/img/delay3.jpg" class="one-third img-polaroid">

---


## Exist

Check if a target exists. If the target *cannot* be found, slides execution is aborted. It can be used to test if the right picture or message is shown after a certain event (e.g., clicking a tab).

<img src="/img/exist1.jpg" class="one-third img-polaroid">
<img src="/img/exist2.jpg" class="one-third img-polaroid">
<img src="/img/exist3.jpg" class="one-third img-polaroid">

---
	
## Not Exist

Check if a target does not exist. If the target *can* be found, slides execution is aborted. It can be used to check if contents that are supposed to disappear after a certain event (e.g., clicking another tab) indeed becomes invisible

<img src="/img/notexist1.jpg" class="one-third img-polaroid">
<img src="/img/notexist2.jpg" class="one-third img-polaroid">
<img src="/img/notexist3.jpg" class="one-third img-polaroid">
