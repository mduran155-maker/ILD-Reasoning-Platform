# ILD Reasoning Platform — Safety / Authority / No-Decision Placement Map v1

Version: v0.19.5  
Status: static_wiring_plan  
Scope: Safety, authority, no-decision, and non-autonomous reasoning boundary placement map after v0.19.4  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.19.5:

- Safety / Authority / No-Decision Placement Map.

v0.19.5 follows:

- v0.19.0 — Static Internal Demo Wiring Entry Gate,
- v0.19.1 — Route-to-Screen Binding Map,
- v0.19.2 — Screen-to-Component Binding Map,
- v0.19.3 — Clinical Reasoning Re-Entry Doctrine / Non-Autonomous Diagnostic Reasoning Boundary,
- v0.19.4 — Component-to-Synthetic ILD Reasoning Fixture Binding Map,
- v0.18.9 — Local Prototype Skeleton Materialization Structural Seal,
- checkpoint-v0.18 — Project Status / Roadmap Checkpoint after v0.18.

v0.19.5 defines where safety labels, authority boundaries, no-decision reminders, review-required notices, synthetic-only labels, and non-autonomous reasoning boundaries must appear across the static internal demo.

This step intentionally balances two needs:

1. Safety must remain visible enough to prevent authority confusion.
2. Clinical reasoning value must remain visible enough that the platform does not become a generic safety wrapper.

This step does not create clinical workflow.

It does not create autonomous final diagnosis.

It does not create autonomous disease exclusion.

It does not create calibrated diagnostic probability.

It does not create treatment authority.

It does not create test-order authority.

It does not create procedure authority.

It does not create follow-up authority.

It does not create triage authority.

It does not create patient-facing output.

It does not create clinical validation.

It does not create diagnostic performance claims.

It does not create real patient data intake.

It does not create deidentified real patient data intake.

It does not create DICOM import.

It does not create HRCT import.

It does not create report import.

It does not create PACS connection.

It does not create EHR connection.

It does not replace MDD.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.5 principle is:

> “Place safety visibly without burying clinical reasoning value.”

The permanent boundary is:

> “Safety is the guardrail; clinical reasoning is the destination.”

---

## 2. Required Previous State

v0.19.5 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.19.0 entry gate exists | true |
| v0.19.1 route-to-screen binding map exists | true |
| v0.19.2 screen-to-component binding map exists | true |
| v0.19.3 clinical reasoning re-entry doctrine exists | true |
| v0.19.4 component-to-synthetic ILD reasoning fixture binding map exists | true |
| v0.18.9 structural seal exists | true |
| checkpoint-v0.18 exists | true |
| Local prototype skeleton is materialized | true |
| Expected prototype file count remains 191 before v0.19.5 | true |
| Working tree before v0.19.5 is clean | true |
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

> v0.19.5 may place only safety and authority boundaries for the sealed static internal synthetic demo.

---

## 3. Doctrine Applied from v0.19.3 and v0.19.4

v0.19.3 clarified that scaffold-phase “no diagnosis / no probability / no rule-out” statements are not permanent product philosophy.

v0.19.4 reconnected component wiring to synthetic ILD reasoning fixture roles.

v0.19.5 applies both corrections.

This means safety placement must not say only:

- no diagnosis,
- no probability,
- no clinical reasoning.

Instead, safety placement must communicate the more precise boundary:

- no autonomous final diagnosis,
- no autonomous disease exclusion,
- no treatment authority,
- no patient-facing clinical conclusion,
- no clinical deployment or claims without validation,
- clinician-facing reasoning support may be developed under governance.

Doctrine placement rule:

> Safety language must prevent authority confusion without erasing the platform’s clinician-facing reasoning purpose.

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

Authority placement rule:

> Authority boundaries must be visible where reasoning could be mistaken for clinical decision-making.

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

No-decision placement rule:

> No-decision reminders must appear wherever the user could mistake reasoning support for clinical closure.

