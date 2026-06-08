# ILD Reasoning Platform — Screen-to-Component Binding Map v1

Version: v0.19.2  
Status: static_wiring_plan  
Scope: Static screen-to-component binding map after v0.19.1  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.19.2:

- Screen-to-Component Binding Map.

v0.19.2 follows:

- v0.19.0 — Static Internal Demo Wiring Entry Gate,
- v0.19.1 — Route-to-Screen Binding Map,
- v0.18.9 — Local Prototype Skeleton Materialization Structural Seal,
- checkpoint-v0.18 — Project Status / Roadmap Checkpoint after v0.18.

v0.19.2 defines a static internal mapping from materialized screen placeholders to materialized component placeholders.

This step does not create a clinical UI.

It does not create clinical action controls.

It does not create diagnosis selection.

It does not create disease exclusion.

It does not create probability display.

It does not create disease ranking.

It does not create treatment selection.

It does not create test-order controls.

It does not create procedure controls.

It does not create follow-up controls.

It does not create triage controls.

It does not create patient-facing output.

It does not create clinical validation UI.

It does not create product-ready UI.

It does not replace MDD.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.2 principle is:

> “Compose screens from safe components, not clinical controls.”

The permanent boundary is:

> “A screen-to-component map is display composition, not clinical action design.”

---

## 2. Required Previous State

v0.19.2 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.19.0 entry gate exists | true |
| v0.19.1 route-to-screen binding map exists | true |
| v0.18.9 structural seal exists | true |
| checkpoint-v0.18 exists | true |
| Local prototype skeleton is materialized | true |
| Expected prototype file count remains 191 before v0.19.2 | true |
| Working tree before v0.19.2 is clean | true |
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

> v0.19.2 may bind only sealed screen placeholders to sealed component placeholders.

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

> Screen-to-component binding grants no clinical authority.

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

> Screen-to-component binding may organize safe visibility, but it must not make or imply clinical decisions.

---

## 5. Available Screen Placeholders

v0.19.2 may bind the following materialized screen placeholders:

| Screen Placeholder | Status |
|---|---|
| prototype/screens/prototype_boundary_screen.md | available |
| prototype/screens/synthetic_case_selector_screen.md | available |
| prototype/screens/demo_intake_review_screen.md | available |
| prototype/screens/reasoning_map_screen.md | available |
| prototype/screens/evidence_panel_hub_screen.md | available |
| prototype/screens/missing_evidence_panel_screen.md | available |
| prototype/screens/mimic_visibility_panel_screen.md | available |
| prototype/screens/overlap_panel_screen.md | available |
| prototype/screens/source_status_panel_screen.md | available |
| prototype/screens/confidence_limiter_panel_screen.md | available |
| prototype/screens/review_prompt_panel_screen.md | available |
| prototype/screens/safe_export_preview_screen.md | available |
| prototype/screens/red_team_fail_closed_screen.md | available |
| prototype/screens/red_team_scenario_detail_screen.md | available |
| prototype/screens/audit_trace_screen.md | available |
| prototype/screens/safety_reference_screen.md | available |
| prototype/screens/authority_envelope_screen.md | available |
| prototype/screens/no_decision_object_screen.md | available |
| prototype/screens/visual_safety_label_screen.md | available |

Screen availability rule:

> Available screens are safe visibility placeholders only.

---

## 6. Available Component Placeholders

v0.19.2 may bind the following materialized component placeholders:

| Component Placeholder | Status |
|---|---|
| prototype/components/prototype_boundary_banner.md | available |
| prototype/components/safety_badge.md | available |
| prototype/components/authority_envelope_card.md | available |
| prototype/components/no_decision_object_card.md | available |
| prototype/components/synthetic_case_card.md | available |
| prototype/components/reasoning_map_panel.md | available |
| prototype/components/evidence_panel_card.md | available |
| prototype/components/missing_evidence_panel_card.md | available |
| prototype/components/mimic_visibility_panel_card.md | available |
| prototype/components/overlap_panel_card.md | available |
| prototype/components/source_status_badge.md | available |
| prototype/components/confidence_limiter_panel.md | available |
| prototype/components/review_prompt_card.md | available |
| prototype/components/safe_export_preview_panel.md | available |
| prototype/components/red_team_fail_closed_panel.md | available |
| prototype/components/audit_trace_panel.md | available |
| prototype/components/visual_safety_label.md | available |

Component availability rule:

> Available components are non-clinical display placeholders only.

---

## 7. Static Screen-to-Component Binding Map

The sealed static screen-to-component binding map is:

| Screen Placeholder | Component Placeholders | Binding Meaning | Safety State |
|---|---|---|---|
| prototype/screens/prototype_boundary_screen.md | prototype_boundary_banner; safety_badge; authority_envelope_card; no_decision_object_card; visual_safety_label | shows root prototype boundary | boundary_visible |
| prototype/screens/synthetic_case_selector_screen.md | prototype_boundary_banner; safety_badge; synthetic_case_card; source_status_badge; review_prompt_card | shows fictional demo case selection | synthetic_only |
| prototype/screens/demo_intake_review_screen.md | safety_badge; synthetic_case_card; evidence_panel_card; missing_evidence_panel_card; review_prompt_card | shows synthetic intake review | no_patient_data |
| prototype/screens/reasoning_map_screen.md | safety_badge; reasoning_map_panel; evidence_panel_card; mimic_visibility_panel_card; overlap_panel_card; confidence_limiter_panel; review_prompt_card | shows reasoning structure | no_diagnosis |
| prototype/screens/evidence_panel_hub_screen.md | safety_badge; evidence_panel_card; missing_evidence_panel_card; mimic_visibility_panel_card; overlap_panel_card; source_status_badge | shows evidence visibility hub | source_governed |
| prototype/screens/missing_evidence_panel_screen.md | safety_badge; missing_evidence_panel_card; source_status_badge; confidence_limiter_panel; review_prompt_card | shows missing evidence visibility | uncertainty_preserved |
| prototype/screens/mimic_visibility_panel_screen.md | safety_badge; mimic_visibility_panel_card; overlap_panel_card; source_status_badge; review_prompt_card | shows mimic visibility | no_exclusion |
| prototype/screens/overlap_panel_screen.md | safety_badge; overlap_panel_card; mimic_visibility_panel_card; confidence_limiter_panel | shows overlap visibility | no_ranking |
| prototype/screens/source_status_panel_screen.md | safety_badge; source_status_badge; evidence_panel_card; review_prompt_card | shows source status visibility | no_authority_claim |
| prototype/screens/confidence_limiter_panel_screen.md | safety_badge; confidence_limiter_panel; no_decision_object_card; review_prompt_card | shows confidence limitation | no_probability |
| prototype/screens/review_prompt_panel_screen.md | safety_badge; review_prompt_card; authority_envelope_card; no_decision_object_card | shows human review requirement | review_required |
| prototype/screens/safe_export_preview_screen.md | safety_badge; safe_export_preview_panel; source_status_badge; audit_trace_panel; review_prompt_card | shows safe export preview | not_clinical_report |
| prototype/screens/red_team_fail_closed_screen.md | safety_badge; red_team_fail_closed_panel; audit_trace_panel; review_prompt_card | shows red-team fail-closed state | quarantine_only |
| prototype/screens/red_team_scenario_detail_screen.md | safety_badge; red_team_fail_closed_panel; audit_trace_panel; source_status_badge; review_prompt_card | shows red-team scenario containment | non_reusable_unsafe_output |
| prototype/screens/audit_trace_screen.md | safety_badge; audit_trace_panel; source_status_badge; no_decision_object_card | shows audit traceability | traceability_only |
| prototype/screens/safety_reference_screen.md | safety_badge; authority_envelope_card; no_decision_object_card; visual_safety_label; prototype_boundary_banner | shows safety reference hub | authority_boundary_visible |
| prototype/screens/authority_envelope_screen.md | authority_envelope_card; safety_badge; visual_safety_label | shows authority envelope | no_clinical_authority |
| prototype/screens/no_decision_object_screen.md | no_decision_object_card; safety_badge; visual_safety_label | shows no-decision object | no_decision |
| prototype/screens/visual_safety_label_screen.md | visual_safety_label; safety_badge; prototype_boundary_banner | shows visual safety label | non_clinical_boundary_visible |

Binding map rule:

> Every screen binds only to safe non-clinical component placeholders.

---

## 8. Component Binding Semantics

Each component binding is static.

Each component binding is internal.

Each component binding is synthetic.

Each component binding is non-clinical.

Each component binding must preserve:

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

Component binding semantic rule:

> Static component binding is display composition, not clinical UI functionality.

---

## 9. Required Safety Component Coverage

Every primary screen must include at least one of the following safety-visible components:

- safety_badge,
- authority_envelope_card,
- no_decision_object_card,
- visual_safety_label,
- prototype_boundary_banner,
- review_prompt_card.

Safety coverage rule:

> Every screen must visibly resist authority confusion.

---

## 10. Component Interaction Boundary

v0.19.2 does not open interactive clinical controls.

Allowed component interactions:

| Interaction Type | State |
|---|---|
| static display | allowed |
| internal synthetic navigation hint | allowed |
| safety explanation expansion | allowed_static_placeholder |
| review-required reminder display | allowed |
| fail-closed display | allowed |
| audit trace visibility | allowed_traceability_only |

Blocked component interactions:

| Interaction Type | State |
|---|---|
| diagnose button | blocked |
| rule-out button | blocked |
| probability slider | blocked |
| disease ranking control | blocked |
| treatment selection | blocked |
| test order button | blocked |
| procedure recommendation button | blocked |
| follow-up scheduler | blocked |
| triage selector | blocked |
| patient-facing export button | blocked |
| clinical validation run button | blocked |
| product publish button | blocked |
| MDD final consensus button | blocked |

Component interaction rule:

> Components may display safe structure, but must not activate clinical actions.

---

## 11. Blocked Component Families

The following component families remain blocked:

- patient data component,
- DICOM viewer component,
- HRCT viewer component,
- report parser component,
- PACS connector component,
- EHR connector component,
- diagnosis component,
- final impression component,
- likely diagnosis component,
- rule-out component,
- exclusion component,
- probability component,
- ranking component,
- treatment component,
- order component,
- procedure component,
- follow-up component,
- triage component,
- patient-facing component,
- clinical validation component,
- diagnostic performance component,
- public demo component,
- product release component,
- MDD final consensus component,
- MDD replacement component.

Blocked component rule:

> A blocked component family cannot be introduced through naming, binding, hidden state, or future TODO notes.

---

## 12. Fail-Closed Component Boundary

Any attempted screen binding to a component outside the static allowed component set must fail closed.

Fail-closed component attempts include:

- unknown component,
- patient component,
- DICOM component,
- report component,
- PACS/EHR component,
- diagnosis component,
- treatment component,
- patient-facing component,
- clinical validation component,
- product/public component,
- MDD final consensus component.

Fail-closed component rule:

> Unknown or unsafe components are stop-states, not warnings.

---

## 13. Audit Visibility Boundary

Screen/component display may be audit-visible only as scaffold traceability.

Allowed audit meanings:

- screen placeholder displayed,
- component placeholder displayed,
- safety component displayed,
- synthetic fixture reference prepared,
- fail-closed component blocked,
- red-team component contained.

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

> Screen/component audit visibility records scaffold display only.

---

## 14. What v0.19.2 Allows

v0.19.2 allows only:

- static map from screen placeholders to component placeholders,
- declaration of safety component coverage,
- declaration of blocked component families,
- declaration of component interaction boundaries,
- declaration of fail-closed component behavior,
- declaration of audit traceability boundary.

Allowed-use rule:

> v0.19.2 creates safe internal display composition plan only.

---

## 15. What v0.19.2 Blocks

v0.19.2 blocks:

- clinical UI actions,
- real patient components,
- DICOM/HRCT components,
- report parser components,
- PACS/EHR components,
- diagnosis components,
- probability/ranking components,
- treatment components,
- test-order components,
- procedure components,
- follow-up components,
- triage components,
- patient-facing components,
- clinical validation components,
- product/public components,
- MDD final consensus components.

Blocked-use rule:

> Screen-to-component binding must not become clinical UI architecture.

---

## 16. Prototype File Count Preservation

v0.19.2 does not add files inside the prototype skeleton.

The v0.18 sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count preservation rule:

> v0.19.2 records a wiring map in docs only; the materialized prototype skeleton remains unchanged.

---

## 17. Acceptance Criteria

v0.19.2 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.19.0 dependency listed | true |
| v0.19.1 dependency listed | true |
| v0.18.9 dependency listed | true |
| checkpoint-v0.18 dependency listed | true |
| all 19 screen placeholders mapped | true |
| all screen mappings target safe component placeholders | true |
| all 17 component placeholders referenced where appropriate | true |
| every screen has visible safety coverage | true |
| no patient component mapped | true |
| no DICOM/HRCT/report/PACS/EHR component mapped | true |
| no diagnosis/treatment/action component mapped | true |
| no patient-facing component mapped | true |
| no clinical validation component mapped | true |
| no public/product component mapped | true |
| no MDD final consensus component mapped | true |
| component interactions limited to display/safety/traceability | true |
| fail-closed component boundary defined | true |
| audit visibility remains traceability-only | true |
| prototype file count remains 191 | true |
| authority envelope preserved | true |
| no-decision object preserved | true |
| no clinical UI opened | true |
| no real patient data opened | true |
| no diagnostic authority opened | true |
| no treatment authority opened | true |
| no patient-facing use opened | true |
| no public readiness opened | true |
| no product readiness opened | true |
| no MDD replacement opened | true |

Acceptance rule:

> v0.19.2 is valid only if screen-to-component binding remains safe internal display scaffolding.

---

## 18. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short

    Get-ChildItem prototype/screens -File | Measure-Object
    Get-ChildItem prototype/components -File | Measure-Object
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected counts:

    prototype/screens file count = 19
    prototype/components file count = 17
    prototype total file count = 191

Verification rule:

> Screen and component counts support scaffold completeness only; they do not certify clinical UI.

---

## 19. Next Step

The next recommended step is:

    v0.19.3 — Component-to-Synthetic-Fixture Binding Map

v0.19.3 may define how component placeholders reference fictional synthetic fixture placeholders only if the map remains:

- internal,
- synthetic,
- non-clinical,
- source-governed,
- no real patient data,
- no deidentified patient data,
- no DICOM/HRCT/report/PACS/EHR,
- no diagnosis,
- no treatment,
- no clinical validation,
- no patient-facing use,
- no public readiness,
- no product readiness,
- no MDD replacement.

Next-step rule:

> v0.19.3 may map components to fictional fixtures, not clinical case data.

---

## 20. Governance Statement

This document records v0.19.2 screen-to-component binding map.

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

The v0.19.2 discipline is:

> “Bind screens to safe components without creating clinical UI.”

The final v0.19.2 boundary is:

> “Screens may compose safe displays; they must not compose clinical authority.”
