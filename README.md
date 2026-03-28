# promptneurons-marketplace

Marketplace for Claude Code plugins and Gemini/Antigravity skills by [Prompt Neurons, LLC](https://promptneurons.com).

## What Is This?

This repo is a **catalog** — it lists available plugins and where to find them. The actual skills and code live in the individual plugin repos.

## Available Plugins

| Plugin | Skills | Access |
|--------|--------|--------|
| [promptneurons](https://github.com/promptneurons/promptneurons) | `install-md-generator`, `agent-scaffolding` | P100 (Public) |
| nqa1-governance | NQA-1 governance workflows | H100/H200 (Private) |

## For Gemini / Antigravity IDE Users

### Install All Public Skills (2 commands)

```bash
git clone https://github.com/promptneurons/promptneurons.git
cp -r promptneurons/.gemini/skills/* .gemini/skills/
```

Windows (PowerShell):
```powershell
git clone https://github.com/promptneurons/promptneurons.git
Copy-Item -Recurse -Force promptneurons\.gemini\skills\* .gemini\skills\
```

### Scaffold a Multi-Agent Workspace

After installing, ask the Antigravity agent:

> "Set up this project as a multi-agent workspace"

The **agent-scaffolding** skill will create `AGENTS.md`, `.agents/`, `.claude/`, and `.gemini/` directories — a complete multi-agent workspace compatible with both Claude Code and Gemini/Antigravity.

See the [promptneurons plugin README](https://github.com/promptneurons/promptneurons) for more details.

## For Claude Code Users

```bash
claude plugin marketplace add https://github.com/promptneurons/promptneurons-marketplace
claude plugin marketplace list
claude plugin install promptneurons
```

## Access Tiers

| Tier | Name | Access |
|------|------|--------|
| **P100** | Public Open Source | Free — this marketplace + public plugins |
| **H100** | Strategic Partner | Paid GitHub org member — private plugins |
| **H200** | Franchisee | Paid GitHub org member — Antigravity IDE required |

## Marketplace Schema

The catalog lives in `.claude-plugin/marketplace.json`. Each plugin entry has:

```json
{
  "name": "plugin-name",
  "source": { "source": "url", "url": "https://github.com/promptneurons/<repo>.git" },
  "description": "What the plugin does",
  "version": "0.0.1",
  "strict": true
}
```

## License

MIT — Prompt Neurons, LLC
