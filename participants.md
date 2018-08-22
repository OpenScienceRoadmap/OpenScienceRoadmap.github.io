---
layout: default
---

# Participants
The following individuals and organizations are participating formally in the development of a joint roadmap for open science tools. [Learn more](https://github.com/OpenScienceRoadmap/jrost#participants) about how to join as a formal participant.

<h2 id="individuals">Individuals</h2>
<people>
<ul>
  {%- assign individuals = site.data.participants.orgs | where:"type","person" | sort: 'org' -%}
  {%- for individual in individuals -%}
    <li>
      {%- if individual.url -%}<a href="{{ individual.url }}">{%- endif -%}
      {%- if individual.namegiven -%}{{ individual.namegiven | append: ' ' }}{%- endif -%}
      {{ individual.namefamily }}
      {%- if individual.url -%}</a>{%- endif -%}
      {%- if individual.wikidataid -%} (<a href="https://www.wikidata.org/wiki/{{ organization.wikidataid }}">{{ individual.wikidataid }}</a>){%- endif -%}
    </li>
  {%- endfor -%}
</ul>
</people>

<h2 id="organizations">Organizations</h2>
You can also view a full-width page of just the <a href="organizations">logos for participating organizations</a>.
<organizations>
{%- assign organizations = site.data.participants.orgs | where:"type","org" | sort_natural: 'org' -%}
{%- for organization in organizations -%}
  <organization>
    <logo>
      {%- if organization.logo -%}
        {%- if organization.url -%}<a href="{{ organization.url }}">{%- endif -%}
        {{ organization.logo | prepend: '<img src="/assets/img/' | append: '" alt="' | append: organization.nick | append: ' logo" />' }}
        {%- if organization.url -%}</a>{%- endif -%}
      {%- elsif organization.parentlogo -%}  
        {%- if organization.parenturl -%}<a href="{{ organization.parenturl }}">{%- endif -%}
        {{ organization.parentlogo | prepend: '<img src="/assets/img/' | append: '" alt="' | append: organization.parentnick | append: ' logo" />' }}
        {%- if organization.parenturl -%}</a>{%- endif -%}
      {%- endif -%}
    </logo>
    <name>
      {%- if organization.url -%}<a href="{{ organization.url }}">{%- endif -%}
      {{ organization.org }}
      {%- if organization.nick != organization.org -%}{{ organization.nick | prepend: ' (' | append: ')' }}{%- endif -%}
      {%- if organization.url -%}</a>{%- endif -%}
      {% if organization.wikidataid %} (<a href="https://www.wikidata.org/wiki/{{ organization.wikidataid }}">{{ organization.wikidataid }}</a>){% endif %}
      {%- if organization.parenturl -%}&nbsp;/&nbsp;<a href="{{ organization.parenturl }}">{%- endif -%}
      {%- if organization.parent -%}{{ organization.parent }}{%- endif -%}
      {%- if organization.parentnick -%}{{ organization.parentnick | prepend: ' (' | append: ')' }}{%- endif -%}
      {%- if organization.parenturl -%}</a>{%- endif -%}
    </name>
  </organization>
{%- endfor -%}
</organizations>
