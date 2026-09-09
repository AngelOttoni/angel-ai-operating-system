# Daily Brief — Paired Shadow Test Protocol

**Version:** 0.1

**Status:** Proposed / Experimental / Non-normative

**Prepared:** 2026-09-09

This proposal does not authorize execution or replace the current Daily Brief contract. Architectural Review by Alice and explicit approval by Angel are required before the first window.

## 1. Purpose

Compare two prospective daily executions of Candidate A (Alice, current workflow) and Candidate B (Bia, experimental end-to-end workflow). Establish the rules before observing outcomes; identify feasibility, failures, and coordination costs without selecting a permanent architecture.

Baseline resolved from [README](README.md): experiment v0.2, Experimental, seven operational days; current [Daily Brief v0.3](angel-daily-brief-v0.3.md) and [Bia Operational Handoff v0.2](bia-operational-handoff-v0.2.md). Preparation reference: Git `abccead`.

Evidence consulted: [capability/access matrix](../../.agents/bia/reports/operational-rhythm-capability-access-matrix.md), [partial Day 1 record](runs/2026-09-08/daily-brief-execution.md), and the ClickUp gate recorded in the preparation conversation. The gate discovered two workspaces, retrieved eight Tamboril tasks and one task's details. Angel reports Alice's classification: **PASS — proceed to paired shadow experiment preparation**. This later evidence supersedes the matrix's unverified ClickUp access for that bounded scope, not its historical record. It does not certify all ClickUp coverage or cognitive quality. The inspected runs directory contains only the Day 1 record; conversation evidence is not represented as an existing repository run.

## 2. Hypotheses and Questions

H2: a single contract-driven execution agent may produce the Daily Brief more reliably and with less human coordination cost than the split workflow.

| Question | Evidence assessed separately |
| --- | --- |
| Q1 — Collection | Can Bia retrieve sufficient operational state without Angel transporting operational information? Assess coverage, discovery, freshness, failures and collection-related interventions. |
| Q2 — Cognition | Given comparable material state, can Bia provide sufficiently useful daily orientation? Assess the blind rubric, then audit whether inputs were actually comparable. |
| Q3 — End-to-end | Can Bia collect, reconcile and synthesize in one workflow with less coordination and no material loss of coverage, contract fidelity or quality? Requires Q1 and Q2 evidence plus whole-run costs and phase compliance. |

A successful read does not establish Q1 sufficiency; Q1 does not establish Q2; a good output alone does not establish Q3. Mark each question supported, not supported, or inconclusive per window, with reasons.

## 3. Governance and Authority

Candidate A remains the operational reference. B is a shadow exception solely for the approved windows and the bounds in §9. No Alice identity, normative authority, Angel decision authority, or power to change contracts is transferred to Bia.

Authority follows repository `AGENTS.md`, the Project Charter, ADR-001/ADR-002 and ABRS precedence over derived AOS. ABRS RQ-008, RQ-014–RQ-016 and RQ-048–RQ-050, and AOS chapters 9–10, inform human authority and governance boundaries; they are not imported as a new Bia identity. This proposal changes none of those documents.

Only approved experimental records may be written to agreed destinations during future execution. No operational source writes, configuration/permission changes, credential changes, Git synchronization, commit or push are part of this test. Stop at any need for additional authorization. Architecture C and the separate H3 runtime-identity investigation are excluded.

## 4. Experimental Design

Use two new operational days after 09/09/2026. Do not replay that date as Candidate B: Bia has already seen its evidence and conclusions. Seek one naturally occurring technical-trigger day and one without a trigger; record absent diversity rather than fabricating events or silently adding windows.

Before each window, complete a short shared window header:

| Field | Rule |
| --- | --- |
| Baseline | Resolve README again; record contract filenames and Git reference. If changed since approval or between windows, pause for review rather than silently mix baselines. |
| Time | Fix operational date, timezone, collection start, common collection cutoff, output-freeze deadline, and source horizons before collection. Default: calendar today through the following seven days; Gmail preceding seven days; tasks open/waiting/overdue plus upcoming items in that horizon. Older evidence is conditional on a concrete reference or dependency. |
| Scope | Shared logical account/calendar/workspace/project inventory, inclusion/exclusion reasons, source-query boundaries and known objectives. Operational IDs are resolved at runtime, not embedded here. |
| Context | Same factual context packet, without previous Brief rankings or intermediate candidate analysis. Each candidate declares additional historical context used; historical facts require currency checks. |
| Logistics | Separate execution contexts, output destinations, single Capture delivery route, freeze deadline and blind packaging route validated before starting. Identify any human transport required and count it. |

Both candidates independently apply §5 to the same logical scope. A scope gap in one runtime is evidence, not grounds to reduce the shared scope to the weaker candidate. Ambiguous source membership is settled factually before collection, or the ambiguity remains explicit. A newly discovered material source is recorded as a scope difference; no candidate's intermediate findings are sent to the other to repair equality.

Run within the same collection interval, preferably concurrently where already authorized isolation permits. If sequential, A collects first in window 1 and B first in window 2. Do not delay real needs for the test. The cutoff is the end of permitted evidence intake, including Capture; it is not a promise of historical snapshot support. Record each observation time and source update time. Post-cutoff changes are excluded from the frozen candidate; if materially urgent, stop the comparison and address the real need separately.

Before its own output is frozen, neither candidate may inspect the other's Brief, priorities, intermediate analysis or candidate logs. A technical handoff supporting A is produced in a separate collection context from Candidate B and carries observations, not B's analysis. B collects its technical state independently. Shared instructions and identical Capture are allowed; sharing candidate reasoning is not. If isolation cannot be maintained, do not claim an independent pair.

## 5. Source Discovery Rules

For each required source (Calendar, Gmail, ClickUp) and triggered conditional source: discover available containers through actual responses, resolve relevant containers, query the declared bounds, follow all pagination in those bounds, read material items beyond snippets, and log outcomes. Availability of a tool is not successful consultation. Use the same relevance rules for both candidates, not necessarily identical connector syntax.

**Calendar.** Enumerate accessible calendars and complete list pagination; primary alone is insufficient. Include calendars representing Angel's work, learning, personal commitments or explicit time blocks, including relevant secondary and shared calendars. Inspect descriptions/context to establish scope. Institutional, Classroom and holiday calendars contribute only applicable deadlines, closures or constraints; do not treat every institutional event as Angel's commitment. Record excluded calendars and reasons; unclear material applicability requires clarification, not silent exclusion. Query each included calendar with explicit time bounds/timezone and complete event pagination. Preserve source calendar and event/occurrence references in the authorized runtime evidence. Collapse only demonstrably identical records, such as repeated pages of the same provider event occurrence; retain aliases/provenance. Similar titles across calendars are possible duplicates, not proof of identity. Preserve recurring-instance dates, exceptions and cancellation state when available; disclose unsupported recurrence semantics. Absence from primary never establishes absence of a commitment.

**Gmail.** Enumerate available connections/accounts from the runtime and map them to the logical scope. Query each relevant account through cutoff, completing pagination for the declared window and search. Assess communications about decisions, deadlines, follow-ups, access, invitations and changes; unread or important labels alone do not establish relevance. Inspect message/thread content when material; attachments only when needed. Do not blanket-exclude a category that may contain operational notifications. Consult older linked threads when necessary and record the extension. Email notifications do not supersede current task state without reconciliation. Account failure is a source gap, not an empty mailbox.

**ClickUp.** Discover all accessible workspaces through a listing or the full explanatory response requesting explicit selection. Inspect hierarchy and map operational projects/lists; names such as “LICA Space” do not establish global coverage. Use only workspace/list/task IDs returned by the surface. Complete hierarchy pagination, then query the relevant project/list scope, including undated open, waiting and overdue tasks rather than only near-term due dates; read material task details. Absence in one workspace says nothing about the others. Preserve both structured errors and explanatory text, redacting secrets or unnecessary identifiers in persisted records. The gate's error was workspace ambiguity, resolved by explicit request parameters, not a configuration change. Empty successful results and errors remain distinct.

