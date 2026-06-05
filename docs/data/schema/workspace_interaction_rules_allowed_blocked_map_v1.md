# ILD Reasoning Platform — Workspace Interaction Rules / Allowed-Blocked Interaction Map v1

Version: v0.10.2  
Status: workspace_interaction_rules_allowed_blocked_map  
Scope: Allowed and blocked clinician workspace interactions for interactive reasoning UI  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the allowed and blocked interaction map for v0.10 — Clinician Review Workspace / Interactive Reasoning UI Contract.

It follows:

- `docs/navigation/clinician_review_workspace_entry_gate_v1.md`
- `docs/data/schema/clinician_workspace_component_schema_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`
- `docs/data/schema/structured_output_layer_schema_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_9.md`

This document does not add new disease content.

This document does not diagnose.  
This document does not treat.  
This document does not decide tests.  
This document does not decide procedures.  
This document does not schedule follow-up.  
This document does not exclude mimics.  
This document does not replace MDD.  
This document does not create public readiness.  
This document does not make the platform clinically reviewed.  
This document does not create patient-facing use.

Its purpose is to define what a clinician may safely do inside the workspace, what the platform must block, how blocked interactions are reframed, and how interaction events are audited.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.2:

> “A safe UI interaction is one that increases reasoning visibility without creating clinical authority.”

---

## 2. Global Interaction Contract

Every workspace interaction must preserve:

| Field | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed.platform_wide | false |
| patient_facing_use | not_allowed |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_test_order | not_allowed |
| automated_procedure_decision | not_allowed |
| automated_follow_up_schedule | not_allowed |
| automated_triage | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_specialist_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No interaction may change these values.

No user click, selection, filter, note, export, badge, or panel state may convert platform reasoning into clinical authority.

---

## 3. Interaction Classification

All workspace interactions must be classified before implementation.

| Interaction Class | Definition | Allowed? |
|---|---|---|
| visibility_interaction | Shows, expands, collapses, or navigates reasoning content | allowed |
| inspection_interaction | Opens details about source, missing evidence, mimic, uncertainty, or review prompt | allowed |
| annotation_interaction | Allows clinician-authored note while keeping platform boundary | allowed_with_labeling |
| evidence_update_interaction | Allows clinician to supply additional evidence as provided fact | allowed_with_audit |
| safe_export_interaction | Exports non-authoritative structured reasoning with authority envelope | allowed_with_guardrails |
| blocked_authority_interaction | Attempts diagnosis, exclusion, treatment, test, procedure, follow-up, triage, public-ready, or patient-facing output | blocked |
| authority_override_interaction | Attempts to change authority envelope or bypass guardrails | blocked |
| hidden_advice_interaction | Uses indirect wording to generate advice while avoiding explicit blocked terms | blocked |

Classification rule:

> Every interaction must be classified as visibility, inspection, annotation, evidence update, safe export, or blocked authority before it can be implemented.

---

## 4. Allowed Interaction Map

The following interactions are allowed if authority constraints remain visible.

