# ILD Reasoning Platform — Source-Governed Prototype Build Scaffold Entry Gate v1

Version: v0.16.0  
Status: source_governed_prototype_build_scaffold_entry_gate  
Scope: Source-governed prototype build scaffold entry gate, internal demo implementation planning, contract-to-build traceability, allowed and blocked build surfaces, synthetic fixture only requirement, no real patient data guard, no DICOM/report import guard, no patient-facing route, no clinical validation route, no product/public readiness route, no diagnostic/treatment/order/procedure/follow-up/triage route, fail-closed implementation principle, audit stub implementation principle, safe export preview stub boundary, and red-team scenario stub boundary  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document opens v0.16 — Source-Governed Prototype Build Scaffold / Internal Demo Implementation Planning.

v0.16 translates the structurally sealed v0.15 prototype workspace UI behavior contract into an internal prototype build scaffold plan.

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
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define the entry gate for building an internal, source-governed, synthetic-only prototype scaffold from the contracts already sealed in v0.15.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16 entry principle is:

> “A prototype build scaffold may plan internal implementation, but it must not open clinical deployment.”

The v0.16 build discipline is:

> “Every route, screen, component, fixture, copy string, disabled control, audit stub, export preview stub, and red-team stub must trace back to a sealed source contract.”

---

## 2. Relationship to v0.15

v0.16 inherits the complete v0.15 structural chain:

- v0.15.0 — Prototype Workspace / Demo UI Behavior Contract Entry Gate,
- v0.15.1 — Demo Workspace Screen / Component Behavior Schema,
- v0.15.2 — Demo Case Selection / Synthetic Intake UI Flow,
- v0.15.3 — Reasoning Map / Guided Visual Reasoning Interaction Contract,
- v0.15.4 — Demo Export Preview / Red-Team Fail-Closed UI Behavior,
- v0.15.5 — Prototype Workspace Validation Checklist / UI Safety Gate,
- v0.15.6 — Prototype Workspace / Demo UI Behavior Structural Seal,
- checkpoint-v0.15.

v0.15 sealed what the prototype workspace may show and how it may behave.

v0.16 begins planning how that sealed behavior may be represented in an internal build scaffold.

v0.16 does not broaden v0.15.

v0.16 must not open:

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

Inheritance rule:

> v0.16 may scaffold only what v0.15 already allowed; it may not create new clinical capability.

---

## 3. Global Authority Envelope

Every v0.16 build scaffold object must inherit the following authority envelope.

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
  real_report_import: not_allowed
  pacs_connection: not_allowed
  ehr_connection: not_allowed
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

No route, screen scaffold, component scaffold, fixture registry, copy map, audit stub, export preview stub, red-team stub, validation stub, disabled control, state machine, navigation path, file name, folder name, or implementation note may override this envelope.

Authority scaffold rule:

> A build scaffold cannot grant authority that the sealed contract does not have.

---

## 4. Global No-Decision Object

The following no-decision object must remain active across the v0.16 scaffold.

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

The no-decision object must be represented in:

- route planning,
- screen planning,
- component planning,
- export preview planning,
- red-team fail-closed planning,
- audit event stub planning,
- validation checklist planning.

No-decision scaffold rule:

> The scaffold must plan how the prototype shows what it did not decide.

---

## 5. v0.16 Scope

v0.16 may define:

- source-governed prototype build scaffold scope,
- internal demo implementation boundary,
- contract-to-build traceability requirements,
- allowed internal prototype routes,
- blocked clinical routes,
- allowed screen scaffold registry,
- blocked screen scaffold registry,
- synthetic fixture registry planning,
- demo state binding planning,
- UI copy source mapping,
- safety language contract,
- disabled clinical control strategy,
- fail-closed state stub planning,
- audit event stub planning,
- safe export preview stub planning,
- red-team scenario stub planning,
- source-to-component traceability,
- validation checklist for scaffold safety,
- structural seal for build scaffold planning.

v0.16 may not define:

