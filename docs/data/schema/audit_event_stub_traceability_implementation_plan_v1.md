# ILD Reasoning Platform — Audit Event Stub / Traceability Implementation Plan v1

Version: v0.16.5  
Status: audit_event_stub_traceability_implementation_plan  
Scope: Audit event stub registry, route audit events, screen audit events, component audit events, fixture binding audit events, fail-closed audit events, export preview audit events, red-team audit events, disabled control attempt audit events, audit event schema, audit event severity categories, audit event source mapping, audit trace display planning, blocked audit meanings, and audit validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.16.5 — Audit Event Stub / Traceability Implementation Plan.

v0.16.5 translates the sealed prototype UI behavior, source-governed build scaffold, route registry, synthetic fixture registry, UI copy contract, and fail-closed state stubs into a traceability-first audit event stub plan.

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

Its purpose is to define how internal prototype UI events may be traced without implying medical correctness, clinical validation, diagnostic performance, product readiness, public readiness, or clinical authority.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16.5 audit principle is:

> “Audit trace may explain prototype state movement, but it must not prove medical truth.”

The traceability discipline is:

> “Every meaningful scaffold event should be traceable to route, screen, component, fixture, source contract, authority effect none, and decision effect none.”

---

## 2. Relationship to v0.16.0–v0.16.4

v0.16.5 inherits:

- v0.16.0 — Source-Governed Prototype Build Scaffold Entry Gate,
- v0.16.1 — Prototype Route / Screen Registry Implementation Plan,
- v0.16.2 — Synthetic Fixture Registry / Demo State Binding Plan,
- v0.16.3 — UI Copy Source Mapping / Safety Language Contract,
- v0.16.4 — Fail-Closed State Stub / Disabled Clinical Control Plan.

v0.16.0 opened source-governed build scaffold planning.

v0.16.1 defined allowed and blocked routes and screen registry.

v0.16.2 defined synthetic fixture registry and demo state binding.

v0.16.3 defined source-governed safety language.

v0.16.4 defined fail-closed stubs and disabled clinical control behavior.

v0.16.5 defines audit event stubs for traceability across those scaffold layers.

v0.16.5 does not broaden v0.16.0–v0.16.4.

v0.16.5 must not open:

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

Audit inheritance rule:

> v0.16.5 may trace prototype behavior only; it may not validate clinical behavior.

---

## 3. Global Authority Envelope

Every audit event stub, audit trace row, audit display, audit filter, audit severity category, audit source mapping, audit export reference, fail-closed audit, disabled-control audit, route audit, screen audit, component audit, fixture-binding audit, red-team audit, and export-preview audit must inherit the following authority envelope.

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

No audit event may grant, imply, certify, validate, or approve clinical authority.

Authority audit rule:

> An audit event can record that something happened; it cannot make that thing clinically authoritative.

---

## 4. Global No-Decision Audit Requirement

Every decision-adjacent audit event must preserve the no-decision object.

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

Required no-decision audit behavior:

- audit diagnosis attempt blocked with diagnosis_made=false,
- audit exclusion attempt blocked with disease_excluded=false and mimic_excluded=false,
- audit treatment attempt blocked with treatment_selected=false,
- audit order attempt blocked with test_ordered=false,
- audit procedure attempt blocked with procedure_decided=false,
- audit follow-up attempt blocked with follow_up_scheduled=false,
- audit triage attempt blocked with triage_assigned=false,
- audit MDD consensus attempt blocked with mdd_consensus_generated=false,
- audit patient-facing attempt blocked with patient_facing_output_generated=false.

No-decision audit rule:

> Audit must record that unsafe decisions were not made, not merely that an unsafe attempt occurred.

---

## 5. Audit Event Stub Object Schema

Every audit event stub must conform to the following schema.

```yaml
audit_event_stub:
  event_id: string
  version: v0.16.5
  event_type: string
  event_category: enum
  event_severity: enum
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  source_route_id: optional
  source_route_path: optional
  source_screen_id: optional
  source_component_id: optional
  source_fixture_id: optional
  source_state_id: optional
  source_stub_id: optional
  source_copy_id: optional
  source_export_preview_id: optional
  source_red_team_scenario_id: optional
  triggered_by: enum
  event_result: enum
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  real_patient_data_involved: false
  deidentified_real_patient_data_involved: false
  dicom_data_involved: false
  real_report_involved: false
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  mdd_consensus_effect: none
  required_display_copy_id: string
  trace_display_allowed: true
  export_as_clinical_evidence_allowed: false
```

