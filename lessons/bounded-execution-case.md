# Case study: first bounded local-file effect

**Classification:** Historical implementation and reported smoke test; unresolved security blocker. Source: [Symfony PR #5](https://github.com/gatomontes/imperium-symfony/pull/5) and [branch handoff](https://github.com/gatomontes/imperium-symfony/blob/codex/first-bounded-execution/docs/NEXT-CAMPAIGN.md).

## Attempted design

One manually authorized effect: create a new output file. The branch records an execution attempt before touching the filesystem and captures file target, output size, SHA-256, timestamps and disposition. The executor is described as deterministic: no LLM makes the authorization or filesystem decision. Existing targets are not overwritten, and retries must reconcile rather than repeat an uncertain write.

## Evidentiary state

The branch handoff reports an operator live success and PostgreSQL test results (64 tests / 471 assertions). These are **claims recorded in repository documentation**, not fresh independent execution by this extraction campaign.

## Known blocker

Symlink resolution of `public/output` could permit a write beyond the intended project root while evidence records the expected relative target. A path string matching policy is not sufficient when its canonical filesystem destination differs. The handoff instructs a narrow fix, caller tests, PostgreSQL suite/re-migration and fresh review before merge.

## Generalizable lesson

Operational proof includes negative cases: an authorized-looking command that escapes the real sandbox must fail. An evidence log accurately describing *requested* path is not proof of the actual effect's confinement.

## Relevance to the new MWS

Do not port the entire execution framework. Keep this case as an adversarial regression scenario if/when file-writing tools are introduced. MWS initially requires only two collaborating agents and visible messages; no file-effects authority infrastructure.
