# Cloud Chaser Player Batch 1 - Corrected

This corrected package rejects the generated idle/hurt replacements from the prior batch because they drifted off-model.

Canonical Cloud Chaser sheets embedded in the playable:
- idle: 7 frames, 64x64 cells
- walk: 11 frames, 64x64 cells
- run: 11 frames, 64x64 cells
- jump: 9 frames, 64x64 cells
- attack: 7 frames, 64x64 cells
- hurt: 3 frames, 64x64 cells

Decision:
Use the reviewed Cloud Chaser sheets directly for batch 1. They preserve the actual character identity, proportions, palette, cap, costume, silhouette, and frame scale. The generated replacement art was worse because it changed the character design.

Next art generation should target enemies/world first, or generate only a carefully controlled v2 candidate sheet for side-by-side QA before integration.
