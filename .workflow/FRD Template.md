## 1. Meta-requirements for the Formal Requirements Document (FRD)

### 1.1 Document purpose and authority

* The FRD **MUST** be the project’s highest-authority SoT for:

  * product intent (what/why),
  * hard constraints (how/where boundaries),
  * success criteria,
  * scope and non-scope.
* The FRD **MUST** explicitly state: **when conflicts arise, FRD wins**; all derived artifacts (constitution, slice map, per-slice prompts) **MUST** be regenerated or corrected to match it. 

### 1.2 Scope: what belongs in FRD (and what does not)

FRD **MUST** include:

* **Core user outcomes** (who, what, why)
* **Core features/user stories** at portfolio level (candidate slices)
* **Cross-cutting requirements** (auth, permissions, auditing, compliance, observability, etc.)
* **Hard constraints**:

  * GitHub integration is **MUST**
  * Agent runs on **WSL only**
  * **Monorepo** requirement
  * “Single complex app vs multiple simple tools sharing DB/infra” decision or explicit option set
  * stack constraints (fixed, preferred, or TBD with decision criteria)

FRD **MUST NOT** include:

* implementation-level task lists,
* detailed code structure,
* “plan.md”-style detailed technical sequencing (Codex will do that per slice).

### 1.3 Writing style and structure requirements

* FRD **MUST** be written in Markdown.
* FRD **MUST** use **normative language**: MUST / SHOULD / MAY (RFC 2119 semantics).
* FRD **MUST** separate:

  * **Facts** (known requirements),
  * **Decisions** (committed choices),
  * **Assumptions** (defaults used in absence of info),
  * **Open Questions** (blockers; SHOULD be minimal and prioritized).
* Each requirement **MUST** be **testable** or **verifiable** (even if not automated).
* Each requirement **MUST** be uniquely identifiable (e.g., `FR-###`, `NFR-###`, `CON-###`).

### 1.4 Traceability requirements (critical for slicing)

* FRD **MUST** include a **Core Features / Candidate Slices** section.
* For each candidate slice, FRD **MUST** include:

  * primary actor and goal,
  * success outcome,
  * acceptance scenarios (Given/When/Then),
  * key data touched,
  * key integrations touched,
  * explicit scope boundaries.
* FRD **SHOULD** include a mapping from “cross-cutting requirements” → “slices impacted” (even if approximate).

### 1.5 Quality constraints for “executable” requirements

To be usable as SoT in an SDD pipeline (transformations rather than hand-wavy guidance), FRD **MUST**:

* minimize ambiguity and internal contradiction, 
* define measurable success criteria,
* define “done” for MVP and for V1,
* define operational realities (environments, constraints, compliance),
* define what is explicitly out of scope to prevent feature creep.

---

## 2. Minimal FRD template (Markdown)

