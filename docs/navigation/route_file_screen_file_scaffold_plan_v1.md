# ILD Reasoning Platform — Route File / Screen File Scaffold Plan v1

Version: v0.17.2  
Status: route_file_screen_file_scaffold_plan  
Scope: Allowed route file registry, blocked route file registry, allowed screen file registry, blocked screen file registry, route file naming convention, screen file naming convention, route-to-folder mapping, screen-to-folder mapping, route/screen source contract mapping, route/screen README requirements, route/screen safety labels, route/screen fail-closed conditions, and route/screen file validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.17.2 — Route File / Screen File Scaffold Plan.

v0.17.2 translates the sealed route/screen registry and local folder namespace into a concrete route file and screen file scaffold plan for the local internal prototype.

This document does not implement a clinical product.

It does not create executable clinical routing.

It does not create executable clinical UI.

It does not add real patient data.

It does not add deidentified real patient data.

It does not add DICOM or HRCT import.

It does not add real clinical report import.

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

Its purpose is to define which local route and screen scaffold files may exist, what they may represent, which source contracts they trace to, and which route/screen files must remain blocked because they imply clinical capability.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.17.2 route file principle is:

> “A route file may organize internal synthetic prototype navigation, but it must not create clinical workflow.”

The v0.17.2 screen file principle is:

> “A screen file may organize safe prototype visibility, but it must not create clinical interpretation, action, validation, readiness, or patient-facing output.”

---

## 2. Relationship to v0.17.0 and v0.17.1

v0.17.2 inherits:

- v0.17.0 — Local Prototype File / Folder Scaffold Entry Gate,
- v0.17.1 — Prototype Folder Namespace / Blocked Folder Registry.

v0.17.0 opened local file/folder scaffold planning.

v0.17.1 defined the allowed local folder namespace and blocked folder registry.

v0.17.2 defines allowed and blocked route/screen files under:

```text
prototype/routes/
prototype/screens/
```

v0.17.2 does not broaden v0.17.0 or v0.17.1.

v0.17.2 must not open:

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

> v0.17.2 may define local route/screen scaffold files only for safe internal synthetic prototype navigation and visibility.

---

## 3. Global Authority Envelope

Every route file, screen file, route path, screen name, route label, screen label, route README, screen README, route metadata, screen metadata, navigation edge, screen component reference, validation row, and implementation note must preserve the following authority envelope.

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

No route file or screen file may imply an exception to this envelope.

Authority route/screen rule:

> A route or screen file cannot grant clinical authority by existing in the local scaffold.

---

## 4. Global No-Decision Object

The no-decision object remains active across all decision-adjacent route and screen files.

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

The no-decision object must be referenced by:

- reasoning map route file,
- reasoning map screen file,
- evidence panel route file,
- evidence panel screen files,
- safe export preview route file,
- safe export preview screen file,
- red-team route file,
- red-team screen file,
- audit trace route file,
- audit trace screen file,
- safety reference route file,
- safety reference screen file.

No-decision route/screen rule:

> Decision-adjacent route and screen files must preserve what the platform does not decide.

---

## 5. Route File Object Schema

Every allowed route file must conform to the following schema.

```yaml
route_file_scaffold:
  route_file_id: string
  version: v0.17.2
  file_path: string
  route_id: string
  route_path: string
  route_name: string
  route_category: enum
  parent_folder: "prototype/routes/"
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  real_report_import_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
  allowed_screen_bindings: list
  blocked_screen_bindings: list
  allowed_next_routes: list
  blocked_next_routes: list
  fail_closed_conditions: list
```

Route file rule:

> A route file is allowed only if it maps to an allowed `/prototype` route and cannot navigate into clinical capability.

---

## 6. Screen File Object Schema

Every allowed screen file must conform to the following schema.

