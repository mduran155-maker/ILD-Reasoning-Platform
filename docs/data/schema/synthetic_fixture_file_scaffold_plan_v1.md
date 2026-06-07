# ILD Reasoning Platform — Synthetic Fixture File Scaffold Plan v1

Version: v0.17.3  
Status: synthetic_fixture_file_scaffold_plan  
Scope: Allowed synthetic fixture file registry, blocked fixture file registry, synthetic case fixture file naming, demo reasoning session fixture file naming, demo intake binding fixture file naming, demo workspace state fixture file naming, demo export fixture file naming, demo red-team fixture file naming, fixture-to-folder mapping, fixture source contract mapping, fixture file safety labels, fixture README requirement, fixture fail-closed conditions, fixture audit stub requirements, and fixture validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.17.3 — Synthetic Fixture File Scaffold Plan.

v0.17.3 translates the sealed synthetic fixture registry and local folder namespace into a concrete synthetic fixture file scaffold plan for the local internal prototype.

This document does not implement a clinical product.

It does not create executable clinical functionality.

It does not create real patient case files.

It does not create deidentified real patient case files.

It does not create DICOM or HRCT files.

It does not create real clinical report files.

It does not create clinical validation datasets.

It does not create diagnostic ground truth.

It does not add PACS or EHR integration.

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
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define which local fixture files may exist under `prototype/fixtures/`, what they may contain, which source contracts they trace to, and which fixture files must remain blocked because they imply patient data, clinical validation, diagnostic ground truth, clinical action, readiness, or MDD replacement.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.17.3 fixture file principle is:

> “A fixture file may demonstrate governed behavior, but it must not become a patient case.”

The v0.17.3 registry principle is:

> “A synthetic fixture registry may organize fictional demo objects, but it must not become a validation dataset.”

---

## 2. Relationship to v0.17.0–v0.17.2

v0.17.3 inherits:

- v0.17.0 — Local Prototype File / Folder Scaffold Entry Gate,
- v0.17.1 — Prototype Folder Namespace / Blocked Folder Registry,
- v0.17.2 — Route File / Screen File Scaffold Plan.

v0.17.0 opened local file/folder scaffold planning.

v0.17.1 defined the allowed local folder namespace and blocked folder registry.

v0.17.2 defined safe route and screen file scaffold planning.

v0.17.3 defines synthetic fixture file scaffold planning under:

```text
prototype/fixtures/
```

v0.17.3 does not broaden v0.17.0–v0.17.2.

v0.17.3 must not open:

- real patient data,
- deidentified real patient data,
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

Inheritance rule:

> v0.17.3 may define fixture files only for sealed synthetic internal prototype demonstration.

---

## 3. Global Authority Envelope

Every fixture file, fixture registry file, fixture ID, fixture field, fixture filename, fixture metadata object, fixture folder mapping, fixture validation row, fixture README note, and fixture implementation note must preserve the following authority envelope.

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

No fixture file may imply an exception to this envelope.

Authority fixture file rule:

> A fixture file cannot grant clinical authority by resembling a case.

---

## 4. Global No-Decision Object

The no-decision object must remain attached to all decision-adjacent synthetic fixture files.

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

The no-decision object must be represented or referenced in:

- synthetic demo case fixture files,
- demo reasoning session fixture files,
- demo intake binding fixture files,
- demo workspace state fixture files,
- demo safe export fixture files,
- demo red-team scenario fixture files,
- demo authority envelope fixture files,
- demo no-decision object fixture files.

No-decision fixture rule:

> Fixture files may describe reasoning visibility, but they must preserve that no clinical decision was made.

---

## 5. Synthetic Fixture File Object Schema

Every allowed synthetic fixture file must conform to the following schema.

