# Continuity

**Preserve evolving project context, user voice, and document position across revisions and sessions.**

Continuity is a skill for Claude Code and Codex. Use it when editing a living note, report, design document, handoff, or any artifact that must build on prior feedback without freezing tentative conclusions or restarting from scratch.

## What it does

Long-running documents drift when each session re-derives intent from chat history. Continuity keeps a small, versioned memory next to the work:

| File | Role |
|------|------|
| `context.md` | Verified facts, timeline, terms, source pointers |
| `voice.md` | Accepted writing traits and corrections (with confidence) |
| `feedback.md` | Compact output→feedback→learned-intent episodes |
| `state.md` | Active artifact, current position, open threads, next step |

The live artifact stays primary. Memory holds only compact facts and pointers so a future session can resume without reconstructing the conversation.

## Install

### Claude Code (user skill)

```bash
# Clone
git clone https://github.com/Jyx0208/continuity-skill.git

# Install into Claude Code user skills
mkdir -p ~/.claude/skills/continuity
cp -r continuity-skill/SKILL.md \
      continuity-skill/references \
      continuity-skill/agents \
      ~/.claude/skills/continuity/
```

On Windows (Git Bash):

```bash
mkdir -p ~/.claude/skills/continuity
cp -r continuity-skill/SKILL.md continuity-skill/references continuity-skill/agents ~/.claude/skills/continuity/
```

Or copy this repository's skill tree directly:

```text
~/.claude/skills/continuity/
  SKILL.md
  agents/openai.yaml
  references/memory-schema.md
```

Restart or start a new Claude Code session, then invoke:

```text
/continuity
```

or ask Claude to use the continuity skill while revising a document.

### Codex

```bash
mkdir -p ~/.codex/skills/continuity
cp -r continuity-skill/SKILL.md continuity-skill/references continuity-skill/agents ~/.codex/skills/continuity/
```

## Quick start

1. Open the document you want to continue.
2. Invoke Continuity (`/continuity` or “use continuity on this report”).
3. On first use, the skill creates `.continuity/` at the project root (or beside the artifact).
4. After each meaningful revision, it updates only what changed in the four memory files.
5. Next session: read the artifact + `.continuity/`, then continue from `state.md`.

## Memory location

Prefer:

```text
<project-root>/.continuity/
  context.md
  voice.md
  feedback.md
  state.md
```

If there is no project root, place `.continuity/` beside the target artifact.

Never store secrets, credentials, or private tokens in continuity memory.

## Workflow (summary)

1. **Re-enter** — Read the live artifact fully, then continuity files and the smallest set of sources needed to verify the request.
2. **Reconcile** — Label information `confirmed` / `working` / `stale`; apply newest feedback without over-generalizing one-off notes.
3. **Locate continuation** — Match the artifact’s mode (ongoing note vs concluding report vs prospective plan).
4. **Revise** — Preserve working wording; keep facts, decisions, interpretations, and plans distinct.
5. **Update memory** — Patch only what changed; do not dump the whole document into memory.

Full instructions live in [`SKILL.md`](./SKILL.md). Schema details: [`references/memory-schema.md`](./references/memory-schema.md).

## Example memory

See [`examples/.continuity/`](./examples/.continuity/) for a minimal filled-in set (fictional project).

## Repository layout

```text
continuity-skill/
  SKILL.md                 # Skill entrypoint (Claude Code / Codex)
  agents/openai.yaml       # Codex skill UI metadata
  references/
    memory-schema.md       # Schemas for the four memory files
  examples/
    .continuity/           # Sample memory for a fictional report
  README.md
  LICENSE
  .gitignore
```

## Design principles

- **Live artifact is source of truth** — memory points; it does not replace the document.
- **Understanding is versioned** — confirmed facts stay; working interpretations stay revisable.
- **Feedback becomes positive rules** — record why something worked or failed, not chat transcripts.
- **Small and safe** — short files, no secrets, no long-form duplication.

## License

MIT — see [LICENSE](./LICENSE).
