---
layout: page
title: Jazz
---
<p> Tags:
	{% for tag in site.tags -%}
		{% capture tag_name %}{{ tag | first }}{% endcapture %}
		{%- if tag_name != "jazz" and forloop.index > 1 -%}
			, <a href="/tag/{{ tag_name }}">{{ tag_name }}</a>
		{%- elsif tag_name != "jazz" -%}
			<a href="/tag/{{ tag_name }}">{{ tag_name }}</a>
		{%- endif -%}
	{%- endfor -%}
</p>
<ul class="posts">
  {% for post in site.categories['jazz'] %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li itemscope>
      <a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
      <p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>
    </li>

  {% endfor %}
</ul>