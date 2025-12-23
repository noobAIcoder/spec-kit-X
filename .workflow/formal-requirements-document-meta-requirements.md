# 1. Meta-requirements for the Formal Requirements Document (FRD)

## 1.1 Document purpose and authority

* The FRD **MUST** be the project’s highest-authority SoT for:

  * product intent (what/why),
  * hard constraints (how/where boundaries),
  * success criteria,
  * scope and non-scope.
* The FRD **MUST** explicitly state: **when conflicts arise, FRD wins**; all derived artifacts (constitution, slice map, per-slice prompts) **MUST** be regenerated or corrected to match it. 

## 1.2 Scope: what belongs in FRD (and what does not)

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

## 1.3 Writing style and structure requirements

* FRD **MUST** be written in Markdown.
* FRD **MUST** use **normative language**: MUST / SHOULD / MAY (RFC 2119 semantics).
* FRD **MUST** separate:

  * **Facts** (known requirements),
  * **Decisions** (committed choices),
  * **Assumptions** (defaults used in absence of info),
  * **Open Questions** (blockers; SHOULD be minimal and prioritized).
* Each requirement **MUST** be **testable** or **verifiable** (even if not automated).
* Each requirement **MUST** be uniquely identifiable (e.g., `FR-##`, `NFR-##`, `CON-##`).

## 1.4 Traceability requirements (critical for slicing)

* FRD **MUST** include a **Core Features / Candidate Slices** section.
* For each candidate slice, FRD **MUST** include:

  * primary actor and goal,
  * success outcome,
  * acceptance scenarios (Given/When/Then),
  * key data touched,
  * key integrations touched,
  * explicit scope boundaries.
* FRD **SHOULD** include a mapping from “cross-cutting requirements” → “slices impacted” (even if approximate).

## 1.5 Quality constraints for “executable” requirements

To be usable as SoT in an SDD pipeline (transformations rather than hand-wavy guidance), FRD **MUST**:

* minimize ambiguity and internal contradiction, 
* define measurable success criteria,
* define “done” for MVP and for V1,
* define operational realities (environments, constraints, compliance),
* define what is explicitly out of scope to prevent feature creep.

---
