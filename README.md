# monkey-brain-skills

Six skills for the monkey-brain dump → kick → play workflow. Works with **Claude Code** (PC/Mac) and **GitHub Copilot** (VS Code Agent mode).

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
/plugin install Theerapon/monkey-brain-skills
```

Then run setup once:

```
/monkey-brain:init-mk-dump
```

### Option B — npx (Claude Code + GitHub Copilot)

Installs skill folders directly into your workspace. Skills appear without namespace prefix (e.g. `/add-mk-dump`). Also works in GitHub Copilot.

```bash
npx skills add Theerapon/monkey-brain-skills
```

Then run setup once:

```
/init-mk-dump
```

## Workflow

```
/add-mk-dump     → brain dump session
/clean-mk-dump   → structured summary
/kick-mk-dump    → challenge + spec
/play-mk-dump    → execute issue by issue
```

## Updating

**Option A:** `/plugin update monkey-brain`

**Option B:** `npx skills update Theerapon/monkey-brain-skills`

## Structure

```
monkey-brain-skills/
├── .claude-plugin/
│   └── plugin.json       ← Claude Code plugin manifest
├── skills/
│   ├── add-mk-dump/
│   ├── clean-mk-dump/
│   ├── init-mk-dump/
│   ├── kick-mk-dump/
│   ├── play-mk-dump/
│   └── remove-mk-dump/
└── README.md
```
