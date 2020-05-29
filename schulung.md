---
layout: training
title: Schulung - React mit TypeScript und Redux

permalink: /schulung
navbar: true
navbar_title: Schulung
navbar_order: 2

image_large_url: /assets/training.svg
image_large_description: Schulung Symbolbild

image_small_url: /assets/training.svg
image_small_description: Schulung Symbolbild

description_short: React Schulungen bei Dir im Unternehmen. Von Entwicklern, für Entwickler.

date: 2020-05-29
categories: schulung update

author: Pawel Sawicki
---

<img
  src="{{ page.image_large_url }}"
  alt="{{ page.image_large_description }}"
  style="width: 90%; margin-bottom: 30px;"
/>
<p>
  React ist eine JavaScript Bibliothek zur Entwicklung von
  Web-Benutzeroberflächen, sogenannter Single Page Applications (SPA).
</p>
<p>
  React wurde ursprünglich von Jordan Walke, einem Softwareingenieur bei
  Facebook, entwickelt und 2011 erstmals für Facebooks Newsfeed und später 2012
  für Instagram eingesetzt. Im Mai 2013 wurde von Facebook angekündigt, React
  zukünftig als Open-Source-Projekt weiterführen zu wollen.
</p>

<h2 class="post-list-heading">{{ page.list_title | default: "Lektionen" }}</h2>

{%- assign lectures = site.tutorial -%}
{%- assign lecture_numbers = lectures | map: 'lecture' | uniq | sort -%}

<ol class="tutorial">


  {%- for lecture_number in lecture_numbers -%}
    {%- assign sub_lectures = lectures | where: 'lecture', lecture_number  | sort: 'sublecture'-%}

    <li>
      {%- assign lecture_name = sub_lectures | map: 'lecture_title'| first -%}
      <span>{{ lecture_name }}</span>
      <ol> 
        {%- for lecture in sub_lectures -%}
        <li>
          <a class="" href="{{ lecture.url | relative_url }}">
            {{ lecture.sublecture_title | escape }}
          </a>
        </li>
        {%- endfor -%}
      </ol>
    </li>

  {%- endfor -%}

  
  
</ol>
