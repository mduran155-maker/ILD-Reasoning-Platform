# ILD Reasoning Platform — Prototype Workspace Validation Checklist / UI Safety Gate v1

Version: v0.15.5  
Status: prototype_workspace_validation_checklist_ui_safety_gate  
Scope: Prototype workspace validation checklist, screen/component safety validation, synthetic-only validation, real patient data block validation, visual safety validation, reasoning map safety validation, export preview safety validation, red-team fail-closed validation, authority envelope validation, no-decision object validation, audit trace validation, public/product readiness overclaim validation, patient-facing leak validation, clinical validation overclaim block, and final v0.15 pre-seal UI safety gate  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.15.5 — Prototype Workspace Validation Checklist / UI Safety Gate.

v0.15.5 validates the prototype workspace UI behavior opened by:

- v0.15.0 — Prototype Workspace / Demo UI Behavior Contract Entry Gate,
- v0.15.1 — Demo Workspace Screen / Component Behavior Schema,
- v0.15.2 — Demo Case Selection / Synthetic Intake UI Flow,
- v0.15.3 — Reasoning Map / Guided Visual Reasoning Interaction Contract,
- v0.15.4 — Demo Export Preview / Red-Team Fail-Closed UI Behavior.

This document does not open new prototype screens.

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
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define a validation checklist and UI safety gate before v0.15 can be structurally sealed.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.15.5 validation principle is:

> “A prototype workspace may pass UI safety validation only if every visible interaction remains synthetic, non-clinical, non-authoritative, non-patient-facing, non-public-ready, non-product-ready, and non-validating.”

---

## 2. Relationship to Prior v0.15 Steps

v0.15.5 validates the following prior steps.

| Version | Layer | Validation Role |
|---|---|---|
| v0.15.0 | Prototype Workspace Entry Gate | Validates entry boundary, allowed/blocked prototype scope |
| v0.15.1 | Screen / Component Behavior Schema | Validates screen and component non-authority behavior |
| v0.15.2 | Synthetic Case Selection / Intake UI Flow | Validates synthetic-only selection and intake flow |
| v0.15.3 | Reasoning Map / Guided Visual Interaction | Validates visual reasoning safety |
| v0.15.4 | Export Preview / Red-Team Fail-Closed UI | Validates preview containment and unsafe language blocking |

v0.15.5 does not broaden v0.15.0–v0.15.4.

v0.15.5 must not open:

- real patient data,
- deidentified real patient data,
- real clinical intake,
- DICOM import,
- real report import,
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

Validation inheritance rule:

> Validation may check prototype safety, but it may not validate clinical performance.

---

## 3. Global Authority Envelope Validation

Every validation item must confirm the following authority envelope.

```yaml
authority_envelope_required:
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
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

Validation must fail if any screen, component, flow, map, preview, red-team state, modal, label, copy control, export control, audit trace, or safety state changes this envelope.

Authority validation rule:

> A prototype workspace cannot pass UI safety validation if any UI element implies clinical authority.

---

## 4. Global No-Decision Object Validation

Every decision-adjacent screen must preserve the no-decision object.

```yaml
no_decision_object_required:
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

Validation must fail if:

- the no-decision object is missing,
- any field is set to true,
- the object is contradicted by labels,
- the object is hidden on export preview,
- the object is absent from reasoning map,
- the object is absent from red-team fail-closed modal,
- the object is absent from audit trace.

No-decision validation rule:

> The workspace cannot pass if it shows reasoning without showing that no decision was made.

---

## 5. Validation Gate Object Schema

Every v0.15.5 validation gate must conform to the following schema.

```yaml
prototype_workspace_validation_gate:
  gate_id: string
  version: v0.15.5
  gate_name: string
  validates_versions:
    - v0.15.0
    - v0.15.1
    - v0.15.2
    - v0.15.3
    - v0.15.4
  gate_scope: prototype_ui_safety_only
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  patient_facing_effect: none
  required_checks: list
  fail_closed_conditions: list
  repair_required_conditions: list
  audit_required: true
  pass_state_allowed: true
  clinical_pass_state_allowed: false
```

Gate schema rule:

> The gate may pass UI safety, not clinical validity.

---

## 6. Validation Result Object Schema

Every validation result must conform to the following schema.

