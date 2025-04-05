---
layout: default
---

{{ content }}

{% assign session_notes = site.session_notes | where_exp: "note", "note.NPCs" %}
{% assign matching_notes = "" | split: "" %}
{% assign all_locations = "" | split: "" %}
{% for note in session_notes %}
  {% for npc in note.NPCs %}
    {% if npc.name == page.title %}
      {% assign matching_notes = matching_notes | push: note %}
      {% if npc.location %}
        {% for loc in npc.location %}
          {% assign all_locations = all_locations | push: loc %}
        {% endfor %}
      {% endif %}
      {% break %}
    {% endif %}
  {% endfor %}
{% endfor %}

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

{% assign unique_locations = all_locations | uniq | sort %}
{% if unique_locations.size > 0 %}
## Locations seen
{% for location in unique_locations %}
- [{{ location }}](/FATE_in_the_BAWG/locations/{{ location | replace: " ", "_" }}.html)
{% endfor %}
{% endif %}

{% assign factions = page.faction %}
{% if factions %}
## Factions they are a part of
{% for faction in factions %}
- [{{ faction }}](/FATE_in_the_BAWG/factions/{{ faction | replace: " ", "_" }}.html)
{% endfor %}
{% endif %} 