- real patient upload,
- deidentified patient upload,
- DICOM import,
- HRCT import,
- clinical report import,
- PACS connection,
- EHR connection,
- live clinical case workflow,
- diagnosis workflow,
- treatment workflow,
- order workflow,
- procedure workflow,
- follow-up workflow,
- triage workflow,
- patient-facing route,
- public launch route,
- product release route,
- clinical validation dashboard,
- diagnostic performance test workflow,
- MDD replacement workflow.

Scope rule:

> v0.16 is an internal scaffold planning phase, not a clinical implementation phase.

---

## 6. Source-Governed Implementation Principle

v0.16 introduces the source-governed implementation principle.

Every scaffold element must declare its source contract.

Required source-governed mapping:

```yaml
source_governed_scaffold_element:
  scaffold_element_id: string
  element_type: enum
  proposed_file_or_module: string
  source_contract_version: string
  source_contract_file: string
  source_section_or_rule: string
  allowed_behavior: string
  blocked_behavior: string
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Allowed source contracts:

- v0.15.0 entry gate,
- v0.15.1 screen/component behavior schema,
- v0.15.2 synthetic selection/intake UI flow,
- v0.15.3 reasoning map contract,
- v0.15.4 export preview/red-team fail-closed UI behavior,
- v0.15.5 UI safety gate,
- v0.15.6 structural seal,
- checkpoint-v0.15,
- earlier sealed contracts where needed.

Blocked source behavior:

- implementation without source contract,
- copy text without source mapping,
- route without source mapping,
- screen without source mapping,
- disabled control without blocked-authority reason,
- audit event without source interaction,
- export preview stub without safe export boundary,
- red-team stub without fail-closed rule.

Source-governed rule:

> No scaffold element may be planned as “just UI”; every element must trace to a sealed governance source.

---

## 7. Contract-to-Build Traceability Requirement

Every build scaffold item must be traceable.

Required traceability dimensions:

| Scaffold Item | Required Trace |
|---|---|
| route | source screen / flow contract |
| screen | source screen registry and safety rule |
| component | source component schema |
| fixture | source synthetic demo fixture contract |
| copy string | source safety language rule |
| disabled control | source blocked action / authority rule |
| fail-closed state | source fail-closed condition |
| audit event | source interaction / traceability rule |
| export preview stub | source safe export preview boundary |
| red-team stub | source red-team scenario rule |
| validation check | source acceptance criterion |

Traceability object:

```yaml
contract_to_build_trace:
  build_item_id: string
  build_item_type: enum
  source_version: string
  source_file: string
  source_rule: string
  implementation_intent: string
  allowed_output: string
  blocked_output: string
  safety_label_required: boolean
  authority_envelope_required: boolean
  no_decision_object_required: boolean
  audit_stub_required: boolean
