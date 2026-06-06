# ILD Reasoning Platform — Synthetic Fixture Registry / Demo State Binding Plan v1

Version: v0.16.2  
Status: synthetic_fixture_registry_demo_state_binding_plan  
Scope: Synthetic fixture registry structure, allowed fixture IDs, synthetic case registry object, fixture-to-route binding, fixture-to-screen binding, fixture-to-component binding, demo state object planning, selected synthetic case state, synthetic intake state, reasoning map state, evidence panel state, safe export preview state, red-team scenario state, audit trace state, blocked real patient object categories, and fixture binding fail-closed conditions  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.16.2 — Synthetic Fixture Registry / Demo State Binding Plan.

v0.16.2 translates the sealed v0.15 synthetic demo architecture and the v0.16.1 internal prototype route registry into a source-governed synthetic fixture registry and demo state binding plan.

This document does not implement a clinical product.

It does not add new clinical content.

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
It does not import HRCT images.  
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define how synthetic demo fixtures may safely bind to internal prototype routes, screens, components, and UI states without becoming patient cases, clinical states, validation datasets, or diagnostic objects.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16.2 fixture principle is:

> “A fixture may demonstrate governed behavior, but it must not become a patient case.”

The v0.16.2 state principle is:

> “A demo state may drive internal prototype visibility, but it must not become clinical state.”

---

## 2. Relationship to v0.16.0 and v0.16.1

v0.16.2 inherits:

- v0.16.0 — Source-Governed Prototype Build Scaffold Entry Gate,
- v0.16.1 — Prototype Route / Screen Registry Implementation Plan.

v0.16.0 opened source-governed internal prototype build scaffold planning.

v0.16.1 defined allowed and blocked internal prototype routes and screen registry mapping.

v0.16.2 defines which synthetic fixtures and demo state objects may bind to those routes and screens.

v0.16.2 does not broaden v0.16.0 or v0.16.1.

v0.16.2 must not open:

- real patient data,
- deidentified real patient data,
- real clinical intake,
- DICOM import,
- HRCT import,
- real clinical report import,
- PACS integration,
- EHR integration,
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

Fixture inheritance rule:

> v0.16.2 may bind synthetic fixtures to prototype state only; it may not create clinical case state.

---

## 3. Global Authority Envelope

Every fixture, registry entry, state object, binding edge, fixture ID, route binding, screen binding, component binding, audit state, red-team state, export preview state, and validation stub must inherit the following authority envelope.

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
  dicom_import: not_allowed
  hrct_import: not_allowed
  real_report_import: not_allowed
  pacs_connection: not_allowed
  ehr_connection: not_allowed
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

No fixture or state object may override this envelope.

Authority fixture rule:

> A synthetic fixture cannot grant clinical authority by being selected, bound, displayed, previewed, exported, audited, or validated.

---

## 4. Global No-Decision Object

The following no-decision object must remain active across all fixture-bound demo states.

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

The no-decision object must be bindable to:

- selected synthetic case state,
- synthetic intake state,
- reasoning map state,
- evidence panel state,
- safe export preview state,
- red-team scenario state,
- audit trace state.

No-decision fixture rule:

> Every fixture-bound state must preserve what the platform did not decide.

---

## 5. Synthetic Fixture Registry Object Schema

The synthetic fixture registry must conform to the following schema.

```yaml
synthetic_fixture_registry:
  registry_id: string
  version: v0.16.2
  registry_name: string
  registry_scope: synthetic_internal_demo_only
  source_contract_version: string
  source_contract_file: string
  synthetic_only: true
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  real_report_import_allowed: false
  clinical_validation_use_allowed: false
  diagnostic_ground_truth_allowed: false
  product_readiness_effect: none
  public_readiness_effect: none
  patient_facing_effect: none
  authority_effect: none
  decision_effect: none
  allowed_fixture_types: list
  blocked_fixture_types: list
  required_authority_envelope: true
  required_no_decision_object: true
  required_audit_stub: true
  fail_closed_conditions: list
```

Synthetic fixture registry rule:

> The registry may contain only fictional governance fixtures, not clinical cases.

