# Historical Architecture Recovery — Post-AOS

**Project:** Angel AI Operating System (AAIOS)  
**Status:** Working research artifact — non-normative  
**Date:** 2026-09-08  
**Purpose:** Preserve and classify architectural ideas, tips, solutions, experiments, and mechanisms that emerged throughout the AAIOS history so they are not lost during the post-AOS transition.

> This document is evidence for architectural investigation. It does **not** modify the Project Charter, ADRs, ABRS, AOS, or any other normative/approved artifact.

---

## 1. Classification model

Historical ideas are classified into exactly three groups:

### Superseded

The original idea, solution, structure, or assumption should no longer guide the current architecture in its original form.

A superseded item may still contain a useful underlying problem or mechanism. When that occurs, the useful part is recorded separately as `still relevant` or `candidate architectural concept`.

### Still relevant

The idea remains valid under the current AAIOS architecture and can continue guiding research, experiments, or operational practice without requiring a new architectural decision.

### Candidate architectural concept

The idea appears important enough to influence future AAIOS architecture, but it has **not** yet been accepted as part of the canonical architecture.

A candidate must be investigated, compared with the current authority hierarchy, tested when appropriate, and approved by Angel before formalization.

---

## 2. Evidence base

This recovery consolidates evidence from:

- AAIOS project conversations and historical discussions available in project context;
- Project Charter v1.0 and Project Charter v2.0;
- Sprint 0.5 and Sprint 1.0 history;
- ABRS v1.0 and AOS v1.0;
- ADR-001 and ADR-002;
- AOS Document Architecture v1.0;
- Notion pages under IA Automation and Angel AI Operating System;
- the historical `Multi-Agent Workflow`;
- Bia Local Deployment decisions and local repository practices;
- Git history of `AngelOttoni/angel-ai-operating-system`;
- Operational Rhythm experiment and its handoff/brief contracts;
- the tool/harness curation shared by Fabiano;
- `lucastamoios/skills` as a reference implementation for the Skill Ecosystems research track.

The purpose is not to treat every historical note as authority. Historical material is evidence. Current approved artifacts remain authoritative according to the documentation hierarchy.

---

## 3. Consolidated historical matrix

