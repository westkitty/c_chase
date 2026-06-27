# Cloud Chaser Build Comparison + Optimization Report

## Compared builds

| Build | Path | Role | Result |
|---|---|---|---|
| Current build | `/mnt/data/cloud_chaser_test_ready` | Later test-ready package assembled from the previous pass | Stronger testing hub, guide overlay, object contrast work, more support files |
| Uploaded build | `/mnt/data/cloud_chaser_visual_simplification_pass(2).zip` | Visual simplification source package | Cleaner playable baseline with clearer dev documentation |
| Optimized build | `/mnt/data/cloud_chaser_optimized_build` | Merged/corrected output | Uses current build as base, adopts uploaded build's restraint, adds toggleable object cues |

## High-level finding

The current playable and the uploaded playable share the same core game. The meaningful code difference is that the current build adds object-priority markers/cues on top of the uploaded visual-simplification build.

That later object-contrast work is valuable, but it partially conflicts with the uploaded build's main design win: reduced scenery/text clutter in Clean View. The optimized build keeps the object readability improvement but makes it less noisy and user-controllable.

## Ways the uploaded build is better than the current build

1. **Cleaner default visual philosophy** — it commits harder to visual simplification and reduced background noise.
2. **Less gameplay overlay clutter** — it does not add many object marker labels on top of Clean View.
3. **Smaller playable HTML** — uploaded playable is about 402 KB; current playable is about 406 KB.
4. **Better source-package documentation** — includes explicit dev notes for visual simplification, audio clarity, controls/accessibility, timing, QA, and license notes.
5. **Clearer package identity** — states plainly that it is a prototype/dev playtest build, not a final release.
6. **Direct `index.html` deployment path** — the game itself is the package index, so opening the ZIP folder is simple.
7. **Better design rationale** — documents why scenery, labels, HUD, and noise were reduced.
8. **Cleaner Clean View baseline** — no extra object cue system exists to accidentally reintroduce noise.
9. **Preserved compatibility filename** — includes both `index.html` and `cloud_chaser_seattle_remastered.html` as playable duplicates.
10. **QA notes are candid** — admits screenshot/browser validation limits.

## Ways the uploaded build is worse than the current build

1. **No guide overlay** — it lacks the generated route/walkthrough companion.
2. **No test hub** — it opens straight into the game but does not organize testing surfaces.
3. **No current object-contrast pass** — important objects can still compete with scenery.
4. **No toggleable object cue system** — no way to raise/lower object readability without code changes.
5. **No combined release-style package** — current package has more downstream handoff artifacts.
6. **No extracted player/contact-sheet work** — lacks the later asset inspection outputs.
7. **No route manifests from the prompt workflow** — no six-level walkthrough spine.
8. **No standalone asset inventory output** — only the preview and sprite PNG are present.
9. **Less helpful for multi-tab testing** — no clear launcher for game + guide + asset preview.
10. **Still not browser-playtested** — documentation says human playtest and screenshot validation are incomplete.

## Ways the current build is better than the uploaded build

1. **Includes a test hub** with links to game, guide overlay, asset preview, and named source build.
2. **Includes standalone guide overlay** generated from the level route manifest.
3. **Includes object sprite preview** in the same test package.
4. **Has stronger object readability work** via clean-priority markers around important objects.
5. **Includes later phase outputs** such as manifests, QA reports, handoff notes, and release-candidate packaging.
6. **Better for production continuation** because it has organized outputs instead of only a playable prototype.
7. **Better for walkthrough development** because the route/guide layer exists.
8. **Better asset archaeology** because player/object extraction and manifests were created.
9. **More explicit known-limit tracking** from the audit and release notes.
10. **Closer to the requested end goal** of game + guide + assets + handoff package.

## Ways the current build is worse than the uploaded build

