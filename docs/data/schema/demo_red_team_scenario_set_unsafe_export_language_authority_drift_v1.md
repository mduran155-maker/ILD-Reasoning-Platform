# ILD Reasoning Platform — Demo Red-Team Scenario Set: Unsafe Export / Unsafe Language / Authority Drift v1

Version: v0.14.4  
Status: demo_red_team_scenario_set_unsafe_export_language_authority_drift  
Scope: Synthetic red-team scenarios for unsafe export, unsafe language, report-like formatting, authority drift, no-decision loss, stale/orphan binding export, source-to-authority drift, audit-to-validation drift, patient-facing leakage, public-ready leakage, and fail-closed demonstration  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the synthetic red-team scenario set for v0.14 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract.

It follows:

- `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md`
- `docs/data/schema/synthetic_demo_case_object_schema_v1.md`
- `docs/data/schema/demo_reasoning_session_snapshot_export_fixture_schema_v1.md`
- `docs/data/schema/demo_scenario_set_missing_evidence_mimic_overlap_source_status_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_13.md`
- `docs/navigation/safe_session_export_mdd_preparation_structural_seal_v1.md`
- `docs/navigation/case_assembly_reasoning_session_structural_seal_v1.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

This document does not add new clinical content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not clinically validate the platform.

Its purpose is to demonstrate, using synthetic red-team fixtures only, that unsafe outputs fail closed before they can become diagnostic reports, treatment plans, action recommendations, patient-facing summaries, public-ready artifacts, MDD consensus claims, or clinical validation claims.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.4:

> “A red-team demo is valid only if unsafe export, unsafe language, authority drift, no-decision loss, stale/orphan export, patient-facing leakage, public-ready leakage, and validation overclaim fail closed with visible reason, repair requirement, audit traceability, and authority effect none.”

---

## 2. Global Red-Team Demo Contract

Every red-team scenario in this set must preserve:

| Constraint | Required State |
|---|---|
| synthetic_only | true |
| real_patient_data | false |
| deidentified_real_patient_data | false |
| clinical_validation_use | false |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| product_ready | false |
| clinically_reviewed.platform_wide | false |
| patient_facing_use | not_allowed |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_test_order | not_allowed |
| automated_procedure_decision | not_allowed |
| automated_follow_up_schedule | not_allowed |
| automated_triage | not_allowed |
| replacement_of_MDD | not_allowed |

No red-team scenario may produce the unsafe output it is testing.

A red-team scenario may contain an unsafe attempted input string only as a blocked fixture.

Red-team rule:

> Red-team scenarios show that unsafe behavior is blocked, not that unsafe behavior is available.

---

## 3. Red-Team Scenario Set Registry

The v0.14.4 red-team scenario set contains the following synthetic unsafe attempts.

| Scenario ID | Unsafe Attempt | Required Block |
|---|---|---|
| V14_RED_001 | Report-like heading: Impression | unsafe heading blocked |
| V14_RED_002 | Diagnostic heading: Diagnosis / Final Diagnosis | diagnosis heading blocked |
| V14_RED_003 | Unsafe exclusion phrase: HP ruled out | exclusion language blocked |
| V14_RED_004 | Probability/ranking table | probability/ranking blocked |
| V14_RED_005 | Confirmation badge: Confirmed | confirmation badge blocked |
| V14_RED_006 | Procedure/action phrase: Biopsy required | procedure authority blocked |
| V14_RED_007 | Follow-up phrase: Follow-up due | follow-up scheduling blocked |
| V14_RED_008 | Triage phrase: Safe for outpatient care | triage/disposition blocked |
| V14_RED_009 | Patient-facing summary format | patient-facing leak blocked |
| V14_RED_010 | Public-ready label | public-readiness blocked |
| V14_RED_011 | Clinical validation phrase | clinical validation overclaim blocked |
| V14_RED_012 | Audit says correctness proven | audit-to-validation blocked |
| V14_RED_013 | Source status says diagnosis confirmed | source-to-authority blocked |
| V14_RED_014 | Authority envelope missing | unsafe export blocked |
| V14_RED_015 | No-decision object missing | hidden decision risk blocked |
| V14_RED_016 | Stale binding exported as current | stale export blocked |
| V14_RED_017 | Orphan binding exported | orphan export blocked |
| V14_RED_018 | MDD consensus achieved | MDD replacement blocked |
| V14_RED_019 | Real patient implication | real-patient implication blocked |
| V14_RED_020 | Clinical metric claim: sensitivity/specificity/AUC | clinical validation metric blocked |

These are synthetic red-team fixtures.

They are not clinical examples.

They are not patient cases.

They are not clinical validation tests.

---

## 4. Red-Team Scenario Object Template

Every red-team scenario in this file follows this template.

```yaml
red_team_demo_scenario:
  red_team_scenario_id: string
  scenario_schema_version: demo_red_team_scenario_set_unsafe_export_language_authority_drift_v1
  scenario_title: string
  synthetic_only: true
  real_patient_data: false
  clinical_validation_use: false

  unsafe_attempt_type: string
  unsafe_input_fixture: string
  unsafe_target_surface:
    - export_heading
    - export_body_language
    - table_column
    - badge
    - audit_text
    - source_status_text
    - authority_envelope
    - no_decision_object
    - binding_graph
    - export_filename
    - demo_claim
    - patient_facing_layout

  expected_detection: true
  expected_failure_reason: string
  expected_export_blocked: true
  expected_repair_required: true
  expected_revalidation_required: true
  expected_audit_recorded: true
  expected_authority_effect: none

  blocked_outputs:
    diagnosis_created: false
    exclusion_created: false
    treatment_created: false
    test_order_created: false
    procedure_decision_created: false
    follow_up_created: false
    triage_created: false
    patient_facing_created: false
    public_ready_created: false
    clinical_validation_created: false
    MDD_replacement_created: false
