# Formal Requirements Document Reference Standard (Spec‑Kit‑Aligned)

**Purpose:** Define a normative, Spec‑Kit‑aligned FRD that serves as the project’s foundational Source of Truth (SoT) and feeds downstream slicing and Spec Kit execution (spec → plan → tasks → implement). 
**Scope:** This reference standard covers **FRD Meta‑requirements**, a **two‑stage FRD authoring template**, and an **FRD Quality Checklist**.

---

## 1. Two‑stage FRD authoring protocol

### 1.1 Stage 1 — FRD Foundation + Capability Candidates (Approval Gate)

**Stage 1 MUST create:**

1. Document control (versioning, status, ownership, approvals).
2. Goals, Non‑Goals.
3. Scope boundaries (in/out) and system boundary.
4. Global constraints (WSL‑only, GitHub mandatory, monorepo mandatory, etc.).
5. Glossary (minimum viable).
6. **Capability Candidates** list (atomic functionalities) with priority and dependencies.
7. Open Questions and Assumptions (initial).

**Stage 1 MUST NOT create:**

1. **User Stories & Testing** section (no P1/P2/P3 stories yet).
2. **Acceptance Scenarios** (no Given/When/Then yet).
3. `FR-###` / `NFR-###` enumerations (no requirement catalog yet).
4. Full slice definitions or per-slice `/speckit.specify` input texts.
5. `spec.md`, `plan.md`, `tasks.md`, checklists, or any Spec‑Kit feature directory artifacts.
6. Final tech stack selection (beyond constraints/preferences).

   * Stage 1 MAY record “stack constraints” (e.g., “MUST run on Postgres”) but MUST NOT lock the final stack.

**Stage 1 STOP condition:** The FRD **MUST** include a clear `STOP FOR OPERATOR APPROVAL` marker immediately after the Capability Candidates list. No Stage 2 content should be generated before explicit approval.

---

### 1.2 Stage 2 — FRD Formalization (after approval)

**Stage 2 MUST create:**

1. **User Scenarios & Testing *(mandatory)*:** user stories formatted as Spec‑Kit style `User Story N — Title (Priority: P1/P2/P3)`.
2. **Acceptance Scenarios:** Given/When/Then per user story.
3. **Requirements *(mandatory)*:**

   * Functional Requirements (`FR-###`) traceable to stories/scenarios.
   * Non‑Functional Requirements (`NFR-###`) with measurable targets.
4. **Key Entities** (if data is involved).
5. **Success Criteria *(mandatory)*:** measurable outcomes.
6. **Edge Cases** section.
7. **Global Technical Context (Candidate)** (stack decision) aligned to Spec‑Kit planning vocabulary (Language/Version, Dependencies, Storage, Testing, Target Platform, Project Type).
8. **Slice Candidates** list (candidate mapping only; not full slice specs):

   * Slice keys MUST match `^S[0-9]{2,3}$`. 
   * Slice candidates MUST map back to user stories and `FR-###/NFR-###`.
9. Traceability matrix (Stories ↔ FR/NFR ↔ Slice Candidates).
10. Updated Open Questions and Assumptions.

**Stage 2 MUST NOT create:**

1. Per-slice full `spec.md` content (that is produced by Codex `/prompts:speckit.specify`).
2. Per-slice `plan.md` or `tasks.md` content (Codex responsibilities).
3. Per-slice `/prompts:speckit.specify` argument blocks (those are produced later by ChatGPT in your **preemptive stage Phase 2**, not inside FRD).
4. Spec‑Kit branch numbers (`NNN-...`) or feature directories (Codex will assign numbers via `/speckit.specify`).

---

## 2. FRD Meta‑requirements

### 2.1 Source of Truth and transformation discipline

1. The FRD **MUST** be the authoritative SoT for product intent and global constraints. 
2. Downstream artifacts (slices, specs, plans, tasks) **MUST** be treated as transformations derived from the FRD. 
3. If downstream artifacts diverge, the FRD **MUST** be updated and the downstream artifacts regenerated or reconciled.

### 2.2 Stage governance

4. The FRD **MUST** declare its current stage: `Stage 1 (Foundation)` or `Stage 2 (Formalized)`.
5. The FRD **MUST** include an approval record for Stage 1 → Stage 2 transition.
6. Stage 2 content **MUST NOT** exist in a Stage 1 FRD beyond empty placeholders.

