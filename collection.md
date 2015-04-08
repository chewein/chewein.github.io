---
layout: page
title: 收藏
---
<div class="page-collection">

{% assign collection = site.mycollection | group_by: "category" %}

{% for group in collection %}
  <h1 class="category-name" id="{{group.name]}}" name="{{group.name}}">{{ group.name | date: "%-d %B %Y" }}</h1>
  <ul>
    {% for post in group.items %}
	    <div class="article">
        <span class="datetime">{{ post.date | date:"%Y-%m-%d" }} </span>
        <a href="{{ post.url }}">{{ post.title }}</a>
	    </div>
    {%endfor%}
  </ul>
{%endfor%}


</div>