Audit schema rule:

> Audit event stubs must preserve traceability without becoming evidence of clinical correctness.

---

## 6. Audit Event Categories

The following audit event categories are allowed.

| Category | Allowed Meaning |
|---|---|
| route_event | user reached or attempted a route |
| screen_event | screen rendered or was blocked |
| component_event | component rendered, expanded, or was blocked |
| fixture_event | synthetic fixture selected or binding blocked |
| state_event | demo state created, transitioned, or blocked |
| copy_event | UI copy displayed, repaired, or blocked |
| export_event | export preview requested, passed, or failed UI safety |
| red_team_event | red-team scenario viewed or blocked |
| fail_closed_event | unsafe attempt blocked |
| disabled_control_event | disabled control attempted |
| safety_event | authority/no-decision/visual safety checked |
| audit_view_event | audit trace viewed or filtered |

Blocked audit event categories:

- diagnosis_event,
- treatment_event,
- order_event,
- procedure_event,
- follow_up_event,
- triage_event,
- patient_facing_event,
- clinical_validation_event,
- diagnostic_performance_event,
- product_readiness_event,
- public_readiness_event,
- mdd_consensus_event.

Audit category rule:

> Audit categories may describe prototype behavior, not clinical actions.

---

## 7. Audit Event Severity Categories

Audit severity describes scaffold safety importance, not clinical severity.

Allowed severity categories:

| Severity | Meaning |
|---|---|
| info | safe prototype navigation or view event |
| boundary_notice | safety boundary displayed or acknowledged |
| safety_check | safety requirement verified |
| blocked_attempt | unsafe attempt blocked |
| repair_required | unsafe scaffold state requires UI safety repair |
| revalidation_required | UI safety revalidation required |
| fail_closed | unsafe state stopped before rendering/reuse/export |

Blocked severity meanings:

- mild disease,
- moderate disease,
- severe disease,
- urgent clinical status,
- safe outpatient,
- admit,
- diagnostic confidence,
- clinical risk score,
- treatment priority.

Severity rule:

> Audit severity is scaffold safety severity, not patient or disease severity.

---

## 8. Audit Event Result Types

Allowed event results:

| Event Result | Meaning |
|---|---|
| viewed | safe route/screen/component viewed |
| expanded | safe component or node expanded |
| selected | synthetic fixture selected |
| bound | synthetic fixture bound safely |
| verified | safety requirement verified |
| blocked | unsafe attempt blocked |
| repaired | UI safety repair applied |
| revalidation_started | UI safety revalidation started |
| revalidation_passed | UI safety revalidation passed |
| revalidation_failed | UI safety revalidation failed |
| safe_preview_available | safe export preview available |
| fail_closed | unsafe state stopped |

Blocked event results:

- diagnosis_made,
- disease_excluded,
- treatment_selected,
- test_ordered,
- procedure_decided,
- follow_up_scheduled,
- triage_assigned,
- mdd_consensus_generated,
- clinically_validated,
- product_ready,
- public_ready.

Result rule:

> Audit result types must not contain clinical decision results.

---

## 9. Audit Stub Registry

The following audit event stubs are required.

