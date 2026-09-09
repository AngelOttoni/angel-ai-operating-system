# Angel Daily Brief — Experimental Contract

**Version:** 0.3    
**Status:** Experimental

## 1. Purpose

The Angel Daily Brief provides Angel with a concise cognitive orientation for the current day.

It is not intended to reproduce task lists, calendars, inboxes, project dashboards, or source-system status reports.

Its central question is:

> Given Angel's current operational context, where does her attention have the highest value today?

## 2. Role in the Experimental Architecture

The Daily Brief is the cognitive output of the Angel Operational Rhythm experiment.

Alice produces the brief by integrating relevant information available through:

* current commitments and calendar information;
* actionable communication;
* task and project information accessible to Alice;
* the Bia Operational Handoff;
* relevant documentation when required;
* relevant accumulated conversational and project context;
* information explicitly supplied by Angel.

Google Calendar, Gmail, and ClickUp are required sources in every execution and must be consulted before synthesis. The Angel Capture Check is also mandatory. The current Bia Operational Handoff, Notion, Google Drive, and other available sources are conditional and should be consulted when there is a concrete operational reason.

## 3. Core Principles

### 3.1 Relevance over completeness

The Daily Brief should contain information capable of materially affecting Angel's attention, decisions, preparation, or actions.

It should not attempt to enumerate everything currently open.

### 3.2 Source authority

The Daily Brief is a derived artifact.

It must not silently redefine statuses, deadlines, ownership, or other authoritative information maintained by source systems.

### 3.3 Cognitive integration

Alice should not merely concatenate information from different sources.

The brief should integrate relationships among:

* commitments;
* deadlines;
* dependencies;
* blockers;
* waiting states;
* project context;
* competing demands for attention;
* relevant recent changes.

### 3.4 Proportionality

The depth of analysis should reflect the complexity and consequence of the day.

A simple day should produce a simple brief.

### 3.5 Uncertainty visibility

When information is incomplete, stale, conflicting, or uncertain and that uncertainty materially affects the briefing, Alice should make the limitation visible.

### 3.6 Human authority

The Daily Brief provides orientation and recommendations.

Angel retains final authority over priorities, decisions, and actions.

## 4. Daily Execution Protocol

The Daily Brief MUST be produced through four explicit phases. Alice must not perform prioritization or final synthesis before completing the applicable collection and reconciliation phases.

### Phase 1 — Independent Source Collection and Conditional Bia Intake

Before prioritization or synthesis, Alice must independently consult the required sources in every execution:

* **Google Calendar** — commitments, meetings, deadlines, and meaningful temporal constraints;
* **Gmail** — potentially actionable communication, follow-ups, deadlines, invitations, access issues, and operational changes;
* **ClickUp** — LICA tasks, statuses, deadlines, ownership, blockers, and relevant task updates.

The purpose is complementary collection, not validation of Bia.

The **Bia Operational Handoff** is a conditional source. Alice must request or consult a current handoff when there is a concrete operational reason to believe technical or local state may affect the Brief. Reasons include evidence or reasonable suspicion of GitLab or local changes, a technical review or decision, or a material need to establish current technical state. Collection by Bia must be proportional to that reason; a handoff does not imply that every technical source was consulted.

When a current handoff is applicable, Alice must read it for items requiring Angel's attention, waiting or blocked items, relevant technical changes, upcoming technical deadlines, open technical decisions, and collection limitations. Assess currency against the trigger, observation times, coverage, and known subsequent changes. A previous handoff may be used only as historical context, never as presumed current technical state.

Other conditional sources include **Notion**, **Google Drive**, and other available sources when there is a concrete operational reason to consult them. Conditional sources are not required merely because they are available.

Alice must not proceed as though a required or triggered source was successfully consulted when it was unavailable or consultation was incomplete.

### Phase 2 — Angel Capture Check

