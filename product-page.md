## _btn-pricematch.liquid

```liquid

<!-- WhatsApp Price Match Snippet -->
{%- assign product_title_escaped = product.title | escape -%}
{%- assign product_full_url = shop.url | append: product.url -%}
{%- assign raw_message = "I would like to request price match for " | append: product_title_escaped | append: " : " | append: product_full_url -%}
{%- assign whatsapp_encoded_message = raw_message | url_encode -%}

<div class="whatsapp-price-match-container">
  <div class="wpm-icon-wrapper">
    <!-- Main WhatsApp Icon -->
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="wpm-main-icon">
      <path d="M380.9 97.1C339 55.1 283.2 32 223.9 32c-122.4 0-222 99.6-222 222 0 39.1 10.2 77.3 29.6 111L0 480l117.7-30.9c32.4 17.7 68.9 27 106.1 27h.1c122.3 0 224.1-99.6 224.1-222 0-59.3-25.2-115-67.1-157zm-157 341.6c-33.2 0-65.7-8.9-94-25.7l-6.7-4-69.8 18.3L72 359.2l-4.4-7c-18.5-29.4-28.2-63.3-28.2-98.2 0-101.7 82.8-184.5 184.6-184.5 49.3 0 95.6 19.2 130.4 54.1 34.8 34.9 56.2 81.2 56.1 130.5 0 101.8-84.9 184.6-186.6 184.6zm101.2-138.2c-5.5-2.8-32.8-16.2-37.9-18-5.1-1.9-8.8-2.8-12.5 2.8-3.7 5.6-14.3 18-17.6 21.8-3.2 3.7-6.5 4.2-12 1.4-32.6-16.3-54-29.1-75.5-66-5.7-9.8 5.7-9.1 16.3-30.3 1.8-3.7 .9-6.9-.5-9.7-1.4-2.8-12.5-30.1-17.1-41.2-4.5-10.8-9.1-9.3-12.5-9.5-3.2-.2-6.9-.2-10.6-.2-3.7 0-9.7 1.4-14.8 6.9-5.1 5.6-19.4 19-19.4 46.3 0 27.3 19.9 53.7 22.6 57.4 2.8 3.7 39.1 59.7 94.8 83.8 35.2 15.2 49 16.5 66.6 13.9 10.7-1.6 32.8-13.4 37.4-26.4 4.6-13 4.6-24.1 3.2-26.4-1.3-2.5-5-3.9-10.5-6.6z"/>
    </svg>
    <!-- Mini Integrated Dollar Badge -->
    <div class="wpm-mini-badge">
      <span class="wpm-badge-text">$</span>
    </div>
  </div>
  <div class="wpm-content">
    <p class="wpm-title">Found Better Price elsewhere?</p>
    {% assign current_branch = shop.metaobjects.branch_info['gtlc-ad'] %}

    <a href="{{ current_branch.ws_link.value.url }}?text={{ whatsapp_encoded_message }}" target="_blank" rel="noopener" class="wpm-link">
      Click here to Whatsapp Us for Price Match.
    </a>
  </div>
</div>

<style>
  .whatsapp-price-match-container {
    display: flex;
    align-items: center;
    background-color: #f5f5f5;
    border: 1px solid #bfbfbf;
    border-radius: 8px;
    padding: 14px 16px;
    margin: 15px 0;
    max-width: 100%;
    box-sizing: border-box;
    font-family: inherit;
  }

  .wpm-icon-wrapper {
    position: relative;
    margin-right: 16px;
    display: inline-block;
    flex-shrink: 0;
    width: 32px;
    height: 32px;
  }

  .wpm-main-icon {
    width: 30px;
    height: 30px;
    fill: #25D366;
  }

  /* Miniature badge offset to the bottom right */
  .wpm-mini-badge {
    position: absolute;
    bottom: -2px;
    right: -2px;
    background-color: #008060; /* Brand Accent Green */
    border: 2px solid #f9f9f9; /* Outer ring to cleanly separate it from the WA icon */
    border-radius: 50%;
    width: 16px;
    height: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    box-sizing: border-box;
  }

  .wpm-badge-text {
    color: #ffffff;
    font-size: 10px;
    font-weight: 700;
    line-height: 1;
    font-family: system-ui, -apple-system, sans-serif;
    transform: translateY(-0.5px); /* Fine-tunes visual vertical alignment */
  }

  .wpm-content {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .wpm-title {
    margin: 0;
    font-size: 14px;
    font-weight: 600;
    color: #2b2b2b;
    line-height: 1.3;
  }

  .wpm-link {
    font-size: 13px;
    font-weight: 500;
    color: #008060; 
    text-decoration: underline;
    text-underline-offset: 3px;
    transition: color 0.2s ease;
    cursor: pointer;
    line-height: 1.3;
  }

  .wpm-link:hover {
    color: #004d3a;
    text-decoration: underline;
  }

  @media (max-width: 360px) {
    .whatsapp-price-match-container {
      padding: 10px 12px;
    }
    .wpm-title { font-size: 13px; }
    .wpm-link { font-size: 12px; }
  }
</style>

```