```

Traceability rule:

> If a build item cannot name its source contract, it cannot enter the scaffold.

---

## 8. Allowed Build Surfaces

The following build surfaces may be planned in v0.16.

| Build Surface | Allowed Meaning |
|---|---|
| internal prototype route scaffold | route planning for synthetic demo only |
| prototype landing route | prototype boundary display |
| synthetic case selector route | sealed fictional case selection |
| synthetic intake review route | fictional supplied/missing field display |
| reasoning map route | guided visual reasoning map display |
| evidence panel routes | missing/mimic/overlap/source visibility |
| authority envelope component scaffold | non-authority display |
| no-decision component scaffold | explicit decision-block display |
| visual safety label component scaffold | visual meaning constraints |
| safe export preview route | non-diagnostic preview stub |
| red-team fail-closed route | unsafe behavior containment demo |
| audit trace route | UI traceability display |
| synthetic fixture registry | sealed demo fixture registry |
| UI copy map | source-governed safety language |
| disabled clinical control stubs | boundary-teaching disabled controls |
| fail-closed state stubs | unsafe state containment |
| validation checklist scaffold | UI safety validation planning |

Allowed surface rule:

> Allowed build surfaces exist to demonstrate sealed governance behavior internally.

---

## 9. Blocked Build Surfaces

The following build surfaces remain blocked.

| Blocked Build Surface | Reason |
|---|---|
| patient route | patient-facing use blocked |
| clinical route | clinical deployment blocked |
| real case upload route | real patient data blocked |
| deidentified case upload route | deidentified real patient data blocked |
| DICOM import route | imaging import blocked |
| HRCT viewer route | clinical image interpretation risk |
| PACS connector | clinical integration blocked |
| EHR connector | clinical integration blocked |
| report paste/import route | real report ingestion blocked |
| diagnosis route | diagnostic authority blocked |
| disease ranking route | ranking/probability blocked |
| disease rule-out route | exclusion authority blocked |
| treatment route | treatment authority blocked |
| order route | test-order authority blocked |
| procedure route | procedure authority blocked |
| follow-up route | follow-up authority blocked |
| triage route | triage authority blocked |
| patient summary route | patient-facing leak risk |
| clinical validation route | validation not opened |
| diagnostic performance dashboard | performance claim blocked |
| product readiness route | product_ready false |
| public launch route | public_ready false |
| MDD consensus route | MDD replacement blocked |

Blocked surface rule:

> A build surface is blocked if it would make the prototype behave like clinical software.

---

## 10. Internal Demo Build Boundary

v0.16 may plan an internal demo scaffold only.

Allowed internal demo properties:

```yaml
internal_demo_build_boundary:
  internal_demo_only: true
  synthetic_demo_only: true
  non_clinical: true
  patient_facing: false
  public_ready: false
  product_ready: false
  clinical_validation: not_opened
  real_patient_data_allowed: false
  deidentified_real_patient_data_allowed: false
  dicom_import_allowed: false
  report_import_allowed: false
  diagnostic_authority: none
  treatment_authority: none
```

Blocked internal demo properties:

- external public demo,
- patient-facing demo,
- clinical pilot,
- product beta,
- real patient sandbox,
- deidentified patient sandbox,
- DICOM sandbox,
- PACS/EHR test integration,
- diagnostic performance test,
- clinical validation cohort.

Internal demo rule:

> Internal demo means internal synthetic demonstration, not external clinical trial, beta, or pilot.

---

## 11. Allowed Route Scaffold Categories

v0.16 may plan the following route categories.

| Route Category | Example Route | Allowed Meaning |
|---|---|---|
| prototype_boundary | `/prototype` | show prototype limits |
| synthetic_case_selection | `/prototype/cases` | list sealed fictional cases |
| synthetic_intake_review | `/prototype/cases/:synthetic_case_id/intake` | review fictional fields |
| reasoning_map | `/prototype/cases/:synthetic_case_id/map` | show guided map |
| evidence_panels | `/prototype/cases/:synthetic_case_id/evidence` | show visibility panels |
| safe_export_preview | `/prototype/cases/:synthetic_case_id/export-preview` | show non-clinical preview |
| red_team_fail_closed | `/prototype/red-team` | show blocked unsafe examples |
| audit_trace | `/prototype/cases/:synthetic_case_id/audit` | show UI traceability |
| safety_reference | `/prototype/safety` | show authority/no-decision/visual labels |

Allowed route rule:

> Allowed routes must remain under a prototype namespace and synthetic fixture boundary.

---

## 12. Blocked Route Scaffold Categories

v0.16 must not plan the following route categories.

| Blocked Route | Reason |
|---|---|
| `/patient` | patient-facing route blocked |
| `/clinical` | clinical deployment route blocked |
| `/cases/upload` | real patient data blocked |
| `/dicom/import` | DICOM import blocked |
| `/pacs/connect` | PACS integration blocked |
| `/ehr/connect` | EHR integration blocked |
| `/diagnosis` | diagnostic authority blocked |
| `/diagnosis/ranking` | ranking/probability blocked |
| `/rule-out` | exclusion authority blocked |
| `/treatment` | treatment authority blocked |
| `/orders` | test-order authority blocked |
| `/procedures` | procedure authority blocked |
| `/follow-up` | follow-up authority blocked |
| `/triage` | triage authority blocked |
| `/patient-summary` | patient-facing output blocked |
| `/validation/clinical` | clinical validation not opened |
| `/performance` | diagnostic performance claim blocked |
| `/product-ready` | product readiness false |
| `/public` | public readiness false |
| `/mdd/consensus` | MDD replacement blocked |

Blocked route rule:

> A blocked route must not exist as an enabled implementation target, hidden feature, future toggle, or placeholder route that implies clinical capability.

---

## 13. Synthetic Fixture Only Requirement

v0.16 may plan only synthetic fixture binding.

Allowed fixture categories:

- synthetic_demo_case,
- demo_case_pack,
- demo_reasoning_session_object,
- demo_intake_binding_fixture,
- demo_workspace_state_fixture,
- demo_structured_output_fixture,
- demo_case_snapshot_fixture,
- demo_revision_history_fixture,
- demo_safe_export_fixture,
- demo_MDD_preparation_package_fixture,
- demo_unsafe_export_failure_fixture,
- demo_audit_event_fixture,
- demo_authority_envelope_fixture,
- demo_no_decision_object_fixture,
- demo_visual_artifact_fixture.

Blocked fixture categories:

- patient_case,
- deidentified_patient_case,
- DICOM_study,
- HRCT_series,
- radiology_report,
- pathology_report,
- microbiology_report,
- clinical_note,
- PACS_record,
- EHR_record,
- clinical_validation_case,
- diagnostic_ground_truth_case,
- performance_benchmark_case,
- patient_facing_case.

Fixture requirement rule:

> Fixture registry may contain synthetic governance objects only.

---

## 14. No Real Patient Data Guard

The build scaffold must plan a hard guard against real patient data.

Required guard states:

```yaml
real_patient_data_guard:
  upload_controls_present: false
  paste_real_report_allowed: false
  patient_identifier_fields_present: false
  dicom_import_present: false
  pacs_connector_present: false
  ehr_connector_present: false
  deidentified_real_patient_upload_allowed: false
  real_patient_data_attempt_result: fail_closed
  audit_event_required: true
