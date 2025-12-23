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
