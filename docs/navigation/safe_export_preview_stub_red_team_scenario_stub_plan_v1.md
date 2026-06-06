# ILD Reasoning Platform — Safe Export Preview Stub / Red-Team Scenario Stub Plan v1

Version: v0.16.6  
Status: safe_export_preview_stub_red_team_scenario_stub_plan  
Scope: Safe export preview stub registry, export preview section stub structure, export preview safety check stub, unsafe heading detector stub, unsafe language detector stub, copy/export block stub, red-team scenario stub registry, red-team scenario detail structure, red-team quarantine display stub, red-team repair/revalidation stub, export/red-team audit event binding, safe preview validation checklist, and red-team scenario validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.16.6 — Safe Export Preview Stub / Red-Team Scenario Stub Plan.

v0.16.6 translates the sealed safe export preview contract, red-team fail-closed UI behavior, UI copy source mapping, fail-closed stubs, and audit event stubs into a source-governed internal build scaffold plan for export preview and red-team scenario stubs.

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

Its purpose is to define how the internal prototype may scaffold:

- safe export preview behavior,
- export section stubs,
- export safety checks,
- unsafe heading/language detection stubs,
- copy/export blocking stubs,
- red-team scenario stubs,
- red-team quarantine display stubs,
- repair-required stubs,
- UI safety revalidation stubs,
- export/red-team audit bindings.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16.6 export stub principle is:

> “An export preview stub may demonstrate safe structure, but it must not become a clinical report generator.”

The v0.16.6 red-team stub principle is:

> “A red-team scenario stub may demonstrate containment, but it must not create reusable unsafe output.”

---

## 2. Relationship to v0.16.0–v0.16.5

v0.16.6 inherits:

- v0.16.0 — Source-Governed Prototype Build Scaffold Entry Gate,
- v0.16.1 — Prototype Route / Screen Registry Implementation Plan,
- v0.16.2 — Synthetic Fixture Registry / Demo State Binding Plan,
- v0.16.3 — UI Copy Source Mapping / Safety Language Contract,
- v0.16.4 — Fail-Closed State Stub / Disabled Clinical Control Plan,
- v0.16.5 — Audit Event Stub / Traceability Implementation Plan.

v0.16.0 opened source-governed build scaffold planning.

v0.16.1 defined allowed and blocked internal prototype routes.

v0.16.2 defined synthetic fixture and demo state binding.

v0.16.3 defined source-governed safety copy.

v0.16.4 defined fail-closed and disabled-control safety stops.

v0.16.5 defined audit traceability stubs.

v0.16.6 defines safe export preview and red-team scenario stubs under those constraints.

v0.16.6 does not broaden v0.16.0–v0.16.5.

v0.16.6 must not open:

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

Stub inheritance rule:

> v0.16.6 may scaffold export/red-team safety behavior only; it may not scaffold clinical report generation or validation.

---

## 3. Global Authority Envelope

Every export preview stub, export section stub, safety check stub, detector stub, red-team scenario stub, quarantine display stub, copy/export block stub, repair-required stub, UI safety revalidation stub, and audit binding must inherit the following authority envelope.

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

No export preview stub or red-team stub may create an exception to this envelope.

Authority stub rule:

> A stub cannot become safe clinical functionality by being called a preview, detector, checker, or red-team scenario.

---

## 4. Global No-Decision Object

The no-decision object must be preserved across export preview and red-team scenario stubs.

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

Required no-decision display contexts:

- safe export preview route,
- export preview safety check stub,
- blocked export preview state,
- red-team scenario detail route,
- red-team quarantine display,
- copy/export block state,
- repair-required state,
- UI safety revalidation state,
- export/red-team audit trace.

No-decision stub rule:

> Export and red-team stubs must show that no clinical decision was made even when unsafe behavior was attempted.

---

## 5. Safe Export Preview Stub Object Schema

Every safe export preview stub must conform to the following schema.

