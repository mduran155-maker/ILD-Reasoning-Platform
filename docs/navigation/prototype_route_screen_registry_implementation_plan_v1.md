# ILD Reasoning Platform — Prototype Route / Screen Registry Implementation Plan v1

Version: v0.16.1  
Status: prototype_route_screen_registry_implementation_plan  
Scope: Internal prototype route namespace, allowed route registry, blocked route registry, route-to-source contract mapping, screen-to-route mapping, safety label route requirements, authority envelope route requirements, no-decision route requirements, audit stub route requirements, safe navigation graph, blocked navigation graph, route fail-closed conditions, and source-governed route/screen implementation planning  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.16.1 — Prototype Route / Screen Registry Implementation Plan.

v0.16.1 translates the sealed v0.15 prototype workspace screen and flow contracts into a source-governed internal route and screen registry plan.

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

Its purpose is to define which routes and screens may exist in an internal synthetic prototype scaffold, and which routes and screens must remain absent, disabled, or fail-closed.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16.1 route principle is:

> “Routes may organize internal synthetic demo navigation, but they must not create clinical workflow.”

The v0.16.1 screen registry principle is:

> “Every prototype screen must trace to a sealed contract before it can enter the build scaffold.”

---

## 2. Relationship to v0.16.0

v0.16.1 inherits v0.16.0 — Source-Governed Prototype Build Scaffold Entry Gate.

v0.16.0 opened:

- source-governed prototype build scaffold planning,
- contract-to-build traceability requirement,
- allowed and blocked build surfaces,
- synthetic fixture only requirement,
- no real patient data guard,
- no DICOM/report import guard,
- no patient-facing route guard,
- no clinical validation route guard,
- no product/public readiness route guard,
- no diagnostic/treatment/action route guard,
- fail-closed implementation principle,
- audit stub implementation principle,
- safe export preview stub boundary,
- red-team scenario stub boundary.

v0.16.1 does not broaden v0.16.0.

v0.16.1 defines the route and screen registry implementation plan under those boundaries.

v0.16.1 must not open:

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

Route inheritance rule:

> v0.16.1 may register internal synthetic prototype routes only; it may not register clinical routes.

---

## 3. Global Authority Envelope

Every route, screen, navigation edge, route guard, route parameter, route label, disabled route, fail-closed route, screen registry item, and audit stub must inherit the following authority envelope.

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

No route or screen may override this envelope.

Authority route rule:

> A route cannot grant clinical authority by existing in the scaffold.

---

## 4. Global No-Decision Object

The following no-decision object must remain active across all decision-adjacent prototype routes.

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

Required route presence:

- `/prototype`
- `/prototype/cases`
- `/prototype/cases/:synthetic_case_id/intake`
- `/prototype/cases/:synthetic_case_id/map`
- `/prototype/cases/:synthetic_case_id/evidence`
- `/prototype/cases/:synthetic_case_id/export-preview`
- `/prototype/red-team`
- `/prototype/cases/:synthetic_case_id/audit`
- `/prototype/safety`

No-decision route rule:

> Any route that shows reasoning, export preview, red-team behavior, or audit state must also show that no clinical decision was made.

---

## 5. Route Object Schema

Every allowed route must conform to the following schema.

```yaml
prototype_route:
  route_id: string
  version: v0.16.1
  route_path: string
  route_name: string
  route_category: enum
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
  allowed_next_routes: list
  blocked_next_routes: list
  fail_closed_conditions: list
```

Allowed route categories:

| Route Category | Meaning |
|---|---|
| prototype_boundary | Shows internal prototype boundary |
| synthetic_case_selection | Lists sealed synthetic demo cases |
| synthetic_intake_review | Shows fictional supplied/missing fields |
| reasoning_map | Shows guided reasoning map |
| evidence_visibility | Shows missing/mimic/overlap/source panels |
| safe_export_preview | Shows non-clinical export preview |
| red_team_fail_closed | Shows blocked unsafe examples |
| audit_trace | Shows UI traceability |
| safety_reference | Shows authority/no-decision/visual labels |

