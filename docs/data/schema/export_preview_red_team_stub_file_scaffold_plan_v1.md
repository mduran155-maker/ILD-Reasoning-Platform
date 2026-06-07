# ILD Reasoning Platform — Export Preview / Red-Team Stub File Scaffold Plan v1

Version: v0.17.6  
Status: export_preview_red_team_stub_file_scaffold_plan  
Scope: Allowed export preview file registry, blocked export preview file registry, allowed red-team file registry, blocked red-team file registry, export preview file naming, red-team file naming, export/red-team-to-folder mapping, export/red-team source contract mapping, export/red-team file safety labels, export/red-team README requirements, export/red-team fail-closed conditions, detector file boundary, quarantine file boundary, copy/export block file boundary, repair/revalidation file boundary, export/red-team audit binding file boundary, and export/red-team file validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.17.6 — Export Preview / Red-Team Stub File Scaffold Plan.

v0.17.6 translates the sealed safe export preview stub plan, red-team scenario stub plan, fail-closed scaffold, audit scaffold, UI copy scaffold, and local folder namespace into concrete export preview and red-team file scaffold planning for the local internal prototype.

This document does not implement a clinical product.

It does not create a clinical report generator.

It does not create an impression generator.

It does not create a diagnosis exporter.

It does not create a patient summary exporter.

It does not create an MDD consensus exporter.

It does not create reusable unsafe output.

It does not create clinical safe phrase templates.

It does not create validated red-team outputs.

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

Its purpose is to define which local export preview and red-team scaffold files may exist under:

```text
prototype/export_preview/
prototype/red_team/
```

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.17.6 export file principle is:

> “An export preview file may scaffold safe structure, but it must not become a clinical report generator.”

The v0.17.6 red-team file principle is:

> “A red-team file may demonstrate containment, but it must not become reusable unsafe output.”

---

## 2. Relationship to v0.17.0–v0.17.5

v0.17.6 inherits:

- v0.17.0 — Local Prototype File / Folder Scaffold Entry Gate,
- v0.17.1 — Prototype Folder Namespace / Blocked Folder Registry,
- v0.17.2 — Route File / Screen File Scaffold Plan,
- v0.17.3 — Synthetic Fixture File Scaffold Plan,
- v0.17.4 — UI Copy Registry File Scaffold Plan,
- v0.17.5 — Fail-Closed / Audit Stub File Scaffold Plan.

v0.17.0 opened local file/folder scaffold planning.

v0.17.1 defined the allowed local folder namespace and blocked folder registry.

v0.17.2 defined route and screen file scaffold planning.

v0.17.3 defined synthetic fixture file scaffold planning.

v0.17.4 defined UI copy registry file scaffold planning.

v0.17.5 defined fail-closed, disabled control, and audit stub file scaffold planning.

v0.17.6 defines export preview and red-team stub file scaffold planning under:

```text
prototype/export_preview/
prototype/red_team/
```

v0.17.6 does not broaden v0.17.0–v0.17.5.

v0.17.6 must not open:

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

> v0.17.6 may define local export/red-team containment files only; it may not define report generation, diagnosis export, patient-facing export, validation, readiness, or MDD consensus files.

---

## 3. Global Authority Envelope

Every export preview file, red-team file, detector file, quarantine file, copy/export block file, repair/revalidation file, export/red-team audit binding file, file ID, filename, file metadata object, file mapping, validation row, README note, and implementation note must preserve the following authority envelope.

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

No export preview or red-team file may imply an exception to this envelope.

Authority export/red-team rule:

> Export and red-team files cannot grant clinical authority by safely displaying or blocking unsafe content.

---

## 4. Global No-Decision Object

The no-decision object must remain visible or referenceable in all export preview and red-team files.

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

- safe export preview stub registry files,
- export section stub registry files,
- export safety check files,
- unsafe heading detector files,
- unsafe language detector files,
- copy/export block files,
- red-team scenario registry files,
- red-team quarantine display files,
- red-team repair/revalidation files,
- export/red-team audit binding files.