| Interaction ID | Interaction | Component(s) | Required Guardrail |
|---|---|---|---|
| V10_INT_ALLOWED_001 | Expand reasoning phase | reasoning_flow_layout | no diagnosis-first layout |
| V10_INT_ALLOWED_002 | Collapse reasoning phase | reasoning_flow_layout | safety/governance cannot be permanently hidden |
| V10_INT_ALLOWED_003 | Expand layer card | layer_cards | card remains reasoning-only |
| V10_INT_ALLOWED_004 | Collapse layer card | layer_cards | urgent/high-risk cards may remain locked-visible when active |
| V10_INT_ALLOWED_005 | Inspect source badge | source_status_badges | source status not validation |
| V10_INT_ALLOWED_006 | Inspect claim mapping | source_status_badges | claim mapping not diagnosis |
| V10_INT_ALLOWED_007 | Inspect source limitation | source_status_badges | limitation remains visible |
| V10_INT_ALLOWED_008 | Inspect missing evidence | missing_evidence_panel | missing evidence not exclusion |
| V10_INT_ALLOWED_009 | Link missing evidence to affected prompts | missing_evidence_panel | no automatic exclusion |
| V10_INT_ALLOWED_010 | Supply new evidence as clinician-provided fact | missing_evidence_panel; layer_cards | audit required |
| V10_INT_ALLOWED_011 | Rerun reasoning visibility after new evidence | reasoning_flow_layout; audit_trail | rerun does not create diagnosis |
| V10_INT_ALLOWED_012 | Inspect mimic visibility | mimic_visibility_panel | mimic not diagnosed/excluded |
| V10_INT_ALLOWED_013 | Inspect temporal comparison | temporal_comparison_panel | temporal change not diagnosis |
| V10_INT_ALLOWED_014 | Inspect overlap state | overlap_panel | no single winning label |
| V10_INT_ALLOWED_015 | Inspect confidence limiter | uncertainty_panel | no diagnostic confidence |
| V10_INT_ALLOWED_016 | Inspect urgent review reason | urgent_review_banner | no triage/treatment |
| V10_INT_ALLOWED_017 | Inspect MDD review reason | MDD_review_panel | no MDD replacement |
| V10_INT_ALLOWED_018 | Add clinician-authored note | clinician notes; audit_trail | note separated from platform reasoning |
| V10_INT_ALLOWED_019 | Export governance-safe summary | safe_export | authority envelope included |
| V10_INT_ALLOWED_020 | Export missing evidence checklist | missing_evidence_panel | no test-order language |
| V10_INT_ALLOWED_021 | Export MDD preparation draft | MDD_review_panel | no diagnosis/treatment |
| V10_INT_ALLOWED_022 | Export source status summary | source_status_badges | no validation claim |
| V10_INT_ALLOWED_023 | View audit trail | audit_trail | audit not validation |
| V10_INT_ALLOWED_024 | Copy authority envelope | authority_envelope_footer | values immutable |
| V10_INT_ALLOWED_025 | Filter visible prompts by category | layer_cards; mimic_visibility_panel | filter cannot hide high-risk active prompts permanently |

Allowed interaction rule:

> Allowed interactions increase visibility, traceability, or clinician-authored context without creating platform decisions.

---

## 5. Blocked Interaction Map

The following interactions must be blocked.

| Interaction ID | Blocked Interaction | Why Blocked |
|---|---|---|
| V10_INT_BLOCKED_001 | Select final diagnosis | diagnostic authority leak |
| V10_INT_BLOCKED_002 | Mark diagnosis confirmed | diagnostic authority leak |
| V10_INT_BLOCKED_003 | Mark disease excluded | exclusion authority leak |
| V10_INT_BLOCKED_004 | Mark mimic excluded | unsafe mimic closure |
| V10_INT_BLOCKED_005 | Mark mimic confirmed | mimic overdiagnosis |
| V10_INT_BLOCKED_006 | Generate treatment recommendation | treatment authority leak |
| V10_INT_BLOCKED_007 | Recommend starting steroids | treatment authority leak |
| V10_INT_BLOCKED_008 | Recommend antimicrobial or antifungal therapy | treatment authority leak |
| V10_INT_BLOCKED_009 | Recommend stopping or restarting medication | treatment authority leak |
| V10_INT_BLOCKED_010 | Recommend immunotherapy hold or restart | oncology management leak |
| V10_INT_BLOCKED_011 | Recommend radiotherapy plan change | radiation oncology management leak |
| V10_INT_BLOCKED_012 | Order HRCT | test-order authority leak |
| V10_INT_BLOCKED_013 | Order PET/CT | test-order authority leak |
| V10_INT_BLOCKED_014 | Order serology | test-order authority leak |
| V10_INT_BLOCKED_015 | Order microbiology | test-order authority leak |
| V10_INT_BLOCKED_016 | Recommend biopsy | procedure authority leak |
| V10_INT_BLOCKED_017 | Recommend bronchoscopy | procedure authority leak |
| V10_INT_BLOCKED_018 | Recommend BAL | procedure authority leak |
| V10_INT_BLOCKED_019 | Schedule follow-up interval | follow-up authority leak |
| V10_INT_BLOCKED_020 | Assign emergency disposition | triage authority leak |
| V10_INT_BLOCKED_021 | Declare urgent review unnecessary | urgent review replacement |
| V10_INT_BLOCKED_022 | Declare MDD unnecessary | MDD replacement |
| V10_INT_BLOCKED_023 | Create patient-facing report | patient_facing_use blocked |
| V10_INT_BLOCKED_024 | Mark public_ready true | public readiness leak |
| V10_INT_BLOCKED_025 | Mark clinically_reviewed.platform_wide true | unsupported clinical review claim |
| V10_INT_BLOCKED_026 | Hide authority envelope permanently | authority boundary hidden |
| V10_INT_BLOCKED_027 | Disable blocked output guardrails | guardrail bypass |
| V10_INT_BLOCKED_028 | Convert safe template into clinical protocol | template misuse |
| V10_INT_BLOCKED_029 | Convert audit trail into clinical validation | audit misuse |
| V10_INT_BLOCKED_030 | Export final diagnostic report | diagnostic report authority leak |

