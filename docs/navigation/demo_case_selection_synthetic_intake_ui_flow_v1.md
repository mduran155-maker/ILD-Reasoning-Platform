# ILD Reasoning Platform — Demo Case Selection / Synthetic Intake UI Flow v1

Version: v0.15.2  
Status: demo_case_selection_synthetic_intake_ui_flow  
Scope: Prototype entry flow, synthetic demo case selection flow, synthetic intake review flow, supplied-vs-missing field interaction, synthetic fixture binding to workspace state, blocked real patient data flow, blocked DICOM/report import flow, audit trace for selection and intake review, and transition into reasoning map and evidence panels  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.15.2 — Demo Case Selection / Synthetic Intake UI Flow.

v0.15.2 converts the v0.15.0 prototype workspace entry gate and the v0.15.1 screen/component behavior schema into a safe prototype navigation flow.

This document defines how a reviewer may move from:

```text
prototype boundary landing screen
→ synthetic demo case selector
→ selected synthetic demo case state
→ synthetic intake review
→ supplied-vs-missing field visibility
→ synthetic fixture binding
→ reasoning map and evidence panels
```

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

Its purpose is to define a safe synthetic-only UI flow that demonstrates prototype behavior without opening clinical use.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.15.2 flow principle is:

> “A prototype flow may move through synthetic reasoning states, but it must not become a clinical intake pathway.”

---

## 2. Relationship to Prior v0.15 Steps

v0.15.2 inherits:

- v0.15.0 — Prototype Workspace / Demo UI Behavior Contract Entry Gate,
- v0.15.1 — Demo Workspace Screen / Component Behavior Schema.

v0.15.0 opened the prototype workspace UI behavior boundary.

v0.15.1 defined allowed prototype screens and components.

v0.15.2 defines how the user may safely move through those screens.

v0.15.2 does not broaden v0.15.0 or v0.15.1.

v0.15.2 must not open:

- real patient data,
- deidentified real patient data,
- real case upload,
- DICOM import,
- real report paste,
- diagnostic output,
- disease ranking,
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

Flow inheritance rule:

> The prototype flow may connect safe screens, but it may not create unsafe clinical capability.

---

## 3. Global Authority Envelope

Every flow state must inherit the following authority envelope.

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

No transition, selector state, intake review state, fixture binding state, reasoning map transition, evidence panel transition, audit event, button, disabled control, warning, modal, or preview may override this envelope.

Authority flow rule:

> A flow transition cannot grant authority that a screen does not have.

---

## 4. Global No-Decision Object

The following no-decision object remains active throughout the flow.

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

No-decision flow rule:

> Moving forward in the prototype must never imply that a decision has been made.

---

## 5. v0.15.2 Flow Map

The permitted v0.15.2 flow is:

```text
FLOW_001: open_prototype_workspace
  → FLOW_002: acknowledge_prototype_boundary
  → FLOW_003: view_synthetic_demo_case_selector
  → FLOW_004: filter_or_inspect_synthetic_demo_cases
  → FLOW_005: select_synthetic_demo_case
  → FLOW_006: bind_selected_synthetic_fixture
  → FLOW_007: view_synthetic_intake_review
  → FLOW_008: inspect_supplied_fields
  → FLOW_009: inspect_missing_fields
  → FLOW_010: confirm_synthetic_only_context
  → FLOW_011: transition_to_reasoning_map
  → FLOW_012: transition_to_evidence_panels
```

The following flow is blocked:

```text
open_prototype_workspace
  → upload_real_patient_case
  → import_dicom
  → paste_real_report
  → generate_diagnosis
  → export_clinical_report
```

Flow map rule:

> The only allowed forward path begins with prototype boundary acknowledgement and remains synthetic-only until workspace reasoning visibility.

---

## 6. Flow State Object Schema

Every flow state must conform to the following schema.