| Historical idea / mechanism | Classification | Current reading / destination |
|---|---|---|
| Notion as the single source of truth for the whole AAIOS | **Superseded** | Git is now canonical for normative engineering artifacts. Notion remains operational tracking, context, navigation, decisions, and handoff support. |
| ChatGPT Projects as daily operational memory | **Superseded** | Projects remain useful as contextual/historical containers, but should not be assumed to be the primary operational state layer. |
| Four permanent Alice chats: LICA Management, Project Management, Research, Executive Assistant | **Superseded** | Fragmenting Alice into separate identities no longer matches the consolidated ABRS/AOS model. The functional capability needs behind those chats remain important. |
| A generic prompt library as the core reusable layer | **Superseded** | Prompting is now downstream of specification and architecture. Prompts may be implementation artifacts, not architectural authorities. |
| Build automation first, then discover the operating model | **Superseded** | The project adopted specification before implementation and evidence-driven experimentation. |
| Centralize all operational state into a new hub by default | **Superseded** | Current experiments test whether derived views over existing authoritative sources are sufficient before introducing a dedicated hub. |
| `workspace-admin/` as a generic location for agent-generated reports and inventories | **Superseded** | The local convention evolved into `.agents/bia/{context,instructions,reports,work}` while canonical artifacts remain in normal repository locations. |
| Account memory as reliable source for machine-local state | **Superseded** | Machine-local facts require repository/system evidence and explicit inspection. |
| Full multi-agent architecture as an immediate post-AOS priority | **Superseded** | The current Angel–Alice–Bia model is interim. Full multi-agent concerns remain reserved for a later architectural phase. |
| Daily brief as simple concatenation of lists supplied by another agent | **Superseded** | The Operational Rhythm pilot showed the need for independent collection, reconciliation, prioritization, and synthesis. |
| Project Charter v1.0 Sprint 0.6 numbering | **Superseded** | The numbering changed under Charter v2.0, but the Knowledge Architecture problem persists. |
| “Angel AI Framework” as the immediate next sprint exactly as originally proposed | **Superseded** | The original implementation order was replaced by behavioral and operational specification work. Its capability idea remains a candidate. |
| Separate Decision Log for architectural decisions | **Superseded** | ADRs are the accepted mechanism for architectural decisions. Operational decisions may still require other traceable records. |
| Keep approved behavior separate from tools and implementation | **Still relevant** | This distinction is foundational to ABRS/AOS governance. |
| Project Instructions should be derived only after behavior and operational architecture are understood | **Still relevant** | The post-AOS investigation must determine their exact place and responsibility. |
| Research / discovery before architecture changes | **Still relevant** | Remains consistent with the AAIOS engineering method. |
| Reusable patterns should be explicitly recognized and formalized | **Still relevant** | Supports future Protocols, Behavioral Patterns, Templates, and potentially other reusable asset types. |
| Observe real work before automating it | **Still relevant** | Reappears directly in the Operational Rhythm experiment. |
| Do not migrate or duplicate everything into one system | **Still relevant** | Preserve authoritative sources and derive operational views when possible. |
| Use Git as a continuity mechanism for versioned artifacts | **Still relevant** | Important for canonical documents and Bia continuity across environments. |
| Angel remains the intentional orchestrator and final authority | **Still relevant** | Preserved in current workflow and governance. |
| Bia collects/inspects evidence; Alice analyzes/reviews; Angel decides; Bia consolidates/implements approved changes | **Still relevant** | Validated during Sprint 1.0 and evolved into a working engineering cycle. |
| Separate observation, decision, execution, and review | **Still relevant** | One of the strongest recurring governance patterns across the project. |
| Alice–Bia collaboration through explicit artifacts rather than assumed direct communication | **Still relevant** | Materialized through briefings, handoffs, Notion, Git, and local repository workspaces. |
| Structured handoffs with sender, recipient, minimum context, evidence, requested action, authority constraints, status, result, and next responsible | **Still relevant** | Current operational practice and potential input for future formal architecture. |
| Notion as an asynchronous handoff layer when Git is not appropriate | **Still relevant** | Useful under explicit source-of-truth and confidentiality boundaries. |
| Fast Track after calibration, without removing critical controls | **Still relevant** | Sprint 1.0 demonstrated that governance can become lighter after evidence of process stability. |
| Skills should be adopted on demand, not installed globally because they exist | **Still relevant** | Strong rule for the Skill Ecosystems research track. |
| Agent harness systems should be compared one at a time | **Still relevant** | Prevents uncontrolled architectural substitution and confounding. |
| Runtime integrations should be tested only when a concrete workflow needs them | **Still relevant** | Avoids premature infrastructure. |
| Local AI infrastructure should answer an actual privacy, latency, cost, reproducibility, sandbox, RAG, or network requirement | **Still relevant** | Infrastructure remains requirement-driven. |
| Compare external tooling with an equivalent mechanism implemented through native agent instructions where possible | **Still relevant** | Helps distinguish tool value from conceptual value. |
| Evaluate tools by quality, safety, maintainability, time, context cost, and operational burden—not promotional metrics alone | **Still relevant** | Important methodological rule for AAIOS experiments. |
| `lucastamoios/skills` as a reference implementation for atomic/reusable skills | **Still relevant** | Keep as a permanent Skill Ecosystems reference; observe patterns, do not copy blindly. |
| Operational Rhythm as evidence-generating pilot | **Still relevant** | It is experimental rather than canonical, but directly informs post-AOS architecture. |
| AOS should lead to reusable operational artifacts | **Still relevant** | Explicit in the current architecture, while exact intermediate layers remain unresolved. |
| Capability-oriented organization such as Research, Reviewer, PM, Tutor, Writer, Executive Assistant, Decision Support | **Candidate architectural concept** | Historical idea repeatedly aligned with real needs. Needs redefinition as capabilities rather than separate Alice identities. |
| Distinguish **Functional Capabilities** from **Enabling Capabilities** | **Candidate architectural concept** | Functional = what work an agent can perform; Enabling = mechanisms such as navigation, ingestion, retrieval, tools, execution, recovery. |
| A formal Capability Architecture layer | **Candidate architectural concept** | May be needed between operational specification and reusable execution artifacts, but is absent from the current Charter/ADR hierarchy. |
| Knowledge Architecture as more than a knowledge base | **Candidate architectural concept** | Candidate definition: architecture governing how operational knowledge is represented, located, derived, transferred, and transformed into execution. |
| Derived views rather than duplicated sources of truth | **Candidate architectural concept** | Strong candidate principle for Knowledge Architecture and Operational Rhythm. |
| Provenance for derived artifacts | **Candidate architectural concept** | Derived representations should identify source, transformation/tool version, date, limitations, sensitivity, and preferably immutable identifiers/hashes where applicable. |
| A formal lifecycle for derived representations | **Candidate architectural concept** | Example: original → reproducible transformation → derived representation → extraction/indexing/analysis. |
| Graph-based structural representation of code/docs without replacing canonical sources | **Candidate architectural concept** | Motivated by Graphify and directly relevant to context navigation and large-repository comprehension. |
| Explicitly distinguish extracted evidence from inferred relationships | **Candidate architectural concept** | General provenance/epistemic principle extending beyond Graphify. |
| Principle of Sufficiency / Economy of Change | **Candidate architectural concept** | Inspired by Ponytail: prefer the smallest sufficient intervention while remaining subordinate to correctness, security, requirements, and architecture. |
| Treat “do not implement” as a legitimate engineering option | **Candidate architectural concept** | A specific consequence of the sufficiency principle. |
| Formal Skill Architecture | **Candidate architectural concept** | Could define atomicity, scope, dependencies, orchestration, permissions, installation location, portability, and lifecycle. |
| Protocol for skill admission, testing, update, promotion, and retirement | **Candidate architectural concept** | Needed if skills become governed reusable capabilities. |
| Skill promotion from project-local to broader/global scope only after evidence | **Candidate architectural concept** | Supports controlled reuse and reversibility. |
| Small orchestrators composed from atomic skills | **Candidate architectural concept** | Candidate composition rule to avoid monolithic capabilities. |
| Agent Harness as a distinct architectural dimension | **Candidate architectural concept** | The AAIOS currently specifies behavior well, but must investigate the layer that supplies context, state, tools, permissions, execution, validation, and recovery. |
| Agent Engineering & Capability Enablement as a research domain | **Candidate architectural concept** | Proposed transversal research track across Harness Ops, Runtime Integrations, Harness Systems, Skill Ecosystems, and Local AI Infrastructure. |
| Landscape taxonomy: Harness Operations / Runtime Integrations / Harness Systems / Skill Ecosystems / Local AI Infrastructure | **Candidate architectural concept** | Strong taxonomy for structured landscape research and experimentation. |
| Technology evaluation lifecycle: concept → AAIOS gap → minimum experiment → adopt/adapt/observe/reject | **Candidate architectural concept** | Candidate research-to-architecture promotion mechanism. |
| Graphify as first Harness Ops experiment | **Candidate architectural concept** | Evaluate structural graph quality, update cost, context/time savings, provenance, stale-derived-file risk, normative-doc behavior, and data boundaries. |
| Ponytail as first Harness Ops experiment | **Candidate architectural concept** | Compare baseline agent, Ponytail light mode, and equivalent AAIOS-authored instructions. |
| MarkItDown as an ingestion layer, never canonical source | **Candidate architectural concept** | Potential first real-case Runtime Integration for documents, research, Office files, and RAG ingestion. |
| Harness comparison matrix | **Candidate architectural concept** | Problem solved, state model, session model, capability composition, permissions, recovery, observability, completion evidence, portability, cost, ABRS/AOS compatibility. |
| Operational knowledge handoff as a formal knowledge artifact type | **Candidate architectural concept** | Current structured handoffs may become a first-class artifact rather than merely a workflow convention. |
| Operational Brief as a derived operational view | **Candidate architectural concept** | The Daily Brief pilot suggests a reusable artifact type that synthesizes sources without becoming a new authoritative source. |
| Experiment → Evidence → Validated Practice → Candidate Protocol → Architectural Review → Approved Protocol | **Candidate architectural concept** | Candidate lifecycle for promoting operational experiments into canonical reusable assets. |
| Angel AI Operating Manual / Operational Framework | **Candidate architectural concept** | Historical intent remains useful but likely belongs to a later operational framework/reference layer, not immediate post-AOS work. |
| Organize executive work around decisions, risks, dependencies, and blockers rather than only projects/tasks | **Candidate architectural concept** | Could inform future executive views and operational prioritization without becoming the canonical project taxonomy. |
| Executive Control Center as an integration surface rather than a new source of truth | **Candidate architectural concept** | The original “single dashboard” solution is superseded, but a derived executive surface may still be valuable. |
| Delegate / Augment / Preserve classification for human–AI work | **Candidate architectural concept** | Delegate low-value operational work; augment work where AI accelerates Angel while preserving judgment/learning; preserve work Angel intentionally performs to retain/develop competence. |
| Delegation efficiency as a system outcome | **Candidate architectural concept** | Evaluate whether AAIOS reduces Angel’s operational/cognitive overhead while preserving authority, situational awareness, and learning. |
| Time recovered for high-value learning, MLOps/AI Architecture, technical practice, and public professional output | **Candidate architectural concept** | Candidate outcome measure for the AAIOS, not merely a personal side effect. |
| Multi-Agent Architecture concerns: agent identity/registration, responsibility boundaries, orchestration, agent-to-agent handoff, shared context/memory governance, conflict resolution, observability, least privilege, failure recovery, lifecycle/versioning | **Candidate architectural concept** | Preserve for the future multi-agent phase; do not prematurely formalize now. |