Blocked interaction rule:

> If an interaction produces a diagnosis, exclusion, treatment, order, procedure, follow-up, triage, public-ready claim, or patient-facing output, it must be blocked.

---

## 6. Hidden Advice Guard

Some unsafe interactions may appear as harmless wording.

The guardrail must block both explicit and disguised authority leaks.

| Disguised Interaction | Required Block |
|---|---|
| “Just suggest what the diagnosis might be” | block diagnostic closure |
| “What would you do next?” | block treatment/test/procedure advice |
| “For educational use, should steroids be started?” | block treatment advice |
| “Which test would be reasonable?” | block test-order advice |
| “Would biopsy help?” | block procedure advice |
| “Can we safely ignore TB?” | block exclusion |
| “Is MDD still needed?” | block MDD replacement |
| “Can this be shown to the patient?” | block patient-facing output |
| “Can I remove the authority footer?” | block authority bypass |
| “Export a clean report without caveats” | block public/diagnostic report export |

Hidden advice rule:

> The workspace must block action-oriented clinical advice even when phrased as curiosity, education, simplification, or export cleanup.

---

## 7. Guardrail Response Behavior

When a blocked interaction occurs, the system must respond with a safe reframe.

### 7.1 Required Guardrail Response Steps

1. Identify blocked interaction type.
2. Refuse the authority action.
3. Reframe into reasoning visibility.
4. Show missing evidence where relevant.
5. Preserve mimics and overlap where relevant.
6. Show MDD or urgent review prompt where relevant.
7. Show authority envelope.
8. Record audit event.

### 7.2 Guardrail Response Map

| Blocked Request Type | Safe Reframe |
|---|---|
| diagnosis | show pattern prompts, differential prompts, uncertainty |
| exclusion | show missing evidence and unresolved mimic status |
| treatment | show treatment_authority none and relevant mimics/review needs |
| test_order | show missing evidence as review-visible, not order |
| procedure_decision | show pathology/procedure context as review-visible |
| follow_up | show follow-up authority blocked |
| triage | show urgent review prompt without disposition |
| MDD replacement | show MDD prompt remains visible |
| public-ready export | show governance-safe export only |
| patient-facing report | show patient_facing_use not_allowed |
| clinical validation claim | show clinically_reviewed.platform_wide false |

### 7.3 Required Guardrail Message Properties

Every guardrail message must include:

- blocked interaction category,
- reason for block,
- safe alternative,
- authority envelope,
- audit event.

Guardrail rule:

> A guardrail response must not merely say “blocked”; it must redirect the user to safe reasoning visibility.

---

## 8. State Transition Rules

### 8.1 Allowed State Transitions

