# ILD Reasoning Platform — Fail-Closed State Stub / Disabled Clinical Control Plan v1

Version: v0.16.4  
Status: fail_closed_state_stub_disabled_clinical_control_plan  
Scope: Fail-closed state stub registry, disabled clinical control registry, unsafe route attempt stub, real patient data attempt stub, DICOM/report import attempt stub, diagnosis/action attempt stub, patient-facing leak attempt stub, validation/readiness overclaim attempt stub, unsafe copy/export attempt stub, authority envelope missing stub, no-decision object missing stub, disabled control explanation requirements, fail-closed audit event binding, repair-required behavior, and UI safety revalidation stub behavior  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.16.4 — Fail-Closed State Stub / Disabled Clinical Control Plan.

v0.16.4 translates the sealed prototype UI behavior, route registry, synthetic fixture registry, and source-governed UI copy contracts into a fail-closed state and disabled clinical control scaffold plan.

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

Its purpose is to define how unsafe scaffold states must fail closed before they become usable clinical behavior, reusable clinical language, patient-facing output, validation claim, readiness claim, or hidden clinical feature.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16.4 fail-closed principle is:

> “Unsafe prototype behavior must stop as explicit safety state, not continue as hidden clinical capability.”

The disabled control principle is:

> “A disabled clinical control may teach a boundary, but it must not advertise a hidden clinical feature.”

---

## 2. Relationship to v0.16.0–v0.16.3

v0.16.4 inherits:

- v0.16.0 — Source-Governed Prototype Build Scaffold Entry Gate,
- v0.16.1 — Prototype Route / Screen Registry Implementation Plan,
- v0.16.2 — Synthetic Fixture Registry / Demo State Binding Plan,
- v0.16.3 — UI Copy Source Mapping / Safety Language Contract.

v0.16.0 opened source-governed build scaffold planning.

v0.16.1 defined allowed and blocked routes and screen registry.

v0.16.2 defined synthetic fixture registry and demo state binding.

v0.16.3 defined source-governed safety language.

v0.16.4 defines fail-closed state stubs and disabled clinical control planning.

v0.16.4 does not broaden v0.16.0–v0.16.3.

v0.16.4 must not open:

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

Fail-closed inheritance rule:

> v0.16.4 may define safety stops only; it may not implement clinical paths behind those stops.

---

## 3. Global Authority Envelope

Every fail-closed state stub, disabled control, blocked route attempt, blocked fixture binding, blocked copy/export state, repair-required state, UI safety revalidation state, warning modal, tooltip, explanation, and audit event must inherit the following authority envelope.

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

No fail-closed state or disabled control may create an exception to this envelope.

Authority fail-closed rule:

> A blocked action cannot become authority by being visible.

---

## 4. Global No-Decision Object

The no-decision object remains active in all fail-closed and disabled-control contexts.

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

Required fail-closed display meaning:

- blocked diagnosis attempt does not generate diagnosis,
- blocked exclusion attempt does not exclude disease or mimic,
- blocked treatment attempt does not select treatment,
- blocked order attempt does not order tests,
- blocked procedure attempt does not decide procedure,
- blocked follow-up attempt does not schedule follow-up,
- blocked triage attempt does not assign triage,
- blocked export attempt does not generate patient-facing output,
- blocked MDD route does not generate MDD consensus.

No-decision fail-closed rule:

> A blocked clinical action must explicitly show that no clinical decision occurred.

---

## 5. Fail-Closed State Stub Object Schema

Every fail-closed state stub must conform to the following schema.

```yaml
fail_closed_state_stub:
  stub_id: string
  version: v0.16.4
  stub_name: string
  unsafe_attempt_type: enum
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  trigger_surface: enum(route, screen, component, fixture, copy, export, audit, validation, readiness)
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  authority_effect: none
  decision_effect: none
  user_output_allowed: false
  navigation_allowed: false
  copy_allowed: false
  export_allowed: false
  repair_required: true
  ui_safety_revalidation_required: conditional_required
  audit_event_required: true
  required_failure_reason: string
  required_boundary_copy_id: string
```

Fail-closed stub rule:

> A fail-closed stub must stop the unsafe behavior and explain why it stopped.

---

## 6. Disabled Clinical Control Object Schema

Every disabled clinical control must conform to the following schema.

