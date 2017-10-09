---
layout: page
title: Blog archive
---
<div class="page-content wc-container">
	<div class="post">
		<h1>Blog Archive</h1>  
		{% for post in site.posts %}
			{% assign currentdate = post.date | date: "%Y" %}
			{% if currentdate != date %}
				{% unless forloop.first %}</ul>{% endunless %}
				<h3 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h3>
				<ul>
				{% assign date = currentdate %}
			{% endif %}
			<li><a href="{{ post.url | prepend: site.baseurl | prepend: site.url }}">{{ post.title }}</a></li>
			{% if forloop.last %}</ul>{% endif %}
		{% endfor %}
	</div>
</div>