# ILD Reasoning Platform — Route-to-Screen Binding Map v1

Version: v0.19.1  
Status: static_wiring_plan  
Scope: Static route-to-screen binding map after v0.19.0  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.19.1:

- Route-to-Screen Binding Map.

v0.19.1 follows:

- v0.19.0 — Static Internal Demo Wiring Entry Gate,
- v0.18.9 — Local Prototype Skeleton Materialization Structural Seal,
- checkpoint-v0.18 — Project Status / Roadmap Checkpoint after v0.18.

v0.19.1 defines a static internal mapping from materialized route placeholders to materialized screen placeholders.

This step does not create a clinical workflow.

It does not create clinical routing.

It does not create real patient routing.

It does not create DICOM routing.

It does not create HRCT routing.

It does not create report routing.

It does not create PACS routing.

It does not create EHR routing.

It does not create diagnosis routing.

It does not create treatment routing.

It does not create test-order routing.

It does not create procedure routing.

It does not create follow-up routing.

It does not create triage routing.

It does not create patient-facing routing.

It does not create clinical validation routing.

It does not create product routing.

It does not replace MDD.

 not create clinical routing.

It does not create real patient routing.

It does not create DICOM routing.

It does not create HRCT routing.

It does not create report routing.

It does not create PACS routing.

It does not create EHR routing.

It does not create diagnosis routing.

It does not create treatment routing.

It does not create test-order routing.

It does not create procedure routing.

It does not create follow-up routing.

It does not create triage routing.

It does not create patient-facing routingThe central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.1 principle is:

> “Bind routes to screens for safe internal walkthrough, not clinical workflow.”

The permanent boundary is:

> “A route-to-screen map is navigation scaffolding, not clinical care flow.”

---

## 2. Required Previous State

v0.19.1 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.19.0 entry gate exists | true |
| v0.18.9 structural seal exists | true |
| checkpoint-v0.18 exists | true |
| Local prototype skeleton is materialized | true |
| Expected prototype file count remains 191 before v0.19.1 | true |
| Working tree before v0.19.1 is clean | true |
| Authority envelope preserved | true |
| No-decision object preserved | true |
| No real patient data opened | true |
| No deidentified real patient data opened | true |
| No DICOM/HRCT/report/PACS/EHR opened | true |
| No clinical validation opened | true |
| No diagnostic authority opened | true |
| No treatment authority opened | true |
| No patient-facing use opened | true |
| No public readiness opened | true |
| No product readiness opened | true |
| No MDD replacement opened | true |

Dependency rule:

> v0.19.1 may bind only sealed route placeholders to sealed screen placeholders.

---

## 3. Global Authority Envelope Preserved

The authority envelope remains unchanged:

| Field | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| test_order_authority | none |
| procedure_decision_authority | none |
| follow_up_authority | none |
| triage_authority | none |
| patient_facing_use | not_allowed |
| public_ready | false |
| product_ready | false |
| clinically_reviewed_platform_wide | false |
| real_patient_data | not_allowed |
| deidentified_real_patient_data | not_allowed |
| dicom_import | not_allowed |
| hrct_import | not_allowed |
| real_report_import | not_allowed |
| pacs_connection | not_allowed |
| ehr_connection | not_allowed |
| clinical_validation | not_opened |
| diagnostic_performance_claim | not_allowed |
| mdd_replacement | not_allowed |

Authority rule:

> Route-to-screen binding grants no clinical authority.

---

## 4. Global No-Decision Object Preserved

The no-decision object remains unchanged:

| Field | Required State |
|---|---|
| diagnosis_made | false |
| disease_excluded | false |
| mimic_excluded | false |
| treatment_selected | false |
| test_ordered | false |
| procedure_decided | false |
| follow_up_scheduled | false |
| triage_assigned | false |
| mdd_consensus_generated | false |
| patient_facing_output_generated | false |

No-decision rule:

> Route-to-screen binding may organize safe visibility, but it must not make or imply clinical decisions.

---

## 5. Static Route-to-Screen Binding Map

The sealed static route-to-screen binding map is:

| Route Placeholder | Screen Placeholder | Binding Meaning | Safety State |
|---|---|---|---|
| prototype/routes/prototype_boundary_route.md | prototype/screens/prototype_boundary_screen.md | prototype boundary visibility | safe_internal_only |
| prototype/routes/synthetic_case_selector_route.md | prototype/screens/synthetic_case_selector_screen.md | fictional demo case selection visibility | synthetic_only |
| prototype/routes/synthetic_intake_review_route.md | prototype/screens/demo_intake_review_screen.md | synthetic intake review visibility | no_patient_data |
| prototype/routes/reasoning_map_route.md | prototype/screens/reasoning_map_screen.md | reasoning structure visibility | no_diagnosis |
| prototype/routes/evidence_panel_route.md | prototype/screens/evidence_panel_hub_screen.md | evidence panel hub visibility | source_governed |
| prototype/routes/missing_evidence_panel_route.md | prototype/screens/missing_evidence_panel_screen.md | missing evidence visibility | uncertainty_preserved |
| prototype/routes/mimic_visibility_panel_route.md | prototype/screens/mimic_visibility_panel_screen.md | mimic visibility | no_exclusion |
| prototype/routes/overlap_panel_route.md | prototype/screens/overlap_panel_screen.md | overlap visibility | no_ranking |
| prototype/routes/source_status_panel_route.md | prototype/screens/source_status_panel_screen.md | source status visibility | no_authority_claim |
| prototype/routes/confidence_limiter_panel_route.md | prototype/screens/confidence_limiter_panel_screen.md | confidence limitation visibility | no_probability |
| prototype/routes/review_prompt_panel_route.md | prototype/screens/review_prompt_panel_screen.md | human review prompt visibility | review_required |
| prototype/routes/safe_export_preview_route.md | prototype/screens/safe_export_preview_screen.md | safe export preview visibility | not_clinical_report |
| prototype/routes/red_team_route.md | prototype/screens/red_team_fail_closed_screen.md | red-team fail-closed visibility | quarantine_only |
| prototype/routes/red_team_scenario_route.md | prototype/screens/red_team_scenario_detail_screen.md | red-team scenario detail visibility | non_reusable_unsafe_output |
| prototype/routes/audit_trace_route.md | prototype/screens/audit_trace_screen.md | audit trace visibility | traceability_only |
| prototype/routes/safety_reference_route.md | prototype/screens/safety_reference_screen.md | safety reference visibility | authority_boundary_visible |

Binding map rule:

> Every route binds to a safe screen placeholder only.

---

## 6. Auxiliary Safety Screen Coverage

The following materialized screens do not require independent primary route binding at v0.19.1.

They are auxiliary safety screens reachable through the safety reference surface.

| Auxiliary Screen | Primary Access Surface | Meaning |
|---|---|---|
| prototype/screens/authority_envelope_screen.md | prototype/routes/safety_reference_route.md | authority envelope visibility |
| prototype/screens/no_decision_object_screen.md | prototype/routes/safety_reference_route.md | no-decision object visibility |
| prototype/screens/visual_safety_label_screen.md | prototype/routes/safety_reference_route.md | visual safety label visibility |

Auxiliary screen rule:

> Safety auxiliary screens may be displayed from safety reference context only; they do not create clinical workflow routes.

---

## 7. Route Binding Semantics

Each route binding is static.

Each route binding is internal.

Each route binding is synthetic.

Each route binding is non-clinical.

Each route binding must preserve:

- authority envelope,
- no-decision object,
- internal-only status,
- synthetic-only status,
- no real patient data,
- no deidentified real patient data,
- no DICOM/HRCT/report/PACS/EHR,
- no diagnosis,
- no treatment,
- no clinical validation,
- no patient-facing use,
- no public readiness,
- no product readiness,
- no MDD replacement.

Route binding semantic rule:

> Static route binding is a map of visibility, not a map of clinical decisions.

---

## 8. Route Parameters Boundary

v0.19.1 does not open dynamic clinical route parameters.

Allowed static parameters:

| Parameter Type | State |
|---|---|
| screen_id | allowed_static_placeholder |
| safety_context_id | allowed_static_placeholder |
| synthetic_fixture_id | allowed_static_placeholder |
| audit_trace_id | allowed_static_placeholder |
| red_team_scenario_id | allowed_static_placeholder |

Blocked parameters:

| Parameter Type | State |
|---|---|
| patient_id | blocked |
| accession_number | blocked |
| MRN | blocked |
| DICOM_UID | blocked |
| study_uid | blocked |
| report_id | blocked |
| diagnosis_id | blocked |
| treatment_id | blocked |
| order_id | blocked |
| procedure_id | blocked |
| follow_up_id | blocked |
| triage_id | blocked |
| clinical_validation_id | blocked |
| product_release_id | blocked |
| MDD_consensus_id | blocked |

Route parameter rule:

> Route parameters may identify synthetic placeholders only, never clinical entities.

---

## 9. Blocked Route Families

The following route families remain blocked:

- patient routes,
- deidentified patient routes,
- clinical case routes,
- DICOM routes,
- HRCT routes,
- image viewer routes,
- real report routes,
- PACS routes,
- EHR routes,
- FHIR routes,
- diagnosis routes,
- final diagnosis routes,
- likely diagnosis routes,
- rule-out routes,
- exclusion routes,
- probability routes,
- ranking routes,
- treatment routes,
- order routes,
- procedure routes,
- follow-up routes,
- triage routes,
- patient-facing routes,
- clinical validation routes,
- diagnostic performance routes,
- public demo routes,
- product release routes,
- MDD final consensus routes,
- MDD replacement routes.

Blocked route rule:

> A blocked route family cannot be introduced as a hidden or future route alias.

---