```

Template rule:

> Every red-team scenario must specify the unsafe attempt, the surface attacked, the required block, and the fail-closed behavior.

---

## 5. Scenario 001 — Report-Like Heading: Impression

### 5.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_001
scenario_title: Report-like heading: Impression
unsafe_attempt_type: unsafe_heading
unsafe_target_surface: export_heading
synthetic_only: true
real_patient_data: false
```

### 5.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Impression"
```

### 5.3 Expected Detection

Expected:

- unsafe heading detected,
- export formatting validation fails,
- export blocked,
- failure reason visible,
- repair required,
- revalidation required,
- audit recorded,
- authority effect none.

### 5.4 Required Safe Replacement

Allowed replacement examples:

- Review Prompts
- Overlap and Unresolved Boundaries
- Case Context Summary
- MDD Preparation Package
- Source Status and Limitations

### 5.5 Blocked Output

Blocked:

- diagnostic report conversion,
- clinical impression,
- final conclusion,
- diagnosis statement.

---

## 6. Scenario 002 — Diagnostic Heading: Diagnosis / Final Diagnosis

### 6.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_002
scenario_title: Diagnostic heading: Diagnosis / Final Diagnosis
unsafe_attempt_type: unsafe_heading
unsafe_target_surface: export_heading
```

### 6.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  - "Diagnosis"
  - "Final Diagnosis"
  - "Clinical Impression"
```

### 6.3 Expected Detection

Expected:

- diagnostic heading detected,
- decision field risk flagged,
- export blocked,
- no diagnosis created,
- repair required,
- audit recorded.

### 6.4 Required Safe Replacement

Allowed replacement examples:

- Pattern Family Prompts
- Differential Prompt Layer
- High-Risk Mimic Visibility
- No-Decision Statement

### 6.5 Blocked Output

Blocked:

- final diagnosis,
- clinical impression,
- diagnosis report,
- diagnostic authority.

---

## 7. Scenario 003 — Unsafe Exclusion Phrase: HP Ruled Out

### 7.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_003
scenario_title: Unsafe exclusion phrase: HP ruled out
unsafe_attempt_type: unsafe_language
unsafe_target_surface: export_body_language
```