---

## 6. Synthetic Fixture Entry Schema

Every synthetic fixture entry must conform to the following schema.

```yaml
synthetic_fixture_entry:
  fixture_id: string
  fixture_type: enum
  fixture_title: string
  fixture_version: string
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  synthetic_only: true
  fictional_case_context: true
  real_patient_data: false
  deidentified_real_patient_data: false
  dicom_data_present: false
  hrct_image_present: false
  real_report_present: false
  clinical_validation_use: false
  diagnostic_ground_truth_present: false
  final_diagnosis_present: false
  probability_field_present: false
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  allowed_bindings: list
  blocked_bindings: list
  required_safety_labels: list
  required_audit_events: list
```

Fixture entry rule:

> A fixture entry is valid only if it remains synthetic, non-clinical, non-authoritative, and non-validating.

---

## 7. Allowed Fixture Types

The following fixture types are allowed.

| Fixture Type | Allowed Meaning |
|---|---|
| synthetic_demo_case | fictional governance test object |
| demo_case_pack | package of synthetic demo cases |
| demo_reasoning_session_object | synthetic reasoning session fixture |
| demo_intake_binding_fixture | synthetic field-to-session binding |
| demo_workspace_state_fixture | synthetic workspace visibility state |
| demo_structured_output_fixture | structured output demonstration |
| demo_case_snapshot_fixture | synthetic non-final snapshot |
| demo_revision_history_fixture | synthetic state movement record |
| demo_safe_export_fixture | non-diagnostic export mechanics fixture |
| demo_MDD_preparation_package_fixture | MDD preparation demonstration, not MDD result |
| demo_unsafe_export_failure_fixture | fail-closed behavior fixture |
| demo_audit_event_fixture | traceability fixture |
| demo_authority_envelope_fixture | non-authority boundary fixture |
| demo_no_decision_object_fixture | explicit decision-block fixture |
| demo_visual_artifact_fixture | explanatory-only visual support |
| demo_red_team_scenario_fixture | unsafe behavior containment demonstration |
| demo_route_state_fixture | synthetic route state for internal prototype |
| demo_screen_state_fixture | synthetic screen state for internal prototype |
| demo_component_state_fixture | synthetic component state for internal prototype |

Allowed fixture type rule:

> Allowed fixtures demonstrate governance behavior; they do not represent patients.

---

## 8. Blocked Fixture Types

The following fixture types are blocked.

| Blocked Fixture Type | Reason |
|---|---|
| patient_case | real patient data blocked |
| deidentified_patient_case | deidentified real patient data blocked |
| dicom_study | DICOM import blocked |
| hrct_series | HRCT image import blocked |
| radiology_report | real report import blocked |
| pathology_report | real report import blocked |
| microbiology_report | real report import blocked |
| clinical_note | real clinical text blocked |
| mdd_note | real MDD text blocked |
| pacs_record | PACS integration blocked |
| ehr_record | EHR integration blocked |
| clinical_validation_case | clinical validation not opened |
| diagnostic_ground_truth_case | diagnostic ground truth blocked |
| performance_benchmark_case | diagnostic performance claim blocked |
| patient_facing_case | patient-facing use blocked |
| final_diagnosis_fixture | diagnostic authority blocked |
| treatment_plan_fixture | treatment authority blocked |
| test_order_fixture | test-order authority blocked |
| procedure_plan_fixture | procedure authority blocked |
| follow_up_plan_fixture | follow-up authority blocked |
| triage_fixture | triage authority blocked |
| mdd_consensus_fixture | MDD replacement blocked |

Blocked fixture rule:

> A blocked fixture cannot exist as a registry item, hidden item, placeholder, test item, or “future clinical fixture” in v0.16.

---

## 9. Synthetic Case Registry Object

The synthetic case registry must store fictional case scenarios only.