**Conditional sources.** Notion, Drive and other documentation are queried only for concrete demands, dependencies or unresolved context; discover the relevant container and fetch current content/metadata, recording plan restrictions, truncation and pagination. Resolve contracts from Git, not an old Drive copy. Technical triggers require current local/GitLab observation through authorized routes; use GitLab API for remote metadata and local Git for checkout state. A root's existence or old handoff is not current technical evidence. A uses the current handoff contract; B records equivalent technical provenance directly. Keep, Element or inaccessible official systems are covered by Capture only when supplied by Angel, without implying direct consultation. No exhaustive source sweep is required.

## 6. Angel Capture

One Capture episode per window: Alice asks Angel whether relevant demands, commitments, ideas, decisions or pending items exist outside accessible sources, including Keep, Element, conversations and unrecorded knowledge. The exact response and its timestamp reach both candidates through the predeclared route before reconciliation. This shared-input arrangement is an explicit trial convention; B does not ask a duplicate daily Capture.

An explicit “nothing to add” completes Capture; silence does not. Preserve Angel provenance and distinguish idea, demand and decision. Do not reuse another day's answer. Factual clarifications within this episode are appended identically for both, before cutoff. Capture may trigger additional collection under §5. If it arrives too late to complete collection, record the run as incomplete; do not move cutoff after seeing the results. The response is legitimate input; the effort to relay it to a second candidate is separately recorded as trial logistics.

## 7. Candidate A Execution

Alice resolves the baseline and follows its four phases: independent required-source collection and conditional handoff intake → shared Capture and any resulting collection → reconciliation → cognitive synthesis. The handoff never substitutes for Calendar, Gmail or ClickUp. No technical trigger means no obligatory handoff.

Freeze the original output with time and reference, including limitations and contract sections. It remains attributable to Alice in the sealed run record. A is the current workflow under equal trial discovery rules, not a deliberately unimproved control. Do not attribute discovery improvements common to both to executor superiority.

## 8. Candidate B Execution

Bia independently resolves the same baseline, collects required and triggered sources, receives the shared Capture, reconciles, and only then performs §9 synthesis. This is an explicit experimental substitution of executor and direct technical intake, not a claim of literal compliance with the contract's Alice-specific role assignment.

Freeze the original output as Bia's experimental candidate. Do not obtain Alice's judgment during production or use A's handoff as B's collection. No live Brief is generated as part of preparing this protocol.

## 9. Bounded Cognitive Synthesis

B may relate commitments, dependencies, conflicts, consequences and explicitly known objectives; recommend priorities and ordering; explain attention value and next steps; and preserve uncertainty. Use the contract's contextual prioritization criteria, never deadline or recency alone.

B may not invent commitments, redefine Angel's goals, write to sources, execute external actions, conceal collection failures, treat historical information as current without evidence, speak as Alice, or change documentary/normative authority. Recommendations do not become decisions. Use **Daily Synthesis** for B's equivalent of “Alice's Read.” Authorship is retained in the original run metadata.

## 10. Blind Evaluation

After both outputs freeze, Bia may act solely as mechanical packaging custodian, provided this role and a route that withholds the mapping from Angel are approved before the window. This is post-freeze handling, not delegated cognition. Randomize the A/B-to-1/2 assignment independently per window, save the mapping separately, and present only **Candidate 1** and **Candidate 2** to Angel initially.

Preserve originals. In evaluation copies, normalize the heading “Alice's Read” to “Daily Synthesis” for A too, remove executor signatures and identifying file labels, and replace explicit self-identification with “the executor.” Apply only these mechanical substitutions; retain substantive limitations, provenance distinctions, reasoning, wording and ordering. Keep a substitution log. Do not suppress a failure because it might reveal the executor. No polishing, rewriting or summarizing is allowed.

Angel scores before mapping revelation and before seeing collection logs. Record an optional authorship guess/confidence to detect compromised blinding. After ratings are locked: reveal mapping, compare provenance/collection, then conduct Alice's Architectural Review. Packaging or prior exposure that reveals authorship makes the rating non-blind and is recorded, never relabeled successful blinding.

