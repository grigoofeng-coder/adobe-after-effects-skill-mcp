# Workflow Basics

Use this file for core After Effects operating patterns from the course: layout, importing, compositions, layer properties, keyframes, organization, and editing fundamentals.

## Workspace Mental Model

- Project/Media panel: imported footage, audio, graphics, compositions, precomps.
- Composition viewer: live preview of the active comp.
- Timeline/layers: layer order, trimming, keyframes, masks, transform properties.
- Effects & Presets: effects, animation presets, visual/audio processing.
- Preview panel/spacebar: playback. Use lower preview resolution (`Half`, `Third`, `Quarter`) when playback lags.

If panels get rearranged, use `Window > Workspace > Reset to Saved Layout`.

## Composition Setup

Create compositions in one of three common ways:

- `Composition > New Composition`
- New composition button in the Project panel
- Drag footage onto the new composition button to match the source settings

Common settings:

- 1920x1080, 29.97/30 fps, black background for general 1080p work.
- 1080x1080 for square social content.
- 1280x720 when intentionally editing 1080p footage in a 720p comp to gain framing room without scaling above 100%.
- Match source fps/duration when the goal is a direct edit of a clip.
- Use transparency grid when creating overlays, lower thirds, stingers, or alpha exports.

Course heuristic: when source footage is higher resolution than the delivery comp, frame by scaling down or repositioning instead of scaling above 100%. Scaling above source quality softens the image.

## Importing and Organization

Import by drag/drop or `File > Import > File`.

Keep the project panel organized early:

- `Footage`
- `Audio`
- `Comps`
- `Precomps`
- `Graphics`
- `Solids`

Rename comps from camera/file names to intent names such as `Comp_Intro_Title`, `Comp_GreenScreen_Key`, or `Main_Edit`.

## Essential Shortcuts

- `Ctrl+S`: save constantly.
- `V`: selection tool.
- `H`: hand/pan tool.
- `Z`: zoom tool.
- `W`: rotation tool.
- `Q`: shape tool.
- `G`: pen tool.
- `Ctrl+T`: text tool.
- `Ctrl+Shift+D`: split layer at playhead.
- `Ctrl+D`: duplicate selected layer.
- `Ctrl+Z`: undo.
- `S`: scale property.
- `P`: position property.
- `R`: rotation property.
- `T`: opacity property.
- `L`: audio levels.
- `LL`: waveform.
- `M`: mask properties.
- `B`: set work-area start.
- `N`: set work-area end.
- Hold `Shift` while resizing to constrain proportions or snap/lock movement.
- Hold `Y`/use Pan Behind tool to move the anchor point.

## Layer Properties

Use transform properties deliberately:

- Anchor Point: pivot for rotation/scale. Center it unless the animation needs an off-center pivot.
- Position: precise X/Y placement; use keyframes for movement.
- Scale: preserve quality by staying at or below 100% unless source resolution allows more.
- Rotation/Orientation: animate spins, tilts, 3D rotations.
- Opacity: fades, flickers, reveals.

For shapes, distinguish:

- Layer transform: transforms the whole layer.
- Shape contents transform: transforms a path/group inside the shape layer.

## Keyframe Basics

Keyframes store property values at times. AE interpolates between them.

Typical structure:

1. Move playhead to the desired end state.
2. Enable the stopwatch for a property.
3. Move to the start state.
4. Change the property.
5. Preview and adjust timing.
6. Select keyframes and apply Easy Ease when smoothness matters.

Common patterns:

- Fade in: opacity 0 -> 100.
- Fade out: opacity 100 -> 0.
- Slide in: position offscreen -> final position.
- Pop in: scale 0 -> 100 or 85 -> 105 -> 100.
- Camera shake imitation: alternating rotation/position keyframes, then Easy Ease.
- Effect pulse: animate brightness/contrast, glow intensity, lens size, light sweep intensity.

## Editing To Audio

Use `LL` to open waveform. For beat cuts:

1. Import video and music.
2. Open audio waveform.
3. Split video on waveform peaks with `Ctrl+Shift+D`.
4. Delete middle sections.
5. Hold `Shift` while dragging clips together to snap.
6. Add text or title at the final beat if useful.

This creates perceived sync even when beats are subtle, because cuts align with repeated waveform events.

## Preview Performance

Use these before blaming the project:

- Drop viewer resolution to `Half`, `Third`, or `Quarter`.
- Trim work area to the active section with `B`/`N`.
- Precompose heavy sub-stacks.
- Work in a fresh project for very heavy Roto Brush/glow/3D tests.
- Render previews before judging timing.