```yaml
synthetic_fixture_file_scaffold:
  fixture_file_id: string
  version: v0.17.3
  file_path: string
  fixture_id: string
  fixture_type: enum
  fixture_title: string
  parent_folder: "prototype/fixtures/"
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  internal_demo_only: true
  synthetic_demo_only: true
  fictional_case_context: conditional_required
  real_patient_data: false
  deidentified_real_patient_data: false
  dicom_data_present: false
  hrct_image_present: false
  real_report_present: false
  clinical_validation_use: false
  diagnostic_ground_truth_present: false
  final_diagnosis_present: false
  probability_field_present: false
  treatment_plan_present: false
  order_plan_present: false
  procedure_plan_present: false
  follow_up_plan_present: false
  triage_plan_present: false
  patient_facing_content_present: false
  public_ready: false
  product_ready: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
  allowed_bindings: list
  blocked_bindings: list
  fail_closed_conditions: list
```

Fixture file rule:

> A fixture file is allowed only if it remains fictional, synthetic, non-clinical, non-authoritative, non-validating, and non-patient-facing.

---

## 6. Fixture Registry File Schema

The synthetic fixture registry file must conform to the following schema.

```yaml
synthetic_fixture_registry_file:
  registry_file_id: SYN_FIX_REGISTRY_FILE_001
  version: v0.17.3
  file_path: "prototype/fixtures/synthetic_demo_case_registry.json"
  registry_scope: synthetic_internal_demo_only
  source_contract_version: string
  source_contract_file: string
  allowed_fixture_files: list
  blocked_fixture_files: list
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  real_report_import_allowed: false
  clinical_validation_use_allowed: false
  diagnostic_ground_truth_allowed: false
  final_diagnosis_allowed: false
  probability_field_allowed: false
  product_readiness_effect: none
  public_readiness_effect: none
  patient_facing_effect: none
  authority_effect: none
  decision_effect: none
  required_authority_envelope: true
  required_no_decision_object: true
  required_audit_stub: true
```

Fixture registry rule:

> The fixture registry organizes fictional demo fixtures; it is not a patient dataset or validation cohort.

---

## 7. Allowed Fixture File Types

The following fixture file types are allowed.

| Fixture File Type | Allowed Meaning |
|---|---|
| synthetic_demo_case_registry_file | registry of fictional demo cases |
| synthetic_demo_case_file | fictional governance scenario |
| demo_reasoning_session_fixture_file | synthetic reasoning session object |
| demo_intake_binding_fixture_file | synthetic intake-to-session binding |
| demo_workspace_state_fixture_file | synthetic workspace state fixture |
| demo_structured_output_fixture_file | structured output demonstration fixture |
| demo_case_snapshot_fixture_file | non-final synthetic case snapshot |
| demo_revision_history_fixture_file | synthetic revision/state movement record |
| demo_safe_export_fixture_file | safe export preview mechanics fixture |
| demo_MDD_preparation_package_fixture_file | MDD preparation preview fixture, not consensus |
| demo_unsafe_export_failure_fixture_file | unsafe export fail-closed fixture |
| demo_audit_event_fixture_file | audit traceability fixture |
| demo_authority_envelope_fixture_file | non-authority boundary fixture |
| demo_no_decision_object_fixture_file | explicit no-decision fixture |
| demo_visual_artifact_fixture_file | explanatory visual safety fixture |
| demo_red_team_scenario_fixture_file | red-team containment scenario fixture |
| demo_route_state_fixture_file | route state fixture |
| demo_screen_state_fixture_file | screen state fixture |
| demo_component_state_fixture_file | component state fixture |

Allowed fixture type rule:

> Allowed fixture files demonstrate governance, state, safety, traceability, and containment only.

---

## 8. Blocked Fixture File Types

The following fixture file types are blocked.

