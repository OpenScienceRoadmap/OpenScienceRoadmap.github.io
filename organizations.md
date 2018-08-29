---
layout: wide
title: Organizations
---

# Participating Organizations
The following organizations are participating formally in the development of a joint roadmap for open science tools. See a <a href="participants" title="formal Joint Roadmap participants">complete list of all individuals and organizations participating formally</a> and learn more about [how to join as a formal participant](https://github.com/OpenScienceRoadmap/jrost#participants).

<!-- organization logos -->
<organizations>
{%- assign organizations = site.data.participants.orgs | where: 'type','org' | sort_natural: 'org' -%}
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
  </organization>
{%- endfor -%}
</organizations>

<!-- organization names -->
<organizations class="list">
{%- assign organizations = site.data.participants.orgs | where: 'type','org' | sort_natural: 'org' -%}
{%- for organization in organizations -%}
  <organization>
    <name>
      {%- if organization.url -%}<a href="{{ organization.url }}">{%- endif -%}
      {{ organization.org }}
      {%- if organization.nick != organization.org -%}{{ organization.nick | prepend: ' (' | append: ')' }}{%- endif -%}
      {%- if organization.url -%}</a>{%- endif -%}
    </name>
  </organization>
  {%- if forloop.last == false -%}&bull;{%- endif -%}
{%- endfor -%}
</organizations>
