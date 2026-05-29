# Export Recipes

Use this file for render/export choices from After Effects.

## Normal Video Export

Preferred course workflow:

1. Set work area with `B` and `N`.
2. `Composition > Add to Adobe Media Encoder Queue`.
3. Use Format: `H.264`.
4. Output as `.mp4`.
5. Render from Media Encoder.

Why:

- Much smaller file sizes than QuickTime.
- Good quality for web/social delivery.
- Faster and more practical for normal videos.

Avoid using AE Render Queue QuickTime for normal delivery unless a specific post-production workflow requires it. It can produce huge files.

## Faster AE Render Queue Preview

If rendering inside AE Render Queue:

- Press `Caps Lock` before rendering to disable live preview updates.
- This can speed renders and reduce crash risk on heavy comps.

This is most helpful on slower machines or heavy effects such as Roto Brush, Glow, 3D, and Warp Stabilizer.

## Transparent Background / Alpha Export

Use this for lower thirds, intro stingers, isolated green-screen characters, animated shapes, and overlay assets.

1. Toggle transparency grid and ensure no background layer is visible.
2. Set work area.
3. Add to Adobe Media Encoder Queue or Render Queue.
4. Format: `QuickTime`.
5. Video Codec: `Animation`.
6. Depth/Channels: `RGB + Alpha` or equivalent `8 bpc + Alpha`.
7. Render.
8. Reimport and test over a colored solid or footage layer.

Normal H.264 does not preserve alpha.

## Still Frame Export

Best simple method:

1. Park playhead on desired frame.
2. `Composition > Save Frame As > File`.
3. Output Module: PNG Sequence or JPEG Sequence.
4. PNG is preferred for quality/transparency.
5. Render the queued still.

Alternative:

- Set work area start/end to a single frame with `B` and `N`, then render a PNG/JPEG sequence.
- This is more awkward than `Save Frame As`.

## Export Checks

Before rendering:

- Confirm active composition is the intended one.
- Confirm work area length.
- Confirm preview-only resolution does not affect final settings.
- Confirm alpha intent: background visible for normal video, transparency grid for overlays.
- Confirm audio is enabled only when needed.
- Confirm frame rate and duration match delivery.

## Practical Presets

- YouTube/social normal video: H.264 MP4, 1920x1080, 30 fps unless source/project says otherwise.
- Transparent overlay: QuickTime Animation RGB+Alpha.
- Screenshot/promo still: PNG.
- Intermediate high-quality video without alpha: QuickTime/ProRes if available, only when the downstream workflow needs it.