| Blocked Fixture File Type | Reason |
|---|---|
| patient_case_file | real patient data blocked |
| deidentified_patient_case_file | deidentified real patient data blocked |
| dicom_study_file | DICOM import blocked |
| hrct_series_file | HRCT image import blocked |
| radiology_report_file | real report import blocked |
| pathology_report_file | real report import blocked |
| microbiology_report_file | real report import blocked |
| clinical_note_file | real clinical text blocked |
| MDD_note_file | real MDD text blocked |
| pacs_record_file | PACS integration blocked |
| ehr_record_file | EHR integration blocked |
| clinical_validation_case_file | clinical validation not opened |
| diagnostic_ground_truth_case_file | diagnostic ground truth blocked |
| performance_benchmark_case_file | diagnostic performance claim blocked |
| patient_facing_case_file | patient-facing use blocked |
| final_diagnosis_fixture_file | diagnostic authority blocked |
| treatment_plan_fixture_file | treatment authority blocked |
| test_order_fixture_file | test-order authority blocked |
| procedure_plan_fixture_file | procedure authority blocked |
| follow_up_plan_fixture_file | follow-up authority blocked |
| triage_fixture_file | triage authority blocked |
| mdd_consensus_fixture_file | MDD replacement blocked |

Blocked fixture file rule:

> Blocked fixture files cannot exist as examples, placeholders, hidden files, future fixtures, or disabled clinical fixtures.

---

## 9. Allowed Fixture File Registry

The following fixture files are allowed.

| Fixture File ID | File Path | Fixture Type |
|---|---|---|
| FIX_FILE_001 | `prototype/fixtures/synthetic_demo_case_registry.json` | synthetic_demo_case_registry_file |
| FIX_FILE_002 | `prototype/fixtures/synthetic_demo_case_001.json` | synthetic_demo_case_file |
| FIX_FILE_003 | `prototype/fixtures/synthetic_demo_case_002.json` | synthetic_demo_case_file |
| FIX_FILE_004 | `prototype/fixtures/synthetic_demo_case_003.json` | synthetic_demo_case_file |
| FIX_FILE_005 | `prototype/fixtures/demo_reasoning_session_fixture_001.json` | demo_reasoning_session_fixture_file |
| FIX_FILE_006 | `prototype/fixtures/demo_intake_binding_fixture_001.json` | demo_intake_binding_fixture_file |
| FIX_FILE_007 | `prototype/fixtures/demo_workspace_state_fixture_001.json` | demo_workspace_state_fixture_file |
| FIX_FILE_008 | `prototype/fixtures/demo_structured_output_fixture_001.json` | demo_structured_output_fixture_file |
| FIX_FILE_009 | `prototype/fixtures/demo_case_snapshot_fixture_001.json` | demo_case_snapshot_fixture_file |
| FIX_FILE_010 | `prototype/fixtures/demo_revision_history_fixture_001.json` | demo_revision_history_fixture_file |
| FIX_FILE_011 | `prototype/fixtures/demo_safe_export_fixture_001.json` | demo_safe_export_fixture_file |
| FIX_FILE_012 | `prototype/fixtures/demo_mdd_preparation_package_fixture_001.json` | demo_MDD_preparation_package_fixture_file |
| FIX_FILE_013 | `prototype/fixtures/demo_unsafe_export_failure_fixture_001.json` | demo_unsafe_export_failure_fixture_file |
| FIX_FILE_014 | `prototype/fixtures/demo_audit_event_fixture_001.json` | demo_audit_event_fixture_file |
| FIX_FILE_015 | `prototype/fixtures/demo_authority_envelope_fixture_001.json` | demo_authority_envelope_fixture_file |
| FIX_FILE_016 | `prototype/fixtures/demo_no_decision_object_fixture_001.json` | demo_no_decision_object_fixture_file |
| FIX_FILE_017 | `prototype/fixtures/demo_visual_artifact_fixture_001.json` | demo_visual_artifact_fixture_file |
| FIX_FILE_018 | `prototype/fixtures/demo_red_team_scenario_fixture_001.json` | demo_red_team_scenario_fixture_file |
| FIX_FILE_019 | `prototype/fixtures/demo_route_state_fixture_001.json` | demo_route_state_fixture_file |
| FIX_FILE_020 | `prototype/fixtures/demo_screen_state_fixture_001.json` | demo_screen_state_fixture_file |
| FIX_FILE_021 | `prototype/fixtures/demo_component_state_fixture_001.json` | demo_component_state_fixture_file |