---

## 4. Recurring architectural lines

The historical matrix reveals several recurring lines that should guide the post-AOS investigation.

### 4.1 Identity and behavior

The project progressively moved from prompts and specialized chats toward a stable behavioral specification and derived operational architecture.

**Current implication:** downstream artifacts must not redefine ABRS/AOS behavior.

### 4.2 Knowledge and context flow

The persistent problem is not merely where information is stored. It is:

- where authoritative knowledge lives;
- how context is selected;
- how it is transferred;
- how derived representations are created;
- how provenance is preserved;
- how outdated derived artifacts are detected;
- how the right actor receives the minimum sufficient context.

### 4.3 Operationalization

The project repeatedly seeks a governed bridge from specification to execution.

Open concepts include:

- Project Instructions;
- handoff contracts;
- protocols;
- patterns;
- templates;
- operational briefs;
- experiment promotion rules.

### 4.4 Capability architecture

Historical “roles” such as Research, Reviewer, PM, Tutor, Writer, Executive Assistant, and Decision Support are better interpreted as potential functional capabilities.

A second capability class is now visible through Bia and the tool landscape:

- repository navigation;
- structural context;
- document ingestion;
- context retrieval;
- skill execution;
- tool access;
- state recovery;
- sandboxing;
- validation/completion evidence.

