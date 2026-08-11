## 

```liquid

```



## __shortcode-manager.liquid

``` liquid
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

## _blog-button.liquid

``` liquid


{%- comment -%}
  Input: raw_string (e.g. "blog-button: /products/guitar | 0 | #ff0000")
  Index mapping:
  - params[0]: URL
  - params[1]: Status (0 = Coming Soon, 2 = View Product)
  - params[2]: Optional HEX Color
{%- endcomment -%}
 <p style="color: blue !important; display: block !important;">TEST: BUTTON SNIPPET IS ALIVE</p>
DEBUG: {{ raw_string }}

{%- assign data = raw_string | split: ':' | last -%}
{%- assign params = data | split: '|' -%}

{%- assign theURL  = params[0] | strip -%}
{%- assign status  = params[1] | strip -%}
{%- assign custom_color = params[2] | strip -%}

{%- comment -%} 
  Define a default color if the 3rd variable is missing 
{%- endcomment -%}
{%- if custom_color == blank -%}
  {%- assign btn_style = "" -%}
{%- else -%}
  {%- capture btn_style -%}style="background-color: {{ custom_color }}; border-color: {{ custom_color }};"{%- endcapture -%}
{%- endif -%}

<a href="{{ theURL }}" class="blog-button-wrapper">
  {%- if status == '0' -%}
    <button class="btn-comingsoon" {{ btn_style }}> 
      Coming Soon 
    </button>
  {%- else -%}
    <button class="btn-viewproduct" {{ btn_style }}> 
      View Product 
    </button>
  {%- endif -%}
</a>
```
## _blog-ending.liquid

```liquid
<hr>

<div style="text-align: center;">
    <button onclick="window.location.href='https://guitarlicious-online.com/'" class="btn-homepage">
    Back To Homepage
    </button>
</div>
```

## Expert Box

### _guitar-expert-box.liquid
```liquid
<div class="quotebox-blog">
    <div style="flex-shrink: 0;">
        <img alt="Guitar Specialist Team" 
             src="https://cdn.shopify.com/s/files/1/0698/8473/9841/files/Gemini_Generated_Image_k17h8dk17h8dk17h.png?v=1765002297" 
             class="rounded-img">
    </div>
    <div>
        <h4>
            <b>Recommended By Guitarlicious Specialist Team</b>
        </h4>
        <p>
            This online guitar guide is recommended by our in-house guitar specialists, whose expertise is built upon years of hands-on experience and deep knowledge of the instrument. Based on their practical application and professional vetting, they have found this resource to be an exceptional and reliable tool for guitarists of all levels.
        </p>
    </div>
</div>
```

### _drum-expert-box.liquid
```liquid
<div class="quotebox-blog">
  <div>
      <img class="rounded-img showImg" alt="Drum Specialist" data-src="https://cdn.shopify.com/s/files/1/0698/8473/9841/files/Gemini_Generated_Image_3urqe93urqe93urq.png?v=1765001368" data-srcset="" srcset="" src="https://cdn.shopify.com/s/files/1/0698/8473/9841/files/Gemini_Generated_Image_3urqe93urqe93urq.png?v=1765001368"></div>
  <div>
    <h4 style="text-align: left; margin: 0;"><b>Recommended By Guitarlicious Drum Specialist Team</b></h4>
    <p><br><i>This online guide is recommended by our team of drum specialists, whose expertise is built upon years of hands-on experience and deep knowledge of drumming instruments. Based on their practical application and professional vetting, they have found these resources and knowledges to be an exceptional and reliable tool for drummers of all levels.</i></p>
  </div>
</div>

<br>
```


## Other Buttons & Formatting

### _btn-comingsoon.liquid
```liquid
<button class="btn-comingsoon"> Coming Soon </button>
```
### _btn-viewproduct.liquid
```liquid
<button class="btn-viewproduct"> View Product </button>
```
### _hr-line.liquid
```liquid
<hr>
```

