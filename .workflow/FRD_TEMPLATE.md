# FRD_TEMPLATE.md

---

## 1. Stage 1

```markdown
# FDR Template stage 1

## 0. Document Control

- Project Name:
- FRD Version:
- Stage: Stage 1 (Foundation) / Stage 2 (Formalized)
- Status: Draft / Approved / Superseded
- Owner:
- Approvers:
- Change Log:
  - vX.Y — date — summary — author

## 1. Goals / Non-Goals / Boundaries

### 1.1 Problem Statement

### 1.2 Goals

### 1.3 Non-Goals

### 1.4 Scope Boundaries

- In scope:
- Out of scope:
- System boundary:

## 2. Operating Constraints *(mandatory)*

- C-001: System MUST …
- C-002: System MUST …
- C-003: System MUST …
- C-004: System MUST …
- C-005: System MUST …

Minimum required constraints:

- GitHub workflow mandatory
- WSL-only execution; bash-first
- Monorepo mandatory
- Shared DB/infra direction (chosen or Q-###)
- Stack constraints (allowed/forbidden)

## 3. Glossary

- Term: definition

## 4. Capability Candidates *(Approval Gate; Stage 1 deliverable)*

For each:

- CAP-### Title (Priority: P1/P2/P3)
  - Primary actor:
  - Outcome:
  - Dependencies: CAP-### / C-### / external
  - Notes: [NEEDS CLARIFICATION: …] (if any)

## 5. Open Questions

- Q-###: question — impact — owner — deadline

## 6. Assumptions

- A-###: assumption — confidence — validation plan

**STOP FOR OPERATOR APPROVAL**

**Stage 2 content below MUST NOT be authored until STOP is explicitly cleared**
```

---

## 2. Stage 2

```markdown
# FDR Template stage 2

## 7. User Scenarios & Testing *(mandatory)*

### User Story 1 — [Title] (Priority: P1)

[Journey]
**Independent Test**:
**Acceptance Scenarios**:

1. Given … When … Then …

(Repeat P2/P3)

## 8. Requirements *(mandatory)*

### Functional Requirements

- FR-001: System MUST …
  - Rationale:
  - References: (User Story / scenario)
  - Verification:

### Non-Functional Requirements

- NFR-001 (Category): System MUST …
  - Target:
  - Verification:

## 9. Key Entities *(include if feature involves data)*

- Entity: description, key fields, invariants, retention

## 10. Success Criteria *(mandatory)*

- SC-001: measurable outcome
- SC-002: measurable outcome

## 11. Edge Cases

- EC-001:
- EC-002:

## 12. Global Technical Context (Candidate)

- Language/Version:
- Primary Dependencies:
- Storage:
- Testing:
- Target Platform:
- Project Type:
- Performance Goals:
- Constraints:

## 13. Constitution Inputs (for template fill later; do NOT output constitution here)

- Project Name:
- Principle candidates (name + 2–5 lines each):
- Section candidates:
- Governance candidates:

## 14. Slice Candidates (candidates only)

| key | title | short_name | depends_on | order | covers (CAP/Story/FR/NFR) |
|---|---|---|---|---:|---|

Rules:

- key MUST match ^S[0-9]{2,3}$ :contentReference[oaicite:4]{index=4}
- short_name MUST be kebab-case :contentReference[oaicite:5]{index=5}

## 15. Traceability

| CAP | User Story | FR/NFR | Slice key |
|---|---|---|---|
```