No-decision export/red-team rule:

> Export and red-team files must preserve that no clinical decision or patient-facing output was generated.

---

## 5. Export Preview File Object Schema

Every allowed export preview file must conform to the following schema.

```yaml
export_preview_file_scaffold:
  export_file_id: string
  version: v0.17.6
  file_path: string
  export_file_type: enum
  export_file_title: string
  parent_folder: "prototype/export_preview/"
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_report_generator: false
  diagnostic_report_generator: false
  impression_generator: false
  patient_summary_generator: false
  mdd_consensus_generator: false
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
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  copy_allowed: conditional_safe_only
  export_allowed: conditional_safe_only
  unsafe_copy_allowed: false
  unsafe_export_allowed: false
  required_authority_envelope: true
  required_no_decision_object: true
  required_audit_stub: true
  fail_closed_conditions: list
```

Export file rule:

> An export preview file is allowed only if it scaffolds safe preview structure and cannot generate a clinical report.

---

## 6. Red-Team File Object Schema

Every allowed red-team file must conform to the following schema.

```yaml
red_team_file_scaffold:
  red_team_file_id: string
  version: v0.17.6
  file_path: string
  red_team_file_type: enum
  red_team_file_title: string
  parent_folder: "prototype/red_team/"
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  internal_demo_only: true
  synthetic_demo_only: true
  unsafe_example_visible: quarantined_only
  unsafe_example_copy_allowed: false
  unsafe_example_export_allowed: false
  reusable_unsafe_output_allowed: false
  clinical_safe_phrase_template_allowed: false
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  authority_effect: none
  decision_effect: none
  required_authority_envelope: true
  required_no_decision_object: true
  required_audit_stub: true
  repair_required_behavior: ui_safety_repair_only
  revalidation_behavior: ui_safety_revalidation_only
  fail_closed_conditions: list
```

Red-team file rule:

> A red-team file is allowed only if unsafe content remains quarantined, non-copyable, non-exportable, and non-reusable.

---

## 7. Allowed Export Preview File Types

The following export preview file types are allowed.

| Export Preview File Type | Allowed Meaning |
|---|---|
| safe_export_preview_stub_registry_file | central safe preview stub registry |
| export_section_stub_registry_file | safe section structure registry |
| export_safety_check_stub_file | UI safety check only |
| unsafe_heading_detector_stub_file | detects unsafe report-like headings |
| unsafe_language_detector_stub_file | detects unsafe clinical language |
| copy_export_block_stub_file | blocks unsafe copy/export |
| export_preview_state_machine_file | safe preview state transitions |
| export_preview_section_order_file | required safe section order |
| export_preview_boundary_copy_binding_file | binds safety copy to preview |
| export_preview_audit_binding_file | binds preview events to audit stubs |
| export_preview_validation_rules_file | scaffold safety validation only |

Allowed export type rule:

> Allowed export preview files define safe preview structure, detection, blocking, and traceability only.

---

## 8. Blocked Export Preview File Types

The following export preview file types are blocked.

| Blocked Export File Type | Reason |
|---|---|
| clinical_report_generator_file | clinical report generation blocked |
| diagnostic_report_generator_file | diagnostic report generation blocked |
| impression_generator_file | impression generation blocked |
| diagnosis_exporter_file | diagnostic authority blocked |
| final_diagnosis_exporter_file | diagnostic closure blocked |
| patient_summary_exporter_file | patient-facing output blocked |
| treatment_plan_exporter_file | treatment authority blocked |
| order_plan_exporter_file | test-order authority blocked |
| procedure_plan_exporter_file | procedure authority blocked |
| follow_up_plan_exporter_file | follow-up authority blocked |
| triage_exporter_file | triage authority blocked |
| mdd_consensus_exporter_file | MDD replacement blocked |
| clinical_validation_exporter_file | clinical validation not opened |
| diagnostic_performance_exporter_file | performance claim blocked |
| product_ready_exporter_file | product readiness false |
| public_ready_exporter_file | public readiness false |

