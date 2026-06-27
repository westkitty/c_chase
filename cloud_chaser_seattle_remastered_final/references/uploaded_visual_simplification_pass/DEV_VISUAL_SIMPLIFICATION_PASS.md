# Cloud Chaser — Dev Visual Simplification Pass

## Triggering feedback

The previous cleanup helped, but the stage scenery still felt busy. The correct next move was to simplify background silhouettes and reduce decorative text.

## Design decision

The game should default to a readable prototype view. Seattle flavor can remain as a mood layer, but it must not compete with clouds, enemies, platforms, hazards, the stormline, or the player.

## Implemented changes

1. **Simplified Clean View background renderer**
   - Clean View no longer renders the full procedural landmark backdrop.
   - It now uses broad skyline, bridge, water, mountain, and stage-shape silhouettes.
   - No background landmark labels are drawn in Clean View.

2. **Subdued uploaded backgrounds**
   - Uploaded stage images are drawn at low opacity in Clean View.
   - Canvas filtering reduces saturation, brightness, and contrast before the readability wash is applied.

3. **Stronger gameplay readability wash**
   - Clean View now uses a darker, more graduated wash so the player layer reads first.
   - Ground/lower-field contrast is flattened so scenery does not fight platform geometry.

4. **Reduced decorative text**
   - Stage neon labels, landmark names, and background signs are not drawn in Clean View.
   - Tiny decorative sprite labels such as the van `CLOUD`, barricade `NO`, and bonus-cloud `P` are hidden in Clean View.
   - Hazard text labels are hidden in Clean View while their telegraph rings remain.

5. **Quieter perspective/floor layer**
   - Clean View uses fewer and softer floor bands.
   - The Mode-7 style grid no longer adds unnecessary line noise by default.

6. **Smaller always-on HUD**
   - The Clean View HUD is now a compact status strip.
   - The always-visible line focuses on clouds, time, HP, storm, gust, item, and chain.
   - Score/world flavor text is no longer permanently visible in the play HUD.

## What stayed

- Gameplay-relevant warnings still appear.
- Boss attack labels remain because they carry real survival information.
- Tutorial coaching remains, but it is still subordinate to play.
- Full visual flavor can still exist when Clean View is turned off.

## Validation

Passed:

```bash
node --check /tmp/cloud_chaser_visual_simplification.js
node /tmp/cloud_chaser_visual_vm_smoke.js
```

Limit:

Headless Chromium screenshot capture timed out in this runtime, so this pass is syntax/smoke validated but still needs a human eyeball pass in a normal browser.

## Next critique target

The next real design pass should focus on gameplay object contrast: clouds, enemies, springs, gates, and platforms should use a stricter visual priority ladder so the player instantly knows what matters.