---

## 6. Placement Tiers

v0.19.5 defines three placement tiers.

| Tier | Placement Meaning | Required Visibility |
|---|---|---|
| Tier 1 | global safety and authority boundary | always visible on entry / boundary / safety screens |
| Tier 2 | contextual reasoning boundary | visible on reasoning, evidence, mimic, overlap, confidence, review, and export screens |
| Tier 3 | event-specific stop or quarantine boundary | visible during fail-closed, red-team, export block, audit, and validation contexts |

Tier rule:

> Safety placement must be proportional to risk and context, not randomly repeated.

---

## 7. Required Safety Components

The following safety components are used for boundary placement:

| Component | Role |
|---|---|
| prototype_boundary_banner | global prototype boundary |
| safety_badge | compact non-clinical status marker |
| authority_envelope_card | current-phase authority limits |
| no_decision_object_card | no autonomous decision closure |
| visual_safety_label | visible non-clinical/synthetic label |
| review_prompt_card | clinician/MDD review requirement |
| confidence_limiter_panel | confidence limitation and uncertainty guard |
| red_team_fail_closed_panel | stop-state / quarantine display |
| audit_trace_panel | scaffold traceability display |

Required component rule:

> At least one safety component must be visible on every screen; high-risk screens require multiple safety components.

---

## 8. Global Safety Placement Map

The following global safety elements must be placed across the static internal demo.

| Surface | Required Placement | Meaning |
|---|---|---|
| prototype entry | prototype_boundary_banner + safety_badge + visual_safety_label | internal synthetic prototype boundary |
| safety reference | authority_envelope_card + no_decision_object_card + visual_safety_label | authority and decision absence |
| reasoning map | safety_badge + confidence_limiter_panel + review_prompt_card | reasoning support without closure |
| evidence panels | safety_badge + source_status_badge + review_prompt_card | source-governed evidence visibility |
| mimic/overlap panels | safety_badge + confidence_limiter_panel + review_prompt_card | no autonomous exclusion/ranking |
| export preview | safety_badge + safe_export_preview_panel + audit_trace_panel | preview only, not report generation |
| red-team screens | safety_badge + red_team_fail_closed_panel + audit_trace_panel | quarantine and containment |
| audit screens | safety_badge + audit_trace_panel + no_decision_object_card | traceability only, not correctness proof |

Global placement rule:

> The user must never enter a reasoning surface without seeing that the platform is non-autonomous and review-required.

---

## 9. Screen-Level Placement Map

The sealed screen-level placement map is:

| Screen | Required Safety / Authority / No-Decision Placement | Placement Purpose |
|---|---|---|
| prototype_boundary_screen | prototype_boundary_banner; safety_badge; authority_envelope_card; no_decision_object_card; visual_safety_label | establish global boundary |
| synthetic_case_selector_screen | safety_badge; synthetic_case_card; source_status_badge; review_prompt_card | synthetic-only case selection |
| demo_intake_review_screen | safety_badge; missing_evidence_panel_card; source_status_badge; review_prompt_card | no patient intake; evidence gaps visible |
| reasoning_map_screen | safety_badge; reasoning_map_panel; confidence_limiter_panel; review_prompt_card; no_decision_object_card | reasoning support without closure |
| evidence_panel_hub_screen | safety_badge; evidence_panel_card; source_status_badge; review_prompt_card | source-governed evidence visibility |
| missing_evidence_panel_screen | safety_badge; missing_evidence_panel_card; confidence_limiter_panel; review_prompt_card | missing evidence prevents premature closure |
| mimic_visibility_panel_screen | safety_badge; mimic_visibility_panel_card; overlap_panel_card; review_prompt_card | mimics remain visible; no autonomous exclusion |
| overlap_panel_screen | safety_badge; overlap_panel_card; confidence_limiter_panel; review_prompt_card | overlap visible; no ranking/probability |
| source_status_panel_screen | safety_badge; source_status_badge; evidence_panel_card; audit_trace_panel | source status visible; no authority claim |
| confidence_limiter_panel_screen | safety_badge; confidence_limiter_panel; no_decision_object_card; review_prompt_card | confidence limitation visible |
| review_prompt_panel_screen | safety_badge; review_prompt_card; authority_envelope_card; no_decision_object_card | clinician/MDD review required |
| safe_export_preview_screen | safety_badge; safe_export_preview_panel; source_status_badge; audit_trace_panel; review_prompt_card | safe preview only; not clinical report |
| red_team_fail_closed_screen | safety_badge; red_team_fail_closed_panel; audit_trace_panel; review_prompt_card | stop-state/quarantine |
| red_team_scenario_detail_screen | safety_badge; red_team_fail_closed_panel; audit_trace_panel; source_status_badge; review_prompt_card | unsafe scenario containment |
| audit_trace_screen | safety_badge; audit_trace_panel; no_decision_object_card; source_status_badge | traceability only |
| safety_reference_screen | safety_badge; authority_envelope_card; no_decision_object_card; visual_safety_label; prototype_boundary_banner | safety reference hub |
| authority_envelope_screen | safety_badge; authority_envelope_card; visual_safety_label | authority boundary |
| no_decision_object_screen | safety_badge; no_decision_object_card; visual_safety_label | no-decision boundary |
| visual_safety_label_screen | safety_badge; visual_safety_label; prototype_boundary_banner | visual safety marker |

Screen placement rule:

> Every screen must place safety without hiding the screen’s reasoning purpose.

---

## 10. Reasoning Surface Placement Map

The clinically meaningful reasoning surfaces created by v0.19.4 require the following placement:

| Reasoning Surface | Required Boundary Placement | Reason |
|---|---|---|
| missing evidence reasoning | missing_evidence_panel_card + confidence_limiter_panel + review_prompt_card | missing evidence prevents closure |
| mimic persistence | mimic_visibility_panel_card + review_prompt_card + no_decision_object_card | mimic remains unresolved unless evidence closes it |
| overlap reasoning | overlap_panel_card + confidence_limiter_panel + review_prompt_card | overlap is not ranking/probability |
| source status | source_status_badge + audit_trace_panel + safety_badge | source state is not authority |
| confidence limitation | confidence_limiter_panel + no_decision_object_card | no calibrated probability |
| MDD preparation | review_prompt_card + authority_envelope_card + no_decision_object_card | preparation, not consensus |
| report overclaim prevention | red_team_fail_closed_panel + audit_trace_panel | unsafe wording fails closed |
| safe export preview | safe_export_preview_panel + safety_badge + review_prompt_card | preview, not report |
| audit traceability | audit_trace_panel + no_decision_object_card | traceability, not validation |

Reasoning placement rule:

> Clinical reasoning surfaces must show their value and their non-autonomous boundary together.

---

## 11. Safety Language Placement

Safety text should be placed using corrected doctrine language.

Preferred language:

- “Internal synthetic reasoning demo.”
- “Clinician-facing reasoning support only.”
- “No autonomous final diagnosis.”
- “No autonomous rule-out.”
- “No treatment authority.”
- “No patient-facing clinical output.”
- “Review required.”
- “MDD preparation only, not MDD consensus.”
- “Scaffold-safety validation only, not clinical validation.”
- “Evidence visibility does not equal diagnostic truth.”
- “Confidence limitation does not equal calibrated probability.”

Avoid over-broad language:

- “No clinical reasoning.”
- “No diagnostic reasoning.”
- “This platform never supports differential reasoning.”
- “This platform only blocks unsafe language.”
- “This platform is only a safety layer.”

Safety language rule:

> Safety copy must preserve product value while blocking autonomous clinical authority.

---

## 12. Authority Placement Boundary

Authority envelope placement is required when the surface involves:

