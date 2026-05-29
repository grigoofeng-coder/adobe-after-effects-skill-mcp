# Adobe After Effects Skill + MCP

This archive contains:

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

