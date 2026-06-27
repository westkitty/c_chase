# Cloud Chaser QA Batch 9

Integrated the final readability/playability QA pass before handoff.

Readability fixes:
- Separated the objective ribbon from the top HUD so warnings no longer crowd the main counters.
- Moved the route map below the polished top HUD band.
- Moved active powerup indicators into their own lower HUD strip.
- Moved the collection tracker to a separate right-side strip below active power indicators.
- Kept the clean-view HUD compact while giving meters and health enough space to read during play.

Validation:
- JavaScript extracts pass `node --check` for both playable HTML files and the asset preview.
- Required major visual assets are present at their runtime paths.
- Major asset dimensions match expected sizes:
  - `title_art/title_backdrop.png`: 960x540
  - `effects/vfx_atlas.png`: 768x96
  - `world_art/world_props.png`: 768x128
  - `cloud_chaser_snes_non_player_sprites.png`: 512x320
- Visible shell copy is now `Cloud Chaser - Seattle Remastered Build` / `CLOUD CHASER - SEATTLE REMASTER`.

Preserved:
- Approved Cloud Chaser player sheets.
- Approved enemy/boss, background, world prop, object, title, VFX, and HUD batches.
- Existing collision, scoring, pickup, powerup, enemy, boss, progression, input, and level logic.

Known limitation:
- Live browser screenshot QA could not run in this container because the Playwright browser executable is not installed.
