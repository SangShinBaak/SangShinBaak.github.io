---
layout: page
title: Publications
permalink: /publications/
description:
nav: true
nav_order: 3
---

## Preprints

<ul style="padding-left: 0;">
{% bibliography --file publications --template pub_bib --query @misc* %}
</ul>

---

## Published Papers

<ul style="padding-left: 0;">
{% bibliography --file publications --template pub_bib --query @article* %}
</ul>

---

## Thesis

<ul style="padding-left: 0;">
{% bibliography --file publications --template pub_bib --query @phdthesis* %}
</ul>
