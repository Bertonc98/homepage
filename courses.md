---
layout: page
title: Courses
permalink: /courses/
description: Courses by Alberto Bertoncini.
---

## Informatica e Biostatistica

{% for file in site.data.courses.ieb_files %}
- [{{ file }}](/src/IeB/{{ file }})
{% endfor %}