Route schema rule:

> A route is valid only if its schema makes clinical use impossible.

---

## 6. Screen Registry Object Schema

Every registered screen must conform to the following schema.

```yaml
prototype_screen_registry_item:
  screen_id: string
  version: v0.16.1
  screen_name: string
  assigned_route_id: string
  assigned_route_path: string
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  screen_category: enum
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
  allowed_components: list
  blocked_components: list
```

Screen registry rule:

> A screen may enter the scaffold only when it has a route and a sealed source contract.

---

## 7. Allowed Route Registry

The following routes are allowed for internal synthetic prototype planning.

| Route ID | Route Path | Route Name | Category | Status |
|---|---|---|---|---|
| ROUTE_001 | `/prototype` | Prototype Boundary Landing | prototype_boundary | allowed |
| ROUTE_002 | `/prototype/cases` | Synthetic Demo Case Selector | synthetic_case_selection | allowed |
| ROUTE_003 | `/prototype/cases/:synthetic_case_id/intake` | Synthetic Intake Review | synthetic_intake_review | allowed |
| ROUTE_004 | `/prototype/cases/:synthetic_case_id/map` | Reasoning Map | reasoning_map | allowed |
| ROUTE_005 | `/prototype/cases/:synthetic_case_id/evidence` | Evidence Panel Hub | evidence_visibility | allowed |
| ROUTE_006 | `/prototype/cases/:synthetic_case_id/evidence/missing` | Missing Evidence Panel | evidence_visibility | allowed |
| ROUTE_007 | `/prototype/cases/:synthetic_case_id/evidence/mimics` | Mimic Visibility Panel | evidence_visibility | allowed |
| ROUTE_008 | `/prototype/cases/:synthetic_case_id/evidence/overlap` | Overlap Panel | evidence_visibility | allowed |
| ROUTE_009 | `/prototype/cases/:synthetic_case_id/evidence/source-status` | Source Status Panel | evidence_visibility | allowed |
| ROUTE_010 | `/prototype/cases/:synthetic_case_id/evidence/confidence-limiter` | Confidence Limiter Panel | evidence_visibility | allowed |
| ROUTE_011 | `/prototype/cases/:synthetic_case_id/evidence/review-prompts` | Review Prompt Panel | evidence_visibility | allowed |
| ROUTE_012 | `/prototype/cases/:synthetic_case_id/export-preview` | Safe Export Preview | safe_export_preview | allowed |
| ROUTE_013 | `/prototype/red-team` | Red-Team Fail-Closed Hub | red_team_fail_closed | allowed |
| ROUTE_014 | `/prototype/red-team/:scenario_id` | Red-Team Scenario Detail | red_team_fail_closed | allowed |
| ROUTE_015 | `/prototype/cases/:synthetic_case_id/audit` | Audit Trace | audit_trace | allowed |
| ROUTE_016 | `/prototype/safety` | Prototype Safety Reference | safety_reference | allowed |

Allowed route registry rule:

> All allowed routes must remain under `/prototype` and must bind only to sealed synthetic fixtures.

---

## 8. Blocked Route Registry

The following routes must not be implemented as enabled routes, hidden routes, future toggles, or “coming soon” route placeholders.

