# FRD_REFERENCE.md

## Authority

- FRD is the project SoT. Downstream artifacts are transformations. :contentReference[oaicite:0]{index=0}
- Stage 1 → Stage 2 transition MUST require explicit operator approval.

## Stage gates: MUST / MUST NOT

### Stage 1 (Foundation + Capability Candidates)

MUST create:

- Document Control (version, status, owner, approvers, changelog)
- Goals / Non-Goals
- Scope Boundaries (in/out, system boundary)
- Operating Constraints (C-###)
- Glossary (minimum viable)
- Capability Candidates (CAP-###), atomic and stand-alone, prioritized (P1/P2/P3)
- Open Questions (Q-###) and Assumptions (A-###)
- STOP marker for operator approval

MUST NOT create:

- User Scenarios & Testing section (no User Story N blocks)
- Acceptance Scenarios (Given/When/Then)
- Functional/Non-Functional requirement catalogs (FR-### / NFR-###)
- Key Entities, Success Criteria, Edge Cases
- Slice Candidates table
- Constitution.md output
- Per-slice /prompts:speckit.specify texts
- Any Spec Kit artifacts: spec.md/plan.md/tasks.md, feature dirs, branch numbers

### Stage 2 (Formalized FRD; after approval)

MUST create:

- User Scenarios & Testing *(mandatory)* (User Story N — Title (Priority: P1/P2/P3))
- Acceptance Scenarios (Given/When/Then) per story
- Requirements *(mandatory)*:
  - Functional Requirements (FR-###)
  - Non-Functional Requirements (NFR-###) with measurable targets
- Key Entities *(include if feature involves data)*
- Success Criteria *(mandatory)* (SC-###)
- Edge Cases (EC-###)
- Global Technical Context (Candidate) aligned to Spec Kit plan vocabulary
- Slice Candidates (candidates only) aligned to slices-map taxonomy:
  - key pattern ^S[0-9]{2,3}$ :contentReference[oaicite:1]{index=1}
  - short_name kebab-case :contentReference[oaicite:2]{index=2}
  - depends_on (keys), order (int)
- Traceability matrix (CAP ↔ Story ↔ FR/NFR ↔ Slice key)

MUST NOT create:

- Per-slice spec.md content (Codex /prompts:speckit.specify responsibility)
- Per-slice plan.md/tasks.md content (Codex responsibility)
- Per-slice /prompts:speckit.specify input blocks (generated later from slices map)
- Spec Kit numeric branch numbers (NNN-...)

## Taxonomy (fixed)

IDs:

- CAP-### capability candidates (Stage 1+)
- C-### constraints
- Q-### open questions
- A-### assumptions
- FR-### functional requirements (Stage 2)
- NFR-### non-functional requirements (Stage 2)
- SC-### success criteria (Stage 2)
- EC-### edge cases (Stage 2)

Headings (Stage 2 MUST use verbatim):

- User Scenarios & Testing *(mandatory)*
- Requirements *(mandatory)*
- Key Entities *(include if feature involves data)*
- Success Criteria *(mandatory)*
- Edge Cases

## Workflow constraints (MUST be constraints)

- GitHub workflow is mandatory.
- WSL-only execution; bash-first.
- Monorepo is mandatory.
- Constitution path for slices-map MUST be `.specify/memory/constitution.md`. :contentReference[oaicite:3]{index=3}