- reasoning map,
- evidence panel,
- missing evidence,
- mimic visibility,
- overlap,
- confidence limitation,
- review prompt,
- export preview,
- MDD preparation,
- red-team scenario,
- audit trace.

Authority placement must clarify:

- current phase has no autonomous diagnostic authority,
- treatment authority is none,
- patient-facing use is not allowed,
- clinical validation is not opened,
- MDD replacement is blocked.

Authority placement must not imply:

- the platform is clinically useless,
- clinician-facing reasoning support is banned,
- future governed reasoning is impossible.

Authority boundary rule:

> Authority limits must be clear without collapsing the platform into a passive disclaimer system.

---

## 13. No-Decision Placement Boundary

No-decision placement is required when the surface may look like a decision point.

Required no-decision contexts:

- reasoning map,
- mimic visibility,
- overlap panel,
- confidence limiter,
- safe export preview,
- review prompt,
- MDD preparation,
- red-team fail-closed,
- audit trace.

The no-decision object must clarify:

- no final diagnosis made,
- no disease autonomously excluded,
- no treatment selected,
- no test ordered,
- no procedure decided,
- no follow-up scheduled,
- no triage assigned,
- no MDD consensus generated,
- no patient-facing output generated.

No-decision placement rule:

> The user must see that reasoning is being structured, not closed.

---

## 14. Review-Required Placement

Review-required notices must appear anywhere the system presents reasoning structure.

Required review-required contexts:

- synthetic intake review,
- reasoning map,
- evidence panel,
- missing evidence,
- mimic visibility,
- overlap,
- confidence limiter,
- safe export preview,
- MDD preparation,
- report overclaim prevention.

Review-required meaning:

- clinician review required,
- MDD discussion may be appropriate,
- platform does not decide,
- missing evidence may change reasoning,
- mimics must remain visible until evidence supports closure.

Review-required rule:

> Review-required placement transforms reasoning output into clinician support rather than autonomous authority.

---

## 15. Confidence Limitation Placement

Confidence limitation must appear when evidence may be mistaken for certainty.

Required confidence limitation contexts:

- missing evidence,
- mimic visibility,
- overlap,
- source status,
- reasoning map,
- safe export preview.

Confidence limitation may say:

- confidence remains limited because evidence is missing,
- source status is incomplete,
- mimic overlap persists,
- pattern/distribution/temporal context is incomplete,
- review is required.

Confidence limitation must not say:

- probability is X percent,
- disease is ranked first,
- diagnosis is confirmed,
- mimic is ruled out,
- evidence proves diagnosis.

Confidence placement rule:

> Confidence limitation explains uncertainty; it does not create calibrated probability.

---

## 16. MDD Preparation Placement

MDD-related placement must clarify:

Allowed:

- MDD preparation,
- MDD discussion questions,
- evidence gap list,
- unresolved mimic list,
- overlap reasoning summary,
- source status summary,
- report overclaim warning.

Blocked:

- MDD final consensus,
- MDD diagnosis,
- MDD treatment decision,
- MDD procedure decision,
- MDD follow-up plan,
- MDD triage decision.

MDD placement rule:

> MDD preparation is allowed; MDD replacement is blocked.

---

## 17. Export Preview Placement

Export preview placement must clarify:

Allowed:

- safe preview,
- non-clinical internal export structure,
- source status summary,
- missing evidence visibility,
- review-required notice,
- overclaim guard.

Blocked:

- clinical report generation,
- impression generation,
- final diagnosis,
- treatment recommendation,
- patient-facing summary,
- MDD consensus.

Export placement rule:

> Export preview may show structure; it must not become a report.

---

## 18. Red-Team Placement

Red-team placement must clarify:

Allowed:

- unsafe scenario display,
- quarantine,
- fail-closed stop-state,
- repair/revalidation requirement,
- blocked phrase prevention,
- audit traceability.

Blocked:

- reusable unsafe output,
- unsafe copy library,
- bypass instructions,
- clinical phrase template,
- exploit library.