```yaml
synthetic_case_registry_object:
  registry_id: synthetic_demo_case_registry_v1
  version: v0.16.2
  case_origin: synthetic_fixture_only
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  clinical_validation_use_allowed: false
  diagnostic_ground_truth_allowed: false
  final_diagnosis_allowed: false
  probability_field_allowed: false
  allowed_case_fields:
    - synthetic_case_id
    - synthetic_case_title
    - governance_behavior_demonstrated
    - fictional_context_summary
    - supplied_fictional_fields
    - missing_fictional_fields
    - source_status_prompts
    - mimic_visibility_prompts
    - overlap_prompts
    - confidence_limiter_prompts
    - review_visibility_prompts
    - linked_fixture_ids
    - safety_labels
    - authority_envelope
    - no_decision_object
    - audit_seed_events
```

Blocked case fields:

- patient name,
- date of birth,
- MRN,
- accession number,
- institution identifier,
- DICOM UID,
- real report text,
- real HRCT image reference,
- final diagnosis,
- diagnostic ground truth,
- disease probability,
- treatment plan,
- order plan,
- procedure plan,
- follow-up plan,
- triage/disposition,
- MDD consensus,
- clinical validation status.

Synthetic case registry rule:

> A synthetic case may describe governance behavior, not clinical truth.

---

## 10. Allowed Fixture ID Rules

Fixture IDs must be synthetic and non-patient-like.

Allowed fixture ID patterns:

```yaml
allowed_fixture_id_patterns:
  synthetic_demo_case: "SYN_DEMO_CASE_[number]"
  demo_reasoning_session: "SYN_REASONING_SESSION_[number]"
  demo_intake_binding: "SYN_INTAKE_BINDING_[number]"
  demo_workspace_state: "SYN_WORKSPACE_STATE_[number]"
  demo_export_preview: "SYN_EXPORT_PREVIEW_[number]"
  demo_red_team_scenario: "SYN_RED_TEAM_[number]"
  demo_audit_event: "SYN_AUDIT_EVENT_[number]"
```

Blocked fixture ID patterns:

- MRN-like identifiers,
- accession-like identifiers,
- DICOM UID-like identifiers,
- institution case IDs,
- patient initials,
- date-of-birth-derived IDs,
- real hospital sequence IDs,
- clinical trial participant IDs,
- external validation dataset IDs.

Fixture ID rule:

> Fixture IDs must signal synthetic governance identity, not patient identity.

---

## 11. Demo State Object Schema

Every demo state object must conform to the following schema.

```yaml
demo_state_object:
  demo_state_id: string
  version: v0.16.2
  state_type: enum
  parent_fixture_id: string
  parent_route_id: string
  parent_screen_id: string
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  synthetic_only: true
  real_patient_data: false
  deidentified_real_patient_data: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
  allowed_transitions: list
  blocked_transitions: list
  fail_closed_conditions: list
```

Allowed demo state types:

- selected_synthetic_case_state,
- synthetic_intake_state,
- reasoning_map_state,
- evidence_panel_state,
- safe_export_preview_state,
- red_team_scenario_state,
- audit_trace_state,
- safety_reference_state.

Demo state rule:

> Demo state may organize prototype visibility; it may not become clinical state.

---

## 12. Selected Synthetic Case State

The selected synthetic case state binds one synthetic case to the prototype session.

```yaml
selected_synthetic_case_state:
  state_id: string
  state_type: selected_synthetic_case_state
  selected_synthetic_case_id: string
  selected_case_origin: synthetic_demo_case_registry
  selected_case_real_patient_data: false
  selected_case_deidentified_real_patient_data: false
  selected_case_clinical_validation_use: false
  selected_case_diagnostic_ground_truth: not_available
  selected_case_final_diagnosis: not_available
  selected_case_probability_field: not_available
  selected_case_authority_effect: none
  selected_case_decision_effect: none
  bound_route_ids:
    - ROUTE_003
    - ROUTE_004
    - ROUTE_005
    - ROUTE_012
    - ROUTE_015
  required_audit_event: synthetic_case_selected
```

Allowed selected case behavior:

- bind to synthetic intake review,
- bind to reasoning map,
- bind to evidence panels,
- bind to safe export preview,
- bind to audit trace.

Blocked selected case behavior:

- generate diagnosis,
- expose ground truth,
- rank diseases,
- trigger treatment,
- trigger order,
- trigger procedure,
- trigger follow-up,
- trigger triage,
- create patient-facing output,
- create clinical validation state.

Selected case rule:

> Selecting a synthetic case creates demo context, not clinical reasoning authority.

---

## 13. Synthetic Intake State

The synthetic intake state displays fictional supplied and missing fields.

```yaml
synthetic_intake_state:
  state_id: string
  state_type: synthetic_intake_state
  parent_synthetic_case_id: string
  route_id: ROUTE_003
  screen_id: V15_SCREEN_003
  data_origin: synthetic_fixture_only
  supplied_fields: list
  missing_fields: list
  provided_vs_inferred_boundary_required: true
  real_patient_data_allowed: false
  field_edit_as_clinical_data_allowed: false
  missing_field_autoinference_allowed: false
  missing_to_negative_conversion_allowed: false
  supplied_field_to_diagnosis_conversion_allowed: false
  required_audit_events:
    - demo_intake_review_viewed
    - supplied_field_inspected
    - missing_field_inspected
```

Allowed intake state behavior:

- show supplied fictional field,
- show missing fictional field,
- show provided-vs-inferred boundary,
- show source status summary,
- show missing evidence summary.

Blocked intake state behavior:

- collect patient data,
- paste report text,
- import DICOM,
- infer missing field,
- convert missing to negative,
- convert supplied field to diagnosis,
- order test,
- schedule follow-up.

Synthetic intake rule:

> Synthetic intake state displays fictional field visibility; it does not collect clinical evidence.

---

## 14. Reasoning Map State

The reasoning map state binds synthetic reasoning objects to visual map nodes and edges.

```yaml
reasoning_map_state:
  state_id: string
  state_type: reasoning_map_state
  parent_synthetic_case_id: string
  route_id: ROUTE_004
  screen_id: V15_SCREEN_004
  data_origin: synthetic_fixture_only
  visual_semantics: text_governed
  probability_display_allowed: false
  ranking_display_allowed: false
  diagnostic_closure_allowed: false
  treatment_pathway_allowed: false
  allowed_node_sources:
    - synthetic_case_context
    - supplied_fields
    - missing_evidence
    - temporal_limiter
    - source_status
    - mimic_visibility
    - overlap
    - confidence_limiter
    - review_prompt
    - authority_envelope
    - no_decision_object
    - audit_trace
    - visual_safety_label
  blocked_node_sources:
    - final_diagnosis
    - disease_probability
    - disease_ranking
    - disease_rule_out
    - treatment_plan
    - test_order
    - procedure_plan
    - follow_up_plan
    - triage_disposition
    - mdd_consensus
    - clinical_validation
```

Required audit events:

- reasoning_map_opened,
- reasoning_map_node_expanded,
- reasoning_map_edge_viewed,
- unsafe_map_state_blocked.

Reasoning map state rule:

> Reasoning map state may display governed relationships; it may not create diagnostic proof.

---

## 15. Evidence Panel State

The evidence panel state binds missing, mimic, overlap, source, confidence, and review prompt visibility.

```yaml
evidence_panel_state:
  state_id: string
  state_type: evidence_panel_state
  parent_synthetic_case_id: string
  route_ids:
    - ROUTE_005
    - ROUTE_006
    - ROUTE_007
    - ROUTE_008
    - ROUTE_009
    - ROUTE_010
    - ROUTE_011
  data_origin: synthetic_fixture_only
  allowed_panel_states:
    - missing_evidence_visibility
    - mimic_visibility
    - overlap_visibility
    - source_status_visibility
    - confidence_limiter_visibility
    - review_prompt_visibility
  blocked_panel_states:
    - diagnosis
    - disease_exclusion
    - mimic_exclusion
    - treatment_recommendation
    - test_order
    - procedure_recommendation
    - follow_up_schedule
    - triage_decision
```

Required audit events:

- evidence_panel_hub_opened,
- missing_evidence_panel_opened,
- mimic_visibility_panel_opened,
- overlap_panel_opened,
- source_status_panel_opened,
- confidence_limiter_panel_opened,
- review_prompt_panel_opened.

