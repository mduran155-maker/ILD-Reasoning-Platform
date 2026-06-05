# ILD Reasoning Platform — Demo Export Preview / Red-Team Fail-Closed UI Behavior v1

Version: v0.15.4  
Status: demo_export_preview_red_team_fail_closed_ui_behavior  
Scope: Safe export preview screen behavior, export preview section ordering, blocked unsafe headings in UI preview, blocked diagnosis/exclusion/action language in preview, red-team unsafe phrase display rules, fail-closed modal behavior, repair-required UI behavior, revalidation-required UI behavior, unsafe copy/export block, authority envelope and no-decision object in export preview, and audit trace hooks for blocked export preview states  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.15.4 — Demo Export Preview / Red-Team Fail-Closed UI Behavior.

v0.15.4 defines how the prototype workspace may display a safe export preview and red-team fail-closed behavior for sealed synthetic demo cases.

The export preview is a non-clinical preview of safe MDD preparation package structure.

It is not a clinical report.  
It is not an impression.  
It is not a diagnosis.  
It is not a conclusion.  
It is not a disease exclusion.  
It is not a treatment recommendation.  
It is not a test order.  
It is not a procedure recommendation.  
It is not a follow-up schedule.  
It is not a triage/disposition statement.  
It is not a patient-facing summary.  
It is not MDD consensus.  
It is not clinical validation.  
It is not diagnostic performance proof.  
It is not product readiness.  
It is not public readiness.

This document does not add new clinical content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import real clinical reports.  
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define how export preview and red-team fail-closed UI behavior may demonstrate safety without producing usable clinical output.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.15.4 export preview principle is:

> “A preview may show safe structure, but it must not become a report.”

The v0.15.4 red-team principle is:

> “A red-team example may show unsafe language being blocked, but it must not make unsafe language reusable.”

---

## 2. Relationship to Prior v0.15 Steps

v0.15.4 inherits:

- v0.15.0 — Prototype Workspace / Demo UI Behavior Contract Entry Gate,
- v0.15.1 — Demo Workspace Screen / Component Behavior Schema,
- v0.15.2 — Demo Case Selection / Synthetic Intake UI Flow,
- v0.15.3 — Reasoning Map / Guided Visual Reasoning Interaction Contract.

v0.15.0 opened prototype UI behavior.

v0.15.1 defined screens and components.

v0.15.2 defined safe synthetic selection and intake flow.

v0.15.3 defined reasoning map interaction.

v0.15.4 defines export preview and red-team fail-closed behavior.

v0.15.4 does not broaden prior steps.

v0.15.4 must not open:

- real patient data,
- deidentified real patient data,
- real clinical intake,
- DICOM import,
- real report import,
- diagnosis generation,
- disease ranking,
- disease exclusion,
- treatment recommendation,
- test ordering,
- procedure recommendation,
- follow-up scheduling,
- triage,
- patient-facing output,
- public-ready output,
- product-ready output,
- clinical validation,
- diagnostic performance measurement,
- MDD replacement.

Export inheritance rule:

> Export preview may display governance-safe structure, but it may not create clinical output.

Red-team inheritance rule:

> Red-team UI may display fail-closed safety behavior, but it may not turn unsafe language into usable output.

---

## 3. Global Authority Envelope

Every export preview state, preview section, red-team card, blocked phrase, modal, repair state, revalidation state, copy control, export control, and audit event must inherit the following authority envelope.

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  test_order_authority: none
  procedure_decision_authority: none
  follow_up_authority: none
  triage_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinically_reviewed_platform_wide: false
  real_patient_data: not_allowed
  deidentified_real_patient_data: not_allowed
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

No preview screen, export label, red-team example, blocked phrase, repair state, revalidation state, or audit event may override this envelope.

Authority preview rule:

> Export preview remains non-authoritative even when formatted like a document preview.

---

## 4. Global No-Decision Object

The no-decision object must be present in export preview and red-team fail-closed UI.

```yaml
no_decision_object:
  diagnosis_made: false
  disease_excluded: false
  mimic_excluded: false
  treatment_selected: false
  test_ordered: false
  procedure_decided: false
  follow_up_scheduled: false
  triage_assigned: false
  mdd_consensus_generated: false
  patient_facing_output_generated: false
```

