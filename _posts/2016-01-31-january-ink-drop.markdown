---
layout: post
title: "January Ink Drop"
date: 2016-01-31 07:19
categories: ["ink-and-paper"]
tags: ["inkdrop"]
---

The January 2016 Ink drop arrived yesterday. Some delicious colours. I've decided to carry the Jane Austin, William Shakespeare, and the Caf&eacute; des Iles for this week and see how things work out.

{% if page.data %}{% assign data = page.data %}
{% else %}
{% assign data = page.path | split:"/" | last | split:"." | first %}
{% endif %}
{% assign data = site.data[data] %}
{% assign gallery = data.gallery %}
{% assign materials = data.materials %}
{% assign gallery_path = site.s3path | append: gallery.path %}
{% assign images = gallery.images %}

{% include image_feature.html image=images.last %}

*******

## Steps

{% for image in images %}
{% include image_entry.html %}
{% endfor %}

*******

## Materials
{% for material in materials %}
### {{ material.first }}
{% for item in material.last %}
* {{ item }}{% endfor %}
{% endfor %}
