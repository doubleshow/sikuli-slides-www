---
layout: page
---

## UI

URL: [Charlie bit my finger - again !](https://www.youtube.com/watch?v=_OBlgSz8sSM)

<a href="https://www.youtube.com/watch?v=_OBlgSz8sSM">
{% include figure.html src="screen.png" %}
</a>

## Slides

Powerpoint: [charlie-ouch.pptx](charlie-ouch.pptx)

<div class="section portfolio">
	{% for x in (1..6) %}
	<div class="work">
		<img src="Slide{{x}}.png" alt="">	
		<div class="mask">
		Slide {{ x }}
		</div>
	</div>
	{% endfor %}
</div>

