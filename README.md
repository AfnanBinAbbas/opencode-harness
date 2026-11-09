# opencode-harness

Example wiring for the opencode harness that runs the red-* agent stack:
providers, local models, MCP, and where agents/commands/skills live.

> **The real `opencode.json` is never committed** — it contains a live API key.
> Use the scrubbed example; fill your own key locally.

## Layout

```
example/opencode.json.example   scrubbed config (apiKey + local paths redacted)
expected ~/.config/opencode/
  opencode.json           <- copy example, add YOUR key (never commit)
  agent/red-*.md          <- from red-agents
  command/redteam.md      <- from red-agents
  redteam/*.md            <- from red-ops-doctrine
  skills/red-ops/SKILL.md <- from red-ops-doctrine
```

## Install

```bash
mkdir -p ~/.config/opencode
cp example/opencode.json.example ~/.config/opencode/opencode.json
# edit: set provider apiKey, model, MCP paths for your machine
# then overlay red-agents + red-ops-doctrine (see their READMEs)
```

## What the example shows

- provider setup (remote compatible API + local Ollama models)
- MCP server registration (OSINT)
- model/context limits
- where phase agents plug in

Keep `.gitignore` covering `opencode.json`, `*.env`, tokens.
Authorized lab use only.