```yaml
disabled_clinical_control:
  control_id: string
  version: v0.16.4
  control_label: string
  control_category: enum
  parent_route_id: optional
  parent_screen_id: optional
  parent_component_id: optional
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  enabled: false
  clickable: false
  navigation_allowed: false
  clinical_action_allowed: false
  authority_effect: none
  decision_effect: none
  required_disabled_reason: string
  required_copy_id: string
  hidden_feature_implication_allowed: false
  audit_event_on_attempt_required: true
```

Disabled control rule:

> Disabled controls may appear only as boundary-teaching artifacts, not as future clinical feature marketing.

---

## 7. Fail-Closed State Stub Registry

The following fail-closed state stubs are required.

| Stub ID | Unsafe Attempt | Required Result |
|---|---|---|
| FC_STUB_001 | unsafe route attempt | block navigation |
| FC_STUB_002 | blocked clinical route attempt | block navigation |
| FC_STUB_003 | real patient data attempt | block intake/state creation |
| FC_STUB_004 | deidentified real patient data attempt | block intake/state creation |
| FC_STUB_005 | DICOM import attempt | block import/state creation |
| FC_STUB_006 | HRCT import attempt | block import/state creation |
| FC_STUB_007 | real report import/paste attempt | block import/state creation |
| FC_STUB_008 | PACS connection attempt | block connection |
| FC_STUB_009 | EHR connection attempt | block connection |
| FC_STUB_010 | diagnosis generation attempt | block output |
| FC_STUB_011 | disease ranking/probability attempt | block output |
| FC_STUB_012 | disease/mimic exclusion attempt | block output |
| FC_STUB_013 | treatment recommendation attempt | block output |
| FC_STUB_014 | test order attempt | block action |
| FC_STUB_015 | procedure recommendation attempt | block action |
| FC_STUB_016 | follow-up scheduling attempt | block action |
| FC_STUB_017 | triage/disposition attempt | block action |
| FC_STUB_018 | patient-facing output attempt | block output/export |
| FC_STUB_019 | clinical validation overclaim attempt | block display |
| FC_STUB_020 | diagnostic performance claim attempt | block display |
| FC_STUB_021 | product/public readiness overclaim attempt | block display |
| FC_STUB_022 | MDD consensus/replacement attempt | block display/output |
| FC_STUB_023 | unsafe copy attempt | block copy |
| FC_STUB_024 | unsafe export attempt | block export |
| FC_STUB_025 | authority envelope missing | block render/export |
| FC_STUB_026 | no-decision object missing | block decision-adjacent render/export |
| FC_STUB_027 | unsafe visual semantics attempt | block visual state |
| FC_STUB_028 | unsafe fixture binding attempt | block binding |
| FC_STUB_029 | unsafe UI copy phrase detected | block display |
| FC_STUB_030 | audit correctness claim attempt | block audit display |

Fail-closed registry rule:

> Every known unsafe path must terminate in an explicit fail-closed state.

---

## 8. Disabled Clinical Control Registry

The following disabled controls may be planned only with boundary-teaching copy.

| Control ID | Disabled Control | Required Explanation |
|---|---|---|
| DC_CTRL_001 | Upload real patient data | Real patient data is not allowed in this internal prototype. |
| DC_CTRL_002 | Upload deidentified patient data | Deidentified real patient data is not allowed. |
| DC_CTRL_003 | Import DICOM | DICOM import is not opened. |
| DC_CTRL_004 | Import HRCT image | HRCT image import is not opened. |
| DC_CTRL_005 | Paste real clinical report | Real clinical report import is not opened. |
| DC_CTRL_006 | Connect PACS | PACS integration is not opened. |
| DC_CTRL_007 | Connect EHR | EHR integration is not opened. |
| DC_CTRL_008 | Generate diagnosis | Diagnostic authority is none. |
| DC_CTRL_009 | Rank diagnoses | Disease ranking and probability display are blocked. |
| DC_CTRL_010 | Rule out disease | Disease exclusion authority is none. |
| DC_CTRL_011 | Confirm mimic | Mimic confirmation is not allowed. |
| DC_CTRL_012 | Exclude mimic | Mimic exclusion is not allowed. |
| DC_CTRL_013 | Recommend treatment | Treatment authority is none. |
| DC_CTRL_014 | Order test | Test-order authority is none. |
| DC_CTRL_015 | Recommend procedure | Procedure decision authority is none. |
| DC_CTRL_016 | Schedule follow-up | Follow-up authority is none. |
| DC_CTRL_017 | Assign triage | Triage authority is none. |
| DC_CTRL_018 | Generate patient summary | Patient-facing output is not allowed. |
| DC_CTRL_019 | Mark clinically validated | Clinical validation is not opened. |
| DC_CTRL_020 | Mark product ready | Product readiness is false. |
| DC_CTRL_021 | Publish public demo | Public readiness is false. |
| DC_CTRL_022 | Generate MDD consensus | MDD replacement is not allowed. |
| DC_CTRL_023 | Export clinical report | Clinical report generation is not allowed. |
| DC_CTRL_024 | Copy unsafe red-team phrase | Unsafe examples are not reusable output. |

