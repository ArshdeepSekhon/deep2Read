---
layout: page
title: Readings ByTag
desc: "Deep Learning Readings Organized by Tags"
---


Click on a tag to see relevant list of readings.

<ul class="tags">
{% assign sorted = site.tags | sort %}
{% for tag in sorted %}
  {% assign t = tag | first %}
  <li><a href="{{ site.baseurl }}/ReadingsIndexByTags/#{{t | replace:" ","-" }}">{{ t }}</a></li>
{% endfor %}
</ul>

---

{% assign sorted = site.tags | sort %}
{% for tag in sorted %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<h2><a name="{{t | replace:" ","-" }}"></a><a class="internal" href="{{ site.baseurl }}/ReadingsIndexByTags/#{{t | replace:" ","-" }}">{{ t  }}</a></h2>

<!--- for each tag, get a table of index -->
<table id="datatab3" summary="Table of readings" border="1">
<tr>
 <h3><b>
  <th>No.</th>
  <th>Date</th>
  <th>Title and Information</th>
  </b>
  </h3>
</tr>

{% assign counter = 1 %}
{% for post in posts %}
  {% if post.tags contains t %}

  <tr>
  <td>{{ counter }}</td>
  <td><span class="date"> {{ post.date | date: "%Y, %-b, %-d "  }}</span></td>
  <td><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></td>
  </tr>

  {% assign counter=counter | plus:1 %}
  {% endif %}
{% endfor %}

</table>

---

{% endfor %}
