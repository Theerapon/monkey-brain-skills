# monkey-brain-skills

Six skills for the monkey-brain dump → kick → play workflow. Works with **Claude Code**, **GitHub Copilot**, **Cursor**, **Windsurf**, and any agent that supports the SKILL.md standard.

## What's included

| Skill | What it does |
|-------|-------------|
| `init-mk-dump` | One-time setup — creates directory structure and templates |
| `add-mk-dump` | Start a new brain dump session |
| `clean-mk-dump` | Distil a raw dump into a structured summary |
| `kick-mk-dump` | Challenge ideas through grilling → produces an action-ready spec |
| `play-mk-dump` | Execute a spec issue by issue, tracking progress across sessions |
| `remove-mk-dump` | Delete a non-kicked dump session |

## Install

> **Pick one option only.** Installing both creates duplicate skills that can drift out of sync.

### Option A — Claude Code plugin

Skills are namespaced as `monkey-brain:skill-name`. Claude Code only.

```
/plugin marketplace add Theerapon/monkey-brain-skills
/plugin install monkey-brain@monkey-brain-skills
```

Then run setup once:

```
/monkey-brain:init-mk-dump
```

### Option B — npx

Works with Claude Code, GitHub Copilot, Cursor, Windsurf, and any agent that supports `.claude/skills/`. Skills appear without namespace prefix (e.g. `/add-mk-dump`).

```bash
# Install all skills at once (recommended)
npx skills@latest add Theerapon/monkey-brain-skills -y

# Or global install (available across all projects)
npx skills@latest add -g Theerapon/monkey-brain-skills -y
```

The `-y` flag skips the per-skill picker and installs all 6 at once. Omit `-y` to select individual skills interactively.

Then run setup once (see [First run](#first-run) below for your tool).

## First run

Run `/init-mk-dump` once to create `docs/monkey-brain/` with templates and empty index files. The skill auto-detects your tool and writes to the correct instructions file.

| Tool | Where to run | Instructions file written |
|------|-------------|--------------------------|
| **Claude Code** | Type `/init-mk-dump` in the prompt (Option A: `/monkey-brain:init-mk-dump`) | `CLAUDE.md` |
| **GitHub Copilot** | Copilot Chat in VS Code → `/init-mk-dump` | `.github/copilot-instructions.md` |
| **Cursor** | Cursor Chat → `/init-mk-dump` | `.cursor/rules/monkey-brain.mdc` |
| **Windsurf** | Cascade panel → `/init-mk-dump` | `AGENTS.md` |
| **Gemini CLI** | Chat prompt → `/init-mk-dump` | `GEMINI.md` |
| **Other** | Chat prompt → `/init-mk-dump` | `AGENTS.md` |

## Workflow

```
/add-mk-dump     → brain dump session
/clean-mk-dump   → structured summary
/kick-mk-dump    → challenge + spec
/play-mk-dump    → execute issue by issue
```

## Updating

**Option A:** `/plugin update monkey-brain@monkey-brain-skills`

**Option B:** `npx skills@latest add Theerapon/monkey-brain-skills -y`

## Companion skills

Recommended skills that pair well with this workflow.

### write-a-skill — Matt Pocock

For building new skills using proper structure and progressive disclosure.

> Source: [mattpocock/skills](https://github.com/mattpocock/skills) · MIT

```bash
npx skills@latest add mattpocock/skills
```

### andrej-karpathy-skills — forrestchang

Behavioral guidelines to reduce common LLM coding mistakes, derived from Andrej Karpathy's observations. Auto-applies on every coding session.

> Source: [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) · MIT · inspired by [Andrej Karpathy](https://karpathy.ai)

```
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin install andrej-karpathy-skills@karpathy-skills
```

## Structure

```
monkey-brain-skills/
├── .claude-plugin/
│   ├── plugin.json         ← Claude Code plugin manifest
│   └── marketplace.json    ← Claude Code marketplace catalog
├── skills/
│   └── monkey-brain/       ← group label shown in npx picker
│       ├── add-mk-dump/
│       ├── clean-mk-dump/
│       ├── init-mk-dump/
│       ├── kick-mk-dump/
│       ├── play-mk-dump/
│       └── remove-mk-dump/
└── README.md
```
