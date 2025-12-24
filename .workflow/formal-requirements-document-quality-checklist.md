# C. FRD Quality Checklist

## C1. Structure and taxonomy

* [ ] FRD uses the canonical headings: **User Scenarios & Testing**, **Requirements**, **Key Entities**, **Success Criteria**, **Edge Cases**.
* [ ] User Stories are formatted as **User Story N — Title (Priority: P1/P2/P3)**.
* [ ] Acceptance scenarios use **Given/When/Then** and are numbered.
* [ ] Ambiguity uses `[NEEDS CLARIFICATION: …]` and each marker is also captured in **Open Questions**.

## C2. Requirement quality

* [ ] Every `FR-###` is testable, single-scope (no compound “and/or”), and uses MUST/SHOULD/MAY.
* [ ] Every `NFR-###` includes a measurable target or an explicit justification for why it cannot.
* [ ] Every requirement has verification guidance (how it will be proven).

## C3. Slice candidate readiness

* [ ] Slice Candidates section exists and includes **only candidates**, not full per-slice specs.
* [ ] Every slice candidate has `key`, `short-name`, dependencies (if any), and an execution order.
* [ ] Each slice candidate represents an independently deliverable user outcome (at least for P1 slices).
* [ ] Every `FR-###` maps to ≥1 slice key or is explicitly “system-wide”.

## C4. Workflow constraints correctness

* [ ] GitHub workflow constraints are explicit (repo + PR + reviews + issues expectations).
* [ ] WSL-only constraints are explicit (bash-first; no required PowerShell).
* [ ] Monorepo structure is defined enough to prevent per-slice drift.
* [ ] Shared DB/infra decision is explicit or recorded as a decision item with options.