```yaml
prototype_flow_state:
  flow_state_id: string
  version: v0.15.2
  parent_screen_id: string
  state_name: string
  state_category: enum
  prototype_only: true
  synthetic_demo_only: true
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  allowed_next_states: list
  blocked_next_states: list
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_event: true
  required_fail_closed_behavior: true
```

Allowed state categories:

| State Category | Meaning |
|---|---|
| boundary_state | Prototype/non-clinical limit displayed |
| selector_state | Synthetic demo cases listed or inspected |
| selection_state | One sealed synthetic case selected |
| fixture_binding_state | Synthetic fixture bound to workspace state |
| intake_review_state | Fictional supplied/missing fields displayed |
| evidence_visibility_state | Missing/source/mimic/overlap state inspected |
| reasoning_transition_state | Safe transition to reasoning map |
| blocked_attempt_state | Unsafe clinical pathway blocked |
| audit_state | Traceability event recorded |

Flow state rule:

> A valid state must either preserve synthetic visibility or block unsafe clinical transition.

---

## 7. Prototype Entry Flow

The prototype entry flow begins at the landing screen.

Required entry behavior:

```yaml
entry_flow:
  starts_at: V15_SCREEN_001
  first_required_display:
    - synthetic_demo_only_banner
    - not_for_clinical_use_banner
    - not_patient_facing_banner
    - public_ready_false_label
    - product_ready_false_label
    - authority_envelope_card
    - no_decision_object_card
  entry_acknowledgement_required: true
  entry_acknowledgement_text: "I understand this is a synthetic, non-clinical prototype behavior demonstration."
  clinical_use_acknowledgement_allowed: false
```

Allowed entry actions:

- view prototype boundary,
- inspect authority envelope,
- inspect no-decision object,
- proceed to synthetic demo case selector after boundary acknowledgement.

Blocked entry actions:

- skip boundary,
- hide authority envelope,
- enter clinical mode,
- upload real patient data,
- import DICOM,
- paste real report,
- generate diagnosis,
- open patient-facing view.

Entry rule:

> The prototype must show the boundary before it shows the demo.

---

## 8. Synthetic Demo Case Selector Flow

The selector flow may list only sealed synthetic demo cases.

Required selector behavior:

```yaml
synthetic_demo_case_selector_flow:
  screen_id: V15_SCREEN_002
  allowed_case_origin: sealed_synthetic_demo_fixture_only
  real_case_origin_allowed: false
  deidentified_real_case_origin_allowed: false
  diagnostic_ground_truth_visible: false
  final_diagnosis_visible: false
  disease_probability_visible: false
  required_case_card_fields:
    - demo_case_id
    - demo_case_title
    - governance_behavior_demonstrated
    - synthetic_only_status
    - real_patient_data_false_status
    - clinical_validation_false_status
    - patient_facing_use_not_allowed_status
    - available_fixture_set
```

Allowed selector actions:

- view synthetic cases,
- filter by governance behavior,
- sort by demo category,
- inspect demo fixture metadata,
- select one synthetic demo case.

Blocked selector actions:

- upload real case,
- upload deidentified real case,
- import HRCT image,
- import DICOM,
- paste real report,
- show final diagnosis,
- show diagnostic ground truth,
- show disease probability,
- mark case clinically validated.

Selector flow rule:

> The selector chooses governance demonstrations, not clinical cases.

---

## 9. Synthetic Case Selection State

When a synthetic case is selected, the workspace must create a selected synthetic case state.

Required selected case object:

```yaml
selected_synthetic_demo_case_state:
  selected_case_id: string
  selected_case_title: string
  selected_case_origin: synthetic_demo_fixture
  selected_case_real_patient_data: false
  selected_case_deidentified_real_patient_data: false
  selected_case_clinical_validation_use: false
  selected_case_patient_facing_use: not_allowed
  selected_case_diagnostic_ground_truth: not_available
  selected_case_final_diagnosis: not_available
  selected_case_disease_probability: not_available
  selected_case_authority_effect: none
  selected_case_decision_effect: none
  selected_case_audit_event_required: true
```

Selection may trigger:

- synthetic fixture binding,
- intake review state,
- audit trace event,
- authority envelope persistence,
- no-decision object persistence.

Selection may not trigger:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment recommendation,
- test order,
- procedure recommendation,
- follow-up schedule,
- triage,
- export generation,
- clinical validation state.

Selection rule:

> Selecting a synthetic case selects a demo fixture, not a diagnosis problem to solve.

---

## 10. Synthetic Fixture Binding Flow

The selected synthetic case may bind to sealed demo fixtures.

Allowed fixture bindings:

| Fixture | Allowed Binding Meaning |
|---|---|
| synthetic_demo_case_object | fictional governance test object |
| demo_reasoning_session_object | synthetic reasoning session fixture |
| demo_intake_binding_fixture | synthetic field-to-session binding |
| demo_workspace_state_fixture | synthetic workspace visibility state |
| demo_structured_output_fixture | structured output demonstration |
| demo_case_snapshot_fixture | synthetic non-final snapshot |
| demo_revision_history_fixture | synthetic state movement record |
| demo_safe_export_fixture | non-diagnostic export mechanics fixture |
| demo_MDD_preparation_package_fixture | MDD preparation demonstration |
| demo_unsafe_export_failure_fixture | fail-closed behavior fixture |
| demo_audit_event_fixture | traceability fixture |
| demo_authority_envelope_fixture | non-authority boundary fixture |
| demo_no_decision_object_fixture | explicit decision-block fixture |
| demo_visual_artifact_fixture | explanatory-only visual support |

Blocked fixture bindings:

- real patient object,
- deidentified patient object,
- real DICOM object,
- real report object,
- clinical validation object,
- diagnostic ground truth object,
- product readiness object,
- public readiness object,
- patient-facing report object,
- MDD consensus object.

Fixture binding rule:

> Fixture binding connects synthetic demo objects only; it does not create clinical case state.

---

## 11. Demo Intake Review Flow

The demo intake review screen displays fictional supplied and missing fields.

Required intake review behavior:

```yaml
demo_intake_review_flow:
  screen_id: V15_SCREEN_003
  data_origin: synthetic_fixture_only
  real_patient_data_allowed: false
  edit_as_real_case_allowed: false
  clinical_submission_allowed: false
  required_sections:
    - supplied_fictional_fields
    - missing_fictional_fields
    - provided_vs_inferred_boundary
    - source_status_summary
    - missing_evidence_summary
    - synthetic_only_label
    - no_real_patient_data_label
    - authority_envelope_footer
    - audit_trace_hook
```

Allowed intake review actions:

- inspect supplied fictional fields,
- inspect missing fictional fields,
- inspect provided-vs-inferred boundary,
- inspect source status,
- inspect missing evidence summary,
- proceed to reasoning map,
- proceed to evidence panels.

Blocked intake review actions:

- edit real patient fields,
- paste report text,
- import image,
- import DICOM,
- infer missing field automatically,
- convert missing field to negative,
- convert supplied fictional field to diagnosis,
- create clinical note,
- order test,
- schedule follow-up.

Demo intake rule:

> Intake review shows fictional input state; it does not collect clinical data.

---

## 12. Supplied Field Interaction

Supplied fictional fields may be inspected but not transformed into clinical decisions.

Allowed supplied field interaction:

```yaml
supplied_field_interaction:
  view_supplied_field: true
  expand_field_explanation: true
  show_field_origin: synthetic_fixture
  show_field_source_status: allowed_if_available
  show_field_limitations: true
  edit_field_as_clinical_data: false
  use_field_for_diagnosis: false
  use_field_for_treatment: false
  use_field_for_order: false
```

Blocked supplied field interpretation:

- supplied exposure history confirms HP,
- supplied CTD/SARD context confirms CTD-ILD,
- supplied oncology context confirms malignancy,
- supplied microbiology context excludes infection,
- supplied prior CT confirms stability/progression by itself,
- supplied pattern family becomes final diagnosis,
- supplied field authorizes treatment or ordering.

Supplied field rule:

> Supplied fictional fields can explain demo state, not decide clinical meaning.

---

## 13. Missing Field Interaction

Missing fictional fields must remain visible as missing.

Allowed missing field interaction:

```yaml
missing_field_interaction:
  view_missing_field: true
  expand_missing_reason: true
  show_interpretation_limiter: true
  show_related_mimic_visibility: allowed_if_relevant
  show_related_source_status: allowed_if_relevant
  convert_missing_to_negative: false
  infer_missing_value: false
  hide_missing_field: false
```

Blocked missing field interpretation:

- missing exposure history means no HP,
- missing CTD/SARD context means no CTD-ILD,
- missing microbiology means no infection,
- missing oncology context means no malignancy,
- missing prior CT means stable disease,
- missing pathology means no uncertainty,
- missing review means clinical closure.

Missing field rule:

> Missing fields remain missing; missingness never becomes exclusion.

---

## 14. Blocked Real Patient Data Flow

Any attempt to introduce real patient data must fail closed.

Blocked real patient data attempts:

```yaml
blocked_real_patient_data_flow:
  upload_real_patient_file:
    allowed: false
    result: blocked_attempt_state
    audit_required: true
  upload_deidentified_patient_file:
    allowed: false
    result: blocked_attempt_state
    audit_required: true
  paste_real_report:
    allowed: false
    result: blocked_attempt_state
    audit_required: true
  enter_patient_identifier:
    allowed: false
    result: blocked_attempt_state
    audit_required: true
  import_dicom:
    allowed: false
    result: blocked_attempt_state
    audit_required: true
  import_hrct_image:
    allowed: false
    result: blocked_attempt_state
    audit_required: true
```

Required blocked-state message:

```text
Real patient data is not allowed in this prototype demo workspace. This workspace is limited to sealed synthetic demo fixtures and does not support clinical use, patient-facing use, public readiness, product readiness, or clinical validation.
```

Real patient data rule:

> The prototype must block real patient data before it becomes workspace state.

---

## 15. Blocked DICOM / Report Import Flow

The prototype workspace must not expose DICOM or report import as available clinical features.

Blocked import controls:

| Attempted Control | Required State |
|---|---|
| Import DICOM | disabled_or_absent |
| Upload HRCT | disabled_or_absent |
| Paste radiology report | disabled_or_absent |
| Import pathology report | disabled_or_absent |
| Import lab report | disabled_or_absent |
| Upload MDD note | disabled_or_absent |
| Connect PACS | disabled_or_absent |
| Connect EHR | disabled_or_absent |

If shown as disabled prototype controls, each must explain:

- clinical import is not opened,
- real patient data is not allowed,
- prototype is synthetic-only,
- no diagnostic authority exists,
- no clinical validation is claimed.

Import flow rule:

> A disabled import control must teach the boundary; it must not imply hidden clinical capability.

---

## 16. Audit Trace for Selection and Intake

Every selection and intake review transition must emit an audit event.

Required audit events:

```yaml
audit_events:
  prototype_boundary_viewed:
    authority_effect: none
    decision_effect: none
  prototype_boundary_acknowledged:
    authority_effect: none
    decision_effect: none
  synthetic_case_selector_viewed:
    authority_effect: none
    decision_effect: none
  synthetic_case_inspected:
    authority_effect: none
    decision_effect: none
  synthetic_case_selected:
    authority_effect: none
    decision_effect: none
  synthetic_fixture_bound:
    authority_effect: none
    decision_effect: none
  demo_intake_review_viewed:
    authority_effect: none
    decision_effect: none
  supplied_field_inspected:
    authority_effect: none
    decision_effect: none
  missing_field_inspected:
    authority_effect: none
    decision_effect: none
  real_patient_data_attempt_blocked:
    authority_effect: none
    decision_effect: none
  dicom_import_attempt_blocked:
    authority_effect: none
    decision_effect: none
  report_paste_attempt_blocked:
    authority_effect: none
    decision_effect: none
```

Blocked audit meanings:

- diagnosis validated,
- clinical correctness proven,
- performance measured,
- treatment authorized,
- order authorized,
- procedure authorized,
- follow-up scheduled,
- triage assigned,
- MDD consensus achieved.

Audit rule:

> Audit records traceability of prototype state, not correctness of clinical reasoning.

---

## 17. Transition to Reasoning Map

The prototype may transition from synthetic intake review to reasoning map only after safe synthetic fixture binding.

Required transition conditions:

```yaml
transition_to_reasoning_map:
  selected_synthetic_demo_case_present: true
  synthetic_fixture_bound: true
  real_patient_data_absent: true
  deidentified_real_patient_data_absent: true
  authority_envelope_present: true
  no_decision_object_present: true
  audit_trace_active: true
  visual_safety_label_available: true
```

Allowed transition result:

- reasoning map screen opens,
- synthetic case context node visible,
- missing evidence node visible,
- mimic visibility node visible where relevant,
- overlap node visible where relevant,
- source status node visible,
- confidence limiter node visible,
- authority envelope node visible,
- no-decision node visible,
- audit trace hook active.

Blocked transition result:

- final diagnosis node,
- probability edge,
- disease winner node,
- treatment action node,
- test order node,
- procedure node,
- follow-up node,
- triage node,
- MDD consensus node.

Reasoning map transition rule:

> Transition to the reasoning map displays governed relationships, not diagnostic conclusions.

---

## 18. Transition to Evidence Panels

The prototype may transition from synthetic intake review or reasoning map into evidence panels.

Allowed evidence panel transitions:

```yaml
evidence_panel_transitions:
  missing_evidence_panel:
    allowed: true
    requires_missing_field_state: true
  mimic_visibility_panel:
    allowed: true
    requires_mimic_visibility_fixture: true
  overlap_panel:
    allowed: true
    requires_overlap_fixture: true
  source_status_panel:
    allowed: true
    requires_source_status_fixture: true
  confidence_limiter_panel:
    allowed: true
    requires_limitation_state: true
  review_prompt_panel:
    allowed: true
    requires_review_prompt_fixture: true
```

Blocked evidence panel transitions:

- diagnosis panel,
- disease ranking panel,
- probability panel,
- treatment panel,
- order panel,
- procedure panel,
- follow-up panel,
- triage panel,
- patient summary panel.

Evidence panel transition rule:

> Evidence panels display limitations and visibility, not recommendations.

---

## 19. Selection Flow Fail-Closed Conditions

The selection flow must fail closed under the following conditions.

```yaml
selection_flow_fail_closed_conditions:
  no_synthetic_case_selected:
    transition_to_intake_review: false
    transition_to_reasoning_map: false
    audit_required: true
  selected_case_not_synthetic:
    workspace_state_creation: false
    audit_required: true
  selected_case_has_real_patient_marker:
    workspace_state_creation: false
    audit_required: true
  selected_case_claims_clinical_validation:
    workspace_state_creation: false
    audit_required: true
  selected_case_has_final_diagnosis_field:
    workspace_state_creation: false
    audit_required: true
  selected_case_has_probability_field:
    workspace_state_creation: false
    audit_required: true
  authority_envelope_missing:
    transition_allowed: false
    repair_required: true
    audit_required: true
  no_decision_object_missing:
    transition_allowed: false
    repair_required: true
    audit_required: true
```

Selection fail-closed rule:

> A case that does not preserve synthetic non-authority cannot enter the prototype workspace.

---

## 20. Intake Flow Fail-Closed Conditions

The intake flow must fail closed under the following conditions.

