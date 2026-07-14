# Context

## Purpose
- Living design note for a fictional inventory API rewrite.
- Audience: eng lead who already knows the product, not the full git history.

## Confirmed Facts
- Current service is a monolithic Express app under `src/legacy/inventory`.
- Target is a separate NestJS service behind the existing gateway path `/v1/inventory`.
- Source of product rules: `docs/inventory-rules.md` (user confirmed 2026-07-01).

## Timeline
- 2026-06-20: Rewrite approved; dual-write period required.
- 2026-07-05: First draft of this note covered current pain points only.
- 2026-07-10: Migration phases section added after review.

## Terms
- Dual-write: new service writes first; legacy remains readable until cutover.
- Soft cutover: gateway routes 10% of read traffic to the new service.

## Source Pointers
- Current implementation: `src/legacy/inventory`
- Baseline design: this note
- Rules doc: `docs/inventory-rules.md`
