# Campaign 003 — Decision provenance and supersession

**Status:** historical source review, not an implementation specification. Reviewed 2026-10-23. Source links below identify the decision or review; reported validation does not equal fresh execution.

## Three distinct kinds of evidence

1. **Merged design decision** establishes what a repository adopted at a particular revision; it does not show that the idea remains current after later resets.
2. **Implementation and test report** describes a checked behavior at a commit; it does not establish deployability, completeness, or safety of other paths.
3. **Review observation** identifies a failure mode and may remain instructive even when later code changes make the particular comment obsolete. Re-check its applicability against the final revision.

## Agentica: competing constitutional baselines

- [Agentica PR #251](https://github.com/gatomontes/imperium-agentica-v02/pull/251) merged an **Office-first reset**. Its own description reports deletion of 1,027 earlier files and explicitly removes the previous executable architecture from the active tree. Earlier merged constitutional/kernel implementations are retained in history, **not automatically re-admitted**.
- The PR diff exposes an earlier **Senate-first constitutional reset** and its discussion of Core Doctrine versions. Those were real historical stages but are not interchangeable with the later Office-first baseline.
- [Agentica PR #256](https://github.com/gatomontes/imperium-agentica-v02/pull/256) subsequently merged a **Profile artifact contract**: immutable, digest-bound envelope; lineage to an exact Persona; append-only lifecycle attestations; distinct approval and current/active designation; refusal of installation where approval authority is unassigned. This contract belongs to the Office-first historical phase, **not** to today's MWS.

### Portable principles

- Record **which baseline and revision** a claim belongs to.
- Distinguish *approval*, *current designation*, *installation*, and *real-world authority*; none is interchangeable.
- Preserve immutable artifact versions while appending lifecycle events separately when the application actually needs audited transitions.
- A reset must be represented as a **supersession**, not as proof that the earlier work never happened.

## Symfony PR #5: review-derived negative test cases

[Symfony PR #5](https://github.com/gatomontes/imperium-symfony/pull/5) is **open and unmerged** as of this inspection; head `e8a44d04fdcbd7f64585c5417ab8beafab7289ae`. Its description still names `var/execution/`, while the later handoff describes `public/output/`: treat target location as **revision-dependent** and inspect current code before relying on it.

Earlier [review comments](https://github.com/gatomontes/imperium-symfony/pull/5) at commit `dc33bae1b2` recorded:

1. **Approved limits must be enforced at the effect boundary.** A generic authorization listing resources/effects is insufficient if it ignores content-size or file-type limits ([review](https://github.com/gatomontes/imperium-symfony/pull/5#discussion_r4109661707)).
2. **Free-text strings must not confer capability.** A substring search for `filesystem write` can match a negative prohibition such as `No filesystem write access`; use controlled positive permission values ([review](https://github.com/gatomontes/imperium-symfony/pull/5#discussion_r4109661708)).
3. **Matching output is not evidence of causation.** A matching hash after a crash does not by itself prove that this execution attempt created the file ([review](https://github.com/gatomontes/imperium-symfony/pull/5#discussion_r4109661709)).
4. **Filesystem path strings are not confinement.** The previously catalogued symlink escape problem requires checking actual resolved destinations, not just expected relative paths ([bounded execution case](../lessons/bounded-execution-case.md)).

The newer automated review summary says code review completed at head `e8a44d0`; this does **not** prove that every historic concern is closed. A full head-code and thread-resolution audit is still pending. We make **no assertion that the earlier review findings reproduce at the latest head**.

## Minimal Working Sample disposition

These findings enter a **testable risk catalogue**, not a required architecture. Start with two collaborating Symfony agents and a UI exposing each message, decision, and tool interaction. No bootstrap machines, Office hierarchy, signed Profiles, or file-writing execution grant is required to begin. When actual effects are introduced, turn the relevant negative cases above into narrow tests.

## Pending investigation

- Check detailed review-thread resolution and final code of Symfony PR #5.
- Examine Agentica PR #249 and Office admission/examination transitions for other durable distinctions.
- Audit older branches and PR decisions without confusing a merged historical proposal with current project doctrine.