### 2.3 Taxonomy alignment (Spec‑Kit vocabulary)

7. Stage 2 sections **MUST** use these headings verbatim:

   * `User Scenarios & Testing *(mandatory)*`
   * `Requirements *(mandatory)*`
   * `Key Entities *(include if feature involves data)*`
   * `Success Criteria *(mandatory)*`
   * `Edge Cases`
8. User stories **MUST** be prioritized as `P1/P2/P3` and be independently testable journeys (Spec‑Kit style).
9. Ambiguity **MUST** be encoded as `[NEEDS CLARIFICATION: …]` and also tracked in `Open Questions`.

### 2.4 Requirement quality and identity

10. Stage 2 requirements **MUST** use stable IDs:

* `FR-###` for functional requirements (`System MUST …`)
* `NFR-###` for non‑functional (`System MUST …` + metric)
* `C-###` for constraints (`System MUST …`)

11. Each `FR-###` **MUST** include:

* rationale,
* linkage to at least one acceptance scenario,
* verification method (how to prove).

12. Each `NFR-###` **MUST** include:

* a measurable target or a documented exception,
* verification method.

### 2.5 Slice candidate alignment

13. Stage 2 **MUST** include slice candidates but **MUST NOT** include fully specified slices.
14. Slice candidate keys **MUST** follow `^S[0-9]{2,3}$`. 
15. Slice candidates **MUST** reference the constitution path used by the downstream slices map (`.specify/memory/constitution.md`). 

### 2.6 Environment constraints (your hard requirements)

16. Constraints section **MUST** include:

* GitHub mandatory workflow expectations,
* WSL‑only execution constraints,
* monorepo constraint and boundaries,
* shared DB/infra decision (or explicit decision item if undecided).

---

## 3. FRD Template (two‑stage, Spec‑Kit‑aligned)

> **Do not rename headings.** Stage 1 ends at the STOP marker.

## 0. Document Control

* Project Name:
* FRD Version:
* Stage: `Stage 1 (Foundation)` / `Stage 2 (Formalized)`
* Status: Draft / Approved / Superseded
* Owner:
* Approvers:
* Change Log:

  * vX.Y — date — summary — author

## 1. Context

### 1.1 Problem Statement

### 1.2 Goals

### 1.3 Non‑Goals

### 1.4 Scope Boundaries

* In scope:
* Out of scope:

## 2. Operating Constraints *(mandatory)*

Write as `C-###: System MUST …`

* C-001 GitHub Workflow:
* C-002 WSL‑Only Execution:
* C-003 Monorepo Structure:
* C-004 Shared DB/Infra Direction:
* C-005 Data/Security Constraints:
* C-006 Other Organizational Constraints:

## 3. Glossary *(minimum viable)*

* Term → definition

## 4. Capability Candidates *(Approval Gate; Stage 1 deliverable)*

**Definition:** A capability candidate is an atomic, stand‑alone “thing the system must enable,” not yet expanded into Spec‑Kit user stories.

Use this format per capability:

* **CAP-### Title**:

  * **Primary actor**:
  * **Outcome**:
  * **Priority**: P1/P2/P3
  * **Dependencies**: CAP-### / C-### / external systems
  * **Notes**: include `[NEEDS CLARIFICATION: …]` if required

### STOP FOR OPERATOR APPROVAL

*No Stage 2 content may be authored until this STOP is explicitly cleared.*

---

## 5. User Scenarios & Testing *(mandatory)*  *(Stage 2 only)*

## User Story 1 — [Title] (Priority: P1)

[Describe journey]

**Independent Test**: …

**Acceptance Scenarios**:

1. **Given** … **When** … **Then** …

(Repeat for P2/P3)

## 6. Requirements *(mandatory)*  *(Stage 2 only)*

### Functional Requirements

* **FR-001**: System MUST …

  * Rationale:
  * References (story/scenario):
  * Verification:
    (Repeat)

### Non‑Functional Requirements

* **NFR-001 (Performance)**: System MUST …

  * Target:
  * Verification:
    (Repeat)

