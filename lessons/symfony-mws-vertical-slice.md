# Campaign 006 — Symfony implementation lessons for the MWS

**Evidence classification:** Historical documented implementation from [Seneschal CLI](https://github.com/gatomontes/imperium-symfony/blob/main/docs/SENESCHAL-CLI.md), [Imperium Steps](https://github.com/gatomontes/imperium-symfony/blob/main/docs/IMPERIUM-STEPS.md), and [Next Campaign](https://github.com/gatomontes/imperium-symfony/blob/main/docs/NEXT-CAMPAIGN.md), as inspected 2026-10-23. Current MWS recommendations below are **new guidance**, not inherited implementation status. Reported historical CI and operator acceptance have not been independently re-executed here.

## What the previous Symfony path actually demonstrated

The historical local CLI recorded interview exchanges in PostgreSQL through Doctrine and a small Atheneum persistence service. It used the configured Symfony AI agent and DeepSeek. A human could resume interviews, retry pending turns, grant drafting permission with a specific command, review versioned proposals, and approve the observed latest proposal. A plain conversational “yes” was not treated as authorization. [CLI documentation](https://github.com/gatomontes/imperium-symfony/blob/main/docs/SENESCHAL-CLI.md).

The sequence **Interview → understanding → permission to draft → proposal → revision → version-specific proposal approval → separate authorization** matters more than the institutional naming. The [authorization campaign handoff](https://github.com/gatomontes/imperium-symfony/blob/main/docs/NEXT-CAMPAIGN.md) reported 47 tests / 383 assertions for a proposal-bound authorization record; its historical scope deliberately included no execution action. These counts are **reported CI evidence**, not fresh verification.

Historical design also explicitly says not to resurrect O4/O5, PPC10 or Atheneum A1–A5 as prerequisites merely because they once existed. [Steps](https://github.com/gatomontes/imperium-symfony/blob/main/docs/IMPERIUM-STEPS.md).

## Engineering lessons suitable for the next app

| Observed design pattern | Transferable lesson | Caution |
| --- | --- | --- |
| Persist message before calling provider | Interrupted calls must remain visible and resumable | Retrying might produce a second inference charge; do not claim exactly-once |
| Explicit `/approve` for drafting | Intent-specific consent should be an application state transition | Natural-language assent is not a trustworthy permission gate |
| Immutable proposal versions | Approval must refer to the exact observed version | Reject stale approval after revision |
| Proposal approval versus authorization record | Acceptance of a plan is not permission to consume resources or cause effects | Validate exact scope mechanically if effects are introduced |
| Symfony Lock + Doctrine version field | Prevent overlapping writes and stale decisions | Local `flock` is not a distributed lock |
| Bounded provider attempts, input/context/output size and duration | Show concrete upper limits and errors | These are not a dollar ceiling |
| Doctrine migrations and disposable test DB | Preserve state changes as reproducible schema transitions | Historical CI is not proof of a newly built app |

## Proposed two-agent MWS (new direction)

For the present Symfony rebuild, **do not reproduce the old Seneschal CLI wholesale**. Build one browser UI showing a session with two explicit agent roles, each attributed turn, model invocation status, failures, and final result. Initial tool use can be absent. Use Symfony's native AI integration, Doctrine persistence and Twig/Stimulus/Turbo where appropriate.

Suggested first vertical slice:
1. Human creates a session with a single request.
2. Agent A interprets the request and sends a visible message to Agent B.
3. Agent B contributes one bounded response.
4. Agent A summarizes an observable result for the human.
5. The UI displays chronological messages, speaker identity, errors, and state; reload resumes without calling the models again.

### Acceptance evidence (proposed tests, not completed)

- A full two-agent exchange is visible and persisted.
- Reloading shows identical message sequence without repeat inference.
- Failure after a persisted input displays a pending/error state rather than manufactured output.
- Concurrent/repeated submissions do not silently duplicate the same operation.
- No operation changes external state; model output cannot silently grant tool authority.

## Deferred

Do not implement Office/Seat administration, signed Profile envelopes, Seneschal's multi-step governance interview, universal executor, complex bootstrap, or historical recovery machines in this initial slice. Introduce one mechanism only when its observed need can be shown and tested.

## Traceability gaps

A future code-level audit should examine historical `src/Command/InterviewCommand.php`, `src/Atheneum/`, associated test files, and the latest PR #5 code. Documentation alone does not establish source-code correctness or deployed behavior.
