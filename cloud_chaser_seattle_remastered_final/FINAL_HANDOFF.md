# Cloud Chaser Seattle Remastered Final Handoff

## Delivery Lock Summary

- Build name: Cloud Chaser Seattle Remastered Build
- Primary playable: `cloud_chaser_playable.html`
- Alternate playable entry: `cloud_chaser_seattle_remastered.html`
- Hub: `index.html`
- Player character name: Cloud Chaser
- Boss name: Cloud Baron
- Visual direction: high-detail painted sprite look, Seattle-themed world, readable gameplay-first overlays
- Canvas size: 960x540
- Sprite frame baseline: 64x64 for Cloud Chaser player sheets and non-player atlas cells
- Non-player atlas cell size: 64x64
- VFX atlas cell size: 96x96
- World prop atlas cell size: 128x128

## Sprite Sheet Spec

Cloud Chaser player sheets are separate horizontal strips:

| Sheet | Frame Size | Frames | Runtime Key |
| --- | ---: | ---: | --- |
| `cloud_chaser_idle_sheet.png` | 64x64 | 7 | `idle` |
| `cloud_chaser_walk_sheet.png` | 64x64 | 11 | `walk` |
| `cloud_chaser_run_sheet.png` | 64x64 | 11 | `run` |
| `cloud_chaser_jump_sheet.png` | 64x64 | 9 | `jump` |
| `cloud_chaser_attack_sheet.png` | 64x64 | 7 | `attack` |
| `cloud_chaser_hurt_sheet.png` | 64x64 | 3 | `hurt` |

Non-player and gameplay objects are in `cloud_chaser_snes_non_player_sprites.png`:

- Frame size: 64x64
- Atlas size: 512x320
- Columns: 8
- Rows: 5
- Margin: 0
- Spacing: 0
- Pivot default: center for collectibles/enemies, bottom-center for gates and tall hazards

VFX are in `effects/vfx_atlas.png`:

- Frame size: 96x96
- Atlas size: 768x96
- Columns: 8
- Rows: 1
- Margin: 0
- Spacing: 0

World props are in `world_art/world_props.png`:

- Frame size: 128x128
- Atlas size: 768x128
- Columns: 6
- Rows: 1
- Margin: 0
- Spacing: 0

## Frame Order / Animation Mapping

Player animation mapping:

| Animation | Runtime FPS | Loop |
| --- | ---: | --- |
| idle | 7 | yes |
| walk | 12 | yes |
| run | 18 | yes |
| jump | 11 | yes during airborne state |
| attack | 18 | no, state-timed |
| hurt | 10 | no, invulnerability-timed |

Key non-player frames:

- Enemies: `drone_idle_1`, `drone_idle_2`, `drone_alert`, `red_tape_barricade`, `red_tape_hopper`
- Boss: `cloud_baron_idle`, `cloud_baron_rage`, `cloud_baron_hit`
- Objects: `cloud`, `bonus_cloud`, `red_cloud`, `lost_cloud`, `spring_idle`, `spring_compressed`, `checkpoint_off`, `checkpoint_on`, `gate_locked`, `gate_open`
- Powerups: `feather_power`, `shoes_power`, `shield_power`, `star_power`, `lamp_power`, `heart_power`
- Interactables/VFX objects: `route_stamp`, `secret_cache_hidden`, `secret_cache_revealed`, `red_switch_block`, `dash_panel_ready`, `cloud_cannon`, `updraft_1`, `updraft_2`, `burst_impact`

VFX frame order:

1. `cloud_puff`
2. `cloud_trail`
3. `collect_spark`
4. `power_burst`
5. `enemy_hit`
6. `storm_swirl`
7. `shield_ring`
8. `dash_streak`

## Manifest Draft

See `asset_manifest.json` for the implementation-facing manifest. It uses zero-based atlas coordinates and preserves current runtime naming.

## HTML Preview / Export Notes

- Open `index.html` first for the test hub.
- Open `cloud_chaser_playable.html` for the primary playable build.
- `cloud_chaser_seattle_remastered.html` is intentionally kept in sync as an alternate entry point.
- External runtime assets are intentionally kept as files instead of embedding everything into the HTML:
  - `backgrounds/*.png`
  - `world_art/world_props.png`
  - `title_art/title_backdrop.png`
  - `effects/vfx_atlas.png`
- The player sheets and non-player atlas remain embedded/loaded by the current HTML runtime path as established by the prior build.

## Implementation Checks

Before calling this fully shipped in a browser, run this manual route:

1. Open `index.html`, then launch the playable.
2. Confirm the title screen shows the painted Seattle waterfront backdrop and `CLOUD CHASER`.
3. Start Pike Place 1-1 and confirm Cloud Chaser uses the approved player sheets.
4. Collect normal and bonus clouds, then verify pickup sparkles and HUD counters are readable.
5. Attack a drone and a red tape enemy to verify enemy hit VFX and atlas frames.
6. Trigger a spring, checkpoint, powerup, and dash panel.
7. Let the stormline approach and confirm the warning ribbon and storm swirl remain readable.
8. Open level select and sample one later Seattle level.
9. Reach or jump to the Cloud Baron encounter and confirm boss idle/rage/hit frames.
10. On a phone-sized viewport, confirm touch controls do not cover the player, gate, hazards, or required pickups.

## Known Limitation

Automated live browser screenshot QA could not run in this container because the Playwright browser executable is not installed. Static validation passed in the prior QA package and this final package preserves that validated build plus handoff metadata.
