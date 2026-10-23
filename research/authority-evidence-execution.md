# Campaign 005 — Authority, evidence and execution boundaries

**Status:** historical doctrine extraction from `imperium-agentica-v02/main`, 2026-10-23. This document is **not** a claim that the contracts were implemented, tested, or deployed.

## Authority is not capability

The [constitutional root](https://github.com/gatomontes/imperium-agentica-v02/blob/main/imperium-doctrine.md) states that possession of a model, Profile, tool, credential, information or capacity does not confer permission. Authority must be explicit about **source, holder, object, scope, duration and revocation**. It does not transfer through a handoff or technical implementation merely because the recipient can act.

The [Imperator contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/imperator.md) is an instructive counterexample to assumed superuser power: authenticated SuperAdmin identity allows only separately Charter-declared exceptional administration. It cannot sign ordinary Profiles or bypass the Charter by default.

## Evidence is not disposition

The constitution distinguishes an observed fact, an artifact, a finding and the competent actor's decision. Missing or contradictory evidence must not silently turn into *approval*, *success* or *failure*. A producer cannot approve merely by producing. A custodian cannot authorize by holding. A successful execution cannot establish that the attempt was authorized.

For consequential actions, a minimal record should answer:
- **Who or what** acted (exact running instance, rather than only its persona/model);
- **what** was requested and which version/configuration it concerned;
- **which authorization** permitted that exact action, at that point in time;
- **what was observed** and what independently proves the action and result;
- **what remains uncertain**, including an interrupted or inconclusive attempt.

This is a conceptual evidence checklist, **not** a mandate to implement the historical cryptographic-identity system in MWS.

## Deterministic boundaries

The constitutional design keeps agent-generated reasoning and proposal distinct from mechanical permission checks. Where an operation changes external state, its enforcement must not rest on an agent's assertion that it is allowed.

The [concurrency/replay contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/runtime-concurrency-replay.md) specifies historically proposed atomic reservations, single-use commissions, idempotency keys, state-generation checks immediately before mutation and append-only receipts. It explicitly distinguishes duplicate observation from duplicate execution. These are **theoretical primitives**, not proof they ran in production.

### Failure modes to keep

| Risk | Countermeasure when actually needed |
| --- | --- |
| Permission implied by model prose | Controlled positive authorization and deterministic enforcement |
| Approved action exceeds limits | Match actual parameters against scope at execution time |
| Same request executed twice on retry | Stable idempotency and exact request binding |
| Stale approval after policy/profile change | Revalidate version and authority before consequential mutation |
| Output exists but did not originate with this attempt | Preserve attempt-specific causation evidence |
| Effect partly completed or status unreadable | Record uncertainty; reconcile without manufacturing a success or failure |
| Requested path differs from actual destination | Validate the real effect target and confinement |

The historical [Symfony PR #5 review discussions](https://github.com/gatomontes/imperium-symfony/pull/5) independently illustrate several of these as observed code-review risks, without establishing that they persist at its latest head.

## Practical MWS adoption sequence

1. **Now:** two Symfony agents, browser-visible conversation, message provenance (agent, time, request ID), error states and human-triggered runs.
2. **When introducing an effect:** structured action request with explicit operator authorization; validate permissions at the effect adapter, not by prompt.
3. **When introducing retries or parallel operations:** add durable attempt identities, idempotency/reconciliation and conditional state updates in response to demonstrated hazards.
4. **When introducing governed agent artifacts:** version binding and separate review/approval/currency states as needed.
5. **Later, if justified:** institutional Offices, Charter/Seat binding, cryptographic identities, bootstrap and recovery machines.

**Guiding rule:** borrow falsifiable *invariants*, not the entire old institution. Tests and UI should reveal when an additional control is necessary.

## Open questions

- Identify exact authority and decision-record schemas in historical Symfony PRs #2–#5.
- Confirm which review findings remained applicable at the last execution PR head.
- Define MWS observation and error displays before importing any higher-level governance terms.