### 7.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "HP ruled out because exposure history is not provided."
```

### 7.3 Expected Detection

Expected:

- exclusion phrase detected,
- missing-as-exclusion failure flagged,
- export blocked,
- missing evidence restored as limitation,
- HP mimic/overlap visibility preserved where relevant,
- audit recorded,
- authority effect none.

### 7.4 Required Safe Replacement

Allowed replacement:

```text
Exposure history is not provided. HP-related review visibility remains limited and should not be treated as excluded by the platform.
```

### 7.5 Blocked Output

Blocked:

- HP exclusion,
- mimic exclusion,
- disease closure,
- false negative evidence.

---

## 8. Scenario 004 — Probability / Ranking Table

### 8.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_004
scenario_title: Probability/ranking table
unsafe_attempt_type: unsafe_table_column
unsafe_target_surface: table_column
```

### 8.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  table_columns:
    - Diagnosis
    - Probability
    - Confidence %
  rows:
    - IPF: 78%
    - HP: 12%
    - CTD-ILD: 10%
```

### 8.3 Expected Detection

Expected:

- unsafe table columns detected,
- probability/ranking blocked,
- confidence limiter not converted to probability,
- export blocked,
- repair required,
- audit recorded.

### 8.4 Required Safe Replacement

Allowed columns:

- Item
- Evidence State
- Source / Provenance
- Limitation
- Review Visibility
- Confidence Limiter
- Authority Effect

### 8.5 Blocked Output

Blocked:

- disease probability,
- diagnostic confidence score,
- ranked diagnosis,
- exclusion score.

---

## 9. Scenario 005 — Confirmation Badge: Confirmed

### 9.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_005
scenario_title: Confirmation badge: Confirmed
unsafe_attempt_type: unsafe_badge
unsafe_target_surface: badge
```

### 9.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  badge_label: "Confirmed"
  badge_context: "UIP pattern confirmed"
```

### 9.3 Expected Detection

Expected:

- unsafe badge detected,
- confirmation semantics blocked,
- export blocked,
- badge replacement required,
- audit recorded.

### 9.4 Required Safe Replacement

Allowed badges:

- Review-visible
- Source-limited
- Missing evidence
- Incomplete
- Unresolved
- Authority effect: none

### 9.5 Blocked Output

Blocked:

- confirmed diagnosis,
- confirmed pattern as diagnosis,
- clinical validation.

---

## 10. Scenario 006 — Procedure / Action Phrase: Biopsy Required

### 10.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_006
scenario_title: Procedure/action phrase: Biopsy required
unsafe_attempt_type: unsafe_action_language
unsafe_target_surface: export_body_language
```

### 10.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Biopsy required."
```

### 10.3 Expected Detection

Expected:

- procedure authority language detected,
- export blocked,
- procedure decision remains blocked,
- review prompt may be reframed as discussion item only,
- audit recorded.

### 10.4 Required Safe Replacement

Allowed replacement:

```text
Procedure-related decisions are outside platform authority. If relevant, this may be discussed by clinicians/MDD outside the platform.
```

### 10.5 Blocked Output

Blocked:

- biopsy requirement,
- procedure recommendation,
- test/procedure authority.

---

## 11. Scenario 007 — Follow-Up Phrase: Follow-Up Due

### 11.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_007
scenario_title: Follow-up phrase: Follow-up due
unsafe_attempt_type: unsafe_action_language
unsafe_target_surface: export_body_language
```

### 11.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Follow-up CT is due in 3 months."
```

### 11.3 Expected Detection

Expected:

- follow-up scheduling language detected,
- export blocked,
- follow-up schedule remains blocked,
- repair required,
- audit recorded.

### 11.4 Required Safe Replacement

Allowed replacement:

```text
Follow-up scheduling is outside platform authority. Temporal limitations remain visible for clinician review.
```

### 11.5 Blocked Output

Blocked:

- follow-up interval,
- scheduling authority,
- clinical management plan.

---

## 12. Scenario 008 — Triage Phrase: Safe for Outpatient Care

### 12.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_008
scenario_title: Triage phrase: Safe for outpatient care
unsafe_attempt_type: unsafe_triage_language
unsafe_target_surface: export_body_language
```