```yaml
intake_flow_fail_closed_conditions:
  real_patient_data_detected:
    intake_allowed: false
    workspace_allowed: false
    audit_required: true
  deidentified_real_patient_data_detected:
    intake_allowed: false
    workspace_allowed: false
    audit_required: true
  dicom_import_attempted:
    import_allowed: false
    workspace_allowed: false
    audit_required: true
  report_paste_attempted:
    paste_allowed: false
    workspace_allowed: false
    audit_required: true
  missing_field_autoinference_attempted:
    inference_allowed: false
    repair_required: true
    audit_required: true
  missing_field_converted_to_negative:
    transition_allowed: false
    repair_required: true
    audit_required: true
  supplied_field_converted_to_diagnosis:
    transition_allowed: false
    repair_required: true
    audit_required: true
  unsafe_clinical_language_detected:
    transition_allowed: false
    repair_required: true
    audit_required: true
```

Intake fail-closed rule:

> Unsafe intake behavior must stop before it contaminates reasoning state.

---

## 21. Allowed Prototype Flow Actions

The following flow actions are allowed.

| Action | Allowed Meaning |
|---|---|
| acknowledge_prototype_boundary | Confirm awareness of synthetic prototype limits |
| view_synthetic_demo_case_selector | Open sealed synthetic case list |
| filter_synthetic_cases | Filter fictional demo cases by governance behavior |
| inspect_synthetic_case_metadata | Inspect synthetic fixture metadata |
| select_synthetic_demo_case | Select one fictional governance scenario |
| bind_synthetic_fixture | Bind sealed synthetic fixture to workspace state |
| view_demo_intake_review | Review fictional supplied/missing fields |
| inspect_supplied_field | Inspect fictional supplied field |
| inspect_missing_field | Inspect missing field limiter |
| inspect_source_status | Inspect source role and limitation |
| inspect_authority_envelope | Inspect non-authority boundary |
| inspect_no_decision_object | Inspect explicit decisions not made |
| proceed_to_reasoning_map | Open reasoning visibility map |
| proceed_to_evidence_panel | Open missing/mimic/overlap/source panels |
| inspect_audit_trace | Inspect traceability event |

Allowed flow action rule:

> Allowed flow actions inspect and connect synthetic state; they do not act clinically.

---

## 22. Blocked Prototype Flow Actions

The following flow actions are blocked.

| Blocked Action | Reason |
|---|---|
| skip_boundary_acknowledgement | prototype boundary must be seen first |
| select_real_patient_case | real patient data blocked |
| select_deidentified_real_case | deidentified real patient data blocked |
| upload_dicom | clinical imaging import blocked |
| paste_real_report | real report ingestion blocked |
| enter_patient_identifier | patient identifier blocked |
| infer_missing_field | missingness must remain visible |
| convert_missing_to_negative | missing evidence cannot exclude disease |
| generate_final_diagnosis | diagnostic authority blocked |
| rank_diagnoses | probability/ranking blocked |
| confirm_mimic | diagnostic authority blocked |
| exclude_mimic | exclusion authority blocked |
| recommend_treatment | treatment authority blocked |
| order_test | order authority blocked |
| recommend_procedure | procedure authority blocked |
| schedule_follow_up | follow-up authority blocked |
| assign_triage | triage authority blocked |
| generate_patient_summary | patient-facing output blocked |
| mark_case_clinically_validated | clinical validation not opened |
| mark_workspace_product_ready | product readiness false |
| publish_public_workspace | public readiness false |
| generate_mdd_consensus | MDD replacement blocked |

Blocked flow action rule:

> A flow action is blocked if it would make the prototype behave like clinical software.

---

## 23. UI Copy Requirements for Flow Steps

Every major flow step must display safe copy.

Required copy examples:

| Flow Step | Required Copy |
|---|---|
| Prototype landing | “Synthetic demo only. Not for clinical use.” |
| Case selector | “Select a fictional governance scenario.” |
| Case selected | “This selection binds a synthetic fixture, not a patient case.” |
| Intake review | “These fields are fictional and non-clinical.” |
| Missing field | “Missing evidence limits interpretation; it does not exclude disease.” |
| Source status | “Source status shows role and limitation; it does not grant authority.” |
| Reasoning map transition | “The map shows governed relationships, not diagnostic proof.” |
| Evidence panel transition | “Panels show visibility and limitations, not recommendations.” |
| Blocked real data attempt | “Real patient data is not allowed in this prototype.” |

