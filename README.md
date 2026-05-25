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

### Option A — Claude Code plugin

Installs as a proper Claude Code plugin. Skills are namespaced as `monkey-brain:skill-name`.

```
/plugin marketplace add Theerapon/monkey-brain-skills
/plugin install monkey-brain@monkey-brain-skills
```

Then run setup once:

```
/monkey-brain:init-mk-dump
```

### Option B — npx (Claude Code + GitHub Copilot + Cursor + Windsurf)

Installs skill folders directly into your workspace. Skills appear without namespace prefix (e.g. `/add-mk-dump`). Works in any agent that supports `.claude/skills/`.

```bash
npx skills add Theerapon/monkey-brain-skills
```

Then run setup once (see [First run](#first-run) below for your tool).

## First run

After installing, run `/init-mk-dump` once to create `docs/monkey-brain/` with templates and empty index files.

| Tool | Where to run |
|------|-------------|
| **Claude Code** | Type `/init-mk-dump` in the prompt (Option A: `/monkey-brain:init-mk-dump`) |
| **GitHub Copilot** | Open Copilot Chat in VS Code → type `/init-mk-dump` |
| **Cursor** | Open Cursor Chat → type `/init-mk-dump` |
| **Windsurf** | Open Cascade panel → type `/init-mk-dump` |
| **Gemini CLI** | Type `/init-mk-dump` in the chat prompt |
| **Other** | Any agent with `.claude/skills/` support → type `/init-mk-dump` |

## Workflow

```
/add-mk-dump     → brain dump session
/clean-mk-dump   → structured summary
/kick-mk-dump    → challenge + spec
/play-mk-dump    → execute issue by issue
```

## Companion skills

Recommended skills that pair well with this workflow.

### write-a-skill — Matt Pocock

For building new skills using proper structure and progressive disclosure.

> Source: [mattpocock/skills](https://github.com/mattpocock/skills) · MIT

```bash
npx skills add mattpocock/skills
```

### andrej-karpathy-skills — forrestchang

Behavioral guidelines to reduce common LLM coding mistakes, derived from Andrej Karpathy's observations. Auto-applies on every coding session.

> Source: [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) · MIT · inspired by [Andrej Karpathy](https://karpathy.ai)

```
/plugin marketplace add forrestchang/andrej-karpathy-skills
/plugin install andrej-karpathy-skills@karpathy-skills
```

## Updating

**Option A:** `/plugin update monkey-brain@monkey-brain-skills`

**Option B:** `npx skills update Theerapon/monkey-brain-skills`

## Structure

```
monkey-brain-skills/
├── .claude-plugin/
│   └── plugin.json       ← Claude Code plugin manifest
├── skills/
│   └── monkey-brain/
│       ├── add-mk-dump/
│       ├── clean-mk-dump/
│       ├── init-mk-dump/
│       ├── kick-mk-dump/
│       ├── play-mk-dump/
│       └── remove-mk-dump/
└── README.md
```
