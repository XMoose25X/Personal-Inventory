---
layout: full
title: Amiibo
permalink: /amiibo/
---

{% assign owned = 0 %}
{% assign total = 0 %}
{% assign ratio = 0 %}
{% for series in site.data.amiibo.series %}
  {% assign temp = series.characters | where: "owned", "true" | size %}
  {% assign owned = owned | plus: temp %}
  {% assign temp = series.characters | size %}
  {% assign total = total | plus: temp %}
{% endfor %}
  {% assign total_as_float = total | times: 1.0 %}
  {% assign ratio = owned | divided_by: total_as_float | times: 100 %}
<span>Total Owned Amiibo: {{owned}} / {{total}}</span>
<div class="meter">
	<span style="width: {{ratio}}%">{{ratio | floor }}%</span>
</div>
<div  stlye="display: flex">
    {% for series in site.data.amiibo.series %}
    <div id="{{series.title | slugify: 'pretty'}}-container">
        <div class="series-header">
            <span>{{series.title}}</span>
            <span>{{ series.characters | where: "owned", "true" | size }} / {{ series.characters | size }}</span>
        </div>
        <div class="series-container">

            {% assign sortedAmiibo = series.characters | sort: "id" %}
            {% for amiibo in sortedAmiibo %}
            <div 
                class="amiibo-container tooltip {% if amiibo.owned %}owned-amiibo{% endif %}"
            >
                <span class="tooltiptext">
                    Released on {{amiibo.release}}
                </span>
                <img 
                    style="width: 100px; height: 118px;"
                    src="{% link {{site.data.amiibo.image-path}}{{series.folder-path}}{{amiibo.image}} %}"
                    alt="{{amiibo.name}}"
                />
                <span style="font-size: 0.8em; height: 3em; text-align: center">{{amiibo.name}}</span>
            </div>
            {% endfor %}
        </div>
    </div>

    {% endfor %}
</div>