| Blocked Route | Reason |
|---|---|
| `/patient` | patient-facing route blocked |
| `/patients` | patient-facing / real patient data risk |
| `/clinical` | clinical deployment blocked |
| `/clinical/cases` | clinical case workflow blocked |
| `/cases/upload` | real patient upload blocked |
| `/cases/import` | real case import blocked |
| `/cases/deidentified` | deidentified real case blocked |
| `/dicom/import` | DICOM import blocked |
| `/hrct/upload` | HRCT import blocked |
| `/images/viewer` | clinical image viewer risk |
| `/pacs/connect` | PACS integration blocked |
| `/ehr/connect` | EHR integration blocked |
| `/reports/import` | real report import blocked |
| `/reports/paste` | real report paste blocked |
| `/diagnosis` | diagnostic authority blocked |
| `/diagnosis/final` | diagnostic closure blocked |
| `/diagnosis/ranking` | ranking/probability blocked |
| `/rule-out` | exclusion authority blocked |
| `/mimics/exclude` | mimic exclusion blocked |
| `/treatment` | treatment authority blocked |
| `/orders` | test-order authority blocked |
| `/procedures` | procedure authority blocked |
| `/follow-up` | follow-up authority blocked |
| `/triage` | triage authority blocked |
| `/disposition` | triage/disposition blocked |
| `/patient-summary` | patient-facing output blocked |
| `/validation/clinical` | clinical validation not opened |
| `/performance` | diagnostic performance claim blocked |
| `/metrics/accuracy` | performance claim blocked |
| `/product-ready` | product readiness false |
| `/public` | public readiness false |
| `/mdd/consensus` | MDD replacement blocked |

Blocked route registry rule:

> A blocked route cannot exist as a navigable path, hidden path, scaffold placeholder, future toggle, or route comment implying planned clinical capability.

---

## 9. Route-to-Source Contract Mapping

Every allowed route must map to a sealed source contract.

| Route ID | Route Path | Source Contract | Source Role |
|---|---|---|---|
| ROUTE_001 | `/prototype` | v0.15.0 / v0.15.6 | prototype boundary and structural seal |
| ROUTE_002 | `/prototype/cases` | v0.15.1 / v0.15.2 | synthetic case selector and selection flow |
| ROUTE_003 | `/prototype/cases/:synthetic_case_id/intake` | v0.15.1 / v0.15.2 | demo intake review and synthetic fields |
| ROUTE_004 | `/prototype/cases/:synthetic_case_id/map` | v0.15.3 | reasoning map interaction contract |
| ROUTE_005 | `/prototype/cases/:synthetic_case_id/evidence` | v0.15.1 / v0.15.3 | evidence panel hub and map-to-panel navigation |
| ROUTE_006 | `/prototype/cases/:synthetic_case_id/evidence/missing` | v0.15.1 / v0.15.3 | missing evidence panel and node behavior |
| ROUTE_007 | `/prototype/cases/:synthetic_case_id/evidence/mimics` | v0.15.1 / v0.15.3 | mimic visibility panel and node behavior |
| ROUTE_008 | `/prototype/cases/:synthetic_case_id/evidence/overlap` | v0.15.1 / v0.15.3 | overlap panel and node behavior |
| ROUTE_009 | `/prototype/cases/:synthetic_case_id/evidence/source-status` | v0.15.1 / v0.15.3 | source status panel and node behavior |
| ROUTE_010 | `/prototype/cases/:synthetic_case_id/evidence/confidence-limiter` | v0.15.1 / v0.15.3 | confidence limiter panel and node behavior |
| ROUTE_011 | `/prototype/cases/:synthetic_case_id/evidence/review-prompts` | v0.15.1 / v0.15.3 | review prompt panel and node behavior |
| ROUTE_012 | `/prototype/cases/:synthetic_case_id/export-preview` | v0.15.4 | safe export preview boundary |
| ROUTE_013 | `/prototype/red-team` | v0.15.4 | red-team fail-closed hub |
| ROUTE_014 | `/prototype/red-team/:scenario_id` | v0.15.4 | red-team scenario detail |
| ROUTE_015 | `/prototype/cases/:synthetic_case_id/audit` | v0.15.1 / v0.15.3 / v0.15.4 / v0.15.5 | audit trace behavior |
| ROUTE_016 | `/prototype/safety` | v0.15.0 / v0.15.5 / v0.15.6 | safety labels, authority envelope, no-decision object |

Route-source mapping rule:

> A route without a source contract is not allowed.

---

## 10. Screen-to-Route Mapping

The following screens are mapped to allowed routes.