```yaml
prototype_workspace_validation_result:
  validation_result_id: string
  version: v0.15.5
  gate_id: string
  result_status: enum(pass_ui_safety, fail_closed, repair_required, not_run)
  clinical_validation_status: not_opened
  diagnostic_performance_status: not_measured
  product_ready: false
  public_ready: false
  patient_facing_use: not_allowed
  diagnostic_authority: none
  treatment_authority: none
  failed_checks: list
  passed_checks: list
  repair_required_items: list
  audit_event_ids: list
  authority_effect: none
  decision_effect: none
```

Blocked result statuses:

- clinically_validated,
- diagnostic_accuracy_passed,
- product_ready,
- public_ready,
- patient_ready,
- deployment_ready,
- expert_equivalent,
- MDD_replacement_ready.

Validation result rule:

> A pass means UI safety gate passed; it does not mean clinical validation passed.

---

## 7. Master Validation Checklist

The prototype workspace may pass v0.15.5 only if all checklist groups pass.

| Checklist Group | Required Result |
|---|---|
| v0.15.0 entry gate validation | pass |
| v0.15.1 screen/component validation | pass |
| v0.15.2 synthetic selection/intake flow validation | pass |
| v0.15.3 reasoning map validation | pass |
| v0.15.4 export preview/red-team validation | pass |
| synthetic-only validation | pass |
| real patient data block validation | pass |
| visual safety validation | pass |
| authority envelope validation | pass |
| no-decision object validation | pass |
| audit trace validation | pass |
| patient-facing leak validation | pass |
| public/product readiness overclaim validation | pass |
| clinical validation overclaim validation | pass |
| diagnostic/treatment/order/procedure/follow-up/triage authority validation | pass |
| MDD replacement block validation | pass |

Master checklist rule:

> One failed safety group fails the entire prototype workspace UI safety gate.

---

## 8. v0.15.0 Entry Gate Validation

The v0.15.0 entry gate passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| V15_0_CHECK_001 | prototype workspace scope defined | true |
| V15_0_CHECK_002 | synthetic demo-only case selection defined | true |
| V15_0_CHECK_003 | non-clinical UI boundary defined | true |
| V15_0_CHECK_004 | visually guided but text-governed principle preserved | true |
| V15_0_CHECK_005 | allowed prototype screens defined | true |
| V15_0_CHECK_006 | blocked prototype screens defined | true |
| V15_0_CHECK_007 | demo intake UI boundary defined | true |
| V15_0_CHECK_008 | reasoning map UI boundary defined | true |
| V15_0_CHECK_009 | missing evidence panel boundary defined | true |
| V15_0_CHECK_010 | mimic visibility panel boundary defined | true |
| V15_0_CHECK_011 | overlap panel boundary defined | true |
| V15_0_CHECK_012 | source status panel boundary defined | true |
| V15_0_CHECK_013 | red-team fail-closed UI boundary defined | true |
| V15_0_CHECK_014 | safe export preview UI boundary defined | true |
| V15_0_CHECK_015 | visual safety label integration required | true |
| V15_0_CHECK_016 | authority envelope display required | true |
| V15_0_CHECK_017 | no-decision object display required | true |
| V15_0_CHECK_018 | audit trace display required | true |
| V15_0_CHECK_019 | no real patient data | true |
| V15_0_CHECK_020 | no clinical validation | true |
| V15_0_CHECK_021 | no product readiness | true |
| V15_0_CHECK_022 | no public readiness | true |
| V15_0_CHECK_023 | no patient-facing use | true |

v0.15.0 validation rule:

> The entry gate passes only if prototype UI behavior is opened while clinical authority remains closed.

---

## 9. v0.15.1 Screen / Component Validation

