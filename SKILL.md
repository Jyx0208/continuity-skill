---
name: continuity
description: Preserve evolving project context, user voice, and document position across revisions and sessions. Use when editing a living note, report, design document, handoff, or other artifact that must build on prior feedback without freezing tentative conclusions or restarting from scratch.
version: 1.0.0
tags: [continuity, writing, documentation, memory, handoff, revision]
---

# Continuity

Carry the work forward from its current position. Treat understanding as versioned: preserve confirmed facts and preferences, keep working interpretations revisable, and let the live artifact remain the primary source.

## Memory Location

Use a `.continuity/` directory at the project root, or beside the target artifact when no project root exists. Read [references/memory-schema.md](references/memory-schema.md) before creating or repairing these files:

- `context.md`: verified facts, timeline, terminology, and source pointers.
- `voice.md`: accepted writing characteristics and user corrections, with confidence labels.
- `feedback.md`: compact output-feedback episodes that explain how the current understanding was learned.
- `state.md`: active artifact, current writing position, open threads, and the next natural continuation.

If the project already has `CONTEXT.md`, ADRs, or a handoff file, read them and point to them from `context.md`; keep each fact in one authoritative place. Never store secrets, credentials, or private tokens in continuity memory.

## Workflow

### 1. Re-enter the work

Read the target artifact in full before editing. Then read the continuity files, including the feedback trail, and the smallest set of current source files needed to verify the request. Prefer live files over conversational summaries when they disagree.

Completion: identify the artifact's purpose, audience, current position, accepted voice, and factual source of truth.

### 2. Reconcile understanding

Separate information into:

- `confirmed`: explicitly accepted by the user or verified from a source.
- `working`: useful current interpretation that may change.
- `stale`: superseded by newer feedback or source state.

Apply the newest user feedback to the current task. Update a general preference only when the feedback plausibly applies beyond one sentence or section. Preserve uncertainty instead of converting it into a firm rule.

Completion: every relevant conflict has a chosen current interpretation and an evidence basis.

### 3. Locate the continuation

Determine what the user is changing now and where it belongs in the artifact's existing progression. Match the artifact's mode: an ongoing note should keep moving; a report may conclude; a plan should remain prospective. Continue the established level of detail unless the user asks to reshape it.

Completion: state internally what remains intact, what changes, and what the revised passage should lead into next.

### 4. Make the revision

Preserve the user's wording where it already works. Add structure only when it improves reading. Write in the accepted voice and maintain chronological or argumentative continuity. Distinguish observed facts, the user's decisions, interpretations, planned work, and completed work.

For code-backed documents, verify implementation claims against the relevant version or commit before writing them. Keep technical detail proportional to the surrounding text.

Completion: the requested section reads as part of the same document, factual additions are traceable, and the ending leaves the document in the correct ongoing or completed state.

### 5. Update continuity memory

After a meaningful revision, update only what changed:

- Add verified project facts or source pointers to `context.md`.
- Add accepted style feedback to `voice.md`; mark unconfirmed inferences as `working`.
- Add a `feedback.md` entry when the user's response reveals why an output worked or failed. Record the attempted direction, feedback, learned intent, and confidence rather than copying the conversation.
- Record the artifact's new position and next open thread in `state.md`.
- Remove or mark stale entries when they are superseded.

Do not copy the whole artifact into memory. Record compact facts and pointers that let a future session resume accurately.

Completion: another session can read the artifact plus `.continuity/` and continue without reconstructing the conversation.

## Revision Check

Before finishing, confirm:

- The live artifact, memory, and verified sources agree.
- The revision answers the newest request rather than an earlier draft direction.
- Confirmed preferences shaped the prose without turning one-off feedback into permanent doctrine.
- Relevant feedback episodes have been translated into positive, reusable understanding.
- The artifact stops or continues where its real purpose requires.
- Continuity memory contains no secrets and no duplicated long-form content.