Red-team placement rule:

> Red-team examples exist to prove containment, not to provide reusable language.

---

## 19. Audit Placement

Audit placement must clarify:

Allowed:

- scaffold traceability,
- route/screen/component/fixture/copy trace,
- fail-closed trace,
- red-team containment trace,
- export preview trace,
- safety verification trace.

Blocked:

- clinical correctness proof,
- diagnostic validation,
- treatment correctness,
- patient care audit,
- PACS/EHR audit,
- regulatory evidence,
- product readiness proof.

Audit placement rule:

> Audit is a record of scaffold safety behavior, not proof of clinical correctness.

---

## 20. Prototype File Count Preservation

v0.19.5 does not add files inside the prototype skeleton.

The v0.18 sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count preservation rule:

> v0.19.5 records a placement map in docs only; the materialized prototype skeleton remains unchanged.

---

## 21. What v0.19.5 Allows

v0.19.5 allows only:

- safety placement mapping,
- authority envelope placement mapping,
- no-decision placement mapping,
- review-required placement mapping,
- confidence limitation placement mapping,
- MDD preparation boundary placement,
- export preview boundary placement,
- red-team containment placement,
- audit traceability placement,
- corrected doctrine safety language.

Allowed-use rule:

> v0.19.5 places guardrails around clinically meaningful reasoning surfaces.

---

## 22. What v0.19.5 Blocks

v0.19.5 blocks:

- safety language that hides clinical reasoning value,
- authority language that implies the platform is clinically useless,
- hidden diagnosis authority,
- hidden rule-out authority,
- hidden probability authority,
- treatment authority,
- patient-facing authority,
- clinical validation claim,
- diagnostic performance claim,
- product readiness claim,
- MDD final consensus claim.

Blocked-use rule:

> Safety placement must neither overclaim clinical authority nor erase clinical reasoning value.

---

## 23. Acceptance Criteria

v0.19.5 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.19.0 dependency listed | true |
| v0.19.1 dependency listed | true |
| v0.19.2 dependency listed | true |
| v0.19.3 doctrine dependency listed | true |
| v0.19.4 reasoning fixture binding dependency listed | true |
| v0.18.9 dependency listed | true |
| checkpoint-v0.18 dependency listed | true |
| three-tier placement system defined | true |
| screen-level placement map defined | true |
| reasoning surface placement map defined | true |
| corrected safety language defined | true |
| authority placement boundary defined | true |
| no-decision placement boundary defined | true |
| review-required placement defined | true |
| confidence limitation placement defined | true |
| MDD preparation placement defined | true |
| export preview placement defined | true |
| red-team placement defined | true |
| audit placement defined | true |
| safety does not erase clinical reasoning value | true |
| autonomous final diagnosis remains blocked | true |
| autonomous rule-out remains blocked | true |
| calibrated probability remains not_opened | true |
| treatment authority remains none | true |
| clinical validation remains not_opened | true |
| patient-facing use remains not_allowed | true |
| MDD replacement remains blocked | true |
| prototype file count remains 191 | true |

Acceptance rule:

> v0.19.5 is valid only if safety placement preserves both boundary clarity and clinical reasoning value.

---

## 24. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> This placement map is docs-only and must not mutate the prototype skeleton.

---

## 25. Next Step

The next recommended step is:

    v0.19.6 — Fail-Closed / Disabled Controls Display Binding Plan

v0.19.6 should define how stop-states and disabled controls appear in the static internal demo.

v0.19.6 must remain:

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

> v0.19.6 must show blocked paths as stop-states, not hidden future clinical buttons.

---

## 26. Governance Statement

This document records v0.19.5 safety, authority, no-decision, review-required, and non-autonomous reasoning boundary placement map.

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

The v0.19.5 discipline is:

> “Make safety visible without burying reasoning.”

The final v0.19.5 boundary is:

> “The user should understand both what the platform helps them reason about and what it must not decide.”