```yaml
safe_export_preview_stub:
  stub_id: string
  version: v0.16.6
  stub_name: string
  route_id: ROUTE_012
  route_path: "/prototype/cases/:synthetic_case_id/export-preview"
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  parent_synthetic_case_id: string
  parent_fixture_id: string
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_report_generator: false
  diagnostic_report_generator: false
  patient_summary_generator: false
  mdd_consensus_generator: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  required_sections: list
  blocked_sections: list
  required_safety_checks: list
  required_copy_ids: list
  required_audit_events: list
  copy_allowed: conditional_safe_only
  export_allowed: conditional_safe_only
  unsafe_copy_allowed: false
  unsafe_export_allowed: false
```

Safe export preview stub rule:

> A safe export preview stub is a scaffolded safety preview, not a document generator.

---

## 6. Export Preview Section Stub Schema

Every export preview section stub must conform to the following schema.

```yaml
export_preview_section_stub:
  section_stub_id: string
  version: v0.16.6
  section_name: string
  section_category: enum
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  parent_export_preview_stub_id: string
  allowed_content_origin: synthetic_fixture_only
  real_patient_data_allowed: false
  clinical_report_content_allowed: false
  diagnostic_content_allowed: false
  action_content_allowed: false
  patient_facing_content_allowed: false
  validation_claim_allowed: false
  readiness_claim_allowed: false
  required_safety_copy_id: string
  required_authority_envelope: conditional_required
  required_no_decision_object: conditional_required
  required_audit_event: true
  blocked_heading_terms: list
  blocked_language_classes: list
```

Allowed section categories:

- synthetic_demo_boundary,
- non_clinical_use_boundary,
- authority_envelope,
- no_decision_object,
- export_identity,
- source_status_summary,
- supplied_context_summary,
- missing_evidence_summary,
- mimic_visibility_summary,
- overlap_visibility_summary,
- confidence_limiter_summary,
- review_prompt_visibility,
- audit_trace_references,
- export_safety_state.

Blocked section categories:

- impression,
- diagnosis,
- final_diagnosis,
- diagnostic_conclusion,
- disease_probability,
- disease_ranking,
- treatment_plan,
- order_plan,
- procedure_recommendation,
- follow_up_schedule,
- triage_disposition,
- patient_summary,
- mdd_consensus,
- clinical_validation_result,
- diagnostic_performance_result,
- product_ready_result,
- public_ready_result.

Section stub rule:

> Export preview sections may display safe governance summaries only.

---

## 7. Safe Export Preview Stub Registry

The following safe export preview stubs are required.

| Stub ID | Stub Name | Required Meaning |
|---|---|---|
| EXPORT_STUB_001 | Safe Export Preview Container | wraps all safe preview sections |
| EXPORT_STUB_002 | Synthetic Demo Boundary Section | identifies fictional demo status |
| EXPORT_STUB_003 | Non-Clinical Use Boundary Section | blocks clinical interpretation |
| EXPORT_STUB_004 | Authority Envelope Section | shows no clinical authority |
| EXPORT_STUB_005 | No-Decision Object Section | shows decisions not made |
| EXPORT_STUB_006 | Export Identity Section | identifies preview as MDD preparation preview only |
| EXPORT_STUB_007 | Source Status Summary Section | shows source role/limitation |
| EXPORT_STUB_008 | Supplied Context Summary Section | shows fictional supplied context |
| EXPORT_STUB_009 | Missing Evidence Summary Section | preserves missingness |
| EXPORT_STUB_010 | Mimic Visibility Summary Section | preserves mimic prompt visibility |
| EXPORT_STUB_011 | Overlap Visibility Summary Section | preserves unresolved overlap |
| EXPORT_STUB_012 | Confidence Limiter Summary Section | blocks probability interpretation |
| EXPORT_STUB_013 | Review Prompt Visibility Section | blocks action interpretation |
| EXPORT_STUB_014 | Audit Trace References Section | shows traceability only |
| EXPORT_STUB_015 | Export Safety State Section | shows safe/blocked UI safety state |

