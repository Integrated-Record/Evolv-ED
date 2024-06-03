---
layout: page
title: Guides 
permalink: /articles/guides/
hero_image: "/images/heros/free-photo-of-termeszet-viz-sziklak-moha.jpeg"
---

On this page you will find How-to and tutorial categories. 

## Scientific topics 

* * * 

{% assign thistopic = site.data.topics | where: 'type', "discipline"  %}

{% assign topiccat = thistopic | sort: "topic" %}

<div class="grid is-col-min-9">

{% for top in topiccat %}

<div class="cell">
<a href="{{site.url}}{{site.baseurl}}/articles/guides/{{top.topic  | slugify}}.html">
<div class="card">
  <div class="card-image">
    <figure class="image is-4by3">
      <img
        src="{{site.url}}{{site.baseurl}}/{{top.image}}"
        alt="Placeholder image"
      />
    </figure>
  </div>
  <div class="card-content">
    <div class="media">
      <div class="media-content">
        <p class="title is-6">{{top.topic}}</p>
      </div>
    </div>
  </div>
</div>
</a>

</div>

{% endfor %}

</div>

{% comment %}
## Technical topics

* * * 

{% assign thistopic = site.data.topics | where: 'type', "technical"  %}

{% assign topiccat = thistopic | sort: "topic" %}

<div class="grid is-col-min-9">

{% for top in topiccat %}

<div class="cell">
<a href="{{site.url}}{{site.baseurl}}/articles/guides/{{top.topic  | slugify}}.html">
<div class="card">
  <div class="card-image">
    <figure class="image is-4by3">
      <img
        src="{{site.url}}{{site.baseurl}}/{{top.image}}"
        alt="Placeholder image"
      />
    </figure>
  </div>
  <div class="card-content">
    <div class="media">
      <div class="media-content">
        <p class="title is-6">{{top.topic}}</p>
      </div>
    </div>
  </div>
</div>
</a>

</div>

{% endfor %}

</div>

{% endcomment %}
