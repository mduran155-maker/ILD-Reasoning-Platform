# ILD Reasoning Platform — Prototype Folder Namespace / Blocked Folder Registry v1

Version: v0.17.1  
Status: prototype_folder_namespace_blocked_folder_registry  
Scope: Allowed local prototype root namespace, allowed folder tree, folder purpose registry, folder-to-source contract mapping, blocked folder registry, blocked folder name patterns, hidden/placeholder folder blocking, folder README requirement, folder safety label requirement, folder validation checklist, and source-governed local scaffold namespace discipline  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.17.1 — Prototype Folder Namespace / Blocked Folder Registry.

v0.17.1 translates the v0.17.0 local prototype file/folder scaffold entry gate into a concrete allowed and blocked folder namespace plan.

This document does not implement a clinical product.

It does not add executable clinical functionality.

It does not create a frontend application.

It does not create a backend application.

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

Its purpose is to define which local prototype folders may exist, why they may exist, which source contracts they trace to, and which folder names or categories must remain blocked because they imply clinical capability.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.17.1 namespace principle is:

> “A folder name can create authority; therefore folder names must remain source-governed, synthetic, internal, non-clinical, and fail-closed.”

The v0.17.1 blocked-folder principle is:

> “Blocked folders cannot exist as empty placeholders, future toggles, hidden directories, or coming-soon clinical paths.”

---

## 2. Relationship to v0.17.0

v0.17.1 inherits v0.17.0 — Local Prototype File / Folder Scaffold Entry Gate.

v0.17.0 opened:

- local prototype repository boundary,
- internal-only scaffold scope,
- source-governed file naming principle,
- allowed folder categories,
- blocked folder categories,
- allowed file categories,
- blocked file categories,
- allowed scaffold root,
- initial allowed folder plan,
- blocked local folder plan,
- route/screen file boundary,
- synthetic fixture file boundary,
- UI copy file boundary,
- fail-closed/disabled control file boundary,
- audit stub file boundary,
- export/red-team stub file boundary,
- validation file boundary,
- README boundary.

v0.17.1 does not broaden v0.17.0.

v0.17.1 defines the first concrete local folder namespace registry under those boundaries.

v0.17.1 must not open:

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

Namespace inheritance rule:

> v0.17.1 may define safe local folders only; it may not define clinical implementation folders.

---

## 3. Global Authority Envelope

Every planned folder, subfolder, namespace, folder description, README, folder source mapping, folder validation row, folder safety label, and folder naming convention must preserve the following authority envelope.

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

No folder name may imply an exception to this envelope.

Authority namespace rule:

> Folder names are not neutral; unsafe folder names can create unsafe meaning.

---

## 4. Global No-Decision Folder Requirement

The no-decision object remains active across the local folder namespace.

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

The following folder categories must reference the no-decision object directly or indirectly:

- safety,
- routes,
- screens,
- components,
- state,
- copy,
- fail_closed,
- disabled_controls,
- audit,
- export_preview,
- red_team,
- validation.

No-decision folder rule:

> Decision-adjacent folders must make clear that no clinical decision can be produced from their contents.

---

## 5. Allowed Local Root Namespace

The allowed primary local root namespace is:

```text
prototype/
```

Allowed alternative root names:

```text
internal_prototype/
synthetic_prototype/
prototype_internal/
```

Preferred root:

```text
prototype/
```

Required root properties:

```yaml
prototype_root_namespace:
  internal_demo_only: true
  synthetic_only: true
  non_clinical: true
  patient_facing: false
  public_ready: false
  product_ready: false
  clinical_validation: not_opened
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  report_import_allowed: false
  pacs_ehr_allowed: false
  diagnosis_allowed: false
  treatment_allowed: false
  orders_allowed: false
  procedures_allowed: false
  follow_up_allowed: false
  triage_allowed: false
  mdd_replacement_allowed: false
```

Blocked root names:

```text
clinical_app/
patient_app/
diagnosis_platform/
ipf_diagnosis/
ipf_clinical_tool/
clinical_validation/
diagnostic_engine/
product/
public_demo/
mdd_consensus/
```

Root namespace rule:

> The root namespace must signal local internal prototype identity, not clinical product identity.

---

## 6. Allowed Folder Tree

The allowed initial folder tree is:

```text
prototype/
  README.md
  safety/
  routes/
  screens/
  components/
  fixtures/
  state/
  copy/
  fail_closed/
  disabled_controls/
  audit/
  export_preview/
  red_team/
  validation/
```