```

Required blocked message:

```text
Real patient data is not allowed in this internal prototype scaffold. The scaffold is limited to sealed synthetic demo fixtures and does not support clinical use, patient-facing use, public readiness, product readiness, clinical validation, DICOM import, PACS/EHR integration, diagnosis, treatment, orders, procedures, follow-up, triage, or MDD replacement.
```

Real patient guard rule:

> The scaffold must prevent real patient data before any workspace state can be created.

---

## 15. No DICOM / Report Import Guard

The build scaffold must plan a hard guard against DICOM and real report import.

Blocked import surfaces:

- DICOM upload,
- HRCT upload,
- image viewer,
- PACS connector,
- EHR connector,
- radiology report paste,
- pathology report import,
- microbiology report import,
- clinical note import,
- MDD note import.

Allowed representation:

- disabled control for boundary teaching,
- absent route,
- fail-closed stub,
- audit event for attempted access,
- explanation copy mapped to v0.15 safety rules.

Blocked representation:

- hidden DICOM route,
- mock DICOM viewer that looks clinical,
- clinical report text area,
- import button without safety boundary,
- “coming soon clinical import” language,
- “future patient upload” language.

DICOM/report guard rule:

> The scaffold must not imply that real clinical data import is a near-term hidden feature.

---

## 16. No Patient-Facing Route Guard

The build scaffold must block patient-facing interpretation.

Blocked patient-facing surfaces:

- patient summary route,
- patient education route,
- patient-friendly report,
- patient download,
- patient share link,
- patient portal export,
- family/caregiver explanation,
- plain-language clinical advice,
- public-facing demo route.

Required patient-facing guard:

```yaml
patient_facing_guard:
  patient_facing_routes_present: false
  patient_facing_export_present: false
  patient_summary_component_present: false
  patient_download_present: false
  patient_share_present: false
  patient_facing_attempt_result: fail_closed
  audit_event_required: true