## 10. Fail-Closed Routing Boundary

Any attempted route binding outside the static map must fail closed.

Fail-closed route attempts include:

- unknown route,
- patient route,
- DICOM route,
- report route,
- PACS/EHR route,
- diagnosis route,
- treatment route,
- patient-facing route,
- clinical validation route,
- public/product route,
- MDD final consensus route.

Fail-closed routing rule:

> Unknown or unsafe routes are stop-states, not warnings.

---

## 11. Audit Visibility Boundary

Route access may be audit-visible only as scaffold traceability.

Allowed audit meanings:

- route placeholder accessed,
- screen placeholder displayed,
- safety boundary displayed,
- synthetic fixture reference displayed,
- fail-closed route blocked,
- red-team route quarantined.

Blocked audit meanings:

- clinical correctness proof,
- diagnostic validation,
- treatment correctness,
- patient care audit,
- PACS audit,
- EHR audit,
- regulatory evidence,
- product readiness proof.

Audit rule:

> Route audit visibility records scaffold navigation only.

---

## 12. What v0.19.1 Allows

v0.19.1 allows only:

- static map from route placeholders to screen placeholders,
- auxiliary safety screen coverage through safety reference route,
- declaration of blocked route families,
- declaration of route parameter boundaries,
- declaration of fail-closed routing behavior,
- declaration of audit traceability boundary.

Allowed-use rule:

> v0.19.1 creates safe internal navigation binding plan only.

---

## 13. What v0.19.1 Blocks

v0.19.1 blocks:

- clinical workflow routing,
- real patient routing,
- deidentified patient routing,
- DICOM/HRCT routing,
- report routing,
- PACS/EHR routing,
- diagnosis routing,
- probability/ranking routing,
- treatment routing,
- test-order routing,
- procedure routing,
- follow-up routing,
- triage routing,
- patient-facing routing,
- clinical validation routing,
- product/public routing,
- MDD final consensus routing.

Blocked-use rule:

> Route-to-screen binding must not become clinical navigation architecture.

---

## 14. Prototype File Count Preservation

v0.19.1 does not add files inside the prototype skeleton.

The v0.18 sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count preservation rule:

> v0.19.1 records a wiring map in docs only; the materialized prototype skeleton remains unchanged.

---

## 15. Acceptance Criteria

v0.19.1 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.19.0 dependency listed | true |
| v0.18.9 dependency listed | true |
| checkpoint-v0.18 dependency listed | true |
| all 16 route placeholders mapped | true |
| all 16 route mappings target safe screen placeholders | true |
| auxiliary safety screens covered | true |
| no patient route mapped | true |
| no DICOM/HRCT/report/PACS/EHR route mapped | true |
| no diagnosis/treatment/action route mapped | true |
| no patient-facing route mapped | true |
| no clinical validation route mapped | true |
| no public/product route mapped | true |
| no MDD final consensus route mapped | true |
| route parameters limited to synthetic placeholders | true |
| fail-closed route boundary defined | true |
| audit visibility remains traceability-only | true |
| prototype file count remains 191 | true |
| authority envelope preserved | true |
| no-decision object preserved | true |
| no clinical workflow opened | true |
| no real patient data opened | true |
| no diagnostic authority opened | true |
| no treatment authority opened | true |
| no patient-facing use opened | true |
| no public readiness opened | true |
| no product readiness opened | true |
| no MDD replacement opened | true |

Acceptance rule:

> v0.19.1 is valid only if route-to-screen binding remains safe internal navigation scaffolding.

---

## 16. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short

    Get-ChildItem prototype/routes -File | Measure-Object
    Get-ChildItem prototype/screens -File | Measure-Object
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected counts:

    prototype/routes file count = 16
    prototype/screens file count = 19
    prototype total file count = 191

Verification rule:

> Route and screen counts support scaffold completeness only; they do not certify clinical workflow.

---

## 17. Next Step

The next recommended step is:

    v0.19.2 — Screen-to-Component Binding Map

v0.19.2 may define how screen placeholders compose safe component placeholders only if the map remains:

- internal,
- synthetic,
- non-clinical,
- source-governed,
- no real patient data,
- no DICOM/HRCT/report/PACS/EHR,
- no diagnosis,
- no treatment,
- no clinical validation,
- no patient-facing use,
- no public readiness,
- no product readiness,
- no MDD replacement.

Next-step rule:

> v0.19.2 may map screens to components, not clinical UI actions.

---

## 18. Governance Statement

This document records v0.19.1 route-to-screen binding map.

It does not implement a clinical product.

It does not diagnose.  
It does not treat.  
It does not validate clinical performance.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not exclude mimics.  
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
It does not replace clinicians, radiologists, pulmonologists, rheumatologists, pathologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.1 discipline is:

> “Bind navigation safely without creating clinical workflow.”

The final v0.19.1 boundary is:

> “Routes may lead to safe screens; they must not lead to clinical authority.”