| Screen ID | Screen Name | Route ID | Route Path |
|---|---|---|---|
| V15_SCREEN_001 | Prototype Boundary Landing Screen | ROUTE_001 | `/prototype` |
| V15_SCREEN_002 | Synthetic Demo Case Selector | ROUTE_002 | `/prototype/cases` |
| V15_SCREEN_003 | Demo Intake Review Screen | ROUTE_003 | `/prototype/cases/:synthetic_case_id/intake` |
| V15_SCREEN_004 | Reasoning Map Screen | ROUTE_004 | `/prototype/cases/:synthetic_case_id/map` |
| V15_SCREEN_005 | Missing Evidence Panel | ROUTE_006 | `/prototype/cases/:synthetic_case_id/evidence/missing` |
| V15_SCREEN_006 | Mimic Visibility Panel | ROUTE_007 | `/prototype/cases/:synthetic_case_id/evidence/mimics` |
| V15_SCREEN_007 | Overlap Panel | ROUTE_008 | `/prototype/cases/:synthetic_case_id/evidence/overlap` |
| V15_SCREEN_008 | Source Status Panel | ROUTE_009 | `/prototype/cases/:synthetic_case_id/evidence/source-status` |
| V15_SCREEN_009 | Confidence Limiter Panel | ROUTE_010 | `/prototype/cases/:synthetic_case_id/evidence/confidence-limiter` |
| V15_SCREEN_010 | Review Prompt Panel | ROUTE_011 | `/prototype/cases/:synthetic_case_id/evidence/review-prompts` |
| V15_SCREEN_011 | Red-Team Fail-Closed Screen | ROUTE_013 / ROUTE_014 | `/prototype/red-team` |
| V15_SCREEN_012 | Safe Export Preview Screen | ROUTE_012 | `/prototype/cases/:synthetic_case_id/export-preview` |
| V15_SCREEN_013 | Authority Envelope Display | ROUTE_016 and embedded | `/prototype/safety` |
| V15_SCREEN_014 | No-Decision Object Display | ROUTE_016 and embedded | `/prototype/safety` |
| V15_SCREEN_015 | Audit Trace Screen | ROUTE_015 | `/prototype/cases/:synthetic_case_id/audit` |
| V15_SCREEN_016 | Visual Safety Label Display | ROUTE_016 and embedded | `/prototype/safety` |

Screen-to-route rule:

> A screen must have a safe route before it can enter the scaffold.

---

## 11. Route Parameter Rules

Route parameters must remain synthetic-only.

Allowed route parameters:

```yaml
allowed_route_parameters:
  synthetic_case_id:
    allowed: true
    source: synthetic_demo_case_registry
    real_patient_identifier_allowed: false
    accession_number_allowed: false
    mrn_allowed: false
    dicom_uid_allowed: false
  scenario_id:
    allowed: true
    source: red_team_scenario_registry
    clinical_case_identifier_allowed: false
```

Blocked route parameters:

- patient_id,
- mrn,
- accession_number,
- study_uid,
- series_uid,
- dicom_uid,
- encounter_id,
- visit_id,
- report_id from real clinical system,
- institution_case_id,
- clinical_validation_case_id.

Route parameter rule:

> Route parameters may identify synthetic fixtures only, never patients or clinical studies.

---

## 12. Safety Label Route Requirements

Every allowed route must display required safety labels.

| Route Category | Required Labels |
|---|---|
| prototype_boundary | synthetic demo only; not for clinical use; not patient-facing; public_ready false; product_ready false |
| synthetic_case_selection | synthetic cases only; real patient data not allowed; clinical validation not opened |
| synthetic_intake_review | fictional fields only; not clinical intake; missing evidence is not exclusion |
| reasoning_map | map is not diagnostic proof; color is not probability; icon is not authority |
| evidence_visibility | visibility/limitation only; no recommendation |
| safe_export_preview | export preview is not clinical report; MDD preparation is not MDD consensus |
| red_team_fail_closed | blocked unsafe example only; not reusable output |
| audit_trace | audit trace is not correctness proof |
| safety_reference | authority envelope and no-decision object |

Safety label rule:

> Every route must teach its boundary before or alongside its content.

---

## 13. Authority Envelope Route Requirements

The authority envelope must be present or embedded in all allowed routes.

Required authority envelope route behavior:

```yaml
authority_envelope_route_requirement:
  diagnostic_authority: none
  treatment_authority: none
  order_authority: none
  procedure_authority: none
  follow_up_authority: none
  triage_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinical_validation: not_opened
  mdd_replacement: not_allowed
```

Display requirement:

| Route | Display Mode |
|---|---|
| `/prototype` | full card required |
| `/prototype/cases` | footer or side card required |
| intake route | footer or side card required |
| map route | node/card required |
| evidence routes | footer or side card required |
| export preview route | full block required before preview content |
| red-team route | full block required in fail-closed context |
| audit route | event metadata and summary required |
| safety route | full reference required |

Authority route rule:

> Route rendering is unsafe if the authority envelope is absent.

---

## 14. No-Decision Route Requirements

The no-decision object must be present on all decision-adjacent routes.

Required no-decision display:

| Route | Required State |
|---|---|
| `/prototype` | full object visible |
| `/prototype/cases/:synthetic_case_id/intake` | visible or directly linked |
| `/prototype/cases/:synthetic_case_id/map` | node and side card |
| `/prototype/cases/:synthetic_case_id/evidence/*` | footer or side card |
| `/prototype/cases/:synthetic_case_id/export-preview` | full block before preview sections |
| `/prototype/red-team` | visible in fail-closed container |
| `/prototype/cases/:synthetic_case_id/audit` | event metadata or summary |
| `/prototype/safety` | full reference |

No-decision route rule:

> Decision-adjacent routes must show decisions not made before users can infer decisions from visible reasoning.

---

## 15. Audit Stub Route Requirements

Every allowed route must plan audit stubs.

Required route audit stubs:

| Route | Required Audit Stub |
|---|---|
| `/prototype` | prototype_boundary_viewed |
| `/prototype/cases` | synthetic_case_selector_viewed |
| `/prototype/cases/:synthetic_case_id/intake` | demo_intake_review_viewed |
| `/prototype/cases/:synthetic_case_id/map` | reasoning_map_opened |
| `/prototype/cases/:synthetic_case_id/evidence` | evidence_panel_hub_opened |
| `/prototype/cases/:synthetic_case_id/evidence/missing` | missing_evidence_panel_opened |
| `/prototype/cases/:synthetic_case_id/evidence/mimics` | mimic_visibility_panel_opened |
| `/prototype/cases/:synthetic_case_id/evidence/overlap` | overlap_panel_opened |
| `/prototype/cases/:synthetic_case_id/evidence/source-status` | source_status_panel_opened |
| `/prototype/cases/:synthetic_case_id/export-preview` | export_preview_requested |
| `/prototype/red-team` | red_team_hub_viewed |
| `/prototype/red-team/:scenario_id` | red_team_scenario_viewed |
| `/prototype/cases/:synthetic_case_id/audit` | audit_trace_viewed |
| `/prototype/safety` | safety_reference_viewed |

Every audit stub must preserve:

```yaml
authority_effect: none
decision_effect: none
correctness_claim: false
clinical_validation_effect: none
product_readiness_effect: none
public_readiness_effect: none
```

Audit route rule:

> Route audit stubs trace UI movement, not medical correctness.

---

## 16. Safe Navigation Graph

The following navigation graph is allowed.