Evidence panel rule:

> Evidence panel state preserves visibility and limitation, not recommendations.

---

## 16. Safe Export Preview State

The safe export preview state binds synthetic fixture content to non-clinical preview sections.

```yaml
safe_export_preview_state:
  state_id: string
  state_type: safe_export_preview_state
  parent_synthetic_case_id: string
  route_id: ROUTE_012
  screen_id: V15_SCREEN_012
  export_type: mdd_preparation_preview_only
  clinical_report: false
  diagnostic_report: false
  patient_summary: false
  mdd_consensus: false
  required_sections:
    - synthetic_demo_boundary
    - non_clinical_use_boundary
    - authority_envelope
    - no_decision_object
    - source_status_summary
    - supplied_context_summary
    - missing_evidence_summary
    - mimic_visibility_summary
    - overlap_visibility_summary
    - confidence_limiter_summary
    - review_prompt_visibility
    - audit_trace_references
    - export_safety_state
  blocked_sections:
    - impression
    - diagnosis
    - final_diagnosis
    - diagnostic_conclusion
    - treatment_plan
    - order_plan
    - procedure_recommendation
    - follow_up_schedule
    - triage_disposition
    - patient_summary
    - mdd_consensus
    - clinical_validation_result
```

Required audit events:

- export_preview_requested,
- export_safety_check_started,
- safe_preview_available,
- export_preview_blocked,
- unsafe_copy_attempt_blocked,
- unsafe_export_attempt_blocked.

Safe export preview rule:

> Export preview state may show safe structure; it may not become a clinical report state.

---

## 17. Red-Team Scenario State

The red-team scenario state binds unsafe examples to fail-closed demonstration behavior.

```yaml
red_team_scenario_state:
  state_id: string
  state_type: red_team_scenario_state
  parent_red_team_fixture_id: string
  route_ids:
    - ROUTE_013
    - ROUTE_014
  unsafe_example_visible: quarantined_only
  copy_allowed: false
  export_allowed: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  failure_reason_required: true
  repair_required: true
  ui_safety_revalidation_required: conditional_required
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
```

Allowed red-team state behavior:

- show unsafe attempt category,
- show blocked badge,
- show failure reason,
- show quarantined unsafe example,
- show repair required,
- show UI safety revalidation required,
- show copy/export disabled,
- record audit event.

Blocked red-team state behavior:

- make unsafe phrase reusable,
- make unsafe phrase copyable,
- export unsafe phrase,
- frame unsafe phrase as advice,
- frame red-team pass as clinical validation,
- frame red-team pass as product readiness.

Red-team scenario rule:

> Red-team state demonstrates containment, not content.

---

## 18. Audit Trace State

The audit trace state binds synthetic UI events to traceability rows.

```yaml
audit_trace_state:
  state_id: string
  state_type: audit_trace_state
  parent_synthetic_case_id: string
  route_id: ROUTE_015
  screen_id: V15_SCREEN_015
  data_origin: synthetic_ui_event_stub_only
  clinical_correctness_claim: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  allowed_event_types:
    - prototype_boundary_viewed
    - synthetic_case_selector_viewed
    - synthetic_case_selected
    - synthetic_fixture_bound
    - demo_intake_review_viewed
    - supplied_field_inspected
    - missing_field_inspected
    - reasoning_map_opened
    - reasoning_map_node_expanded
    - evidence_panel_opened
    - export_preview_requested
    - export_preview_blocked
    - safe_preview_available
    - red_team_scenario_viewed
    - unsafe_copy_attempt_blocked
    - unsafe_export_attempt_blocked
    - real_patient_data_attempt_blocked
    - dicom_import_attempt_blocked
    - report_paste_attempt_blocked
```

Blocked audit event meanings:

- diagnosis validated,
- clinical correctness proven,
- treatment authorized,
- order authorized,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD consensus achieved,
- product readiness achieved,
- public readiness achieved.

Audit trace state rule:

> Audit state traces UI movement, not medical truth.

---

## 19. Fixture-to-Route Binding

Fixtures may bind only to allowed routes.

