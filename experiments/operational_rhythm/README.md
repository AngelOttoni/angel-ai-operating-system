# Angel Operational Rhythm — Experimental Pilot

**Status:** Experimental
**Version:** 0.2
**Pilot duration:** 7 operational days

## Experimental direction — 2026-09-09

Angel and Alice decided to test Bia's practical usefulness as an end-to-end Daily Brief executor. The [capability/access diagnosis](../../.agents/bia/reports/operational-rhythm-capability-access-matrix.md) and the subsequent ClickUp capability gate provided sufficient evidence to attempt this experiment, not to establish complete coverage or cognitive quality. The gate, recorded in the experimental conversation, resolved multiple-workspace selection and verified bounded task discovery and reading without configuration changes.

The [paired A/B shadow protocol](daily-brief-ab-shadow-test-protocol-v0.1.md) and [Window 1 preparation](runs/2026-09-10/window-1-preparation.md) were prepared but are no longer the active experimental path. Parallel candidates, blind evaluation and blind packaging are suspended. The [blind-delivery dummy test](blind-delivery-dummy-test-2026-09-09.md) remained inconclusive; resolving that gap is not a prerequisite for the next step. These artifacts remain historical, non-normative evidence, with their original conclusions and statuses preserved.

The next step is one experimental Angel Daily Brief executed end-to-end by Bia, only after Angel's subsequent explicit execution authorization. Alice is not a mandatory stage of this experimental runtime. Angel will assess the result directly in use: **Is Bia's autonomously produced Brief sufficiently useful to orient Angel's attention and actions today?** Concrete execution failures will determine whether additional complexity is warranted. The working heuristic for this phase is to prefer the smallest sufficient solution that produces observable value and add structure only when a concrete failure justifies its cost; this is not a normative requirement or persistent policy.

This is a temporary, explicitly authorized experimental exception, not permanent architectural adoption. The existing contracts and canonical documents remain unchanged; the Daily Brief contract's Alice-specific executor wording is temporarily accepted under this exception. Bia may perform bounded cognitive synthesis without acquiring Alice's identity or normative authority, or Angel's final decision authority. Required collection, Angel Capture, visible collection limitations and existing safety/governance boundaries remain applicable; operational-source writes require separate explicit authorization. The sections below retain the existing contractual baseline and are not an instruction to restore the suspended A/B or blind-delivery path.

## 1. Purpose

The Angel Operational Rhythm experiment evaluates a lightweight operational architecture for integrating information distributed across Angel's work, study, personal organization, and Angel AI Operating System activities into a coherent daily orientation process.

The experiment is intended to determine whether the combination of sources accessible to Alice, Bia's on-demand technical observation, Angel's explicit input, and Alice's cognitive integration is sufficient to produce a useful daily operational briefing without introducing a new orchestration platform or custom operational application.

The experiment must validate the workflow before additional infrastructure is introduced.

## 2. Problem

Angel's operational context is distributed across multiple systems and environments.

Relevant information may exist in task management systems, calendars, email, documentation platforms, Git repositories, GitLab, local development environments, and project-specific artifacts.

No single source represents Angel's complete operational state.

Attempting to make any one of these systems the global source of truth would duplicate information and blur the responsibilities of the existing systems.

The experiment therefore tests an integration model in which existing systems retain their authority while a derived operational view supports daily attention and decision-making.

## 3. Hypothesis

A useful daily operational rhythm can be produced without initially building a dedicated Operational Hub.

The working hypothesis is:

> Sources accessible to Alice + on-demand technical observation by Bia + explicit input from Angel may already provide sufficient inputs for Alice to produce a useful integrated operational view.

Under this hypothesis:

* existing systems remain sources of truth for their respective domains;
* Bia observes technical and local operational state on-demand / condition-triggered within her authorized scope;
* Alice consults Google Calendar, Gmail, and ClickUp in every Brief execution and requests or consults a current Bia Operational Handoff when a concrete technical trigger applies;
* the mandatory Angel Capture Check obtains explicit input about relevant information outside sources accessible to Alice and Bia, including Google Keep and demands not recorded in any system;
* Alice integrates this information cognitively and produces the Angel Daily Brief;
* Angel retains final authority over priorities, decisions, and actions.

## 4. Experimental Architecture

```text
Sources accessible to Alice    Technical/local sources    Angel Capture
Calendar / Gmail / ClickUp     (authorized scope)         Outside accessible sources
+ applicable conditional                 |               or not recorded in systems
sources                                  v                         |
          |                   Bia (on-demand /                     |
          |                   condition-triggered)                 |
          |                              |                         |
          |                   Bia Operational Handoff              |
          |                       when applicable                  |
          +------------------------------+-------------------------+
                                         |
                                         v
                               Alice: collection complete
                                         |
                                   reconciliation
                                         |
                                 cognitive synthesis
                                         |
                                  Angel Daily Brief
                                         |
                                       Angel
```

