# Cloud Chaser dev clarity/audio pass

This is not a release candidate. It is a prototype/dev playtest build focused on reducing sensory noise and screen clutter.

## Player feedback addressed

- Music felt obnoxious.
- The game screen felt cluttered.

## Changes made

1. Music is now **off by default**.
2. Sound effects are quieter.
3. Optional music is slower, softer, and less piercing when manually enabled.
4. `M` now behaves as an audio toggle, not a forced music toggle.
5. Clean View is now **on by default**.
6. Scanlines, screen shake, ghost replay, and course-sign overlays are now **off by default**.
7. The HUD was reduced to essential play information: world, score, time, HP, clouds, storm, and gust.
8. Routine objective ribbon text is hidden in Clean View unless danger/exit state makes it relevant.
9. Tutorial coaching no longer stacks on top of the intro title card in Clean View.
10. Intro card was shrunk in Clean View so it stops blocking half the playfield.
11. Decorative street props, extra course signs, foreground silhouettes, and bottom post-FX labels are suppressed in Clean View.
12. Backgrounds receive a stronger readability wash in Clean View so gameplay objects separate better from scenery.
13. Saved settings use `cloudChaserSettingsV3` so old noisy defaults do not leak forward from previous localStorage.
14. The build text now identifies the package as a prototype playtest build, not an itch/release candidate.

## Defaults after this pass

- Music: off
- Sound FX: on, quieter
- Clean View: on
- Course signs: off
- Scanlines: off
- Screen shake: off
- Ghost replay: off
- Tutorial coach: on, less intrusive

## Validation

Passed:

```bash
node --check src/game-source.js
node tools/build_single_html.js
node tools/regression_harness.js
node tools/browser_level_smoke.js
node tools/capture_screenshots.js
```

Known limit: this is still a prototype. The screen is cleaner, but the underlying art direction still has a lot of high-detail scenery. A deeper pass should simplify stage silhouettes, reduce background text, and make collectible/enemy colors more reserved.
