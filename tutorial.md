---
layout: page
title: Tutorial - React mit Hooks und TypeScript
permalink: /tutorial/
navbar: false
navbar_title: Tutorial
navbar_order: 1

image_large_url: /assets/reactjs.svg
image_large_description: React JS Symbolbild

image_small_url: /assets/reactjs.svg
image_small_description: React JS Symbolbild

description_short: Lerne React anhand von anschaulichen Beispielen und Übungen.
---

<img
  src="{{ page.image_large_url }}"
  alt="{{ page.image_large_description }}"
  style="width: 100%; margin-bottom: 30px;"
/>
React ist eine JavaScript Bibliothek zur Entwicklung von
Web-Benutzeroberflächen, sogenannter Single Page Applications (SPA).

React wurde ursprünglich von Jordan Walke, einem Softwareingenieur bei
Facebook, entwickelt und 2011 erstmals bei Facebook eingesetzt.

Ab Mai 2013 steht React als Open-Source-Projekt für jedermann zur freien Verwendung. Daher kam es innerhalb kürzester Zeit im ganzen Silicon Valley an. Sei es nun *Facebook*, *Instagram*, *Airbnb* oder *Tesla*: **Die ganz Großen setzen auf React**.


Trotz dem Aufkommen vieler JavaScript basierten Bibliotheken und Frameworks zur Entwicklung von Webanwendungen, verteidigt React seine Marktposition als Platzhirsch - und erfährt mitunter die schnellste Weiterentwicklung.

Lass uns zusammen in die wunderbare Welt der *Singe Plage Applications* einsteigen. 

**Setze auch Du auf React**. Lass uns gemeinsam **React lernen**!



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
