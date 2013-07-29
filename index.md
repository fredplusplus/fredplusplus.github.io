---
layout: page
title: Home
tagline:  == 127.0.0.1
---
{% include JB/setup %}

{% for post in site.posts %}
<div>
	<h3><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h3>    
	<span>{{ post.date | date_to_string }}</span>
	{{ post.content |strip_html |truncatewords:30}}<br>
	<a href="{{ post.url }}">Read more...</a><br><br>
	<hr/>
</div>
{% endfor %}