| Event ID | Event Type | Category | Severity |
|---|---|---|---|
| AUDIT_001 | prototype_boundary_viewed | route_event | boundary_notice |
| AUDIT_002 | prototype_boundary_acknowledged | route_event | boundary_notice |
| AUDIT_003 | synthetic_case_selector_viewed | route_event | info |
| AUDIT_004 | synthetic_case_inspected | fixture_event | info |
| AUDIT_005 | synthetic_case_selected | fixture_event | info |
| AUDIT_006 | synthetic_fixture_bound | fixture_event | safety_check |
| AUDIT_007 | demo_intake_review_viewed | screen_event | info |
| AUDIT_008 | supplied_field_inspected | component_event | info |
| AUDIT_009 | missing_field_inspected | component_event | info |
| AUDIT_010 | reasoning_map_opened | screen_event | info |
| AUDIT_011 | reasoning_map_node_expanded | component_event | info |
| AUDIT_012 | reasoning_map_edge_viewed | component_event | info |
| AUDIT_013 | evidence_panel_opened | screen_event | info |
| AUDIT_014 | source_status_panel_opened | screen_event | info |
| AUDIT_015 | authority_envelope_verified | safety_event | safety_check |
| AUDIT_016 | no_decision_object_verified | safety_event | safety_check |
| AUDIT_017 | visual_safety_label_verified | safety_event | safety_check |
| AUDIT_018 | export_preview_requested | export_event | info |
| AUDIT_019 | export_safety_check_started | export_event | safety_check |
| AUDIT_020 | safe_export_preview_available | export_event | safety_check |
| AUDIT_021 | unsafe_export_preview_blocked | fail_closed_event | fail_closed |
| AUDIT_022 | red_team_hub_viewed | red_team_event | info |
| AUDIT_023 | red_team_scenario_viewed | red_team_event | info |
| AUDIT_024 | disabled_control_attempted | disabled_control_event | blocked_attempt |
| AUDIT_025 | unsafe_route_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_026 | real_patient_data_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_027 | deidentified_real_patient_data_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_028 | dicom_import_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_029 | report_import_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_030 | pacs_ehr_connection_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_031 | diagnosis_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_032 | clinical_action_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_033 | patient_facing_output_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_034 | validation_overclaim_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_035 | readiness_overclaim_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_036 | unsafe_copy_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_037 | unsafe_export_attempt_blocked | fail_closed_event | fail_closed |
| AUDIT_038 | authority_envelope_missing_blocked | fail_closed_event | fail_closed |
| AUDIT_039 | no_decision_object_missing_blocked | fail_closed_event | fail_closed |
| AUDIT_040 | unsafe_visual_semantics_blocked | fail_closed_event | fail_closed |
| AUDIT_041 | unsafe_fixture_binding_blocked | fail_closed_event | fail_closed |
| AUDIT_042 | unsafe_ui_copy_phrase_blocked | fail_closed_event | fail_closed |
| AUDIT_043 | audit_correctness_claim_blocked | fail_closed_event | fail_closed |
| AUDIT_044 | ui_safety_repair_required | fail_closed_event | repair_required |
| AUDIT_045 | ui_safety_revalidation_started | safety_event | revalidation_required |
| AUDIT_046 | ui_safety_revalidation_passed | safety_event | safety_check |
| AUDIT_047 | ui_safety_revalidation_failed | fail_closed_event | fail_closed |
| AUDIT_048 | audit_trace_viewed | audit_view_event | info |
| AUDIT_049 | audit_trace_filtered | audit_view_event | info |
| AUDIT_050 | safety_reference_viewed | safety_event | boundary_notice |

Audit registry rule:

> Audit stubs must cover safe navigation, safety verification, blocked unsafe attempts, repair, and UI safety revalidation.

---

## 10. Route Audit Events

Every allowed route must emit route audit events.

| Route | Required Audit Event |
|---|---|
| `/prototype` | prototype_boundary_viewed |
| `/prototype/cases` | synthetic_case_selector_viewed |
| `/prototype/cases/:synthetic_case_id/intake` | demo_intake_review_viewed |
| `/prototype/cases/:synthetic_case_id/map` | reasoning_map_opened |
| `/prototype/cases/:synthetic_case_id/evidence` | evidence_panel_opened |
| `/prototype/cases/:synthetic_case_id/evidence/source-status` | source_status_panel_opened |
| `/prototype/cases/:synthetic_case_id/export-preview` | export_preview_requested |
| `/prototype/red-team` | red_team_hub_viewed |
| `/prototype/red-team/:scenario_id` | red_team_scenario_viewed |
| `/prototype/cases/:synthetic_case_id/audit` | audit_trace_viewed |
| `/prototype/safety` | safety_reference_viewed |

Blocked route audit meanings:

- clinical_route_entered,
- patient_route_entered,
- diagnosis_route_entered,
- treatment_route_entered,
- validation_route_entered,
- product_ready_route_entered.

Route audit rule:

> Route events trace internal prototype navigation only.

---

## 11. Screen Audit Events

Every safety-critical screen must emit a screen audit event.

