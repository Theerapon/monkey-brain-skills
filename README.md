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

### Option A — Claude Code plugin (recommended)

Installs as a proper Claude Code plugin. Skills are namespaced as `monkey-brain:skill-name`.

```
/plugin install github:Theerapon/monkey-brain-skills
```

Then run setup once:

```
/monkey-brain:init-mk-dump
```

### Option B — Manual copy (Claude Code + GitHub Copilot)

Use this when you want the skills to appear without a namespace prefix (e.g. `/add-mk-dump` instead of `/monkey-brain:add-mk-dump`), or to install in Copilot which doesn't use the plugin system.

```bash
# Clone repo
git clone https://github.com/Theerapon/monkey-brain-skills.git /tmp/monkey-brain-skills

# Copy skill folders into your workspace
cp -r /tmp/monkey-brain-skills/skills/add-mk-dump      {workspace-root}/.claude/skills/
cp -r /tmp/monkey-brain-skills/skills/clean-mk-dump     {workspace-root}/.claude/skills/
cp -r /tmp/monkey-brain-skills/skills/init-mk-dump      {workspace-root}/.claude/skills/
cp -r /tmp/monkey-brain-skills/skills/kick-mk-dump      {workspace-root}/.claude/skills/
cp -r /tmp/monkey-brain-skills/skills/play-mk-dump      {workspace-root}/.claude/skills/
cp -r /tmp/monkey-brain-skills/skills/remove-mk-dump    {workspace-root}/.claude/skills/
```

Replace `{workspace-root}` with the path you open in Claude Code or VS Code (e.g. `~/projects`).

Then run setup once inside Claude Code or Copilot Chat:

```
/init-mk-dump
```

## First run

After installing, open your workspace in Claude Code or VS Code and run `/init-mk-dump` (or `/monkey-brain:init-mk-dump` for plugin install).

This creates `docs/monkey-brain/` with the required templates and empty index files.

## Workflow

```
/add-mk-dump     → brain dump session
/clean-mk-dump   → structured summary
/kick-mk-dump    → challenge + spec
/play-mk-dump    → execute issue by issue
```

## Updating

**Option A:** `/plugin update monkey-brain`

**Option B:** Pull and re-copy the `skills/` folders.

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