Disabled registry rule:

> Disabled controls must explain blocked authority, not imply dormant capability.

---

## 9. Unsafe Route Attempt Stub

Unsafe route attempts must block navigation before rendering.

```yaml
unsafe_route_attempt_stub:
  stub_id: FC_STUB_001
  trigger:
    - route_not_in_allowed_registry
    - route_in_blocked_registry
    - blocked_navigation_edge_requested
  result:
    navigation_allowed: false
    route_render_allowed: false
    user_output_allowed: false
    repair_required: true
    audit_event_required: true
  required_copy:
    - "This route is blocked because it would create clinical, patient-facing, validation, product-readiness, public-readiness, or MDD-replacement behavior."
```

Blocked route attempts include:

- `/patient`,
- `/clinical`,
- `/dicom/import`,
- `/pacs/connect`,
- `/ehr/connect`,
- `/diagnosis`,
- `/treatment`,
- `/orders`,
- `/procedures`,
- `/follow-up`,
- `/triage`,
- `/validation/clinical`,
- `/product-ready`,
- `/public`,
- `/mdd/consensus`.

Unsafe route rule:

> A blocked route must not render partially, silently redirect to unsafe content, or imply a future clinical feature.

---

## 10. Real Patient Data Attempt Stub

Real patient data attempts must fail closed before state creation.

```yaml
real_patient_data_attempt_stub:
  stub_id: FC_STUB_003
  trigger:
    - upload_real_patient_file
    - enter_patient_identifier
    - paste_patient_text
    - patient_like_id_detected
  result:
    intake_allowed: false
    state_creation_allowed: false
    fixture_binding_allowed: false
    export_allowed: false
    audit_event_required: true
  required_copy:
    - "Real patient data is not allowed in this internal synthetic prototype."
```

Blocked material:

- patient name,
- date of birth,
- MRN,
- accession number,
- institution case ID,
- clinical encounter ID,
- real clinical note,
- real imaging report,
- real pathology report,
- real microbiology report.

Real patient data rule:

> Real patient data must fail closed before it becomes fixture, state, route parameter, copy, export, or audit content.

---

## 11. Deidentified Real Patient Data Attempt Stub

Deidentified real patient data attempts must also fail closed.

```yaml
deidentified_real_patient_data_attempt_stub:
  stub_id: FC_STUB_004
  trigger:
    - upload_deidentified_patient_case
    - paste_deidentified_report
    - import_deidentified_dataset
    - mark_real_case_as_synthetic
  result:
    intake_allowed: false
    fixture_binding_allowed: false
    state_creation_allowed: false
    validation_dataset_creation_allowed: false
    audit_event_required: true
  required_copy:
    - "Deidentified real patient data is not allowed. Deidentification does not convert real patient material into a synthetic demo fixture."
```

Deidentified data rule:

> Deidentified real patient material remains real patient material and is blocked.

---

## 12. DICOM / HRCT Import Attempt Stub

DICOM and HRCT import attempts must fail closed.

```yaml
dicom_hrct_import_attempt_stub:
  stub_ids:
    - FC_STUB_005
    - FC_STUB_006
  trigger:
    - dicom_file_selected
    - hrct_image_selected
    - image_viewer_route_requested
    - dicom_uid_detected
    - study_uid_detected
    - series_uid_detected
  result:
    import_allowed: false
    viewer_allowed: false
    state_creation_allowed: false
    audit_event_required: true
  required_copy:
    - "DICOM and HRCT image import are not opened in this scaffold."
```

