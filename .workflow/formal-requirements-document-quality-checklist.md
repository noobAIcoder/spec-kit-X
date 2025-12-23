# 3. FRD quality checklist (use as “unit tests” for SoT)

Use this as the operator’s readiness gate before ChatGPT proceeds to architecture/constitution/slicing.

## Completeness

* [ ] Goals and non-goals are explicit.
* [ ] At least one persona and at least one P1 journey exist.
* [ ] Candidate slices exist and cover all goals.
* [ ] Cross-cutting requirements (auth/security/ops) are stated or intentionally N/A.

## Testability / Verifiability

* [ ] Each FR/NFR/CON statement is testable or verifiable (no vague adjectives without criteria).
* [ ] Each slice has Given/When/Then scenarios.

## Constraint clarity (your must-haves)

* [ ] GitHub integration requirements are explicit (what exactly “integration” means here).
* [ ] WSL-only constraint is explicit (what is allowed/not allowed).
* [ ] Monorepo is explicit (expected package/module boundaries).
* [ ] “Single app vs multiple tools sharing DB/infra” is decided OR defined as an explicit decision point with criteria.

## Traceability for Spec Kit

* [ ] Each candidate slice can become a standalone Spec Kit feature without inventing scope.
* [ ] Cross-cutting requirements note which slices they impact (at least qualitatively).

## Minimal ambiguity

* [ ] Open questions are prioritized and limited to true blockers.
* [ ] Assumptions are explicitly recorded (so they can be surfaced during approval).
