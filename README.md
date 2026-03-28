# promptneurons-marketplace

Marketplace for Claude Code plugins and Gemini/Antigravity skills by [Prompt Neurons, LLC](https://promptneurons.com).

## What Is This?

This repo is a **catalog** — it lists available plugins and where to find them. The actual skills and code live in the individual plugin repos.

## Available Plugins

| Plugin | Description | Access |
|--------|-------------|--------|
| [promptneurons](https://github.com/promptneurons/promptneurons) | Core skills library (install.md generator, etc.) | P100 (Public) |
| nqa1-governance | NQA-1 governance workflows as Petri Nets over OWL ontologies | H100/H200 (Private) |

## For Claude Code Users

```bash
claude plugin marketplace add https://github.com/promptneurons/promptneurons-marketplace
claude plugin marketplace list
claude plugin install promptneurons
```

## For Gemini / Antigravity IDE Users

Each plugin repo ships with Gemini-ready skills in `.gemini/skills/`. To install:

```bash
# Clone the plugin repo:
git clone https://github.com/promptneurons/promptneurons.git

# Copy skills to your workspace:
mkdir -p .gemini/skills
cp -r promptneurons/.gemini/skills/* .gemini/skills/

# Windows (PowerShell):
New-Item -ItemType Directory -Force -Path .gemini\skills
Copy-Item -Recurse -Force promptneurons\.gemini\skills\* .gemini\skills\
```

Or use the CLI tool:

```bash
npx pn-antigravity-plugin install promptneurons
```

See individual plugin READMEs for detailed setup instructions.

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
