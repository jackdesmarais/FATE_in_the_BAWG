---
title: Francie LaFerone
layout: default
sessions:
  - arc: Arc 1
    scenarios:
      - name: Scenario 1
        sessions:
          - 2025_03_23_Session2_Clearing_Gerties_Greens
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
{% for arc in sessions %}
{% for scenario in arc.scenarios %}
- [{{ arc.arc }} - {{ scenario.name }}: {{ scenario.sessions[0] }}](/FATE_in_the_BAWG/session_notes/{{ arc.arc | replace: " ", "_" }}/{{ scenario.name | replace: " ", "_" }}/{{ scenario.sessions[0] }}.html)
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