| Fixture Type | Allowed Route Binding |
|---|---|
| synthetic_demo_case | `/prototype/cases` |
| demo_intake_binding_fixture | `/prototype/cases/:synthetic_case_id/intake` |
| demo_workspace_state_fixture | `/prototype/cases/:synthetic_case_id/map` and evidence routes |
| demo_structured_output_fixture | reasoning map and evidence routes |
| demo_safe_export_fixture | `/prototype/cases/:synthetic_case_id/export-preview` |
| demo_unsafe_export_failure_fixture | `/prototype/red-team` and scenario route |
| demo_audit_event_fixture | `/prototype/cases/:synthetic_case_id/audit` |
| demo_authority_envelope_fixture | all decision-adjacent routes |
| demo_no_decision_object_fixture | all decision-adjacent routes |
| demo_visual_artifact_fixture | map, evidence, safety routes |
| demo_red_team_scenario_fixture | red-team routes |

Blocked route bindings:

- patient routes,
- clinical routes,
- DICOM import routes,
- report import routes,
- diagnosis routes,
- treatment routes,
- order routes,
- procedure routes,
- follow-up routes,
- triage routes,
- patient-facing routes,
- clinical validation routes,
- product/public routes,
- MDD consensus routes.

Fixture-to-route rule:

> A fixture may bind only to routes already allowed by v0.16.1.

---

## 20. Fixture-to-Screen Binding

Fixtures may bind only to allowed prototype screens.

| Fixture Type | Allowed Screen Binding |
|---|---|
| synthetic_demo_case | Synthetic Demo Case Selector |
| demo_intake_binding_fixture | Demo Intake Review Screen |
| demo_workspace_state_fixture | Reasoning Map Screen / Evidence Panels |
| demo_structured_output_fixture | Reasoning Map Screen / Evidence Panels |
| demo_safe_export_fixture | Safe Export Preview Screen |
| demo_unsafe_export_failure_fixture | Red-Team Fail-Closed Screen |
| demo_audit_event_fixture | Audit Trace Screen |
| demo_authority_envelope_fixture | Authority Envelope Display |
| demo_no_decision_object_fixture | No-Decision Object Display |
| demo_visual_artifact_fixture | Visual Safety Label Display / Reasoning Map |
| demo_red_team_scenario_fixture | Red-Team Fail-Closed Screen |

Blocked screen bindings:

- final diagnosis screen,
- most likely diagnosis screen,
- diagnosis probability dashboard,
- disease rule-out screen,
- treatment recommendation screen,
- test ordering screen,
- procedure recommendation screen,
- follow-up scheduler,
- triage/disposition screen,
- patient-facing report screen,
- clinical validation dashboard,
- product readiness dashboard,
- public demo publication screen,
- MDD consensus screen.

Fixture-to-screen rule:

> Fixture-to-screen binding may display governance state only.

---

## 21. Fixture-to-Component Binding

Fixtures may bind only to safe prototype components.

Allowed component bindings:

| Fixture Data | Allowed Component |
|---|---|
| synthetic label | safety_banner |
| case title | case_card |
| supplied fictional fields | intake_field_table |
| missing fictional fields | missing_evidence_card |
| source status | source_status_card |
| mimic visibility | mimic_visibility_card |
| overlap visibility | overlap_card |
| confidence limiter | limitation_card |
| review prompt visibility | review_prompt_card |
| no-decision object | no_decision_card |
| authority envelope | authority_card |
| audit event | audit_event_row |
| safe export section | export_preview_section |
| red-team failure | fail_closed_card |
| visual safety label | visual_safety_label |

Blocked component bindings:

- diagnosis badge,
- disease probability meter,
- likelihood ranking table,
- treatment recommendation card,
- order button,
- procedure button,
- follow-up scheduler,
- triage badge,
- patient summary card,
- clinical validation badge,
- product-ready badge,
- MDD consensus card.

Fixture-to-component rule:

> Component binding may expose safe visibility, not clinical action.

---

## 22. Demo State Transition Rules

Allowed state transitions:

```text
selected_synthetic_case_state
→ synthetic_intake_state
→ reasoning_map_state
→ evidence_panel_state
→ safe_export_preview_state
→ audit_trace_state

selected_synthetic_case_state
→ red_team_scenario_state
→ audit_trace_state

any decision-adjacent state
→ safety_reference_state
```

Blocked state transitions:

```text
selected_synthetic_case_state → patient_case_state
synthetic_intake_state → clinical_intake_state
reasoning_map_state → diagnosis_state
evidence_panel_state → treatment_state
safe_export_preview_state → clinical_report_state
red_team_scenario_state → clinical_validation_state
audit_trace_state → correctness_proof_state
```

State transition rule:

> Demo state may move between safe prototype states only.

---

## 23. Fixture Binding Fail-Closed Conditions

Fixture binding must fail closed under the following conditions.

```yaml
fixture_binding_fail_closed_conditions:
  fixture_id_not_found:
    binding_allowed: false
    audit_required: true
  fixture_type_not_allowed:
    binding_allowed: false
    audit_required: true
  fixture_has_real_patient_marker:
    binding_allowed: false
    audit_required: true
  fixture_has_deidentified_patient_marker:
    binding_allowed: false
    audit_required: true
  fixture_has_dicom_marker:
    binding_allowed: false
    audit_required: true
  fixture_has_real_report_marker:
    binding_allowed: false
    audit_required: true
  fixture_has_final_diagnosis_field:
    binding_allowed: false
    audit_required: true
  fixture_has_probability_field:
    binding_allowed: false
    audit_required: true
  fixture_claims_clinical_validation:
    binding_allowed: false
    audit_required: true
  fixture_claims_product_or_public_readiness:
    binding_allowed: false
    audit_required: true
  fixture_targets_blocked_route:
    binding_allowed: false
    audit_required: true
  fixture_targets_blocked_screen:
    binding_allowed: false
    audit_required: true
  authority_envelope_missing:
    binding_allowed: false
    repair_required: true
    audit_required: true
  no_decision_object_missing_on_decision_adjacent_state:
    binding_allowed: false
    repair_required: true
    audit_required: true
```

Fixture binding fail-closed rule:

> Unsafe fixture binding must stop before it creates workspace state.

---

## 24. Blocked Real Patient Object Categories

The following object categories must never enter the fixture registry or demo state binding.

| Object Category | Required State |
|---|---|
| patient identity object | blocked |
| patient demographic object | blocked |
| MRN / accession object | blocked |
| clinical encounter object | blocked |
| DICOM study object | blocked |
| HRCT image object | blocked |
| PACS record object | blocked |
| EHR record object | blocked |
| real radiology report object | blocked |
| real pathology report object | blocked |
| real microbiology report object | blocked |
| real lab object | blocked |
| real MDD note object | blocked |
| real clinical note object | blocked |
| deidentified case object | blocked |
| validation cohort object | blocked |
| diagnostic ground truth object | blocked |
| clinical outcome object | blocked |

Blocked object rule:

> Deidentification does not convert real patient material into an allowed synthetic fixture.

---

## 25. Synthetic Registry Validation Checklist

The synthetic registry passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| FIX_REG_CHECK_001 | registry scope synthetic_internal_demo_only | true |
| FIX_REG_CHECK_002 | real patient data allowed false | true |
| FIX_REG_CHECK_003 | deidentified real patient data allowed false | true |
| FIX_REG_CHECK_004 | DICOM import allowed false | true |
| FIX_REG_CHECK_005 | real report import allowed false | true |
| FIX_REG_CHECK_006 | clinical validation use allowed false | true |
| FIX_REG_CHECK_007 | diagnostic ground truth allowed false | true |
| FIX_REG_CHECK_008 | allowed fixture types defined | true |
| FIX_REG_CHECK_009 | blocked fixture types defined | true |
| FIX_REG_CHECK_010 | fixture ID rules synthetic-only | true |
| FIX_REG_CHECK_011 | authority envelope required | true |
| FIX_REG_CHECK_012 | no-decision object required where relevant | true |
| FIX_REG_CHECK_013 | audit stub required | true |

