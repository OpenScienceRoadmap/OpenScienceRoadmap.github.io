---
layout: wide
---

# Participating Organizations
The following organizations are participating in the development of a joint roadmap for open science tools. See a <a href="participants" title="JROST participants">complete list of participants</a> or <a href="mailto:info@jrost.org" title="email JROST">contact us to join</a>.

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
{%- endfor -%}
</organizations>
