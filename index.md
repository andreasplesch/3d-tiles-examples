---
layout: default
title: Migration Folder Listing
viewer-url: https://andreasplesch.github.io/3d-tiles-examples/Viewer/?url=
---

# Migration Folder File Listing
<ol>
{% assign migration_files = site.static_files | where_exp: "file", "file.path contains 'migration/output_from'" | where_exp: "file", "file.extname contains 'json' " %}
{% for file in migration_files %}
  <li>
    <a href="{{ file.path | relative_url }}">{{ file.path | remove_first: 'migration/' }} -- </a>
    <a href="{{ page.viewer-url }}{{ file.path | absolute_url }}">Viewer</a>
  </li>
{% endfor %}
</ol>