Blocked export file rule:

> Export preview files cannot become report, diagnosis, action, validation, readiness, patient-facing, or MDD consensus generators.

---

## 9. Allowed Red-Team File Types

The following red-team file types are allowed.

| Red-Team File Type | Allowed Meaning |
|---|---|
| red_team_scenario_stub_registry_file | central red-team scenario registry |
| red_team_scenario_detail_structure_file | scenario detail structure |
| red_team_quarantine_display_stub_file | quarantined unsafe example display |
| red_team_copy_export_block_file | copy/export disabled behavior |
| red_team_repair_revalidation_stub_file | UI safety repair/revalidation only |
| red_team_audit_binding_file | red-team event traceability |
| red_team_blocked_meanings_file | blocked red-team interpretations |
| red_team_validation_rules_file | scaffold containment validation only |

Allowed red-team type rule:

> Allowed red-team files demonstrate containment and blocked unsafe behavior only.

---

## 10. Blocked Red-Team File Types

The following red-team file types are blocked.

| Blocked Red-Team File Type | Reason |
|---|---|
| reusable_unsafe_output_examples_file | unsafe reuse blocked |
| clinical_safe_phrase_templates_file | clinical phrase suggestion blocked |
| validated_red_team_outputs_file | validation claim blocked |
| diagnosis_red_team_solution_file | diagnosis generation blocked |
| treatment_red_team_solution_file | treatment authority blocked |
| patient_summary_red_team_solution_file | patient-facing output blocked |
| product_safe_red_team_outputs_file | product readiness false |
| public_safe_red_team_outputs_file | public readiness false |
| mdd_consensus_red_team_solution_file | MDD replacement blocked |
| expert_equivalent_red_team_outputs_file | expert replacement risk |

Blocked red-team file rule:

> Red-team files cannot store reusable unsafe phrases, clinical replacements, validation claims, or product-safe outputs.

---

## 11. Allowed Export Preview File Registry

The following export preview files are allowed.

```text
prototype/export_preview/safe_export_preview_stub_registry.json
prototype/export_preview/export_section_stub_registry.json
prototype/export_preview/export_safety_check_stub.json
prototype/export_preview/unsafe_heading_detector_stub.json
prototype/export_preview/unsafe_language_detector_stub.json
prototype/export_preview/copy_export_block_stub.json
prototype/export_preview/export_preview_state_machine.json
prototype/export_preview/export_preview_section_order.json
prototype/export_preview/export_preview_boundary_copy_binding.json
prototype/export_preview/export_preview_audit_binding.json
prototype/export_preview/export_preview_validation_rules.json
```

Allowed export registry rule:

> Allowed export preview files must remain under `prototype/export_preview/` and must not generate clinical output.

---

## 12. Blocked Export Preview File Registry

The following export preview files are blocked.

```text
prototype/export_preview/clinical_report_generator.json
prototype/export_preview/diagnostic_report_generator.json
prototype/export_preview/impression_generator.json
prototype/export_preview/diagnosis_exporter.json
prototype/export_preview/final_diagnosis_exporter.json
prototype/export_preview/patient_summary_exporter.json
prototype/export_preview/treatment_plan_exporter.json
prototype/export_preview/order_plan_exporter.json
prototype/export_preview/procedure_plan_exporter.json
prototype/export_preview/follow_up_plan_exporter.json
prototype/export_preview/triage_exporter.json
prototype/export_preview/disposition_exporter.json
prototype/export_preview/mdd_consensus_exporter.json
prototype/export_preview/clinical_validation_exporter.json
prototype/export_preview/diagnostic_performance_exporter.json
prototype/export_preview/product_ready_exporter.json
prototype/export_preview/public_ready_exporter.json
```

Blocked export registry rule:

> Blocked export preview files may not exist because they imply clinical report generation, clinical action, validation, readiness, or MDD replacement.

---