The v0.15.1 screen/component layer passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| V15_1_CHECK_001 | screen object schema defined | true |
| V15_1_CHECK_002 | component object schema defined | true |
| V15_1_CHECK_003 | authority envelope inheritance required | true |
| V15_1_CHECK_004 | no-decision object inheritance required | true |
| V15_1_CHECK_005 | global allowed actions inspection-only | true |
| V15_1_CHECK_006 | global blocked clinical actions defined | true |
| V15_1_CHECK_007 | screen registry defined | true |
| V15_1_CHECK_008 | landing screen has boundary-first behavior | true |
| V15_1_CHECK_009 | synthetic case selector blocks real cases | true |
| V15_1_CHECK_010 | intake review screen blocks real intake | true |
| V15_1_CHECK_011 | reasoning map screen blocks diagnosis/action nodes | true |
| V15_1_CHECK_012 | missing evidence panel blocks missing-as-negative | true |
| V15_1_CHECK_013 | mimic visibility panel blocks diagnosis/exclusion | true |
| V15_1_CHECK_014 | overlap panel blocks winner selection | true |
| V15_1_CHECK_015 | source status panel blocks source-as-authority | true |
| V15_1_CHECK_016 | confidence limiter blocks probability/ranking | true |
| V15_1_CHECK_017 | review prompt panel blocks order/procedure/follow-up/triage | true |
| V15_1_CHECK_018 | red-team fail-closed screen blocks unsafe reuse | true |
| V15_1_CHECK_019 | safe export preview screen blocks clinical report behavior | true |
| V15_1_CHECK_020 | disabled-state semantics teach boundary | true |
| V15_1_CHECK_021 | unsafe copy behavior blocked | true |

Screen/component validation rule:

> Screens and components pass only if they remain governance visibility surfaces, not clinical controls.

---

## 10. v0.15.2 Synthetic Selection / Intake Flow Validation

The v0.15.2 flow passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| V15_2_CHECK_001 | prototype entry flow defined | true |
| V15_2_CHECK_002 | boundary acknowledgement required | true |
| V15_2_CHECK_003 | synthetic demo selector flow defined | true |
| V15_2_CHECK_004 | selected case state synthetic-only | true |
| V15_2_CHECK_005 | synthetic fixture binding defined | true |
| V15_2_CHECK_006 | fixture binding excludes real objects | true |
| V15_2_CHECK_007 | demo intake review flow defined | true |
| V15_2_CHECK_008 | supplied field interaction inspection-only | true |
| V15_2_CHECK_009 | missing field interaction preserves missingness | true |
| V15_2_CHECK_010 | real patient data flow blocked | true |
| V15_2_CHECK_011 | DICOM import flow blocked | true |
| V15_2_CHECK_012 | report paste flow blocked | true |
| V15_2_CHECK_013 | audit trace for selection/intake defined | true |
| V15_2_CHECK_014 | transition to reasoning map gated by synthetic binding | true |
| V15_2_CHECK_015 | transition to evidence panels safe | true |
| V15_2_CHECK_016 | selection fail-closed conditions defined | true |
| V15_2_CHECK_017 | intake fail-closed conditions defined | true |
| V15_2_CHECK_018 | UI copy requirements safe | true |
| V15_2_CHECK_019 | navigation constraints prevent authority escalation | true |
| V15_2_CHECK_020 | safe flow completion does not imply clinical validation | true |

Synthetic flow validation rule:

> The flow passes only if it moves through synthetic demo state without creating clinical intake.

---

## 11. v0.15.3 Reasoning Map Validation

The v0.15.3 reasoning map passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| V15_3_CHECK_001 | reasoning map object schema defined | true |
| V15_3_CHECK_002 | node schema defined | true |
| V15_3_CHECK_003 | edge schema defined | true |
| V15_3_CHECK_004 | node taxonomy allows only visibility/limitation/audit/authority nodes | true |
| V15_3_CHECK_005 | blocked node taxonomy excludes diagnosis/action nodes | true |
| V15_3_CHECK_006 | visual hierarchy does not imply certainty | true |
| V15_3_CHECK_007 | non-probabilistic state display enforced | true |
| V15_3_CHECK_008 | missing evidence node preserves missingness | true |
| V15_3_CHECK_009 | mimic visibility node preserves safety prompt | true |
| V15_3_CHECK_010 | overlap node preserves unresolved boundaries | true |
| V15_3_CHECK_011 | source status node preserves limitation | true |
| V15_3_CHECK_012 | confidence limiter node blocks probability | true |
| V15_3_CHECK_013 | review prompt node blocks action authority | true |
| V15_3_CHECK_014 | authority envelope node required | true |
| V15_3_CHECK_015 | no-decision node required | true |
| V15_3_CHECK_016 | audit trace node blocks correctness claim | true |
| V15_3_CHECK_017 | visual safety label node required | true |
| V15_3_CHECK_018 | color rules block probability/severity/confidence | true |
| V15_3_CHECK_019 | icon rules block authority | true |
| V15_3_CHECK_020 | edge visual rules block likelihood/action | true |
| V15_3_CHECK_021 | visual ranking blocked | true |
| V15_3_CHECK_022 | diagnostic closure blocked | true |
| V15_3_CHECK_023 | map-to-panel navigation constrained | true |
| V15_3_CHECK_024 | map fail-closed conditions defined | true |
| V15_3_CHECK_025 | audit hooks for map interaction defined | true |

