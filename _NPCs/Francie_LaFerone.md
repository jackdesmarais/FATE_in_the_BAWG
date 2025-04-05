---
title: Francie LaFerone
layout: default
faction:
  - Pulley Pullers
---

# Francie LaFerone
Francie is short and thin with a swoop topped undercut, frameless glasses, and a loose button up with the collar open and the sleeves rolled up. Tattoos of intertwined mechanisms peak from the edges of their collars and cuffs. They run the [Windy Gate](/FATE_in_the_BAWG/locations/Windy_Gate.html) chapter of the [Pulley Pullers](/FATE_in_the_BAWG/factions/Pulley_Pullers.html).

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
- [{{ hierarchy }}](/FATE_in_the_BAWG/session_notes/{{ note.path | split: "/" | slice: -2, 2 | join: "/" | remove: ".md" }}.html)
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