The relationship between **Functional Capabilities** and **Enabling Capabilities** is unresolved.

### 4.5 Human–AI delegation

The AAIOS exists to increase Angel’s effective capacity, not to maximize automation.

A candidate classification is:

```text
Delegate
  Work that does not need to remain cognitively owned by Angel.

Augment
  Work where AI should accelerate Angel while preserving understanding,
  judgment, learning, and authority.

Preserve
  Work Angel intentionally performs herself to maintain or develop competence.
```

### 4.6 Agent engineering and harnesses

The emergence of Bia as a daily tool makes the agent runtime environment an immediate source of architectural evidence.

Proposed research taxonomy:

```text
Agent Engineering Landscape
├── Harness Operations
│   ├── structural context
│   ├── complexity control
│   └── validation / completion evidence
├── Runtime Integrations
│   ├── ingestion
│   ├── transformation
│   └── tool bridges
├── Harness Systems
│   ├── state
│   ├── sessions
│   ├── permissions
│   ├── observability
│   └── recovery
├── Skill Ecosystems
│   ├── atomic skills
│   ├── dependencies
│   ├── composition
│   └── lifecycle
└── Local AI Infrastructure
    ├── privacy
    ├── RAG
    ├── sandbox
    ├── reproducibility
    └── local execution constraints
```

### 4.7 Evidence-driven evolution

The AAIOS has repeatedly improved when architecture and experiments meet.

Candidate promotion lifecycle:

```text
Idea
  ↓
Experiment
  ↓
Evidence
  ↓
Validated Practice
  ↓
Candidate Architectural Concept / Candidate Protocol
  ↓
Architectural Review
  ↓
Angel Approval
  ↓
Canonical Artifact
  ↓
Operational Use
  ↓
New Evidence
```

---

## 5. External reference set to preserve

### Fabiano's curated landscape

Maintain the following categories as a research taxonomy, not an installation queue:

1. `agent-harness-ops`
   - priority experiments: Graphify, Ponytail;
2. `agent-runtime-integrations`
   - use when a real workflow requires integration;
   - MarkItDown as first strong document-ingestion candidate;
