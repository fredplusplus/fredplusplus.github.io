---
layout: page
title: Home
tagline:  == 127.0.0.1
---
{% include JB/setup %}


{% for post in site.posts %}
<div>
	<h2><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h2>    
	<span>{{ post.date | date_to_string }}</span>
	{{ post.content |strip_html |truncatewords:10}}<br>
	<a href="{{ post.url }}">Read more...</a><br><br>
	<hr/>
</div>
{% endfor %}
