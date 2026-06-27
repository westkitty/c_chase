# Cloud Chaser World Batch 3

Integrated six high-detail painted Seattle background images at the runtime paths already referenced by the game:

- backgrounds/level-01-market.png
- backgrounds/level-02-center.png
- backgrounds/level-03-waterfront.png
- backgrounds/level-04-gasworks.png
- backgrounds/level-05-fremont.png
- backgrounds/level-06-monorail.png

Preserved:
- Corrected canonical Cloud Chaser player sheets from batch 1
- Upgraded enemy/boss atlas from batch 2
- Existing collision, platform layout, hazards, pickups, and gameplay logic
- Existing clean-view readability wash and procedural fallback backgrounds

QA notes:
- Backgrounds are 960x540 to match the canvas.
- Backgrounds are deliberately muted/darkened so sprites remain readable.
- The runtime already maps bonus/moonbonus to Gas Works and boss to Fremont.
- Browser playtest is still recommended because the final look depends on runtime clean-view opacity and parallax overlays.
