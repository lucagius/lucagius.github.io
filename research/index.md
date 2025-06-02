---
title: Research
layout: single
permalink: /research/
author_profile: true
hide_title: true
---

<style>
  /* hide the big “Research” banner */
  .page__title { display: none; }

  /* 1) make paper titles blue */
  .paper-title {
    color: #0066cc;
    text-decoration: none;
    cursor: default;
  }

  /* 2) make venue line green */
  .paper-venue {
  color: green;
  font-size: 0.9rem;
  margin: 0 0 1rem 0;
}


  /* 3) shrink the abstract text */
  .paper-abstract {
    font-size: 0.9rem;
    margin-bottom: 1.5rem;
    /* ensure the “Abstract:” prefix sits on the same line as the first sentence */
    display: inline-block;
  }

  /* 3a) prepend “Abstract:” to every abstract container except indicated */
  .paper-abstract:not(.no-prefix)::before {
  content: "Abstract: ";
  font-weight: bold;
}


  /* 4) make subtitles match the abstract’s font size */
  .paper-sub {
    margin: 0 0 0.25rem 0;
    font-style: italic;
    font-size: 0.9rem;
  }

  /* 5) space below PDF/DOI links */
  .paper-links {
    margin: 0 0 1rem 0;
  }
</style>

{% comment %} --------  WORKING PAPERS -------- {% endcomment %}
## Working Papers
{% assign wps = site.research | where:"category","working-paper" | sort:"year" | reverse %}
{% for paper in wps %}
### <span class="paper-title">{{ paper.title }}</span>
{% if paper.subtitle %}
<p class="paper-sub">{{ paper.subtitle }}</p>
{% endif %}
{% if paper.venue %}
<p class="paper-venue">{{ paper.venue }}</p>
{% endif %}
{% if paper.pdf or paper.doi %}
<p class="paper-links">
  {% if paper.pdf %}<a href="{{ paper.pdf }}" target="_blank">PDF</a>{% endif %}
  {% if paper.pdf and paper.doi %} | {% endif %}
  {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank">DOI</a>{% endif %}
</p>
{% endif %}

<div class="paper-abstract">
  {{ paper.content }}
</div>
{% endfor %}

{% comment %} --------  PUBLICATIONS -------- {% endcomment %}
## Refereed Publications
{% assign pubs = site.research | where:"category","publication" | sort:"year" | reverse %}
{% for paper in pubs %}
### <span class="paper-title">{{ paper.title }}</span>
{% if paper.subtitle %}
<p class="paper-sub">{{ paper.subtitle }}</p>
{% endif %}
{% if paper.venue %}
<p class="paper-venue">{{ paper.venue }}</p>
{% endif %}
{% if paper.pdf or paper.doi %}
<p class="paper-links">
  {% if paper.pdf %}<a href="{{ paper.pdf }}" target="_blank">PDF</a>{% endif %}
  {% if paper.pdf and paper.doi %} | {% endif %}
  {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank">DOI</a>{% endif %}
</p>
{% endif %}

<div class="paper-abstract">
  {{ paper.content }}
</div>
{% endfor %}

{% comment %} --------  NON-PEER-REVIEWED -------- {% endcomment %}
## Other Publications
{% assign misc = site.research | where:"category","non-peer-reviewed" | sort:"year" | reverse %}
{% for paper in misc %}
### <span class="paper-title">{{ paper.title }}</span>
{% if paper.subtitle %}
<p class="paper-sub">{{ paper.subtitle }}</p>
{% endif %}
{% if paper.venue %}
<p class="paper-venue">{{ paper.venue }}</p>
{% endif %}
{% if paper.pdf or paper.doi %}
<p class="paper-links">
  {% if paper.pdf %}<a href="{{ paper.pdf }}" target="_blank">PDF</a>{% endif %}
  {% if paper.pdf and paper.doi %} | {% endif %}
  {% if paper.doi %}<a href="{{ paper.doi }}" target="_blank">DOI</a>{% endif %}
</p>
{% endif %}

<div class="paper-abstract">
  {{ paper.content }}
</div>
{% endfor %}
