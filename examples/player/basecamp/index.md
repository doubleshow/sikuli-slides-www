---
layout: page
---

## UI

URL: [Basecamp Signup Form](https://basecamp.com/start)

<a href="https://basecamp.com/start">
{% include figure.html src="screen.png" %}
</a>

## Slides

Powerpoint: [basecamp-signup.pptx](basecamp-signup.pptx)

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