No other top-level prototype folder may be added unless it passes:

- source-governed mapping,
- allowed folder category test,
- blocked folder name pattern test,
- authority envelope test,
- no-decision test where relevant,
- no clinical capability test.

Allowed folder tree rule:

> The initial tree is intentionally narrow to prevent premature clinical expansion.

---

## 7. Folder Purpose Registry

Every allowed folder must have a declared purpose.

| Folder | Purpose | Clinical Capability Effect |
|---|---|---|
| `prototype/` | local internal synthetic prototype scaffold root | none |
| `prototype/safety/` | authority envelope, no-decision, visual safety references | none |
| `prototype/routes/` | internal `/prototype` route scaffold files | none |
| `prototype/screens/` | internal prototype screen scaffold files | none |
| `prototype/components/` | safe UI component scaffold files | none |
| `prototype/fixtures/` | synthetic demo fixture files only | none |
| `prototype/state/` | synthetic demo state files only | none |
| `prototype/copy/` | source-governed UI copy registry files | none |
| `prototype/fail_closed/` | fail-closed unsafe attempt stub files | none |
| `prototype/disabled_controls/` | disabled clinical control definition files | none |
| `prototype/audit/` | audit event stub and traceability files | none |
| `prototype/export_preview/` | safe export preview stub files | none |
| `prototype/red_team/` | red-team fail-closed scenario stub files | none |
| `prototype/validation/` | scaffold safety validation checklist files | none |

Folder purpose rule:

> A folder may organize scaffold artifacts only; it may not introduce clinical functionality.

---

## 8. Folder-to-Source Contract Mapping

Every allowed folder must trace to sealed contracts.

| Folder | Primary Source Contracts |
|---|---|
| `prototype/` | v0.16.8 structural seal; checkpoint-v0.16; v0.17.0 |
| `prototype/safety/` | v0.15.5; v0.15.6; v0.16.7; v0.16.8 |
| `prototype/routes/` | v0.16.1; v0.17.0 |
| `prototype/screens/` | v0.15.1; v0.16.1; v0.17.0 |
| `prototype/components/` | v0.15.1; v0.16.1; v0.16.3 |
| `prototype/fixtures/` | v0.14; v0.16.2; v0.17.0 |
| `prototype/state/` | v0.12; v0.16.2; v0.17.0 |
| `prototype/copy/` | v0.16.3; v0.17.0 |
| `prototype/fail_closed/` | v0.15.4; v0.16.4; v0.17.0 |
| `prototype/disabled_controls/` | v0.16.4; v0.16.3; v0.17.0 |
| `prototype/audit/` | v0.12; v0.13; v0.16.5; v0.17.0 |
| `prototype/export_preview/` | v0.13; v0.15.4; v0.16.6; v0.17.0 |
| `prototype/red_team/` | v0.14; v0.15.4; v0.16.6; v0.17.0 |
| `prototype/validation/` | v0.15.5; v0.16.7; v0.17.0 |

Folder-source mapping rule:

> A folder without source-contract mapping cannot enter the local scaffold.

---

## 9. Folder Safety Label Requirement

Every top-level folder must carry or inherit safety labels.

Required inherited safety labels:

```yaml
required_folder_safety_labels:
  internal_demo_only: true
  synthetic_only: true
  non_clinical: true
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  report_import_allowed: false
  patient_facing_allowed: false
  clinical_validation: not_opened
  diagnostic_authority: none
  treatment_authority: none
  product_ready: false
  public_ready: false
  mdd_replacement: not_allowed
```

Folder safety label rule:

> A folder is safe only if its intended content inherits the platform boundary.

---

## 10. Folder README Requirement

The local scaffold root must include:

```text
prototype/README.md
```

The following folders should include README or README-equivalent boundary notes when files are later added:

```text
prototype/safety/README.md
prototype/fixtures/README.md
prototype/copy/README.md
prototype/fail_closed/README.md
prototype/audit/README.md
prototype/export_preview/README.md
prototype/red_team/README.md
prototype/validation/README.md
```

Required folder README statements:

```text
This folder belongs to the internal synthetic prototype scaffold.
It is not a clinical implementation.
It is not for patient-facing use.
It contains no real patient data.
It contains no deidentified real patient data.
It does not import DICOM, HRCT images, or real clinical reports.
It does not connect to PACS or EHR.
It does not diagnose, treat, order, decide procedures, schedule follow-up, triage, or replace MDD.
It is not clinically validated.
It is not product ready.
It is not public ready.
```