```

Patient-facing guard rule:

> No route or copy may let synthetic demo output appear as patient material.

---

## 17. No Clinical Validation Route Guard

The build scaffold must block clinical validation interpretation.

Blocked validation surfaces:

- clinical validation dashboard,
- accuracy dashboard,
- sensitivity/specificity dashboard,
- AUC dashboard,
- expert-equivalence screen,
- case performance leaderboard,
- red-team pass as clinical safety,
- UI safety pass as clinical validation,
- audit trace as correctness proof.

Required validation guard:

```yaml
clinical_validation_guard:
  clinical_validation_route_present: false
  diagnostic_performance_route_present: false
  accuracy_metrics_present: false
  sensitivity_specificity_present: false
  auc_present: false
  expert_equivalence_present: false
  validation_overclaim_attempt_result: fail_closed
  audit_event_required: true
```

Clinical validation guard rule:

> v0.16 may plan UI safety checks only, not clinical validation or diagnostic performance measurement.

---

## 18. No Product / Public Readiness Route Guard

The build scaffold must preserve public_ready=false and product_ready=false.

Blocked readiness surfaces:

- product readiness dashboard,
- public launch route,
- publish public demo control,
- release-ready label,
- safe-for-use label,
- deployment-ready label,
- beta clinical use route,
- external trial route.

Required readiness guard:

```yaml
readiness_guard:
  public_ready: false
  product_ready: false
  public_publish_route_present: false
  product_release_route_present: false
  deployment_ready_label_present: false
  readiness_overclaim_attempt_result: fail_closed
  audit_event_required: true
```

Readiness guard rule:

> An internal scaffold may be build-plannable without being product-ready or public-ready.

---

## 19. No Diagnostic / Treatment / Action Route Guard

The build scaffold must block all clinical action routes.

Blocked clinical action routes:

- diagnosis route,
- disease ranking route,
- disease exclusion route,
- mimic confirmation route,
- mimic exclusion route,
- treatment route,
- order route,
- procedure route,
- follow-up route,
- triage route,
- disposition route.

Required action guard:

```yaml
clinical_action_guard:
  diagnosis_route_present: false
  treatment_route_present: false
  order_route_present: false
  procedure_route_present: false
  follow_up_route_present: false
  triage_route_present: false
  diagnosis_action_attempt_result: fail_closed
  audit_event_required: true
```

Clinical action guard rule:

> If a route would matter clinically, it cannot enter the scaffold.

---

## 20. Fail-Closed Implementation Principle

v0.16 may plan fail-closed implementation stubs.

Allowed fail-closed stubs:

- real_patient_data_attempt_blocked,
- dicom_import_attempt_blocked,
- report_paste_attempt_blocked,
- unsafe_heading_detected,
- diagnosis_language_detected,
- exclusion_language_detected,
- treatment_language_detected,
- order_language_detected,
- procedure_language_detected,
- follow_up_language_detected,
- triage_language_detected,
- patient_facing_language_detected,
- clinical_validation_claim_detected,
- product_ready_claim_detected,
- public_ready_claim_detected,
- authority_envelope_missing,
- no_decision_object_missing,
- unsafe_copy_attempt_blocked,
- unsafe_export_attempt_blocked.

Required stub behavior:

```yaml
fail_closed_stub:
  unsafe_attempt_detected: true
  user_output_allowed: false
  copy_allowed: false
  export_allowed: false
  clinical_authority_effect: none
  decision_effect: none
  repair_required: true
  ui_safety_revalidation_required: conditional_required
  audit_event_required: true
