# Cloud Chaser UI Batch 8

Integrated a visual polish pass for the game shell and HUD.

Updated presentation:
- Renamed the browser title to `Cloud Chaser - Seattle Remastered Build`.
- Replaced the old prototype cabinet copy with `CLOUD CHASER - SEATTLE REMASTER`.
- Reworked the page/cabinet colors to better match the Seattle remaster direction.
- Updated the canvas frame accent from the older orange/purple prototype trim to a cleaner cyan/gold remaster frame.

Updated HUD:
- Added reusable badge-style HUD helpers.
- Rebuilt the full HUD into clear badge groups for world/title, score, time, health, cloud count, storm distance, gust/cloud blow, and chain.
- Rebuilt the clean-view HUD with the same visual language while keeping it compact.
- Replaced square health blocks with clearer heart-shaped health marks.
- Improved meter rendering with highlights and framed tracks.

Preserved:
- Approved Cloud Chaser player sheets.
- Approved enemy/boss, background, world prop, object, title, and VFX batches.
- Existing collision, scoring, pickup, powerup, enemy, boss, progression, and input logic.

QA notes:
- JavaScript extracts pass `node --check` for both playable HTML files and the asset preview.
- Live browser screenshot QA could not run in this container because the Playwright browser executable is not installed.
