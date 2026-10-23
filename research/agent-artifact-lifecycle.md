# Campaign 004 — Persona, Profile, and manifestation lifecycle

**Classification:** Historical Office-first doctrine, extracted 2026-10-23 from `imperium-agentica-v02/main`. This is *not* an implementation claim or the specification for the new Symfony Minimum Working Sample.

## Lifecycle and distinct gates

1. **Produce Persona candidate.** [Foundry](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/foundry/doctrine.md) composes versioned material with attributed research and governance authorship. Independent adversarial review examines the *static artifact*. Clean review does not grant Foundry approval; Foundry approval does not admit the Persona.
2. **Examine pre-admission manifestation.** [Senate](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/senate/doctrine.md) requests a strictly `examination_only` Profile and sealed assembly packet. Senate-owned mechanics instantiate a sterile witness without real operational assets. Findings distinguish practice, governance, consistency and security; critical security failures cannot be averaged away. Lord Speaker's `CONFIRMED` disposition is *not admission*.
3. **Admit and hold Persona.** [Garrison](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/garrison/doctrine.md) requires the exact Foundry release, Senate confirmation, and Constable admission disposition. Custody and retrieval do not grant suitability, Profile approval or deployment.
4. **Derive target-specific Profile.** [Laboratorium](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/laboratorium/doctrine.md) transforms a particular admitted Persona version to a declared Seat, role, framework, skill or prompt target. A favorable transformation finding is neither approval nor installation.
5. **Approve/designate the Profile.** The [Profile Artifact Contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/profile-artifact.md) defines immutable digest-bound envelopes and separate append-only attestations. A competent class-specific authority must approve; the destination steward independently designates `current_active`. The **current** source contract expressly says Imperator/SuperAdmin identity is *not automatically* competent approval authority. This differs from older extracted PR #256 wording: read authority against exact revision.
6. **Assemble and qualify manifestation.** [Conscription](https://github.com/gatomontes/imperium-agentica-v02/blob/main/offices/conscription/doctrine.md) installs the exact approved Profile on an authorized generic substrate, performs qualification, and delivers a result. Qualification alone is not Seat occupancy, tool/credential grant or deployment. The historical MasterMason Seat-binding path is an additional, separate transition.

## Two paths, not one

**Examination path:** Foundry-approved *pending-admission* Persona → Senate request → `examination_only` Profile through Laboratorium/Conscription → sterile Senate witness → confirmation decision → possible Garrison admission. Examination Profile expires with its proceeding and cannot be promoted to ordinary Profile.

**Ordinary path:** Garrison-admitted Persona → Laboratorium ordinary Profile → competent approval → destination `current_active` designation → Conscription installation and qualification → separate binding/activation/deployment decision.

This ordering resolves the apparent cycle: Senate can test a not-yet-admitted Persona without pretending it has an ordinarily installable Profile.

## Portable knowledge, not required machinery

- **Artifact identity != manifested behavior:** a successful static review cannot prove live conduct.
- **Proof is configuration-bound:** testing binds exact Persona, model, runtime, Profile, hearing protocol and examiner versions; material changes require reassessment.
- **Status is not capability:** constructed, tested, admitted, approved, active and authorized are materially different claims.
- **Transformation is not invention:** a derived agent artifact must disclose limits of what the target medium can express.
- **Provenance survives revisions:** corrections make new immutable versions with lineage; a state transition must not silently rewrite its subject.
- **Security is a veto where required:** a critical containment failure is not outweighed by other successful trials.

## MWS disposition

Keep the first Symfony MWS much smaller: two agents, visible UI, messages, attributed outputs, and clear human-triggered execution. No Office hierarchy, Senate hearing, Profile signatures, MasterMason or bootstrap workflow needed at the start. Introduce separately named review, approval and effect authorization only when there is a real observable boundary to enforce and test.

## Evidence limitations and follow-up

These are source-document contracts, not freshly executed controls. Latest `main` may differ from the 2026-08-08 PR snapshot; notably approval authority text evolved. Further campaigns should audit exact Git commits, PR discussion, qualification tests and unresolved operational transitions before asserting historical implementation or present authority.