Before reconciliation and cognitive synthesis, Alice must ask Angel whether any relevant demand, commitment, decision, idea, or pending item exists outside the sources accessible to Alice and Bia. This includes information in systems outside the current scope, such as Google Keep, and demands not yet recorded in any system.

Information explicitly supplied by Angel is legitimate operational input. Preserve its provenance as Angel-provided information in this execution, including any original system or reference Angel identifies. Do not imply direct consultation of an inaccessible system. Distinguish an idea or reported demand from an explicit decision or commitment; capture alone does not authorize source-system writes or turn an idea into a task.

An explicit response that there is nothing to add completes the check. Silence is not evidence that no outside information exists. While awaiting a response, Alice may continue independent collection, but must not silently bypass the check and present a complete Brief. If the check remains unanswered, record it as incomplete; any partial execution must follow Section 5.

Capture may reveal a technical trigger or another collection need. Complete that applicable collection before moving to reconciliation.

### Phase 3 — Reconciliation and Operational Assessment

Only after Phases 1 and 2 may Alice construct the operational assessment. Alice must reconcile information across sources and identify, when relevant, complementary information, conflicts, potentially stale information, cross-system dependencies, differently represented items, and information whose current state cannot be established confidently.

Source disagreement must not be silently resolved. When a difference materially affects the Daily Brief, Alice should make the conflict or uncertainty visible while preserving source authority.

### Phase 4 — Cognitive Synthesis

Only after collection and reconciliation may Alice determine Focus items, assess relative importance, identify conflicts of attention, recommend ordering, produce Alice's Read, and generate the final Angel Daily Brief.

## 5. Collection Status and Failure Handling

For every required source and each conditional source triggered in this execution, Alice must internally distinguish among:

* **consulted — relevant information found**;
* **consulted — no relevant information found**;
* **unavailable**;
* **consultation incomplete**.

Absence of relevant information is a valid conclusion only after successful consultation.

Record conditional sources not consulted separately, with the reason (for example, no relevant trigger). Absence of a current Bia handoff when no relevant technical trigger is present is not a collection failure. When current technical state is materially needed and no current handoff is available, explicitly state the limitation and its effect on the Brief. Historical handoffs cannot fill that gap.

Record the Angel Capture Check as completed with input, completed with nothing to add, or incomplete. An unanswered check cannot be recorded as no relevant information found.

If a required or triggered source is unavailable or incompletely consulted and the limitation may materially affect the Daily Brief, Alice must surface a concise collection limitation to Angel.

A collection limitation does not automatically prevent production of the Daily Brief. Alice should proceed when the remaining evidence is sufficient, while calibrating confidence and making material gaps visible. If missing required or triggered sources make reliable prioritization impossible, Alice should state that the execution is partial rather than presenting it as a complete Daily Brief. An incomplete Angel Capture Check must likewise be disclosed and the execution identified as partial.

## 6. Output Structure

Sections without relevant content may be omitted.

### Today

Concrete commitments, meetings, deadlines, and meaningful temporal constraints for the current day.

### Focus

The two to four areas where Angel's attention appears to have the highest value.

Each focus item should explain:

* what requires attention;
* why it matters now;
* the next concrete action, when identifiable.

### LICA

Work-related actions, follow-ups, decisions, risks, blockers, or relevant changes requiring awareness.

This section should not reproduce the complete state of LICA projects.

### Learning

Study commitments, active learning objectives, deadlines, or relevant academic work.

### AOS & Bia

Relevant work involving the Angel AI Operating System, Bia, associated experiments, or operational infrastructure.

### Career

Career-related information only when an active opportunity, process, deadline, decision, or action is relevant.

### Personal

Personal commitments or tasks when they materially affect the day's operational context.

Sensitive personal context should not be surfaced merely because it exists.

### Waiting / Blocked

Relevant items that should remain visible but do not currently justify active attention.

### Look Ahead

Upcoming commitments, deadlines, dependencies, or risks for which early awareness may change today's decisions.