```yaml
screen_file_scaffold:
  screen_file_id: string
  version: v0.17.2
  file_path: string
  screen_id: string
  screen_name: string
  screen_category: enum
  parent_folder: "prototype/screens/"
  assigned_route_id: string
  assigned_route_path: string
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
  allowed_component_refs: list
  blocked_component_refs: list
  fail_closed_conditions: list
```

Screen file rule:

> A screen file is allowed only if it maps to an allowed route and safe screen contract.

---

## 7. Route File Naming Convention

Allowed route file naming convention:

```text
prototype/routes/[safe_route_name]_route.md
```

Allowed route file name terms:

- prototype_boundary,
- synthetic_case_selector,
- synthetic_intake_review,
- reasoning_map,
- evidence_panel,
- missing_evidence_panel,
- mimic_visibility_panel,
- overlap_panel,
- source_status_panel,
- confidence_limiter_panel,
- review_prompt_panel,
- safe_export_preview,
- red_team,
- red_team_scenario,
- audit_trace,
- safety_reference.

Blocked route file name terms:

- patient,
- clinical_case,
- dicom_import,
- hrct_upload,
- pacs_connect,
- ehr_connect,
- report_import,
- diagnosis,
- final_diagnosis,
- likely_diagnosis,
- probability,
- ranking,
- rule_out,
- treatment,
- orders,
- procedures,
- follow_up,
- triage,
- disposition,
- patient_summary,
- clinical_validation,
- diagnostic_performance,
- product_ready,
- public,
- mdd_consensus.

Route naming rule:

> Route file names must describe safe prototype navigation, not clinical function.

---

## 8. Screen File Naming Convention

Allowed screen file naming convention:

```text
prototype/screens/[safe_screen_name]_screen.md
```

Allowed screen file name terms:

- prototype_boundary,
- synthetic_case_selector,
- demo_intake_review,
- reasoning_map,
- missing_evidence_panel,
- mimic_visibility_panel,
- overlap_panel,
- source_status_panel,
- confidence_limiter_panel,
- review_prompt_panel,
- safe_export_preview,
- red_team_fail_closed,
- red_team_scenario_detail,
- audit_trace,
- authority_envelope,
- no_decision_object,
- visual_safety_label,
- safety_reference.

Blocked screen file name terms:

- patient,
- clinical,
- diagnosis,
- final_diagnosis,
- most_likely_diagnosis,
- probability_dashboard,
- rule_out,
- confirmed,
- excluded,
- treatment_recommendation,
- order_form,
- procedure_recommendation,
- follow_up_scheduler,
- triage,
- disposition,
- patient_summary,
- clinical_validation,
- diagnostic_accuracy,
- product_ready,
- public_ready,
- mdd_consensus.

Screen naming rule:

> Screen file names must describe governed visibility, not clinical conclusion or action.

---

## 9. Allowed Route File Registry

The following route files are allowed.

| Route File ID | File Path | Route Path | Route Name |
|---|---|---|---|
| ROUTE_FILE_001 | `prototype/routes/prototype_boundary_route.md` | `/prototype` | Prototype Boundary Route |
| ROUTE_FILE_002 | `prototype/routes/synthetic_case_selector_route.md` | `/prototype/cases` | Synthetic Case Selector Route |
| ROUTE_FILE_003 | `prototype/routes/synthetic_intake_review_route.md` | `/prototype/cases/:synthetic_case_id/intake` | Synthetic Intake Review Route |
| ROUTE_FILE_004 | `prototype/routes/reasoning_map_route.md` | `/prototype/cases/:synthetic_case_id/map` | Reasoning Map Route |
| ROUTE_FILE_005 | `prototype/routes/evidence_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence` | Evidence Panel Hub Route |
| ROUTE_FILE_006 | `prototype/routes/missing_evidence_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence/missing` | Missing Evidence Panel Route |
| ROUTE_FILE_007 | `prototype/routes/mimic_visibility_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence/mimics` | Mimic Visibility Panel Route |
| ROUTE_FILE_008 | `prototype/routes/overlap_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence/overlap` | Overlap Panel Route |
| ROUTE_FILE_009 | `prototype/routes/source_status_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence/source-status` | Source Status Panel Route |
| ROUTE_FILE_010 | `prototype/routes/confidence_limiter_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence/confidence-limiter` | Confidence Limiter Panel Route |
| ROUTE_FILE_011 | `prototype/routes/review_prompt_panel_route.md` | `/prototype/cases/:synthetic_case_id/evidence/review-prompts` | Review Prompt Panel Route |
| ROUTE_FILE_012 | `prototype/routes/safe_export_preview_route.md` | `/prototype/cases/:synthetic_case_id/export-preview` | Safe Export Preview Route |
| ROUTE_FILE_013 | `prototype/routes/red_team_route.md` | `/prototype/red-team` | Red-Team Hub Route |
| ROUTE_FILE_014 | `prototype/routes/red_team_scenario_route.md` | `/prototype/red-team/:scenario_id` | Red-Team Scenario Route |
| ROUTE_FILE_015 | `prototype/routes/audit_trace_route.md` | `/prototype/cases/:synthetic_case_id/audit` | Audit Trace Route |
| ROUTE_FILE_016 | `prototype/routes/safety_reference_route.md` | `/prototype/safety` | Safety Reference Route |