Safe export registry rule:

> Every export preview stub must show boundary and no-decision context before reasoning summaries.

---

## 8. Required Export Preview Section Order

The export preview stub must preserve section order.

```yaml
safe_export_preview_stub_section_order:
  1: synthetic_demo_boundary
  2: non_clinical_use_boundary
  3: authority_envelope
  4: no_decision_object
  5: export_identity
  6: source_status_summary
  7: supplied_context_summary
  8: missing_evidence_summary
  9: mimic_visibility_summary
  10: overlap_visibility_summary
  11: confidence_limiter_summary
  12: review_prompt_visibility
  13: audit_trace_references
  14: export_safety_state
```

Blocked order:

- reasoning before safety boundary,
- source summary before authority envelope,
- review prompt before no-action disclaimer,
- audit references framed as proof,
- export safety state hidden at bottom only,
- no-decision object omitted or delayed after content.

Section order rule:

> Safety and no-decision context must precede every export preview summary.

---

## 9. Export Preview Safety Check Stub

The export preview safety check stub must verify safety before preview availability.

```yaml
export_preview_safety_check_stub:
  stub_id: EXPORT_SAFETY_CHECK_001
  version: v0.16.6
  input_origin: synthetic_fixture_only
  real_patient_data_allowed: false
  clinical_report_generation_allowed: false
  checks_required:
    - synthetic_label_present
    - non_clinical_label_present
    - authority_envelope_present
    - no_decision_object_present
    - unsafe_heading_absent
    - diagnosis_language_absent
    - exclusion_language_absent
    - probability_language_absent
    - treatment_language_absent
    - order_language_absent
    - procedure_language_absent
    - follow_up_language_absent
    - triage_language_absent
    - patient_facing_language_absent
    - clinical_validation_claim_absent
    - diagnostic_performance_claim_absent
    - product_ready_claim_absent
    - public_ready_claim_absent
    - mdd_consensus_claim_absent
  pass_result: safe_preview_available
  fail_result: unsafe_export_preview_blocked
  audit_events_required:
    - export_safety_check_started
    - safe_export_preview_available
    - unsafe_export_preview_blocked
```

Safety check rule:

> Export safety check may verify UI safety only; it may not validate clinical correctness.

---

## 10. Unsafe Heading Detector Stub

The unsafe heading detector stub must block report-like headings.

```yaml
unsafe_heading_detector_stub:
  stub_id: EXPORT_DETECTOR_001
  version: v0.16.6
  detector_scope: ui_heading_safety_only
  clinical_validation_effect: none
  blocked_headings:
    - Impression
    - Diagnosis
    - Final Diagnosis
    - Diagnostic Conclusion
    - Assessment
    - Recommendation
    - Management Plan
    - Treatment Plan
    - Orders
    - Procedure Recommendation
    - Follow-Up Plan
    - Triage
    - Disposition
    - Patient Summary
    - MDD Consensus
    - Clinically Validated Result
    - Product Ready
    - Public Ready
  detection_result:
    unsafe_heading_detected: true
    preview_allowed: false
    copy_allowed: false
    export_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: unsafe_export_preview_blocked
```

Heading detector rule:

> Heading detection protects UI safety; it does not evaluate medical correctness.

---

## 11. Unsafe Language Detector Stub

The unsafe language detector stub must block unsafe clinical language.

```yaml
unsafe_language_detector_stub:
  stub_id: EXPORT_DETECTOR_002
  version: v0.16.6
  detector_scope: ui_language_safety_only
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  blocked_language_classes:
    - diagnosis_language
    - exclusion_language
    - probability_language
    - treatment_language
    - order_language
    - procedure_language
    - follow_up_language
    - triage_language
    - patient_facing_language
    - clinical_validation_language
    - diagnostic_performance_language
    - product_ready_language
    - public_ready_language
    - mdd_consensus_language
  detection_result:
    unsafe_language_detected: true
    preview_allowed: false
    copy_allowed: false
    export_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: unsafe_export_preview_blocked
```

