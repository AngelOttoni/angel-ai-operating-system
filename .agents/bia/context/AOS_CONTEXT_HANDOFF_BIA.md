# AOS context handoff for Bia

**Date:** 2026-09-08
**Standing:** Operational context for review; not a normative specification or approval record.
**Evidence boundary:** Repository documents and file contents inspected for this handoff. Documented status is reported as written, not independently certified as current approval.

## Documented facts

### Objective and milestone

The Project Charter v2.0 defines a specification-driven methodology for designing, governing, and operating long-term Human–AI partnerships. The immediate objective is to transform the ABRS into a coherent operational specification while preserving behavioral identity and explicit governance (Charter, sections 1–8 and 10).

The root `README.md`, under Project Status, names the current milestone as **Sprint 1.0 — Alice Operational Specification (AOS v1.0)**. The Charter marks Phase 0 and Phase 0.5 completed and Phase 1.0 — Operational Engineering in progress. The README likewise lists AOS v1.0 as in progress. `docs/sprint_1_roles.md` defines the sprint process and acceptance criteria; it does not provide a chapter progress ledger or declare sprint completion.

### Governing and operational sources

Paths are relative to the repository root. Engineering documents follow the hierarchy established by ADR-002. Auxiliary documents and operational instructions guide the work without acquiring normative authority. The presence of a file in the repository does not establish approval of its current version.

| Source | Responsibility and documented status |
| --- | --- |
| `docs/project_charter_v2.0.md` | Project purpose, principles, governance, roadmap, and organization; Active, version 2.0. |
| `docs/architecture/aos-document-architecture-v1.0.md` | AOS macroarchitecture, chapter microarchitectures, and editorial rules; Approved, version 1.0. Organizes the specification without defining behavior. |
| `docs/adr/ADR-001-abrs-is-the-normative-specification.md` | Accepted decision establishing ABRS as normative and AOS as derived; requires traceability. |
| `docs/adr/ADR-002-project-documentation-hierarchy.md` | Accepted decision establishing artifact responsibilities and downward authority. |
| `docs/specifications/ABRS-v1.0.md` | Normative source for Alice's behavioral identity, requirement records, and structural validation cases. |
| `docs/specifications/AOS-v1.0.md` | Derived operational model; Document Control says Draft for consolidation. |
| `docs/sprint_1_roles.md` | Sprint 1.0 operational workflow, roles, acceptance criteria, and agent handoff contract. |

`AGENTS.md` governs Bia's repository work. The root `README.md` supplies an overview and milestone statement; it does not replace engineering documents. Workspace material does not replace these sources.

### Authority and roles

ADR-002 establishes: Project Charter → Architecture Documents → ADRs → ABRS → AOS → Operational Protocols → Behavioral Patterns → Templates. Higher applicable layers constrain lower ones. ADR-001 specifically establishes ABRS precedence over AOS; behavioral changes must originate in ABRS before propagation. Emergent properties have no independent behavioral authority.

Under `AGENTS.md` and the sprint roles document:

- **Angel — Chief Architect:** final authority over direction, architectural and structural decisions, document and version approval, and acceptance or rejection of deliverables.
- **Alice — Lead Systems Architect:** governs operational architecture, preserves ABRS fidelity, resolves architectural ambiguity, reviews consolidated chapters, and proposes structural decisions for Angel's approval.
- **Bia — Documentation Engineer:** governs documentary consolidation, integrates validated requirements, preserves terminology and editorial consistency, applies approved architecture, edits only within authorization, and escalates architectural questions. Bia cannot change behavior, make architectural decisions, or approve her own deliverables.

### Chapter workflow

1. Architectural Review by Alice.
2. Chapter Assignment by Angel.
3. Operational Consolidation by Bia.
4. Self Review by Bia.
5. Architectural Review by Alice.
6. Approval by Angel.
7. Git Commit, only with explicit authorization.

No stage advances before its predecessor is complete. Each approved chapter is a separate architectural commit unit. Alice supplies the objective, responsibility, constraints, risks, and validation criteria. Bia returns consolidated text, relevant editorial rationale, architectural questions, and decision points (`AGENTS.md`; `docs/sprint_1_roles.md`).

## Observed repository state

- The AOS contains chapters 1–15, from Introduction through References, plus Document Control and a Closing Note. Its explicit status remains Draft for consolidation. Chapter presence and a version number do not establish approval.
- Chapter 12 contains a chapter-to-ABRS matrix for chapters 1–11; chapter 13 lists eight emergent properties with derivation references. Their presence does not establish that full semantic traceability has been reviewed or accepted.
- The AOS follows the approved architecture's chapter sequence but lacks its five explicit part headings. Chapters 2 and 3 include Operational Implications beyond the Type A template. Chapter 9 uses Operational Model and Operational Implications instead of the Type C Governance Model and Operational Consequences. Chapter 11 adds Architectural Notes beyond the Type D template; chapter 12 contains prose beyond the Type E matrix-only structure. These are observed structural differences, not authorized corrections or findings of behavioral invalidity.
- The ABRS contains RQ-000 through RQ-056 and TC-001 through TC-004. RQ-051–RQ-056 and TC-001–TC-004 retain the literal status `Validado (proposto)`. RQ-016 appears in a different record format without an explicit status field. The Charter's completed Phase 0.5 statement does not resolve these record-level uncertainties for this handoff.
- The inspected sources do not establish which chapter has completed each sprint gate, chapter-specific approvals, or the next assigned chapter. No completion percentage or inferred approval is recorded here.

## Next work supported by the sources

The documented work is continued AOS consolidation within Sprint 1.0. The next specific chapter is not established by the inspected sources. Before chapter editing, Angel must identify or confirm the assignment and Alice's preceding architectural review must be available. Bia should then follow the documented workflow within that scope. This handoff does not select a chapter or advance a sprint gate.

## Decisions and restrictions requiring attention

- **Angel and Alice:** confirm the current chapter gate and next assignment; distinguish approval evidence supplied later from the draft status observed here.
- **Alice, with Angel's final authority:** assess the structural differences above and provide applicable chapter guidance before consolidation. Bia must not silently resolve them.
- **Angel and Alice:** clarify the ABRS validation markers and missing explicit RQ-016 status before treating affected material as demonstrably validated for consolidation. Bia must not normalize those statuses herself.
- **Alice, with Angel for structural decisions:** AOS section 1.2 inserts Project Instructions in its derivation diagram, while ADR-002 does not list that layer. This handoff retains ADR-002's hierarchy and does not decide the formal placement of Project Instructions.
- The sprint roles document mentions Alice approving structural changes while also reserving final authority to the Chief Architect. `AGENTS.md` explicitly assigns structural decisions to Angel and proposals to Alice. Do not treat Alice's review as Angel's final approval; escalate any request relying on a different approval boundary.

This handoff grants no authorization to change canonical documents, revise behavior, or perform Git operations. Workspace context remains subordinate to source documents and must be checked against them when work resumes.
