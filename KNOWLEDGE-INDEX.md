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
