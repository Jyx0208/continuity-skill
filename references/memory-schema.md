# Continuity Memory Schema

Keep the files short. Use dated entries only when chronology matters.

## `context.md`

```markdown
# Context

## Purpose
- What the project or artifact is for.

## Confirmed Facts
- Fact. Source: `path`, commit, log, or user confirmation.

## Timeline
- YYYY-MM-DD: Event or decision.

## Terms
- Term: meaning used in this project.

## Source Pointers
- Current implementation: `path`
- Baseline: commit or artifact
```

Put implementation facts here only after verification. Point to existing ADRs or `CONTEXT.md` instead of duplicating them.

## `voice.md`

```markdown
# Voice

## Confirmed
- Preference accepted or repeatedly demonstrated.
- Example the user approved: short excerpt or artifact pointer.

## Working
- Tentative interpretation to test in the next revision.

## Corrections
- Feedback: what felt wrong.
  Preferred target: the positive writing behavior to use instead.
```

Promote a working preference to confirmed after explicit acceptance or repeated evidence. Remove stale corrections once the positive rule captures them.

## `state.md`

```markdown
# State

## Active Artifact
- Path:
- Purpose:
- Audience:

## Current Position
- Last completed section or decision:
- Current narrative or work phase:

## Open Threads
- Topic that still needs explanation or implementation.

## Next Natural Continuation
- The next section, question, or action implied by the artifact.

## Latest Revision
- What changed and why.
```

Update this file after meaningful progress. It is a resume point, not a backlog or a summary of the whole project.

## `feedback.md`

```markdown
# Feedback

## YYYY-MM-DD — Short topic
- Attempt: concise description of the output direction.
- User feedback: the important response, paraphrased.
- Learned intent: positive behavior to carry forward.
- Scope: this passage, this artifact, or general collaboration.
- Confidence: confirmed or working.
```

Record an episode only when it changes future behavior. Preserve the reason behind the feedback, not a transcript. Merge repeated episodes after their shared lesson is stable, while keeping unusual exceptions visible.