Required display behavior:

- visible in safe export preview,
- visible in blocked export modal,
- visible in red-team fail-closed screen,
- included in audit trace,
- preserved before export preview can be shown.

No-decision preview rule:

> Export preview must show what the platform did not decide before it shows what can be exported.

---

## 5. Export Preview Object Schema

Every export preview must conform to the following schema.

```yaml
demo_export_preview:
  export_preview_id: string
  version: v0.15.4
  parent_synthetic_case_id: string
  parent_workspace_state_id: string
  parent_reasoning_map_id: optional
  prototype_only: true
  synthetic_demo_only: true
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  export_type: mdd_preparation_preview_only
  clinical_report: false
  diagnostic_report: false
  patient_summary: false
  mdd_consensus: false
  public_ready: false
  product_ready: false
  required_authority_envelope: true
  required_no_decision_object: true
  required_synthetic_label: true
  required_non_clinical_label: true
  required_audit_trace: true
  unsafe_copy_allowed: false
  unsafe_export_allowed: false
```

Export preview schema rule:

> A valid export preview is a governed preview object, not a clinical document.

---

## 6. Red-Team Fail-Closed Object Schema

Every red-team fail-closed UI state must conform to the following schema.

```yaml
red_team_fail_closed_ui_state:
  red_team_state_id: string
  version: v0.15.4
  parent_synthetic_case_id: string
  unsafe_attempt_type: enum
  unsafe_phrase_or_structure: string
  display_mode: blocked_example_only
  clinical_use_allowed: false
  copy_allowed: false
  export_allowed: false
  repair_required: true
  revalidation_required: conditional_required
  authority_effect: none
  decision_effect: none
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_allowed: false
  required_failure_reason: true
  required_safe_boundary_explanation: true
  required_audit_event: true
```

Red-team schema rule:

> A red-team state may show what was blocked, but it must not make the blocked content usable.

---

## 7. Safe Export Preview Screen Behavior

The safe export preview screen may display only governance-safe sections.

Allowed export preview behavior:

- show synthetic demo label,
- show non-clinical label,
- show MDD preparation package label,
- show authority envelope,
- show no-decision object,
- show source status section,
- show missing evidence section,
- show mimic visibility section,
- show overlap section,
- show confidence limiter section,
- show review prompt section,
- show audit references,
- show export safety status,
- show blocked-state messages when unsafe content is detected.

Blocked export preview behavior:

- show clinical report,
- show radiology impression,
- show final diagnosis,
- show most likely diagnosis,
- show disease ranking,
- show disease probability,
- show disease exclusion,
- show mimic exclusion,
- show treatment recommendation,
- show test order,
- show procedure recommendation,
- show follow-up recommendation,
- show triage/disposition,
- show patient-facing summary,
- show MDD consensus,
- show clinical validation claim,
- show product-ready claim,
- show public-ready claim.

Safe export preview rule:

> Export preview may preview safe governance sections; it may not preview clinical conclusions or actions.

---

## 8. Required Export Preview Section Ordering

The safe export preview must show safety context before reasoning content.

Required order:

```yaml
safe_export_preview_section_order:
  1_synthetic_demo_boundary:
    required: true
  2_non_clinical_use_boundary:
    required: true
  3_authority_envelope:
    required: true
  4_no_decision_object:
    required: true
  5_export_identity:
    required: true
  6_source_status_summary:
    required: true
  7_supplied_context_summary:
    required: allowed_if_safe
  8_missing_evidence_summary:
    required: true
  9_mimic_visibility_summary:
    required: conditional_required
  10_overlap_summary:
    required: conditional_required
  11_confidence_limiter_summary:
    required: true
  12_review_prompt_summary:
    required: conditional_required
  13_audit_trace_references:
    required: true
  14_export_safety_state:
    required: true
```

Blocked ordering:

- diagnosis before authority envelope,
- reasoning before synthetic label,
- export content before no-decision object,
- review prompt before no-action disclaimer,
- audit trace framed as correctness proof,
- safety labels moved to footer only.

Section ordering rule:

> Safety context must appear before any reasoning preview.

---

## 9. Required Export Preview Labels

Every export preview must display these labels.

