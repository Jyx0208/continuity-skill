# State

## Active Artifact
- Path: `docs/inventory-rewrite-note.md`
- Purpose: capture rewrite rationale, phases, and open questions for the next design review.
- Audience: eng lead and on-call owners of the inventory path.

## Current Position
- Last completed section: Migration phases (dual-write → soft cutover → hard cutover).
- Current narrative phase: risks and open questions before implementation kickoff.

## Open Threads
- How long dual-write must run before soft cutover metrics are trusted.
- Whether stock adjustment events stay on the legacy bus during dual-write.

## Next Natural Continuation
- Draft the “Open questions for design review” section, then stop before implementation tickets.

## Latest Revision
- 2026-07-12: Reordered migration as a sequence with entry criteria; demoted unknowns from blockers to review questions.
