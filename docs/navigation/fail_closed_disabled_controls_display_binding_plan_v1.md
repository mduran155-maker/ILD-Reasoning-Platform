# ILD Reasoning Platform — Fail-Closed / Disabled Controls Display Binding Plan v1

Version: v0.19.6  
Status: static_wiring_plan  
Scope: Fail-closed and disabled controls display binding plan after v0.19.5  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.19.6:

- Fail-Closed / Disabled Controls Display Binding Plan.

v0.19.6 follows:

- v0.19.0 — Static Internal Demo Wiring Entry Gate,
- v0.19.1 — Route-to-Screen Binding Map,
- v0.19.2 — Screen-to-Component Binding Map,
- v0.19.3 — Clinical Reasoning Re-Entry Doctrine / Non-Autonomous Diagnostic Reasoning Boundary,
- v0.19.4 — Component-to-Synthetic ILD Reasoning Fixture Binding Map,
- v0.19.5 — Safety / Authority / No-Decision Placement Map,
- v0.18.9 — Local Prototype Skeleton Materialization Structural Seal,
- checkpoint-v0.18 — Project Status / Roadmap Checkpoint after v0.18.

v0.19.6 defines how fail-closed stop-states and disabled clinical controls should be displayed in the static internal demo.

This step must preserve two things at the same time:

1. Unsafe actions must stop.
2. The user must still understand the safe clinical reasoning path that remains available.

This step does not create clinical override behavior.

It does not create proceed-anyway behavior.

It does not create hidden clinical buttons.

It does not create diagnosis controls.

It does not create rule-out controls.

It does not create probability controls.

It does not create treatment controls.

It does not create test-order controls.

It does not create procedure controls.

It does not create follow-up controls.

It does not create triage controls.

It does not create patient-facing controls.

It does not create clinical validation controls.

It does not create product/public release controls.

It does not create MDD final consensus controls.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.6 principle is:

> “Stop unsafe paths while preserving safe reasoning paths.”

The permanent boundary is:

> “Fail-closed is a stop-state; disabled controls are not hidden clinical features.”

---

## 2. Required Previous State

v0.19.6 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.19.0 entry gate exists | true |
| v0.19.1 route-to-screen binding map exists | true |
| v0.19.2 screen-to-component binding map exists | true |
| v0.19.3 clinical reasoning re-entry doctrine exists | true |
| v0.19.4 component-to-synthetic ILD reasoning fixture binding map exists | true |
| v0.19.5 safety / authority / no-decision placement map exists | true |
| v0.18.9 structural seal exists | true |
| checkpoint-v0.18 exists | true |
| Local prototype skeleton is materialized | true |
| Expected prototype file count remains 191 before v0.19.6 | true |
| Working tree before v0.19.6 is clean | true |
| Authority envelope preserved for current phase | true |
| No-decision object preserved for current phase | true |
| No real patient data opened | true |
| No deidentified real patient data opened | true |
| No DICOM/HRCT/report/PACS/EHR opened | true |
| No clinical validation opened | true |
| No autonomous final diagnosis opened | true |
| No autonomous rule-out opened | true |
| Treatment authority remains none | true |
| Patient-facing use remains not_allowed | true |
| Public readiness remains false | true |
| Product readiness remains false | true |
| MDD replacement remains blocked | true |

Dependency rule:

> v0.19.6 may display only sealed fail-closed and disabled-control placeholders under the v0.19.3 doctrine.

---

## 3. Doctrine Applied

v0.19.3 clarified that the product should not become merely a generic safety layer.

v0.19.4 restored synthetic ILD reasoning value through fixture binding.

v0.19.5 placed safety boundaries without burying clinical reasoning value.

v0.19.6 applies the same correction to fail-closed and disabled-control displays.

Therefore, fail-closed displays must not simply say:

- “blocked,”
- “not allowed,”
- “no clinical reasoning.”

They should explain:

- what unsafe authority was attempted,
- why it must stop,
- which safe reasoning surface remains available,
- which evidence gap, mimic, overlap, source status, or review path should remain visible.

Doctrine display rule:

> Stop the unsafe action, but keep the safe reasoning question alive.

---

