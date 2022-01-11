---
title: Забери питомца из приюта 2
layout: default
---

<style>
a img.photo { border-color: transparent; border-width: 3px; border-style: solid; }
a:hover img.photo { border-color: #88CCCC; }
li.card { border-color: #f3f3f3; border-width: 1px; border-style: solid; background-color: #f9f9f9; border-radius: 0.9rem; padding: 10px; list-style: none; }
</style>

исходники: 
<a href="{{ '/blob/master/_data/pets2.csv' | prepend: site.github.repository_url | relative_url }}"><b>таблица</b></a>, 
<a href="{{ '/blob/master/_includes/petlist.md' | prepend: site.github.repository_url | relative_url }}">скрипт рендеринга</a>

{% include petlist.md %}