| Screen | Required Event |
|---|---|
| Prototype Boundary Landing Screen | prototype_boundary_viewed |
| Synthetic Demo Case Selector | synthetic_case_selector_viewed |
| Demo Intake Review Screen | demo_intake_review_viewed |
| Reasoning Map Screen | reasoning_map_opened |
| Missing Evidence Panel | evidence_panel_opened |
| Mimic Visibility Panel | evidence_panel_opened |
| Overlap Panel | evidence_panel_opened |
| Source Status Panel | source_status_panel_opened |
| Confidence Limiter Panel | evidence_panel_opened |
| Review Prompt Panel | evidence_panel_opened |
| Safe Export Preview Screen | export_preview_requested |
| Red-Team Fail-Closed Screen | red_team_scenario_viewed |
| Authority Envelope Display | authority_envelope_verified |
| No-Decision Object Display | no_decision_object_verified |
| Audit Trace Screen | audit_trace_viewed |
| Visual Safety Label Display | visual_safety_label_verified |

Screen audit rule:

> Screen audit events record safe UI visibility, not clinical review completion.

---

## 12. Component Audit Events

Safety-critical components must emit component audit events.

| Component | Required Event |
|---|---|
| case_card | synthetic_case_inspected |
| intake_field_table | supplied_field_inspected or missing_field_inspected |
| missing_evidence_card | missing_field_inspected |
| mimic_visibility_card | evidence_panel_opened |
| overlap_card | evidence_panel_opened |
| source_status_card | source_status_panel_opened |
| limitation_card | evidence_panel_opened |
| review_prompt_card | evidence_panel_opened |
| reasoning_node | reasoning_map_node_expanded |
| reasoning_edge | reasoning_map_edge_viewed |
| export_preview_section | export_safety_check_started |
| fail_closed_card | fail_closed_event |
| authority_card | authority_envelope_verified |
| no_decision_card | no_decision_object_verified |
| audit_event_row | audit_trace_viewed |
| visual_safety_label | visual_safety_label_verified |

Component audit rule:

> Component audit events show which safety-relevant UI element was inspected, not whether its medical content is correct.

---

## 13. Fixture Binding Audit Events

Synthetic fixture binding must emit audit events.

Required fixture audit sequence:

```text
synthetic_case_inspected
→ synthetic_case_selected
→ synthetic_fixture_bound
```

Fixture binding event requirements:

```yaml
fixture_binding_audit:
  synthetic_fixture_id_required: true
  fixture_type_required: true
  source_contract_required: true
  synthetic_only_confirmed: true
  real_patient_data_involved: false
  deidentified_real_patient_data_involved: false
  dicom_data_involved: false
  real_report_involved: false
  diagnostic_ground_truth_involved: false
  clinical_validation_effect: none
  authority_effect: none
  decision_effect: none
```

Blocked fixture audit meanings:

- patient case loaded,
- clinical case loaded,
- diagnosis case loaded,
- validation dataset loaded,
- ground truth loaded.

Fixture audit rule:

> Fixture audit proves synthetic binding traceability, not clinical validity.

---

## 14. Fail-Closed Audit Events

Every fail-closed state must emit an audit event.

Required fail-closed audit fields:

```yaml
fail_closed_audit_event:
  event_type: fail_closed_state_triggered
  source_stub_id: string
  unsafe_attempt_type: string
  trigger_surface: string
  blocked_result: true
  repair_required: boolean
  ui_safety_revalidation_required: boolean
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Required fail-closed audit events:

- unsafe_route_attempt_blocked,
- real_patient_data_attempt_blocked,
- deidentified_real_patient_data_attempt_blocked,
- dicom_import_attempt_blocked,
- report_import_attempt_blocked,
- pacs_ehr_connection_attempt_blocked,
- diagnosis_attempt_blocked,
- clinical_action_attempt_blocked,
- patient_facing_output_attempt_blocked,
- validation_overclaim_attempt_blocked,
- readiness_overclaim_attempt_blocked,
- unsafe_copy_attempt_blocked,
- unsafe_export_attempt_blocked,
- authority_envelope_missing_blocked,
- no_decision_object_missing_blocked,
- unsafe_visual_semantics_blocked,
- unsafe_fixture_binding_blocked,
- unsafe_ui_copy_phrase_blocked,
- audit_correctness_claim_blocked.

Fail-closed audit rule:

> Fail-closed audit records containment of unsafe behavior, not clinical safety.

---

## 15. Export Preview Audit Events

Export preview must emit audit events.

Required export preview audit sequence:

```text
export_preview_requested
→ export_safety_check_started
→ authority_envelope_verified
→ no_decision_object_verified
→ safe_export_preview_available
```

If unsafe:

```text
export_preview_requested
→ export_safety_check_started
→ unsafe_export_preview_blocked
→ ui_safety_repair_required
→ ui_safety_revalidation_started
```

Export audit required fields:

```yaml
export_preview_audit:
  export_preview_id_required: true
  parent_synthetic_case_id_required: true
  unsafe_content_class_optional: true
  authority_effect: none
  decision_effect: none
  clinical_report_created: false
  patient_facing_output_created: false
  mdd_consensus_generated: false
  clinical_validation_effect: none
