---
layout: page
title: Notes
permalink: /notes/
description: 강의 노트 및 물리학 공부 자료 모음
nav: true
nav_order: 4
---

강의 노트와 공부 자료를 PDF 파일로 제공합니다.  
`assets/pdfs/notes/과목명/` 폴더에 PDF를 추가하면 아래 목록에 자동으로 나타납니다.

---

{% assign note_files = site.static_files | where_exp: "file", "file.extname == '.pdf' and file.path contains 'pdfs/notes'" | sort: "path" %}

{% if note_files.size > 0 %}

{% comment %} 중복 없이 카테고리(서브폴더) 목록 수집 {% endcomment %}
{% assign categories = "" | split: "" %}
{% for file in note_files %}
  {% assign parts = file.path | split: "/" %}
  {% assign cat = parts[-2] %}
  {% unless categories contains cat %}
    {% assign categories = categories | push: cat %}
  {% endunless %}
{% endfor %}

{% for cat in categories %}
  {% assign cat_label = cat | replace: "-", " " | replace: "_", " " %}

### {{ cat_label }}

<ul style="list-style:none; padding-left:1rem;">
{% for file in note_files %}
  {% assign parts = file.path | split: "/" %}
  {% assign file_cat = parts[-2] %}
  {% if file_cat == cat %}
  <li style="margin: 0.4em 0;">
    <a href="{{ file.path }}" target="_blank" rel="noopener noreferrer">
      {{ file.name | remove: ".pdf" | replace: "-", " " | replace: "_", " " }}
    </a>
  </li>
  {% endif %}
{% endfor %}
</ul>

{% endfor %}

{% else %}

<p style="color: gray;">아직 업로드된 노트가 없습니다.<br>
<code>assets/pdfs/notes/과목명/</code> 폴더에 PDF 파일을 넣어주세요.<br>
예: <code>assets/pdfs/notes/classical-mechanics/CM-note-1.pdf</code></p>

{% endif %}
