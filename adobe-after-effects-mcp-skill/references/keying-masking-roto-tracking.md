# Keying, Masking, Rotoscoping, Tracking

Use this file for green screens, alpha mattes, masks, mask transitions, Roto Brush, and motion tracking.

## Green Screen / Chroma Key

Basic Keylight workflow:

1. Put green-screen footage in a comp.
2. Apply `Keylight 1.2`.
3. Use the eyedropper to sample the green background.
4. Toggle transparency grid to inspect the key.
5. Increase Screen Gain to remove wrinkles/uneven green.
6. Duplicate the keyed layer if blue/near-green subject regions become too transparent.
7. Place the new background below.
8. Add Drop Shadow to subject for separation.
9. Use an adjustment layer with a shared color grade to tie subject and background together.
10. Add subtle background/subject scale animation so the composite feels alive.

Notes:

- Wrinkled green screens require higher Screen Gain or extra cleanup.
- Blue clothing/hair can become semi-transparent because blue is close enough to green for some key settings.
- A static background often makes the subject look pasted on; add slight motion or grade.

## Artificial Green Screens

Artificial green screens are motion graphics rendered over green instead of alpha.

To create:

1. Build text/shape animation.
2. Add a bright green solid below.
3. Export or import into another comp.
4. Apply Keylight and sample green.
5. Replace the background.

In AE-only workflows, prefer alpha exports over artificial green screens when possible. Use green only when a target workflow expects chroma key.

## Alpha Matte / Video In Text

1. Put text layer above the video.
2. Set video Track Matte to Alpha Matte using the text.
3. Precompose text+video if applying global shadow/glow.
4. Use Drop Shadow on the precomp to make the filled text stand out.
5. Optional: animate text with Write-on or opacity/scale.

## Masks

Mask rules:

- Pen/shape tool on selected footage/solid creates a mask.
- Pen/shape tool with nothing selected creates a new shape.
- Press `M` to reveal mask properties.
- Mask Path can be keyframed.
- Feather softens edges.
- Masks are crops, not new vector artwork.

Still-image masking:

1. Select the image.
2. Use Pen tool.
3. Trace object edges.
4. Close path.
5. Adjust points while zoomed in.
6. Toggle transparency grid to inspect isolation.

Moving-object masking:

1. Draw the initial mask around the object.
2. Enable Mask Path stopwatch.
3. Move forward a few frames.
4. Adjust points to match the object.
5. Repeat until done.
6. Use more frequent keyframes when motion is fast or perspective changes.

Use masks for hard-edged objects, graphic transitions, and short shots. Avoid long organic masks unless necessary.

## Mask Transitions

A masking transition uses an existing object in footage to reveal the next clip.

Workflow:

1. Choose clip A where an object crosses the full frame or enough of the frame.
2. Place clip B below clip A.
3. At the first frame where the object starts revealing the background, draw a mask on clip A over the revealed region.
4. Enable Mask Path.
5. Move frame by frame or every few frames.
6. Adjust the mask edge to follow the moving object.
7. Add Mask Feather to hide a hard seam.
8. Trim/scale clip B so it begins at the reveal.
9. If the moving object slows, scale or cut clip A to keep the transition feeling smooth.

Best sources:

- Poles, doors, walls, foreground pass-bys, signs, people crossing camera, camera wipes.

Quality target:

- Viewer should feel the next shot was naturally carried in by the object.
- Use tight masks; visible background leaks break the illusion.

## Rotoscoping / Roto Brush

Use Roto Brush when isolating complex organic or moving shapes that would be tedious to mask manually.

Workflow:

1. Double-click footage layer to open Layer panel.
2. Select Roto Brush.
3. Adjust brush size with `Ctrl` + drag.
4. Paint green strokes over subject/object to include.
5. Hold `Alt` and paint red strokes to exclude unwanted areas.
6. Step forward frames and correct edge drift.
7. Reassign strokes when AE asks/when propagation stops.
8. Duplicate the original layer below if you need the original background to fade back in.
9. Replace the background below the roto layer.
10. Add transitions via opacity, blur, glow, or background animation.

Tips:

- Roto Brush is heavy. Work in short segments.
- Motion blur makes edges harder to track.
- It is best for seconds, not minutes.
- Use a fresh project or precomp for very heavy roto/glow work.

Common roto recipes:

- Object isolation: roto hands/product, put animated liquify/background behind, fade original background back in.
- Screen replacement: roto screen, invert foreground/background, place new clip underneath, scale/rotate new clip into screen, then zoom through.
- Glowing eyes: roto both eyes, duplicate original below, apply CC Light Rays and Glow to eye layer, keyframe intensity/radius up and down.

## Motion Tracking

Motion tracking attaches a layer to movement in footage.

Basic position track:

1. Select footage.
2. `Animation > Track Motion`.
3. Place Track Point over a feature that clearly contrasts with surroundings.
4. Inner box: feature to track.
5. Outer box: search area.
6. Analyze forward.
7. Create `Layer > New > Null Object`.
8. Set tracker target to the null.
9. Apply X/Y.
10. Parent text/logo/graphic to the null.

Good track points:

- High contrast marks.
- Corners.
- Logos.
- Colored objects against neutral backgrounds.
- Tree/sign edges if clear enough.

Poor track points:

- Flat colors.
- Motion blur.
- Repeating textures.
- Features that leave frame.
- Areas with changing reflections.

Scale/rotation track:

1. Enable Scale and/or Rotation in the tracker.
2. Use two track points on features that move relative to camera.
3. Analyze.
4. Apply to null.
5. Parent target layer.

If tracking drifts:

- Pick a more contrasty feature.
- Analyze shorter sections.
- Manually correct the null or target layer with extra keyframes.
- Avoid pretending a rough track is perfect; trim the shot or hide drift with motion.

## Integration Tricks

To make inserted text/logo feel in-scene:

- Add Drop Shadow.
- Match blur/sharpness to footage.
- Match color temperature with Lumetri/Curves.
- Add slight opacity/fade.
- Use scale/rotation track when the plane moves toward camera.
- Trim the tracked layer to only the section where the track is reliable.
