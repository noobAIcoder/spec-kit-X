# A. FRD Meta‑requirements

## A1. SoT governance

1. The FRD **MUST** be the single authoritative Source of Truth for:
   * product intent and scope,
   * global constraints and architecture direction,
   * user scenarios and measurable success criteria,
   * the authoritative list of requirements and slice candidates.

2. The FRD **MUST** include: version, status, owner, approvers, ratification date, change log.

3. The FRD **MUST** define precedence rules (e.g., Constitution > FRD > Slice Specs > Plans > Tasks).

4. The FRD **MUST** separate: **Requirements** vs **Assumptions** vs **Open Questions**.

## A2. Spec‑Kit taxonomy and structure

5. The FRD **MUST** use these **canonical headings** (verbatim) to reduce drift:
   * `User Scenarios & Testing *(mandatory)*`
   * `Requirements *(mandatory)*` with `Functional Requirements` and `Non‑Functional Requirements`
   * `Key Entities *(include if feature involves data)*`
   * `Success Criteria *(mandatory)*` with `Measurable Outcomes`
   * `Edge Cases`

6. The FRD **MUST** express user work as **User Stories** with priorities **P1/P2/P3** (matching Spec‑Kit templates).

7. The FRD **MUST** express behavior in **Acceptance Scenarios** (Given/When/Then).

8. Ambiguity **MUST** be recorded as `[NEEDS CLARIFICATION: …]` and also listed in an `Open Questions` section (so the marker is not lost).

## A3. Requirement identity and testability

9. Every requirement **MUST** have an ID and modality:
   * `FR-###` for functional requirements (`System MUST …`)
   * `NFR-###` for non-functional requirements (`System MUST …` + metric/threshold)
   * `C-###` for constraints (`System MUST …`)

10. Each `FR-###` **MUST** include:

* a rationale,
* at least one acceptance scenario (or an explicit reference to a user story scenario),
* verification guidance (what would constitute proof).

## A4. Slice‑candidate alignment (no fully specified slices)

11. The FRD **MUST** contain a **Slice Candidates** section, but it **MUST NOT** contain completed per-slice `spec.md` content.

12. Each slice candidate **MUST** include:

* `key` patterned like `S01`/`S001` (per schema), 
* a `short-name` that matches the kebab-case rule, 
* dependency keys (`depends_on`) and an execution order,
* references back to user stories and `FR-###/NFR-###`.

13. Each `FR-###` **MUST** map to ≥1 slice candidate key (or be explicitly marked “system-wide / cross-slice”).

## A5. Workflow constraints (your hard requirements)

14. The FRD **MUST** include global constraints for:

* **GitHub is mandatory** (repo + workflow; optionally product integration if applicable),
* **WSL-only execution** (bash-first; no required PowerShell),
* **monorepo** structure,
* shared DB/infra reality (single complex app vs multiple tools sharing DB/infra) as a decision or chosen direction.
