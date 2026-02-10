---
layout: default
---

{{ content }}

{% capture location_content %}
{% assign session_notes = site.session_notes | where_exp: "note", "note.NPCs" %}
{% assign matching_notes = "" | split: "" %}
{% assign location_npcs = "" | split: "" %}

{% for note in session_notes %}
  {% assign found_in_note = false %}
  {% for npc in note.NPCs %}
    {% if npc.location contains page.title %}
      {% assign location_npcs = location_npcs | push: npc.name %}
      {% unless found_in_note %}
        {% assign matching_notes = matching_notes | push: note %}
        {% assign found_in_note = true %}
      {% endunless %}
    {% endif %}
  {% endfor %}
{% endfor %}

{% assign unique_npcs = location_npcs | uniq | sort %}
{% if unique_npcs.size > 0 %}
## NPCs seen here
{% for npc in unique_npcs %}
- [{{ npc }}](/FATE_in_the_BAWG/NPCs/{{ npc | replace: " ", "_" }}.html)
{% endfor %}
{% endif %}

{% assign culture_items = site.culture | where_exp: "item", "item.locations" %}
{% assign matching_culture_items = "" | split: "" %}
{% for item in culture_items %}
  {% if item.locations contains page.title %}
    {% assign matching_culture_items = matching_culture_items | push: item %}
  {% endif %}
{% endfor %}

{% if matching_culture_items.size > 0 %}
## Culture
{% assign sorted_culture_items = matching_culture_items | sort: "title" %}
{% for item in sorted_culture_items %}
- [{{ item.title }}]({{ item.url | relative_url }})
{% endfor %}
{% endif %}

{% if matching_notes.size > 0 %}
## Sessions appearing
{% for note in matching_notes %}
{% assign hierarchy = note.title %}
{% if note.parent %}
  {% assign hierarchy = note.parent | append: " - " | append: hierarchy %}
  {% assign parent_page = site.session_notes | where: "title", note.parent | first %}
  {% if parent_page.parent %}
    {% assign hierarchy = parent_page.parent | append: " - " | append: hierarchy %}
  {% endif %}
{% endif %}
{% assign path_parts = note.path | split: "/" %}
{% assign file_name = path_parts | last | remove: ".md" %}
{% assign dir_path = path_parts | slice: 1, path_parts.size | join: "/" | remove: ".md" %}

- [{{ hierarchy }}](/FATE_in_the_BAWG/session_notes/{{ dir_path }}.html)
{% endfor %}
{% endif %}
{% endcapture %}

{{ location_content | markdownify }} 