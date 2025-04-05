---
title: Wendy Garrison
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
  - Heavy Hoisters
---

# Wendy Garrison
The [Windy Gate](/FATE_in_the_BAWG/locations/Windy_Gate.html) chapter boss of the [Heavy Hoisters](/FATE_in_the_BAWG/factions/heavy_hoisters.html), built like an ox Wendy looks like she spends all day throwing parachute platforms with main strength.


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