Folder README rule:

> Folder boundary text must precede later implementation interpretation.

---

## 11. Blocked Folder Registry

The following folders are blocked.

```text
prototype/patient_data/
prototype/patients/
prototype/patient_cases/
prototype/deidentified_patient_data/
prototype/deidentified_cases/
prototype/clinical_cases/
prototype/clinical/
prototype/dicom/
prototype/dicom_import/
prototype/hrct/
prototype/hrct_images/
prototype/images/
prototype/image_viewer/
prototype/pacs/
prototype/dicomweb/
prototype/ehr/
prototype/fhir/
prototype/reports/
prototype/report_import/
prototype/report_parser/
prototype/radiology_reports/
prototype/pathology_reports/
prototype/microbiology_reports/
prototype/clinical_notes/
prototype/diagnosis/
prototype/final_diagnosis/
prototype/likely_diagnosis/
prototype/probability/
prototype/ranking/
prototype/rule_out/
prototype/exclusion/
prototype/treatment/
prototype/therapy/
prototype/management_plan/
prototype/orders/
prototype/test_orders/
prototype/procedures/
prototype/procedure_recommendations/
prototype/follow_up/
prototype/follow_up_scheduler/
prototype/triage/
prototype/disposition/
prototype/patient_summary/
prototype/patient_facing/
prototype/patient_portal/
prototype/share_with_patient/
prototype/clinical_validation/
prototype/validation_clinical/
prototype/performance/
prototype/diagnostic_performance/
prototype/accuracy/
prototype/sensitivity_specificity/
prototype/auc/
prototype/expert_equivalence/
prototype/product_ready/
prototype/release/
prototype/deployment/
prototype/public/
prototype/public_demo/
prototype/mdd_consensus/
prototype/mdd_final_decision/
```

Blocked folder registry rule:

> Blocked folders may not exist as enabled folders, hidden folders, empty placeholders, future toggles, comments, examples, or planned near-term folders.

---

## 12. Blocked Folder Name Patterns

The following name patterns are blocked anywhere under the prototype root.

```yaml
blocked_folder_name_patterns:
  patient:
    - "patient"
    - "patients"
    - "patient_data"
    - "patient_cases"
    - "patient_summary"
    - "patient_portal"
  clinical:
    - "clinical"
    - "clinical_cases"
    - "clinical_validation"
    - "clinical_workflow"
  imaging_import:
    - "dicom"
    - "dicom_import"
    - "hrct"
    - "images"
    - "image_viewer"
    - "pacs"
    - "dicomweb"
  ehr_report:
    - "ehr"
    - "fhir"
    - "reports"
    - "report_import"
    - "report_parser"
    - "clinical_notes"
  diagnosis:
    - "diagnosis"
    - "final_diagnosis"
    - "likely_diagnosis"
    - "probability"
    - "ranking"
    - "rule_out"
    - "exclusion"
  action:
    - "treatment"
    - "therapy"
    - "orders"
    - "procedures"
    - "follow_up"
    - "triage"
    - "disposition"
  validation_readiness:
    - "performance"
    - "accuracy"
    - "sensitivity"
    - "specificity"
    - "auc"
    - "expert_equivalence"
    - "product_ready"
    - "public"
    - "deployment"
  mdd_replacement:
    - "mdd_consensus"
    - "mdd_final_decision"
```

Pattern rule:

> Unsafe folder names are blocked by semantic meaning, not only exact string match.

---

## 13. Hidden / Placeholder Folder Blocking

The following are blocked:

- empty clinical folders,
- hidden clinical folders,
- `.clinical/`,
- `_clinical/`,
- `__clinical/`,
- `clinical_unused/`,
- `clinical_future/`,
- `diagnosis_stub/`,
- `patient_upload_disabled/`,
- `pacs_soon/`,
- `dicom_future/`,
- `validation_later/`,
- `product_ready_placeholder/`,
- `public_demo_placeholder/`.

Blocked placeholder language:

- coming soon clinical mode,
- future patient upload,
- diagnosis module later,
- connect PACS soon,
- validation ready soon,
- unlock clinical version,
- product release folder,
- public deployment folder.

Placeholder blocking rule:

> A forbidden folder remains forbidden even when empty, disabled, hidden, commented out, or marked future.

---