Blocked representations:

- DICOM viewer,
- image upload zone,
- HRCT upload modal,
- PACS preview,
- image-derived finding state,
- clinical image annotation state.

DICOM/HRCT rule:

> The scaffold may not create a visual clinical image pathway.

---

## 13. Real Report Import Attempt Stub

Real clinical report import or paste attempts must fail closed.

```yaml
real_report_import_attempt_stub:
  stub_id: FC_STUB_007
  trigger:
    - report_paste_attempt
    - report_file_upload_attempt
    - pathology_report_import_attempt
    - microbiology_report_import_attempt
    - clinical_note_import_attempt
  result:
    import_allowed: false
    text_ingestion_allowed: false
    state_creation_allowed: false
    audit_event_required: true
  required_copy:
    - "Real clinical report import is not opened in this scaffold."
```

Blocked report types:

- radiology report,
- pathology report,
- microbiology report,
- lab report,
- clinical note,
- MDD note,
- discharge summary,
- oncology note,
- rheumatology note.

Report import rule:

> Clinical text cannot enter the prototype under the label of synthetic intake.

---

## 14. PACS / EHR Connection Attempt Stub

PACS and EHR connection attempts must fail closed.

```yaml
pacs_ehr_connection_attempt_stub:
  stub_ids:
    - FC_STUB_008
    - FC_STUB_009
  trigger:
    - pacs_connect_requested
    - ehr_connect_requested
    - dicomweb_endpoint_added
    - fhir_endpoint_added
    - clinical_api_key_added
  result:
    connection_allowed: false
    credential_storage_allowed: false
    clinical_fetch_allowed: false
    audit_event_required: true
  required_copy:
    - "PACS and EHR integration are not opened in this internal prototype scaffold."
```

PACS/EHR rule:

> No connector may create hidden clinical integration.

---

## 15. Diagnosis / Ranking / Exclusion Attempt Stub

Diagnostic and exclusion attempts must fail closed.

```yaml
diagnosis_ranking_exclusion_attempt_stub:
  stub_ids:
    - FC_STUB_010
    - FC_STUB_011
    - FC_STUB_012
  trigger:
    - generate_diagnosis_requested
    - final_diagnosis_label_requested
    - most_likely_diagnosis_requested
    - probability_display_requested
    - disease_rule_out_requested
    - mimic_confirmation_requested
    - mimic_exclusion_requested
  result:
    output_allowed: false
    copy_allowed: false
    export_allowed: false
    decision_effect: none
    audit_event_required: true
  required_copy:
    - "Diagnostic, ranking, probability, confirmation, and exclusion language are blocked because diagnostic and exclusion authority are none."
```

Blocked outputs:

- final diagnosis,
- most likely diagnosis,
- diagnosis ranking,
- probability percentage,
- confidence score,
- ruled out,
- excluded,
- confirmed mimic,
- excluded mimic.

Diagnostic/exclusion rule:

> Fail-closed diagnosis behavior must not return softer diagnostic wording.

---

## 16. Treatment / Order / Procedure / Follow-Up / Triage Attempt Stub

Clinical action attempts must fail closed.

```yaml
clinical_action_attempt_stub:
  stub_ids:
    - FC_STUB_013
    - FC_STUB_014
    - FC_STUB_015
    - FC_STUB_016
    - FC_STUB_017
  trigger:
    - recommend_treatment_requested
    - order_test_requested
    - recommend_procedure_requested
    - schedule_follow_up_requested
    - assign_triage_requested
    - disposition_requested
  result:
    action_allowed: false
    output_allowed: false
    copy_allowed: false
    export_allowed: false
    decision_effect: none
    audit_event_required: true
  required_copy:
    - "Clinical action language is blocked because treatment, ordering, procedure, follow-up, and triage authority are none."
```

Blocked actions:

- treatment selection,
- medication or therapy suggestion,
- test order,
- biopsy/procedure recommendation,
- repeat CT timing,
- follow-up interval,
- outpatient/inpatient disposition,
- triage level.

Clinical action rule:

> A blocked clinical action cannot return advice, recommendation, or scheduling language.

---

## 17. Patient-Facing Leak Attempt Stub

Patient-facing output attempts must fail closed.

