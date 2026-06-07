# ILD Reasoning Platform — UI Copy Registry File Scaffold Plan v1

Version: v0.17.4  
Status: ui_copy_registry_file_scaffold_plan  
Scope: Allowed UI copy registry file registry, blocked UI copy file registry, safety language file naming, route copy mapping file naming, screen copy mapping file naming, component copy mapping file naming, blocked phrase registry file naming, disabled control copy file naming, fail-closed copy file naming, export/red-team copy file naming, copy-to-folder mapping, copy source contract mapping, copy file safety labels, copy README requirement, copy file fail-closed conditions, copy repair file boundary, copy audit stub requirements, and copy validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.17.4 — UI Copy Registry File Scaffold Plan.

v0.17.4 translates the sealed UI copy source mapping and local folder namespace into a concrete UI copy registry file scaffold plan for the local internal prototype.

This document does not implement a clinical product.

It does not create clinical language.

It does not create a diagnosis phrase library.

It does not create a treatment recommendation library.

It does not create order templates.

It does not create procedure recommendation templates.

It does not create follow-up scheduling templates.

It does not create triage wording.

It does not create patient-facing copy.

It does not create clinical validation claims.

It does not create diagnostic performance claims.

It does not create product marketing claims.

It does not create MDD consensus copy.

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

Its purpose is to define which local UI copy files may exist under `prototype/copy/`, what they may contain, which source contracts they trace to, and which copy files must remain blocked because they imply diagnosis, treatment, ordering, procedure decision, follow-up, triage, patient-facing output, clinical validation, product readiness, public readiness, or MDD replacement.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.17.4 copy file principle is:

> “A copy file may teach boundaries, but it must not become a clinical language library.”

The v0.17.4 blocked phrase principle is:

> “A blocked phrase registry may detect unsafe language, but it must not become a reusable unsafe phrase bank.”

---

## 2. Relationship to v0.17.0–v0.17.3

v0.17.4 inherits:

- v0.17.0 — Local Prototype File / Folder Scaffold Entry Gate,
- v0.17.1 — Prototype Folder Namespace / Blocked Folder Registry,
- v0.17.2 — Route File / Screen File Scaffold Plan,
- v0.17.3 — Synthetic Fixture File Scaffold Plan.

v0.17.0 opened local file/folder scaffold planning.

v0.17.1 defined the allowed local folder namespace and blocked folder registry.

v0.17.2 defined route and screen file scaffold planning.

v0.17.3 defined synthetic fixture file scaffold planning.

v0.17.4 defines UI copy registry file scaffold planning under:

```text
prototype/copy/
```

v0.17.4 does not broaden v0.17.0–v0.17.3.

v0.17.4 must not open:

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

> v0.17.4 may define local UI copy files only for source-governed safety language, not clinical language.

---

## 3. Global Authority Envelope

Every UI copy file, copy registry file, copy ID, copy string, copy metadata object, copy mapping file, blocked phrase file, copy repair rule file, copy folder mapping, copy validation row, copy README note, and copy implementation note must preserve the following authority envelope.

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

No copy file may imply an exception to this envelope.

Authority copy file rule:

> A UI copy file cannot grant clinical authority by using clinical-sounding language.

---

## 4. Global No-Decision Object

The no-decision object must remain visible or referenceable in decision-adjacent copy files.

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

- safety language core file,
- route copy mapping file,
- screen copy mapping file,
- component copy mapping file,
- disabled control copy mapping file,
- fail-closed copy mapping file,
- export preview copy mapping file,
- red-team quarantine copy mapping file,
- audit trace copy mapping file,
- copy repair rule file.

No-decision copy file rule:

> Copy files must say what the platform does not decide before users infer clinical action.

---

## 5. UI Copy File Object Schema

Every allowed UI copy file must conform to the following schema.

```yaml
ui_copy_file_scaffold:
  copy_file_id: string
  version: v0.17.4
  file_path: string
  copy_file_type: enum
  copy_file_title: string
  parent_folder: "prototype/copy/"
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
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  allowed_copy_classes: list
  blocked_copy_classes: list
  required_safety_labels: list
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
  allowed_bindings: list
  blocked_bindings: list
  fail_closed_conditions: list
```

Copy file rule:

> A copy file is allowed only if it stores source-governed safety language or unsafe-language blocking logic.

---

## 6. UI Copy Registry File Schema

The UI copy registry file must conform to the following schema.

```yaml
ui_copy_registry_file:
  registry_file_id: UI_COPY_REGISTRY_FILE_001
  version: v0.17.4
  file_path: "prototype/copy/ui_copy_registry.json"
  registry_scope: source_governed_internal_demo_safety_copy_only
  source_contract_version: string
  source_contract_file: string
  allowed_copy_files: list
  blocked_copy_files: list
  clinical_copy_allowed: false
  diagnosis_copy_allowed: false
  treatment_copy_allowed: false
  order_copy_allowed: false
  procedure_copy_allowed: false
  follow_up_copy_allowed: false
  triage_copy_allowed: false
  patient_facing_copy_allowed: false
  clinical_validation_claim_allowed: false
  diagnostic_performance_claim_allowed: false
  product_marketing_claim_allowed: false
  public_ready_claim_allowed: false
  mdd_consensus_copy_allowed: false
  authority_effect: none
  decision_effect: none
  required_authority_envelope: true
  required_no_decision_object: conditional_required
  required_audit_stub: true
```

Copy registry rule:

> The UI copy registry organizes safety language; it is not a clinical phrase library.

---

## 7. Allowed UI Copy File Types

The following UI copy file types are allowed.

| Copy File Type | Allowed Meaning |
|---|---|
| ui_copy_registry_file | central source-governed copy registry |
| safety_language_core_file | core boundary copy |
| route_copy_mapping_file | route-level safety copy mapping |
| screen_copy_mapping_file | screen-level safety copy mapping |
| component_copy_mapping_file | component-level safety copy mapping |
| disabled_control_copy_mapping_file | disabled control boundary copy |
| fail_closed_copy_mapping_file | fail-closed explanation copy |
| export_preview_copy_mapping_file | safe export preview copy |
| red_team_quarantine_copy_mapping_file | red-team containment copy |
| visual_safety_copy_file | visual safety label copy |
| authority_envelope_copy_file | authority envelope copy |
| no_decision_object_copy_file | no-decision copy |
| missing_evidence_copy_file | missing evidence limiter copy |
| mimic_visibility_copy_file | mimic visibility boundary copy |
| overlap_copy_file | overlap boundary copy |
| source_status_copy_file | source status limiter copy |
| confidence_limiter_copy_file | confidence limiter copy |
| review_prompt_copy_file | review prompt boundary copy |
| audit_trace_copy_file | audit trace boundary copy |
| blocked_phrase_registry_file | unsafe phrase detection registry |
| copy_repair_rules_file | UI safety copy repair rules |

Allowed copy type rule:

> Allowed copy files explain boundaries, limitations, containment, traceability, and safety only.

---

## 8. Blocked UI Copy File Types

The following UI copy file types are blocked.

| Blocked Copy File Type | Reason |
|---|---|
| diagnosis_phrase_file | diagnostic authority blocked |
| final_diagnosis_copy_file | diagnostic closure blocked |
| likely_diagnosis_copy_file | ranking/probability blocked |
| disease_probability_copy_file | probability display blocked |
| rule_out_copy_file | exclusion authority blocked |
| mimic_confirmation_copy_file | diagnostic authority blocked |
| mimic_exclusion_copy_file | exclusion authority blocked |
| treatment_recommendation_copy_file | treatment authority blocked |
| order_template_copy_file | test-order authority blocked |
| procedure_recommendation_copy_file | procedure authority blocked |
| follow_up_template_copy_file | follow-up authority blocked |
| triage_copy_file | triage authority blocked |
| disposition_copy_file | triage/disposition blocked |
| patient_summary_copy_file | patient-facing use blocked |
| clinical_validation_claim_copy_file | clinical validation not opened |
| diagnostic_performance_copy_file | diagnostic performance claim blocked |
| product_marketing_claim_copy_file | product readiness false |
| public_launch_copy_file | public readiness false |
| mdd_consensus_copy_file | MDD replacement blocked |
| expert_equivalence_copy_file | expert replacement risk |

Blocked copy type rule:

> If a copy file sounds like clinical conclusion, action, validation, readiness, patient-facing material, or MDD outcome, it is blocked.

---