Language detector rule:

> Language detection blocks unsafe UI language; it does not measure diagnosis, accuracy, or performance.

---

## 12. Copy / Export Block Stub

Unsafe copy and export must be blocked.

```yaml
copy_export_block_stub:
  stub_id: EXPORT_COPY_BLOCK_001
  version: v0.16.6
  blocked_copy_states:
    - unsafe_heading_detected
    - unsafe_language_detected
    - red_team_unsafe_example
    - blocked_preview
    - diagnosis_language_detected
    - exclusion_language_detected
    - clinical_action_language_detected
    - patient_facing_language_detected
    - validation_or_readiness_claim_detected
  blocked_export_states:
    - unsafe_heading_detected
    - unsafe_language_detected
    - red_team_unsafe_example
    - blocked_preview
    - authority_envelope_missing
    - no_decision_object_missing
  result:
    copy_allowed: false
    export_allowed: false
    reusable_output_created: false
    audit_event_required: true
```

Allowed copy/export states:

- safe authority envelope text,
- safe no-decision object text,
- synthetic boundary text,
- non-clinical boundary text,
- safe export preview after all safety checks pass,
- audit event IDs and trace metadata that do not claim correctness.

Copy/export block rule:

> Unsafe text cannot leave the prototype as reusable output.

---

## 13. Export Preview State Machine Stub

The export preview stub must follow a safe state machine.

```yaml
export_preview_state_machine_stub:
  draft_preview_requested:
    next: export_safety_check_pending
  export_safety_check_pending:
    next:
      - safe_preview_available
      - unsafe_preview_blocked
  safe_preview_available:
    requirements:
      - all_required_safety_sections_present
      - all_required_boundary_copy_present
      - unsafe_heading_absent
      - unsafe_language_absent
      - copy_export_policy_safe
  unsafe_preview_blocked:
    requirements:
      - failure_reason_visible
      - copy_allowed_false
      - export_allowed_false
      - repair_required_visible
      - audit_event_recorded
  repair_applied:
    next: ui_safety_revalidation_pending
  ui_safety_revalidation_pending:
    next:
      - safe_preview_available
      - unsafe_preview_blocked
```

Blocked transitions:

- unsafe_preview_blocked → copy_allowed,
- unsafe_preview_blocked → export_allowed,
- repair_applied → clinically_validated,
- safe_preview_available → product_ready,
- safe_preview_available → public_ready,
- safe_preview_available → clinical_report_generated,
- safe_preview_available → MDD_consensus_generated.

Export state machine rule:

> Export preview may pass UI safety; it may not pass clinical validation.

---

## 14. Red-Team Scenario Stub Object Schema

Every red-team scenario stub must conform to the following schema.

```yaml
red_team_scenario_stub:
  scenario_stub_id: string
  version: v0.16.6
  scenario_name: string
  scenario_category: enum
  route_id: ROUTE_014
  route_path: "/prototype/red-team/:scenario_id"
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  internal_demo_only: true
  synthetic_demo_only: true
  unsafe_example_visible: quarantined_only
  unsafe_example_copy_allowed: false
  unsafe_example_export_allowed: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  authority_effect: none
  decision_effect: none
  required_failure_reason: string
  required_safe_boundary_copy_ids: list
  required_audit_events: list
  repair_required: true
  ui_safety_revalidation_required: conditional_required
```

Red-team scenario stub rule:

> A red-team scenario stub may show unsafe behavior being blocked, not unsafe content being suggested.

---

## 15. Red-Team Scenario Stub Registry

The following red-team scenario stubs are required.