```yaml
patient_facing_leak_attempt_stub:
  stub_id: FC_STUB_018
  trigger:
    - generate_patient_summary_requested
    - patient_share_link_requested
    - patient_download_requested
    - patient_friendly_explanation_requested
    - patient_portal_export_requested
  result:
    patient_output_allowed: false
    export_allowed: false
    share_allowed: false
    copy_allowed: false
    audit_event_required: true
  required_copy:
    - "Patient-facing output is not allowed."
```

Blocked outputs:

- patient summary,
- patient education handout,
- patient-friendly report,
- shareable patient link,
- portal export,
- caregiver explanation.

Patient-facing rule:

> Prototype output must never become patient material.

---

## 18. Validation / Performance Overclaim Attempt Stub

Clinical validation and performance overclaims must fail closed.

```yaml
validation_performance_overclaim_attempt_stub:
  stub_ids:
    - FC_STUB_019
    - FC_STUB_020
  trigger:
    - clinically_validated_label_requested
    - accuracy_metric_requested
    - sensitivity_metric_requested
    - specificity_metric_requested
    - auc_metric_requested
    - expert_equivalence_claim_requested
    - red_team_pass_as_clinical_validation_requested
    - ui_safety_pass_as_clinical_validation_requested
  result:
    display_allowed: false
    export_allowed: false
    product_readiness_effect: none
    clinical_validation_effect: none
    audit_event_required: true
  required_copy:
    - "Clinical validation is not opened. UI safety validation is not clinical validation."
```

Validation overclaim rule:

> No UI safety pass, red-team pass, or audit trace can become clinical validation.

---

## 19. Product / Public Readiness Overclaim Attempt Stub

Product and public readiness overclaims must fail closed.

```yaml
readiness_overclaim_attempt_stub:
  stub_id: FC_STUB_021
  trigger:
    - product_ready_label_requested
    - public_ready_label_requested
    - deployment_ready_label_requested
    - safe_for_clinical_use_label_requested
    - publish_public_demo_requested
    - release_product_requested
  result:
    display_allowed: false
    publish_allowed: false
    release_allowed: false
    product_readiness_effect: none
    public_readiness_effect: none
    audit_event_required: true
  required_copy:
    - "Product readiness is false and public readiness is false."
```

Readiness rule:

> Internal scaffold progress must not become release readiness.

---

## 20. MDD Consensus / Replacement Attempt Stub

MDD consensus or replacement attempts must fail closed.

```yaml
mdd_consensus_replacement_attempt_stub:
  stub_id: FC_STUB_022
  trigger:
    - generate_mdd_consensus_requested
    - mdd_complete_label_requested
    - multidisciplinary_final_decision_requested
    - mdd_replacement_claim_requested
  result:
    output_allowed: false
    export_allowed: false
    consensus_generated: false
    decision_effect: none
    audit_event_required: true
  required_copy:
    - "MDD preparation preview is not MDD consensus. MDD replacement is not allowed."
```

MDD rule:

> MDD preparation support cannot become MDD outcome.

---

## 21. Unsafe Copy / Export Attempt Stub

Unsafe copy and export attempts must fail closed.

```yaml
unsafe_copy_export_attempt_stub:
  stub_ids:
    - FC_STUB_023
    - FC_STUB_024
  trigger:
    - copy_unsafe_phrase_requested
    - copy_blocked_preview_requested
    - export_unsafe_preview_requested
    - export_red_team_phrase_requested
    - copy_diagnosis_or_action_language_requested
  result:
    copy_allowed: false
    export_allowed: false
    reusable_output_created: false
    audit_event_required: true
  required_copy:
    - "Unsafe language cannot be copied or exported as reusable output."
```

Unsafe copy/export rule:

> Unsafe text may be quarantined for demonstration only; it cannot leave as reusable output.

---

## 22. Authority Envelope Missing Stub

Missing authority envelope must fail closed.

```yaml
authority_envelope_missing_stub:
  stub_id: FC_STUB_025
  trigger:
    - authority_envelope_not_rendered
    - authority_envelope_missing_from_export_preview
    - authority_envelope_missing_from_decision_adjacent_screen
    - authority_envelope_missing_from_fail_closed_modal
  result:
    route_render_allowed: false
    export_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: true
  required_copy:
    - "Authority envelope is required before this state can render."
```

