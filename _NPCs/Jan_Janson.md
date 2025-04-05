---
title: Jan Janson
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
  - Windy Gate Borough Commission
---

# Jan Janson
Jan Janson is a minor functionary for the [Windy Gate borough commission](/FATE_in_the_BAWG/factions/Windy_Gate_borough_commission.html), but he knows someday soon he'll be running all of [Aeol](/FATE_in_the_BAWG/locations/Aeol.html). Though currently stuck dealing with dragon population booms and legal battles over building permits, he sees each crisis as a potential big break that could launch his political career. He's always in a suit and tie with a sun shaped tie pin and a rock solid Mitt Romney haircut.

# Aspects
**Overworked minor functionary** \
**Damn I'm hot** \
**My responsibilities outstrip my authority but not my ambition**


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