## 7. Key Entities *(include if feature involves data)*  *(Stage 2 only)*

* Entity: description, key fields, invariants, retention

## 8. Success Criteria *(mandatory)*  *(Stage 2 only)*

## Measurable Outcomes

* SC-001 …
* SC-002 …

## 9. Edge Cases  *(Stage 2 only)*

* EC-001 …
* EC-002 …

## 10. Global Technical Context (Candidate)  *(Stage 2 only)*

Use Spec‑Kit planning vocabulary:

* Language/Version:
* Primary Dependencies:
* Storage:
* Testing:
* Target Platform:
* Project Type:
* Performance Goals:
* Constraints:

## 11. Slice Candidates (Spec‑Kit Features; candidates only)  *(Stage 2 only)*

**Rules:** keys MUST match `^S[0-9]{2,3}$`. 
Table columns:

| key | title | short_name | depends_on | order | covers (CAP/Stories/FR/NFR) |
| --- | ----- | ---------- | ---------- | ----: | --------------------------- |

**Important:** This section lists **candidates only**. Do NOT include per-slice `/prompts:speckit.specify` texts here.

## 12. Traceability *(mandatory; Stage 2 only)*

| CAP | User Story | FR/NFR | Slice Candidate |
| --- | ---------- | ------ | --------------- |

## 13. Open Questions *(mandatory if any)*

* Q-###: question, impact, owner, deadline

## 14. Assumptions

* A-###: assumption, confidence, validation plan

```

---

## 4) FRD Quality Checklist (stage‑gated)

### 4.1 Stage 1 approval checklist (before STOP is cleared)

* [ ] Document Control completed (version, owner, approvers, stage declared).
* [ ] Goals and Non‑Goals are non-overlapping and specific.
* [ ] Scope boundaries are explicit (in/out).
* [ ] Constraints include GitHub mandatory, WSL‑only, monorepo mandatory.
* [ ] Capability candidates are atomic and stand‑alone (single actor/outcome where possible).
* [ ] Capability candidates have priorities (P1/P2/P3) and dependencies.
* [ ] Open questions use `[NEEDS CLARIFICATION: …]` and are listed.

**Stage 1 MUST NOT contain:**

* [ ] No user stories with acceptance scenarios.
* [ ] No `FR-###` / `NFR-###` catalogs.
* [ ] No per-slice specify texts or per-slice spec content.

### 4.2 Stage 2 readiness checklist (after STOP is cleared)

* [ ] `User Scenarios & Testing *(mandatory)*` exists and stories are in Spec‑Kit format.
* [ ] Each user story has at least one Given/When/Then acceptance scenario.
* [ ] `Requirements *(mandatory)*` exists with `FR-###` and `NFR-###` IDs.
* [ ] Every `FR-###` traces to at least one story/scenario and has verification guidance.
* [ ] NFRs have measurable targets or documented exceptions.
* [ ] Key Entities included if data exists.
* [ ] Success Criteria are measurable.
* [ ] Edge cases exist and are realistic.
* [ ] Global Technical Context (Candidate) is present (stack decision after capabilities).
* [ ] Slice Candidates exist; keys match `^S[0-9]{2,3}$`. 
* [ ] Traceability table is complete.

**Stage 2 MUST NOT contain:**

* [ ] No per-slice `/prompts:speckit.specify` text blocks.
* [ ] No `spec.md`/`plan.md`/`tasks.md` content or task breakdowns.
* [ ] No Spec‑Kit numeric branch numbers; slice keys are independent of branch numbering.

### 4.3 Drift control checklist (pre-slicing)

* [ ] Terminology matches Spec‑Kit taxonomy (stories, acceptance scenarios, FR/NFR, key entities, success criteria).
* [ ] Cross-cutting constraints are centralized (not duplicated inconsistently across stories).
* [ ] Slice candidates are candidates only; detailed per-slice generation is deferred to the slice-map + `/speckit.specify` step.
* [ ] Constitution path planned for downstream artifacts is `.specify/memory/constitution.md`. 

---

If you want the next refinement: I can add a **one-page transformation spec** (“How to convert Stage 2 FRD → slices-map JSON + per-slice `/prompts:speckit.specify` texts”), explicitly aligned to your JSON schema and using your constitution template location. 