```

Blocked export audit meanings:

- clinical report generated,
- impression generated,
- diagnosis exported,
- patient summary exported,
- MDD consensus generated,
- clinical validation passed.

Export audit rule:

> Export audit records preview safety state, not clinical report generation.

---

## 16. Red-Team Audit Events

Red-team scenario interactions must emit audit events.

Required red-team audit sequence:

```text
red_team_hub_viewed
→ red_team_scenario_viewed
→ unsafe_copy_attempt_blocked or unsafe_export_attempt_blocked when attempted
```

Red-team audit fields:

```yaml
red_team_audit_event:
  red_team_scenario_id_required: true
  unsafe_example_visible: quarantined_only
  copy_allowed: false
  export_allowed: false
  red_team_validation_effect: none
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  authority_effect: none
  decision_effect: none
```

Blocked red-team audit meanings:

- red-team passed clinical validation,
- red-team proves safety,
- red-team confirms product readiness,
- red-team confirms public readiness,
- red-team proves diagnostic performance.

Red-team audit rule:

> Red-team audit traces containment demonstration, not validation.

---

## 17. Disabled Control Attempt Audit Events

Every disabled clinical control attempt must emit an audit event.

Required disabled control audit fields:

```yaml
disabled_control_attempt_audit:
  event_type: disabled_control_attempted
  control_id_required: true
  control_label_required: true
  blocked_authority_required: true
  disabled_reason_required: true
  source_contract_required: true
  enabled: false
  clickable: false
  navigation_allowed: false
  action_created: false
  authority_effect: none
  decision_effect: none
```

Required disabled control audit categories:

- real patient upload control attempted,
- deidentified patient upload control attempted,
- DICOM import control attempted,
- report import control attempted,
- diagnosis control attempted,
- ranking control attempted,
- rule-out control attempted,
- treatment control attempted,
- order control attempted,
- procedure control attempted,
- follow-up control attempted,
- triage control attempted,
- patient summary control attempted,
- clinical validation control attempted,
- product/public readiness control attempted,
- MDD consensus control attempted.

Disabled control audit rule:

> Disabled control audit must show the control stayed disabled and no action occurred.

---

## 18. Safety Verification Audit Events

The following safety checks require audit events.

| Safety Check | Required Audit Event |
|---|---|
| authority envelope visible | authority_envelope_verified |
| no-decision object visible | no_decision_object_verified |
| visual safety label visible | visual_safety_label_verified |
| synthetic fixture bound safely | synthetic_fixture_bound |
| export safety check started | export_safety_check_started |
| safe export preview available | safe_export_preview_available |
| UI safety repair required | ui_safety_repair_required |
| UI safety revalidation started | ui_safety_revalidation_started |
| UI safety revalidation passed | ui_safety_revalidation_passed |
| UI safety revalidation failed | ui_safety_revalidation_failed |

Safety verification audit rule:

> Safety verification events validate UI safety conditions only, not clinical correctness.

---

## 19. Audit Event Source Mapping

Every audit event must map to a source contract.

Required source mapping fields:

```yaml
audit_event_source_mapping:
  event_id: string
  event_type: string
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  source_route_id: optional
  source_screen_id: optional
  source_component_id: optional
  source_fixture_id: optional
  source_stub_id: optional
  source_copy_id: optional
