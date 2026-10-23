# Knowledge extraction index

## Source repositories

- [imperium-agentica-v02](https://github.com/gatomontes/imperium-agentica-v02) — institutional doctrine, Offices and contracts, chiefly **theoretical/design**. Source HEAD may change.
- [imperium-symfony](https://github.com/gatomontes/imperium-symfony) — Symfony/DeepSeek/PostgreSQL mission implementations, tests and operator docs.
- [imperium-knowledge](https://github.com/gatomontes/imperium-knowledge) — cumulative synthesis and provenance.

## Initial extraction matrix

| Subject | Sources | Destination | Classification |
| --- | --- | --- | --- |
| Assume nothing; behavior before institution | [constitutional root](https://github.com/gatomontes/imperium-agentica-v02/blob/main/imperium-doctrine.md) | [Principles](doctrine/constitutional-principles.md) | Doctrinal proposal |
| Authority distinct from technical capability | Same; [Imperator](https://github.com/gatomontes/imperium-agentica-v02/blob/main/imperator.md) | [Principles](doctrine/constitutional-principles.md) | Doctrinal proposal |
| Persona, Profile, manifestation, authorization distinction | [Doctrine](https://github.com/gatomontes/imperium-agentica-v02/blob/main/imperium-doctrine.md); [Profile contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/profile-artifact.md) | [Lifecycle](doctrine/agent-artifact-lifecycle.md) | Doctrinal proposal |
| Foundry production vs live examination vs admission | [Foundry](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/foundry/doctrine.md); [Senate](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/senate/doctrine.md); [Garrison](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/garrison/doctrine.md) | [Lifecycle](doctrine/agent-artifact-lifecycle.md) | Doctrinal proposal |
| Derivation of target-specific agent artifact | [Laboratorium](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/laboratorium/doctrine.md) | [Lifecycle](doctrine/agent-artifact-lifecycle.md) | Doctrinal proposal |
| Interview, proposal, explicit approval, authorization | [Seneschal CLI](https://github.com/gatomontes/imperium-symfony/blob/main/docs/SENESCHAL-CLI.md); [Next campaign](https://github.com/gatomontes/imperium-symfony/blob/main/docs/NEXT-CAMPAIGN.md) | [Operational lessons](lessons/symfony-operational-lessons.md) | Documented implementation/test |
| Concurrency, replay, recovery primitives | [Runtime replay contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/runtime-concurrency-replay.md) | [Principles](doctrine/constitutional-principles.md) | Theoretical contract, deferred |
| Minimum working sample scope | Prior project discussion; [Symfony incrementalism](https://github.com/gatomontes/imperium-symfony/blob/main/docs/IMPERIUM-STEPS.md) | [MWS guidance](decisions/minimum-working-sample.md) | Current direction |

## Remaining extraction

This is **an initial pass**, not a completed audit. Still review all Office mechanics, Seat and Profile texts, remaining bootstrap/recovery contracts, Symfony application source and tests, Git branches, pull-request decisions and historical commits. In particular, branch and PR history may contain knowledge no longer represented on `main`. Track decisions that were superseded instead of silently elevating their old wording.

## Campaign 002 — History and mechanisms

- [Bootstrap and forward recovery](research/bootstrap-and-recovery.md) — theoretical manifest, state machine, replay and recovery designs.
- [Office mechanics inventory](research/office-mechanics-inventory.md) — ten historical Offices and mechanical/cognitive separation.
- [Repository history](research/repository-history.md) — supersession map, major PRs and branch caveats.
- [Bounded execution case](lessons/bounded-execution-case.md) — PR #5 reported live effect and unresolved containment blocker.

Historical GitHub activity was inspected at the level of branch/PR inventory plus selected document contents and PR #5. Further diff-level and review-comment work remains; this is **not** a complete forensic audit.

## Campaign 003 — Decision provenance and supersession

- [Decision provenance and supersession](research/decision-provenance-and-supersession.md) — constitutional reset lineage, immutable Profile contract, and review-derived negative cases from Symfony PR #5.

This review preserves historical findings as test candidates, not claims about current deployed behavior or mandatory MWS architecture. The latest Symfony execution code and historical review-thread dispositions still require further verification.

## Campaign 004 — Agent artifact lifecycle

- [Persona → Profile → manifestation](research/agent-artifact-lifecycle.md) — historical Foundry, Senate, Garrison, Laboratorium and Conscription gates; pre-admission examination exception, exact-version authority boundaries, and MWS disposition.

Classification: historical design specifications, not evidence that all transitions were operationally implemented.

## Campaign 005 — Authority, evidence and execution

- [Authority, evidence and execution boundaries](research/authority-evidence-execution.md) — historical explicit authority and replay principles, risk-driven negative cases, and phased MWS adoption.