Allowed fixture registry rule:

> Allowed fixture files must remain under `prototype/fixtures/` and must contain synthetic demo objects only.

---

## 10. Blocked Fixture File Registry

The following fixture files are blocked.

```text
prototype/fixtures/patient_case_001.json
prototype/fixtures/real_patient_case_001.json
prototype/fixtures/deidentified_patient_case_001.json
prototype/fixtures/deidentified_case_001.json
prototype/fixtures/clinical_case_001.json
prototype/fixtures/dicom_study_001.json
prototype/fixtures/hrct_series_001.json
prototype/fixtures/hrct_image_001.json
prototype/fixtures/radiology_report_001.json
prototype/fixtures/pathology_report_001.json
prototype/fixtures/microbiology_report_001.json
prototype/fixtures/clinical_note_001.json
prototype/fixtures/mdd_note_001.json
prototype/fixtures/pacs_record_001.json
prototype/fixtures/ehr_record_001.json
prototype/fixtures/fhir_record_001.json
prototype/fixtures/final_diagnosis_case_001.json
prototype/fixtures/diagnostic_ground_truth_case_001.json
prototype/fixtures/ipf_confirmed_case_001.json
prototype/fixtures/ipf_probability_case_001.json
prototype/fixtures/rule_out_case_001.json
prototype/fixtures/treatment_plan_case_001.json
prototype/fixtures/test_order_case_001.json
prototype/fixtures/procedure_plan_case_001.json
prototype/fixtures/follow_up_plan_case_001.json
prototype/fixtures/triage_case_001.json
prototype/fixtures/patient_summary_case_001.json
prototype/fixtures/clinical_validation_case_001.json
prototype/fixtures/performance_benchmark_case_001.json
prototype/fixtures/accuracy_benchmark_case_001.json
prototype/fixtures/product_ready_fixture_001.json
prototype/fixtures/public_ready_fixture_001.json
prototype/fixtures/mdd_consensus_case_001.json
```

Blocked fixture registry rule:

> Blocked fixture files may not be created because their names imply clinical data, clinical validation, clinical action, readiness, or MDD replacement.

---

## 11. Fixture File Naming Convention

Allowed fixture file naming patterns:

```yaml
allowed_fixture_file_naming:
  synthetic_demo_case_registry: "synthetic_demo_case_registry.json"
  synthetic_demo_case: "synthetic_demo_case_[number].json"
  demo_reasoning_session: "demo_reasoning_session_fixture_[number].json"
  demo_intake_binding: "demo_intake_binding_fixture_[number].json"
  demo_workspace_state: "demo_workspace_state_fixture_[number].json"
  demo_structured_output: "demo_structured_output_fixture_[number].json"
  demo_case_snapshot: "demo_case_snapshot_fixture_[number].json"
  demo_revision_history: "demo_revision_history_fixture_[number].json"
  demo_safe_export: "demo_safe_export_fixture_[number].json"
  demo_mdd_preparation_package: "demo_mdd_preparation_package_fixture_[number].json"
  demo_unsafe_export_failure: "demo_unsafe_export_failure_fixture_[number].json"
  demo_audit_event: "demo_audit_event_fixture_[number].json"
  demo_authority_envelope: "demo_authority_envelope_fixture_[number].json"
  demo_no_decision_object: "demo_no_decision_object_fixture_[number].json"
  demo_visual_artifact: "demo_visual_artifact_fixture_[number].json"
  demo_red_team_scenario: "demo_red_team_scenario_fixture_[number].json"
  demo_route_state: "demo_route_state_fixture_[number].json"
  demo_screen_state: "demo_screen_state_fixture_[number].json"
  demo_component_state: "demo_component_state_fixture_[number].json"
```

Blocked fixture file naming terms:

- patient,
- real_patient,
- deidentified,
- clinical_case,
- dicom,
- hrct,
- image,
- pacs,
- ehr,
- fhir,
- report,
- radiology_report,
- pathology_report,
- microbiology_report,
- clinical_note,
- diagnosis,
- final_diagnosis,
- confirmed,
- probability,
- ranking,
- rule_out,
- treatment,
- order,
- procedure,
- follow_up,
- triage,
- patient_summary,
- clinical_validation,
- performance,
- benchmark,
- accuracy,
- product_ready,
- public_ready,
- mdd_consensus.

Fixture naming rule:

> Fixture file names must signal synthetic governance identity, not patient or clinical identity.

---

## 12. Fixture-to-Folder Mapping

All allowed fixture files must live only in:

```text
prototype/fixtures/
```

Allowed mapping:

| Fixture File Category | Folder |
|---|---|
| synthetic demo case registry | `prototype/fixtures/` |
| synthetic demo cases | `prototype/fixtures/` |
| demo reasoning session fixtures | `prototype/fixtures/` |
| demo intake binding fixtures | `prototype/fixtures/` |
| demo workspace state fixtures | `prototype/fixtures/` |
| demo export fixtures | `prototype/fixtures/` |
| demo audit fixtures | `prototype/fixtures/` |
| demo red-team fixtures | `prototype/fixtures/` |

Blocked mapping:

- fixture files under patient folders,
- fixture files under clinical folders,
- fixture files under DICOM/report/PACS/EHR folders,
- fixture files under diagnosis/action folders,
- fixture files under validation/performance folders,
- fixture files outside `prototype/fixtures/` without source mapping.

Fixture-to-folder rule:

> Synthetic fixture files may exist only inside the safe local fixture namespace.

---

## 13. Fixture Source Contract Mapping

Every allowed fixture file must map to source contracts.

| Fixture File Group | Source Contracts |
|---|---|
| synthetic demo case registry | v0.14; v0.16.2; v0.17.0 |
| synthetic demo case files | v0.14; v0.15.2; v0.16.2 |
| demo reasoning session fixture files | v0.12; v0.16.2 |
| demo intake binding fixture files | v0.11; v0.15.2; v0.16.2 |
| demo workspace state fixture files | v0.15.1; v0.16.2 |
| demo structured output fixture files | v0.9; v0.16.2 |
| demo case snapshot fixture files | v0.12; v0.13; v0.16.2 |
| demo revision history fixture files | v0.12; v0.16.5 |
| demo safe export fixture files | v0.13; v0.15.4; v0.16.6 |
| demo MDD preparation package fixture files | v0.13; v0.16.6 |
| demo unsafe export failure fixture files | v0.15.4; v0.16.4; v0.16.6 |
| demo audit event fixture files | v0.16.5 |
| demo authority envelope fixture files | v0.15.5; v0.16.8 |
| demo no-decision object fixture files | v0.15.5; v0.16.8 |
| demo visual artifact fixture files | v0.14; v0.15.3; v0.16.3 |
| demo red-team scenario fixture files | v0.14; v0.15.4; v0.16.6 |
| demo route/screen/component state fixture files | v0.16.1; v0.16.2; v0.17.2 |

Source mapping rule:

> Fixture files without sealed source contract mapping are blocked.

---

## 14. Fixture File Safety Labels

Every fixture file must include or reference safety labels.

```yaml
required_fixture_file_safety_labels:
  internal_demo_only: true
  synthetic_demo_only: true
  fictional_context_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  real_patient_data: false
  deidentified_real_patient_data: false
  dicom_data_present: false
  hrct_image_present: false
  real_report_present: false
  clinical_validation_use: false
  diagnostic_ground_truth_present: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  mdd_replacement: not_allowed
```

Fixture safety label rule:

> A fixture file cannot be considered safe if its synthetic and non-clinical labels are missing.

---

## 15. Fixture README Requirement

The fixture folder should include:

```text
prototype/fixtures/README.md
```

Required fixture README statements:

```text
This folder contains synthetic demo fixture files only.
Fixture files are fictional governance objects.
Fixture files are not patient cases.
Fixture files are not deidentified patient cases.
Fixture files are not DICOM or HRCT data.
Fixture files are not real clinical reports.
Fixture files are not clinical validation cases.
Fixture files are not diagnostic ground truth.
Fixture files do not diagnose, treat, order, decide procedures, schedule follow-up, triage, or generate MDD consensus.
Fixture files are not patient-facing.
Fixture files are not product ready.
Fixture files are not public ready.
```

Fixture README rule:

> Fixture folder boundary text must prevent fixtures from being read as clinical data.

---

## 16. Synthetic Demo Case Fixture Boundary

Synthetic demo case fixture files may include:

- synthetic case ID,
- synthetic case title,
- fictional context summary,
- governance behavior demonstrated,
- supplied fictional fields,
- missing fictional fields,
- source status prompts,
- mimic visibility prompts,
- overlap prompts,
- confidence limiter prompts,
- review visibility prompts,
- linked fixture IDs,
- safety labels,
- authority envelope,
- no-decision object,
- audit seed events.

Synthetic demo case fixture files may not include:

- patient name,
- date of birth,
- MRN,
- accession number,
- institution case ID,
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

Synthetic demo case rule:

> A synthetic demo case may demonstrate a reasoning-governance problem, not a clinical truth.

---

## 17. Demo Reasoning Session Fixture Boundary

Demo reasoning session fixture files may include:

- synthetic session ID,
- parent synthetic case ID,
- fictional intake context,
- source status states,
- missing evidence states,
- mimic visibility states,
- overlap states,
- confidence limiter states,
- review prompt states,
- audit event references,
- authority envelope,
- no-decision object.

Demo reasoning session fixture files may not include:

- final diagnosis,
- disease ranking,
- probability score,
- exclusion state,
- treatment decision,
- order decision,
- procedure decision,
- follow-up decision,
- triage decision,
- patient-facing summary,
- clinical validation result,
- diagnostic performance result.

Reasoning session fixture rule:

> A demo reasoning session fixture may organize visibility, not decide diagnosis or action.

---

## 18. Demo Export Fixture Boundary

Demo export fixture files may include:

- safe export preview section IDs,
- synthetic demo boundary,
- non-clinical use boundary,
- authority envelope,
- no-decision object,
- source status summary,
- missing evidence summary,
- mimic visibility summary,
- overlap visibility summary,
- confidence limiter summary,
- review prompt visibility,
- audit trace references,
- export safety state.

Demo export fixture files may not include:

- impression,
- diagnosis,
- final diagnosis,
- diagnostic conclusion,
- treatment plan,
- order plan,
- procedure recommendation,
- follow-up schedule,
- triage/disposition,
- patient summary,
- MDD consensus,
- clinical validation result,
- product-ready result,
- public-ready result.

Export fixture rule:

> A demo export fixture may scaffold safe preview structure, not clinical report output.

---

## 19. Demo Red-Team Fixture Boundary

Demo red-team fixture files may include:

- unsafe attempt type,
- quarantined unsafe example placeholder,
- blocked badge state,
- failure reason,
- blocked authority,
- copy allowed false,
- export allowed false,
- repair required,
- UI safety revalidation required,
- audit event reference.

Demo red-team fixture files may not include:

- reusable unsafe clinical phrase,
- suggested clinical replacement phrase,
- “use this instead” output,
- copyable red-team output,
- exportable red-team output,
- clinical validation pass,
- product readiness pass,
- public readiness pass,
- diagnostic performance pass.

Red-team fixture rule:

> A red-team fixture demonstrates containment, not reusable output.

---

## 20. Fixture File Fail-Closed Conditions

Fixture file planning must fail closed under the following conditions.

