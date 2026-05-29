# Practical Recipes

Use this file when the user asks for a concrete After Effects outcome. Combine with the technique references as needed.

## Mini Lesson: Slow-Motion Clip With Preset Transition

1. Import clip.
2. Create comp from footage to match source.
3. Disable audio if not needed.
4. Trim start/end with `Ctrl+Shift+D`.
5. Set preview resolution lower if playback lags.
6. Apply `Animation > Apply Animation Preset > Transitions - Movement > Stretch and Blur`.
7. Copy/paste transition keyframes near the end and reverse order for transition-out.
8. Set work area end with `N`.

## Beat-Synced Edit

1. Import video and audio.
2. Create comp from video or target delivery settings.
3. Add audio to timeline.
4. Press `LL` to show waveform.
5. Play and split video at beat peaks.
6. Delete middle sections and snap remaining clips.
7. Add final text such as `FIN` or a title card.
8. Trim work area.

## Framed Shot Without Quality Loss

1. Inspect footage resolution.
2. If source is 1080p and comp is 1080p, avoid scaling above 100%.
3. If reframing is needed, reduce comp to 720p or use higher-res source.
4. Reposition and rotate at 100% scale.
5. Use 4K source in 1080p comps for safer reframing.

## Hazard Warning Arrows

1. Import/reference arrow graphic if tracing.
2. Create one custom arrow with Pen tool.
3. Set fill to yellow/orange and optional stroke.
4. Open shape contents.
5. Add `Repeater`.
6. Set copies to 3.
7. Adjust repeater transform position/offset.
8. Refine original path; repeats update.

## 3D Globe With Stars

1. Import flat world map.
2. Apply `CC Sphere`.
3. Increase radius.
4. Keyframe sphere rotation over 10 seconds.
5. Create star shape layers.
6. Enable 3D switch on stars.
7. Add light.
8. Keyframe orientation/rotation of stars.
9. Duplicate stars at varied scales/extrusion depths.
10. Optional: animate globe radius larger and stars smaller for depth.

## Animated Course Title

1. Create main title.
2. Create subtitle.
3. Style main title bold, subtitle italic/smaller.
4. Apply text preset such as slow fade-on to main title.
5. Keyframe subtitle opacity from 0 to 100 as main title appears.
6. Keyframe both scales subtly upward.
7. Fade both out.

## Video-In-Text Write-On

1. Place video below text.
2. Alpha matte video to text.
3. Precompose result.
4. Apply `Write-on` to precomp.
5. Keyframe brush path across the letters.
6. Add Drop Shadow to precomp.
7. Optional: add Vibrance and Brightness/Contrast to source video inside precomp.
8. Keyframe precomp scale for subtle motion.

## Stabilized Annotation Shot

1. Apply Warp Stabilizer to shaky footage and let analysis finish.
2. Add annotation text near subject.
3. Apply `Warp` to make text playful.
4. Animate text in with `CC Lens`.
5. Add Drop Shadow.
6. Add CC Light Sweep or shine if appropriate.
7. Reverse the CC Lens animation to animate out.

## Green-Screen Composite

1. Apply Keylight to green-screen footage.
2. Sample green.
3. Increase Screen Gain until wrinkles vanish.
4. Duplicate keyed layer if subject becomes transparent.
5. Add background layer below.
6. Add Drop Shadow to subject.
7. Add adjustment layer with shared Lumetri look.
8. Keyframe subtle background/subject scale.

## Masking Transition

1. Pick footage with a foreground object crossing frame.
2. Place next shot below.
3. Draw a mask on top layer where object reveals next shot.
4. Feather mask.
5. Keyframe mask path frame by frame as object crosses.
6. Start next shot at reveal.
7. Trim and optionally scale top layer if the wipe slows.

## Roto Screen Transition

1. Use Roto Brush to isolate screen region.
2. Invert foreground/background so screen is removed.
3. Duplicate original below and fade screen removal in.
4. Place replacement video below.
5. Scale/rotate replacement to fit the screen.
6. Keyframe all layers to zoom through the screen.
7. Cut away once replacement fills frame.

## Glowing Eyes

1. Open close-up eye clip.
2. Roto Brush both eyes.
3. Duplicate original layer below.
4. On roto eye layer, apply CC Light Rays centered on each eye.
5. Apply Glow.
6. Keyframe light/glow intensity up, hold briefly, then down.
7. Keep the effect short; it is render-heavy.

## Logo/Text Motion Track

1. Track high-contrast feature in footage.
2. Apply tracker to a null.
3. Parent logo/text to null.
4. Add Drop Shadow.
5. Trim target layer to reliable tracking section.
6. If scale/rotation is needed, use two track points.

## Full Short Edit

1. Import clips and audio.
2. Build skeleton edit first: trims, speed ramps, rough order.
3. Add titles and motion tracking.
4. Add adjustment-layer color grade.
5. Add transitions/effects only after timing works.
6. Precompose if speeding entire edit or applying global effects.
7. Export H.264 for review.
