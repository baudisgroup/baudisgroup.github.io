---
title: "baudisgroup @ UZH"
layout: default
permalink: /index.html
date:   2019-03-18
---

## [Welcome to the _baudisgroup_ Pages](http://info.baudisgroup.org)

The _baudisgroup_ website represents projects and information by the __Computational Oncogenomics Group__ of the [University of Zurich (UZH)](https://www.mls.uzh.ch/en/research/baudis/) and the [Swiss Institute of Bioinformatics (SIB)](https://www.sib.swiss/baudis-michael/). For visitors more interested in Particle Astrophysics, we strongly recommend the website of another, although related, [Professor Baudis](https://www.physik.uzh.ch/en/groups/baudis.html).

The Computational Oncogenomics Group focus lies in the exploration of structural genome variations in cancer. Our work centres around our [arrayMap](arraymap.org) and [Progenetix](progenetix.org) resources of curated molecular-cytogenetic and sequencing data.

Specific projects explore computational methods, genomics of selected tumour entities as well as genomic variant patterns across malignancies. As members of the [Global Alliance for Genomics and Health](http://ga4gh.org), the group is developing standards in biocuration and data sharing for genomic variants and phenotypic data, for instance in driving development of the [ELIXIR Beacon](https://www.elixir-europe.org/about-us/implementation-studies/beacons) project through the [Beacon+ implementation](http://beacon.progenetix.org/ui/). Other projects are related to genome data epistemology, e.g. geographic and diagnostic sampling biases.

### Some Projects

* [bycon](https://github.com/progenetix/bycon) at Github in __Progenetix__
* [segment-liftover](https://github.com/baudisgroup/segment-liftover) at Github __baudisgroup__
    * [publication](http://info.baudisgroup.org/publications/2018/03/14/segment_liftover.html)
* [SNP2pop](https://github.com/baudisgroup/snp2pop) at Github __baudisgroup__
    * [publication at ScientificReports](https://www.nature.com/articles/s41598-020-61854-x)
* [ICDOntologies](https://github.com/progenetix/ICDOntologies) at Github in __Progenetix__


### Latest News    

{% comment %}
	Some news ...
{% endcomment %}


{%- assign this_name = "news" -%}
{%- assign this_category = "news" -%}
{%- assign max_list = 5 -%}
{%- assign count_list = 0 -%}

{%- assign cat_posts = site.emptyArray -%}
{%- for post in site.documents -%}
  {%- if post.categories contains this_category -%}
    {%- assign cat_posts = cat_posts | push: post -%}
  {%- endif -%}
{%- endfor -%}

{%- assign cat_posts = cat_posts | sort: 'date' | reverse -%}

{% for post in cat_posts limit: max_list %}
  {% unless post.tags contains '.prepend' or post.tags contains '.append' %}
    {%- assign post_author = post.author | downcase -%}
    {%- assign excerpt_link = post.url | relative_url -%}
    {%- if post.excerpt_link contains '/' -%}
      {%- assign excerpt_link = post.excerpt_link -%}
    {%- endif -%}
<div class="excerpt">
<a href="{{ excerpt_link }}">{{ post.excerpt }}</a>
  <p class="footnote">
    {%- if post.author -%}{{ post.author | join: " | " }}&nbsp;{%- endif -%}
    {%- if post.date -%}{{ post.date | date: "%Y-%m-%d" }}: {% endif %}
 <a href="{{ excerpt_link }}">more ...</a>
  </p>
</div>
  {% endunless %}  
{% endfor %}

{% comment %}
	More static content ...
{% endcomment %}


### Support or Contact

For requests & support, please use standard Github procedures such as pull
requests or issues on our project repositories, or [contact us](contact@progenetix.org).

### Address

Winterthurerstrasse 190 | Y-13F-01 | CH-8057 Zurich | Switzerland

<a href="/assets/img/access-map-Irchel.png" target="_blank">![How to find the Baudisgroup](/assets/img/access-map-Irchel.png){:style="width: 100%;"}</a>