| Scenario Stub ID | Unsafe Attempt | Required Result |
|---|---|---|
| RT_STUB_001 | Impression heading | block preview/copy/export |
| RT_STUB_002 | Diagnosis heading | block preview/copy/export |
| RT_STUB_003 | Final diagnosis phrase | block preview/copy/export |
| RT_STUB_004 | Disease ruled out phrase | block preview/copy/export |
| RT_STUB_005 | Mimic excluded phrase | block preview/copy/export |
| RT_STUB_006 | Probability/ranking table | block preview/copy/export |
| RT_STUB_007 | Confirmed badge | block preview/copy/export |
| RT_STUB_008 | Treatment recommendation | block preview/copy/export |
| RT_STUB_009 | Test order phrase | block preview/copy/export |
| RT_STUB_010 | Procedure required phrase | block preview/copy/export |
| RT_STUB_011 | Follow-up due phrase | block preview/copy/export |
| RT_STUB_012 | Triage/disposition phrase | block preview/copy/export |
| RT_STUB_013 | Patient-facing summary | block preview/copy/export |
| RT_STUB_014 | Public-ready label | block display/copy/export |
| RT_STUB_015 | Product-ready label | block display/copy/export |
| RT_STUB_016 | Clinical validation claim | block display/copy/export |
| RT_STUB_017 | Diagnostic performance claim | block display/copy/export |
| RT_STUB_018 | Audit proves correctness claim | block audit display |
| RT_STUB_019 | Source confirms diagnosis claim | block display/copy/export |
| RT_STUB_020 | Authority envelope missing | block render/export |
| RT_STUB_021 | No-decision object missing | block decision-adjacent render/export |
| RT_STUB_022 | Unsafe copy attempt | block copy |
| RT_STUB_023 | Unsafe export attempt | block export |
| RT_STUB_024 | Red-team pass as clinical validation | block claim |
| RT_STUB_025 | Safe preview as clinical report | block claim |

Red-team registry rule:

> Every red-team scenario must demonstrate containment, not provide a template for unsafe output.

---

## 16. Red-Team Scenario Detail Structure

Every red-team scenario detail page must include:

```yaml
red_team_scenario_detail:
  scenario_id: string
  unsafe_attempt_type: string
  unsafe_example_container: quarantined
  blocked_badge: required
  failure_reason: required
  why_unsafe: required
  blocked_authority: required
  copy_allowed: false
  export_allowed: false
  repair_required: true
  ui_safety_revalidation_required: conditional_required
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  audit_event_reference: required
```

Blocked detail behavior:

- render unsafe example as normal text,
- provide “use this instead” clinical phrase,
- allow copy,
- allow export,
- imply clinical validation,
- imply product readiness,
- imply diagnostic performance,
- imply MDD consensus.

Scenario detail rule:

> Red-team detail must keep unsafe content inside quarantine.

---

## 17. Red-Team Quarantine Display Stub

Unsafe examples must render only inside quarantine display.

```yaml
red_team_quarantine_display_stub:
  display_mode: blocked_example_only
  container_label: "Blocked unsafe example — not reusable clinical output."
  required_warning: "This phrase is displayed only to demonstrate fail-closed behavior."
  copy_button_enabled: false
  export_button_enabled: false
  print_enabled: false
  share_enabled: false
  markdown_reuse_enabled: false
  required_boundary_copy:
    - "This is not advice."
    - "This is not diagnosis."
    - "This is not exclusion."
    - "This is not treatment."
    - "This is not an order."
    - "This is not a procedure decision."
    - "This is not follow-up."
    - "This is not triage."
    - "This is not patient-facing material."
    - "This is not clinical validation."
    - "This is not MDD consensus."
```

Quarantine display rule:

> Quarantined unsafe text must be visibly unsafe and technically non-reusable.

---

## 18. Red-Team Repair / Revalidation Stub

Red-team repair and revalidation must remain UI safety only.

