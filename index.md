---
layout: default
title: Migration Folder Listing
---

# Migration Folder File Listing

<ul>
{% assign migration_files = site.static_files | where_exp:"file","file.path contains 'migration/output_from' and file.extname == '.json'" %}
{% for file in migration_files %}
  <li>
    <a href="{{ file.path | relative_url }}">{{ file.path | remove_first: 'migration/' }}</a>
  </li>
{% endfor %}
</ul>
