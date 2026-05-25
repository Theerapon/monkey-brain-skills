# Spec Doc Format

Written to `docs/monkey-brain/specs/{yyyy}/{mm}/{yyyy-mm-dd}-{dump|idea}-{NNN}-{topic}-kick.md`:

```markdown
status: remaining

# Spec: {topic}
_Kicked: {yyyy-mm-dd} · source: {full_dump_filename}.md_

(For new ideas with no dump source, use: `source: new idea — {brief description}`)

## Summary
[1–2 lines: what this is about]

## Decisions Made
- **[original BRANCH/UNCLEAR item]:** [answer + brief reasoning]
- ...

## Research Findings
[Round 1–3 summaries: approach name, brief description, pros, cons]

| Approach | Pros | Cons |
|----------|------|------|
| ...      | ...  | ...  |

**Recommended direction:** [based on grilling + research combined]

## Issues

### Issue 1: [title]
_Independent_
Done when: [1–2 sentence success criteria — specific enough to verify]
- [ ] [sub-step 1]
- [ ] [sub-step 2]

---

### Issue 2: [title]
_Depends on: Issue 1_
Done when: [criteria]
- [ ] [sub-step 1]
- [ ] [sub-step 2]

---
```

---

## Filename Convention

`docs/monkey-brain/specs/{yyyy}/{mm}/{yyyy-mm-dd}-{type}-{NNN}-{topic}-kick.md`

- `{type}`: `dump` if sourced from a cleaned dump session; `idea` if sourced from a new idea
- `{NNN}`: zero-padded 3-digit number
  - Dump source: extract from session filename (e.g. `2026-05-23-001-…` → `001`)
  - Idea source: count `{yyyy-mm-dd}-idea-*` files in `specs/{yyyy}/{mm}/` for today + 1
- `{topic}`: 2–4 words, kebab-case, derived from the idea's topic
- Examples: `2026-05-23-dump-001-dump-system-design-kick.md`, `2026-05-24-idea-001-play-skill-validation-kick.md`