Reasoning map validation rule:

> The map passes only if it guides attention without becoming probability, proof, diagnosis, recommendation, or action.

---

## 12. v0.15.4 Export Preview / Red-Team Validation

The v0.15.4 export preview and red-team UI pass only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| V15_4_CHECK_001 | export preview object schema defined | true |
| V15_4_CHECK_002 | red-team fail-closed object schema defined | true |
| V15_4_CHECK_003 | safe export preview screen behavior defined | true |
| V15_4_CHECK_004 | export preview section ordering puts safety first | true |
| V15_4_CHECK_005 | required export preview labels defined | true |
| V15_4_CHECK_006 | unsafe headings blocked | true |
| V15_4_CHECK_007 | diagnosis language blocked | true |
| V15_4_CHECK_008 | exclusion language blocked | true |
| V15_4_CHECK_009 | action language blocked | true |
| V15_4_CHECK_010 | patient-facing language blocked | true |
| V15_4_CHECK_011 | clinical validation overclaim blocked | true |
| V15_4_CHECK_012 | product/public readiness overclaim blocked | true |
| V15_4_CHECK_013 | red-team phrase display quarantined | true |
| V15_4_CHECK_014 | red-team scenario UI registry defined | true |
| V15_4_CHECK_015 | fail-closed modal behavior defined | true |
| V15_4_CHECK_016 | repair means UI safety repair only | true |
| V15_4_CHECK_017 | revalidation means UI safety revalidation only | true |
| V15_4_CHECK_018 | unsafe copy/export blocked | true |
| V15_4_CHECK_019 | export preview state machine defined | true |
| V15_4_CHECK_020 | authority envelope required in preview | true |
| V15_4_CHECK_021 | no-decision object required in preview | true |
| V15_4_CHECK_022 | audit trace hooks for export preview defined | true |
| V15_4_CHECK_023 | export preview fail-closed conditions defined | true |
| V15_4_CHECK_024 | copy control semantics safe | true |
| V15_4_CHECK_025 | export control semantics safe | true |
| V15_4_CHECK_026 | red-team does not equal clinical validation | true |
| V15_4_CHECK_027 | export preview does not equal MDD consensus | true |

Export/red-team validation rule:

> Export preview and red-team UI pass only if unsafe content fails closed before becoming reusable output.

---

## 13. Synthetic-Only Validation

The prototype workspace passes synthetic-only validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| SYN_CHECK_001 | all selectable cases are synthetic | true |
| SYN_CHECK_002 | all demo fixtures are synthetic | true |
| SYN_CHECK_003 | selected case origin is synthetic_demo_fixture | true |
| SYN_CHECK_004 | real_patient_data is false for demo artifacts | true |
| SYN_CHECK_005 | deidentified_real_patient_data is false for demo artifacts | true |
| SYN_CHECK_006 | clinical_validation_use is false | true |
| SYN_CHECK_007 | patient_facing_use is not_allowed | true |
| SYN_CHECK_008 | diagnostic_ground_truth is not exposed | true |
| SYN_CHECK_009 | final diagnosis field is absent | true |
| SYN_CHECK_010 | probability field is absent | true |
| SYN_CHECK_011 | synthetic label visible before reasoning content | true |
| SYN_CHECK_012 | synthetic label visible in export preview | true |
| SYN_CHECK_013 | synthetic label visible in red-team screen | true |
| SYN_CHECK_014 | synthetic label present in audit trace | true |

Synthetic-only validation rule:

> The workspace cannot pass if any demo object can be mistaken for a real patient case.

---

## 14. Real Patient Data Block Validation