Allowed route registry rule:

> Allowed route files must remain under `prototype/routes/` and must map only to v0.16.1 allowed route paths.

---

## 10. Blocked Route File Registry

The following route files are blocked.

```text
prototype/routes/patient_route.md
prototype/routes/patients_route.md
prototype/routes/clinical_case_route.md
prototype/routes/clinical_cases_route.md
prototype/routes/real_case_upload_route.md
prototype/routes/deidentified_case_upload_route.md
prototype/routes/dicom_import_route.md
prototype/routes/hrct_upload_route.md
prototype/routes/image_viewer_route.md
prototype/routes/pacs_connect_route.md
prototype/routes/ehr_connect_route.md
prototype/routes/report_import_route.md
prototype/routes/report_paste_route.md
prototype/routes/diagnosis_route.md
prototype/routes/final_diagnosis_route.md
prototype/routes/diagnosis_ranking_route.md
prototype/routes/probability_route.md
prototype/routes/rule_out_route.md
prototype/routes/mimic_exclusion_route.md
prototype/routes/treatment_route.md
prototype/routes/orders_route.md
prototype/routes/procedures_route.md
prototype/routes/follow_up_route.md
prototype/routes/triage_route.md
prototype/routes/disposition_route.md
prototype/routes/patient_summary_route.md
prototype/routes/clinical_validation_route.md
prototype/routes/diagnostic_performance_route.md
prototype/routes/product_ready_route.md
prototype/routes/public_route.md
prototype/routes/mdd_consensus_route.md
```

Blocked route file rule:

> Blocked route files may not exist as enabled files, hidden files, empty placeholders, comments, future toggles, or scaffold examples.

---

## 11. Allowed Screen File Registry

The following screen files are allowed.