## 13. Allowed Red-Team File Registry

The following red-team files are allowed.

```text
prototype/red_team/red_team_scenario_stub_registry.json
prototype/red_team/red_team_scenario_detail_structure.json
prototype/red_team/red_team_quarantine_display_stub.json
prototype/red_team/red_team_copy_export_block.json
prototype/red_team/red_team_repair_revalidation_stub.json
prototype/red_team/red_team_audit_binding.json
prototype/red_team/red_team_blocked_meanings.json
prototype/red_team/red_team_validation_rules.json
```

Allowed red-team registry rule:

> Allowed red-team files must remain under `prototype/red_team/` and must demonstrate containment only.

---

## 14. Blocked Red-Team File Registry

The following red-team files are blocked.

```text
prototype/red_team/reusable_unsafe_output_examples.json
prototype/red_team/clinical_safe_phrase_templates.json
prototype/red_team/validated_red_team_outputs.json
prototype/red_team/diagnosis_red_team_solution.json
prototype/red_team/treatment_red_team_solution.json
prototype/red_team/order_red_team_solution.json
prototype/red_team/procedure_red_team_solution.json
prototype/red_team/follow_up_red_team_solution.json
prototype/red_team/triage_red_team_solution.json
prototype/red_team/patient_summary_red_team_solution.json
prototype/red_team/product_safe_red_team_outputs.json
prototype/red_team/public_safe_red_team_outputs.json
prototype/red_team/mdd_consensus_red_team_solution.json
prototype/red_team/expert_equivalent_red_team_outputs.json
```

Blocked red-team registry rule:

> Blocked red-team files may not exist because they convert unsafe scenarios into reusable clinical or product outputs.

---

## 15. Export Preview File Naming Convention

Allowed export preview naming patterns:

```yaml
allowed_export_preview_file_naming:
  registry: "safe_export_preview_stub_registry.json"
  sections: "export_section_stub_registry.json"
  safety_check: "export_safety_check_stub.json"
  heading_detector: "unsafe_heading_detector_stub.json"
  language_detector: "unsafe_language_detector_stub.json"
  copy_export_block: "copy_export_block_stub.json"
  state_machine: "export_preview_state_machine.json"
  section_order: "export_preview_section_order.json"
  boundary_copy: "export_preview_boundary_copy_binding.json"
  audit_binding: "export_preview_audit_binding.json"
  validation_rules: "export_preview_validation_rules.json"
```

Blocked export naming terms:

- clinical_report,
- diagnostic_report,
- impression,
- diagnosis_export,
- final_diagnosis,
- patient_summary,
- treatment_plan,
- order_plan,
- procedure_plan,
- follow_up_plan,
- triage,
- disposition,
- MDD_consensus,
- clinical_validation,
- diagnostic_performance,
- product_ready,
- public_ready.

Export naming rule:

> Export filenames must describe safety preview mechanics, not clinical report output.

---

## 16. Red-Team File Naming Convention

Allowed red-team naming patterns:

```yaml
allowed_red_team_file_naming:
  registry: "red_team_scenario_stub_registry.json"
  detail_structure: "red_team_scenario_detail_structure.json"
  quarantine_display: "red_team_quarantine_display_stub.json"
  copy_export_block: "red_team_copy_export_block.json"
  repair_revalidation: "red_team_repair_revalidation_stub.json"
  audit_binding: "red_team_audit_binding.json"
  blocked_meanings: "red_team_blocked_meanings.json"
  validation_rules: "red_team_validation_rules.json"
```

Blocked red-team naming terms:

- reusable,
- clinical_safe_phrase,
- validated_output,
- diagnosis_solution,
- treatment_solution,
- order_solution,
- procedure_solution,
- follow_up_solution,
- triage_solution,
- patient_summary_solution,
- product_safe,
- public_safe,
- MDD_consensus,
- expert_equivalent.

Red-team naming rule:

> Red-team filenames must describe containment, not reusable output or clinical replacement language.

---