The prototype workspace passes real patient data block validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| RPD_CHECK_001 | upload real patient file blocked | true |
| RPD_CHECK_002 | upload deidentified patient file blocked | true |
| RPD_CHECK_003 | paste real report blocked | true |
| RPD_CHECK_004 | enter patient identifier blocked | true |
| RPD_CHECK_005 | import DICOM blocked | true |
| RPD_CHECK_006 | import HRCT image blocked | true |
| RPD_CHECK_007 | connect PACS blocked | true |
| RPD_CHECK_008 | connect EHR blocked | true |
| RPD_CHECK_009 | real patient data attempt triggers fail-closed state | true |
| RPD_CHECK_010 | real patient data attempt records audit event | true |
| RPD_CHECK_011 | real patient data attempt cannot create workspace state | true |
| RPD_CHECK_012 | real patient data attempt cannot enter export preview | true |

Real patient data validation rule:

> Real patient data must fail closed before it becomes state.

---

## 15. Visual Safety Validation

The prototype workspace passes visual safety validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| VIS_CHECK_001 | visually guided but text-governed principle present | true |
| VIS_CHECK_002 | visual is not diagnosis label present | true |
| VIS_CHECK_003 | diagram is not proof label present | true |
| VIS_CHECK_004 | color is not probability label present | true |
| VIS_CHECK_005 | icon is not authority label present | true |
| VIS_CHECK_006 | flow is not treatment pathway label present | true |
| VIS_CHECK_007 | reasoning map blocks probability heatmaps | true |
| VIS_CHECK_008 | reasoning map blocks confidence meters | true |
| VIS_CHECK_009 | reasoning map blocks diagnostic ranking layout | true |
| VIS_CHECK_010 | color does not encode probability | true |
| VIS_CHECK_011 | color does not encode severity/triage | true |
| VIS_CHECK_012 | icon does not encode diagnosis/exclusion/action | true |
| VIS_CHECK_013 | edge thickness does not encode likelihood | true |
| VIS_CHECK_014 | visual hierarchy does not imply final diagnosis | true |
| VIS_CHECK_015 | visual artifact safety label visible in export preview | true |

Visual safety validation rule:

> Visuals pass only if they guide attention without creating clinical meaning.

---

## 16. Authority Envelope Validation

The authority envelope passes validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| AUTH_CHECK_001 | diagnostic_authority none | true |
| AUTH_CHECK_002 | treatment_authority none | true |
| AUTH_CHECK_003 | test_order_authority none | true |
| AUTH_CHECK_004 | procedure_decision_authority none | true |
| AUTH_CHECK_005 | follow_up_authority none | true |
| AUTH_CHECK_006 | triage_authority none | true |
| AUTH_CHECK_007 | patient_facing_use not_allowed | true |
| AUTH_CHECK_008 | public_ready false | true |
| AUTH_CHECK_009 | product_ready false | true |
| AUTH_CHECK_010 | clinically_reviewed_platform_wide false | true |
| AUTH_CHECK_011 | clinical_validation not_opened | true |
| AUTH_CHECK_012 | mdd_replacement not_allowed | true |
| AUTH_CHECK_013 | authority envelope visible on landing screen | true |
| AUTH_CHECK_014 | authority envelope visible on reasoning map | true |
| AUTH_CHECK_015 | authority envelope visible in export preview | true |
| AUTH_CHECK_016 | authority envelope visible in red-team fail-closed modal | true |
| AUTH_CHECK_017 | authority envelope recorded in audit trace | true |
| AUTH_CHECK_018 | no UI label contradicts authority envelope | true |

Authority envelope validation rule:

> Authority must be absent clinically and visible structurally.

---

## 17. No-Decision Object Validation

The no-decision object passes validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| ND_CHECK_001 | diagnosis_made false | true |
| ND_CHECK_002 | disease_excluded false | true |
| ND_CHECK_003 | mimic_excluded false | true |
| ND_CHECK_004 | treatment_selected false | true |
| ND_CHECK_005 | test_ordered false | true |
| ND_CHECK_006 | procedure_decided false | true |
| ND_CHECK_007 | follow_up_scheduled false | true |
| ND_CHECK_008 | triage_assigned false | true |
| ND_CHECK_009 | mdd_consensus_generated false | true |
| ND_CHECK_010 | patient_facing_output_generated false | true |
| ND_CHECK_011 | no-decision object visible on reasoning map | true |
| ND_CHECK_012 | no-decision object visible in export preview | true |
| ND_CHECK_013 | no-decision object visible in fail-closed modal | true |
| ND_CHECK_014 | no-decision object recorded in audit trace | true |
| ND_CHECK_015 | no UI copy contradicts no-decision object | true |