```text
/prototype
  → /prototype/cases

/prototype/cases
  → /prototype/cases/:synthetic_case_id/intake

/prototype/cases/:synthetic_case_id/intake
  → /prototype/cases/:synthetic_case_id/map
  → /prototype/cases/:synthetic_case_id/evidence
  → /prototype/cases/:synthetic_case_id/audit

/prototype/cases/:synthetic_case_id/map
  → /prototype/cases/:synthetic_case_id/evidence
  → /prototype/cases/:synthetic_case_id/export-preview
  → /prototype/cases/:synthetic_case_id/audit
  → /prototype/safety

/prototype/cases/:synthetic_case_id/evidence
  → /prototype/cases/:synthetic_case_id/evidence/missing
  → /prototype/cases/:synthetic_case_id/evidence/mimics
  → /prototype/cases/:synthetic_case_id/evidence/overlap
  → /prototype/cases/:synthetic_case_id/evidence/source-status
  → /prototype/cases/:synthetic_case_id/evidence/confidence-limiter
  → /prototype/cases/:synthetic_case_id/evidence/review-prompts
  → /prototype/cases/:synthetic_case_id/map
  → /prototype/cases/:synthetic_case_id/export-preview

/prototype/cases/:synthetic_case_id/export-preview
  → /prototype/cases/:synthetic_case_id/audit
  → /prototype/safety

/prototype/red-team
  → /prototype/red-team/:scenario_id
  → /prototype/safety

/prototype/red-team/:scenario_id
  → /prototype/red-team
  → /prototype/safety

/prototype/safety
  → /prototype
  → /prototype/cases
```

Safe navigation rule:

> Safe navigation may deepen synthetic visibility; it may not escalate into clinical workflow.

---

## 17. Blocked Navigation Graph

The following navigation edges are blocked.

```text
/prototype → /clinical
/prototype → /patient
/prototype/cases → /cases/upload
/prototype/cases → /dicom/import
/prototype/cases → /reports/import
/prototype/cases/:synthetic_case_id/intake → /diagnosis
/prototype/cases/:synthetic_case_id/intake → /orders
/prototype/cases/:synthetic_case_id/map → /diagnosis/ranking
/prototype/cases/:synthetic_case_id/map → /treatment
/prototype/cases/:synthetic_case_id/map → /triage
/prototype/cases/:synthetic_case_id/evidence → /rule-out
/prototype/cases/:synthetic_case_id/evidence → /procedures
/prototype/cases/:synthetic_case_id/export-preview → /patient-summary
/prototype/cases/:synthetic_case_id/export-preview → /mdd/consensus
/prototype/red-team → /validation/clinical
/prototype/red-team → /product-ready
/prototype/safety → /public
```

Blocked navigation rule:

> No safe route may link into a blocked clinical, patient-facing, validation, product, public, or MDD consensus path.

---

## 18. Route Fail-Closed Conditions

Routes must fail closed under the following conditions.

```yaml
route_fail_closed_conditions:
  route_not_in_allowed_registry:
    navigation_allowed: false
    audit_required: true
  route_in_blocked_registry:
    navigation_allowed: false
    audit_required: true
  synthetic_case_id_not_found_in_registry:
    navigation_allowed: false
    audit_required: true
  synthetic_case_id_resolves_to_real_patient_marker:
    navigation_allowed: false
    audit_required: true
  patient_identifier_detected_in_route:
    navigation_allowed: false
    audit_required: true
  dicom_identifier_detected_in_route:
    navigation_allowed: false
    audit_required: true
  authority_envelope_missing:
    route_render_allowed: false
    repair_required: true
    audit_required: true
  no_decision_object_missing_on_decision_adjacent_route:
    route_render_allowed: false
    repair_required: true
    audit_required: true
  unsafe_route_label_detected:
    route_render_allowed: false
    repair_required: true
    audit_required: true
  clinical_validation_claim_detected:
    route_render_allowed: false
    repair_required: true
    audit_required: true
  product_or_public_ready_claim_detected:
    route_render_allowed: false
    repair_required: true
    audit_required: true
```

Route fail-closed rule:

> Unsafe route state must stop navigation before clinical meaning is created.

---

## 19. Disabled / Absent Route Behavior

Blocked routes should generally be absent.

If a blocked route is shown as a disabled educational control, it must follow disabled route rules.

Allowed disabled route behavior:

```yaml
disabled_route_control:
  enabled: false
  clickable: false
  route_navigation_allowed: false
  explanation_required: true
  source_contract_required: true
  audit_event_on_attempt_required: true
  authority_effect: none
  decision_effect: none
```