## 4. Global Authority Envelope Preserved for Current Phase

The authority envelope remains preserved for the current phase:

| Field | Required State |
|---|---|
| diagnostic_authority | none_current_phase |
| autonomous_final_diagnosis | blocked |
| autonomous_disease_exclusion | blocked |
| calibrated_diagnostic_probability | not_opened |
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

> Fail-closed and disabled-control displays grant no clinical authority.

---

## 5. No-Decision Object Preserved for Current Phase

The no-decision object remains preserved for the current phase:

| Field | Required State |
|---|---|
| final_diagnosis_made | false |
| disease_excluded_autonomously | false |
| mimic_excluded_autonomously | false |
| treatment_selected | false |
| test_ordered | false |
| procedure_decided | false |
| follow_up_scheduled | false |
| triage_assigned | false |
| mdd_consensus_generated | false |
| patient_facing_output_generated | false |

No-decision rule:

> A blocked action may be displayed, but no clinical decision may be made.

---

## 6. Available Fail-Closed Placeholders

v0.19.6 may display the following materialized fail-closed placeholders:

| Fail-Closed Placeholder | Display Meaning | Safety State |
|---|---|---|
| unsafe_route_attempt_stub.json | unsafe route was attempted | stop_state |
| real_patient_data_attempt_stub.json | real patient data attempt was blocked | stop_state |
| deidentified_patient_data_attempt_stub.json | deidentified patient data attempt was blocked | stop_state |
| dicom_report_import_attempt_stub.json | DICOM/report import attempt was blocked | stop_state |
| pacs_ehr_connection_attempt_stub.json | PACS/EHR connection attempt was blocked | stop_state |
| diagnosis_action_attempt_stub.json | autonomous diagnosis action was blocked | stop_state |
| patient_facing_leak_attempt_stub.json | patient-facing output attempt was blocked | stop_state |
| validation_readiness_overclaim_stub.json | validation/readiness overclaim was blocked | stop_state |
| unsafe_copy_export_attempt_stub.json | unsafe copy/export attempt was blocked | stop_state |
| authority_no_decision_missing_stub.json | authority/no-decision missing state was blocked | stop_state |
| unsafe_visual_semantics_stub.json | unsafe visual semantics were blocked | stop_state |
| unsafe_fixture_binding_stub.json | unsafe fixture binding was blocked | stop_state |
| audit_correctness_claim_stub.json | audit correctness overclaim was blocked | stop_state |
| ui_safety_repair_required_stub.json | UI safety repair is required | stop_until_repaired |
| ui_safety_revalidation_stub.json | UI safety revalidation is required | stop_until_revalidated |
| fail_closed_stub_registry.json | fail-closed registry | registry_only |

Fail-closed availability rule:

> Fail-closed placeholders may be displayed only as stop-state explanations.

---

## 7. Available Disabled Control Placeholders

v0.19.6 may display the following materialized disabled-control placeholders:

| Disabled Control Placeholder | Display Meaning | Safety State |
|---|---|---|
| disabled_clinical_control_registry.json | registry of disabled clinical controls | non_activatable |
| disabled_control_copy_mapping.json | disabled control copy mapping | non_activatable |
| disabled_data_import_controls.json | disabled data import controls | non_activatable |
| disabled_diagnosis_action_controls.json | disabled diagnosis action controls | non_activatable |
| disabled_patient_facing_controls.json | disabled patient-facing controls | non_activatable |
| disabled_validation_readiness_controls.json | disabled validation/readiness controls | non_activatable |
| disabled_mdd_consensus_controls.json | disabled MDD consensus controls | non_activatable |

Disabled control availability rule:

> Disabled controls may explain blocked authority, but they must not behave like hidden future clinical buttons.

---

## 8. Fail-Closed Display Binding Map

The sealed fail-closed display binding map is:

| Stop-State | Display Component | Display Surface | Safe Reasoning Continuation |
|---|---|---|---|
| unsafe route attempt | red_team_fail_closed_panel + audit_trace_panel | red_team_fail_closed_screen | return to safety_reference_screen |
| real patient data attempt | red_team_fail_closed_panel + safety_badge | prototype_boundary_screen or safety_reference_screen | use synthetic_demo_case_registry only |
| deidentified patient data attempt | red_team_fail_closed_panel + safety_badge | prototype_boundary_screen or safety_reference_screen | use fictional synthetic fixtures only |
| DICOM/report import attempt | red_team_fail_closed_panel + source_status_badge | demo_intake_review_screen | show source-status limitation, not import |
| PACS/EHR connection attempt | red_team_fail_closed_panel + audit_trace_panel | safety_reference_screen | show no external connection boundary |
| diagnosis action attempt | red_team_fail_closed_panel + no_decision_object_card | reasoning_map_screen | redirect to reasoning_map + review_prompt |
| disease rule-out attempt | red_team_fail_closed_panel + mimic_visibility_panel_card | mimic_visibility_panel_screen | keep mimic visible, no autonomous exclusion |
| probability/ranking attempt | red_team_fail_closed_panel + confidence_limiter_panel | confidence_limiter_panel_screen | show confidence limitation, no calibrated probability |
| treatment/action attempt | red_team_fail_closed_panel + authority_envelope_card | review_prompt_panel_screen | show treatment authority none |
| patient-facing leak attempt | red_team_fail_closed_panel + visual_safety_label | safe_export_preview_screen | keep export internal and non-patient-facing |
| validation/readiness overclaim | red_team_fail_closed_panel + audit_trace_panel | audit_trace_screen | show scaffold-safety-only validation |
| unsafe copy/export attempt | red_team_fail_closed_panel + safe_export_preview_panel | safe_export_preview_screen | block unsafe export and require repair |
| authority/no-decision missing | red_team_fail_closed_panel + authority_envelope_card + no_decision_object_card | safety_reference_screen | restore authority/no-decision visibility |
| unsafe visual semantics | red_team_fail_closed_panel + visual_safety_label | visual_safety_label_screen | repair visual safety label |
| unsafe fixture binding | red_team_fail_closed_panel + audit_trace_panel | audit_trace_screen | return to synthetic fixture boundary |
| audit correctness claim | red_team_fail_closed_panel + audit_trace_panel | audit_trace_screen | show traceability-only audit |
| UI safety repair required | red_team_fail_closed_panel + review_prompt_card | red_team_fail_closed_screen | repair unsafe wording before display |
| UI safety revalidation required | red_team_fail_closed_panel + audit_trace_panel | red_team_fail_closed_screen | revalidate scaffold safety before display |

Fail-closed binding rule:

> Every unsafe stop-state must preserve a safe reasoning continuation path without allowing the unsafe action.

---

## 9. Disabled Controls Display Binding Map

The sealed disabled-control display binding map is:

| Disabled Control Category | Display Component | Display Surface | Explanation |
|---|---|---|---|
| data import controls | authority_envelope_card + visual_safety_label | safety_reference_screen | real/deidentified/DICOM/report data import is not opened |
| diagnosis action controls | no_decision_object_card + confidence_limiter_panel | reasoning_map_screen | autonomous final diagnosis is blocked |
| rule-out controls | mimic_visibility_panel_card + no_decision_object_card | mimic_visibility_panel_screen | mimics remain visible; no autonomous exclusion |
| probability/ranking controls | confidence_limiter_panel + overlap_panel_card | overlap_panel_screen | no calibrated probability or ranking in current phase |
| treatment/order/procedure controls | authority_envelope_card + review_prompt_card | review_prompt_panel_screen | treatment and action authority are none |
| follow-up/triage controls | authority_envelope_card + review_prompt_card | review_prompt_panel_screen | follow-up and triage authority are none |
| patient-facing controls | visual_safety_label + safe_export_preview_panel | safe_export_preview_screen | patient-facing use is not allowed |
| validation/readiness controls | audit_trace_panel + safety_badge | audit_trace_screen | validation is scaffold-safety-only, not clinical performance |
| MDD consensus controls | review_prompt_card + no_decision_object_card | review_prompt_panel_screen | MDD preparation is allowed; final consensus is blocked |

Disabled-control binding rule:

> Disabled controls explain boundaries; they are not dormant clinical features.

---

## 10. Corrected Display Language

Fail-closed and disabled-control displays should use corrected doctrine language.