No-decision validation rule:

> The no-decision object must be structurally visible and semantically uncontradicted.

---

## 18. Audit Trace Validation

The audit trace passes validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| AUD_CHECK_001 | prototype boundary viewed event defined | true |
| AUD_CHECK_002 | synthetic case selected event defined | true |
| AUD_CHECK_003 | synthetic fixture bound event defined | true |
| AUD_CHECK_004 | intake review viewed event defined | true |
| AUD_CHECK_005 | missing field inspected event defined | true |
| AUD_CHECK_006 | reasoning map opened event defined | true |
| AUD_CHECK_007 | node expanded event defined | true |
| AUD_CHECK_008 | unsafe map state blocked event defined | true |
| AUD_CHECK_009 | export preview requested event defined | true |
| AUD_CHECK_010 | unsafe export preview blocked event defined | true |
| AUD_CHECK_011 | repair required event defined | true |
| AUD_CHECK_012 | UI safety revalidation event defined | true |
| AUD_CHECK_013 | real patient data attempt blocked event defined | true |
| AUD_CHECK_014 | unsafe copy/export attempt blocked event defined | true |
| AUD_CHECK_015 | every audit event has authority_effect none | true |
| AUD_CHECK_016 | every audit event has decision_effect none | true |
| AUD_CHECK_017 | audit trace does not claim correctness | true |
| AUD_CHECK_018 | audit trace does not claim clinical validation | true |

Audit trace validation rule:

> Audit trace validates traceability of UI state, not correctness of medical reasoning.

---

## 19. Patient-Facing Leak Validation

The prototype workspace passes patient-facing leak validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| PFL_CHECK_001 | patient-facing use remains not_allowed | true |
| PFL_CHECK_002 | patient summary screen absent | true |
| PFL_CHECK_003 | patient-friendly report absent | true |
| PFL_CHECK_004 | patient education visual absent | true |
| PFL_CHECK_005 | patient-facing export absent | true |
| PFL_CHECK_006 | patient-facing language blocked in preview | true |
| PFL_CHECK_007 | patient-facing language blocked in red-team examples | true |
| PFL_CHECK_008 | patient-facing copy/export blocked | true |
| PFL_CHECK_009 | patient-facing leak triggers fail-closed state | true |
| PFL_CHECK_010 | patient-facing leak records audit event | true |

Patient-facing validation rule:

> The prototype cannot pass if any output can be mistaken for patient material.

---

## 20. Public / Product Readiness Overclaim Validation

The prototype workspace passes public/product overclaim validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| PP_CHECK_001 | public_ready false | true |
| PP_CHECK_002 | product_ready false | true |
| PP_CHECK_003 | public-ready label blocked | true |
| PP_CHECK_004 | product-ready label blocked | true |
| PP_CHECK_005 | deployment-ready label blocked | true |
| PP_CHECK_006 | release-ready label blocked | true |
| PP_CHECK_007 | safe-for-use label blocked | true |
| PP_CHECK_008 | public publish control absent or disabled | true |
| PP_CHECK_009 | product release control absent or disabled | true |
| PP_CHECK_010 | public/product overclaim triggers fail-closed state | true |
| PP_CHECK_011 | public/product overclaim records audit event | true |

Public/product validation rule:

> A prototype may be internally demonstrable without being public-ready or product-ready.

---

## 21. Clinical Validation Overclaim Validation

The prototype workspace passes clinical validation overclaim validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| CLIN_VAL_CHECK_001 | clinical_validation remains not_opened | true |
| CLIN_VAL_CHECK_002 | diagnostic performance not measured | true |
| CLIN_VAL_CHECK_003 | accuracy claim absent | true |
| CLIN_VAL_CHECK_004 | sensitivity claim absent | true |
| CLIN_VAL_CHECK_005 | specificity claim absent | true |
| CLIN_VAL_CHECK_006 | AUC claim absent | true |
| CLIN_VAL_CHECK_007 | expert-equivalence claim absent | true |
| CLIN_VAL_CHECK_008 | red-team success not framed as clinical validation | true |
| CLIN_VAL_CHECK_009 | UI safety revalidation not framed as clinical validation | true |
| CLIN_VAL_CHECK_010 | audit trace not framed as correctness proof | true |
| CLIN_VAL_CHECK_011 | clinical validation overclaim triggers fail-closed state | true |
| CLIN_VAL_CHECK_012 | clinical validation overclaim records audit event | true |