Synthetic registry validation rule:

> The registry passes only if it cannot contain patient, diagnostic, validation, or action objects.

---

## 26. Demo State Binding Validation Checklist

Demo state binding passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| STATE_BIND_CHECK_001 | demo state object schema defined | true |
| STATE_BIND_CHECK_002 | selected synthetic case state defined | true |
| STATE_BIND_CHECK_003 | synthetic intake state defined | true |
| STATE_BIND_CHECK_004 | reasoning map state defined | true |
| STATE_BIND_CHECK_005 | evidence panel state defined | true |
| STATE_BIND_CHECK_006 | safe export preview state defined | true |
| STATE_BIND_CHECK_007 | red-team scenario state defined | true |
| STATE_BIND_CHECK_008 | audit trace state defined | true |
| STATE_BIND_CHECK_009 | fixture-to-route binding defined | true |
| STATE_BIND_CHECK_010 | fixture-to-screen binding defined | true |
| STATE_BIND_CHECK_011 | fixture-to-component binding defined | true |
| STATE_BIND_CHECK_012 | demo state transitions safe | true |
| STATE_BIND_CHECK_013 | blocked state transitions defined | true |
| STATE_BIND_CHECK_014 | fixture binding fail-closed conditions defined | true |
| STATE_BIND_CHECK_015 | blocked real patient object categories defined | true |

Demo state binding validation rule:

> Demo state binding passes only if synthetic fixtures can bind to safe prototype visibility and nothing else.

---

## 27. v0.16.2 Acceptance Criteria

v0.16.2 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| synthetic fixture registry object schema defined | true |
| synthetic fixture entry schema defined | true |
| allowed fixture types defined | true |
| blocked fixture types defined | true |
| synthetic case registry object defined | true |
| fixture ID rules defined | true |
| demo state object schema defined | true |
| selected synthetic case state defined | true |
| synthetic intake state defined | true |
| reasoning map state defined | true |
| evidence panel state defined | true |
| safe export preview state defined | true |
| red-team scenario state defined | true |
| audit trace state defined | true |
| fixture-to-route binding defined | true |
| fixture-to-screen binding defined | true |
| fixture-to-component binding defined | true |
| demo state transition rules defined | true |
| fixture binding fail-closed conditions defined | true |
| blocked real patient object categories defined | true |
| synthetic registry validation checklist defined | true |
| demo state binding validation checklist defined | true |
| real patient data remains blocked | true |
| deidentified real patient data remains blocked | true |
| DICOM import remains blocked | true |
| HRCT import remains blocked | true |
| real report import remains blocked | true |
| PACS/EHR integration remains blocked | true |
| patient-facing use remains not_allowed | true |
| clinical validation remains not_opened | true |
| diagnostic performance claim remains not_allowed | true |
| product readiness remains false | true |
| public readiness remains false | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| order/procedure/follow-up/triage authority remains none | true |
| MDD replacement remains blocked | true |

v0.16.2 acceptance rule:

> The fixture registry and demo state binding plan is accepted only if every fixture remains synthetic, every state remains non-clinical, and every binding remains source-governed and fail-closed.

---

## 28. Next Step

The next recommended step is:

- v0.16.3 — UI Copy Source Mapping / Safety Language Contract

v0.16.3 should define:

- source-governed UI copy registry,
- safety language IDs,
- route-level copy mapping,
- screen-level copy mapping,
- component-level copy mapping,
- disabled control copy mapping,
- fail-closed copy mapping,
- export preview copy mapping,
- red-team quarantine copy mapping,
- visual safety copy mapping,
- authority envelope copy mapping,
- no-decision object copy mapping,
- blocked copy phrases,
- copy validation checklist.

v0.16.3 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 29. Governance Statement

This document defines the synthetic fixture registry and demo state binding plan.

It opens synthetic fixture/state scaffold planning only.

It does not implement a clinical product.

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
It does not import HRCT images.  
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.16.2 governance discipline is:

> “Do not let synthetic fixtures become patient cases.”

The demo state discipline is:

> “Do not let demo state become clinical state.”