## _color-pill.liquid
``` liquid
<div class="custom-variant-wrapper">
  <div id="swatch-list" class="swatch-grid" style="min-height: 0px; display: flex; flex-wrap: wrap; gap: 8px;"></div>
</div>

<style>
  .swatch-circle {
    transition: transform 0.2s, border 0.2s;
    border: 1px solid #e0e0e0;
    box-sizing: border-box;
  }
  .swatch-circle:hover {
    transform: scale(1.1);
  }
  .swatch-circle.active {
    border: 2px solid #000 !important;
    transform: scale(1.15);
    box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  }
</style>

<script>
(function() {
  const colorLookup = {
    // LONG COLOR NAMES
    "pearl green":"#88d8b0",
    "sky blue":"#a0d9ef",
    "silver blue":"linear-gradient(135deg, #101d2c 0%, #649cbc 50%, #d5e7f1 100%)",
    "beach fade surf":"linear-gradient(135deg, #faea85 0%, #31767c 50%, #19284a 100%)",
    "tequila sunrise surf":"linear-gradient(135deg, #fec23a 0%, #fd1f26 50%, #cd0801 100%)",
    "cobalt blue":"#0047AB",
    "black pink":"linear-gradient(135deg,#000000 50%, #ffc0cb 50%)",

    // COMMON COLORS
    "natural": "#d4b174",
    "sunburst": "linear-gradient(135deg, #3d231a 0%, #8b5a2b 50%, #d2a679 100%)",
    "black": "#1a1a1a",
    "gray": "#808080",
    "grey": "#808080",
    "white": "#ffffff",
    "red": "#b22222",
    "orange": "#ff8c00",
    "yellow": "#ffd700",
    "green": "#55DFB8",
    "lime": "#32cd32",
    "blue": "#276AB3",
    "navy": "#000080",
    "purple": "#6a0dad",

    // METALLIC COLORS
    "silver": "#c0c0c0",
    "titanium": "linear-gradient(135deg, #a0a0a0 0%, #e8e8e8 50%, #a0a0a0 100%)",
    "gold": "linear-gradient(135deg, #bf953f 0%, #fcf6ba 50%, #b38728 100%)",
    "pink": "#ffc0cb",

    // FANCY COLOR NAMES
    "lavender": "#d174dc",
    "evergreen":"#097343",
    "beige": "#f5f5dc",
    "khaki": "#c3b091",
    "coffee":"#241204",
    "latte":"#b6a897",
    "magenta": "#FF00FF",
    "maroon": "#800000",
    "blonde":"#E4B55E",
    "champagne":"#b2a076",
    "cherry":"#e30202",
    "bry":"linear-gradient(135deg, #020408 0%, #d84325 50%, #b38728 100%)",
    "honey":"#ED8C00",
    "mint":"#ADEBB3",
  };

  function extractColor(text) {
    // Clean text by splitting at -, &, or "and"
    let clean = text.toLowerCase().split(/-|&|\band\b/)[0].trim();
    
    // FIX: Check for the WHOLE phrase first (e.g., "beach fade surf")
    if (colorLookup.hasOwnProperty(clean)) {
      return colorLookup[clean];
    }
    
    // FALLBACK: If no exact phrase match, check word by word
    const words = clean.split(/\s+/);
    const matchedKey = words.find(w => colorLookup.hasOwnProperty(w));
    return matchedKey ? colorLookup[matchedKey] : "#eeeeee";
  }

  function buildSwatches() {
    const listContainer = document.getElementById('swatch-list');
    if (!listContainer || listContainer.children.length > 0) return;

    const allSelects = document.querySelectorAll('select');
    const selectEl = document.querySelector('select[name="id"]') || 
                     document.querySelector('.single-option-selector') || 
                     document.querySelector('select[id*="variant"]') ||
                     allSelects[0];

    if (!selectEl) return;

    Array.from(selectEl.options).forEach(option => {
      const rawText = option.text.trim();
      if (!rawText || /select|choose/i.test(rawText)) return;

      const bgValue = extractColor(rawText);
      const circle = document.createElement('div');
      
      circle.className = 'swatch-circle';
      circle.title = rawText; 
      circle.style.background = bgValue;
      circle.style.width = "40px";
      circle.style.height = "40px";
      circle.style.display = "inline-block";
      circle.style.borderRadius = "50%";
      circle.style.cursor = "pointer";

      circle.onclick = function() {
        selectEl.value = option.value;
        selectEl.dispatchEvent(new Event('change', { bubbles: true }));
        document.querySelectorAll('.swatch-circle').forEach(c => c.classList.remove('active'));
        this.classList.add('active');
      };

      listContainer.appendChild(circle);
      
      if (option.selected) {
        circle.classList.add('active');
      }
    });
  }

  const observer = new MutationObserver((mutations, obs) => {
    const select = document.querySelector('select[name="id"]') || document.querySelector('select[id*="variant"]');
    if (select) {
      buildSwatches();
      if (document.querySelectorAll('.swatch-circle').length > 0) obs.disconnect();
    }
  });

  observer.observe(document.body, { childList: true, subtree: true });
  window.addEventListener('DOMContentLoaded', buildSwatches);
  window.addEventListener('load', buildSwatches);
  
  let attempts = 0;
  const interval = setInterval(() => {
    buildSwatches();
    if (attempts++ > 15 || document.querySelectorAll('.swatch-circle').length > 0) clearInterval(interval);
  }, 500);
})();
</script>

```

