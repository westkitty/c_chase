# Cloud Chaser Optimized Build

Open `index.html` first.

This package compares and merges the current test-ready build with the uploaded visual-simplification build.

Main correction: object contrast cues are preserved but made less intrusive. The in-game Options menu now includes:

- Clean view
- Object cues
- Object cue labels

Recommended default: Clean view ON, Object cues ON, Object cue labels OFF.

Known limits: not browser-playtested here, not mobile-device-tested here, guide overlay remains standalone.

## Patch: Non-blocking tutorial coach
The tutorial coach no longer draws a large panel over the playfield. It now renders in an external dock below the game cabinet, with a compact collision-avoiding canvas fallback only if the dock is unavailable.