| Screen File ID | File Path | Screen Name | Assigned Route |
|---|---|---|---|
| SCREEN_FILE_001 | `prototype/screens/prototype_boundary_screen.md` | Prototype Boundary Screen | `/prototype` |
| SCREEN_FILE_002 | `prototype/screens/synthetic_case_selector_screen.md` | Synthetic Case Selector Screen | `/prototype/cases` |
| SCREEN_FILE_003 | `prototype/screens/demo_intake_review_screen.md` | Demo Intake Review Screen | `/prototype/cases/:synthetic_case_id/intake` |
| SCREEN_FILE_004 | `prototype/screens/reasoning_map_screen.md` | Reasoning Map Screen | `/prototype/cases/:synthetic_case_id/map` |
| SCREEN_FILE_005 | `prototype/screens/evidence_panel_hub_screen.md` | Evidence Panel Hub Screen | `/prototype/cases/:synthetic_case_id/evidence` |
| SCREEN_FILE_006 | `prototype/screens/missing_evidence_panel_screen.md` | Missing Evidence Panel Screen | evidence missing route |
| SCREEN_FILE_007 | `prototype/screens/mimic_visibility_panel_screen.md` | Mimic Visibility Panel Screen | evidence mimics route |
| SCREEN_FILE_008 | `prototype/screens/overlap_panel_screen.md` | Overlap Panel Screen | evidence overlap route |
| SCREEN_FILE_009 | `prototype/screens/source_status_panel_screen.md` | Source Status Panel Screen | evidence source-status route |
| SCREEN_FILE_010 | `prototype/screens/confidence_limiter_panel_screen.md` | Confidence Limiter Panel Screen | evidence confidence-limiter route |
| SCREEN_FILE_011 | `prototype/screens/review_prompt_panel_screen.md` | Review Prompt Panel Screen | evidence review-prompts route |
| SCREEN_FILE_012 | `prototype/screens/safe_export_preview_screen.md` | Safe Export Preview Screen | export-preview route |
| SCREEN_FILE_013 | `prototype/screens/red_team_fail_closed_screen.md` | Red-Team Fail-Closed Screen | `/prototype/red-team` |
| SCREEN_FILE_014 | `prototype/screens/red_team_scenario_detail_screen.md` | Red-Team Scenario Detail Screen | `/prototype/red-team/:scenario_id` |
| SCREEN_FILE_015 | `prototype/screens/audit_trace_screen.md` | Audit Trace Screen | audit route |
| SCREEN_FILE_016 | `prototype/screens/safety_reference_screen.md` | Safety Reference Screen | `/prototype/safety` |
| SCREEN_FILE_017 | `prototype/screens/authority_envelope_screen.md` | Authority Envelope Display Screen | embedded/safety |
| SCREEN_FILE_018 | `prototype/screens/no_decision_object_screen.md` | No-Decision Object Display Screen | embedded/safety |
| SCREEN_FILE_019 | `prototype/screens/visual_safety_label_screen.md` | Visual Safety Label Display Screen | embedded/safety |

Allowed screen registry rule:

> Allowed screen files display governed visibility only and must not create clinical interpretation or action.

---

## 12. Blocked Screen File Registry

The following screen files are blocked.

```text
prototype/screens/patient_screen.md
prototype/screens/clinical_case_screen.md
prototype/screens/real_patient_upload_screen.md
prototype/screens/deidentified_patient_upload_screen.md
prototype/screens/dicom_import_screen.md
prototype/screens/hrct_viewer_screen.md
prototype/screens/pacs_connection_screen.md
prototype/screens/ehr_connection_screen.md
prototype/screens/report_import_screen.md
prototype/screens/report_paste_screen.md
prototype/screens/diagnosis_screen.md
prototype/screens/final_diagnosis_screen.md
prototype/screens/most_likely_diagnosis_screen.md
prototype/screens/diagnosis_probability_screen.md
prototype/screens/diagnosis_ranking_screen.md
prototype/screens/rule_out_screen.md
prototype/screens/mimic_exclusion_screen.md
prototype/screens/treatment_recommendation_screen.md
prototype/screens/order_form_screen.md
prototype/screens/procedure_recommendation_screen.md
prototype/screens/follow_up_scheduler_screen.md
prototype/screens/triage_screen.md
prototype/screens/disposition_screen.md
prototype/screens/patient_summary_screen.md
prototype/screens/clinical_validation_screen.md
prototype/screens/diagnostic_performance_screen.md
prototype/screens/accuracy_dashboard_screen.md
prototype/screens/product_ready_screen.md
prototype/screens/public_ready_screen.md
prototype/screens/mdd_consensus_screen.md
```

Blocked screen file rule:

> Blocked screen files may not exist because they make the scaffold look like clinical software.

---

## 13. Route-to-Folder Mapping

All route files must live only in:

```text
prototype/routes/
```

Allowed mapping:

