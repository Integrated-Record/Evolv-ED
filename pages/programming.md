---
layout: page
title: Programming
subtitle: ... in Eco-Evoutionary Science 
permalink: /software/programming/
hero_image: "/images/heros/free-photo-of-grass-and-mountains.jpeg"
menubar_toc: true
---

Complex data analysis, numerical simulations and file manipulations are usually executed with the use of programming tools. These programming tools are often used in specific contexts. Many researchers know how use multiple of them, but they typically use one as a primary driver. 

## Programming environments and languages

Note that this list is not complete by far - and it represents a tiny subset of the avaiable languages that are used in Eco-Evoluationary sciences. Many of these languages (especially scripting languages) serve as platforms for **libraries** and **extension packages** that have domain-specific use.  

{% assign programming = site.data.software | where: 'category', 'Programming' %}


{% for s in programming %}

- {{s.id}}

{% endfor %}

## Code editing, IDEs