Use 0 = inadequate/material defect, 1 = usable with correction, 2 = sufficient, and N/A where genuinely inapplicable; add one concrete reason for any defect:

| Criterion | Question |
| --- | --- |
| Practical usefulness | Does the orientation help Angel act today? |
| Material coverage | Are the demands and constraints that change today's decisions represented? |
| Relevant omissions | Is anything important missing? Higher score means fewer material omissions. |
| Priorities | Is relative attention justified in context? |
| Cross-domain relationships | Are useful dependencies/connections identified where applicable? |
| Unsupported inference | Are claims/recommendations grounded? Higher score means fewer unsupported inferences. |
| Uncertainty | Are material gaps/conflicts clear and appropriately calibrated? |
| Next steps | Are proposed steps concrete, proportionate and within Angel's authority? |

Record provisional blind coverage judgments; factual adjudication follows provenance review as a separate entry, without overwriting the original ratings. Disagreement between candidates is not itself an error.

## 11. Human Coordination Cost

Use a lightweight ledger: candidate, intervention purpose, category, approximate active minutes, number of transfers/restarts, and reason. Record elapsed waiting separately; estimates may be ranges. Do not infer zero from missing logs.

- **A — legitimate human input:** Capture, objectives, substantive decisions and approval of operational recommendations.
- **B — governance:** Architectural Review, experimental authorization and permission decisions; an approval is assigned by purpose, not counted twice.
- **C — operational middleware:** handoff copying, response relaying, manual contract-version reminders, repeating retrievable context, avoidable relaunches, and integration-compensating exports.

Report per-candidate category totals and the combined total. Shared Capture is recorded once as shared A input. Blinding, duplicate trial invocation and evaluator scoring are separate trial overhead; no hypothetical savings are credited. Transport that the normal workflow would still require remains C, even if performed during trial setup. Authorization friction is visible in B and total effort, not hidden as free execution. H2 targets lower C; a reduction offset by other recurring human effort is explicitly reported.

## 12. Failure Handling

| Condition | Required response within the trial |
| --- | --- |
| Required or materially triggered source fails | Log unavailable/incomplete and full diagnostic meaning; disclose effect. Follow contract §5: limited output may be possible, but cannot establish sufficient coverage if a material gap remains. |
| Pagination/truncation unresolved | Mark consultation incomplete; no “nothing found” claim. One bounded read-only retry or corrected request using returned evidence is allowed before cutoff; retain every attempt. |
| Different inputs or source change between reads | Preserve both timestamps/states. Separate scope/retrieval failure from temporal change. Do not feed one candidate's findings into the other before freezing. Mark Q2 inconclusive if material comparability cannot be established. |
| Capture adds information | Give identical Capture to both; perform independently triggered collection before reconciliation. Missing response or unfinished resulting collection remains incomplete. |
| B needs extra authorization or a state change | Stop the affected operation and report; do not alter configuration, ask for credentials or improvise a workaround. No escalation is implicitly granted by this protocol. |
| Run misses cutoff/freeze deadline or is incomplete | Freeze available partial evidence/output with that status; preserve the attempt. Do not silently replace it with a corrected successful run. |
| Material unsupported inference | Flag the exact claim and missing/contradictory evidence; preserve the frozen output. A post-evaluation correction is an addendum, not a replacement or a passing score. |
| Candidate contamination or premature synthesis | Mark the independence/fidelity breach and stop treating the pair as a valid comparison. |

“Material” means capable of changing Angel's attention, commitment, preparation or action. Angel adjudicates this with evidence; disagreement in preference alone is insufficient. Urgent real-world needs take precedence over maintaining a clean trial.

## 13. Provenance and Run Record

Future records belong under `experiments/operational_rhythm/runs/` in approved per-window locations. No run is created by this preparation. Maintain separate originals/evidence and blind presentation copies; keep the executor mapping out of the initial evaluator packet.