| Route File Category | Folder |
|---|---|
| prototype boundary route | `prototype/routes/` |
| synthetic case route | `prototype/routes/` |
| synthetic intake route | `prototype/routes/` |
| reasoning map route | `prototype/routes/` |
| evidence panel routes | `prototype/routes/` |
| safe export preview route | `prototype/routes/` |
| red-team routes | `prototype/routes/` |
| audit trace route | `prototype/routes/` |
| safety reference route | `prototype/routes/` |

Blocked mapping:

- route files under `clinical/`,
- route files under `patient/`,
- route files under `diagnosis/`,
- route files under `validation/clinical/`,
- route files under `product_ready/`,
- route files outside allowed prototype namespace without source mapping.

Route-to-folder rule:

> Route files may exist only inside the safe local prototype route namespace.

---

## 14. Screen-to-Folder Mapping

All screen files must live only in:

```text
prototype/screens/
```

Allowed mapping:

| Screen File Category | Folder |
|---|---|
| prototype boundary screen | `prototype/screens/` |
| synthetic case selector screen | `prototype/screens/` |
| intake review screen | `prototype/screens/` |
| reasoning map screen | `prototype/screens/` |
| evidence panel screens | `prototype/screens/` |
| export preview screen | `prototype/screens/` |
| red-team screens | `prototype/screens/` |
| audit trace screen | `prototype/screens/` |
| safety reference screen | `prototype/screens/` |

Blocked mapping:

- clinical screens under any folder,
- patient-facing screens under any folder,
- diagnosis screens under any folder,
- treatment/order/procedure/follow-up/triage screens under any folder,
- validation/performance screens under any folder,
- MDD consensus screens under any folder.

Screen-to-folder rule:

> Screen files may exist only inside the safe local prototype screen namespace.

---

## 15. Route / Screen Source Contract Mapping

Every route and screen file must trace to source contracts.

| File Group | Source Contracts |
|---|---|
| prototype boundary route/screen | v0.15.0; v0.15.6; v0.16.1; v0.17.0 |
| synthetic case selector route/screen | v0.14; v0.15.2; v0.16.1; v0.16.2 |
| synthetic intake route/screen | v0.11; v0.15.2; v0.16.1; v0.16.2 |
| reasoning map route/screen | v0.15.3; v0.16.1; v0.16.3 |
| evidence panel route/screens | v0.15.1; v0.15.3; v0.16.1 |
| safe export preview route/screen | v0.13; v0.15.4; v0.16.6 |
| red-team route/screens | v0.14; v0.15.4; v0.16.4; v0.16.6 |
| audit trace route/screen | v0.12; v0.13; v0.16.5 |
| safety reference route/screen | v0.15.5; v0.16.7; v0.16.8 |

Source mapping rule:

> Route and screen files without sealed source contracts are blocked.

---

## 16. Route File Safety Labels

Every route file must include or reference these safety labels.

