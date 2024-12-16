---
layout: default
permalink: /publications/
title: Publications
nav: true
nav_order: 2
---

{% assign publications = site.data.publications.publications | sort: 'date' | reverse %}
{% assign current_year = "" %}

{% for publication in publications %}
  {% assign publication_year = publication.date | date: "%Y" %}

  <div style="margin-bottom: 10px;">
      {% if publication_year != current_year %}
        {% assign current_year = publication_year %}
        <h4 style="margin-top: 10px;">{{ current_year }}</h4> 
        <hr>
      {% endif %}
      <strong>
        {% if publication.link %}
          <a href="{{ publication.link }}">{{ publication.title }}</a>
        {% else %}
          {{ publication.title }}
        {% endif %}
      </strong> <br>
      {{ publication.authors }} <br>
      {{ publication.conference }}
      {% if publication.extras %}
        (
        {% for extra in publication.extras %}
          {% if extra.url %}
            <a href="{{ extra.url }}" class="extra-link">{{ extra.label }}</a>
          {% else %}
            {% if extra.note %}{{ extra.note }}{% endif %}
          {% endif %}
          {% if forloop.last == false %}, {% endif %}
        {% endfor %}
        )
      {% endif %} <br>
  </div>
{% endfor %}