## 17. Export / Red-Team-to-Folder Mapping

Allowed mappings:

| File Group | Folder |
|---|---|
| export preview stub files | `prototype/export_preview/` |
| red-team scenario stub files | `prototype/red_team/` |

Blocked mappings:

- export files under reports folders,
- export files under patient-facing folders,
- export files under diagnosis/action folders,
- export files under validation/performance folders,
- red-team files under clinical phrase folders,
- red-team files under product/public folders,
- red-team files outside allowed folders without source mapping.

Mapping rule:

> Export preview and red-team files must remain inside safe local containment namespaces.

---

## 18. Export / Red-Team Source Contract Mapping

Every allowed export/red-team file must map to source contracts.

| File Group | Source Contracts |
|---|---|
| safe export preview stub registry | v0.13; v0.15.4; v0.16.6 |
| export section stub registry | v0.13; v0.16.6 |
| export safety check stub | v0.15.4; v0.16.6; v0.16.7 |
| unsafe heading detector stub | v0.16.3; v0.16.6 |
| unsafe language detector stub | v0.16.3; v0.16.6; v0.17.4 |
| copy/export block stub | v0.16.4; v0.16.6; v0.17.5 |
| export preview state machine | v0.16.6 |
| export preview section order | v0.16.6 |
| export preview boundary copy binding | v0.16.3; v0.16.6; v0.17.4 |
| export preview audit binding | v0.16.5; v0.16.6; v0.17.5 |
| red-team scenario stub registry | v0.14; v0.15.4; v0.16.6 |
| red-team scenario detail structure | v0.16.6 |
| red-team quarantine display stub | v0.15.4; v0.16.6 |
| red-team copy/export block | v0.16.4; v0.16.6; v0.17.5 |
| red-team repair/revalidation stub | v0.16.4; v0.16.6; v0.17.5 |
| red-team audit binding | v0.16.5; v0.16.6; v0.17.5 |
| red-team blocked meanings | v0.16.6 |
| export/red-team validation rules | v0.16.6; v0.16.7 |

Source mapping rule:

> Export/red-team files without sealed source contract mapping are blocked.

---

## 19. File Safety Labels

Every export preview and red-team file must include or reference safety labels.

```yaml
required_export_red_team_file_safety_labels:
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
  clinical_report_generation_allowed: false
  diagnosis_export_allowed: false
  patient_summary_export_allowed: false
  treatment_export_allowed: false
  order_export_allowed: false
  procedure_export_allowed: false
  follow_up_export_allowed: false
  triage_export_allowed: false
  mdd_consensus_export_allowed: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
```

Safety label rule:

> Export/red-team files cannot be considered safe if non-clinical and non-authority labels are missing.

---

## 20. README Requirements

The export preview folder should include:

```text
prototype/export_preview/README.md
```

Required export preview README statements:

```text
This folder contains safe export preview scaffold files only.
Export preview files are not clinical report generators.
Export preview files do not generate impressions, diagnoses, treatment plans, orders, procedures, follow-up schedules, triage decisions, patient summaries, or MDD consensus.
Detector files check UI safety language only; they do not validate clinical performance.
Copy/export block files prevent unsafe reuse.
Safe preview means UI safety preview only, not clinical validation.
```

The red-team folder should include:

```text
prototype/red_team/README.md
```

Required red-team README statements:

```text
This folder contains red-team containment scaffold files only.
Red-team files demonstrate fail-closed behavior.
Red-team files are not reusable unsafe output libraries.
Red-team files are not clinical phrase templates.
Red-team files are not validation results.
Red-team pass does not mean clinical validation, product readiness, public readiness, diagnostic performance, or MDD consensus.
Unsafe examples must remain quarantined, non-copyable, and non-exportable.
```

README rule:

> Export/red-team folder README files must prevent preview and red-team artifacts from being interpreted as clinical reports, reusable unsafe output, or validation.

---

## 21. Export Detector File Boundary

Detector files may define:

- unsafe heading detection,
- unsafe language detection,
- report-like heading detection,
- diagnosis language detection,
- exclusion language detection,
- probability/ranking language detection,
- treatment/order/procedure/follow-up/triage language detection,
- patient-facing language detection,
- validation/performance claim detection,
- product/public readiness claim detection,
- MDD consensus claim detection.

Detector files may not define:

- clinical validation,
- diagnostic accuracy,
- sensitivity,
- specificity,
- AUC,
- clinical correctness,
- expert equivalence,
- diagnosis decision,
- treatment decision.

Detector file rule:

> Detector files check UI safety only; they do not validate clinical truth.

---

## 22. Export Preview State Machine Boundary

The export preview state machine may define:

```text
preview_requested
→ safety_check_started
→ authority_envelope_verified
→ no_decision_object_verified
→ safe_preview_available
```

or, if unsafe:

```text
preview_requested
→ safety_check_started
→ unsafe_preview_blocked
→ repair_required
→ ui_safety_revalidation_required
```

Blocked transitions:

- unsafe_preview_blocked → copy_allowed,
- unsafe_preview_blocked → export_allowed,
- safe_preview_available → clinical_report_generated,
- safe_preview_available → diagnosis_exported,
- safe_preview_available → patient_summary_generated,
- safe_preview_available → MDD_consensus_generated,
- repair_required → clinical_validation_passed,
- revalidation_required → diagnostic_performance_passed.

State machine rule:

> Export preview state may pass UI safety only; it cannot pass clinical validation.

---

## 23. Red-Team Quarantine File Boundary

Red-team quarantine files may define:

- quarantined unsafe example display,
- blocked badge,
- failure reason,
- blocked authority,
- not reusable output label,
- copy disabled,
- export disabled,
- print disabled,
- share disabled,
- repair required,
- UI safety revalidation required,
- audit event reference.

Red-team quarantine files may not define:

- suggested safe clinical replacement,
- use-this-instead copy,
- copyable unsafe example,
- exportable unsafe example,
- report-ready phrase,
- clinically validated phrase,
- product-safe phrase,
- public-ready phrase.

Quarantine file rule:

> Quarantine files contain unsafe content only as blocked demonstration, never as reusable language.

---

## 24. Copy / Export Block File Boundary

Copy/export block files may define blocked states for:

- unsafe heading detected,
- unsafe language detected,
- red-team unsafe example,
- blocked preview,
- authority envelope missing,
- no-decision object missing,
- diagnosis language detected,
- exclusion language detected,
- clinical action language detected,
- patient-facing language detected,
- validation/readiness claim detected,
- MDD consensus claim detected.

Copy/export block files may not define:

- allow copy anyway,
- allow export anyway,
- admin override,
- clinical override,
- unsafe export with warning,
- clinical use at own risk.

Copy/export block rule:

> Unsafe copy/export must remain blocked without override.

---

## 25. Repair / Revalidation File Boundary

Export/red-team repair/revalidation files may define:

- UI safety repair required,
- unsafe heading removed,
- unsafe language removed,
- authority envelope restored,
- no-decision object restored,
- quarantine restored,
- copy/export disabled,
- audit binding restored,
- UI safety revalidation started,
- UI safety revalidation passed,
- UI safety revalidation failed.

Export/red-team repair/revalidation files may not define:

- clinical correction,
- diagnostic correction,
- treatment correction,
- probability recalculation,
- clinical validation,
- diagnostic performance validation,
- expert equivalence validation,
- product readiness validation,
- public readiness validation.

Repair/revalidation rule:

> Export/red-team repair and revalidation protect containment only; they do not validate medicine.

---

## 26. Export / Red-Team Audit Binding Boundary

Export/red-team audit binding files may define audit events for:

- export preview requested,
- export safety check started,
- authority envelope verified,
- no-decision object verified,
- safe export preview available,
- unsafe export preview blocked,
- unsafe copy attempt blocked,
- unsafe export attempt blocked,
- red-team hub viewed,
- red-team scenario viewed,
- red-team unsafe example quarantined,
- red-team copy/export blocked,
- repair required,
- UI safety revalidation started,
- UI safety revalidation passed,
- UI safety revalidation failed.