##FAQ

### _faq-general.liquid

``` liquid
{% comment %}
  Usage: {% render '_faq-general' %}
{% endcomment %}

<style>
.faq-item summary h4 {
    margin: 0;
    font-size: 1.6rem;
}

.modern-faq-wrapper {
    margin: 0;
    display: flex;
    flex-direction: column;
    width: auto;
}

  /* Container card with static neutral border */
  .faq-item {
    background-color: #ffffff;
    border: 1px solid #e0e0e0;
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 12px;
  }

  /* Interactive Header */
  .faq-question {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 18px 20px;
    cursor: pointer;
    list-style: none;
    user-select: none;
  }

  /* Default native h3 resets inside the summary header */
  .faq-question h3 {
    margin: 0;
  }

  /* Hide default webkit/browser disclosure arrows */
  .faq-question::-webkit-details-marker,
  .faq-question::marker {
    display: none;
  }

  /* V Arrow (Chevron) Animation */
  .faq-icon-arrow {
    width: 16px;
    height: 16px;
    flex-shrink: 0;
    transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .faq-icon-arrow path {
    stroke: currentColor;
    stroke-width: 2;
    stroke-linecap: round;
    stroke-linejoin: round;
  }

  /* Flip V arrow when open */
  .faq-item[open] .faq-icon-arrow {
    transform: rotate(180deg);
  }

  /* Answer Container */
  .faq-answer {
    padding: 0 20px 20px 20px;
  }

  /* Native p margin reset */
  .faq-answer p {
      margin: 0;
      font-size: 1.6rem;
  }
</style>

<div class="modern-faq-wrapper qna-general">
  {% assign type_of_faqs = shop.metaobjects.faq_general.values %}
  {% if type_of_faqs != blank %}
    {% for faq in type_of_faqs %}
      <details class="faq-item">
        <summary class="faq-question">
          <h4>{{ faq.question.value | default: faq.question }}</h4>
          <svg class="faq-icon-arrow" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 9L12 15L18 9"/>
          </svg>
        </summary>
        <div class="faq-answer">
          <p>{{ faq.answer.value | default: faq.answer }}</p>
        </div>
      </details>
    {% endfor %}
  {% endif %}

</div>
```

### _faq-instrument.liquid

``` liquid
{% comment %}
  Usage: {% render '_faq-instrument' %}
{% endcomment %}

<div class="modern-faq-wrapper qna-product">
  {% assign faq_numbers = "01,02,03" | split: "," %}

  {% for num in faq_numbers %}
    {% comment %} Build the dynamic metafield key names {% endcomment %}
    {% assign ques_key = "qna" | append: num | append: "_ques" %}
    {% assign ans_key = "qna" | append: num | append: "_ans" %}

    {% assign question = product.metafields.custom[ques_key].value | default: product.metafields.custom[ques_key] %}
    {% assign answer = product.metafields.custom[ans_key].value | default: product.metafields.custom[ans_key] %}

    {% if question != blank and answer != blank %}
      <details class="faq-item">
        <summary class="faq-question">
          <h4>{{ question }}</h4>
          <svg class="faq-icon-arrow" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 9L12 15L18 9"/>
          </svg>
        </summary>
        <div class="faq-answer">
          <p>{{ answer }}</p>
        </div>
      </details>
    {% endif %}
  {% endfor %}
</div>

<div class="modern-faq-wrapper qna-instrument">
  {% assign type_of_faqs = shop.metaobjects.faq_instrument.values %}
  {% if type_of_faqs != blank %}
    {% for faq in type_of_faqs %}
      {% assign faq_type = faq.type.value | default: faq.type | downcase %}
      {% assign current_template = template.suffix | downcase %}

      {% comment %} Show FAQ only if the type matches the template suffix {% endcomment %}
      {% if faq_type == current_template %}
        <details class="faq-item">
          <summary class="faq-question">
            <h4>{{ faq.question.value | default: faq.question }}</h4>
            <svg class="faq-icon-arrow" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M6 9L12 15L18 9"/>
            </svg>
          </summary>
          <div class="faq-answer">
            <p>{{ faq.answer.value | default: faq.answer }}</p>
          </div>
        </details>
      {% endif %}
    {% endfor %}
  {% endif %}
</div>
```

### _faq-render.liquid

``` liquid
{% comment %}
 USAGE
 {% render '_faq-render-01' %}
{% endcomment %}

<h2>Frequently Asked Questions (FAQ)</h2>
<br>

{% comment %}
 {% render '_faq-instrument' %}
{% endcomment %}

{% render '_faq-general' %}

```