```yaml
fixture_file_fail_closed_conditions:
  fixture_file_name_matches_blocked_registry:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_file_name_matches_blocked_pattern:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_file_has_no_source_contract:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_file_missing_safety_labels:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_real_patient_marker:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_deidentified_patient_marker:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_dicom_or_hrct_marker:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_real_report_marker:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_final_diagnosis:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_probability_or_ranking:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_contains_treatment_order_procedure_followup_triage:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_claims_clinical_validation_or_performance:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_claims_product_or_public_readiness:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  fixture_generates_mdd_consensus:
    result: reject_file
    repair_required: true
    audit_stub_required: true
```

Fixture fail-closed rule:

> Unsafe fixture files must be rejected before they become local scaffold artifacts.

---

## 21. Fixture File Repair Rules

Repair is allowed only as scaffold safety repair.

Allowed repair actions:

- rename unsafe fixture file,
- remove blocked fixture file,
- remove real patient-like fields,
- remove deidentified patient-like fields,
- remove DICOM/HRCT/report markers,
- remove diagnostic ground truth,
- remove final diagnosis fields,
- remove probability/ranking fields,
- remove treatment/order/procedure/follow-up/triage fields,
- remove clinical validation/performance claims,
- restore synthetic fixture label,
- restore source contract mapping,
- restore authority envelope,
- restore no-decision object,
- restore audit stub reference,
- update fixture validation checklist.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- patient data deidentification correction,
- DICOM parsing correction,
- clinical validation correction,
- diagnostic performance correction,
- product readiness correction,
- public readiness correction.

Fixture repair rule:

> Fixture repair fixes scaffold safety and naming, not clinical content.

---

## 22. Fixture Audit Stub Requirement

Fixture file planning should be audit-stub traceable in future implementation.

Allowed fixture audit events:

- fixture_file_registered,
- fixture_file_rejected,
- fixture_source_mapping_verified,
- fixture_safety_label_verified,
- synthetic_fixture_loaded,
- synthetic_fixture_bound,
- blocked_fixture_file_detected,
- unsafe_fixture_content_detected,
- fixture_repair_required,
- fixture_repair_applied,
- fixture_validation_passed,
- fixture_validation_failed.

Audit fields:

