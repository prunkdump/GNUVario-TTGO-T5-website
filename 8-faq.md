---
layout: default
title: FAQ
description: FAQ
css-add: accordion
---

**FAQ**. Ceci est la liste des questions les plus souvent posées.

<section class="faq">
	{% for item in site.faq %}
	  <button class="accordion">{{ item.description }}</button>
	  <div class="panel">
	    {{ item.content | markdownify }}
	  </div>
	{% endfor %}
</section>
