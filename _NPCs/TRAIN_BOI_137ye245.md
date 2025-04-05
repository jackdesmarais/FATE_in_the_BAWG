---
title: Train_Boi_137ye245
layout: default
sessions:
  - arc: Arc 0
    scenarios:
      - name: Scenario 0
        sessions:
          - 2025_02_23_Session1_Charecter_creation
location:
  - Windy Gate
---

# Train_Boi_137ye245
A conductor on the cable car that runs into [Aeol](/FATE_in_the_BAWG/locations/Aeol.html).

## Aspects
**Chipper conductor** \
**Pneumatic!**


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