# MCP Bridge Reference

Use this file when operating the `after-effects-mcp` server or troubleshooting the connection to After Effects.

## Architecture

The server is a file-bridge integration, not a direct live AE API:

1. The MCP client sends a tool call to the Node server.
2. The server writes a JSON command into the bridge directory, typically under the user's Documents folder.
3. The `mcp-bridge-auto.jsx` panel inside After Effects polls for commands.
4. After Effects executes ExtendScript and writes a JSON result.
5. The MCP server reads the result back.

Consequences:

- After Effects must be open.
- The bridge panel must be open from `Window > mcp-bridge-auto.jsx`.
- Auto-run/listening must be enabled in the panel.
- Results can be stale if the panel did not process the latest command.
- Some operations are limited to allowlisted scripts or exposed MCP tools.

Repository: https://github.com/Dakkshin/after-effects-mcp

## Setup Checklist

1. Install dependencies in the MCP repo:

```powershell
npm install
npm run build
npm run install-bridge
```

2. If bridge install fails, manually copy `build/scripts/mcp-bridge-auto.jsx` into the After Effects `Scripts/ScriptUI Panels` folder.
3. In After Effects, enable scripting permissions:
   - `Edit > Preferences > Scripting & Expressions`
   - Enable script file/network access.
4. Restart/open After Effects.
5. Open `Window > mcp-bridge-auto.jsx`.
6. Confirm the panel is checking for commands.

## Tool Surface In This Codex Session

Prefer these callable MCP tools when available:

- `mcp__AfterEffectsMCP__.get_help()`
- `mcp__AfterEffectsMCP__.get_results()`
- `mcp__AfterEffectsMCP__.run_script({ script, parameters? })`
- `mcp__AfterEffectsMCP__.create_composition({ name, width, height, frameRate?, duration?, pixelAspect?, backgroundColor? })`
- `mcp__AfterEffectsMCP__.setLayerKeyframe({ compIndex, layerIndex, propertyName, timeInSeconds, value? })`
- `mcp__AfterEffectsMCP__.setLayerExpression({ compIndex, layerIndex, propertyName, expressionString })`
- `mcp__AfterEffectsMCP__.apply_effect({ compIndex, layerIndex, effectName?, effectMatchName?, effectCategory?, effectSettings?, presetPath? })`
- `mcp__AfterEffectsMCP__.apply_effect_template({ compIndex, layerIndex, templateName, customSettings? })`

The current template names are:

- `gaussian-blur`
- `directional-blur`
- `color-balance`
- `brightness-contrast`
- `curves`
- `glow`
- `drop-shadow`
- `cinematic-look`
- `text-pop`

## Discovery Scripts

Use `run_script` for project inspection and supported operations. Common script names from the bridge help/repo include:

- `getProjectInfo`
- `listCompositions`
- `getLayerInfo`
- `createComposition`
- `createTextLayer`
- `createShapeLayer`
- `createSolidLayer`
- `setLayerProperties`
- `setLayerKeyframe`
- `setLayerExpression`
- `applyEffect`
- `applyEffectTemplate`
- `deleteLayer`
- `setLayerMask`
- `bridgeTestEffects`

Example:

```json
{
  "script": "listCompositions"
}
```

## Common Calls

Create a composition:

```json
{
  "name": "Title_Intro_1080p",
  "width": 1920,
  "height": 1080,
  "frameRate": 30,
  "duration": 8,
  "backgroundColor": { "r": 0, "g": 0, "b": 0 }
}
```

Set layer keyframes:

```json
{
  "compIndex": 1,
  "layerIndex": 1,
  "propertyName": "Opacity",
  "timeInSeconds": 0,
  "value": "0"
}
```

```json
{
  "compIndex": 1,
  "layerIndex": 1,
  "propertyName": "Opacity",
  "timeInSeconds": 0.75,
  "value": "100"
}
```

Apply a reliable effect by match name:

```json
{
  "compIndex": 1,
  "layerIndex": 1,
  "effectMatchName": "ADBE Gaussian Blur 2",
  "effectSettings": { "Blurriness": 25 }
}
```

Apply a template:

```json
{
  "compIndex": 1,
  "layerIndex": 1,
  "templateName": "text-pop"
}
```

Set an expression:

```json
{
  "compIndex": 1,
  "layerIndex": 1,
  "propertyName": "Position",
  "expressionString": "wiggle(2, 20)"
}
```

## Effect Match Names

Prefer `effectMatchName` over display names when possible:

- Gaussian Blur: `ADBE Gaussian Blur 2`
- Camera Lens Blur: `ADBE Camera Lens Blur`
- Directional Blur: `ADBE Directional Blur`
- Radial Blur: `ADBE Radial Blur`
- Unsharp Mask: `ADBE Unsharp Mask`
- Brightness & Contrast: `ADBE Brightness & Contrast 2`
- Hue/Saturation: `ADBE HUE SATURATION`
- Levels: `ADBE Pro Levels2`
- Curves: `ADBE CurvesCustom`
- Exposure: `ADBE Exposure2`
- Vibrance: `ADBE Vibrance`
- Glow: `ADBE Glow`
- Drop Shadow: `ADBE Drop Shadow`
- Bevel Alpha: `ADBE Bevel Alpha`
- Noise: `ADBE Noise`
- Fractal Noise: `ADBE Fractal Noise`
- CC Light Sweep: `CC Light Sweep`
- CC Particle World: `CC Particle World`

## Troubleshooting

If a command seems ignored:

1. Confirm After Effects is open.
2. Confirm `Window > mcp-bridge-auto.jsx` is open.
3. Confirm the bridge panel is auto-running commands.
4. Call `get_results`; if stale, the panel probably did not process the latest JSON.
5. Check scripting permissions in After Effects.
6. Check that the MCP server and AE panel use the same bridge directory.
7. Try `run_script({ "script": "getProjectInfo" })` or `bridgeTestEffects`.
8. Restart the MCP server and reopen the AE panel if file polling appears stuck.

If an operation is not exposed:

- Use available MCP tools for the mechanical parts.
- Give the user precise AE UI steps for manual-only operations such as Roto Brush refinement, Warp Stabilizer analysis, Easy Ease, or Media Encoder export.
- Use `run_script` only with allowlisted script names.