```yaml
red_team_repair_revalidation_stub:
  repair_type: ui_safety_repair_only
  allowed_repairs:
    - remove_unsafe_heading
    - remove_unsafe_language
    - restore_authority_envelope
    - restore_no_decision_object
    - restore_quarantine_container
    - disable_copy_export
    - restore_failure_reason
    - restore_audit_binding
  blocked_repairs:
    - clinical_correction
    - diagnostic_correction
    - treatment_correction
    - validation_correction
    - performance_correction
  revalidation_type: ui_safety_only
  blocked_revalidation:
    - clinical_validation
    - diagnostic_performance_validation
    - expert_equivalence_validation
    - product_readiness_validation
    - public_readiness_validation
```

Required copy:

```text
Repair required: UI safety repair only. This is not clinical correction or clinical validation.
```

```text
UI safety revalidation only. This does not validate clinical performance.
```

Red-team repair rule:

> Red-team repair fixes containment, not medicine.

---

## 19. Export / Red-Team Audit Binding

Export and red-team stubs must bind to audit events.

Required export audit events:

- export_preview_requested,
- export_safety_check_started,
- authority_envelope_verified,
- no_decision_object_verified,
- safe_export_preview_available,
- unsafe_export_preview_blocked,
- unsafe_copy_attempt_blocked,
- unsafe_export_attempt_blocked,
- ui_safety_repair_required,
- ui_safety_revalidation_started.

Required red-team audit events:

- red_team_hub_viewed,
- red_team_scenario_viewed,
- unsafe_copy_attempt_blocked,
- unsafe_export_attempt_blocked,
- unsafe_ui_copy_phrase_blocked,
- authority_envelope_missing_blocked,
- no_decision_object_missing_blocked,
- validation_overclaim_attempt_blocked,
- readiness_overclaim_attempt_blocked,
- audit_correctness_claim_blocked.

Audit binding fields:

```yaml
export_red_team_audit_binding:
  event_id: string
  source_stub_id: string
  source_route_id: string
  source_scenario_id: optional
  source_export_preview_id: optional
  unsafe_content_class: optional
  result: enum(safe_preview_available, blocked, repair_required, revalidation_required)
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Audit binding rule:

> Export/red-team audit records containment and safety state, not clinical correctness.

---

## 20. Safe Preview Validation Checklist

Safe export preview stub validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| EXPORT_CHECK_001 | safe export preview stub schema defined | true |
| EXPORT_CHECK_002 | export section stub schema defined | true |
| EXPORT_CHECK_003 | safe export preview stub registry defined | true |
| EXPORT_CHECK_004 | required section order defined | true |
| EXPORT_CHECK_005 | export safety check stub defined | true |
| EXPORT_CHECK_006 | unsafe heading detector stub defined | true |
| EXPORT_CHECK_007 | unsafe language detector stub defined | true |
| EXPORT_CHECK_008 | copy/export block stub defined | true |
| EXPORT_CHECK_009 | export preview state machine defined | true |
| EXPORT_CHECK_010 | authority envelope required before preview content | true |
| EXPORT_CHECK_011 | no-decision object required before preview content | true |
| EXPORT_CHECK_012 | clinical report generator false | true |
| EXPORT_CHECK_013 | diagnostic report generator false | true |
| EXPORT_CHECK_014 | patient summary generator false | true |
| EXPORT_CHECK_015 | MDD consensus generator false | true |
| EXPORT_CHECK_016 | unsafe copy/export blocked | true |
| EXPORT_CHECK_017 | export audit binding defined | true |

Safe preview validation rule:

> Safe preview validation passes only if preview cannot become report, diagnosis, patient summary, MDD consensus, or reusable unsafe output.

---

## 21. Red-Team Scenario Validation Checklist

Red-team scenario stub validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| RT_CHECK_001 | red-team scenario stub schema defined | true |
| RT_CHECK_002 | red-team scenario registry defined | true |
| RT_CHECK_003 | scenario detail structure defined | true |
| RT_CHECK_004 | quarantine display stub defined | true |
| RT_CHECK_005 | red-team repair/revalidation stub defined | true |
| RT_CHECK_006 | unsafe examples visible only as quarantined | true |
| RT_CHECK_007 | unsafe examples copy_allowed false | true |
| RT_CHECK_008 | unsafe examples export_allowed false | true |
| RT_CHECK_009 | red-team pass does not equal clinical validation | true |
| RT_CHECK_010 | red-team pass does not equal product readiness | true |
| RT_CHECK_011 | red-team pass does not equal public readiness | true |
| RT_CHECK_012 | red-team pass does not equal diagnostic performance | true |
| RT_CHECK_013 | red-team audit binding defined | true |
| RT_CHECK_014 | repair means UI safety repair only | true |
| RT_CHECK_015 | revalidation means UI safety revalidation only | true |

Red-team validation rule:

> Red-team validation passes only if unsafe examples are contained and cannot become clinical output.

---

## 22. Export / Red-Team Blocked Meanings

The following meanings remain blocked.

| Blocked Meaning | Applies To |
|---|---|
| preview is clinical report | export preview |
| preview is diagnosis | export preview |
| preview is clinical conclusion | export preview |
| preview is treatment plan | export preview |
| preview is order plan | export preview |
| preview is follow-up plan | export preview |
| preview is triage/disposition | export preview |
| preview is patient summary | export preview |
| preview is MDD consensus | export preview |
| detector is clinical validator | detector stubs |
| detector measures accuracy | detector stubs |
| repair is clinical correction | repair stubs |
| revalidation is clinical validation | revalidation stubs |
| red-team pass proves safety | red-team stubs |
| red-team unsafe example is reusable | red-team stubs |
| audit proves correctness | audit bindings |

Blocked meaning rule:

> Export and red-team stubs must not smuggle clinical authority through safety language.

---

## 23. v0.16.6 Acceptance Criteria

v0.16.6 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| safe export preview stub registry defined | true |
| export preview section stub structure defined | true |
| export preview safety check stub defined | true |
| unsafe heading detector stub defined | true |
| unsafe language detector stub defined | true |
| copy/export block stub defined | true |
| export preview state machine stub defined | true |
| red-team scenario stub registry defined | true |
| red-team scenario detail structure defined | true |
| red-team quarantine display stub defined | true |
| red-team repair/revalidation stub defined | true |
| export/red-team audit event binding defined | true |
| safe preview validation checklist defined | true |
| red-team scenario validation checklist defined | true |
| export/red-team blocked meanings defined | true |
| export preview stub is not clinical report generator | true |
| red-team stub does not create reusable unsafe output | true |
| detector stubs do not validate clinical performance | true |
| repair stub is not clinical correction | true |
| revalidation stub is not clinical validation | true |
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

v0.16.6 acceptance rule:

> The safe export preview and red-team scenario stub plan is accepted only if preview, detector, quarantine, repair, revalidation, copy/export, and audit behavior remain synthetic, non-clinical, non-authoritative, non-patient-facing, non-validating, non-ready, and fail-closed.

---

## 24. Next Step

The next recommended step is:

- v0.16.7 — Prototype Build Scaffold Validation Checklist

v0.16.7 should define:

- scaffold-wide validation checklist,
- route/screen registry validation,
- synthetic fixture/state validation,
- UI copy source mapping validation,
- fail-closed/disabled control validation,
- audit event validation,
- safe export preview/red-team stub validation,
- no real patient data validation,
- no DICOM/report/PACS/EHR validation,
- no clinical validation/readiness validation,
- no diagnostic/action authority validation,
- no patient-facing/MDD replacement validation,
- v0.16 pre-seal safety gate.

v0.16.7 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 25. Governance Statement

This document defines safe export preview stubs and red-team scenario stubs.

It opens export/red-team scaffold planning only.

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

The v0.16.6 governance discipline is:

> “Do not let export preview stubs become clinical report generators.”

The red-team discipline is:

> “Do not let red-team stubs create reusable unsafe output.”