## 14. Allowed Subfolder Expansion Rules

Allowed folders may have subfolders only if the subfolders preserve the parent boundary.

Allowed examples:

```text
prototype/routes/route_registry/
prototype/routes/navigation_graph/

prototype/screens/screen_registry/
prototype/screens/panel_screens/

prototype/components/safety_components/
prototype/components/evidence_visibility_components/

prototype/fixtures/synthetic_cases/
prototype/fixtures/demo_sessions/
prototype/fixtures/red_team_fixtures/

prototype/state/demo_state_objects/
prototype/state/session_state_fixtures/

prototype/copy/core_safety_copy/
prototype/copy/route_copy/
prototype/copy/blocked_phrases/

prototype/fail_closed/route_attempts/
prototype/fail_closed/data_attempts/
prototype/fail_closed/action_attempts/

prototype/audit/route_events/
prototype/audit/fail_closed_events/
prototype/audit/export_events/

prototype/export_preview/section_stubs/
prototype/export_preview/detector_stubs/

prototype/red_team/scenario_registry/
prototype/red_team/quarantine_display/

prototype/validation/checklists/
prototype/validation/gate_results/
```

Subfolder rule:

> Subfolders inherit parent boundaries and must not introduce blocked clinical terms.

---

## 15. Folder Namespace State Machine

Folder namespace planning must follow this state machine.

```yaml
folder_namespace_state_machine:
  proposed_folder:
    next:
      - source_mapping_pending
      - rejected_blocked_name
  source_mapping_pending:
    next:
      - safety_label_pending
      - rejected_source_missing
  safety_label_pending:
    next:
      - blocked_pattern_scan_pending
      - rejected_safety_label_missing
  blocked_pattern_scan_pending:
    next:
      - allowed_folder_registered
      - rejected_blocked_pattern
  allowed_folder_registered:
    result: folder_allowed
  rejected_blocked_name:
    result: folder_blocked
  rejected_source_missing:
    result: folder_blocked
  rejected_safety_label_missing:
    result: folder_blocked
  rejected_blocked_pattern:
    result: folder_blocked
```

Folder state rule:

> A folder becomes allowed only after source mapping, safety labeling, and blocked-name scanning.

---

## 16. Folder Fail-Closed Conditions

Folder planning must fail closed under the following conditions.

```yaml
folder_fail_closed_conditions:
  folder_name_matches_blocked_registry:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_name_matches_blocked_pattern:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_has_no_source_contract:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_safety_label_missing:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_implies_clinical_use:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_implies_patient_data:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_implies_dicom_report_pacs_ehr:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_implies_diagnosis_action:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_implies_validation_or_readiness:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
  folder_implies_mdd_replacement:
    result: reject_folder
    repair_required: true
    audit_stub_required: true
```

Folder fail-closed rule:

> Unsafe folder names must be rejected before files can be created inside them.

---

## 17. Folder Repair Rules

Folder repair is allowed only as scaffold safety repair.

Allowed folder repair actions:

- rename unsafe folder to safe source-governed name,
- remove blocked folder,
- move safe content into allowed folder,
- add source contract mapping,
- add README boundary note,
- add safety label,
- remove hidden/future clinical implication,
- update validation checklist.

Blocked repair meanings:

- clinical implementation correction,
- diagnosis module correction,
- patient data pipeline correction,
- DICOM import correction,
- clinical validation correction,
- product readiness correction,
- public release correction.

Folder repair rule:

> Folder repair fixes scaffold meaning, not clinical functionality.

---

## 18. Folder Audit Stub Requirement

Folder namespace changes should be audit-stub traceable in future implementation.

Allowed folder namespace audit events:

- folder_namespace_viewed,
- allowed_folder_registered,
- blocked_folder_rejected,
- folder_source_mapping_verified,
- folder_safety_label_verified,
- folder_readme_boundary_verified,
- blocked_pattern_detected,
- folder_repair_required,
- folder_repair_applied,
- folder_namespace_validation_passed,
- folder_namespace_validation_failed.

Audit fields:

```yaml
folder_namespace_audit_stub:
  event_id: string
  event_type: string
  folder_path: string
  source_contract: string
  event_result: enum(registered, rejected, verified, repair_required, repaired, failed)
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Folder audit rule:

> Folder audit records scaffold namespace safety, not clinical correctness.

---

## 19. Folder Validation Checklist

v0.17.1 folder namespace validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| FOLDER_CHECK_001 | allowed root namespace defined | true |
| FOLDER_CHECK_002 | allowed folder tree defined | true |
| FOLDER_CHECK_003 | folder purpose registry defined | true |
| FOLDER_CHECK_004 | folder-to-source contract mapping defined | true |
| FOLDER_CHECK_005 | folder safety label requirement defined | true |
| FOLDER_CHECK_006 | folder README requirement defined | true |
| FOLDER_CHECK_007 | blocked folder registry defined | true |
| FOLDER_CHECK_008 | blocked folder name patterns defined | true |
| FOLDER_CHECK_009 | hidden/placeholder folder blocking defined | true |
| FOLDER_CHECK_010 | allowed subfolder expansion rules defined | true |
| FOLDER_CHECK_011 | folder namespace state machine defined | true |
| FOLDER_CHECK_012 | folder fail-closed conditions defined | true |
| FOLDER_CHECK_013 | folder repair rules defined | true |
| FOLDER_CHECK_014 | folder audit stub requirement defined | true |
| FOLDER_CHECK_015 | no patient data folder allowed | true |
| FOLDER_CHECK_016 | no deidentified patient data folder allowed | true |
| FOLDER_CHECK_017 | no DICOM/HRCT/image/PACS/EHR folder allowed | true |
| FOLDER_CHECK_018 | no report import/parser folder allowed | true |
| FOLDER_CHECK_019 | no diagnosis/ranking/rule-out folder allowed | true |
| FOLDER_CHECK_020 | no treatment/order/procedure/follow-up/triage folder allowed | true |
| FOLDER_CHECK_021 | no patient-facing folder allowed | true |
| FOLDER_CHECK_022 | no clinical validation/performance folder allowed | true |
| FOLDER_CHECK_023 | no product/public readiness folder allowed | true |
| FOLDER_CHECK_024 | no MDD consensus folder allowed | true |
| FOLDER_CHECK_025 | every allowed folder maps to source contract | true |
| FOLDER_CHECK_026 | every allowed folder inherits authority envelope | true |

Folder validation rule:

> Folder namespace validation passes only if the local tree cannot be mistaken for clinical software.

---

## 20. v0.17.1 Acceptance Criteria

v0.17.1 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| allowed local root namespace defined | true |
| allowed folder tree defined | true |
| folder purpose registry defined | true |
| folder-to-source contract mapping defined | true |
| blocked folder registry defined | true |
| blocked folder name patterns defined | true |
| hidden/placeholder folder blocking defined | true |
| folder README requirement defined | true |
| folder safety label requirement defined | true |
| allowed subfolder expansion rules defined | true |
| folder namespace state machine defined | true |
| folder fail-closed conditions defined | true |
| folder repair rules defined | true |
| folder audit stub requirement defined | true |
| folder validation checklist defined | true |
| no real patient data folder opened | true |
| no deidentified real patient data folder opened | true |
| no DICOM/HRCT/report/PACS/EHR folder opened | true |
| no patient-facing folder opened | true |
| no clinical validation/performance folder opened | true |
| no diagnosis/treatment/order/procedure/follow-up/triage folder opened | true |
| no product/public readiness folder opened | true |
| no MDD consensus folder opened | true |
| public_ready remains false | true |
| product_ready remains false | true |
| clinical_validation remains not_opened | true |
| diagnostic_authority remains none | true |
| treatment_authority remains none | true |

v0.17.1 acceptance rule:

> The folder namespace plan is accepted only if the local prototype tree remains internal, synthetic, source-governed, non-clinical, non-authoritative, non-patient-facing, non-validating, non-ready, and fail-closed.

---

## 21. Next Step

The next recommended step is:

- v0.17.2 — Route File Scaffold / Screen File Scaffold Plan

v0.17.2 should define:

- allowed route file registry,
- blocked route file registry,
- allowed screen file registry,
- blocked screen file registry,
- route file naming convention,
- screen file naming convention,
- route-to-folder mapping,
- screen-to-folder mapping,
- route/screen source contract mapping,
- route/screen README requirements,
- route/screen safety labels,
- route/screen file validation checklist.

v0.17.2 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 22. Governance Statement

This document defines the local prototype folder namespace and blocked folder registry.

It opens folder namespace planning only.

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

The v0.17.1 governance discipline is:

> “Do not let folder names become clinical claims.”

The folder namespace discipline is:

> “Unsafe folders are blocked before unsafe files can exist.”