This architecture separates collection, reconciliation, and cognitive synthesis. Angel Capture is an explicit experimental input surface, not an integration with inaccessible systems. Angel-provided information retains its provenance.

## 5. Responsibilities

### Angel

Angel is the final authority over objectives, priorities, decisions, and actions.

Angel supplies relevant outside-source information through the mandatory Angel Capture Check, or explicitly indicates that there is nothing to add. During the experiment, Angel also provides feedback about the usefulness, accuracy, relevance, and prioritization of the Daily Brief.

### Alice

Alice acts as the cognitive integration and judgment layer.

Alice:

* obtains relevant information from sources available to her;
* requests or consults a current Bia Operational Handoff when a concrete technical reason applies;
* performs the mandatory Angel Capture Check before reconciliation and synthesis;
* relates current operational state to relevant accumulated context;
* identifies conflicts of attention, risks, dependencies, and priorities;
* produces the Angel Daily Brief;
* does not replace the authoritative source systems.

### Bia

Bia acts as the local and technical operational observation layer.

Bia:

* observes sources within her authorized scope;
* identifies operationally relevant changes;
* reports information that may affect Angel's attention or actions;
* produces the Bia Operational Handoff according to its experimental contract;
* does not determine Angel's global priorities;
* does not replace Alice's cognitive role;
* does not create new authoritative operational state.

## 6. Source-of-Truth Principle

The experiment does not create a new global source of truth.

Existing systems retain authority within their respective domains.

The Bia Operational Handoff and Angel Daily Brief are derived artifacts.

They represent operational views of source information and explicit Angel input, with provenance, and must not compete with or silently redefine their source systems.

## 7. Experimental Contracts

### Bia Operational Handoff

The current contract is:

`bia-operational-handoff-v0.2.md`

`bia-daily-operational-handoff-v0.1.md` is retained as a historical contract.

Its purpose is to provide Alice with relevant technical and local operational state on-demand / condition-triggered, incrementally when comparison is reliable or as a baseline otherwise. Collection is proportional to the trigger; no exhaustive source sweep or daily handoff is required. Without a relevant technical trigger, absence of a current handoff is not a collection failure. If current technical state is materially needed but unavailable, Alice states the limitation. Previous handoffs are historical context only.

### Angel Daily Brief

The current contract is:

`angel-daily-brief-v0.3.md`

Its purpose is to transform relevant operational state, commitments, context, and dependencies into a concise cognitive orientation for Angel's day.

`angel-daily-brief-v0.2.md` and `angel-daily-brief-v0.1.md` are retained as historical contracts. Version 0.1 was used for the partial Pilot Day 1 execution. Prior execution records remain unchanged.

Every execution requires Google Calendar, Gmail, ClickUp, and the Angel Capture Check. The customizable experimental invocation phrase is defined in the current Daily Brief contract and initiates the full protocol.

## 8. Pilot Rules

During the initial pilot:

1. No new orchestration platform or custom Operational Hub will be introduced solely to support the experiment.
2. Existing systems remain authoritative for their respective information.
3. Bia reports operational state; Alice integrates and judges; Angel decides.
4. The process seeks relevance rather than exhaustive collection.
5. Information should be collected only when it can materially affect understanding, attention, decisions, or action.
6. Missing information, irrelevant information, incorrect prioritization, duplication, and access limitations are experimental evidence and should be recorded rather than immediately hidden through additional infrastructure.
7. Automation should not be introduced before the manual interaction contract is sufficiently understood.

## 9. Evaluation

The pilot should observe, at minimum:

* important information that was missing;
* information included but not useful;
* duplicated information;
* incorrect or weak prioritization;
* corrections required from Angel;
* sources that were unavailable or unreliable;
* information Alice repeatedly required but could not obtain;
* information collected by Bia that Alice repeatedly did not need;
* friction created by the handoff itself.

The purpose is not to benchmark Alice or Bia individually.

The purpose is to identify architectural gaps in the operational workflow.

## 10. Expected Architectural Decision

At the end of the pilot, the results should support an architectural review of whether:

* sources accessible to Alice, on-demand Bia observation, and explicit Angel input are sufficient;
* additional scheduling or time-planning tooling is justified;
* workflow orchestration such as n8n is justified;
* a dedicated Angel Operational Hub is justified;
* the handoff contract requires revision;
* the experiment is mature enough to inform a formal Operational Protocol.

No experimental artifact becomes normative solely because the pilot succeeds.

Promotion into the canonical AOS documentation hierarchy requires explicit architectural review and approval.