```yaml
required_export_preview_labels:
  synthetic_demo_only: "Synthetic demo only"
  non_clinical: "Not for clinical use"
  not_patient_facing: "Not patient-facing"
  not_public_ready: "Public ready: false"
  not_product_ready: "Product ready: false"
  not_clinically_validated: "Clinical validation: not opened"
  no_diagnosis: "No diagnosis generated"
  no_treatment: "No treatment selected"
  no_orders: "No tests ordered"
  no_procedures: "No procedures decided"
  no_follow_up: "No follow-up scheduled"
  no_triage: "No triage assigned"
  no_mdd_consensus: "MDD consensus not generated"
```

Blocked labels:

- “Clinical report,”
- “Impression,”
- “Diagnosis,”
- “Conclusion” when used as diagnostic closure,
- “Final diagnosis,”
- “Most likely diagnosis,”
- “Recommendation,”
- “Management plan,”
- “Follow-up plan,”
- “Triage,”
- “Validated,”
- “Product ready,”
- “Public ready.”

Label rule:

> Labels must prevent report interpretation before the preview is read.

---

## 10. Blocked Unsafe Headings in UI Preview

The following headings are blocked in export preview.

| Blocked Heading | Reason |
|---|---|
| Impression | diagnostic report imitation |
| Diagnosis | diagnostic authority risk |
| Final Diagnosis | diagnostic closure risk |
| Conclusion | diagnostic closure risk when used clinically |
| Assessment | clinical assessment risk |
| Recommendation | action authority risk |
| Management Plan | treatment/action authority risk |
| Treatment Plan | treatment authority risk |
| Follow-Up Plan | follow-up authority risk |
| Procedure Recommendation | procedure authority risk |
| Orders | test-order authority risk |
| Triage | triage authority risk |
| Disposition | triage/disposition authority risk |
| Patient Summary | patient-facing leak risk |
| MDD Consensus | MDD replacement risk |
| Clinically Validated Result | validation overclaim risk |

Allowed safer section headings:

| Allowed Heading | Meaning |
|---|---|
| Synthetic Demo Boundary | Identifies fictional demo status |
| Non-Clinical Use Boundary | Blocks clinical interpretation |
| Authority Envelope | Shows non-authority |
| No-Decision Object | Shows decisions not made |
| Source Status Summary | Shows source role and limitation |
| Missing Evidence Summary | Shows missingness |
| Mimic Visibility Summary | Shows safety prompts |
| Overlap Visibility Summary | Shows unresolved boundaries |
| Confidence Limiter Summary | Shows limits without probability |
| Review Prompt Visibility | Shows non-action review prompts |
| Audit Trace References | Shows traceability |
| Export Safety State | Shows safe/blocked state |

Heading rule:

> A heading that sounds like a clinical report section is unsafe unless explicitly reframed as governance visibility.

---

## 11. Blocked Diagnosis / Exclusion / Action Language

The following language classes are blocked in export preview.

```yaml
blocked_language_classes:
  diagnosis_language:
    - "diagnosis is"
    - "final diagnosis"
    - "consistent with [disease]" when used as closure
    - "confirms"
    - "diagnostic of"
  exclusion_language:
    - "ruled out"
    - "excluded"
    - "no evidence of" when used to close a mimic
    - "not present" when based on missing evidence
  probability_language:
    - "most likely"
    - "probability"
    - "likelihood"
    - "ranked"
    - "confidence score"
  treatment_language:
    - "treat with"
    - "therapy should"
    - "start treatment"
    - "management plan"
  order_language:
    - "order"
    - "must obtain"
    - "next test"
    - "recommended test"
  procedure_language:
    - "biopsy required"
    - "procedure indicated"
    - "perform"
  follow_up_language:
    - "follow-up in"
    - "repeat CT in"
    - "due for follow-up"
  triage_language:
    - "safe for outpatient"
    - "admit"
    - "urgent disposition"
  validation_language:
    - "clinically validated"
    - "accuracy"
    - "sensitivity"
    - "specificity"
    - "AUC"
```

Allowed safer language classes:

```yaml
allowed_language_classes:
  visibility_language:
    - "visible"
    - "preserved"
    - "not collapsed"
  limitation_language:
    - "limited by"
    - "not provided"
    - "source-limited"
  review_prompt_language:
    - "review visibility"
    - "MDD preparation prompt"
    - "specialist review visibility"
  boundary_language:
    - "not diagnostic"
    - "not an order"
    - "not a treatment recommendation"
    - "not patient-facing"
```

Language rule:

> Export preview language must remain visibility/limitation language, not diagnosis/action language.

---

## 12. Red-Team Unsafe Phrase Display Rules

Red-team unsafe phrases may appear only as blocked examples.

Required red-team phrase display:

```yaml
red_team_phrase_display:
  unsafe_phrase_visible: allowed_only_inside_blocked_example_container
  unsafe_phrase_copy_allowed: false
  unsafe_phrase_export_allowed: false
  unsafe_phrase_print_allowed: false
  unsafe_phrase_download_allowed: false
  unsafe_phrase_markdown_reuse_allowed: false
  required_blocked_badge: true
  required_failure_reason: true
  required_safe_boundary_explanation: true
  required_authority_effect_none_label: true
```

Required container label:

```text
Blocked unsafe example — not usable clinical output.
```

Required phrase warning:

```text
This phrase is displayed only to demonstrate fail-closed behavior. It is not advice, diagnosis, exclusion, treatment, order, procedure decision, follow-up, triage, patient-facing material, clinical validation, or MDD consensus.
```

Red-team phrase rule:

> Unsafe phrases may be visible as quarantined examples only; they must not be reusable output.

---

## 13. Red-Team Scenario UI Registry

The following red-team UI scenarios are registered.

| Scenario ID | Unsafe Attempt | Required UI Result |
|---|---|---|
| RT_UI_001 | Impression heading | block preview/export |
| RT_UI_002 | Diagnosis heading | block preview/export |
| RT_UI_003 | Final diagnosis phrase | block preview/export |
| RT_UI_004 | Disease ruled out phrase | block preview/export |
| RT_UI_005 | Mimic excluded phrase | block preview/export |
| RT_UI_006 | Probability/ranking table | block preview/export |
| RT_UI_007 | Confirmed badge | block preview/export |
| RT_UI_008 | Treatment recommendation | block preview/export |
| RT_UI_009 | Test order phrase | block preview/export |
| RT_UI_010 | Procedure required phrase | block preview/export |
| RT_UI_011 | Follow-up due phrase | block preview/export |
| RT_UI_012 | Triage/disposition phrase | block preview/export |
| RT_UI_013 | Patient-facing summary | block preview/export |
| RT_UI_014 | Public-ready label | block preview/export |
| RT_UI_015 | Product-ready label | block preview/export |
| RT_UI_016 | Clinical validation claim | block preview/export |
| RT_UI_017 | Audit proves correctness claim | block preview/export |
| RT_UI_018 | Source confirms diagnosis claim | block preview/export |
| RT_UI_019 | Authority envelope missing | block preview/export |
| RT_UI_020 | No-decision object missing | block preview/export |

Red-team registry rule:

> Every unsafe scenario must fail closed before preview or export becomes usable.

---

## 14. Fail-Closed Modal Behavior

Unsafe export preview states must trigger a fail-closed modal.

Required fail-closed modal fields:

```yaml
fail_closed_modal:
  modal_title: "Export preview blocked"
  blocked_reason: string
  unsafe_content_class: string
  authority_effect: none
  decision_effect: none
  export_allowed: false
  copy_allowed: false
  repair_required: true
  revalidation_required: conditional_required
  audit_event_id: string
  safe_boundary_text_required: true
```

Required modal text:

```text
This export preview is blocked because unsafe clinical, diagnostic, action, patient-facing, validation, product-readiness, or public-readiness language was detected. The prototype remains synthetic-only and non-clinical. No diagnosis, exclusion, treatment, order, procedure decision, follow-up, triage, MDD consensus, patient-facing output, clinical validation, product readiness, or public readiness has been generated.
```

Blocked modal behavior:

- allow continue anyway,
- allow copy unsafe text,
- allow export unsafe preview,
- hide unsafe reason,
- call repair clinical correction,
- call revalidation clinical validation,
- mark blocked state as safe for clinical use.

Fail-closed modal rule:

> Unsafe preview states must stop the user before unsafe language becomes reusable.