Authority envelope missing rule:

> Safety-critical UI cannot render without visible non-authority.

---

## 23. No-Decision Object Missing Stub

Missing no-decision object must fail closed.

```yaml
no_decision_object_missing_stub:
  stub_id: FC_STUB_026
  trigger:
    - no_decision_object_not_rendered
    - no_decision_object_missing_from_export_preview
    - no_decision_object_missing_from_reasoning_map
    - no_decision_object_missing_from_fail_closed_modal
  result:
    route_render_allowed: false
    export_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: true
  required_copy:
    - "No-decision object is required before this state can render."
```

No-decision missing rule:

> Decision-adjacent UI cannot render unless decisions not made are visible.

---

## 24. Unsafe Visual Semantics Attempt Stub

Unsafe visual semantics must fail closed.

```yaml
unsafe_visual_semantics_attempt_stub:
  stub_id: FC_STUB_027
  trigger:
    - color_as_probability_detected
    - icon_as_authority_detected
    - edge_as_likelihood_detected
    - map_as_diagnostic_proof_detected
    - flow_as_treatment_pathway_detected
    - diagnostic_heatmap_requested
  result:
    visual_render_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: true
  required_copy:
    - "Visual semantics are blocked because visual elements cannot imply diagnosis, probability, authority, treatment pathway, or diagnostic proof."
```

Visual semantics rule:

> Visual design must fail closed when it starts carrying clinical meaning.

---

## 25. Unsafe Fixture Binding Attempt Stub

Unsafe fixture binding must fail closed.

```yaml
unsafe_fixture_binding_attempt_stub:
  stub_id: FC_STUB_028
  trigger:
    - fixture_type_not_allowed
    - fixture_has_real_patient_marker
    - fixture_has_deidentified_patient_marker
    - fixture_has_dicom_marker
    - fixture_has_real_report_marker
    - fixture_has_final_diagnosis_field
    - fixture_has_probability_field
    - fixture_claims_clinical_validation
    - fixture_targets_blocked_route
    - fixture_targets_blocked_screen
  result:
    binding_allowed: false
    state_creation_allowed: false
    route_navigation_allowed: false
    repair_required: true
    audit_event_required: true
  required_copy:
    - "Fixture binding is blocked because only sealed synthetic demo fixtures may create prototype state."
```

Fixture binding rule:

> Unsafe fixtures must stop before they become workspace state.

---

## 26. Unsafe UI Copy Phrase Detected Stub

Unsafe UI copy must fail closed before display.

```yaml
unsafe_ui_copy_phrase_detected_stub:
  stub_id: FC_STUB_029
  trigger:
    - blocked_phrase_detected
    - diagnosis_language_detected
    - exclusion_language_detected
    - treatment_language_detected
    - order_language_detected
    - procedure_language_detected
    - follow_up_language_detected
    - triage_language_detected
    - validation_overclaim_detected
    - readiness_overclaim_detected
  result:
    display_allowed: false
    copy_allowed: false
    export_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: true
  required_copy:
    - "Unsafe UI language is blocked because it may imply clinical output, validation, readiness, or patient-facing use."
```

Unsafe copy phrase rule:

> Unsafe copy must be repaired before it reaches UI display.

---

## 27. Audit Correctness Claim Attempt Stub

Audit correctness claims must fail closed.

```yaml
audit_correctness_claim_attempt_stub:
  stub_id: FC_STUB_030
  trigger:
    - audit_claims_correctness
    - audit_claims_diagnosis_validated
    - audit_claims_clinical_validation_passed
    - audit_claims_performance_measured
    - audit_claims_expert_equivalence
  result:
    audit_display_allowed: false
    repair_required: true
    ui_safety_revalidation_required: true
    audit_event_required: true
  required_copy:
    - "Audit trace explains UI state, not medical correctness."
```

Audit correctness rule:

> Audit can trace state movement, not validate truth.

---

## 28. Disabled Control Explanation Requirements

Every disabled control must include:

```yaml
disabled_control_explanation_requirements:
  explicit_disabled_state: true
  blocked_authority_named: true
  source_contract_named: true
  hidden_feature_implication_blocked: true
  audit_event_on_attempt: true
  no_clinical_action_created: true
```

Required explanation pattern:

```text
This control is disabled because [blocked authority / blocked data path / blocked readiness path]. This internal prototype is synthetic-only, non-clinical, non-patient-facing, non-public-ready, non-product-ready, and not clinically validated.
```

Blocked explanation patterns:

- “coming soon,”
- “unlock later,”
- “enable clinical mode,”
- “available in product version,”
- “connect PACS soon,”
- “upload patient case soon,”
- “start validation soon,”
- unexplained disabled state.

Disabled explanation rule:

> The explanation must close the door, not tease the door.

---

## 29. Repair-Required Stub Behavior

Repair is allowed only as UI safety repair.

```yaml
repair_required_stub_behavior:
  repair_type: ui_safety_repair_only
  allowed_repairs:
    - restore_authority_envelope
    - restore_no_decision_object
    - restore_synthetic_label
    - remove_blocked_route
    - remove_unsafe_copy
    - remove_unsafe_visual_semantics
    - remove_unsafe_export_heading
    - disable_unsafe_control
    - remove_blocked_fixture_binding
    - restore_audit_event_requirement
  blocked_repairs:
    - clinical_correction
    - diagnostic_correction
    - treatment_correction
    - probability_recalculation
    - performance_improvement
    - clinical_validation
    - product_readiness_fix
    - public_readiness_approval
```

Required repair copy:

```text
Repair required: UI safety repair only. This is not clinical correction or clinical validation.
```

Repair rule:

> Repair fixes unsafe scaffold behavior, not medical content.

---

## 30. UI Safety Revalidation Stub Behavior

Revalidation in v0.16.4 means UI safety revalidation only.

```yaml
ui_safety_revalidation_stub_behavior:
  revalidation_type: ui_safety_only
  allowed_revalidation:
    - rerun_fail_closed_checks
    - verify_disabled_control_explanations
    - verify_authority_envelope_visible
    - verify_no_decision_object_visible
    - verify_blocked_route_absent
    - verify_unsafe_copy_removed
    - verify_copy_export_disabled
    - verify_audit_event_recorded
    - verify_no_new_authority_opened
  blocked_revalidation:
    - clinical_validation
    - diagnostic_performance_validation
    - treatment_safety_validation
    - workflow_deployment_validation
    - expert_equivalence_validation
    - regulatory_validation
```

Required revalidation copy:

```text
UI safety revalidation only. This does not validate clinical performance.
```

Revalidation rule:

> Revalidation checks scaffold safety, not medicine.

---

## 31. Fail-Closed Audit Event Binding

Every fail-closed state must bind to an audit event.

