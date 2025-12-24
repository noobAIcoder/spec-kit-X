# B. FRD Template

**Use the headings below exactly.**

## 0. Document Control

* **Project Name**:
* **FRD Version**:
* **Status**: Draft / Approved / Superseded
* **Owner**:
* **Approvers**:
* **Ratified**:
* **Last Amended**:
* **Change Log**:

  * vX.Y — date — summary — author

## 1. Context

### 1.1 Problem Statement

### 1.2 Goals

### 1.3 Non‑Goals

### 1.4 Scope Boundaries

* In scope:
* Out of scope:

## 2. Operating Constraints *(mandatory)*

> Write these as `C-###: System MUST …`

* **C-001 GitHub Workflow**: System MUST use GitHub for repo + PR workflow (branch protections, reviews, issue tracking expectations).
* **C-002 WSL‑Only Execution**: System MUST assume automation/agents run on WSL; bash-first; no required PowerShell.
* **C-003 Monorepo**: System MUST be structured as a monorepo with defined module boundaries.
* **C-004 Shared Infra**: System MUST [use one shared DB/infra OR define multiple stacks] — [NEEDS CLARIFICATION if undecided].
* **C-005 Stack Constraints**: System MUST constrain language/framework/storage options (see §6).

## 3. User Scenarios & Testing *(mandatory)*

> Write like Spec‑Kit: prioritized, independently testable journeys.

### User Story 1 — [Title] (Priority: P1)

[Plain-language journey]

**Independent Test**: [how to test story alone]

**Acceptance Scenarios**:

1. **Given** … **When** … **Then** …

### User Story 2 — [Title] (Priority: P2)

…

### User Story 3 — [Title] (Priority: P3)

…

### Edge Cases

* EC‑001 …
* EC‑002 …

## 4. Requirements *(mandatory)*

### Functional Requirements

> Use bullet style to match Spec‑Kit spec template.

* **FR-001**: System MUST …

  * **Rationale**:
  * **References**: (User Story IDs / scenario numbers)
  * **Verification**: (demo/test/log/metric)
* **FR-002**: System MUST …
  …

### Non‑Functional Requirements

* **NFR-001 (Performance)**: System MUST …

  * **Target**: (numeric threshold)
  * **Verification**:
* **NFR-002 (Security/Privacy)**: System MUST …
  …

## 5. Key Entities *(include if feature involves data)*

* **[Entity 1]**: description, key fields, invariants, retention
* **[Entity 2]**: …

## 6. Success Criteria *(mandatory)*

### Measurable Outcomes

* **SC-001**: …
* **SC-002**: …

## 7. Global Technical Context *(feeds constitution + downstream plans)*

> Keep field names aligned with Spec‑Kit plan template.

* **Language/Version**: [or NEEDS CLARIFICATION]
* **Primary Dependencies**: [or NEEDS CLARIFICATION]
* **Storage**: [or N/A / NEEDS CLARIFICATION]
* **Testing**: [or NEEDS CLARIFICATION]
* **Target Platform**: [or NEEDS CLARIFICATION]
* **Project Type**: [single/web/mobile/multi-tool; drives repo structure]
* **Constraints**: [performance, compliance, hosting, licensing]

## 8. Constitution Inputs *(do not write constitution here; only inputs)*

> The constitution template in spec-kit contains placeholders for: Project name, principles, governance, and additional sections.

* **Project Name**: …
* **Core Principles candidates** (names + 2–5 line descriptions each):

  * P‑01: [PRINCIPLE_NAME] — [DESCRIPTION]
  * P‑02: …
* **Additional Sections candidates**:

  * Section‑A name: …
  * Section‑A content outline: …
* **Governance rules candidates**:

  * G‑01 …
  * G‑02 …

## 9. Slice Candidates *(Spec‑Kit Features; candidates only)*

> Use this table to match the slice taxonomy and reduce drift.

| key (S##) | title | short-name | depends_on | order | covers (Stories / FRs) | notes |
| --------- | ----- | ---------- | ---------- | ----: | ---------------------- | ----- |

Rules:

* `key` **MUST** match `^S[0-9]{2,3}$`. 
* `short-name` **MUST** be kebab-case per schema constraints. 
* `covers` **MUST** reference User Stories + `FR-###/NFR-###`.

## 10. Traceability *(mandatory)*

| Requirement ID | User Story / Scenario | Slice Candidate key(s) |
| -------------- | --------------------- | ---------------------- |

## 11. Open Questions *(mandatory if any)*

* **Q-001**: [NEEDS CLARIFICATION: …] — impact — owner — deadline
* **Q-002**: …

## 12. Assumptions

* **A-001**: …
* **A-002**: …