Minimum record: date/window/timezone; protocol and contract-base versions; Git reference; actual executor and observable runtime/model if available (otherwise unknown); start/cutoff/freeze times; logical required/triggered sources; discovery inventory and selection reasons; per-source query bounds, observed/update times, pagination/limits and status; Capture response/status; failures/retries; approximate duration; intervention ledger; frozen output reference and content hash; locked blind scores; packaging log; subsequent authorship revelation, comparability assessment and review outcome.

Use the contract's statuses: consulted—relevant information found; consulted—no relevant information found; unavailable; consultation incomplete. Record non-triggered conditional sources separately with reasons. Each material output claim should be traceable to a minimal evidence excerpt/reference, not necessarily a full raw response. Store only the personal content needed to interpret the result. Use relative artifact references and logical source labels; omit credentials, tokens, unnecessary sensitive IDs, absolute paths and hostnames. Retain provider IDs transiently only as needed for correct calls; sanitized error records retain diagnostic meaning. If sanitization prevents independent verification, state that reproducibility limit.

## 14. Evaluation Criteria

Q1 is supported in a window only if all required/triggered material coverage is demonstrated and no source gap is compensated by Angel exporting or relaying operational data for B. Read success in a few containers is insufficient; omissions discovered later revise the finding through an explicit addendum.

Q2 is assessed only after establishing that both candidates had the facts needed for the judgments being compared. Different containers or item counts do not automatically mean different material state. For comparable state, proposed sufficiency is no material defect, no zero score on an applicable criterion, and no evidence-backed material quality loss in B relative to A. Scores describe dimensions, not a single winner score. If state is materially different or context equivalence is unknown, Q2 is inconclusive; an equal-snapshot cognitive test would require separate approval and would not count as end-to-end evidence.

Q3 needs Q1 and Q2 support, preserved phase order and authority, and lower C active minutes without increased transfer/restart count or offsetting recurring human burden. If timing ranges overlap, cost reduction is inconclusive. If A already needs zero C, equality cannot be called a reduction. Zero tolerance for hidden material failures, fabricated commitments, unsupported material factual claims, or treating unanswered Capture as complete. No claim of repeated viability unless both windows support it; even then the conclusion is limited to further experimentation.

## 15. Stop / Continue Conditions

Start only after §17 is complete and isolation/blind delivery are feasible. Stop affected work for new authorization, prohibited writes, baseline drift, unavailable material evidence preventing reliable orientation, or lost independence. Preserve failures and allow remaining independent, authorized observation only; never repair the run invisibly.

Window 2 may proceed under the same approved rules if there was no governance/authorization breach and its prerequisites still hold. A material failure is retained and reviewed before another execution where it could recur unaddressed. Changes to design, scope rules or success criteria require renewed approval; no tuning to make B pass. Missing natural trigger diversity is a limitation, not permission to manufacture it. After two windows, stop for review. No architecture adoption, third window or C test follows automatically.

## 16. Known Limitations

Two windows provide diagnostic evidence, not statistical reliability. Live APIs may lack as-of queries; observation times cannot reconstruct unseen changes. Memory/context differences and recognizable writing style can defeat cognitive equivalence or blinding. A and B share discovery improvements, so their benefit is not attributable solely to B. Bia's post-freeze custodian role is not an independent judge; originals and mechanical-change logs enable audit. The ClickUp gate confirms bounded access only. No new orchestration platform or assumed agent-to-agent transport is introduced.

## 17. Approval Gate

Pending Alice review and Angel approval of: the bounded B exception; common discovery rules and time horizons; comparability/rubric thresholds; technical-collector isolation; single Capture delivery; and the mechanical blind-packaging role and route. Before execution, fill dates, collection/cutoff/freeze times, logical scope, contexts and approved record destinations. If the available interface cannot withhold originals/mapping from Angel, resolve that design issue before calling evaluation blind.

Preparation self-review: only this proposal is created; no candidate, Daily Brief, source collection, run, external write, contract/canonical-document change, permission/configuration change, commit or push is part of preparation. Publication of this proposal is not approval. Wait for Architectural Review and Angel's explicit approval before either candidate starts.