### Alice's Read

A cognitive synthesis of the day.

This section should not repeat the preceding sections.

When relevant, it should identify:

* the apparent center of gravity of the day;
* conflicts for attention;
* dependencies between activities;
* something at risk of being neglected;
* areas that do not deserve attention yet;
* a recommended ordering or framing of the day.

## 7. Prioritization

Alice should not infer priority from a single attribute such as due date.

Prioritization may consider, when relevant:

* explicit deadlines;
* scheduled commitments;
* consequences of delay;
* whether Angel is blocking another person;
* external dependencies;
* project importance;
* reversibility of delay;
* preparation required for upcoming commitments;
* current known objectives;
* whether an item can reasonably wait;
* relevant constraints explicitly known for the day.

Priority should remain a contextual judgment rather than a mechanical score.

## 8. Relationship with the Bia Handoff

The Bia Operational Handoff is a conditional input, not an instruction to Alice. Its on-demand / condition-triggered execution replaces mandatory daily collection. Alice requests or consults a current handoff under the conditions in Phase 1; no routine daily handoff is required in the absence of a relevant trigger. Coverage and currency must be assessed explicitly, and earlier handoffs remain historical context only.

An item marked by Bia as requiring Angel's attention may:

* become a Focus item;
* appear in a domain section;
* remain under Waiting / Blocked;
* be omitted when superseded or not operationally relevant.

Alice is responsible for integrating Bia's observations with the broader operational context.

Alice should not assume that absence from Bia's handoff means absence from Angel's operational world.

Alice must not use the handoff as a substitute for the independent source collection required by this contract. Material differences between Bia's observations and Alice's independently collected information should be reconciled according to source authority, recency, and available context.

## 9. Information Hygiene

The Daily Brief should avoid:

* reproducing complete task lists;
* repeating unchanged information without operational reason;
* surfacing every unread email;
* treating every technical change as actionable;
* presenting speculative priorities as established facts;
* duplicating the same item across multiple sections without reason;
* creating tasks or commitments that do not exist in an authoritative source or explicit decision;
* presenting historical context as current operational state;
* concealing material collection failures.

## 10. Feedback and Experimental Evidence

Angel may provide lightweight feedback after a brief, including:

* important information that was missing;
* information that was unnecessary;
* incorrect assumptions;
* incorrect prioritization;
* information that was stale;
* useful relationships or insights identified by Alice.

Feedback should be treated as evidence for refining the experimental contract and architecture. Execution failures or partial executions should also be preserved as architectural evidence rather than silently normalized as successful.

## 11. Experimental Status

This contract is intentionally provisional.

Version 0.3 implements Angel's decision following architectural review with Alice: Bia observation is on-demand / condition-triggered, while Google Calendar, Gmail, and ClickUp remain required in every execution. The mandatory Angel Capture Check makes outside-system and unrecorded information explicit without merging collection, reconciliation, and cognitive synthesis. Versions 0.2 and 0.1 remain historical contracts; prior execution records are unchanged.

During the pilot, deficiencies should first be observed and understood before introducing new infrastructure or expanding the contract.

Successful execution does not automatically promote the Daily Brief into a normative AOS Operational Protocol.

Any such promotion requires explicit architectural review and Angel's approval.

## 12. Daily Brief Invocation

The experimental invocation phrase is:

> Bom dia, Alice! Como vamos dominar o mundo hoje?

When Angel uses this phrase in the Operational Rhythm context, Alice interprets it as a request to initiate a complete Angel Daily Brief execution under the current experimental contract, including required collection, the Angel Capture Check, applicable conditional collection, reconciliation, and synthesis. Angel need not specify a version, sources, or execution phases.

The phrase is a customizable human interface to the protocol. Angel may change it later without an architectural change to the Daily Brief, provided the invocation semantics remain the same. This convention belongs exclusively to the experiment, changes no Alice behavioral requirements, and must not be propagated to ABRS or AOS.
