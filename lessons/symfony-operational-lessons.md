# Symfony operational lessons

**Classification:** Findings documented in the prior Symfony implementation. These are historical records, not tests of the fresh application.

Sources: [Seneschal CLI](https://github.com/gatomontes/imperium-symfony/blob/main/docs/SENESCHAL-CLI.md), [Next campaign](https://github.com/gatomontes/imperium-symfony/blob/main/docs/NEXT-CAMPAIGN.md), [Implementation steps](https://github.com/gatomontes/imperium-symfony/blob/main/docs/IMPERIUM-STEPS.md), [tests](https://github.com/gatomontes/imperium-symfony/tree/main/tests).

## Documented working path

The docs describe a Symfony AI / DeepSeek interview persisted in PostgreSQL through Doctrine, then a structured proposal with version history and explicit approval. Approval of a proposal is distinct from later authorization of resources or effects. The September 25 campaign document reports **47 tests / 383 assertions** for the authorization increment, with CI migration rollback/reapply. That number is a historical documented report, **not a current test run**.

## Reusable engineering lessons

- **Model judgment versus deterministic state:** Let the model interpret intent or generate language. PHP services enforce lifecycle transitions and permissions.
- **Persist before inference:** Save the operator's message first. Interrupted provider calls leave a recoverable pending state.
- **Be truthful about retries:** Retrying a lost provider response can incur another charge; exactly-once inference was not claimed.
- **Use bounded requests:** Previous CLI capped input, context, attempts and model request duration, and surfaced useful error categories.
- **Keep versions:** Proposal revisions created new retained versions; stale approval of an old proposal was refused.
- **Test the actual integration boundary:** Tests exercised the container, mocked HTTP provider, serializer, CLI and persistence without paid live inference.
- **Use framework facilities:** Doctrine for persistence; Symfony Lock for local single-host concurrency; Messenger only when needed; migrate database changes.
- **Don't mistake a plan for execution:** The documented authorization campaign explicitly had no executor; authorization records alone did not perform effects.
- **Keep UI transparent:** The old CLI showed progress, state and actionable distinctions. In the new application expose the same facts in browser views.

## Limits documented by the previous system

Local OS-based access was not suitable as unauthenticated remote access. The `flock` lock was single-host; no distributed guarantee. Model readiness was a judgment, not formally proven semantic understanding. Real secrets and private mission evidence did not belong in Git.

## Caution

The [Next campaign](https://github.com/gatomontes/imperium-symfony/blob/main/docs/NEXT-CAMPAIGN.md) reflects a specific historical snapshot. Later PRs or branches may contain bounded execution work not covered by it. This extraction does not claim to have audited those branches or live-tested the current repository.
