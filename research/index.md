---
title: Research
layout: single          # switch from page → single
permalink: /research/
author_profile: true    # extra‑safe; forces the sidebar on this page
---

<style>
/* show titles as plain text (no link, no underline) */
.paper-title { color: inherit; text-decoration: none; cursor: default; }
.paper-sub   { margin: 0 0 0.5rem 0; font-style: italic; }
.paper-links { margin: 0 0 1rem 0; }
</style>

{% comment %} --------  WORKING PAPERS -------- {% endcomment %}
## Working Papers
{% assign wps = site.research | where:"category","working-paper" | sort:"year" | reverse %}
{% for paper in wps %}
### <span class="paper-title">{{ paper.title }}</span>
{% if paper.subtitle %}
<p class="paper-sub">{{ paper.subtitle }}</p>
{% endif %}
{% if paper.pdf or paper.doi %}
<p class="paper-links">
  {% if paper.pdf %}[PDF]({{ paper.pdf }}){% endif %}
  {% if paper.pdf and paper.doi %} | {% endif %}
  {% if paper.doi %}[DOI]({{ paper.doi }}){% endif %}
</p>
{% endif %}
{{ paper.content }}

{% endfor %}

{% comment %} --------  PUBLICATIONS -------- {% endcomment %}
## Publications
{% assign pubs = site.research | where:"category","publication" | sort:"year" | reverse %}
{% for paper in pubs %}
### <span class="paper-title">{{ paper.title }}</span>
{% if paper.subtitle %}
<p class="paper-sub">{{ paper.subtitle }}</p>
{% endif %}
{% if paper.pdf or paper.doi %}
<p class="paper-links">
  {% if paper.pdf %}[PDF]({{ paper.pdf }}){% endif %}
  {% if paper.pdf and paper.doi %} | {% endif %}
  {% if paper.doi %}[DOI]({{ paper.doi }}){% endif %}
</p>
{% endif %}
{{ paper.content }}

{% endfor %}

{% comment %} --------  NON‑PEER‑REVIEWED -------- {% endcomment %}
## Non‑peer‑reviewed Work
{% assign misc = site.research | where:"category","non-peer-reviewed" | sort:"year" | reverse %}
{% for paper in misc %}
### <span class="paper-title">{{ paper.title }}</span>
{% if paper.subtitle %}
<p class="paper-sub">{{ paper.subtitle }}</p>
{% endif %}
{% if paper.pdf or paper.doi %}
<p class="paper-links">
  {% if paper.pdf %}[PDF]({{ paper.pdf }}){% endif %}
  {% if paper.pdf and paper.doi %} | {% endif %}
  {% if paper.doi %}[DOI]({{ paper.doi }}){% endif %}
</p>
{% endif %}
{{ paper.content }}

{% endfor %}