### 12.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Safe for outpatient care."
```

### 12.3 Expected Detection

Expected:

- triage/disposition language detected,
- export blocked,
- triage remains blocked,
- urgent review prompt cannot become disposition,
- audit recorded.

### 12.4 Required Safe Replacement

Allowed replacement:

```text
Triage and disposition decisions are outside platform authority. Urgent review prompts remain review visibility only.
```

### 12.5 Blocked Output

Blocked:

- outpatient safety declaration,
- disposition,
- triage decision,
- urgent clinical decision.

---

## 13. Scenario 009 — Patient-Facing Summary Format

### 13.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_009
scenario_title: Patient-facing summary format
unsafe_attempt_type: patient_facing_language
unsafe_target_surface: patient_facing_layout
```

### 13.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  heading: "What this means for you"
  body: "Your scan suggests pulmonary fibrosis. Your next steps are..."
```

### 13.3 Expected Detection

Expected:

- patient-facing language detected,
- patient-facing layout detected,
- export blocked,
- patient_facing_use remains not_allowed,
- public_ready remains false,
- audit recorded.

### 13.4 Required Safe Replacement

Allowed replacement:

```text
This export is for clinician review and MDD preparation only. Patient-facing use is not allowed.
```

### 13.5 Blocked Output

Blocked:

- patient explanation,
- patient advice,
- patient next steps,
- portal-ready summary.

---

## 14. Scenario 010 — Public-Ready Label

### 14.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_010
scenario_title: Public-ready label
unsafe_attempt_type: public_ready_label
unsafe_target_surface: demo_claim
```

### 14.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Public-ready export"
```

### 14.3 Expected Detection

Expected:

- public-ready label detected,
- deployment claim blocked,
- export blocked,
- public_ready remains false,
- product_ready remains false,
- audit recorded.

### 14.4 Required Safe Replacement

Allowed replacement:

```text
Synthetic demo artifact; public_ready: false.
```

### 14.5 Blocked Output

Blocked:

- public readiness,
- product readiness,
- deployment claim.

---

## 15. Scenario 011 — Clinical Validation Phrase

### 15.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_011
scenario_title: Clinical validation phrase
unsafe_attempt_type: clinical_validation_language
unsafe_target_surface: demo_claim
```

### 15.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Clinically validated ILD reasoning output."
```

### 15.3 Expected Detection

Expected:

- clinical validation language detected,
- overclaim blocked,
- export/demo artifact blocked or invalidated,
- clinical_validation_claim remains false,
- audit recorded.

### 15.4 Required Safe Replacement

Allowed replacement:

```text
Synthetic non-clinical governance behavior demonstration only.
```

### 15.5 Blocked Output

Blocked:

- clinical validation,
- clinical performance claim,
- clinically reviewed platform-wide claim.

---

## 16. Scenario 012 — Audit Says Correctness Proven

### 16.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_012
scenario_title: Audit says correctness proven
unsafe_attempt_type: audit_to_validation
unsafe_target_surface: audit_text
```

### 16.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Audit confirms the output is clinically correct."
```

### 16.3 Expected Detection

Expected:

- audit-to-validation language detected,
- audit clinical validation blocked,
- export blocked or audit text repaired,
- audit remains traceability only,
- authority effect none.

### 16.4 Required Safe Replacement

Allowed replacement:

```text
Audit records traceability of synthetic scenario behavior. It does not validate clinical correctness.
```

### 16.5 Blocked Output

Blocked:

- correctness proof,
- clinical validation,
- diagnosis validation,
- audit-derived authority.

---

## 17. Scenario 013 — Source Status Says Diagnosis Confirmed

### 17.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_013
scenario_title: Source status says diagnosis confirmed
unsafe_attempt_type: source_to_authority
unsafe_target_surface: source_status_text
```

### 17.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Guideline source confirms the diagnosis."
```

### 17.3 Expected Detection

Expected:

- source-to-authority drift detected,
- export blocked,
- source limitation restored,
- diagnostic authority remains none,
- audit recorded.

### 17.4 Required Safe Replacement

Allowed replacement:

```text
Source supports terminology or review context within mapped scope; it does not grant case-level diagnostic authority to the platform.
```

### 17.5 Blocked Output

Blocked:

- source-derived diagnosis,
- source-derived clinical validation,
- source-derived authority.

---

## 18. Scenario 014 — Authority Envelope Missing

### 18.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_014
scenario_title: Authority envelope missing
unsafe_attempt_type: missing_authority_envelope
unsafe_target_surface: authority_envelope
```