```yaml
required_route_file_safety_labels:
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  report_import_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

Route safety label rule:

> A route file cannot be considered safe if its safety labels are missing.

---

## 17. Screen File Safety Labels

Every screen file must include or reference these safety labels.

```yaml
required_screen_file_safety_labels:
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
```

Screen safety label rule:

> A screen file cannot be considered safe if it can render without safety labels.

---

## 18. Route README Requirement

The route folder should include:

```text
prototype/routes/README.md
```

Required route README statements:

```text
This folder contains internal synthetic prototype route scaffold files only.
Routes are not clinical workflows.
Routes are not patient-facing.
Routes do not accept real patient data.
Routes do not import DICOM, HRCT images, or real clinical reports.
Routes do not connect to PACS or EHR.
Routes do not diagnose, treat, order, decide procedures, schedule follow-up, triage, or generate MDD consensus.
All route files must map to sealed source contracts and remain fail-closed.
```

Route README rule:

> Route folder boundary text must prevent route files from being read as clinical workflow.

---

## 19. Screen README Requirement

The screen folder should include:

```text
prototype/screens/README.md
```

Required screen README statements:

```text
This folder contains internal synthetic prototype screen scaffold files only.
Screens organize safe prototype visibility.
Screens are not clinical interpretation surfaces.
Screens are not patient-facing.
Screens do not display diagnosis, probability, treatment, orders, procedures, follow-up, triage, patient summary, clinical validation, product readiness, public readiness, or MDD consensus.
All screen files must map to sealed source contracts and preserve the authority envelope and no-decision object.
```

Screen README rule:

> Screen folder boundary text must prevent screen files from being read as clinical output.

---

## 20. Route / Screen Fail-Closed Conditions

Route and screen file planning must fail closed under the following conditions.

```yaml
route_screen_fail_closed_conditions:
  route_file_name_matches_blocked_registry:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  screen_file_name_matches_blocked_registry:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  file_name_matches_blocked_pattern:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  route_path_not_under_prototype_namespace:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  route_file_has_no_source_contract:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  screen_file_has_no_source_contract:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  route_file_implies_clinical_workflow:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  screen_file_implies_clinical_output:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  route_or_screen_missing_authority_envelope:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  decision_adjacent_screen_missing_no_decision_object:
    result: reject_file
    repair_required: true
    audit_stub_required: true
```

Route/screen fail-closed rule:

> Unsafe route or screen files must be rejected before they become scaffold artifacts.

---

## 21. Route / Screen Repair Rules

Repair is allowed only as scaffold safety repair.

Allowed repair actions:

- rename unsafe route file,
- rename unsafe screen file,
- remove blocked route file,
- remove blocked screen file,
- move safe file into correct folder,
- add source contract mapping,
- add safety labels,
- add authority envelope reference,
- add no-decision object reference,
- add audit stub requirement,
- remove unsafe route path,
- remove unsafe screen copy,
- update validation checklist.

Blocked repair meanings:

- clinical correction,
- diagnosis correction,
- treatment correction,
- route-to-clinical-workflow conversion,
- clinical validation correction,
- product readiness correction,
- public release correction.

Repair rule:

> Repair fixes unsafe scaffold meaning, not clinical functionality.

---

## 22. Route / Screen Audit Stub Requirement

Route and screen file planning should be audit-stub traceable in future implementation.

Allowed audit events:

- route_file_registered,
- route_file_rejected,
- route_source_mapping_verified,
- route_safety_label_verified,
- screen_file_registered,
- screen_file_rejected,
- screen_source_mapping_verified,
- screen_safety_label_verified,
- blocked_route_file_detected,
- blocked_screen_file_detected,
- route_screen_repair_required,
- route_screen_repair_applied,
- route_screen_validation_passed,
- route_screen_validation_failed.

Audit fields:

```yaml
route_screen_audit_stub:
  event_id: string
  event_type: string
  file_path: string
  route_id: optional
  screen_id: optional
  source_contract: string
  event_result: enum(registered, rejected, verified, repair_required, repaired, failed)
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Audit rule:

> Route/screen audit records scaffold safety, not clinical correctness.

---

## 23. Route / Screen Validation Checklist

