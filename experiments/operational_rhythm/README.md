# Angel Operational Rhythm — Experimental Pilot

**Status:** Experimental
**Version:** 0.1
**Pilot duration:** 7 operational days

## 1. Purpose

The Angel Operational Rhythm experiment evaluates a lightweight operational architecture for integrating information distributed across Angel's work, study, personal organization, and Angel AI Operating System activities into a coherent daily orientation process.

The experiment is intended to determine whether the combination of existing information sources, Bia's local operational visibility, and Alice's cognitive integration is sufficient to produce a useful daily operational briefing without introducing a new orchestration platform or custom operational application.

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

> Alice + Bia + existing integrations may already constitute a sufficient operational integration architecture.

Under this hypothesis:

* existing systems remain sources of truth for their respective domains;
* Bia observes technical and local operational state that Alice cannot reliably observe directly;
* Alice obtains information from the sources available to her and receives Bia's operational handoff;
* Alice integrates this information cognitively and produces the Angel Daily Brief;
* Angel retains final authority over priorities, decisions, and actions.

## 4. Experimental Architecture

```text
Operational Sources
        |
        +--> Sources accessible to Alice
        |       |
        |       +--> Calendar
        |       +--> Email
        |       +--> task/document systems when applicable
        |       |
        |       +-----------------------+
        |                               |
        +--> Technical/local sources    |
                |                       |
                v                       |
               Bia                     |
                |                       |
                v                       |
       Daily Operational Handoff        |
                |                       |
                +-----------+-----------+
                            |
                            v
                          Alice
                            |
                  cognitive integration
                            |
                            v
                   Angel Daily Brief
                            |
                            v
                          Angel
```

This architecture deliberately separates operational observation from cognitive prioritization.

## 5. Responsibilities

### Angel

Angel is the final authority over objectives, priorities, decisions, and actions.

During the experiment, Angel also provides feedback about the usefulness, accuracy, relevance, and prioritization of the Daily Brief.

### Alice

Alice acts as the cognitive integration and judgment layer.

Alice:

* obtains relevant information from sources available to her;
* consumes Bia's Daily Operational Handoff;
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
* produces the Bia Daily Operational Handoff according to its experimental contract;
* does not determine Angel's global priorities;
* does not replace Alice's cognitive role;
* does not create new authoritative operational state.

## 6. Source-of-Truth Principle

The experiment does not create a new global source of truth.

Existing systems retain authority within their respective domains.

The Daily Operational Handoff and Angel Daily Brief are derived artifacts.

They represent operational views of authoritative information and must not compete with or silently redefine their source systems.

## 7. Experimental Contracts

### Bia Daily Operational Handoff

Defined in:

`bia-daily-operational-handoff-v0.1.md`

Its purpose is to provide Alice with an incremental and actionable representation of relevant technical and local operational state.

### Angel Daily Brief

Defined in:

`angel-daily-brief-v0.1.md`

Its purpose is to transform relevant operational state, commitments, context, and dependencies into a concise cognitive orientation for Angel's day.

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

* Alice + Bia + existing integrations are sufficient;
* additional scheduling or time-planning tooling is justified;
* workflow orchestration such as n8n is justified;
* a dedicated Angel Operational Hub is justified;
* the handoff contract requires revision;
* the experiment is mature enough to inform a formal Operational Protocol.

No experimental artifact becomes normative solely because the pilot succeeds.

Promotion into the canonical AOS documentation hierarchy requires explicit architectural review and approval.
