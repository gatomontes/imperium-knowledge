# Rebuild decision: Minimum Working Sample first

**Classification:** Current project direction (operator discussion, October 2026), not proof of implementation.

## Goal

Build a basic, visibly working Symfony multi-agent app before integrating institutional governance. The smallest complete demonstration:

1. Symfony application with browser UI, Symfony AI, configured model provider and PostgreSQL.
2. Manually configured Coordinator and Worker.
3. Operator submits a task; Coordinator delegates; Worker responds; Coordinator returns an answer.
4. UI shows task, handoff, individual contributions, final result and failure state.
5. Automated test of the cooperation path with mocked provider responses, and a separate live smoke run.

## Non-goals for the MWS

No automatic Legate bootstrap, MasterMason, Recruiter, Curia, Senate, Persona formation pipeline, universal journal framework, distributed execution or automatic recruitment. Do not build abstractions in advance of demonstrated need.

## Rules

- Develop a vertical slice including UI, behavior and test.
- Use ordinary security safeguards and secret management immediately; postponing **Imperium governance** is not postponing basic safety.
- Prefer Symfony-native facilities over custom infrastructure.
- After an observable baseline, add one doctrine mechanism per verified problem and test the *before vs. after* behavior.
- Keep this repository as accumulated reasoning/evidence, separate from runtime code.

Source precedent: [Imperium steps](https://github.com/gatomontes/imperium-symfony/blob/main/docs/IMPERIUM-STEPS.md) already advocated growing only the next useful Symfony mission path.
