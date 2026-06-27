# Cloud Chaser prototype visual simplification pass

This is a development/playtest iteration, not a release candidate.

The pass addresses the feedback that the game is cleaner than before but the scenery is still visually busy. The goal was restraint: fewer background details, fewer decorative words, lower visual contrast behind the player, and a cleaner default playfield.

## Open

Use `cloud_chaser/index.html` in a browser.

## Main changes

- Clean View now draws a simplified silhouette background instead of the full procedural landmark layer.
- Uploaded scenic backgrounds are heavily subdued in Clean View.
- Background stripes, fake rain, window grids, neon labels, landmark text, and decorative props are suppressed in Clean View.
- Decorative object text such as tiny van/cloud and barricade lettering is hidden in Clean View.
- Hazard telegraph text is hidden in Clean View; the ring/shape cue remains.
- The Clean View HUD is smaller and drops score/world labels from the always-visible strip.
- The floor perspective effect is quieter in Clean View.

## Validation

- JavaScript extracted from `index.html` passed `node --check`.
- A Node VM smoke test initialized the game script with stubbed canvas/browser APIs.
- Browser screenshot capture was attempted, but headless Chromium timed out in this runtime; no browser screenshot validation is claimed.