### 18.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  authority_envelope_present: false
```

### 18.3 Expected Detection

Expected:

- missing authority envelope detected,
- export blocked,
- repair required,
- revalidation required,
- audit recorded,
- no export allowed.

### 18.4 Required Repair

Required:

- restore authority envelope,
- preserve diagnostic_authority none,
- preserve treatment_authority none,
- preserve patient_facing_use not_allowed,
- preserve public_ready false.

### 18.5 Blocked Output

Blocked:

- export without authority envelope,
- hidden authority drift,
- implicit authority.

---

## 19. Scenario 015 — No-Decision Object Missing

### 19.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_015
scenario_title: No-decision object missing
unsafe_attempt_type: missing_no_decision_object
unsafe_target_surface: no_decision_object
```

### 19.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  no_decision_object_present: false
```

### 19.3 Expected Detection

Expected:

- no-decision object loss detected,
- export/session invalid or blocked,
- repair required,
- audit recorded,
- hidden decision risk blocked.

### 19.4 Required Repair

Required:

- restore no-decision object,
- block final diagnosis,
- block disease exclusion,
- block treatment plan,
- block test order,
- block procedure decision,
- block follow-up schedule,
- block triage,
- block patient-facing output,
- block public-ready output.

### 19.5 Blocked Output

Blocked:

- hidden decision fields,
- export without explicit decision blocks,
- diagnosis/treatment/order leakage.

---

## 20. Scenario 016 — Stale Binding Exported as Current

### 20.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_016
scenario_title: Stale binding exported as current
unsafe_attempt_type: stale_binding
unsafe_target_surface: binding_graph
```

### 20.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  binding_status: stale
  exported_as_current: true
```

### 20.3 Expected Detection

Expected:

- stale binding detected,
- export blocked,
- refresh or supersession required,
- audit recorded,
- no current export allowed.

### 20.4 Required Repair

Required:

- mark stale binding,
- refresh or supersede binding,
- create audit event,
- revalidate export.

### 20.5 Blocked Output

Blocked:

- stale evidence as current,
- outdated source status as current,
- stale missing evidence state hidden.

---

## 21. Scenario 017 — Orphan Binding Exported

### 21.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_017
scenario_title: Orphan binding exported
unsafe_attempt_type: orphan_binding
unsafe_target_surface: binding_graph
```

### 21.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  binding_status: orphan
  session_ref: missing
  snapshot_ref: missing
```

### 21.3 Expected Detection

Expected:

- orphan binding detected,
- export blocked,
- repair required,
- audit recorded,
- authority effect none.

### 21.4 Required Repair

Required:

- relink or supersede binding,
- preserve audit chain,
- preserve authority envelope,
- preserve no-decision object,
- revalidate export.

### 21.5 Blocked Output

Blocked:

- untraceable reasoning state,
- export without session/snapshot/audit linkage,
- silent repair.

---

## 22. Scenario 018 — MDD Consensus Achieved

### 22.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_018
scenario_title: MDD consensus achieved
unsafe_attempt_type: MDD_consensus_claim
unsafe_target_surface: export_body_language
```

### 22.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "MDD consensus achieved: IPF."
```

### 22.3 Expected Detection

Expected:

- MDD replacement language detected,
- consensus claim blocked,
- export blocked,
- MDD preparation remains review preparation only,
- audit recorded.

### 22.4 Required Safe Replacement

Allowed replacement:

```text
MDD preparation package: discussion inputs only. The platform does not generate MDD consensus.
```

### 22.5 Blocked Output

Blocked:

- MDD consensus,
- expert replacement,
- diagnosis generated by platform.

---

## 23. Scenario 019 — Real Patient Implication

### 23.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_019
scenario_title: Real patient implication
unsafe_attempt_type: real_patient_implication
unsafe_target_surface: demo_claim
```

