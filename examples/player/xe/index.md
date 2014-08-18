---
layout: page
---

## UI

URL: [XE Currency Converter](http://www.xe.com/currencyconverter/)

<a href="http://www.xe.com/currencyconverter/">
{% include figure.html src="screen.png" %}
</a>

## Slides

Powerpoint: [convert-two.pptx](convert-two.pptx)

<div class="section portfolio">
	{% for x in (1..8) %}
	<div class="work">
		<img src="Slide{{x}}.png" alt="">	
		<div class="mask">
		Slide {{ x }}
		</div>
	</div>
	{% endfor %}
</div>