## 9. Allowed UI Copy File Registry

The following UI copy files are allowed.

| Copy File ID | File Path | Copy File Type |
|---|---|---|
| COPY_FILE_001 | `prototype/copy/ui_copy_registry.json` | ui_copy_registry_file |
| COPY_FILE_002 | `prototype/copy/safety_language_core.json` | safety_language_core_file |
| COPY_FILE_003 | `prototype/copy/route_copy_mapping.json` | route_copy_mapping_file |
| COPY_FILE_004 | `prototype/copy/screen_copy_mapping.json` | screen_copy_mapping_file |
| COPY_FILE_005 | `prototype/copy/component_copy_mapping.json` | component_copy_mapping_file |
| COPY_FILE_006 | `prototype/copy/disabled_control_copy_mapping.json` | disabled_control_copy_mapping_file |
| COPY_FILE_007 | `prototype/copy/fail_closed_copy_mapping.json` | fail_closed_copy_mapping_file |
| COPY_FILE_008 | `prototype/copy/export_preview_copy_mapping.json` | export_preview_copy_mapping_file |
| COPY_FILE_009 | `prototype/copy/red_team_quarantine_copy_mapping.json` | red_team_quarantine_copy_mapping_file |
| COPY_FILE_010 | `prototype/copy/visual_safety_copy.json` | visual_safety_copy_file |
| COPY_FILE_011 | `prototype/copy/authority_envelope_copy.json` | authority_envelope_copy_file |
| COPY_FILE_012 | `prototype/copy/no_decision_object_copy.json` | no_decision_object_copy_file |
| COPY_FILE_013 | `prototype/copy/missing_evidence_copy.json` | missing_evidence_copy_file |
| COPY_FILE_014 | `prototype/copy/mimic_visibility_copy.json` | mimic_visibility_copy_file |
| COPY_FILE_015 | `prototype/copy/overlap_copy.json` | overlap_copy_file |
| COPY_FILE_016 | `prototype/copy/source_status_copy.json` | source_status_copy_file |
| COPY_FILE_017 | `prototype/copy/confidence_limiter_copy.json` | confidence_limiter_copy_file |
| COPY_FILE_018 | `prototype/copy/review_prompt_copy.json` | review_prompt_copy_file |
| COPY_FILE_019 | `prototype/copy/audit_trace_copy.json` | audit_trace_copy_file |
| COPY_FILE_020 | `prototype/copy/blocked_phrase_registry.json` | blocked_phrase_registry_file |
| COPY_FILE_021 | `prototype/copy/copy_repair_rules.json` | copy_repair_rules_file |

Allowed copy registry rule:

> Allowed copy files must remain under `prototype/copy/` and must store only safety-governed language or unsafe-language blocking logic.

---

## 10. Blocked UI Copy File Registry

The following UI copy files are blocked.

```text
prototype/copy/diagnosis_phrases.json
prototype/copy/final_diagnosis_copy.json
prototype/copy/likely_diagnosis_copy.json
prototype/copy/disease_probability_copy.json
prototype/copy/diagnosis_ranking_copy.json
prototype/copy/rule_out_copy.json
prototype/copy/mimic_confirmation_copy.json
prototype/copy/mimic_exclusion_copy.json
prototype/copy/treatment_recommendations.json
prototype/copy/therapy_recommendations.json
prototype/copy/order_templates.json
prototype/copy/test_order_templates.json
prototype/copy/procedure_recommendations.json
prototype/copy/follow_up_templates.json
prototype/copy/follow_up_scheduler_copy.json
prototype/copy/triage_copy.json
prototype/copy/disposition_copy.json
prototype/copy/patient_summary_copy.json
prototype/copy/patient_facing_copy.json
prototype/copy/clinical_validation_claims.json
prototype/copy/diagnostic_performance_claims.json
prototype/copy/accuracy_claims.json
prototype/copy/sensitivity_specificity_claims.json
prototype/copy/auc_claims.json
prototype/copy/product_marketing_claims.json
prototype/copy/product_ready_copy.json
prototype/copy/public_ready_copy.json
prototype/copy/public_launch_copy.json
prototype/copy/mdd_consensus_copy.json
prototype/copy/expert_equivalence_copy.json
```

Blocked copy registry rule:

> Blocked copy files may not exist because their names imply clinical language, action, validation, readiness, or patient-facing use.

---

## 11. UI Copy File Naming Convention

Allowed copy file naming patterns:

```yaml
allowed_copy_file_naming:
  central_registry: "ui_copy_registry.json"
  core_safety: "safety_language_core.json"
  route_mapping: "route_copy_mapping.json"
  screen_mapping: "screen_copy_mapping.json"
  component_mapping: "component_copy_mapping.json"
  disabled_control_mapping: "disabled_control_copy_mapping.json"
  fail_closed_mapping: "fail_closed_copy_mapping.json"
  export_preview_mapping: "export_preview_copy_mapping.json"
  red_team_quarantine_mapping: "red_team_quarantine_copy_mapping.json"
  visual_safety: "visual_safety_copy.json"
  authority_envelope: "authority_envelope_copy.json"
  no_decision_object: "no_decision_object_copy.json"
  missing_evidence: "missing_evidence_copy.json"
  mimic_visibility: "mimic_visibility_copy.json"
  overlap: "overlap_copy.json"
  source_status: "source_status_copy.json"
  confidence_limiter: "confidence_limiter_copy.json"
  review_prompt: "review_prompt_copy.json"
  audit_trace: "audit_trace_copy.json"
  blocked_phrases: "blocked_phrase_registry.json"
  copy_repair: "copy_repair_rules.json"
```

Blocked copy file naming terms:

- diagnosis,
- final_diagnosis,
- likely_diagnosis,
- probability,
- ranking,
- rule_out,
- exclude,
- excluded,
- confirmed,
- treatment,
- therapy,
- order,
- procedure,
- follow_up,
- triage,
- disposition,
- patient_summary,
- patient_facing,
- clinical_validation,
- performance,
- accuracy,
- sensitivity,
- specificity,
- AUC,
- product_ready,
- public_ready,
- public_launch,
- marketing_claims,
- MDD_consensus,
- expert_equivalence.

Copy naming rule:

> Copy file names must signal safety boundary language, not clinical content.

---

## 12. Copy-to-Folder Mapping

All allowed UI copy files must live only in:

```text
prototype/copy/
```

Allowed mapping:

| Copy File Category | Folder |
|---|---|
| central copy registry | `prototype/copy/` |
| safety language core | `prototype/copy/` |
| route copy mapping | `prototype/copy/` |
| screen copy mapping | `prototype/copy/` |
| component copy mapping | `prototype/copy/` |
| disabled control copy | `prototype/copy/` |
| fail-closed copy | `prototype/copy/` |
| export preview copy | `prototype/copy/` |
| red-team quarantine copy | `prototype/copy/` |
| blocked phrase registry | `prototype/copy/` |
| copy repair rules | `prototype/copy/` |

Blocked mapping:

- copy files under patient folders,
- copy files under clinical folders,
- copy files under diagnosis/action folders,
- copy files under validation/performance folders,
- copy files under product/public folders,
- copy files under MDD consensus folders,
- copy files outside `prototype/copy/` without source mapping.

Copy-to-folder rule:

> UI copy files may exist only inside the safe local copy namespace.

---

## 13. Copy Source Contract Mapping

Every allowed copy file must map to source contracts.

| Copy File Group | Source Contracts |
|---|---|
| UI copy registry | v0.16.3; v0.17.0 |
| safety language core | v0.15.5; v0.16.3; v0.16.8 |
| route copy mapping | v0.16.1; v0.16.3; v0.17.2 |
| screen copy mapping | v0.15.1; v0.16.3; v0.17.2 |
| component copy mapping | v0.15.1; v0.16.3 |
| disabled control copy mapping | v0.16.4; v0.16.3 |
| fail-closed copy mapping | v0.16.4; v0.16.3 |
| export preview copy mapping | v0.13; v0.15.4; v0.16.6 |
| red-team quarantine copy mapping | v0.14; v0.15.4; v0.16.6 |
| visual safety copy | v0.14; v0.15.3; v0.16.3 |
| authority envelope copy | v0.15.5; v0.16.8 |
| no-decision object copy | v0.15.5; v0.16.8 |
| missing evidence copy | v0.11; v0.15.3; v0.16.3 |
| mimic visibility copy | v0.11; v0.15.3; v0.16.3 |
| overlap copy | v0.12; v0.15.3; v0.16.3 |
| source status copy | v0.11; v0.16.3 |
| confidence limiter copy | v0.9; v0.16.3 |
| review prompt copy | v0.10; v0.16.3 |
| audit trace copy | v0.16.5; v0.16.3 |
| blocked phrase registry | v0.16.3; v0.16.4 |
| copy repair rules | v0.16.3; v0.16.4 |

