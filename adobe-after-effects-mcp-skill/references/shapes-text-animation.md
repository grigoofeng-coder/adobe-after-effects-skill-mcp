# Shapes, Text, And Animation

Use this file for shape layers, solids, custom paths, 3D layers, text/title work, intro stingers, and lower thirds.

## Shapes And Solids

Shape tool behavior depends on selection:

- If no layer is selected, drawing creates a new shape layer.
- If a footage/solid layer is selected, drawing creates a mask on that layer.
- If a shape layer is selected, drawing adds another shape inside the same layer.

Basic shape tools:

- Rectangle / rounded rectangle
- Ellipse / circle when holding `Shift`
- Polygon
- Star

Use fill/stroke controls to style shapes. Stroke is an outline; fill is the interior. For clean motion graphics, keep fill/stroke choices simple and add depth with shadows, glow, or light sweep only when needed.

## Custom Shapes

Use the Pen tool (`G`) for custom shapes:

1. Deselect all layers if you want a new shape layer.
2. Click points around the intended object.
3. Hold `Shift` for straight or constrained lines.
4. Close the path by clicking the first point.
5. Adjust points after drawing.

Use custom shape layers instead of masked solids when you need fill/stroke color to remain easily editable.

## Shape Effects

Open shape layer `Contents`, select the shape/group, then use `Add`:

- Repeater: duplicate arrows, hazard marks, pattern rows.
- Trim Paths: reveal outlines over time.
- Twist: twist path geometry.
- Zig Zag: jagged or wavy outline.
- Pucker & Bloat: curve or flower-like deformation.
- Round Corners: soften hard paths.

Repeater recipe:

1. Draw one arrow/mark.
2. Add `Repeater`.
3. Set copies to the desired count.
4. Adjust repeater transform position/offset.
5. Edit the original path; repeated copies update automatically.

## 3D Shapes

For real 3D shape/text extrusion:

1. Set the comp renderer to Cinema 4D when extrusion is needed.
2. Create a shape/text layer.
3. Enable the 3D layer switch.
4. Open `Geometry Options`.
5. Increase `Extrusion Depth`.
6. Add `Layer > New > Light` so depth/shadows are visible.
7. Rotate with 3D orientation/rotation properties.

Use lower preview resolution while working. Extruded 3D is heavier than normal 2D layers.

Fake 3D:

- Use `CC Sphere` on a flat map/image to create a globe.
- Use `CC Cylinder` for wrapped cylinder-like media.
- Animate effect rotation/radius instead of true 3D geometry when speed matters.

## Text Basics

Create text with:

- `Ctrl+T`, click in comp, type.
- `Layer > New > Text`.
- Right-click timeline > `New > Text`.

Style in Character/Paragraph panels:

- Font and style family
- Fill and stroke color
- Font size
- Tracking/letter spacing
- Horizontal/vertical scaling
- Faux bold/italic, all caps, small caps, superscript/subscript
- Paragraph alignment

Set the text anchor point to the visual center before scaling/rotating.

## Animated Titles

Manual title animation:

1. Press `P`, `S`, `R`, or `T` depending on desired motion.
2. Set the final state first.
3. Set the start state offscreen, smaller, rotated, or transparent.
4. Easy Ease the keyframes.
5. Add a subtle ongoing scale movement if the title would otherwise feel static.

Animation presets:

- `Animation > Apply Animation Preset`
- Useful folders: text animate-in/out, movement transitions, behaviors, backgrounds.
- Presets save time but reduce precision. Use manual keyframes when the exact path/timing matters.

Common title stack:

- Main title uses preset such as slow fade on.
- Subtitle uses manual opacity fade.
- Both layers share a slow scale-up.
- Both fade out near the end.

## Text Effects

Text animator effects:

1. Open text layer.
2. Use `Animate`.
3. Add Fill Color, Stroke Color, Skew, Tracking, Position, Scale, etc.
4. Keyframe animator values.

Color pulse recipe:

- Add Fill Color RGB and Stroke Color RGB.
- Start with fill A / stroke B.
- At 2s swap to fill B / stroke A.
- Copy/paste alternating keyframes.

Video inside text:

1. Put video layer below text.
2. Set the video layer Track Matte to Alpha Matte using the text layer.
3. Precompose the video+text pair if applying shadows to the combined result.
4. Apply Drop Shadow to the precomp for a solid shadow.
5. Keep text large/bold so the video is readable inside letters.

Write-on text:

1. Create text.
2. Apply `Write-on`.
3. Set brush size large enough to cover each letter stroke.
4. Set paint style to reveal original image.
5. Keyframe brush position along the letter paths.
6. For video-inside-text write-on, precompose the matte result and apply Write-on to the precomp.

## Lower Third Recipe

1. Create rounded/rectangular shape bars in the lower third.
2. Precompose shape bars if masking them as a unit.
3. Use a diagonal mask with feather to wipe bars on.
4. Add name and secondary line text.
5. Precompose text and mask it on from the opposite direction.
6. Add Drop Shadow to the shape/text group.
7. Copy/paste and reverse mask keyframes to animate out.
8. Export with alpha if the lower third must be reused.

## Intro Stinger Recipe

1. Decide final frame first: logo/name plus backing shape.
2. Build shape elements around the logo/name.
3. Animate shape scale from 0 and rotation into final state.
4. Animate text with a preset or manual scale/opacity.
5. Add subtle wiggle/rotation only if it fits the brand.
6. Add shadows/glow sparingly.
7. Trim work area to the stinger length.
8. Export with alpha for reuse over video.