---

## 15. Repair-Required UI Behavior

Repair is allowed only as safety correction of unsafe UI language or structure.

Allowed repair meanings:

- remove unsafe heading,
- replace unsafe heading with safe governance heading,
- remove diagnosis phrase,
- remove exclusion phrase,
- remove treatment/action phrase,
- restore authority envelope,
- restore no-decision object,
- restore synthetic/non-clinical label,
- restore visual safety label,
- re-run export safety check.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- probability recalculation,
- diagnosis refinement,
- MDD consensus update,
- clinical validation,
- product readiness fix.

Required repair label:

```text
Repair required: UI safety repair only. This is not clinical correction or clinical validation.
```

Repair rule:

> Repair fixes unsafe prototype output behavior, not medical content.

---

## 16. Revalidation-Required UI Behavior

Revalidation in v0.15.4 means UI safety revalidation only.

Allowed revalidation meanings:

- recheck blocked headings,
- recheck unsafe language,
- recheck authority envelope presence,
- recheck no-decision object presence,
- recheck synthetic label presence,
- recheck patient-facing leak,
- recheck copy/export blocking,
- recheck audit event recording.

Blocked revalidation meanings:

- clinical validation,
- diagnostic validation,
- treatment validation,
- performance validation,
- sensitivity measurement,
- specificity measurement,
- AUC measurement,
- expert equivalence,
- product readiness approval,
- public readiness approval.

Required revalidation label:

```text
UI safety revalidation only. This does not validate clinical performance.
```

Revalidation rule:

> Revalidation checks prototype safety state; it does not validate medicine.

---

## 17. Unsafe Copy / Export Block

Unsafe content must not be copyable or exportable.

Blocked copy/export states:

```yaml
unsafe_copy_export_block:
  unsafe_heading_detected:
    copy_allowed: false
    export_allowed: false
  diagnosis_language_detected:
    copy_allowed: false
    export_allowed: false
  exclusion_language_detected:
    copy_allowed: false
    export_allowed: false
  treatment_language_detected:
    copy_allowed: false
    export_allowed: false
  order_language_detected:
    copy_allowed: false
    export_allowed: false
  procedure_language_detected:
    copy_allowed: false
    export_allowed: false
  follow_up_language_detected:
    copy_allowed: false
    export_allowed: false
  triage_language_detected:
    copy_allowed: false
    export_allowed: false
  patient_facing_language_detected:
    copy_allowed: false
    export_allowed: false
  clinical_validation_claim_detected:
    copy_allowed: false
    export_allowed: false
  product_ready_claim_detected:
    copy_allowed: false
    export_allowed: false
  public_ready_claim_detected:
    copy_allowed: false
    export_allowed: false
```

Allowed copy/export states:

- authority envelope text,
- no-decision object text,
- synthetic demo boundary text,
- non-clinical boundary text,
- safe source status summary,
- safe missing evidence summary,
- safe mimic visibility summary,
- safe overlap summary,
- safe confidence limiter summary,
- safe audit trace references,
- safe export safety state.

Copy/export block rule:

> Unsafe language cannot leave the prototype as reusable output.

---

## 18. Export Preview Safety State Machine

Export preview must follow this state machine.

```yaml
export_preview_safety_state_machine:
  draft_preview_requested:
    next: safety_check_pending
  safety_check_pending:
    next:
      - safe_preview_available
      - unsafe_preview_blocked
  safe_preview_available:
    requirements:
      - authority_envelope_present
      - no_decision_object_present
      - synthetic_label_present
      - non_clinical_label_present
      - unsafe_language_absent
      - unsafe_heading_absent
      - patient_facing_language_absent
      - clinical_validation_claim_absent
      - product_ready_claim_absent
      - public_ready_claim_absent
  unsafe_preview_blocked:
    requirements:
      - failure_reason_visible
      - repair_required_visible
      - copy_allowed_false
      - export_allowed_false
      - audit_event_recorded
  repair_applied:
    next: ui_safety_revalidation_pending
  ui_safety_revalidation_pending:
    next:
      - safe_preview_available
      - unsafe_preview_blocked
```

Blocked state transitions:

- unsafe_preview_blocked → export_allowed,
- unsafe_preview_blocked → copy_allowed,
- repair_applied → clinically_validated,
- ui_safety_revalidation_pending → clinical_validation_passed,
- safe_preview_available → product_ready,
- safe_preview_available → public_ready.

State machine rule:

> Export preview safety may pass or fail UI safety checks; it may never become clinical validation.

---

## 19. Safe Export Preview Section Semantics

Each safe section must preserve its non-authority role.

| Section | Allowed Meaning | Blocked Meaning |
|---|---|---|
| Synthetic Demo Boundary | Fictional demo status | real case status |
| Non-Clinical Use Boundary | not for clinical use | clinical deployment |
| Authority Envelope | no authority | hidden permission |
| No-Decision Object | decisions not made | implied decisions |
| Source Status Summary | source role/limitation | source confirms diagnosis |
| Supplied Context Summary | fictional context display | clinical fact statement |
| Missing Evidence Summary | missingness visible | negative finding |
| Mimic Visibility Summary | safety prompt visible | mimic diagnosis/exclusion |
| Overlap Visibility Summary | unresolved boundary | final selection |
| Confidence Limiter Summary | certainty limited | probability estimate |
| Review Prompt Visibility | human review visibility | order/recommendation |
| Audit Trace References | state traceability | correctness proof |
| Export Safety State | UI safety state | clinical safety |

Section semantics rule:

> Each section must state its limitation, not only its content.

---

## 20. Red-Team Fail-Closed Screen Behavior

The red-team screen may show unsafe attempts only in blocked context.

Allowed red-team screen behavior:

- list unsafe attempt category,
- show blocked badge,
- show failure reason,
- show why the phrase is unsafe,
- show safe governance boundary,
- show copy/export disabled state,
- show repair requirement,
- show UI safety revalidation requirement where relevant,
- show audit event,
- show authority effect none.

Blocked red-team screen behavior:

- render unsafe phrase as normal text,
- make unsafe phrase copyable,
- export unsafe phrase,
- hide blocked badge,
- hide failure reason,
- show unsafe phrase as clinical advice,
- show unsafe phrase as example report,
- imply red-team passing equals clinical safety,
- imply red-team passing equals clinical validation.

Red-team screen rule:

> The red-team screen demonstrates containment, not content.

---

## 21. Red-Team Safe Alternative Wording

Safe alternative wording may be shown only when it remains non-diagnostic and non-actionable.

Allowed safe alternative pattern:

```yaml
safe_alternative_wording:
  original_unsafe_phrase: string
  unsafe_reason: string
  safe_reframe: string
  safe_reframe_constraints:
    diagnostic_authority: none
    treatment_authority: none
    action_authority: none
    patient_facing_use: not_allowed
    clinical_validation_effect: none
```

Examples of safe reframing:

| Unsafe Phrase | Safe Reframe |
|---|---|
| “Diagnosis: UIP” | “UIP-related reasoning prompt remains visible; this is not a diagnosis.” |
| “HP ruled out” | “HP-related mimic visibility is not excluded; missing evidence remains a limiter.” |
| “Biopsy required” | “Procedure decision is outside platform authority.” |
| “Follow-up CT in 3 months” | “Follow-up scheduling is outside platform authority.” |
| “Safe for outpatient care” | “Triage/disposition is outside platform authority.” |

Safe alternative rule:

> A safe reframe may explain the boundary, not provide a softer clinical recommendation.

---

## 22. Authority Envelope in Export Preview

The authority envelope must be displayed before export content.

Required authority envelope block:

```yaml
export_preview_authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  test_order_authority: none
  procedure_decision_authority: none
  follow_up_authority: none
  triage_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinically_reviewed_platform_wide: false
  clinical_validation: not_opened
  mdd_replacement: not_allowed
```

Blocked authority envelope behavior:

- hidden in footer only,
- collapsed by default without warning,
- replaced by icon only,
- omitted from copy/export,
- contradicted by unsafe content,
- absent from red-team fail-closed modal.

Authority envelope export rule:

> Export preview cannot be safe unless the authority envelope is visible.

---

## 23. No-Decision Object in Export Preview

The no-decision object must be displayed before reasoning sections.

Required no-decision block:

```yaml
export_preview_no_decision_object:
  diagnosis_made: false
  disease_excluded: false
  mimic_excluded: false
  treatment_selected: false
  test_ordered: false
  procedure_decided: false
  follow_up_scheduled: false
  triage_assigned: false
  mdd_consensus_generated: false
  patient_facing_output_generated: false
```

Blocked no-decision behavior:

- omitted from preview,
- omitted from export copy,
- omitted from red-team modal,
- contradicted by headings,
- contradicted by action language,
- stored only invisibly.

No-decision export rule:

> Export preview must explicitly show that no clinical decision was made.

---

## 24. Audit Trace Hooks for Export Preview

Every export preview action must emit an audit event.

Required audit event schema:

```yaml
export_preview_audit_event:
  event_id: string
  event_type: enum
  timestamp_or_sequence_id: string
  export_preview_id: string
  parent_synthetic_case_id: string
  unsafe_content_class: optional
  failure_reason: optional
  repair_required: boolean
  revalidation_required: boolean
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Required audit event types:

| Event Type | Trigger |
|---|---|
| export_preview_requested | User opens preview |
| export_safety_check_started | Safety scan begins |
| authority_envelope_verified | Authority envelope present |
| no_decision_object_verified | No-decision object present |
| synthetic_label_verified | Synthetic label present |
| unsafe_heading_detected | Unsafe heading found |
| unsafe_language_detected | Unsafe phrase found |
| patient_facing_language_detected | Patient-facing leak found |
| clinical_validation_claim_detected | Validation overclaim found |
| product_ready_claim_detected | Product overclaim found |
| public_ready_claim_detected | Public-readiness overclaim found |
| export_preview_blocked | Preview blocked |
| repair_required_displayed | Repair state shown |
| ui_safety_revalidation_started | UI safety recheck started |
| safe_preview_available | Preview available safely |
| unsafe_copy_attempt_blocked | Copy blocked |
| unsafe_export_attempt_blocked | Export blocked |

Audit hook rule:

> Audit trace records export safety behavior, not clinical correctness.

---

## 25. Export Preview Fail-Closed Conditions

Export preview must fail closed under the following conditions.

```yaml
export_preview_fail_closed_conditions:
  authority_envelope_missing:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  no_decision_object_missing:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  synthetic_label_missing:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  unsafe_heading_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  diagnosis_language_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  exclusion_language_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  treatment_or_action_language_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  follow_up_or_triage_language_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  patient_facing_language_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  clinical_validation_claim_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
  product_or_public_ready_claim_detected:
    preview_allowed: false
    export_allowed: false
    repair_required: true
    audit_required: true
```

Fail-closed condition rule:

> Unsafe export preview must stop at preview time, not after export.

---

## 26. Preview Copy Control Semantics

Copy controls must distinguish safe copy from unsafe copy.

Allowed copy controls:

```yaml
allowed_copy_controls:
  copy_authority_envelope:
    allowed: true
  copy_no_decision_object:
    allowed: true
  copy_synthetic_boundary:
    allowed: true
  copy_safe_export_preview:
    allowed: true
    requires_safe_preview_available: true
  copy_audit_event_id:
    allowed: true
```

Blocked copy controls:

```yaml
blocked_copy_controls:
  copy_unsafe_red_team_phrase:
    allowed: false
  copy_blocked_preview:
    allowed: false
  copy_diagnosis_language:
    allowed: false
  copy_exclusion_language:
    allowed: false
  copy_treatment_language:
    allowed: false
  copy_order_language:
    allowed: false
  copy_follow_up_language:
    allowed: false
  copy_triage_language:
    allowed: false
  copy_patient_facing_language:
    allowed: false