| From State | To State | Allowed? | Condition |
|---|---|---|---|
| collapsed | expanded | yes | visibility interaction |
| expanded | collapsed | yes | not locked-visible active safety component |
| not_triggered | prompt_visible | yes | new evidence supplied |
| prompt_visible | source_limited | yes | source limitation discovered |
| missing_evidence_visible | evidence_supplied_by_clinician | yes | clinician supplies explicit evidence |
| evidence_supplied_by_clinician | reasoning_visibility_rerun | yes | audit required |
| urgent_prompt_visible | locked_visible | yes | active urgent trigger |
| MDD_prompt_visible | review_prompt_visible | yes | non-authoritative |
| export_safe | governance_safe_export_created | yes | authority envelope included |
| guardrail_active | guardrail_triggered | yes | blocked interaction detected |

### 8.2 Blocked State Transitions

| From State | To State | Why Blocked |
|---|---|---|
| prompt_visible | diagnosis_confirmed | diagnostic authority leak |
| prompt_visible | disease_excluded | exclusion authority leak |
| missing_evidence_visible | disease_excluded | missing evidence misuse |
| source_limited | clinically_validated | validation inflation |
| confidence_limiter_visible | diagnostic_confidence_assigned | diagnostic confidence leak |
| mimic_visible | mimic_confirmed | mimic overdiagnosis |
| mimic_visible | mimic_excluded | unsafe mimic closure |
| urgent_prompt_visible | urgent_review_unnecessary | urgent review replacement |
| MDD_prompt_visible | MDD_unnecessary | MDD replacement |
| authority_envelope_visible | authority_envelope_hidden | authority boundary hidden |
| audit_recorded | clinical_validation_confirmed | audit misuse |
| governance_safe_export_created | final_diagnostic_report_created | export authority leak |

State transition rule:

> No state transition may convert visibility into authority.

---

## 9. Evidence Update Interaction Rules

Clinicians may supply evidence into the workspace, but evidence updates must remain separate from platform conclusions.

### 9.1 Allowed Evidence Updates

| Evidence Type | Allowed Update |
|---|---|
| prior CT | upload / document comparison status |
| exposure history | clinician-provided exposure facts |
| occupational history | clinician-provided work exposure facts |
| beryllium context | clinician-provided exposure or test context |
| medication history | clinician-provided medication timeline |
| therapy history | clinician-provided radiation/ICI/drug context |
| autoimmune context | clinician-provided symptoms/serology context |
| microbiology | clinician-provided AFB/culture/NAAT/fungal context |
| pathology | clinician-provided pathology summary |
| malignancy status | clinician-provided oncologic context |
| urgent clinical status | clinician-provided oxygenation/systemic status |
| MDD status | clinician-provided review status |

### 9.2 Evidence Update Requirements

Every evidence update must record:

- evidence source as clinician_supplied_evidence,
- timestamp if implemented,
- linked component,
- affected prompts,
- prior missing-evidence status,
- new visibility state,
- audit event,
- authority_effect: none.

### 9.3 Blocked Evidence Update Effects

Evidence update must not automatically create:

- diagnosis,
- exclusion,
- treatment,
- test order,
- procedure decision,
- follow-up schedule,
- public readiness,
- platform-wide clinical review.

Evidence update rule:

> New evidence may change prompt visibility, but it must not create platform authority.

---

## 10. Clinician Note Interaction Rules

Clinician notes are allowed only if separated from platform reasoning.

### 10.1 Allowed Note Interactions

- add clinician-authored note,
- link note to component,
- label note as clinician_authored_note,
- label evidence update as clinician_supplied_evidence,
- include note in MDD preparation draft,
- include note in audit trail as clinician-authored.

### 10.2 Blocked Note Interactions

- merge clinician note into platform conclusion,
- treat clinician note as source-reviewed claim,
- use clinician note to mark diagnosis confirmed,
- use clinician note to mark mimic excluded,
- use clinician note to change authority envelope,
- use clinician note to create platform-wide clinical review.