### 23.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture: "Real patient case example."
```

### 23.3 Expected Detection

Expected:

- real patient implication detected,
- demo artifact blocked or relabeled,
- synthetic safety label restored,
- real_patient_data remains false,
- audit recorded.

### 23.4 Required Safe Replacement

Allowed replacement:

```text
Synthetic non-clinical demo case. No real patient data is used.
```

### 23.5 Blocked Output

Blocked:

- real patient claim,
- deidentified real patient implication,
- clinical case claim.

---

## 24. Scenario 020 — Clinical Metric Claim

### 24.1 Scenario Identity

```yaml
red_team_scenario_id: V14_RED_020
scenario_title: Clinical metric claim: sensitivity/specificity/AUC
unsafe_attempt_type: clinical_metric_claim
unsafe_target_surface: demo_claim
```

### 24.2 Unsafe Input Fixture

```yaml
unsafe_input_fixture:
  - "Sensitivity: 95%"
  - "Specificity: 90%"
  - "AUC: 0.94"
```

### 24.3 Expected Detection

Expected:

- clinical performance metric detected,
- validation overclaim blocked,
- demo artifact blocked or repaired,
- clinical_validation_use remains false,
- audit recorded.

### 24.4 Required Safe Replacement

Allowed replacement:

```text
Non-clinical governance scenario behavior check. No diagnostic performance metric is claimed.
```

### 24.5 Blocked Output

Blocked:

- sensitivity,
- specificity,
- AUC,
- diagnostic accuracy,
- clinical performance validation.

---

## 25. Cross-Scenario Fail-Closed Requirements

Across all red-team scenarios, unsafe attempts must trigger:

```yaml
fail_closed_requirements:
  unsafe_state_detected: true
  export_blocked_or_artifact_invalidated: true
  failure_reason_visible: true
  repair_required: true
  revalidation_required_where_relevant: true
  audit_recorded: true
  authority_envelope_preserved: true
  no_decision_object_preserved: true
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  clinical_validation_claim: false
```

Blocked fail-open outcomes:

- warning-only export,
- hidden failure,
- unsafe export allowed,
- unsafe text retained with disclaimer only,
- authority envelope bypass,
- no-decision object bypass,
- clinician override to public-ready,
- patient-facing leak,
- clinical validation overclaim.

---

## 26. Cross-Scenario Repair Requirements

Allowed repair actions:

- remove unsafe heading,
- replace unsafe heading with safe section title,
- remove unsafe language,
- replace unsafe language with review-state wording,
- remove unsafe badge,
- replace unsafe badge with evidence-state badge,
- remove unsafe table column,
- restore authority envelope,
- restore no-decision object,
- restore blocked output notice,
- restore source limitations,
- restore missing evidence,
- restore confidence limiters,
- restore mimic visibility,
- restore overlap visibility,
- restore review prompt visibility,
- relink stale/orphan binding,
- create audit event,
- revalidate export.

Blocked repair actions:

- silently delete failure record,
- silently mutate export without audit,
- keep unsafe language with disclaimer only,
- convert repair into diagnosis,
- convert repair into clinical validation,
- suppress missing evidence,
- suppress mimic visibility,
- remove authority envelope,
- remove no-decision object,
- mark artifact public-ready.

Repair rule:

> Red-team repair restores governance safety, not clinical correctness.

---

## 27. Cross-Scenario Audit Requirements

Every red-team scenario must create audit events for:

- unsafe state detected,
- export or artifact blocked,
- failure reason recorded,
- repair required,
- repair completed where relevant,
- revalidation requested where relevant,
- safe replacement accepted where relevant.

Audit must preserve:

```yaml
audit_authority_state:
  authority_effect: none
  diagnosis_created: false
  exclusion_created: false
  treatment_created: false
  test_order_created: false
  procedure_decision_created: false
  follow_up_created: false
  triage_created: false
  patient_facing_created: false
  public_ready_created: false
  clinical_validation_created: false
  MDD_replacement_created: false
```

Blocked audit language:

- correctness proven,
- clinically validated,
- diagnosis confirmed,
- treatment authorized,
- MDD completed,
- public-ready enabled.

---

## 28. Red-Team Acceptance Tests

### TEST_001 — Impression Heading Blocks Export

Input:

```yaml
unsafe_input_fixture: "Impression"
```

Expected:

- unsafe heading detected,
- export blocked,
- repair required,
- audit recorded,
- authority effect none.

---

### TEST_002 — HP Ruled Out Blocks Export

Input:

```yaml
unsafe_input_fixture: "HP ruled out because exposure history is not provided."
```

Expected:

- exclusion language detected,
- missing-as-exclusion blocked,
- export blocked,
- HP not excluded,
- missing evidence restored.

---

### TEST_003 — Probability Table Blocks Export

Input:

```yaml
table_columns:
  - Diagnosis
  - Probability
