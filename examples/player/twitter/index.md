---
layout: page
---

## UI

URL: [Twitter Search](https://twitter.com/search-home
)

<a href="https://twitter.com/search-home">
{% include figure.html src="screen.png" %}
</a>

## Slides

Powerpoint: [twitter-search.pptx](twitter-search.pptx)

<div class="section portfolio">
	{% for x in (1..2) %}
	<div class="work">
		<img src="Slide{{x}}.png" alt="">	
		<div class="mask">
		Slide {{ x }}
		</div>
	</div>
	{% endfor %}
</div>