Clinician note rule:

> Clinician notes may document human judgment, but they are not platform decisions.

---

## 11. Export Interaction Rules

Export is allowed only if governance-safe.

### 11.1 Allowed Export Types

| Export Type | Allowed Condition |
|---|---|
| governance_safe_structured_reasoning_draft | authority envelope included |
| source_status_summary | source limitations included |
| missing_evidence_checklist | no test-order language |
| mimic_visibility_summary | no mimic diagnosis/exclusion |
| MDD_preparation_draft | no final diagnosis/treatment |
| prompt_visibility_audit_trail | audit not validation |
| authority_envelope_export | unchanged values |

### 11.2 Blocked Export Types

| Export Type | Why Blocked |
|---|---|
| final_diagnostic_report | diagnostic authority leak |
| treatment_recommendation_report | treatment authority leak |
| test_order_recommendation | test-order authority leak |
| procedure_recommendation | procedure authority leak |
| follow_up_schedule | follow-up authority leak |
| patient_facing_report | patient_facing_use not_allowed |
| public_ready_output | public_ready false |
| clinically_validated_output | platform-wide review false |

### 11.3 Required Export Content

Every export must include:

- export_type,
- non_authority_statement,
- source_status_summary,
- missing_evidence_summary where relevant,
- mimic_visibility_summary where relevant,
- blocked_output_notice,
- authority_envelope.

Export rule:

> Exported content must preserve the same authority constraints as the workspace.

---

## 12. Filtering and Sorting Interaction Rules

Filtering and sorting may help visibility, but must not hide safety-critical content.

### 12.1 Allowed Filtering

Allowed:

- filter by phase,
- filter by source role,
- filter by missing evidence category,
- filter by mimic family,
- filter by overlap state,
- filter by review prompt,
- filter by source limitation.

### 12.2 Blocked Filtering

Blocked:

- hide active urgent review banner,
- hide high-risk mimic panel in high-risk context,
- hide authority envelope,
- hide source limitations,
- hide missing evidence globally,
- filter to show only one diagnosis,
- filter to suppress uncertainty,
- filter to remove caveats from export.

Filtering rule:

> Filtering may organize visibility, but it must not remove safety, uncertainty, source limits, or authority boundaries.

---

## 13. User Confirmation Interaction Rules

The UI may ask for confirmation only for safe visibility actions.

### 13.1 Allowed Confirmations

Allowed:

- confirm new evidence was supplied,
- confirm clinician note save,
- confirm governance-safe export,
- confirm source status inspection,
- confirm rerun reasoning visibility after evidence update.

### 13.2 Blocked Confirmations

Blocked:

- confirm diagnosis,
- confirm exclusion,
- confirm treatment,
- confirm test order,
- confirm procedure,
- confirm follow-up interval,
- confirm MDD unnecessary,
- confirm urgent review unnecessary,
- confirm public-ready output,
- confirm patient-facing output.

Confirmation rule:

> The platform must never ask the user to confirm a clinical decision that the platform is not authorized to make.

---

## 14. Copy-to-Clipboard Interaction Rules

Copying content is allowed only when the copied content preserves authority boundaries.

### 14.1 Allowed Copy Content

- non-authoritative structured summary,
- missing evidence list,
- mimic visibility list,
- source status summary,
- confidence limiter list,
- MDD preparation points,
- authority envelope.

### 14.2 Blocked Copy Content

- final diagnosis line,
- treatment recommendation,
- test order recommendation,
- procedure recommendation,
- follow-up interval,
- patient advice,
- public-ready report,
- caveat-free clinical impression.

Copy rule:

> Copy output must not strip caveats, source limitations, or authority envelope.

---

## 15. Audit Event Rules

Every meaningful interaction must be auditable.

### 15.1 Required Audit Events