Allowed disabled explanations:

- “Real patient data is not allowed.”
- “DICOM import is not opened.”
- “Diagnostic authority is none.”
- “Treatment authority is none.”
- “Clinical validation is not opened.”
- “Product readiness is false.”
- “Patient-facing use is not allowed.”

Blocked disabled route behavior:

- “coming soon clinical mode,”
- “unlock diagnosis,”
- “enable patient upload,”
- “connect PACS soon,”
- “start clinical validation,”
- “publish when ready,”
- disabled control without explanation,
- disabled control that looks like hidden feature marketing.

Disabled route rule:

> A disabled route may teach a boundary; it may not advertise clinical capability.

---

## 20. Route Naming and Language Rules

Allowed route naming language:

- prototype,
- synthetic,
- demo,
- safety,
- map,
- evidence,
- missing,
- mimics,
- overlap,
- source status,
- confidence limiter,
- review prompts,
- export preview,
- red-team,
- audit.

Blocked route naming language:

- patient,
- clinical,
- diagnosis,
- final diagnosis,
- likely diagnosis,
- probability,
- rule-out,
- treatment,
- orders,
- procedures,
- follow-up,
- triage,
- disposition,
- validation,
- accuracy,
- product-ready,
- public,
- MDD consensus.

Route naming rule:

> Route names must not imply clinical function, clinical authority, validation, product readiness, or patient-facing use.

---

## 21. Route-Level UI Copy Requirements

Every route must carry source-governed safe copy.

Required route copy examples:

| Route | Required Copy |
|---|---|
| `/prototype` | “Synthetic internal prototype only. Not for clinical use.” |
| `/prototype/cases` | “Select a fictional governance scenario.” |
| intake route | “These fields are fictional and non-clinical.” |
| map route | “Reasoning map is visual guidance, not diagnostic proof.” |
| evidence routes | “Panels show visibility and limitations, not recommendations.” |
| export preview route | “Export preview is not a clinical report.” |
| red-team route | “Blocked unsafe examples are not reusable output.” |
| audit route | “Audit trace explains UI state, not medical correctness.” |
| safety route | “Authority remains none; no clinical decision is made.” |

Blocked route copy:

- “Start clinical case,”
- “Upload patient CT,”
- “Generate diagnosis,”
- “Confirm disease,”
- “Rule out disease,”
- “Recommended treatment,”
- “Order next test,”
- “Schedule follow-up,”
- “Safe for outpatient care,”
- “Clinically validated,”
- “Product ready,”
- “Public ready.”

Route copy rule:

> Route copy must teach governance, not clinical action.

---

## 22. Route Registry Validation Checklist

v0.16.1 route registry passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| ROUTE_CHECK_001 | all allowed routes under `/prototype` | true |
| ROUTE_CHECK_002 | no patient route registered | true |
| ROUTE_CHECK_003 | no clinical route registered | true |
| ROUTE_CHECK_004 | no DICOM/import route registered | true |
| ROUTE_CHECK_005 | no PACS/EHR route registered | true |
| ROUTE_CHECK_006 | no diagnosis route registered | true |
| ROUTE_CHECK_007 | no treatment/order/procedure/follow-up/triage route registered | true |
| ROUTE_CHECK_008 | no patient-facing route registered | true |
| ROUTE_CHECK_009 | no clinical validation route registered | true |
| ROUTE_CHECK_010 | no product/public readiness route registered | true |
| ROUTE_CHECK_011 | no MDD consensus route registered | true |
| ROUTE_CHECK_012 | every allowed route maps to a source contract | true |
| ROUTE_CHECK_013 | every allowed route requires safety labels | true |
| ROUTE_CHECK_014 | every decision-adjacent route requires no-decision object | true |
| ROUTE_CHECK_015 | every route requires audit stub | true |
| ROUTE_CHECK_016 | route fail-closed conditions defined | true |
| ROUTE_CHECK_017 | blocked navigation graph defined | true |
| ROUTE_CHECK_018 | route parameters synthetic-only | true |

