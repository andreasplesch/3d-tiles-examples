---
layout: default
title: Migration Folder Listing
description: a listing of all 3d tiles examples migrated to v. 1.1
viewer-url: https://andreasplesch.github.io/3d-tiles-examples/Viewer/?url=
---

# Migration Folder File Listing

{% assign migration_files = site.static_files | where_exp: "file", "file.path contains 'migration/output_from'" | where_exp: "file", "file.extname contains 'json' " %}
{% assign json11e_files = migration_files | where_exp: "file", "file.path contains 'output_from_1.1'" | where_exp: "file", "file.path contains 'tileset.json'" %}
{% assign json11_files = migration_files | where_exp: "file", "file.path contains 'tileset_1.1.json'" | concat: json11e_files %}
{% assign json_files = migration_files | where_exp: "file", "file.path contains 'output_from_1.0/'" | concat: json11_files %}

<ol>
{% for file in json_files %}
<li>
  <a target='_blank' href="{{ page.viewer-url }}{{ file.path | absolute_url }}">Viewer :eye: </a>
  <a href="{{ file.path | relative_url }}">{{ file.path | remove_first: 'migration/' }}</a>
</li>
{% endfor %}
</ol>
