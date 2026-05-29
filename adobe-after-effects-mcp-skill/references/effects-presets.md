# Effects And Presets

Use this file for effect selection, effect stacking, color correction, audio effects, visualizers, light effects, generated backgrounds, and distortions.

## General Effect Strategy

- Effects are rarely final by themselves. Stack simple effects until the shot feels integrated.
- Animate effect parameters with keyframes for transitions and pulses.
- Use adjustment layers for effects that should apply to multiple clips.
- Precompose when a shadow/glow/matte should apply to a combined result instead of individual child layers.
- Use preview at lower resolution while tuning heavy effects.

## Animation Presets

Access through:

- `Animation > Apply Animation Preset`
- Effects & Presets > `Animation Presets`

Useful folders:

- `Text`: animate-in/out, behaviors, fades, optical effects.
- `Transitions - Movement`: stretch/blur, slide, zoom spiral, swoop.
- `Behaviors`: wiggle position, wiggle scale, wiggle rotation, opacity flashes.
- `Backgrounds`: generated animated backgrounds from solid layers.

Presets can be copied/reversed by copying generated keyframes and swapping their order.

## Blur And Sharpen

Common uses:

- Gaussian Blur: simple softening, background defocus.
- Directional Blur: motion blur feel.
- Radial Blur: spin/zoom blur.
- Vector Blur: aggressive stylized smear/liquid effect.
- Unsharp Mask: sharpen detail.

MCP match names:

- `ADBE Gaussian Blur 2`
- `ADBE Directional Blur`
- `ADBE Radial Blur`
- `ADBE Unsharp Mask`

## Color Correction

Basic controls:

- Brightness & Contrast: quick exposure/contrast adjustment.
- Vibrance: boost color or reduce saturation to black-and-white.
- Levels: adjust blacks/whites and recover over/under exposure.
- Lumetri Color: preferred all-in-one grade, including LUTs/creative looks.

Adjustment layer workflow:

1. Add `Layer > New > Adjustment Layer`.
2. Apply Lumetri/Curves/Levels to the adjustment layer.
3. Place above all clips that should share the grade.
4. Lower adjustment layer opacity if the look is too strong.

Change-color workflows:

- `Hue/Saturation`: good for single-color graphics/shapes.
- `Change to Color`: better when changing a specific sampled color in footage.
- `Colorama`: very stylized; use mainly for music videos, glitch, sci-fi, or surreal looks.
- `CC Toner`: vintage/sepia/western-like looks.

## Distort Effects

Mirror:

- Apply `Mirror`.
- Move Reflection Center.
- Rotate Reflection Angle.
- Use for music-video symmetry or stylized reflection.

Fisheye:

- Use `Spherize` or `CC Lens`.
- Increase radius/size carefully.
- Works best with footage that has extra resolution/work area.

Warp:

- Excellent for text.
- Use Arc, Bulge, Flag, Rise, Squeeze, Twist, etc.
- Animate Bend for living title motion.

Environment distortion:

- `CC Smear`: pull/stretch an area.
- `Twirl`: swirl a region; animate angle as a character turns or a beat hits.
- `Bulge`: big-head effect; keyframe center to follow the face/head.
- `Magnify`: similar but more obvious edges; feather if used.

Warp Stabilizer:

- Use when handheld footage is shaky.
- Apply and let analysis complete.
- It can take time, especially with 4K.
- If edges crop strangely, adjust stabilization options manually in AE.

## Light Effects

CC Light Sweep:

- Use behind or on text/logos for shine.
- Animate Direction for a sweep across the object.
- Animate Intensity/Width for pulse.
- Match light color to the text/logo color when integrating it.

CC Light Rays:

- Place center at an existing light source such as a window.
- Keyframe the center to remain attached to that source as the camera moves.
- Keep intensity believable unless intentionally supernatural.

Lens Flare:

- Use only when a real/credible light source exists.
- Keyframe flare center and brightness.
- Use Blend with Original to fade it in/out.
- Avoid floating flares that do not track with the source.

Glow:

- Use for neon, eyes, logos, titles, energy effects.
- Combine with rotoscoped eyes/objects for superhero-style looks.
- Glow threshold/radius/intensity interact strongly; tune gently.

## Generate Effects

Use Generate when creating visual elements from a solid:

- Advanced Lightning: lightning arcs.
- Beam: laser-like start/end line.
- Circle: useful with invert for old-cartoon iris close/open.
- Lens Flare: generated flare.
- Audio Spectrum / Audio Waveform: visualizers.
- Fractal Noise: animated texture/background base.

Generated backgrounds:

1. Create a solid.
2. Apply a background preset or generate effect.
3. Animate parameters if static.
4. Lower opacity or blend if using as atmosphere over footage.

## Audio Effects

Use Audio effects when AE is already the active environment:

- Delay: repeated echo effect.
- Flange & Chorus: robotic/alien voice.
- High-Low Pass: radio/walkie-talkie filtered voice.
- Reverb: large room/cave/hall sound.

For precise audio mixing, prefer dedicated audio tools or Premiere/Audition, but AE effects are useful for synced VFX moments.

## Audio Spectrum Visualizer

1. Import audio.
2. Create a solid.
3. Apply `Audio Spectrum` to the solid.
4. Set Audio Layer to the imported audio.
5. Increase Maximum Height.
6. Increase Frequency Bands for density.
7. Choose Digital, Analog Lines, or Analog Dots.
8. Use Side A, Side B, or Side A & B.
9. Adjust Start/End points to position horizontal, vertical, diagonal, or border visualizers.
10. Extend solid duration to cover full audio.

Use `Audio Waveform` for heart-monitor style line; use `Audio Spectrum` for common podcast/music visualizers.

## Polished Effect Stack Example

For a text annotation over footage:

1. Warp text into a playful arc.
2. Animate it in with `CC Lens` size.
3. Add Drop Shadow.
4. Add CC Light Sweep behind it on the footage or directly on the text.
5. Add a short shine sound effect.
6. Keyframe out by reversing the CC Lens animation.

For a light-rich room shot:

1. Warp Stabilizer on footage.
2. CC Light Rays from a window.
3. Lens Flare only while the window/light source is visible.
4. Text callout with Drop Shadow.
5. Light Sweep on text for shine.