Blocked copy examples:

- “Start clinical case,”
- “Upload patient CT,”
- “Generate diagnosis,”
- “Confirm diagnosis,”
- “Rule out disease,”
- “Recommended treatment,”
- “Order next test,”
- “Schedule follow-up,”
- “Safe for outpatient care,”
- “Clinically validated,”
- “Product ready,”
- “Public ready.”

Copy rule:

> Flow copy must teach governance, not clinical action.

---

## 24. UI Navigation Constraints

Allowed navigation:

```text
landing
→ selector
→ intake review
→ reasoning map
→ evidence panels
→ safe export preview
→ audit trace
```

Allowed backward navigation:

```text
evidence panels
→ reasoning map
→ intake review
→ selector
→ landing
```

Blocked navigation:

```text
selector
→ diagnosis screen

intake review
→ clinical report

reasoning map
→ treatment pathway

evidence panel
→ order workflow

safe export preview
→ patient-facing report

audit trace
→ clinical validation dashboard
```

Navigation rule:

> Navigation may deepen visibility; it may not escalate authority.

---

## 25. Safe Flow Completion State

The flow may reach a completed prototype demo state.

Allowed completed state:

```yaml
prototype_demo_flow_completed:
  synthetic_case_selected: true
  synthetic_fixture_bound: true
  intake_review_viewed: true
  supplied_fields_inspected: optional
  missing_fields_inspected: optional
  reasoning_map_viewed: optional
  evidence_panels_viewed: optional
  safe_export_preview_viewed: optional
  audit_trace_available: true
  diagnosis_made: false
  disease_excluded: false
  treatment_selected: false
  test_ordered: false
  procedure_decided: false
  follow_up_scheduled: false
  triage_assigned: false
  mdd_consensus_generated: false
  patient_facing_output_generated: false
  clinical_validation_claimed: false
  product_ready_claimed: false
  public_ready_claimed: false
```

Completed flow rule:

> A completed prototype flow means the demo was navigated safely; it does not mean clinical reasoning was validated.

---

## 26. v0.15.2 Acceptance Criteria

v0.15.2 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| prototype entry flow defined | true |
| synthetic demo case selector flow defined | true |
| selected synthetic case state defined | true |
| synthetic fixture binding flow defined | true |
| demo intake review flow defined | true |
| supplied field interaction defined | true |
| missing field interaction defined | true |
| blocked real patient data flow defined | true |
| blocked DICOM/report import flow defined | true |
| audit trace for selection/intake defined | true |
| transition to reasoning map defined | true |
| transition to evidence panels defined | true |
| selection fail-closed conditions defined | true |
| intake fail-closed conditions defined | true |
| allowed prototype flow actions defined | true |
| blocked prototype flow actions defined | true |
| UI copy requirements defined | true |
| navigation constraints defined | true |
| safe flow completion state defined | true |
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

v0.15.2 acceptance rule:

> The flow is accepted only if it moves through synthetic demo state without creating clinical intake, clinical action, or clinical authority.

---

## 27. Next Step

The next recommended step is:

- v0.15.3 — Reasoning Map / Guided Visual Reasoning Interaction Contract

v0.15.3 should define:

- reasoning map node taxonomy,
- reasoning map edge semantics,
- visual hierarchy rules,
- non-probabilistic state display,
- missing evidence node behavior,
- mimic visibility node behavior,
- overlap node behavior,
- source status node behavior,
- confidence limiter node behavior,
- review prompt node behavior,
- authority envelope node behavior,
- no-decision node behavior,
- blocked visual ranking behavior,
- blocked diagnostic closure behavior,
- audit trace hooks for node expansion and navigation.

v0.15.3 must not open clinical deployment, real patient data, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 28. Governance Statement

This document defines the synthetic demo case selection and synthetic intake UI flow for the prototype workspace.

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

The v0.15.2 governance discipline is:

> “Do not let synthetic demo selection become clinical intake.”