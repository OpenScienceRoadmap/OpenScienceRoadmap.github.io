---
layout: default
---

# Participants
The following individuals and organizations are participating in the development of a joint roadmap for open science tools, <a href="mailto:info@jrost.org" title="email JROST">Contact us to join</a>.

<h2 id="individuals">Individuals</h2>
<people>
<ul>
  {%- assign individuals = site.data.participants.people | sort: 'namefamily' -%}
  {%- for individual in individuals -%}
    <li>
      {%- if individual.url -%}<a href="{{ individual.url }}">{%- endif -%}
      {%- if individual.namegiven -%}{{ individual.namegiven | append: ' ' }}{%- endif -%}
      {{ individual.namefamily }}
      {%- if individual.url -%}</a>{%- endif -%}
    </li>
  {%- endfor -%}
</ul>
</people>

<h2 id="organizations">Organizations</h2>
<organizations>
{%- assign organizations = site.data.participants.orgs | sort_natural: 'org' -%}
{%- for organization in organizations -%}
  <organization>
    <logo>
      {%- if organization.orglogo -%}
        {%- if organization.orgurl -%}<a href="{{ organization.orgurl }}">{%- endif -%}
        {{ organization.orglogo | prepend: '<img src="/assets/img/' | append: '" alt="' | append: organization.orgnick | append: ' logo" />' }}
        {%- if organization.orgurl -%}</a>{%- endif -%}
      {%- elsif organization.parentlogo -%}  
        {%- if organization.parenturl -%}<a href="{{ organization.parenturl }}">{%- endif -%}
        {{ organization.parentlogo | prepend: '<img src="/assets/img/' | append: '" alt="' | append: organization.parentnick | append: ' logo" />' }}
        {%- if organization.parenturl -%}</a>{%- endif -%}
      {%- endif -%}
    </logo>
    <name>
      {%- if organization.orgurl -%}<a href="{{ organization.orgurl }}">{%- endif -%}
      {{ organization.org }}
      {%- if organization.orgnick -%}{{ organization.orgnick | prepend: ' (' | append: ')' }}{%- endif -%}
      {%- if organization.orgurl -%}</a>{%- endif -%}
      {%- if organization.parenturl -%}&nbsp;/&nbsp;<a href="{{ organization.parenturl }}">{%- endif -%}
      {%- if organization.parent -%}{{ organization.parent }}{%- endif -%}
      {%- if organization.parentnick -%}{{ organization.parentnick | prepend: ' (' | append: ')' }}{%- endif -%}
      {%- if organization.parenturl -%}</a>{%- endif -%}
    </name>
  </organization>
{%- endfor -%}
</organizations>