Audit binding files may not define:

- clinical report generated,
- diagnosis exported,
- treatment plan exported,
- order exported,
- procedure exported,
- follow-up exported,
- triage exported,
- patient summary exported,
- MDD consensus generated,
- clinical validation passed,
- diagnostic performance passed.

Audit binding rule:

> Export/red-team audit binding records containment and preview state, not clinical output.

---

## 27. File Fail-Closed Conditions

File planning must fail closed under the following conditions.

```yaml
export_red_team_file_fail_closed_conditions:
  file_name_matches_blocked_registry:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  file_name_matches_blocked_pattern:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  file_has_no_source_contract:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  file_missing_safety_labels:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  export_file_generates_report:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  export_file_exports_diagnosis_or_action:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  export_file_generates_patient_summary:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  export_file_generates_mdd_consensus:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  detector_file_claims_clinical_validation:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  red_team_file_allows_unsafe_reuse:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  red_team_file_contains_clinical_safe_phrase_template:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  red_team_file_claims_validation_or_readiness:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_export_block_file_allows_override:
    result: reject_file
    repair_required: true
    audit_stub_required: true
```

File fail-closed rule:

> Unsafe export/red-team files must be rejected before they can normalize clinical output or unsafe reuse.

---

## 28. File Repair Rules

Repair is allowed only as scaffold safety repair.

Allowed repair actions:

- rename unsafe export preview file,
- remove blocked export preview file,
- remove report-generation language,
- remove diagnosis/action export language,
- remove patient summary export language,
- remove MDD consensus export language,
- rename unsafe red-team file,
- remove reusable unsafe output language,
- remove clinical safe phrase template language,
- remove validation/readiness claim,
- restore source contract mapping,
- restore safety labels,
- restore authority envelope,
- restore no-decision object,
- restore copy/export block,
- restore quarantine display,
- restore audit binding,
- update validation checklist.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- report correction,
- patient communication correction,
- clinical validation correction,
- performance correction,
- product readiness correction,
- public readiness correction.

File repair rule:

> Export/red-team file repair fixes scaffold containment only.

---

## 29. File Validation Checklist

v0.17.6 validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| EXPORT_RT_CHECK_001 | export preview file object schema defined | true |
| EXPORT_RT_CHECK_002 | red-team file object schema defined | true |
| EXPORT_RT_CHECK_003 | allowed export preview file types defined | true |
| EXPORT_RT_CHECK_004 | blocked export preview file types defined | true |
| EXPORT_RT_CHECK_005 | allowed red-team file types defined | true |
| EXPORT_RT_CHECK_006 | blocked red-team file types defined | true |
| EXPORT_RT_CHECK_007 | allowed export preview file registry defined | true |
| EXPORT_RT_CHECK_008 | blocked export preview file registry defined | true |
| EXPORT_RT_CHECK_009 | allowed red-team file registry defined | true |
| EXPORT_RT_CHECK_010 | blocked red-team file registry defined | true |
| EXPORT_RT_CHECK_011 | export preview file naming defined | true |
| EXPORT_RT_CHECK_012 | red-team file naming defined | true |
| EXPORT_RT_CHECK_013 | export/red-team-to-folder mapping defined | true |
| EXPORT_RT_CHECK_014 | export/red-team source contract mapping defined | true |
| EXPORT_RT_CHECK_015 | export/red-team safety labels defined | true |
| EXPORT_RT_CHECK_016 | export/red-team README requirements defined | true |
| EXPORT_RT_CHECK_017 | detector file boundary defined | true |
| EXPORT_RT_CHECK_018 | export preview state machine boundary defined | true |
| EXPORT_RT_CHECK_019 | red-team quarantine file boundary defined | true |
| EXPORT_RT_CHECK_020 | copy/export block file boundary defined | true |
| EXPORT_RT_CHECK_021 | repair/revalidation file boundary defined | true |
| EXPORT_RT_CHECK_022 | audit binding boundary defined | true |
| EXPORT_RT_CHECK_023 | file fail-closed conditions defined | true |
| EXPORT_RT_CHECK_024 | file repair rules defined | true |
| EXPORT_RT_CHECK_025 | no clinical report generator files allowed | true |
| EXPORT_RT_CHECK_026 | no diagnosis/action exporter files allowed | true |
| EXPORT_RT_CHECK_027 | no patient summary exporter files allowed | true |
| EXPORT_RT_CHECK_028 | no MDD consensus exporter files allowed | true |
| EXPORT_RT_CHECK_029 | no reusable unsafe red-team output files allowed | true |
| EXPORT_RT_CHECK_030 | no clinical safe phrase template files allowed | true |
| EXPORT_RT_CHECK_031 | detector files are not clinical validators | true |
| EXPORT_RT_CHECK_032 | repair/revalidation remains UI safety only | true |

