# FATE in the BAWG

A Jekyll-powered campaign wiki for a homebrew FATE game, viewable at [jackdesmarais.github.io/FATE_in_the_BAWG](https://jackdesmarais.github.io/FATE_in_the_BAWG).

## Overview
This is a living world document for a technicolor steampunk FATE campaign set in the city of [Aeol](/FATE_in_the_BAWG/locations/Aeol.html). The game features a free-form magic system built around channeling energy from conceptual elements.

## Website Structure

### Collections
- `_session_notes/`: Campaign session summaries, organized by arc and scenario
- `_NPCs/`: NPC character pages
- `_PCs/`: Player character pages
- `_locations/`: Location descriptions
- `_factions/`: Organization descriptions
- `_creatures/`: Creature descriptions
- `_subsystems/`: Game specific systems
- `_spiritual_realms/`: Alternate realities from which charecters can draw power to perform magic

### Automated Features
The site uses custom layouts to automatically maintain relationships between pages:

- `_layouts/NPC.html`: Shows sessions where an NPC appears and locations they've been seen in, based on session note front matter. NPC front matter is used to track which factions the NPC belongs to.
- `_layouts/location.html`: Lists NPCs that have been seen at a location and relevant sessions
- `_layouts/faction.html`: Shows NPC and PC members, plus sessions mentioning the faction based on session note content, NPC front matter, and PC front matter

### Session Notes Format
Session notes use YAML front matter to track:
- NPCs present and their locations
- Player characters present
- Parent arc/scenario structure

Example:
```yaml
---
title: Session Name
layout: default
parent: Scenario Name
NPCs:
- name: NPC Name
  location:
    - Location Name 
players:
- name: Player Name
  character: Character Name
---
```

### NPC and PC Front Matter
NPC and PC front matter is used to track which factions they belong to.
```yaml
faction:
  - Faction Name
title: NPC/PC Name
layout: NPC # in the case of NPCs
layout: default # in the case of PCs
```


## System
We are using the [FATE Core](https://fate-srd.com/fate-core) system with some homebrew additions.