v0.17.2 route/screen validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| ROUTE_SCREEN_CHECK_001 | route file object schema defined | true |
| ROUTE_SCREEN_CHECK_002 | screen file object schema defined | true |
| ROUTE_SCREEN_CHECK_003 | route file naming convention defined | true |
| ROUTE_SCREEN_CHECK_004 | screen file naming convention defined | true |
| ROUTE_SCREEN_CHECK_005 | allowed route file registry defined | true |
| ROUTE_SCREEN_CHECK_006 | blocked route file registry defined | true |
| ROUTE_SCREEN_CHECK_007 | allowed screen file registry defined | true |
| ROUTE_SCREEN_CHECK_008 | blocked screen file registry defined | true |
| ROUTE_SCREEN_CHECK_009 | route-to-folder mapping defined | true |
| ROUTE_SCREEN_CHECK_010 | screen-to-folder mapping defined | true |
| ROUTE_SCREEN_CHECK_011 | route/screen source contract mapping defined | true |
| ROUTE_SCREEN_CHECK_012 | route file safety labels defined | true |
| ROUTE_SCREEN_CHECK_013 | screen file safety labels defined | true |
| ROUTE_SCREEN_CHECK_014 | route README requirement defined | true |
| ROUTE_SCREEN_CHECK_015 | screen README requirement defined | true |
| ROUTE_SCREEN_CHECK_016 | route/screen fail-closed conditions defined | true |
| ROUTE_SCREEN_CHECK_017 | route/screen repair rules defined | true |
| ROUTE_SCREEN_CHECK_018 | route/screen audit stub requirement defined | true |
| ROUTE_SCREEN_CHECK_019 | no patient route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_020 | no clinical route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_021 | no DICOM/HRCT/report/PACS/EHR route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_022 | no diagnosis/ranking/rule-out route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_023 | no treatment/order/procedure/follow-up/triage route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_024 | no patient-facing route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_025 | no validation/performance route/screen files allowed | true |
| ROUTE_SCREEN_CHECK_026 | no product/public/MDD consensus route/screen files allowed | true |

Route/screen validation rule:

> Route/screen validation passes only if every route and screen file remains internal, synthetic, source-governed, non-clinical, non-authoritative, non-patient-facing, non-validating, non-ready, and fail-closed.

---

## 24. v0.17.2 Acceptance Criteria

v0.17.2 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| allowed route file registry defined | true |
| blocked route file registry defined | true |
| allowed screen file registry defined | true |
| blocked screen file registry defined | true |
| route file naming convention defined | true |
| screen file naming convention defined | true |
| route-to-folder mapping defined | true |
| screen-to-folder mapping defined | true |
| route/screen source contract mapping defined | true |
| route file safety labels defined | true |
| screen file safety labels defined | true |
| route README requirement defined | true |
| screen README requirement defined | true |
| route/screen fail-closed conditions defined | true |
| route/screen repair rules defined | true |
| route/screen audit stub requirement defined | true |
| route/screen validation checklist defined | true |
| no patient route/screen file opened | true |
| no clinical route/screen file opened | true |
| no DICOM/HRCT/report/PACS/EHR route/screen file opened | true |
| no diagnosis/treatment/order/procedure/follow-up/triage route/screen file opened | true |
| no patient-facing route/screen file opened | true |
| no clinical validation/performance route/screen file opened | true |
| no product/public readiness route/screen file opened | true |
| no MDD consensus route/screen file opened | true |
| public_ready remains false | true |
| product_ready remains false | true |
| clinical_validation remains not_opened | true |
| diagnostic_authority remains none | true |
| treatment_authority remains none | true |

v0.17.2 acceptance rule:

> The route/screen file scaffold plan is accepted only if local route and screen files cannot be mistaken for clinical workflow, clinical output, patient-facing use, validation, readiness, or MDD replacement.

---

## 25. Next Step

The next recommended step is:

- v0.17.3 — Synthetic Fixture File Scaffold Plan

v0.17.3 should define:

- allowed synthetic fixture file registry,
- blocked fixture file registry,
- synthetic case fixture file naming,
- demo reasoning session fixture file naming,
- demo intake binding fixture file naming,
- demo workspace state fixture file naming,
- demo export fixture file naming,
- demo red-team fixture file naming,
- fixture-to-folder mapping,
- fixture source contract mapping,
- fixture file safety labels,
- fixture README requirement,
- fixture fail-closed conditions,
- fixture validation checklist.

v0.17.3 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 26. Governance Statement

This document defines the local route file and screen file scaffold plan.

It opens route/screen file scaffold planning only.

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

The v0.17.2 governance discipline is:

> “Do not let route files become clinical workflow and do not let screen files become clinical output.”

The route/screen scaffold discipline is:

> “Safe navigation and safe visibility are allowed; clinical action and clinical interpretation are not.”