Source mapping rule:

> Copy files without sealed source contract mapping are blocked.

---

## 14. Copy File Safety Labels

Every copy file must include or reference safety labels.

```yaml
required_copy_file_safety_labels:
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  clinical_language_allowed: false
  diagnosis_copy_allowed: false
  treatment_copy_allowed: false
  order_copy_allowed: false
  procedure_copy_allowed: false
  follow_up_copy_allowed: false
  triage_copy_allowed: false
  clinical_validation_claim_allowed: false
  diagnostic_performance_claim_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  decision_effect: none
  mdd_replacement: not_allowed
```

Copy safety label rule:

> A copy file cannot be considered safe if its non-clinical safety labels are missing.

---

## 15. Copy README Requirement

The copy folder should include:

```text
prototype/copy/README.md
```

Required copy README statements:

```text
This folder contains source-governed UI safety copy files only.
Copy files are not clinical language libraries.
Copy files are not diagnosis phrase libraries.
Copy files are not treatment recommendation libraries.
Copy files are not order templates.
Copy files are not procedure recommendation templates.
Copy files are not follow-up scheduling templates.
Copy files are not triage wording.
Copy files are not patient-facing material.
Copy files are not clinical validation claims.
Copy files are not product or public readiness claims.
Blocked phrase registries detect unsafe language; they are not reusable phrase banks.
Copy repair rules fix UI safety wording only; they are not clinical correction.
```

Copy README rule:

> Copy folder boundary text must prevent safety language files from being read as clinical phrase libraries.

---

## 16. Safety Language Core File Boundary

The safety language core file may include:

- Synthetic demo only.
- Not for clinical use.
- Not patient-facing.
- Public ready: false.
- Product ready: false.
- Clinical validation: not opened.
- No diagnosis generated.
- No treatment selected.
- No tests ordered.
- No procedures decided.
- No follow-up scheduled.
- No triage assigned.
- MDD preparation preview is not MDD consensus.
- Audit trace explains UI state, not medical correctness.

The safety language core file may not include:

- diagnostic impression,
- final diagnosis,
- likely diagnosis,
- disease probability,
- ruled out,
- excluded,
- treatment recommendation,
- test order,
- procedure recommendation,
- follow-up interval,
- triage status,
- patient summary,
- clinically validated,
- product ready,
- public ready,
- MDD consensus.

Safety language core rule:

> Core safety language must be plain boundary language, not softened clinical language.

---

## 17. Route / Screen / Component Copy Mapping Boundary

Route, screen, and component copy mapping files may include mappings for:

- prototype boundary copy,
- synthetic case selector copy,
- demo intake review copy,
- reasoning map safety copy,
- missing evidence limiter copy,
- mimic visibility boundary copy,
- overlap unresolved copy,
- source status limiter copy,
- confidence limiter copy,
- review prompt boundary copy,
- safe export preview boundary copy,
- red-team quarantine copy,
- authority envelope copy,
- no-decision object copy,
- audit trace boundary copy,
- visual safety label copy.

They may not include mappings for:

- final diagnosis screens,
- diagnosis probability dashboards,
- treatment screens,
- order screens,
- procedure screens,
- follow-up scheduler screens,
- triage screens,
- patient summary screens,
- clinical validation dashboards,
- product/public readiness screens,
- MDD consensus screens.

Route/screen/component copy rule:

> Mapping files may attach safety copy to safe UI surfaces only.

---

## 18. Disabled Control Copy File Boundary

The disabled control copy mapping file may include explanations for:

- upload real patient data disabled,
- upload deidentified patient data disabled,
- import DICOM disabled,
- import HRCT disabled,
- paste real report disabled,
- connect PACS disabled,
- connect EHR disabled,
- generate diagnosis disabled,
- rank diagnoses disabled,
- rule out disease disabled,
- confirm or exclude mimic disabled,
- recommend treatment disabled,
- order test disabled,
- recommend procedure disabled,
- schedule follow-up disabled,
- assign triage disabled,
- generate patient summary disabled,
- mark clinically validated disabled,
- mark product ready disabled,
- publish public demo disabled,
- generate MDD consensus disabled.

