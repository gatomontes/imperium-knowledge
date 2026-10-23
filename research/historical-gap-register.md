# Campaign 007 — Historical gap register and extraction disposition

**Classification:** Research inventory and current project decision guidance, 2026-10-23. Historical claims are backed by source links; priorities below are proposed, not historical enacted doctrine.

## What has already been preserved

Campaigns 001–006 capture constitutional distinctions, agent artifact lifecycle, Office inventory, bootstrap/recovery proposals, historical reset decisions, bounded execution concerns, and the Symfony interview/proposal/authorization path. See [the index](../KNOWLEDGE-INDEX.md). They do **not** constitute exhaustive audit of old branches, code, or review comments.

## Remaining historical gaps

| Source | Unrecovered material | Status / next evidence |
| --- | --- | --- |
| [Agentica PR and branch history](https://github.com/gatomontes/imperium-agentica-v02/pulls?q=is%3Apr) | Seat occupancy, Office reorganization, supersession chains, rejected variants and reviewer deliberations | Open research; examine exact commits/diffs before claiming decision lineage |
| [Agentica Office contracts](https://github.com/gatomontes/imperium-agentica-v02/tree/main/offices) | Detailed qualifications and lifecycle failure branches beyond the summarized five-Office path | Theoretical documents; preserve only distinctions not already catalogued |
| [Symfony PR #5](https://github.com/gatomontes/imperium-symfony/pull/5) | Current head code, review-thread dispositions, migration reversibility and end-to-end operational validation | Historical branch, not assumed integrated; independent revalidation required |
| [Symfony interview implementation](https://github.com/gatomontes/imperium-symfony) | Full code-level match between CLI docs, Doctrine entities, lock behavior and tests | Documented behavior extracted; code-and-test audit incomplete |

## Additional adversarial cases found in historical Symfony PR #5 reviews

The discussion surfaced specific **review observations** (not necessarily present at latest head): writing to web-served `public/` without separate publication authority; incomplete files visible before atomic publication; deleting mission records while leaving orphaned output; races between path validation and filesystem changes; symlinked staging paths; ambiguous filesystem read/stat failures; and migration rollbacks that discard or cannot reconcile versioned authorization evidence. See [review discussions](https://github.com/gatomontes/imperium-symfony/pull/5).

**Disposition:** retain these as negative-test candidates **only when corresponding external effects, file publication, or authorization versioning exist**. They are not dependencies of a simple two-agent conversation.

## Consolidation decision proposed for MWS

A practical threshold is now met for *starting* the MWS; finishing the entire historical audit first would repeat the old pattern of building governance before useful behavior. Keep this knowledge repository as a living record, and resume targeted archival extraction when a real implementation decision demands it.

First increment in the **separate runtime repository**: browser form → Coordinator message → Worker reply → Coordinator result, persisted and attributable, with explicit failures and mocked integration tests. No external file-writing executor, institutional spawning, or elevated authority is needed.

## Acceptance of this extraction

This campaign delivers a navigable list of open research, distinctions between document evidence / review findings / recommended decisions, and a stop rule. It does **not** certify that historical review findings are still present or remedied, nor that the new MWS works.
