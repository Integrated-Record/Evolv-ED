---
layout: page
title: Datasets and Databases 
permalink: /data/
hero_image: "/images/heros/pexels-photo-975771.jpeg"
menubar: data_menu
---

About data in general... Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Biological Data

* * * 


{% assign biocateg = site.data.data_categ | where: 'domain', "bio"  %}

{% assign biocateg = biocateg | sort: "long" %}

<div class="grid is-col-min-9">

{% for categ in biocateg %}

<div class="cell" style="padding: 10px">
<div class="card">
  <a href="{{site.url}}{{site.baseurl}}/data/{{categ.id}}.html">
  <div class="card-image">
    <figure class="image is-4by3">
      <img
        src="{{site.url}}{{site.baseurl}}/{{categ.image}}"
        alt="Placeholder image"
      />
    </figure>
  </div>
  </a>
  <a href="{{site.url}}{{site.baseurl}}/data/{{categ.id}}.html">
  <div class="card-content">
    <div class="media">
      <div class="media-content">
        <p class="title is-5">{{categ.long}}</p>
      </div>
    </div>
    <div class="content">
	{{categ.basic}}
    </div>
  </div>
  </a>
</div>

</div>

{% endfor %}

</div>


## Geological/Geographic

* * *

{% assign geocateg = site.data.data_categ | where: 'domain', "geo"  %}

{% assign geocateg = geocateg | sort: "long" %}


<div class="tile is-ancestor" style="flex-wrap: wrap;">

{% for categ in geocateg %}

<div class="tile is-4" style="padding: 10px">
<div class="card">
  <a href="{{site.url}}{{site.baseurl}}/data/{{categ.id}}.html">
  <div class="card-image">
    <figure class="image is-4by3">
      <img
        src="{{site.url}}{{site.baseurl}}/{{categ.image}}"
        alt="Placeholder image"
      />
    </figure>
  </div>
  </a>
  <a href="{{site.url}}{{site.baseurl}}/data/{{categ.id}}.html">
  <div class="card-content">
    <div class="media">
      <div class="media-content">
        <p class="title is-5">{{categ.long}}</p>
      </div>
    </div>
    <div class="content">
	{{categ.basic}}
    </div>
  </div>
  </a>
</div>

</div>

{% endfor %}

</div>