1. **Object cues are too assertive** — the current object-contrast pass risks undoing the visual simplification pass.
2. **Too many labels in Clean View** — labels like JUMP, LAUNCH, CHECK, STAMP, BOOST, SWITCH can crowd play space.
3. **Slightly larger playable HTML** due to added cue functions and calls.
4. **Guide overlay is not integrated into the game runtime** — it is a companion tab, not an in-game overlay.
5. **Some earlier claims were too broad** — route pages/visual parity/playable overlay wording needed correction.
6. **No real browser/device playtest was performed** in this runtime.
7. **Hub copy called the playable original** even though it was actually a later object-contrast variant.
8. **No user-facing control for object cue intensity** before this optimization.
9. **More moving parts** — the package is useful but easier to misunderstand.
10. **Higher risk of stale artifacts** because many phase folders and generated docs exist.

## Corrections implemented in the optimized build

1. **Used current build as the base** because it contains the guide overlay, hub, and object-contrast improvements.
2. **Kept the uploaded build's restraint** by reducing cue intensity and removing most always-on cue labels.
3. **Added `Object cues` option** to the in-game options menu.
4. **Added `Object cue labels` option** to let testers enable/disable non-critical labels.
5. **Defaulted object labels to OFF** so Clean View remains clean.
6. **Kept critical labels only** by default: `EXIT`, `LOCKED`, `DANGER`, and `BLOW`.
7. **Softened object marker opacity and stroke weight** so cues support gameplay without shouting over it.
8. **Updated hub copy** to identify this as an optimized merge, not the untouched source build.
9. **Copied uploaded source docs into `references/uploaded_visual_simplification_pass/`** for audit continuity.
10. **Validated inline JavaScript syntax** for game, named game copy, guide overlay, and sprite preview.

## Optimized behavior

Open the optimized playable and press `O` for Options:

- `Clean view`: keeps the simplified playfield.
- `Object cues`: turns the object marker system on/off.
- `Object cue labels`: adds/removes extra instructional labels.

Recommended default for normal playtesting:

- Clean view: ON
- Object cues: ON
- Object cue labels: OFF

Recommended diagnostic mode:

- Clean view: ON
- Object cues: ON
- Object cue labels: ON

Recommended visual-noise comparison:

- Clean view: ON
- Object cues: OFF
- Object cue labels: OFF

## Validation performed

| Check | Result |
|---|---:|
| Uploaded ZIP extracted | pass |
| Current build files found | pass |
| Optimized playable generated | pass |
| Optimized named playable generated | pass |
| Guide overlay preserved | pass |
| Asset preview preserved | pass |
| PNG asset opens | pass |
| Inline JS syntax: playable | pass |
| Inline JS syntax: named playable | pass |
| Inline JS syntax: guide overlay | pass |
| Inline JS syntax: asset preview | pass |
| Human browser playtest | not performed |
| Mobile device touch test | not performed |
| Full guide overlay runtime integration | not implemented |

## Remaining limits

- The guide overlay is still standalone, not injected into the live game canvas.
- No real browser/gameplay completion test was performed here.
- No mobile hardware test was performed here.
- No new art was generated; this was a code/package optimization pass.

## Next best test

1. Open `index.html`.
2. Launch `Run Optimized Playable Game`.
3. Press `O` and compare:
   - Object cues ON/OFF.
   - Object cue labels ON/OFF.
4. On mobile, verify the touch controls do not cover hazards, clouds, gates, or tutorial/guide-critical objects.
5. Keep the guide overlay open in another tab while testing route clarity.

## Follow-up Patch: Tutorial Coach Must Not Block Player
User screenshot showed the `COACH` instruction panel covering the player/path area. This was a real UX failure.

### Correction
- Removed the large in-canvas tutorial panel behavior.
- Added a `#coachDock` element outside the active canvas playfield.
- Tutorial text now appears below the game cabinet and cannot obscure the player.
- Added an emergency canvas fallback that uses a compact ribbon and checks the player's screen-space rectangle before placing itself.

### Validation
- Playable JavaScript syntax checked after patch.
- Named remastered playable JavaScript syntax checked after patch.
- Guide overlay and asset preview JavaScript syntax rechecked.

### Remaining Test Needed
- Manual browser test on desktop and mobile to confirm the coach dock layout feels good across screen sizes.