Clinical validation overclaim rule:

> UI safety validation is not clinical validation.

---

## 22. Diagnostic / Treatment / Action Authority Validation

The prototype workspace passes diagnostic/treatment/action authority validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| ACTION_CHECK_001 | diagnosis generation blocked | true |
| ACTION_CHECK_002 | disease ranking blocked | true |
| ACTION_CHECK_003 | disease exclusion blocked | true |
| ACTION_CHECK_004 | mimic confirmation blocked | true |
| ACTION_CHECK_005 | mimic exclusion blocked | true |
| ACTION_CHECK_006 | treatment recommendation blocked | true |
| ACTION_CHECK_007 | test ordering blocked | true |
| ACTION_CHECK_008 | procedure recommendation blocked | true |
| ACTION_CHECK_009 | follow-up scheduling blocked | true |
| ACTION_CHECK_010 | triage/disposition blocked | true |
| ACTION_CHECK_011 | diagnosis/action language blocked in preview | true |
| ACTION_CHECK_012 | diagnosis/action nodes blocked in reasoning map | true |
| ACTION_CHECK_013 | diagnosis/action copy blocked | true |
| ACTION_CHECK_014 | diagnosis/action export blocked | true |
| ACTION_CHECK_015 | diagnosis/action attempt records audit event | true |

Action authority validation rule:

> If a UI behavior would matter clinically, it must be blocked.

---

## 23. MDD Replacement Block Validation

The prototype workspace passes MDD replacement validation only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| MDD_CHECK_001 | MDD replacement not_allowed | true |
| MDD_CHECK_002 | MDD consensus generated false | true |
| MDD_CHECK_003 | MDD preparation preview labeled as preparation only | true |
| MDD_CHECK_004 | MDD consensus screen absent | true |
| MDD_CHECK_005 | MDD agreement language blocked | true |
| MDD_CHECK_006 | multidisciplinary final decision language blocked | true |
| MDD_CHECK_007 | MDD preparation preview does not imply outcome | true |
| MDD_CHECK_008 | MDD replacement overclaim triggers fail-closed state | true |
| MDD_CHECK_009 | MDD replacement overclaim records audit event | true |

MDD validation rule:

> MDD preparation support is not MDD consensus or replacement.

---

## 24. Validation Fail-Closed Conditions

The entire v0.15.5 UI safety gate must fail closed under the following conditions.

```yaml
validation_fail_closed_conditions:
  authority_envelope_missing:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  no_decision_object_missing:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  synthetic_label_missing:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  real_patient_data_path_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  deidentified_real_patient_data_path_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  dicom_import_path_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  diagnostic_node_or_action_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  probability_or_ranking_display_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  unsafe_export_heading_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  unsafe_copy_export_path_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  patient_facing_leak_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  clinical_validation_overclaim_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
  product_or_public_ready_overclaim_detected:
    validation_result: fail_closed
    repair_required: true
    audit_required: true
```

Fail-closed validation rule:

> A failed safety gate must stop prototype progression before v0.15 structural seal.

---

## 25. Repair and Revalidation Rules

Repair in v0.15.5 means UI safety repair only.

Allowed repair actions:

- restore authority envelope,
- restore no-decision object,
- restore synthetic-only label,
- remove unsafe heading,
- remove diagnostic language,
- remove exclusion language,
- remove action language,
- remove patient-facing language,
- remove clinical validation overclaim,
- remove public/product readiness overclaim,
- disable unsafe copy/export path,
- remove real patient data path,
- restore audit event requirement,
- re-run UI safety validation.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- performance correction,
- accuracy improvement,
- clinical validation,
- product readiness fix,
- public readiness approval.

Revalidation means UI safety revalidation only.

Allowed revalidation:

- rerun checklist,
- rerun fail-closed conditions,
- verify repair applied,
- verify audit event recorded,
- verify no new authority opened.