```yaml
fail_closed_audit_event:
  event_id: string
  event_type: fail_closed_state_triggered
  source_stub_id: string
  unsafe_attempt_type: string
  trigger_surface: string
  route_id: optional
  screen_id: optional
  component_id: optional
  fixture_id: optional
  copy_id: optional
  export_preview_id: optional
  result: blocked
  repair_required: boolean
  ui_safety_revalidation_required: boolean
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Required fail-closed audit event types:

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

Audit binding rule:

> Every fail-closed state must leave a trace, but the trace must not claim correctness.

---

## 32. Fail-Closed State Validation Checklist

v0.16.4 fail-closed state validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| FC_CHECK_001 | fail-closed state stub schema defined | true |
| FC_CHECK_002 | disabled clinical control schema defined | true |
| FC_CHECK_003 | fail-closed stub registry defined | true |
| FC_CHECK_004 | disabled clinical control registry defined | true |
| FC_CHECK_005 | unsafe route attempt stub defined | true |
| FC_CHECK_006 | real patient data attempt stub defined | true |
| FC_CHECK_007 | deidentified real patient data attempt stub defined | true |
| FC_CHECK_008 | DICOM/HRCT import attempt stub defined | true |
| FC_CHECK_009 | real report import attempt stub defined | true |
| FC_CHECK_010 | PACS/EHR connection attempt stub defined | true |
| FC_CHECK_011 | diagnosis/ranking/exclusion attempt stub defined | true |
| FC_CHECK_012 | treatment/order/procedure/follow-up/triage attempt stub defined | true |
| FC_CHECK_013 | patient-facing leak attempt stub defined | true |
| FC_CHECK_014 | validation/performance overclaim stub defined | true |
| FC_CHECK_015 | product/public readiness overclaim stub defined | true |
| FC_CHECK_016 | MDD consensus/replacement attempt stub defined | true |
| FC_CHECK_017 | unsafe copy/export attempt stub defined | true |
| FC_CHECK_018 | authority envelope missing stub defined | true |
| FC_CHECK_019 | no-decision object missing stub defined | true |
| FC_CHECK_020 | unsafe visual semantics stub defined | true |
| FC_CHECK_021 | unsafe fixture binding stub defined | true |
| FC_CHECK_022 | unsafe UI copy phrase stub defined | true |
| FC_CHECK_023 | audit correctness claim stub defined | true |
| FC_CHECK_024 | repair-required behavior defined | true |
| FC_CHECK_025 | UI safety revalidation behavior defined | true |
| FC_CHECK_026 | fail-closed audit event binding defined | true |

Fail-closed validation rule:

> Fail-closed validation passes only if every unsafe scaffold path has an explicit blocked state.

---

## 33. Disabled Control Validation Checklist

Disabled clinical control validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| DC_CHECK_001 | all disabled controls enabled=false | true |
| DC_CHECK_002 | all disabled controls clickable=false | true |
| DC_CHECK_003 | all disabled controls navigation_allowed=false | true |
| DC_CHECK_004 | all disabled controls have explanation | true |
| DC_CHECK_005 | all explanations name blocked authority or data path | true |
| DC_CHECK_006 | no disabled control says coming soon clinical mode | true |
| DC_CHECK_007 | no disabled control advertises hidden clinical feature | true |
| DC_CHECK_008 | all disabled controls map to source contract | true |
| DC_CHECK_009 | all disabled controls trigger audit on attempt | true |
| DC_CHECK_010 | disabled diagnosis controls cannot generate output | true |
| DC_CHECK_011 | disabled action controls cannot create action | true |
| DC_CHECK_012 | disabled import controls cannot create state | true |
| DC_CHECK_013 | disabled validation/readiness controls cannot create claim | true |

Disabled control validation rule:

> Disabled controls pass only if they teach blocked authority without implying future clinical availability.

---

## 34. v0.16.4 Acceptance Criteria

v0.16.4 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| fail-closed state stub registry defined | true |
| disabled clinical control registry defined | true |
| unsafe route attempt stub defined | true |
| real patient data attempt stub defined | true |
| deidentified real patient data attempt stub defined | true |
| DICOM/HRCT import attempt stub defined | true |
| real report import attempt stub defined | true |
| PACS/EHR connection attempt stub defined | true |
| diagnosis/action attempt stubs defined | true |
| patient-facing leak attempt stub defined | true |
| validation/readiness overclaim attempt stubs defined | true |
| unsafe copy/export attempt stub defined | true |
| authority envelope missing stub defined | true |
| no-decision object missing stub defined | true |
| unsafe visual semantics stub defined | true |
| unsafe fixture binding stub defined | true |
| unsafe UI copy phrase stub defined | true |
| audit correctness claim attempt stub defined | true |
| disabled control explanation requirements defined | true |
| repair-required behavior defined | true |
| UI safety revalidation behavior defined | true |
| fail-closed audit event binding defined | true |
| fail-closed validation checklist defined | true |
| disabled control validation checklist defined | true |
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

v0.16.4 acceptance rule:

> The fail-closed and disabled control plan is accepted only if unsafe scaffold behavior cannot render, navigate, copy, export, validate, or imply hidden clinical capability.

---

## 35. Next Step

The next recommended step is:

- v0.16.5 — Audit Event Stub / Traceability Implementation Plan

v0.16.5 should define:

- audit event stub registry,
- route audit events,
- screen audit events,
- component audit events,
- fixture binding audit events,
- fail-closed audit events,
- export preview audit events,
- red-team audit events,
- disabled control attempt audit events,
- audit event schema,
- audit event severity categories,
- audit event source mapping,
- audit trace display planning,
- blocked audit meanings,
- audit validation checklist.

v0.16.5 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 36. Governance Statement

This document defines fail-closed state stubs and disabled clinical control planning.

It opens safety stop scaffold planning only.

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

The v0.16.4 governance discipline is:

> “Do not let unsafe scaffold behavior become hidden clinical capability.”

The disabled-control discipline is:

> “Do not let a disabled clinical control advertise a future clinical feature.”