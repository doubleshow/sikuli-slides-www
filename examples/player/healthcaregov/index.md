---
layout: page
---

## UI

URL: [Healthcare.gov](https://www.healthcare.gov/)

<a href="https://www.healthcare.gov/">
{% include figure.html src="screen.png" %}
</a>

## Slides

Powerpoint: [step-by-step.pptx](step-by-step.pptx)

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

