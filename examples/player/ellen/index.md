---
layout: page
---

## UI

URL: [Ellen's Oscar Selfie](https://twitter.com/TheEllenShow/status/440322224407314432/photo/1)

<a href="https://twitter.com/TheEllenShow/status/440322224407314432/photo/1">
{% include figure.html src="screen.png" %}
</a>

## Slides

Powerpoint: [ellens-selfie.pptx](ellens-selfie.pptx)

<div class="section portfolio">
	{% for x in (1..4) %}
	<div class="work">
		<img src="Slide{{x}}.png" alt="">	
		<div class="mask">
		Slide {{ x }}
		</div>
	</div>
	{% endfor %}
</div>