Route validation rule:

> Route registry passes only if it cannot navigate into clinical capability.

---

## 23. Screen Registry Validation Checklist

v0.16.1 screen registry passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| SCREEN_CHECK_001 | every registered screen has route | true |
| SCREEN_CHECK_002 | every registered screen has source contract | true |
| SCREEN_CHECK_003 | prototype boundary screen mapped | true |
| SCREEN_CHECK_004 | synthetic case selector mapped | true |
| SCREEN_CHECK_005 | demo intake review screen mapped | true |
| SCREEN_CHECK_006 | reasoning map screen mapped | true |
| SCREEN_CHECK_007 | evidence panel screens mapped | true |
| SCREEN_CHECK_008 | safe export preview screen mapped | true |
| SCREEN_CHECK_009 | red-team fail-closed screen mapped | true |
| SCREEN_CHECK_010 | audit trace screen mapped | true |
| SCREEN_CHECK_011 | safety reference screen mapped | true |
| SCREEN_CHECK_012 | no final diagnosis screen mapped | true |
| SCREEN_CHECK_013 | no treatment/order/procedure/follow-up/triage screen mapped | true |
| SCREEN_CHECK_014 | no patient-facing screen mapped | true |
| SCREEN_CHECK_015 | no clinical validation screen mapped | true |
| SCREEN_CHECK_016 | no product/public readiness screen mapped | true |

Screen registry validation rule:

> A screen registry passes only if every screen remains synthetic, non-clinical, and source-governed.

---

## 24. v0.16.1 Acceptance Criteria

v0.16.1 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| route object schema defined | true |
| screen registry object schema defined | true |
| allowed route registry defined | true |
| blocked route registry defined | true |
| route-to-source contract mapping defined | true |
| screen-to-route mapping defined | true |
| route parameter rules defined | true |
| safety label route requirements defined | true |
| authority envelope route requirements defined | true |
| no-decision route requirements defined | true |
| audit stub route requirements defined | true |
| safe navigation graph defined | true |
| blocked navigation graph defined | true |
| route fail-closed conditions defined | true |
| disabled/absent route behavior defined | true |
| route naming and language rules defined | true |
| route-level UI copy requirements defined | true |
| route registry validation checklist defined | true |
| screen registry validation checklist defined | true |
| all routes remain internal demo only | true |
| all routes remain synthetic-only | true |
| no real patient data route opened | true |
| no deidentified real patient route opened | true |
| no DICOM/report import route opened | true |
| no PACS/EHR route opened | true |
| no patient-facing route opened | true |
| no clinical validation route opened | true |
| no product/public readiness route opened | true |
| no diagnostic/treatment/order/procedure/follow-up/triage route opened | true |
| no MDD replacement route opened | true |

v0.16.1 acceptance rule:

> The route and screen registry implementation plan is accepted only if every route remains source-governed, synthetic-only, internal-demo-only, non-clinical, non-authoritative, and fail-closed.

---

## 25. Next Step

The next recommended step is:

- v0.16.2 — Synthetic Fixture Registry / Demo State Binding Plan

v0.16.2 should define:

- synthetic fixture registry structure,
- allowed fixture IDs,
- synthetic case registry object,
- fixture-to-route binding,
- fixture-to-screen binding,
- fixture-to-component binding,
- demo state object planning,
- selected synthetic case state,
- synthetic intake state,
- reasoning map state,
- evidence panel state,
- safe export preview state,
- red-team scenario state,
- audit trace state,
- blocked real patient object categories,
- fixture binding fail-closed conditions.

v0.16.2 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 26. Governance Statement

This document defines the prototype route and screen registry implementation plan.

It opens internal route/screen scaffold planning only.

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

The v0.16.1 governance discipline is:

> “Do not let route planning become clinical workflow planning.”

The route scaffold discipline is:

> “A route may exist only if it remains internal, synthetic, source-governed, non-clinical, non-authoritative, and fail-closed.”