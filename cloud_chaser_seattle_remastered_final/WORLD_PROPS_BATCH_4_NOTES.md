# Cloud Chaser World Props Batch 4

Integrated a new authored Seattle world-prop atlas at:

- world_art/world_props.png

Runtime changes:
- Loads the prop atlas as an external image asset.
- Draws low-opacity authored props in Clean View.
- Draws stronger authored props in detailed view.
- Falls back to the old procedural location props if the prop atlas is missing or fails to load.

Updated prop themes:
- market stall
- Seattle Center arch
- waterfront pier
- Gas Works pipe cluster
- Fremont bridge/troll-inspired structure
- monorail train/support

Preserved:
- Corrected Cloud Chaser player sheets
- Upgraded enemy/boss atlas
- Approved Seattle background batch
- Collision, hazards, pickups, and gameplay logic

QA notes:
- Prop atlas is 768x128, six 128x128 cells.
- Because props are decorative, browser playtest should focus on whether they create visual clutter around hazards or pickups.