```yaml
fixture_file_audit_stub:
  event_id: string
  event_type: string
  file_path: string
  fixture_id: optional
  fixture_type: optional
  source_contract: string
  event_result: enum(registered, rejected, verified, loaded, bound, repair_required, repaired, failed)
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Fixture audit rule:

> Fixture audit records synthetic scaffold traceability, not clinical validity.

---

## 23. Fixture Validation Checklist

v0.17.3 fixture validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| FIXTURE_FILE_CHECK_001 | fixture file object schema defined | true |
| FIXTURE_FILE_CHECK_002 | fixture registry file schema defined | true |
| FIXTURE_FILE_CHECK_003 | allowed fixture file types defined | true |
| FIXTURE_FILE_CHECK_004 | blocked fixture file types defined | true |
| FIXTURE_FILE_CHECK_005 | allowed fixture file registry defined | true |
| FIXTURE_FILE_CHECK_006 | blocked fixture file registry defined | true |
| FIXTURE_FILE_CHECK_007 | fixture file naming convention defined | true |
| FIXTURE_FILE_CHECK_008 | fixture-to-folder mapping defined | true |
| FIXTURE_FILE_CHECK_009 | fixture source contract mapping defined | true |
| FIXTURE_FILE_CHECK_010 | fixture file safety labels defined | true |
| FIXTURE_FILE_CHECK_011 | fixture README requirement defined | true |
| FIXTURE_FILE_CHECK_012 | synthetic demo case fixture boundary defined | true |
| FIXTURE_FILE_CHECK_013 | demo reasoning session fixture boundary defined | true |
| FIXTURE_FILE_CHECK_014 | demo export fixture boundary defined | true |
| FIXTURE_FILE_CHECK_015 | demo red-team fixture boundary defined | true |
| FIXTURE_FILE_CHECK_016 | fixture fail-closed conditions defined | true |
| FIXTURE_FILE_CHECK_017 | fixture repair rules defined | true |
| FIXTURE_FILE_CHECK_018 | fixture audit stub requirement defined | true |
| FIXTURE_FILE_CHECK_019 | no patient fixture files allowed | true |
| FIXTURE_FILE_CHECK_020 | no deidentified patient fixture files allowed | true |
| FIXTURE_FILE_CHECK_021 | no DICOM/HRCT/report/PACS/EHR fixture files allowed | true |
| FIXTURE_FILE_CHECK_022 | no final diagnosis/ground truth fixture files allowed | true |
| FIXTURE_FILE_CHECK_023 | no probability/ranking fixture files allowed | true |
| FIXTURE_FILE_CHECK_024 | no treatment/order/procedure/follow-up/triage fixture files allowed | true |
| FIXTURE_FILE_CHECK_025 | no patient-facing fixture files allowed | true |
| FIXTURE_FILE_CHECK_026 | no clinical validation/performance fixture files allowed | true |
| FIXTURE_FILE_CHECK_027 | no product/public readiness fixture files allowed | true |
| FIXTURE_FILE_CHECK_028 | no MDD consensus fixture files allowed | true |

Fixture validation rule:

> Fixture validation passes only if every fixture file remains synthetic, internal, source-governed, non-clinical, non-authoritative, non-validating, non-ready, and fail-closed.

---

## 24. v0.17.3 Acceptance Criteria

v0.17.3 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| allowed synthetic fixture file registry defined | true |
| blocked fixture file registry defined | true |
| synthetic case fixture file naming defined | true |
| demo reasoning session fixture file naming defined | true |
| demo intake binding fixture file naming defined | true |
| demo workspace state fixture file naming defined | true |
| demo export fixture file naming defined | true |
| demo red-team fixture file naming defined | true |
| fixture-to-folder mapping defined | true |
| fixture source contract mapping defined | true |
| fixture file safety labels defined | true |
| fixture README requirement defined | true |
| fixture fail-closed conditions defined | true |
| fixture repair rules defined | true |
| fixture audit stub requirement defined | true |
| fixture validation checklist defined | true |
| no real patient fixture file opened | true |
| no deidentified patient fixture file opened | true |
| no DICOM/HRCT/report/PACS/EHR fixture file opened | true |
| no final diagnosis/ground truth fixture file opened | true |
| no probability/ranking fixture file opened | true |
| no treatment/order/procedure/follow-up/triage fixture file opened | true |
| no patient-facing fixture file opened | true |
| no clinical validation/performance fixture file opened | true |
| no product/public readiness fixture file opened | true |
| no MDD consensus fixture file opened | true |
| public_ready remains false | true |
| product_ready remains false | true |
| clinical_validation remains not_opened | true |
| diagnostic_authority remains none | true |
| treatment_authority remains none | true |

v0.17.3 acceptance rule:

> The synthetic fixture file scaffold plan is accepted only if local fixture files cannot be mistaken for patient cases, validation datasets, diagnostic ground truth, clinical actions, product readiness, public readiness, or MDD consensus.

---

## 25. Next Step

The next recommended step is:

- v0.17.4 — UI Copy Registry File Scaffold Plan

v0.17.4 should define:

- allowed UI copy registry file registry,
- blocked UI copy file registry,
- safety language file naming,
- route copy mapping file naming,
- screen copy mapping file naming,
- component copy mapping file naming,
- blocked phrase registry file naming,
- disabled control copy file naming,
- fail-closed copy file naming,
- export/red-team copy file naming,
- copy-to-folder mapping,
- copy source contract mapping,
- copy file safety labels,
- copy README requirement,
- copy file fail-closed conditions,
- copy validation checklist.

v0.17.4 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 26. Governance Statement

This document defines the synthetic fixture file scaffold plan.

It opens synthetic fixture file scaffold planning only.

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

The v0.17.3 governance discipline is:

> “Do not let fixture files become patient cases or validation datasets.”

The fixture scaffold discipline is:

> “Synthetic fixtures may demonstrate reasoning-governance need, but they must not claim clinical truth.”