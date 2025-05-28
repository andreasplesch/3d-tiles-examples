---
layout: default
title: Migration Folder Listing
description: a listing of all 3d tiles examples migrated to v. 1.1
viewer-url: https://andreasplesch.github.io/3d-tiles-examples/Viewer/?url=
---

# Migration Folder File Listing

{% assign migration_files = site.static_files | where_exp: "file", "file.path contains 'migration/output_from'" | where_exp: "file", "file.extname contains 'json' " %}

| Viewer link | file path |
| ----------- | --------- |
{% for file in migration_files %}
| <a href="{{ page.viewer-url }}{{ file.path | absolute_url }}">Viewer :eye: </a> | <a href="{{ file.path | relative_url }}">{{ file.path | remove_first: 'migration/' }}</a> |
{% endfor %}
