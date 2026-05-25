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

```bash
npx skills@latest add Theerapon/monkey-brain-skills
```

## First run

Run `/init-mk-dump` once to create `docs/monkey-brain/` with templates and empty index files. The skill auto-detects your tool and writes to the correct instructions file.

| Tool | Where to run | Instructions file written |
|------|-------------|--------------------------|
| **Claude Code** | Type `/init-mk-dump` in the prompt | `CLAUDE.md` |
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

## Update

```bash
npx skills@latest add Theerapon/monkey-brain-skills
```

## Companion skills

### write-a-skill — Matt Pocock

For building new skills using proper structure and progressive disclosure.

> Source: [mattpocock/skills](https://github.com/mattpocock/skills) · MIT

```bash
npx skills@latest add mattpocock/skills
```

### andrej-karpathy-skills — forrestchang

Behavioral guidelines to reduce common LLM coding mistakes, derived from Andrej Karpathy's observations. Auto-applies on every coding session.

> Source: [forrestchang/andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) · MIT · inspired by [Andrej Karpathy](https://karpathy.ai)

```bash
npx skills@latest add forrestchang/andrej-karpathy-skills
```