Preferred phrases:

- “This action is outside the current prototype authority.”
- “The safe reasoning surface remains available.”
- “Mimic visibility is preserved; autonomous exclusion is blocked.”
- “Confidence limitation is shown; calibrated probability is not opened.”
- “MDD preparation is supported; MDD consensus is not generated.”
- “Export preview is internal and non-clinical.”
- “Audit records scaffold traceability, not clinical correctness.”
- “This path requires repair and revalidation before display.”

Avoid phrases:

- “No clinical reasoning is allowed.”
- “This platform does not support reasoning.”
- “Only safety blocking is available.”
- “Clinical value is out of scope.”
- “Proceed anyway.”
- “Override.”
- “Enable hidden clinical feature.”
- “Continue with diagnosis.”
- “Export clinical report.”

Display language rule:

> Stop-state language must reduce unsafe authority while preserving reasoning usefulness.

---

## 11. Stop-State Severity Tiers

v0.19.6 defines stop-state severity tiers.

| Tier | Meaning | Examples | Required Behavior |
|---|---|---|---|
| Tier 1 | boundary clarification | missing safety label, unclear copy | repair_required |
| Tier 2 | unsafe prototype meaning | unsafe visual semantics, unsafe fixture binding | fail_closed_until_repaired |
| Tier 3 | clinical authority attempt | diagnosis, rule-out, treatment, patient-facing output | hard_stop |
| Tier 4 | forbidden data/integration attempt | real patient data, DICOM, PACS/EHR | hard_stop_and_audit |
| Tier 5 | overclaim attempt | validation/product/public/MDD consensus claim | hard_stop_and_revalidation |

Severity rule:

> Higher-risk unsafe meanings must stop harder and require clearer audit visibility.

---

## 12. Safe Reasoning Continuation Paths

A blocked action should not leave the user in a dead end.

The display should redirect toward a safe reasoning surface.

| Blocked Attempt | Safe Continuation |
|---|---|
| diagnosis attempt | reasoning map + confidence limiter + review prompt |
| rule-out attempt | mimic visibility + overlap + review prompt |
| probability/ranking attempt | confidence limiter + missing evidence + source status |
| treatment/action attempt | review prompt + authority envelope |
| patient-facing export attempt | safe export preview + visual safety label |
| real data attempt | synthetic case selector + safety reference |
| DICOM/report import attempt | source status limitation + missing evidence |
| clinical validation overclaim | audit trace + scaffold-safety validation boundary |
| MDD consensus attempt | MDD preparation + no-decision object |

Safe continuation rule:

> Blocked clinical authority should redirect to safe reasoning, not to silence.

---

## 13. Hidden Feature Prevention

Disabled controls must not be represented as:

- hidden feature flags,
- future buttons,
- locked premium features,
- greyed clinical tools awaiting activation,
- clinical actions behind permissions,
- developer-only diagnosis controls,
- future treatment controls,
- internal patient-facing toggles.

Disabled controls must be represented as:

- explicitly blocked authority,
- current-phase non-capability,
- safety education,
- non-activatable display,
- audit-visible boundary.

Hidden feature rule:

> A disabled clinical control is a boundary marker, not a feature waiting to be unlocked.

---

## 14. Audit Visibility Boundary

Fail-closed and disabled-control display events may be audit-visible only as scaffold traceability.

Allowed audit events:

- fail-closed state displayed,
- disabled control boundary displayed,
- unsafe route blocked,
- unsafe fixture binding blocked,
- unsafe copy/export blocked,
- authority/no-decision missing state blocked,
- repair required,
- revalidation required.

Blocked audit meanings:

- clinical correctness proof,
- diagnostic validation,
- treatment correctness,
- patient care audit,
- PACS audit,
- EHR audit,
- regulatory evidence,
- product readiness proof.

Audit boundary rule:

> Audit may record that an unsafe action was blocked; it must not prove that a clinical conclusion is correct.

---

## 15. Current-Phase Boundary

v0.19.6 does not open:

| Capability | State |
|---|---|
| real patient data | not_allowed |
| deidentified patient data | not_allowed |
| DICOM/HRCT/report/PACS/EHR | not_opened |
| autonomous final diagnosis | blocked |
| autonomous rule-out | blocked |
| calibrated probability | not_opened |
| treatment/order/procedure/follow-up/triage | none |
| patient-facing output | not_allowed |
| clinical validation | not_opened |
| diagnostic performance claim | not_allowed |
| public readiness | false |
| product readiness | false |
| MDD replacement | blocked |

Current-phase rule:

> v0.19.6 improves display behavior only; it opens no new clinical capability.

---

## 16. Prototype File Count Preservation

v0.19.6 does not add files inside the prototype skeleton.

The v0.18 sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count preservation rule:

> v0.19.6 records a display binding plan in docs only; the materialized prototype skeleton remains unchanged.

---

## 17. What v0.19.6 Allows

v0.19.6 allows only:

- fail-closed display binding,
- disabled-control display binding,
- stop-state severity tiering,
- safe reasoning continuation mapping,
- hidden feature prevention rules,
- audit traceability rules,
- corrected fail-closed language,
- corrected disabled-control language.

Allowed-use rule:

> v0.19.6 improves unsafe-path display clarity without opening unsafe-path execution.

---

## 18. What v0.19.6 Blocks

v0.19.6 blocks:

- proceed-anyway behavior,
- override behavior,
- hidden clinical feature behavior,
- diagnosis action controls,
- rule-out action controls,
- probability/ranking controls,
- treatment/order/procedure/follow-up/triage controls,
- patient-facing controls,
- clinical validation controls,
- product/public readiness controls,
- MDD final consensus controls.

Blocked-use rule:

> Displaying a blocked control must never imply that the blocked authority is available.

---

## 19. Acceptance Criteria

v0.19.6 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.19.0 dependency listed | true |
| v0.19.1 dependency listed | true |
| v0.19.2 dependency listed | true |
| v0.19.3 doctrine dependency listed | true |
| v0.19.4 reasoning fixture binding dependency listed | true |
| v0.19.5 placement map dependency listed | true |
| v0.18.9 dependency listed | true |
| checkpoint-v0.18 dependency listed | true |
| fail-closed display binding map defined | true |
| disabled controls display binding map defined | true |
| corrected display language defined | true |
| stop-state severity tiers defined | true |
| safe reasoning continuation paths defined | true |
| hidden feature prevention defined | true |
| audit visibility boundary defined | true |
| fail-closed remains stop-state-only | true |
| disabled controls remain non-activatable | true |
| no proceed-anyway behavior opened | true |
| no clinical override opened | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no calibrated probability opened | true |
| no treatment/order/procedure/follow-up/triage opened | true |
| no patient-facing output opened | true |
| no clinical validation opened | true |
| no MDD replacement opened | true |
| prototype file count remains 191 | true |

Acceptance rule:

> v0.19.6 is valid only if fail-closed and disabled-control displays stop unsafe authority while preserving safe reasoning continuity.

---

## 20. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> This display binding plan is docs-only and must not mutate the prototype skeleton.

---

## 21. Next Step

The next recommended step is:

    v0.19.7 — Audit / Export Preview / Red-Team Walkthrough Binding Plan

v0.19.7 should define how audit traceability, safe export preview, and red-team containment appear together in the static internal demo.

v0.19.7 must remain:

- internal,
- synthetic,
- non-clinical,
- no real patient data,
- no deidentified patient data,
- no DICOM/HRCT/report/PACS/EHR,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no treatment authority,
- no clinical validation opened,
- no patient-facing use,
- no public readiness,
- no product readiness,
- no MDD replacement.

Next-step rule:

> v0.19.7 must show traceability, preview, and red-team containment without creating report generation or validation proof.

---

## 22. Governance Statement

This document records v0.19.6 fail-closed and disabled controls display binding plan.

It does not implement a clinical product.

It does not diagnose autonomously.  
It does not rule out disease autonomously.  
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
It does not replace clinicians, radiologists, pulmonologists, rheumatologists, pathologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.6 discipline is:

> “Stop unsafe actions while preserving safe reasoning continuity.”

The final v0.19.6 boundary is:

> “Blocked authority stops; clinical reasoning visibility remains.”