```

Mapping examples:

| Event | Source Contract |
|---|---|
| synthetic_case_selected | v0.16.2 synthetic fixture registry |
| reasoning_map_opened | v0.15.3 reasoning map contract / v0.16.1 route registry |
| unsafe_route_attempt_blocked | v0.16.1 route registry / v0.16.4 fail-closed plan |
| unsafe_ui_copy_phrase_blocked | v0.16.3 copy contract / v0.16.4 fail-closed plan |
| safe_export_preview_available | v0.15.4 export preview contract / v0.16.4 fail-closed plan |
| audit_correctness_claim_blocked | v0.16.5 audit plan |

Source mapping rule:

> Audit events without source contract mapping cannot enter the scaffold.

---

## 20. Audit Trace Display Planning

The audit trace screen may display audit events in a safe way.

Allowed audit trace display fields:

- event ID,
- event type,
- event category,
- event severity,
- timestamp or sequence ID,
- source route,
- source screen,
- source component,
- source fixture,
- source contract,
- event result,
- authority effect none,
- decision effect none,
- clinical validation effect none,
- product readiness effect none,
- public readiness effect none,
- failure reason where relevant,
- repair required where relevant,
- UI safety revalidation required where relevant.

Blocked audit trace display fields:

- diagnosis result,
- clinical correctness result,
- treatment authorization,
- order authorization,
- procedure decision,
- follow-up schedule,
- triage assignment,
- patient-facing output,
- clinical validation pass,
- diagnostic accuracy,
- sensitivity,
- specificity,
- AUC,
- product-ready status,
- public-ready status,
- MDD consensus.

Audit trace display rule:

> Audit trace display must make non-authority visible.

---

## 21. Audit Trace Filtering Rules

Allowed audit filters:

- by route,
- by screen,
- by component,
- by fixture,
- by event category,
- by scaffold safety severity,
- by fail-closed state,
- by repair-required state,
- by UI safety revalidation state,
- by source contract,
- by synthetic case ID.

Blocked audit filters:

- by disease,
- by diagnosis,
- by probability,
- by treatment,
- by test order,
- by procedure,
- by follow-up,
- by triage,
- by patient,
- by MRN,
- by accession number,
- by DICOM UID,
- by clinical validation status,
- by diagnostic performance.

Audit filter rule:

> Audit filters may organize scaffold events, not clinical cases or outcomes.

---

## 22. Blocked Audit Meanings

The following audit meanings are blocked.

| Blocked Audit Meaning | Reason |
|---|---|
| audit proves diagnosis | diagnostic authority blocked |
| audit proves disease exclusion | exclusion authority blocked |
| audit validates treatment | treatment authority blocked |
| audit confirms order | order authority blocked |
| audit confirms procedure | procedure authority blocked |
| audit confirms follow-up | follow-up authority blocked |
| audit confirms triage | triage authority blocked |
| audit proves clinical correctness | correctness claim blocked |
| audit proves clinical validation | validation not opened |
| audit proves diagnostic performance | performance claim blocked |
| audit proves product readiness | product_ready false |
| audit proves public readiness | public_ready false |
| audit proves MDD consensus | MDD replacement blocked |

Blocked audit meaning rule:

> Audit must never be allowed to launder traceability into truth.

---

## 23. Audit Event Copy Requirements

Audit events must use source-governed copy.

Required audit copy:

```yaml
audit_event_copy:
  primary_boundary: "Audit trace explains UI state, not medical correctness."
  no_validation: "Audit trace is not clinical validation."
  no_performance: "Audit trace does not measure diagnostic performance."
  authority_none: "Audit authority effect: none."
  decision_none: "Audit decision effect: none."
  safety_trace: "This event records prototype safety behavior."
