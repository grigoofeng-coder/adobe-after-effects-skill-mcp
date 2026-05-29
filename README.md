# Adobe After Effects Skill + MCP

1. Скачай zip ниже.

2. Закинь zip своему ИИ-агенту.

3. Попроси его распаковать архив, установить skill + MCP, поставить зависимости MCP.

4. Открой After Effects.

5. Нажми Edit > Preferences > Scripting & Expressions.

6. Включи галочку Allow Scripts to Write Files and Access Network.

7. Нажми Window > mcp-bridge-auto.jsx.

8. Включи bridge/auto-run.

## Download

[adobe-after-effects-skill-mcp.zip](./adobe-after-effects-skill-mcp.zip)

## Archive Contents

- `adobe-after-effects-mcp-skill/` - Codex skill directory. Copy it to `%USERPROFILE%\.codex\skills\adobe-after-effects-mcp`.
- `after-effects-mcp/` - MCP server repository from `https://github.com/Dakkshin/after-effects-mcp`.

## Install MCP Server

1. Open PowerShell in `after-effects-mcp`.
2. Run:

```powershell
npm install
npm run build
npm run install-bridge
```

3. If bridge install fails, copy `after-effects-mcp\build\scripts\mcp-bridge-auto.jsx` into the After Effects `Scripts\ScriptUI Panels` folder manually.
4. In After Effects, enable scripting permissions:

```text
Edit > Preferences > Scripting & Expressions > Allow Scripts to Write Files and Access Network
```

5. Restart After Effects and open:

```text
Window > mcp-bridge-auto.jsx
```

## Codex MCP Config

Add or update this block in `%USERPROFILE%\.codex\config.toml`, replacing the path if you unpacked the archive elsewhere:

```toml
[mcp_servers.AfterEffectsMCP]
command = "node"
args = ['C:\path\to\after-effects-mcp\build\index.js']
```
