---
layout: page
title: Reihe - React Hook der Woche
permalink: /hooks/
navbar: true
navbar_title: Hooks
navbar_order: 2

image_large_url: /assets/hooks.jpg
image_large_description: React Hook Symbolbild

image_small_url: /assets/hooks.jpg
image_small_description: React Hook Symbolbild

description_short: Jede Woche ein neuer React Hook, sinnvoll oder spaßig.

last_modified_at: 2020-05-30
---

<img
  src="{{ page.image_large_url }}"
  alt="{{ page.image_large_description }}"
  style="width: 100%; margin-bottom: 30px;"
/>

An dieser Stelle soll jede Woche ein neuer React Hook entwickelt werden.

Manche dieser Hooks sind sehr sinnvoll, für den täglichen Projekteinsatz. Andere Hooks hingegen, dienen dem Spaß und der Freude an der Entwicklung.

So oder so: Viel Spaß!

<h2 class="post-list-heading">{{ page.list_title | default: "React Hooks of the Week" }}</h2>

{%- assign weeks = site.hooks -%}
{%- assign week_numbers = weeks | map: 'week' | uniq | sort -%}

<ul class="hooks">


  {%- for week_number in week_numbers -%}
    {%- assign week = weeks | where: 'week', week_number  | first -%}
    <li>

      <a class="" href="{{ week.url | relative_url }}">
            {{week.week}} | {{ week.title | escape }}
          </a>
    </li>

  {%- endfor -%}

  
  
</ul>