```

Fail-closed scaffold rule:

> Unsafe implementation paths must end in blocked state, not hidden clinical functionality.

---

## 21. Audit Stub Implementation Principle

v0.16 may plan audit event stubs for UI traceability only.

Allowed audit event stubs:

- prototype_boundary_viewed,
- prototype_boundary_acknowledged,
- synthetic_case_selector_viewed,
- synthetic_case_selected,
- synthetic_fixture_bound,
- demo_intake_review_viewed,
- supplied_field_inspected,
- missing_field_inspected,
- reasoning_map_opened,
- reasoning_map_node_expanded,
- evidence_panel_opened,
- export_preview_requested,
- export_safety_check_started,
- export_preview_blocked,
- safe_preview_available,
- red_team_scenario_viewed,
- unsafe_copy_attempt_blocked,
- unsafe_export_attempt_blocked,
- real_patient_data_attempt_blocked,
- dicom_import_attempt_blocked,
- report_paste_attempt_blocked.

Required audit stub fields:

```yaml
audit_event_stub:
  event_id: string
  event_type: string
  source_route: string
  source_component: optional
  source_contract: string
  authority_effect: none
  decision_effect: none
  correctness_claim: false
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
```

Blocked audit stub meanings:

- diagnosis validated,
- clinical correctness proven,
- diagnostic performance measured,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD consensus achieved,
- product readiness achieved,
- public readiness achieved.

Audit scaffold rule:

> Audit stubs may trace UI state; they may not prove medicine.

---

## 22. Safe Export Preview Stub Boundary

v0.16 may plan a safe export preview stub.

Allowed safe export preview stub sections:

- synthetic demo boundary,
- non-clinical use boundary,
- authority envelope,
- no-decision object,
- source status summary,
- supplied context summary,
- missing evidence summary,
- mimic visibility summary,
- overlap visibility summary,
- confidence limiter summary,
- review prompt visibility,
- audit trace references,
- export safety state.

Blocked safe export preview stub sections:

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

Export preview stub rule:

> The stub may show safe structure; it may not become a clinical report generator.

---

## 23. Red-Team Scenario Stub Boundary

v0.16 may plan red-team scenario stubs for fail-closed UI behavior.

Allowed red-team stub categories:

- unsafe heading stub,
- diagnosis phrase stub,
- exclusion phrase stub,
- probability/ranking table stub,
- confirmation badge stub,
- treatment recommendation stub,
- test order phrase stub,
- procedure required phrase stub,
- follow-up due phrase stub,
- triage phrase stub,
- patient-facing summary stub,
- public-ready label stub,
- product-ready label stub,
- clinical validation claim stub,
- audit-proves-correctness claim stub,
- source-confirms-diagnosis claim stub,
- authority envelope missing stub,
- no-decision object missing stub.

Required red-team stub behavior:

```yaml
red_team_stub:
  unsafe_example_visible: quarantined_only
  copy_allowed: false
  export_allowed: false
  failure_reason_required: true
  repair_required: true
  ui_safety_revalidation_required: conditional_required
  authority_effect: none
  decision_effect: none
  audit_event_required: true
```

Red-team stub rule:

> Red-team stubs may demonstrate blocked unsafe behavior; they may not provide reusable unsafe output.

---

## 24. UI Copy Source Mapping Requirement

v0.16 may plan UI copy only when source-governed.

Required copy mapping:

```yaml
ui_copy_source_mapping:
  copy_id: string
  copy_text: string
  source_contract_version: string
  source_contract_file: string
  source_rule: string
  screen_or_component: string
  required_visibility: string
  unsafe_reuse_risk: string
  authority_effect: none
  decision_effect: none