The disabled control copy mapping file may not include:

- coming soon clinical mode,
- unlock diagnosis,
- enable treatment recommendations,
- connect PACS soon,
- upload patients later,
- start validation soon,
- product version available,
- clinical mode roadmap copy.

Disabled control copy rule:

> Disabled control copy must close unsafe authority, not advertise future clinical capability.

---

## 19. Fail-Closed Copy File Boundary

The fail-closed copy mapping file may include explanations for:

- unsafe route blocked,
- real patient data blocked,
- deidentified real patient data blocked,
- DICOM/HRCT import blocked,
- real report import blocked,
- PACS/EHR connection blocked,
- diagnosis/ranking/exclusion language blocked,
- clinical action language blocked,
- patient-facing output blocked,
- validation/performance overclaim blocked,
- product/public readiness overclaim blocked,
- MDD replacement blocked,
- unsafe copy/export blocked,
- authority envelope missing blocked,
- no-decision object missing blocked,
- unsafe visual semantics blocked,
- unsafe fixture binding blocked,
- audit correctness claim blocked.

The fail-closed copy mapping file may not include:

- soft warnings that allow continuation,
- hidden override language,
- admin bypass language,
- clinical unlock language,
- “proceed anyway” clinical language,
- “use at your own risk” clinical language.

Fail-closed copy rule:

> Fail-closed copy must explain blocked authority and stop unsafe behavior.

---

## 20. Export Preview Copy File Boundary

The export preview copy mapping file may include:

- export preview is not a clinical report,
- MDD preparation preview is not MDD consensus,
- no diagnosis generated,
- no disease or mimic excluded,
- no treatment selected,
- no tests ordered,
- no procedures decided,
- no follow-up scheduled,
- no triage assigned,
- patient-facing output is not generated,
- clinical validation is not opened,
- audit references explain UI state only.

The export preview copy mapping file may not include:

- impression,
- diagnosis,
- final diagnosis,
- diagnostic conclusion,
- recommended treatment,
- order,
- biopsy required,
- follow-up in,
- safe outpatient,
- patient summary,
- MDD consensus,
- clinically validated,
- product ready,
- public ready.

Export preview copy rule:

> Export copy may preserve safe structure; it may not become report wording.

---

## 21. Red-Team Quarantine Copy File Boundary

The red-team quarantine copy mapping file may include:

- blocked unsafe example,
- not reusable clinical output,
- displayed only to demonstrate fail-closed behavior,
- not advice,
- not diagnosis,
- not exclusion,
- not treatment,
- not an order,
- not a procedure decision,
- not follow-up,
- not triage,
- not patient-facing material,
- not clinical validation,
- not MDD consensus,
- copy and export disabled.

The red-team quarantine copy mapping file may not include:

- use this instead,
- suggested clinical wording,
- clinically safe phrase,
- validated safe output,
- product-safe output,
- public-ready output,
- copyable unsafe example,
- exportable unsafe example.

Red-team copy rule:

> Red-team copy demonstrates containment, not replacement language.

---

## 22. Blocked Phrase Registry File Boundary

The blocked phrase registry file may contain blocked terms only for detection and fail-closed behavior.

Allowed blocked phrase registry use:

- detect diagnostic language,
- detect probability/ranking language,
- detect exclusion language,
- detect treatment language,
- detect order language,
- detect procedure language,
- detect follow-up language,
- detect triage language,
- detect patient-facing language,
- detect validation claims,
- detect performance claims,
- detect readiness claims,
- detect MDD consensus claims.

Blocked blocked-phrase registry use:

- reusable unsafe phrase bank,
- clinical phrase suggestion bank,
- report-writing assistance,
- diagnosis wording assistance,
- treatment wording assistance,
- order template suggestion,
- patient summary wording,
- validation claim wording.

Blocked phrase registry rule:

> Blocked phrases may be stored for detection only, not for reuse.

---

## 23. Copy Repair Rules File Boundary

The copy repair rules file may define UI safety repair only.