Validation rule:

> v0.17.6 validation passes only if export preview files cannot generate reports and red-team files cannot become reusable unsafe output.

---

## 30. v0.17.6 Acceptance Criteria

v0.17.6 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| allowed export preview file registry defined | true |
| blocked export preview file registry defined | true |
| allowed red-team file registry defined | true |
| blocked red-team file registry defined | true |
| export preview file naming defined | true |
| red-team file naming defined | true |
| export/red-team-to-folder mapping defined | true |
| export/red-team source contract mapping defined | true |
| export/red-team file safety labels defined | true |
| export/red-team README requirements defined | true |
| detector file boundary defined | true |
| quarantine file boundary defined | true |
| copy/export block file boundary defined | true |
| repair/revalidation file boundary defined | true |
| export/red-team audit binding file boundary defined | true |
| export/red-team fail-closed conditions defined | true |
| export/red-team repair rules defined | true |
| export/red-team validation checklist defined | true |
| no clinical report generator file opened | true |
| no impression generator file opened | true |
| no diagnosis exporter file opened | true |
| no treatment/order/procedure/follow-up/triage exporter file opened | true |
| no patient summary exporter file opened | true |
| no MDD consensus exporter file opened | true |
| no reusable unsafe output file opened | true |
| no clinical safe phrase template file opened | true |
| no validated red-team output file opened | true |
| export preview file is not clinical report generator | true |
| red-team file is not reusable unsafe output | true |
| detector file is not clinical validator | true |
| quarantine file is not phrase library | true |
| public_ready remains false | true |
| product_ready remains false | true |
| clinical_validation remains not_opened | true |
| diagnostic_authority remains none | true |
| treatment_authority remains none | true |

v0.17.6 acceptance rule:

> The export preview/red-team stub file scaffold plan is accepted only if local export files cannot become clinical report generators and local red-team files cannot become reusable unsafe output.

---

## 31. Next Step

The next recommended step is:

- v0.17.7 — Local Scaffold Validation Checklist

v0.17.7 should define:

- local scaffold-wide validation checklist,
- folder namespace validation,
- route/screen file validation,
- synthetic fixture file validation,
- UI copy file validation,
- fail-closed/audit file validation,
- export/red-team file validation,
- no real patient data file validation,
- no DICOM/report/PACS/EHR file validation,
- no clinical validation/performance file validation,
- no diagnosis/action file validation,
- no patient-facing/MDD replacement file validation,
- source-governed local file traceability validation,
- v0.17 pre-seal local scaffold safety gate.

v0.17.7 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 32. Governance Statement

This document defines the export preview and red-team stub file scaffold plan.

It opens export preview and red-team file scaffold planning only.

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

The v0.17.6 governance discipline is:

> “Do not let export files become clinical report generators and do not let red-team files become reusable unsafe output.”

The export/red-team scaffold discipline is:

> “Safe preview is allowed; containment is allowed; clinical output is not.”