```

Required copy classes:

- synthetic demo label,
- non-clinical label,
- not patient-facing label,
- public_ready false label,
- product_ready false label,
- no diagnosis label,
- no treatment label,
- no order label,
- no procedure label,
- no follow-up label,
- no triage label,
- visual safety label,
- missing evidence limiter text,
- mimic visibility boundary text,
- overlap unresolved boundary text,
- source status limitation text,
- export preview boundary text,
- red-team quarantine text,
- UI safety revalidation label.

Copy rule:

> No safety-critical UI copy may be invented without source mapping.

---

## 25. Disabled Clinical Control Strategy

v0.16 may plan disabled controls only when they teach the boundary.

Allowed disabled controls:

| Disabled Control | Required Explanation |
|---|---|
| Upload real patient data | Real patient data is not allowed |
| Import DICOM | DICOM import is not opened |
| Paste real report | Real report import is not opened |
| Generate diagnosis | Diagnostic authority is none |
| Rank diagnoses | Probability/ranking is blocked |
| Rule out disease | Exclusion authority is none |
| Recommend treatment | Treatment authority is none |
| Order test | Test-order authority is none |
| Recommend procedure | Procedure authority is none |
| Schedule follow-up | Follow-up authority is none |
| Assign triage | Triage authority is none |
| Generate patient summary | Patient-facing use is not allowed |
| Mark clinically validated | Clinical validation is not opened |
| Mark product ready | Product readiness is false |
| Publish public demo | Public readiness is false |

Blocked disabled-control behavior:

- disabled control that implies hidden near-term clinical feature,
- “coming soon clinical mode,”
- “unlock clinical validation,”
- “enable diagnosis,”
- “connect PACS soon,”
- “upload patient case soon,”
- disabled action without explanation.

Disabled control rule:

> A disabled clinical control must teach the boundary, not market a hidden clinical feature.

---

## 26. v0.16 Entry Gate Acceptance Criteria

v0.16.0 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| v0.16 scaffold scope defined | true |
| relationship to v0.15 defined | true |
| source-governed implementation principle defined | true |
| contract-to-build traceability required | true |
| allowed build surfaces defined | true |
| blocked build surfaces defined | true |
| internal demo boundary defined | true |
| allowed route scaffold categories defined | true |
| blocked route scaffold categories defined | true |
| synthetic fixture only requirement defined | true |
| no real patient data guard defined | true |
| no DICOM/report import guard defined | true |
| no patient-facing route guard defined | true |
| no clinical validation route guard defined | true |
| no product/public readiness route guard defined | true |
| no diagnostic/treatment/action route guard defined | true |
| fail-closed implementation principle defined | true |
| audit stub implementation principle defined | true |
| safe export preview stub boundary defined | true |
| red-team scenario stub boundary defined | true |
| UI copy source mapping requirement defined | true |
| disabled clinical control strategy defined | true |
| real patient data remains blocked | true |
| deidentified real patient data remains blocked | true |
| DICOM import remains blocked | true |
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

v0.16.0 acceptance rule:

> The entry gate passes only if build scaffold planning is opened while clinical implementation remains closed.

---

## 27. Recommended v0.16 Sequence

Recommended v0.16 chain:

| Version | Proposed Step |
|---|---|
| v0.16.0 | Source-Governed Prototype Build Scaffold Entry Gate |
| v0.16.1 | Prototype Route / Screen Registry Implementation Plan |
| v0.16.2 | Synthetic Fixture Registry / Demo State Binding Plan |
| v0.16.3 | UI Copy Source Mapping / Safety Language Contract |
| v0.16.4 | Fail-Closed State Stub / Disabled Clinical Control Plan |
| v0.16.5 | Audit Event Stub / Traceability Implementation Plan |
| v0.16.6 | Safe Export Preview Stub / Red-Team Scenario Stub Plan |
| v0.16.7 | Prototype Build Scaffold Validation Checklist |
| v0.16.8 | Source-Governed Prototype Build Scaffold Structural Seal |
| checkpoint-v0.16 | Project Status / Roadmap Checkpoint after v0.16 |

v0.16 sequence rule:

> v0.16 may plan internal build scaffolding only under source-governed traceability.

---

## 28. Next Step

The next recommended step is:

- v0.16.1 — Prototype Route / Screen Registry Implementation Plan

v0.16.1 should define:

- internal prototype route namespace,
- allowed route registry,
- blocked route registry,
- route-to-source contract mapping,
- screen-to-route mapping,
- safety label route requirements,
- authority envelope route requirements,
- no-decision route requirements,
- audit stub route requirements,
- safe navigation graph,
- blocked navigation graph,
- route fail-closed conditions.

v0.16.1 must not open clinical deployment, real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 29. Governance Statement

This document opens source-governed prototype build scaffold planning.

It opens internal demo implementation planning only.

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
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.16.0 governance discipline is:

> “Do not let build scaffold planning become clinical implementation.”

The build scaffold discipline is:

> “Every planned build element must trace to a sealed contract before it can enter the internal prototype scaffold.”