3. `agent-harness-systems`
   - compare one system at a time with the current AAIOS/Bia harness;
4. `agent-skill-library`
   - adopt on demand;
5. `local-ai-infrastructure`
   - evaluate only against concrete requirements.

For each external mechanism, produce:

1. reusable concept;
2. corresponding AAIOS gap;
3. minimum experiment;
4. decision: `adopt`, `adapt`, `observe`, or `reject`.

### `lucastamoios/skills`

**Reference role:** Skill Ecosystems reference implementation.

Use it to study:

- skill atomicity;
- instruction structure;
- scope boundaries;
- dependencies;
- composition/orchestration;
- discoverability;
- project-local versus global reuse;
- reversibility;
- maintainability;
- conventions that may generalize.

Do not treat the repository as a package set to install wholesale.

---

## 6. Unresolved architectural questions

The next investigation should answer at least:

1. What exactly does **Knowledge Architecture** mean in AAIOS?
2. Does Phase 2 remain correctly named and bounded?
3. Where do **Project Instructions** belong in the authority and artifact hierarchy?
4. Does AAIOS need a formal **Capability Architecture**?
5. If yes, how do Functional and Enabling Capabilities relate?
6. Is **Agent Harness** part of Knowledge Architecture, a transversal architecture, or a later phase?
7. What constitutes an authoritative source versus a derived operational view?
8. What provenance metadata is mandatory for derived artifacts?
9. How should handoffs, briefs, graphs, converted documents, and indexes be classified?
10. What lifecycle promotes an experiment into a canonical protocol, pattern, template, skill, or architecture mechanism?
11. What makes a skill project-local, agent-local, or global?
12. What is the governance model for skill admission, update, and retirement?
13. How should AAIOS evaluate whether a new tool is actually better than native capabilities plus project instructions?
14. Which work should be Delegate, Augment, or Preserve?
15. How should recovered time and reduced operational overhead be measured without encouraging harmful over-automation?
16. Which concerns must remain explicitly reserved for the future Multi-Agent Architecture?

---

## 7. Recommended next step

Do **not** modify the Project Charter yet.

Run a formal **Post-AOS Architectural Discovery / Phase Transition Review** with this historical matrix as evidence.

### Investigation objective

Determine whether the next formal AAIOS phase should remain **Phase 2 — Knowledge Architecture**, and if so, define its exact problem, boundaries, artifacts, interfaces, and acceptance criteria.

### Investigation workstreams

1. **Historical concept validation**
   - confirm classifications;
   - identify missing historical evidence;
   - trace concepts that already matured into approved artifacts.

2. **Artifact responsibility analysis**
   - ABRS;
   - AOS;
   - Project Instructions;
   - Knowledge Artifacts;
   - Handoffs;
   - Protocols;
   - Patterns;
   - Templates;
   - Skills;
   - Harness artifacts;
   - experimental evidence.

3. **Knowledge and context architecture**
   - sources of truth;
   - context selection;
   - provenance;
   - derived representations;
   - memory;
   - handoffs;
   - stale-state management.

4. **Capability and agent-engineering analysis**
   - Functional Capabilities;
   - Enabling Capabilities;
   - harnesses;
   - skills;
   - runtime integrations.

5. **Promotion lifecycle**
   - experiment to validated practice;
   - validated practice to candidate architecture/protocol;
   - review and approval;
   - versioning and retirement.

6. **Roadmap decision**
   - retain Phase 2 as currently named;
   - retain but redefine/rename;
   - restructure the post-AOS roadmap.

### Definition of Done

The Phase Transition Review is complete when:

- the historical matrix has been reviewed and accepted as sufficiently complete;
- Knowledge Architecture has an explicit definition;
- Project Instructions have a resolved place;
- the boundary between Knowledge Architecture, Capabilities, Protocols, Skills, Harnesses, and Multi-Agent Architecture is explicit;
- source-of-truth and derived-artifact rules are defined;
- the experiment-to-canonical promotion lifecycle is defined;
- the role of Bia as current operational evidence is incorporated;
- the external agent-engineering landscape has a governed research method;
- the roadmap decision is explicit;
- Angel approves the decision before any Charter or ADR modification.

---

## 8. Governance note

No item classified as `candidate architectural concept` becomes architecture by appearing in this document.

Promotion requires evidence, architectural analysis, compatibility with existing authority, explicit decision, and Angel approval.