```

Blocked audit copy:

- “clinically validated,”
- “diagnosis validated,”
- “correct result,”
- “safe clinically,”
- “performance verified,”
- “expert equivalent,”
- “product-ready,”
- “public-ready.”

Audit copy rule:

> Audit copy must make the limitation of audit visible.

---

## 24. Audit Event Repair Rules

Unsafe audit events must trigger UI safety repair.

Repair required when:

- event category implies clinical action,
- event result implies diagnosis or treatment,
- audit copy claims correctness,
- audit trace claims clinical validation,
- audit severity implies disease severity,
- audit filter implies patient identity,
- audit source mapping is missing,
- authority effect is not none,
- decision effect is not none,
- product/public readiness effect is not none.

Allowed repair actions:

- rename event type to scaffold-safe event,
- remove clinical result field,
- restore authority_effect none,
- restore decision_effect none,
- add source contract mapping,
- add blocked meaning disclaimer,
- remove unsafe audit copy,
- rerun UI safety revalidation.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- validation correction,
- performance correction,
- product readiness correction.

Audit repair rule:

> Audit repair fixes trace language and structure, not medical correctness.

---

## 25. Audit Validation Checklist

v0.16.5 audit validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| AUDIT_CHECK_001 | audit event stub schema defined | true |
| AUDIT_CHECK_002 | audit event categories defined | true |
| AUDIT_CHECK_003 | blocked audit categories defined | true |
| AUDIT_CHECK_004 | scaffold safety severity categories defined | true |
| AUDIT_CHECK_005 | clinical severity meanings blocked | true |
| AUDIT_CHECK_006 | audit event result types defined | true |
| AUDIT_CHECK_007 | clinical decision result types blocked | true |
| AUDIT_CHECK_008 | audit stub registry defined | true |
| AUDIT_CHECK_009 | route audit events defined | true |
| AUDIT_CHECK_010 | screen audit events defined | true |
| AUDIT_CHECK_011 | component audit events defined | true |
| AUDIT_CHECK_012 | fixture binding audit events defined | true |
| AUDIT_CHECK_013 | fail-closed audit events defined | true |
| AUDIT_CHECK_014 | export preview audit events defined | true |
| AUDIT_CHECK_015 | red-team audit events defined | true |
| AUDIT_CHECK_016 | disabled control attempt audit events defined | true |
| AUDIT_CHECK_017 | safety verification audit events defined | true |
| AUDIT_CHECK_018 | audit event source mapping defined | true |
| AUDIT_CHECK_019 | audit trace display planning defined | true |
| AUDIT_CHECK_020 | audit trace filtering rules defined | true |
| AUDIT_CHECK_021 | blocked audit meanings defined | true |
| AUDIT_CHECK_022 | audit event copy requirements defined | true |
| AUDIT_CHECK_023 | audit event repair rules defined | true |
| AUDIT_CHECK_024 | every audit event authority_effect none | true |
| AUDIT_CHECK_025 | every audit event decision_effect none | true |
| AUDIT_CHECK_026 | every audit event clinical_validation_effect none | true |
| AUDIT_CHECK_027 | every audit event product/public readiness effect none | true |
| AUDIT_CHECK_028 | audit trace does not claim correctness | true |
| AUDIT_CHECK_029 | audit trace does not claim diagnostic performance | true |
| AUDIT_CHECK_030 | audit trace does not claim clinical validation | true |

Audit validation rule:

> Audit validation passes only if traceability cannot be mistaken for clinical correctness, validation, readiness, or authority.

---

## 26. v0.16.5 Acceptance Criteria

v0.16.5 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| audit event stub registry defined | true |
| route audit events defined | true |
| screen audit events defined | true |
| component audit events defined | true |
| fixture binding audit events defined | true |
| fail-closed audit events defined | true |
| export preview audit events defined | true |
| red-team audit events defined | true |
| disabled control attempt audit events defined | true |
| audit event schema defined | true |
| audit event severity categories defined | true |
| audit event source mapping defined | true |
| audit trace display planning defined | true |
| audit trace filtering rules defined | true |
| blocked audit meanings defined | true |
| audit copy requirements defined | true |
| audit repair rules defined | true |
| audit validation checklist defined | true |
| every audit event authority_effect none | true |
| every audit event decision_effect none | true |
| every audit event correctness_claim false | true |
| every audit event clinical_validation_effect none | true |
| every audit event diagnostic_performance_effect none | true |
| every audit event product/public readiness effect none | true |
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

v0.16.5 acceptance rule:

> The audit event stub plan is accepted only if audit traceability remains source-governed, synthetic-only, non-clinical, non-authoritative, non-validating, non-ready, non-patient-facing, and unable to prove medical truth.

---

## 27. Next Step

The next recommended step is:

- v0.16.6 — Safe Export Preview Stub / Red-Team Scenario Stub Plan

v0.16.6 should define:

- safe export preview stub registry,
- export preview section stub structure,
- export preview safety check stub,
- unsafe heading/language detector stub,
- copy/export block stub,
- red-team scenario stub registry,
- red-team scenario detail structure,
- red-team quarantine display stub,
- red-team repair/revalidation stub,
- export/red-team audit event binding,
- safe preview validation checklist,
- red-team scenario validation checklist.

v0.16.6 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 28. Governance Statement

This document defines audit event stubs and traceability implementation planning.

It opens traceability scaffold planning only.

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

The v0.16.5 governance discipline is:

> “Do not let audit traceability become clinical correctness.”

The audit discipline is:

> “Every trace must explain what the prototype did, what it did not do, and why it has no clinical authority.”