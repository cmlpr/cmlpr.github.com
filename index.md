---
layout: page
title: Welcome!
tagline: Internet person
---
{% include JB/setup %}

I blog about `everything` when there is time..

My github [profile](http://www.github.com/cmlpr)

## Trying a code sample

    $ echo "Hello" > hello.html

A short list of my posts:

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## Recently published posts:

{% for post in site.posts offset: 0 limit: 50 %}
<div class="container-narrow">
  <div class="span7">    
    <div class="container-narrow">
      <div class="span2">
        <a href="{{ post.url }}" >
            <img border="0" width="250" height="150" src="/images/posts/{{ post.image }}" alt="">
        </a>
      </div>
      <div class="span5">
        <h4><strong><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></strong></h4>      
        <p>
          {{ post.summary }}
        </p>
        {{ post.excerpt }} 
        <p>
          <span class="glyphicon glyphicon-calendar"></span> {{ post.date | date: "%B %e, %Y" }}
          | <span class="glyphicon glyphicon-comment"></span> <a href="{{ BASE_PATH }}{{ post.url }}#disqus_thread" data-disqus-identifier="{{ post.url }}"> Comments </a> | <span class="glyphicon glyphicon-tags"></span> Tags :{% for tag in post.tags %} <a href="/tags/{{ tag }}" rel="tooltip" title="View posts tagged with &quot;{{ tag }}&quot;"><span class="label label-info">{{ tag }}</span></a>  {% if forloop.last != true %} {% endif %} {% endfor %}               
        </p>
        <p><a href="{{ post.url }}">Read more</a></p>
      </div>
    </div>    
  <hr>
  </div>
</div>
{% endfor %}  