```markdown
# Formal Requirements Document (FRD): <Project Name>

**Version**: 0.1 | **Date**: YYYY-MM-DD | **Owner**: <Name/Team>
**Status**: Draft | Reviewed: [ ] Product [ ] Eng [ ] Operator

## 0. Authority and Change Rules

- This FRD is the **Source of Truth (SoT)** for this project.
- Derived artifacts (constitution, slice map, per-slice spec prompts, plans, tasks) MUST match this FRD.
- Change control: <how updates are approved + versioned>.

## 1. Problem Statement

- What problem are we solving?
- Why now?
- Who is impacted?

## 2. Goals and Success Metrics

### 2.1 Goals (MUST)

- G-01: ...
- G-02: ...

### 2.2 Non-Goals (Out of scope)

- NG-01: ...
- NG-02: ...

### 2.3 Success Metrics / KPIs (measurable)

- KPI-01: ...
- KPI-02: ...

## 3. Users and Context

### 3.1 Personas / Actors

- P-01: <actor> — motivations, constraints
- P-02: ...

### 3.2 Key User Journeys (portfolio-level)

- J-01 (P1): ...
- J-02 (P2): ...

## 4. Core Features / Candidate Slices (Slice == Spec-Kit Feature)

For each slice, include: Actor, Goal, Scope, Acceptance Scenarios, Data, Integrations.

### Slice Candidate C-01: <Name>

- **Primary Actor**: ...
- **User Goal**: ...
- **In Scope**: ...
- **Out of Scope**: ...
- **Acceptance Scenarios**:
  1) Given ... When ... Then ...
  2) Given ... When ... Then ...
- **Data touched**: ...
- **Integrations touched**: ...
- **Notes / Risks**: ...

(Repeat for C-02, C-03, ...)

## 5. Functional Requirements (global, cross-slice)

List only globally true requirements here; slice-specific details belong in section 4.

- FR-001: System MUST ...
- FR-002: System MUST ...
- FR-003: System SHOULD ...
- FR-004: System MAY ...

## 6. Non-Functional Requirements (NFRs)

### 6.1 Security & Privacy

- NFR-SEC-001: ...
- NFR-SEC-002: ...

### 6.2 Performance & Scalability

- NFR-PERF-001: ...
- NFR-PERF-002: ...

### 6.3 Reliability & Availability

- NFR-REL-001: ...

### 6.4 Observability & Operations

- NFR-OBS-001: logs/metrics/traces requirements
- NFR-OBS-002: auditability requirements

## 7. Hard Constraints (non-negotiable)

- CON-001: GitHub integration is MUST (repo + PR workflow + issue tracking requirements).
- CON-002: Agent execution environment MUST be WSL-only.
- CON-003: Repository MUST be a monorepo.
- CON-004: App topology MUST be: [choose] single app OR multiple tools sharing DB/infra OR TBD with decision criteria.
- CON-005: Stack constraints: [fixed | preferred | TBD], plus decision criteria if TBD.

## 8. Data and Compliance (if applicable)

- Data classification: ...
- Retention: ...
- PII handling: ...
- Compliance requirements: ...

## 9. Integrations and External Dependencies

- INT-001: ...
- INT-002: ...

## 10. Open Questions (prioritized)

- Q-01 (P0): ...
- Q-02 (P1): ...

## 11. Assumptions

- A-01: ...
- A-02: ...

## 12. Acceptance: “Definition of Done” for MVP and V1

### MVP Done Criteria

- D-MVP-01: ...

### V1 Done Criteria

- D-V1-01: ...

```

---

## 3. FRD quality checklist (use as “unit tests” for SoT)

Use this as the operator’s readiness gate before ChatGPT proceeds to architecture/constitution/slicing.

### Completeness

* [ ] Goals and non-goals are explicit.
* [ ] At least one persona and at least one P1 journey exist.
* [ ] Candidate slices exist and cover all goals.
* [ ] Cross-cutting requirements (auth/security/ops) are stated or intentionally N/A.

### Testability / Verifiability

* [ ] Each FR/NFR/CON statement is testable or verifiable (no vague adjectives without criteria).
* [ ] Each slice has Given/When/Then scenarios.

### Constraint clarity (your must-haves)

* [ ] GitHub integration requirements are explicit (what exactly “integration” means here).
* [ ] WSL-only constraint is explicit (what is allowed/not allowed).
* [ ] Monorepo is explicit (expected package/module boundaries).
* [ ] “Single app vs multiple tools sharing DB/infra” is decided OR defined as an explicit decision point with criteria.

### Traceability for Spec Kit

* [ ] Each candidate slice can become a standalone Spec Kit feature without inventing scope.
* [ ] Cross-cutting requirements note which slices they impact (at least qualitatively).

### Minimal ambiguity

* [ ] Open questions are prioritized and limited to true blockers.
* [ ] Assumptions are explicitly recorded (so they can be surfaced during approval).

---

## Key alignment note

This FRD template is intentionally “transformable”: it gives ChatGPT enough structure to produce (1) architecture/stack proposals, (2) a constitution consistent with constraints, and (3) per-slice input blocks that are rich enough for Codex’s `/prompts:speckit.specify` to generate high-quality `spec.md` artifacts—matching the SDD transformation approach. 

If you share your existing constitution template and the slice-map template once you create it, I can tighten §7 and §4 so the FRD maps cleanly into those exact schemas.