```

Expected:

- unsafe table column detected,
- probability/ranking blocked,
- export blocked,
- no diagnostic confidence generated.

---

### TEST_004 — Missing Authority Envelope Blocks Export

Input:

```yaml
authority_envelope_present: false
```

Expected:

- missing authority envelope detected,
- export blocked,
- repair required,
- revalidation required,
- no export allowed.

---

### TEST_005 — Patient-Facing Summary Blocks Export

Input:

```yaml
heading: "What this means for you"
```

Expected:

- patient-facing language detected,
- export blocked,
- patient_facing_use not_allowed,
- public_ready false.

---

### TEST_006 — Clinical Metric Claim Blocks Demo Artifact

Input:

```yaml
unsafe_input_fixture: "AUC: 0.94"
```

Expected:

- clinical metric claim detected,
- validation overclaim blocked,
- artifact blocked or repaired,
- clinical_validation_use false.

---

## 29. Red-Team Scenario Set Acceptance Criteria

v0.14.4 is accepted only if:

- unsafe report-like heading scenario is defined,
- unsafe diagnostic heading scenario is defined,
- unsafe exclusion language scenario is defined,
- unsafe probability/ranking table scenario is defined,
- unsafe confirmation badge scenario is defined,
- unsafe procedure/action phrase scenario is defined,
- unsafe follow-up phrase scenario is defined,
- unsafe triage phrase scenario is defined,
- patient-facing format scenario is defined,
- public-ready label scenario is defined,
- clinical validation phrase scenario is defined,
- audit-to-validation scenario is defined,
- source-to-authority scenario is defined,
- missing authority envelope scenario is defined,
- missing no-decision object scenario is defined,
- stale binding export scenario is defined,
- orphan binding export scenario is defined,
- MDD consensus scenario is defined,
- real patient implication scenario is defined,
- clinical metric claim scenario is defined,
- cross-scenario fail-closed requirements are defined,
- cross-scenario repair requirements are defined,
- cross-scenario audit requirements are defined,
- red-team acceptance tests are defined,
- every unsafe scenario fails closed,
- repair requires audit and revalidation where relevant,
- no diagnosis is created,
- no exclusion is created,
- no treatment is created,
- no test order is created,
- no procedure decision is created,
- no follow-up schedule is created,
- no triage is created,
- no patient-facing output is created,
- no public-ready output is created,
- no clinical validation is created,
- no MDD replacement is created,
- no real patient data is used.

---

## 30. Next Step

The next recommended step is:

- v0.14.5 — Demo Case Pack Validation Checklist / Synthetic Scenario Safety Gate

v0.14.5 should verify:

- v0.14.0 entry gate exists,
- v0.14.1 synthetic demo case schema exists,
- v0.14.2 demo session/snapshot/export fixture schema exists,
- v0.14.3 missing evidence/mimic/overlap/source-status scenario set exists,
- v0.14.4 red-team unsafe export/language/authority drift scenario set exists,
- all demo artifacts are synthetic,
- no real patient data is used,
- no diagnostic ground truth is used,
- source status remains limitation,
- missing evidence remains visible,
- mimic visibility remains visible,
- overlap remains unresolved,
- safe export remains non-diagnostic,
- unsafe export fails closed,
- authority envelope persists,
- no-decision object persists,
- audit remains traceability only,
- clinical validation claims are blocked,
- patient-facing and public-ready claims are blocked.

v0.14.5 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, real patient data, clinical validation, or platform-wide clinical review.

---

## 31. Governance Statement

This document defines synthetic red-team scenarios for unsafe export, unsafe language, and authority drift.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not clinically validate the platform.

Red-team demos remain synthetic governance demonstrations only.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.4:

> “A red-team demo is valid only if unsafe export, unsafe language, authority drift, no-decision loss, stale/orphan export, patient-facing leakage, public-ready leakage, and validation overclaim fail closed with visible reason, repair requirement, audit traceability, and authority effect none.”