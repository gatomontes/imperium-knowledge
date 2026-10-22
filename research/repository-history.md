# Source history and supersession map

**Extraction:** GitHub API branch/PR/commit inventory, 2026-10-22. **Partial history review:** titles and selected PR content, not every PR diff or historical commit.

## Agentica v02

- [PR #239](https://github.com/gatomontes/imperium-agentica-v02/pull/239) — historical end-to-end Persona production integration test.
- [PR #241](https://github.com/gatomontes/imperium-agentica-v02/pull/241) — constitutional root and Secretariat organization.
- [PR #249](https://github.com/gatomontes/imperium-agentica-v02/pull/249) — adversarial artifact review moved into Foundry.
- [PR #251](https://github.com/gatomontes/imperium-agentica-v02/pull/251) — **Office-first architectural reset**; important supersession boundary.
- [PR #256](https://github.com/gatomontes/imperium-agentica-v02/pull/256) — immutable versioned Profile artifact and attestations.
- [PRs #258–264](https://github.com/gatomontes/imperium-agentica-v02/pulls?q=is%3Apr+is%3Aclosed) — MasterMason, Manifest, bootstrap state machine, forward recovery, replay and disaster recovery.

The repository has many historical `agent/*` branches representing abandoned, superseded or alternative design work. Branch existence by itself is **not evidence of adoption or successful execution**. Review old versions as historical experiments, not current doctrine.

## Symfony

- [PR #1](https://github.com/gatomontes/imperium-symfony/pull/1) — persisted CLI interview.
- [PR #2](https://github.com/gatomontes/imperium-symfony/pull/2) — proposal generation and persistence.
- [PR #3](https://github.com/gatomontes/imperium-symfony/pull/3) — revision/approval.
- [PR #4](https://github.com/gatomontes/imperium-symfony/pull/4) — resource/effect authorization, merged.
- [PR #5](https://github.com/gatomontes/imperium-symfony/pull/5) — first bounded local-file execution, **open and unmerged** at this review.

The main branch at review ended at `91e8707be9d2794e5e5e37af80200d4ad27ae916`, the authorization merge. The bounded-execution campaign is **not on main**.

## Historical execution evidence and blocker

[PR #5](https://github.com/gatomontes/imperium-symfony/pull/5) describes one authorization-bound local-file creation, a persisted execution attempt before I/O, no overwrites, bounded size, hashing, and reconciliation without blind retry. Its [campaign handoff](https://github.com/gatomontes/imperium-symfony/blob/codex/first-bounded-execution/docs/NEXT-CAMPAIGN.md) reports an operator live smoke test that wrote `public/output/imperium-test.txt` (32 bytes), and historical PostgreSQL CI of 64 tests / 471 assertions.

**However**, the same handoff explicitly bars merging until `public/output` symlink / outside-project-root containment is enforced and re-reviewed. Do not represent this campaign as accepted, safe, integrated or completed; independent revalidation remains outstanding. The PR description also contains an older `var/execution` path that conflicts with later handoff wording, illustrating why phase, exact revision and provenance matter.

## Next historic review targets

Review PR comments and unresolved review threads, PR #5 current head and code, all Office mechanics/Profiles and early agent platform transitions; distinguish adopted decisions from competing branches.