Allowed repair actions:

- replace clinical heading with governance heading,
- replace diagnosis phrase with visibility phrase,
- replace exclusion phrase with missingness/visibility limiter,
- replace treatment phrase with authority boundary,
- replace order phrase with no-order boundary,
- replace procedure phrase with no-procedure boundary,
- replace follow-up phrase with no-follow-up boundary,
- replace triage phrase with no-triage boundary,
- replace validation phrase with UI safety boundary,
- replace readiness phrase with public_ready/product_ready false boundary,
- restore authority envelope copy,
- restore no-decision copy.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- probability recalculation,
- performance correction,
- clinical validation,
- product readiness approval,
- public readiness approval.

Copy repair rule:

> Copy repair fixes unsafe UI wording, not medical content.

---

## 24. Copy File Fail-Closed Conditions

Copy file planning must fail closed under the following conditions.

```yaml
copy_file_fail_closed_conditions:
  copy_file_name_matches_blocked_registry:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_name_matches_blocked_pattern:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_has_no_source_contract:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_missing_safety_labels:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_diagnostic_language:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_exclusion_language:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_treatment_order_procedure_followup_triage_language:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_patient_facing_language:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_validation_or_performance_claim:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_product_or_public_ready_claim:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  copy_file_contains_mdd_consensus_language:
    result: reject_file
    repair_required: true
    audit_stub_required: true
  blocked_phrase_registry_used_as_reusable_phrase_bank:
    result: reject_file
    repair_required: true
    audit_stub_required: true
```

Copy fail-closed rule:

> Unsafe copy files must be rejected before unsafe language can become UI text.

---

## 25. Copy File Repair Rules

Repair is allowed only as scaffold safety repair.

Allowed repair actions:

- rename unsafe copy file,
- remove blocked copy file,
- remove diagnostic language,
- remove exclusion language,
- remove treatment/order/procedure/follow-up/triage language,
- remove patient-facing language,
- remove validation/performance claims,
- remove product/public readiness claims,
- remove MDD consensus language,
- restore source contract mapping,
- restore safety labels,
- restore authority envelope,
- restore no-decision object,
- restore blocked phrase detection-only status,
- restore audit stub reference,
- update copy validation checklist.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- patient communication correction,
- clinical validation correction,
- performance correction,
- product readiness correction,
- public readiness correction.

Copy file repair rule:

> Copy file repair fixes scaffold safety language only.

---

## 26. Copy Audit Stub Requirement

Copy file planning should be audit-stub traceable in future implementation.

Allowed copy audit events:

- copy_file_registered,
- copy_file_rejected,
- copy_source_mapping_verified,
- copy_safety_label_verified,
- safety_copy_loaded,
- copy_mapping_bound,
- blocked_copy_file_detected,
- unsafe_copy_language_detected,
- blocked_phrase_detected,
- copy_repair_required,
- copy_repair_applied,
- copy_validation_passed,
- copy_validation_failed.

Audit fields:

```yaml
copy_file_audit_stub:
  event_id: string
  event_type: string
  file_path: string
  copy_file_type: optional
  source_contract: string
  event_result: enum(registered, rejected, verified, loaded, bound, repair_required, repaired, failed)
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Copy audit rule:

> Copy audit records safety-language traceability, not clinical correctness.

---

## 27. Copy Validation Checklist

v0.17.4 copy validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| COPY_FILE_CHECK_001 | UI copy file object schema defined | true |
| COPY_FILE_CHECK_002 | UI copy registry file schema defined | true |
| COPY_FILE_CHECK_003 | allowed UI copy file types defined | true |
| COPY_FILE_CHECK_004 | blocked UI copy file types defined | true |
| COPY_FILE_CHECK_005 | allowed UI copy file registry defined | true |
| COPY_FILE_CHECK_006 | blocked UI copy file registry defined | true |
| COPY_FILE_CHECK_007 | UI copy file naming convention defined | true |
| COPY_FILE_CHECK_008 | copy-to-folder mapping defined | true |
| COPY_FILE_CHECK_009 | copy source contract mapping defined | true |
| COPY_FILE_CHECK_010 | copy file safety labels defined | true |
| COPY_FILE_CHECK_011 | copy README requirement defined | true |
| COPY_FILE_CHECK_012 | safety language core boundary defined | true |
| COPY_FILE_CHECK_013 | route/screen/component copy mapping boundary defined | true |
| COPY_FILE_CHECK_014 | disabled control copy boundary defined | true |
| COPY_FILE_CHECK_015 | fail-closed copy boundary defined | true |
| COPY_FILE_CHECK_016 | export preview copy boundary defined | true |
| COPY_FILE_CHECK_017 | red-team quarantine copy boundary defined | true |
| COPY_FILE_CHECK_018 | blocked phrase registry boundary defined | true |
| COPY_FILE_CHECK_019 | copy repair rules boundary defined | true |
| COPY_FILE_CHECK_020 | copy fail-closed conditions defined | true |
| COPY_FILE_CHECK_021 | copy repair rules defined | true |
| COPY_FILE_CHECK_022 | copy audit stub requirement defined | true |
| COPY_FILE_CHECK_023 | no diagnosis copy files allowed | true |
| COPY_FILE_CHECK_024 | no treatment/order/procedure/follow-up/triage copy files allowed | true |
| COPY_FILE_CHECK_025 | no patient-facing copy files allowed | true |
| COPY_FILE_CHECK_026 | no clinical validation/performance copy files allowed | true |
| COPY_FILE_CHECK_027 | no product/public readiness copy files allowed | true |
| COPY_FILE_CHECK_028 | no MDD consensus copy files allowed | true |
| COPY_FILE_CHECK_029 | blocked phrase registry detection-only | true |
| COPY_FILE_CHECK_030 | copy repair means UI safety repair only | true |

Copy validation rule:

> Copy validation passes only if every copy file remains source-governed safety language and cannot become clinical wording.

---

## 28. v0.17.4 Acceptance Criteria

v0.17.4 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| allowed UI copy registry file registry defined | true |
| blocked UI copy file registry defined | true |
| safety language file naming defined | true |
| route copy mapping file naming defined | true |
| screen copy mapping file naming defined | true |
| component copy mapping file naming defined | true |
| blocked phrase registry file naming defined | true |
| disabled control copy file naming defined | true |
| fail-closed copy file naming defined | true |
| export/red-team copy file naming defined | true |
| copy-to-folder mapping defined | true |
| copy source contract mapping defined | true |
| copy file safety labels defined | true |
| copy README requirement defined | true |
| copy file fail-closed conditions defined | true |
| copy repair rules defined | true |
| copy audit stub requirement defined | true |
| copy validation checklist defined | true |
| no diagnosis copy file opened | true |
| no treatment recommendation copy file opened | true |
| no order/procedure/follow-up/triage copy file opened | true |
| no patient-facing copy file opened | true |
| no clinical validation/performance copy file opened | true |
| no product/public readiness copy file opened | true |
| no MDD consensus copy file opened | true |
| blocked phrase registry not reusable phrase bank | true |
| copy repair not clinical correction | true |
| public_ready remains false | true |
| product_ready remains false | true |
| clinical_validation remains not_opened | true |
| diagnostic_authority remains none | true |
| treatment_authority remains none | true |

v0.17.4 acceptance rule:

> The UI copy registry file scaffold plan is accepted only if local copy files cannot be mistaken for clinical language libraries, patient-facing material, validation claims, readiness claims, or reusable unsafe phrase banks.

---

## 29. Next Step

The next recommended step is:

- v0.17.5 — Fail-Closed / Audit Stub File Scaffold Plan

v0.17.5 should define:

- allowed fail-closed file registry,
- blocked fail-closed file registry,
- allowed audit stub file registry,
- blocked audit file registry,
- fail-closed file naming,
- audit file naming,
- disabled control file naming,
- fail-closed-to-folder mapping,
- audit-to-folder mapping,
- fail-closed/audit source contract mapping,
- fail-closed/audit file safety labels,
- fail-closed/audit README requirements,
- fail-closed/audit file validation checklist.

v0.17.5 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 30. Governance Statement

This document defines the UI copy registry file scaffold plan.

It opens UI copy file scaffold planning only.

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

The v0.17.4 governance discipline is:

> “Do not let copy files become clinical language libraries.”

The copy scaffold discipline is:

> “Safety copy teaches boundaries; blocked phrase registries detect unsafe language; neither may become clinical output.”
