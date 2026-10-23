# Historical bootstrap and recovery designs

**Classification:** Theoretical contracts in `imperium-agentica-v02` (2026-08-08); **not tested features of the new MWS**.

## Artifact-pinned bootstrap

The [Bootstrap Manifest](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/bootstrap-manifest.md) aimed to authenticate an exact Charter, runtime implementation, primordial institutions, profiles, substrate definitions and routing set. Independently valid artifacts would not suffice: composition compatibility and identity had to be bound into one manifest.

The [bootstrap state machine](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/bootstrap-state-machine.md) described ten sequential states from `UNINITIALIZED` to `READY`, with progress recorded as durable checkpoints. Initial bootstrap was separate from ordinary spawning.

The [forward-recovery contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/bootstrap-forward-recovery.md) avoided pretending partial external effects had been rolled back: retry would start from the last durable checkpoint, reconcile incomplete effects, retire failed manifestations, and allocate fresh commission/instance identities.

The [Recruiter disaster-recovery contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/recruiter-disaster-recovery.md) described a narrowly authorized, recovery-only Recruiter, instantiated only after a confirmed irrecoverable loss, to produce one ordinary successor. It was explicitly distinct from initial bootstrap or routine succession.

The [concurrency and replay contract](https://github.com/gatomontes/imperium-agentica-v02/blob/main/contracts/runtime-concurrency-replay.md) specified expected-generation comparisons, single-use commissions, reservations, idempotency keys, and append-only replay ledger.

## Transferable knowledge

1. Define the exact configuration and version that an observation describes.
2. Durable transitions cannot be inferred from merely receiving an event or tool output.
3. A retry after an uncertain effect is not automatically safe; reconcile actual state first.
4. Failed attempts retain identities and evidence; they do not silently become fresh work.
5. An administrative principal's identity is not itself authorization to override policies.

## Present disposition

**Deferred.** No MasterMason, Launcher, Bootstrap Manifest, provisional Recruiter, succession process, or institution-level recovery machine in MWS. Implement framework-normal startup first. Revisit individual principles when concurrent state changes, recovery, multi-agent authority or operational deployment actually require them. This is a historical design inventory, not a promise that all described mechanisms existed as functioning code.