```

Copy control rule:

> Copy controls must not become a route around fail-closed safety.

---

## 27. Preview Export Control Semantics

Export controls must remain preview-only unless all safety checks pass.

Allowed export control states:

| State | Meaning |
|---|---|
| preview_disabled | Safety check not complete |
| preview_blocked | Unsafe state detected |
| preview_available | Safe non-clinical preview available |
| export_copy_allowed | Safe copy allowed only for safe preview |
| audit_available | Traceability available |

Blocked export control states:

| State | Reason |
|---|---|
| clinical_export_available | clinical report risk |
| patient_export_available | patient-facing risk |
| diagnostic_report_export | diagnostic authority risk |
| treatment_plan_export | treatment authority risk |
| public_publish_available | public readiness risk |
| product_release_available | product readiness risk |

Export control rule:

> Export controls must show preview safety state, not clinical readiness.

---

## 28. Red-Team Does Not Equal Clinical Validation

The UI must explicitly block interpretation of red-team success as clinical validation.

Required red-team disclaimer:

```text
Red-team fail-closed behavior demonstrates UI safety containment only. It does not validate clinical performance, diagnostic accuracy, treatment safety, workflow safety, or product readiness.
```

Blocked red-team claims:

- red-team passed means clinically safe,
- red-team passed means validated,
- red-team passed means product ready,
- red-team passed means public ready,
- red-team passed means diagnostic performance proven,
- red-team passed means expert-equivalent,
- red-team passed means MDD replacement.

Red-team validation rule:

> Passing a red-team UI safety check is not clinical validation.

---

## 29. Export Preview Does Not Equal MDD Consensus

The UI must explicitly block interpretation of export preview as MDD consensus.

Required MDD disclaimer:

```text
This preview is an MDD preparation package preview only. It does not represent MDD consensus, clinical agreement, final diagnosis, treatment plan, procedure decision, follow-up plan, or triage decision.
```

Blocked MDD claims:

- MDD consensus generated,
- MDD complete,
- MDD agrees,
- multidisciplinary diagnosis,
- final MDD decision,
- consensus treatment plan,
- consensus follow-up plan.

MDD preview rule:

> MDD preparation preview is not MDD outcome.

---

## 30. v0.15.4 Acceptance Criteria

v0.15.4 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| export preview object schema defined | true |
| red-team fail-closed object schema defined | true |
| safe export preview screen behavior defined | true |
| export preview section ordering defined | true |
| required export preview labels defined | true |
| blocked unsafe headings defined | true |
| blocked diagnosis/exclusion/action language defined | true |
| red-team unsafe phrase display rules defined | true |
| red-team scenario UI registry defined | true |
| fail-closed modal behavior defined | true |
| repair-required UI behavior defined | true |
| revalidation-required UI behavior defined | true |
| unsafe copy/export block defined | true |
| export preview safety state machine defined | true |
| safe export preview section semantics defined | true |
| red-team fail-closed screen behavior defined | true |
| safe alternative wording constraints defined | true |
| authority envelope in export preview required | true |
| no-decision object in export preview required | true |
| audit trace hooks for export preview defined | true |
| export preview fail-closed conditions defined | true |
| copy control semantics defined | true |
| export control semantics defined | true |
| red-team does not equal clinical validation | true |
| export preview does not equal MDD consensus | true |
| real patient data remains blocked | true |
| deidentified real patient data remains blocked | true |
| clinical validation remains blocked | true |
| diagnostic performance claim remains blocked | true |
| product readiness remains false | true |
| public readiness remains false | true |
| patient-facing use remains not_allowed | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| order/procedure/follow-up/triage authority remains none | true |
| MDD replacement remains blocked | true |

v0.15.4 acceptance rule:

> Export preview and red-team UI behavior are accepted only if unsafe content fails closed before it becomes reusable clinical output.

---

## 31. Next Step

The next recommended step is:

- v0.15.5 — Prototype Workspace Validation Checklist / UI Safety Gate

v0.15.5 should define:

- prototype workspace validation checklist,
- screen/component safety validation,
- synthetic-only validation,
- real patient data block validation,
- visual safety validation,
- reasoning map safety validation,
- export preview safety validation,
- red-team fail-closed validation,
- authority envelope validation,
- no-decision object validation,
- audit trace validation,
- public/product readiness overclaim validation,
- patient-facing leak validation,
- clinical validation overclaim block,
- final v0.15 pre-seal safety gate.

v0.15.5 must not open clinical deployment, real patient data, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 32. Governance Statement

This document defines demo export preview and red-team fail-closed UI behavior for the prototype workspace.

It does not diagnose.  
It does not treat.  
It does not validate clinical performance.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import real clinical reports.  
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.15.4 governance discipline is:

> “Do not let export preview become a clinical report.”

The red-team governance discipline is:

> “Do not let blocked unsafe language become reusable output.”