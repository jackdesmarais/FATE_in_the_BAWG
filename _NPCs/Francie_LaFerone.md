---
title: Francie LaFerone
layout: default
sessions:
  - Arc 1:
    - Scenario 1: 2025_03_23_Session2_Clearing_Gerties_Greens
location:
  - Windy Gate
faction:
  - Pulley Pullers
---

# Francie LaFerone
Francie is short and thin with a swoop topped undercut, frameless glasses, and a loose button up with the collar open and the sleeves rolled up. Tattoos of intertwined mechanisms peak from the edges of their collars and cuffs. They run the [Windy Gate](/FATE_in_the_BAWG/locations/Windy_Gate.html) chapter of the [Pulley Pullers](/FATE_in_the_BAWG/factions/Pulley_Pullers.html).


{% assign sessions = page.sessions %}
{% if sessions %}
## Sessions appearing
{% for arc_hash in sessions %}
{% for arc_name, scenarios in arc_hash %}
{% if scenarios.first.first %}
  {% for scenario in scenarios %}
  {% for scenario_name, session_file in scenario %}
- [{{ arc_name }} - {{ scenario_name }}: {{ session_file }}](/FATE_in_the_BAWG/session_notes/{{ arc_name | replace: " ", "_" }}/{{ scenario_name | replace: " ", "_" }}/{{ session_file }}.html)
  {% endfor %}
  {% endfor %}
{% else %}
- [{{ arc_name }}: {{ scenarios }}](/FATE_in_the_BAWG/session_notes/{{ arc_name | replace: " ", "_" }}/{{ scenarios }}.html)
{% endif %}
{% endfor %}
{% endfor %}
{% endif %}

{% assign locations = page.location %}
{% if locations %}
## Locations seen
{% for location in locations %}
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