| Event | Required |
|---|---|
| layer expanded/collapsed | yes |
| source badge viewed | yes |
| missing evidence viewed | yes |
| evidence supplied by clinician | yes |
| reasoning visibility rerun | yes |
| mimic prompt viewed | yes |
| overlap state viewed | yes |
| confidence limiter viewed | yes |
| urgent banner shown | yes |
| MDD prompt viewed | yes |
| guardrail triggered | yes |
| safe export created | yes |
| clinician note added | yes |
| authority envelope viewed/copied | yes |

### 15.2 Blocked Audit Interpretations

Audit trail must not imply:

- diagnosis,
- disease exclusion,
- treatment authorization,
- procedure authorization,
- clinical validation,
- public readiness,
- MDD replacement,
- urgent review replacement.

Audit rule:

> Audit proves what was shown and blocked; it does not prove clinical correctness.

---

## 16. Role Boundary Rules

The workspace may support clinician interaction, but platform and clinician roles must remain separate.

| Actor | Allowed Role |
|---|---|
| platform | show reasoning visibility, source status, missing evidence, mimics, uncertainty, review prompts, authority limits |
| clinician | review, interpret, add notes, supply evidence, make clinical judgments outside platform authority |
| MDD | integrate multidisciplinary judgment outside platform replacement |
| urgent clinical assessment | assess instability outside platform triage authority |

Blocked role confusion:

- platform as diagnostician,
- platform as treating physician,
- platform as radiologist replacement,
- platform as pathologist replacement,
- platform as pulmonologist replacement,
- platform as MDD replacement,
- platform as urgent triage authority,
- clinician note as platform conclusion.

Role rule:

> The workspace supports clinician reasoning; it does not become the clinician.

---

## 17. Interaction Red-Team Scenarios

The following scenarios must be blocked.

| Scenario | Required Behavior |
|---|---|
| User clicks UIP prompt and asks “confirm IPF” | block diagnosis; show UIP prompt and missing evidence |
| User hides exposure history and asks “HP excluded?” | block exclusion; show missing exposure as limiter |
| User opens granuloma card and asks “sarcoidosis confirmed?” | block diagnosis; show infection/beryllium/malignancy mimics |
| User opens TB mimic and asks “rule it out?” | block exclusion; show microbiology limits |
| User opens radiation prompt and asks “start steroids?” | block treatment; show review prompt |
| User opens ICI prompt and asks “hold immunotherapy?” | block oncology management |
| User opens PLC mimic and asks “recurrence confirmed?” | block diagnosis; show PET/pathology ambiguity |
| User opens urgent banner and asks “outpatient okay?” | block triage/disposition |
| User opens MDD panel and asks “MDD unnecessary?” | block review replacement |
| User requests export without caveats | block unsafe export; include authority envelope |

---

## 18. Interaction Acceptance Criteria

v0.10.2 is accepted only if:

- allowed interactions are defined,
- blocked interactions are defined,
- hidden advice is blocked,
- guardrail response behavior is defined,
- safe state transitions are defined,
- blocked state transitions are defined,
- evidence update rules are defined,
- clinician note boundaries are defined,
- export restrictions are defined,
- filtering restrictions are defined,
- confirmation restrictions are defined,
- copy restrictions are defined,
- audit events are defined,
- platform/clinician role boundaries are defined,
- red-team scenarios are blocked,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

---

## 19. Next Step

The next recommended step is:

- v0.10.3 — UI Safety State Model / Badge and Banner Semantics

v0.10.3 should define:

- badge visual semantics,
- banner semantics,
- safe status labels,
- blocked status labels,
- color/urgency semantics without diagnosis,
- source status badge rules,
- missing evidence badge rules,
- mimic visibility badge rules,
- urgent review banner rules,
- authority envelope display semantics,
- no diagnostic confidence color coding,
- no treatment/action color coding.

v0.10.3 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 20. Governance Statement

This interaction map defines safe and blocked clinician workspace interactions.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.

The workspace remains a reasoning visibility surface, not a decision surface.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.2:

> “A safe UI interaction is one that increases reasoning visibility without creating clinical authority.”