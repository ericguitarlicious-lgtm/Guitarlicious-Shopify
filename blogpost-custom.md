``` liquiz
{% assign output = content %}

{%- if output contains '[guitar-expert-box]' -%}
  {% capture snippet %}{% render '_guitar-expert-box' %}{% endcapture %}
  {% assign output = output | replace: '[guitar-expert-box]', snippet %}
{%- endif -%}

{%- if output contains '[drum-expert-box]' -%}
  {% capture snippet %}{% render '_drum-expert-box' %}{% endcapture %}
  {% assign output = output | replace: '[drum-expert-box]', snippet %}
{%- endif -%}

{%- if output contains '[blog-ending]' -%}
  {% capture snippet %}{% render '_blog-ending' %}{% endcapture %}
  {% assign output = output | replace: '[blog-ending]', snippet %}
{%- endif -%}

{%- if output contains '[hr-line]' -%}
  {% capture snippet %}{% render '_hr-line' %}{% endcapture %}
  {% assign output = output | replace: '[hr-line]', snippet %}
{%- endif -%}

{%- if output contains '[btn-viewproduct]' -%}
  {% capture snippet %}{% render '_btn-viewproduct' %}{% endcapture %}
  {% assign output = output | replace: '[btn-viewproduct]', snippet %}
{%- endif -%}

{%- if output contains '[btn-comingsoon]' -%}
  {% capture snippet %}{% render '_btn-comingsoon' %}{% endcapture %}
  {% assign output = output | replace: '[btn-comingsoon]', snippet %}
{%- endif -%}

{{ output }}
```
