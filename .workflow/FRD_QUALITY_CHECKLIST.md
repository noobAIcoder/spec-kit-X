# FRD_QUALITY_CHECKLIST.md

## Stage 1 Gate (before STOP is cleared)

- [ ] Document Control complete (stage declared).
- [ ] Goals/Non-Goals non-overlapping.
- [ ] Scope boundaries explicit (in/out/system boundary).
- [ ] Constraints include: GitHub mandatory, WSL-only, monorepo, shared infra direction, stack constraints.
- [ ] Capability candidates:
  - [ ] Atomic (single outcome).
  - [ ] Stand-alone value.
  - [ ] Priority P1/P2/P3.
  - [ ] Dependencies declared where needed.
- [ ] Open Questions captured (and mirrored from any [NEEDS CLARIFICATION]).
- [ ] STOP marker present.

Stage 1 MUST NOT contain:

- [ ] No User Story sections.
- [ ] No Given/When/Then scenarios.
- [ ] No FR-### / NFR-### catalogs.
- [ ] No Slice Candidates table.
- [ ] No constitution output.
- [ ] No per-slice /prompts:speckit.specify texts.
- [ ] No spec.md/plan.md/tasks.md content.

## Stage 2 Gate (after STOP is cleared)

- [ ] User Scenarios & Testing *(mandatory)* present; stories formatted as Spec Kit.
- [ ] Each story has ≥1 acceptance scenario (Given/When/Then).
- [ ] Requirements *(mandatory)*:
  - [ ] FR-### each references story/scenario and has verification.
  - [ ] NFR-### each has measurable target (or exception) + verification.
- [ ] Key Entities included if data exists.
- [ ] Success Criteria measurable (SC-###).
- [ ] Edge Cases captured (EC-###).
- [ ] Global Technical Context (Candidate) filled.
- [ ] Slice Candidates present:
  - [ ] key matches ^S[0-9]{2,3}$ :contentReference[oaicite:6]{index=6}
  - [ ] short_name matches kebab-case :contentReference[oaicite:7]{index=7}
  - [ ] dependencies and order set where needed
- [ ] Traceability complete (CAP ↔ Story ↔ FR/NFR ↔ Slice).

Stage 2 MUST NOT contain:

- [ ] No per-slice spec.md content.
- [ ] No per-slice plan.md/tasks.md content.
- [ ] No per-slice /prompts:speckit.specify input blocks.
- [ ] No Spec Kit numeric branch numbers (NNN-...).

## Drift Controls

- [ ] Headings match taxonomy (verbatim).
- [ ] Cross-cutting requirements centralized (no inconsistent duplication).
- [ ] Constitution path for slices-map is `.specify/memory/constitution.md`. :contentReference[oaicite:8]{index=8}
