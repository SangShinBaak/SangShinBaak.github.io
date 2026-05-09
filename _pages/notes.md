---
layout: page
title: Notes
permalink: /notes/
description: 강의 노트 및 물리학 공부 자료 모음
nav: true
nav_order: 4
---

강의 노트와 공부 자료를 PDF 파일로 제공합니다.  
`assets/pdfs/notes/` 폴더에 PDF를 추가하면 아래 목록에 자동으로 나타납니다.

---

{% assign note_files = site.static_files | where_exp: "file", "file.path contains '/assets/pdfs/notes'" | sort: "name" %}

{% if note_files.size > 0 %}

<ul class="notes-list" style="list-style:none; padding:0;">
{% for file in note_files %}
  <li style="margin: 0.6em 0;">
    <a href="{{ file.path }}" target="_blank" rel="noopener noreferrer">
      📄 {{ file.name | remove: ".pdf" | replace: "-", " " | replace: "_", " " }}
    </a>
  </li>
{% endfor %}
</ul>

{% else %}

<p style="color: gray;">아직 업로드된 노트가 없습니다.<br>
<code>assets/pdfs/notes/</code> 폴더에 PDF 파일을 넣어주세요.</p>

{% endif %}
