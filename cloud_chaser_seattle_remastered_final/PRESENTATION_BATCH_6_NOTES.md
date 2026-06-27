# Cloud Chaser Presentation Batch 6

Integrated a painted Seattle title/menu backdrop and updated the title presentation layer.

Updated runtime presentation:
- Added `title_art/title_backdrop.png` at the exact 960x540 game canvas size.
- Patched `cloud_chaser_playable.html` and `cloud_chaser_seattle_remastered.html` to load the title backdrop through the existing safe image-loader path.
- Reworked `drawTitleShowcase()` so title, level select, and options screens use the painted Seattle waterfront backdrop with subtle rain, storm lines, enemy silhouettes, and vignette treatment.
- Reworked the title overlay so the Cloud Chaser name sits directly over the scene with sharper canvas-rendered typography and a cleaner start prompt.

Preserved:
- Approved Cloud Chaser player sheets.
- Approved enemy/boss atlas frames, including Cloud Baron.
- Approved Seattle level backgrounds.
- Approved world prop sheet.
- Approved gameplay object atlas.
- Existing input, progression, level, pickup, enemy, and boss logic.

QA notes:
- JavaScript extracts pass `node --check` for both playable HTML files and the asset preview.
- The title backdrop is 960x540 RGB PNG and lives at the expected runtime path.
- Live browser screenshot QA could not run in this container because the Playwright browser executable is not installed.