Blocked revalidation:

- clinical validation,
- diagnostic performance validation,
- treatment safety validation,
- workflow deployment validation,
- expert equivalence validation,
- regulatory validation.

Repair/revalidation rule:

> Repair and revalidation protect prototype UI safety; they do not validate clinical performance.

---

## 26. Pass State Definition

A valid v0.15.5 pass state is:

```yaml
v0_15_5_pass_state:
  result_status: pass_ui_safety
  prototype_workspace_entry_gate_validated: true
  screen_component_behavior_validated: true
  synthetic_selection_intake_flow_validated: true
  reasoning_map_safety_validated: true
  export_preview_red_team_safety_validated: true
  synthetic_only_validated: true
  real_patient_data_block_validated: true
  visual_safety_validated: true
  authority_envelope_validated: true
  no_decision_object_validated: true
  audit_trace_validated: true
  patient_facing_leak_blocked: true
  public_product_overclaim_blocked: true
  clinical_validation_overclaim_blocked: true
  diagnostic_treatment_action_authority_blocked: true
  mdd_replacement_blocked: true
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

Blocked pass state meanings:

- clinically validated,
- product ready,
- public ready,
- patient-facing ready,
- diagnostic performance established,
- safe for clinical use,
- MDD replacement ready,
- deployment ready.

Pass state rule:

> v0.15.5 can pass UI safety only; it cannot pass clinical readiness.

---

## 27. v0.15.5 Acceptance Criteria

v0.15.5 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| validation gate object schema defined | true |
| validation result object schema defined | true |
| master validation checklist defined | true |
| v0.15.0 entry gate validation defined | true |
| v0.15.1 screen/component validation defined | true |
| v0.15.2 selection/intake flow validation defined | true |
| v0.15.3 reasoning map validation defined | true |
| v0.15.4 export/red-team validation defined | true |
| synthetic-only validation defined | true |
| real patient data block validation defined | true |
| visual safety validation defined | true |
| authority envelope validation defined | true |
| no-decision object validation defined | true |
| audit trace validation defined | true |
| patient-facing leak validation defined | true |
| public/product readiness overclaim validation defined | true |
| clinical validation overclaim validation defined | true |
| diagnostic/treatment/action authority validation defined | true |
| MDD replacement block validation defined | true |
| validation fail-closed conditions defined | true |
| repair/revalidation rules defined | true |
| pass state definition defined | true |
| real patient data remains blocked | true |
| deidentified real patient data remains blocked | true |
| clinical validation remains blocked | true |
| diagnostic performance claim remains blocked | true |
| product readiness remains false | true |
| public readiness remains false | true |
| patient-facing use remains not_allowed | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| order/procedure/follow-up/triage authority remains none | true |
| MDD replacement remains blocked | true |

v0.15.5 acceptance rule:

> The prototype workspace UI safety gate is accepted only if every v0.15 UI surface remains synthetic, non-clinical, non-authoritative, non-patient-facing, non-public-ready, non-product-ready, non-validating, and fail-closed.

---

## 28. Next Step

The next recommended step is:

- v0.15.6 — Prototype Workspace / Demo UI Behavior Structural Seal

v0.15.6 should structurally seal v0.15 after confirming:

- v0.15.0 entry gate is complete,
- v0.15.1 screen/component schema is complete,
- v0.15.2 synthetic case selection/intake UI flow is complete,
- v0.15.3 reasoning map contract is complete,
- v0.15.4 export preview/red-team fail-closed UI behavior is complete,
- v0.15.5 UI safety gate is complete,
- no real patient data opened,
- no clinical validation opened,
- no product readiness claimed,
- no public readiness claimed,
- no patient-facing use opened,
- no diagnostic/treatment/order/procedure/follow-up/triage authority opened,
- no MDD replacement opened.

v0.15.6 must not open clinical deployment, real patient data, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 29. Governance Statement

This document defines the prototype workspace validation checklist and UI safety gate.

It validates UI safety behavior only.

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
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.15.5 governance discipline is:

> “Do not let UI safety validation become clinical validation.”

The pre-seal discipline is:

> “Do not seal v0.15 unless every prototype UI surface remains synthetic, non-clinical, non-authoritative, non-patient-facing, non-public-ready, non-product-ready, non-validating, and fail-closed.”