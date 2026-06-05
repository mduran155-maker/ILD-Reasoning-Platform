# ILD Reasoning Platform — Demo Workspace Screen / Component Behavior Schema v1

Version: v0.15.1  
Status: demo_workspace_screen_component_behavior_schema  
Scope: Prototype workspace screen schema, component behavior schema, synthetic-only UI binding, non-clinical component semantics, required safety labels, authority envelope placement, no-decision object placement, allowed/blocked actions, disabled-state semantics, fail-closed UI states, audit trace hooks, visual/text governance, and safe export preview component behavior  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.15.1 — Demo Workspace Screen / Component Behavior Schema.

v0.15.1 converts the v0.15.0 Prototype Workspace / Demo UI Behavior Contract Entry Gate into concrete prototype screen and component behavior rules.

This document does not add new clinical content.

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
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to define how each allowed prototype workspace screen and component may behave while preserving the synthetic-only, non-clinical, non-authoritative boundary.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.15.1 component principle is:

> “A prototype component may display governed reasoning state, but it must not become a clinical control.”

---

## 2. Relationship to v0.15.0

v0.15.1 inherits the v0.15.0 entry gate.

v0.15.0 opened:

- prototype workspace scope,
- synthetic demo-only case selection,
- non-clinical UI boundary,
- visually guided but text-governed interaction,
- allowed prototype screens,
- blocked prototype screens,
- demo intake UI boundary,
- reasoning map UI boundary,
- missing evidence panel UI boundary,
- mimic visibility panel UI boundary,
- overlap panel UI boundary,
- source status panel UI boundary,
- red-team fail-closed UI boundary,
- safe export preview UI boundary,
- visual safety label integration,
- authority envelope display requirement,
- no-decision object display requirement,
- audit trace display requirement.

v0.15.1 does not broaden v0.15.0.

v0.15.1 only defines concrete screen and component behavior for the prototype surfaces already opened.

v0.15.1 must not open:

- real patient data,
- deidentified real patient data,
- real clinical intake,
- diagnostic output,
- disease ranking,
- treatment recommendation,
- test ordering,
- procedure recommendation,
- follow-up scheduling,
- triage,
- patient-facing output,
- public-ready output,
- product-ready output,
- platform-wide clinical review,
- clinical validation,
- diagnostic performance measurement,
- MDD replacement.

---

## 3. Global Authority Envelope

Every v0.15.1 screen and component must inherit the following authority envelope.

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
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

No screen or component may override, hide, soften, collapse, visually contradict, or semantically dilute this envelope.

Authority inheritance rule:

> Every prototype component must inherit non-authority before it displays reasoning content.

---

## 4. Global No-Decision Object

Every decision-adjacent prototype screen must display or directly link to the no-decision object.

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

No-decision inheritance rule:

> If a screen shows reasoning, it must also show what the platform did not decide.

---

## 5. Screen Object Schema

Every prototype screen must conform to the following screen object schema.

```yaml
prototype_screen:
  screen_id: string
  version: v0.15.1
  screen_name: string
  screen_category: enum
  prototype_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  real_patient_data_allowed: false
  diagnostic_authority: none
  treatment_authority: none
  required_safety_labels: list
  required_authority_envelope_display: true
  required_no_decision_object_display: conditional_required
  required_audit_trace_hook: true
  required_visual_text_governance: true
  allowed_components: list
  blocked_components: list
  allowed_actions: list
  blocked_actions: list
  disabled_state_semantics: list
  fail_closed_states: list
  export_allowed: false_or_preview_only
  audit_events_emitted: list
```

Required screen categories:

| Category | Meaning |
|---|---|
| prototype_boundary | States prototype/non-clinical limits |
| synthetic_case_selection | Selects sealed fictional scenarios only |
| synthetic_intake_review | Displays fictional supplied/missing context |
| reasoning_visibility | Shows governed reasoning state |
| evidence_visibility | Shows missing evidence/source/mimic/overlap state |
| safety_visibility | Shows authority/no-decision/fail-closed state |
| export_preview | Shows non-diagnostic safe export preview only |
| audit_visibility | Shows traceability without correctness claim |

Screen schema rule:

> A screen is valid only if its schema makes clinical authority impossible.

---

## 6. Component Object Schema

Every prototype component must conform to the following component object schema.

```yaml
prototype_component:
  component_id: string
  component_name: string
  component_type: enum
  parent_screen_id: string
  prototype_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  authority_effect: none
  decision_effect: none
  data_origin: synthetic_fixture_only
  visual_semantics: text_governed
  allowed_states: list
  blocked_states: list
  allowed_actions: list
  blocked_actions: list
  required_label: string_or_list
  required_tooltip: string_or_list
  required_audit_hook: true
  unsafe_copy_block: true
  export_behavior: preview_only_or_blocked
```

Required component types:

| Component Type | Allowed Meaning |
|---|---|
| safety_banner | States synthetic/non-clinical/prototype limits |
| case_card | Shows synthetic demo scenario identity |
| intake_field_table | Shows supplied vs missing fictional data |
| reasoning_node | Shows governed reasoning-state node |
| reasoning_edge | Shows relationship without probability |
| evidence_card | Shows missing/source/mimic/overlap state |
| limitation_card | Shows confidence/source/temporal limitation |
| review_prompt_card | Shows review prompt without action authority |
| fail_closed_card | Shows unsafe state blocked |
| export_preview_section | Shows safe export preview section |
| authority_card | Shows authority envelope |
| no_decision_card | Shows decisions not made |
| audit_event_row | Shows traceability event |
| disabled_control | Shows blocked action without enabling it |

Component schema rule:

> A component may expose visibility, limitation, or traceability; it may not expose clinical action.

---

## 7. Allowed Global UI Actions

The following actions are allowed across v0.15.1 only when bound to synthetic demo artifacts.

| Action | Allowed Meaning |
|---|---|
| view | View a synthetic prototype screen |
| select_synthetic_demo_case | Select a sealed fictional scenario |
| expand | Expand explanatory governance text |
| collapse | Collapse explanatory governance text |
| filter_demo_cases | Filter synthetic cases by governance behavior |
| sort_demo_cases | Sort synthetic cases by demo category |
| inspect_fixture | Inspect synthetic fixture fields |
| inspect_missing_evidence | Inspect why evidence is missing |
| inspect_mimic_visibility | Inspect visible mimic prompts |
| inspect_overlap | Inspect unresolved overlap prompts |
| inspect_source_status | Inspect source role and limitation |
| inspect_authority_envelope | Inspect non-authority boundary |
| inspect_no_decision_object | Inspect explicit decisions not made |
| inspect_audit_trace | Inspect traceability without correctness claim |
| preview_safe_export | Preview non-diagnostic MDD preparation export |
| view_fail_closed_reason | Inspect why unsafe output was blocked |

Allowed action rule:

> Allowed actions are inspection actions, not clinical actions.

---

## 8. Blocked Global UI Actions

The following actions are blocked across v0.15.1.

| Blocked Action | Reason |
|---|---|
| upload_real_patient_data | real patient data blocked |
| upload_deidentified_patient_data | deidentified real patient data blocked |
| import_dicom | clinical imaging import blocked |
| paste_real_report | real report ingestion blocked |
| enter_patient_identifier | patient identifier blocked |
| generate_diagnosis | diagnostic authority blocked |
| rank_diagnoses | probability/ranking blocked |
| rule_out_disease | exclusion authority blocked |
| confirm_mimic | diagnostic authority blocked |
| exclude_mimic | exclusion authority blocked |
| recommend_treatment | treatment authority blocked |
| order_test | test-order authority blocked |
| recommend_procedure | procedure authority blocked |
| schedule_follow_up | follow-up authority blocked |
| assign_triage | triage authority blocked |
| generate_patient_summary | patient-facing output blocked |
| publish_public_demo | public-ready output blocked |
| mark_product_ready | product-readiness overclaim blocked |
| mark_clinically_validated | clinical validation overclaim blocked |
| claim_diagnostic_performance | diagnostic performance claim blocked |
| generate_mdd_consensus | MDD replacement blocked |

Blocked action rule:

> If an action would matter clinically, it is not a prototype action.

---

## 9. Screen Registry

The following prototype screens are registered for v0.15.1.

| Screen ID | Screen Name | Category | Status |
|---|---|---|---|
| V15_SCREEN_001 | Prototype Boundary Landing Screen | prototype_boundary | allowed |
| V15_SCREEN_002 | Synthetic Demo Case Selector | synthetic_case_selection | allowed |
| V15_SCREEN_003 | Demo Intake Review Screen | synthetic_intake_review | allowed |
| V15_SCREEN_004 | Reasoning Map Screen | reasoning_visibility | allowed |
| V15_SCREEN_005 | Missing Evidence Panel | evidence_visibility | allowed |
| V15_SCREEN_006 | Mimic Visibility Panel | evidence_visibility | allowed |
| V15_SCREEN_007 | Overlap Panel | evidence_visibility | allowed |
| V15_SCREEN_008 | Source Status Panel | evidence_visibility | allowed |
| V15_SCREEN_009 | Confidence Limiter Panel | reasoning_visibility | allowed |
| V15_SCREEN_010 | Review Prompt Panel | reasoning_visibility | allowed |
| V15_SCREEN_011 | Red-Team Fail-Closed Screen | safety_visibility | allowed |
| V15_SCREEN_012 | Safe Export Preview Screen | export_preview | allowed |
| V15_SCREEN_013 | Authority Envelope Display | safety_visibility | required |
| V15_SCREEN_014 | No-Decision Object Display | safety_visibility | required |
| V15_SCREEN_015 | Audit Trace Screen | audit_visibility | allowed |
| V15_SCREEN_016 | Visual Safety Label Display | safety_visibility | required |

Screen registry rule:

> Registered screens are allowed only within synthetic prototype demonstration.

---

## 10. Prototype Boundary Landing Screen Schema

```yaml
screen_id: V15_SCREEN_001
screen_name: Prototype Boundary Landing Screen
screen_category: prototype_boundary
required_components:
  - synthetic_demo_only_banner
  - not_for_clinical_use_banner
  - not_patient_facing_banner
  - public_ready_false_label
  - product_ready_false_label
  - authority_envelope_card
  - no_decision_object_card
  - proceed_to_synthetic_case_selector_control
allowed_actions:
  - view
  - inspect_authority_envelope
  - inspect_no_decision_object
  - proceed_to_synthetic_case_selector
blocked_actions:
  - upload_real_patient_data
  - enter_patient_identifier
  - generate_diagnosis
  - publish_public_demo
```

Landing screen rule:

> The first prototype screen must say what the platform is not before showing what it can demonstrate.

---

## 11. Synthetic Demo Case Selector Schema

```yaml
screen_id: V15_SCREEN_002
screen_name: Synthetic Demo Case Selector
screen_category: synthetic_case_selection
required_components:
  - synthetic_case_list
  - synthetic_case_card
  - scenario_governance_behavior_label
  - synthetic_only_badge
  - real_patient_data_false_badge
  - clinical_validation_false_badge
  - authority_envelope_footer
  - audit_trace_hook
allowed_actions:
  - view
  - filter_demo_cases
  - sort_demo_cases
  - select_synthetic_demo_case
  - inspect_fixture
blocked_actions:
  - upload_real_patient_data
  - upload_deidentified_patient_data
  - paste_real_report
  - import_dicom
  - show_diagnostic_ground_truth
  - show_final_diagnosis
  - show_disease_probability
```

Synthetic selector rule:

> The selector chooses fictional governance scenarios, not patient cases.

---

## 12. Demo Intake Review Screen Schema

```yaml
screen_id: V15_SCREEN_003
screen_name: Demo Intake Review Screen
screen_category: synthetic_intake_review
required_components:
  - synthetic_intake_field_table
  - supplied_field_badge
  - missing_field_badge
  - provided_vs_inferred_boundary_label
  - no_real_patient_data_label
  - source_status_summary_card
  - missing_evidence_summary_card
  - authority_envelope_footer
  - audit_trace_hook
allowed_actions:
  - view
  - inspect_fixture
  - inspect_missing_evidence
  - inspect_source_status
blocked_actions:
  - edit_as_real_case
  - auto_infer_missing_field
  - convert_missing_to_negative
  - upload_real_patient_data
  - import_dicom
  - generate_diagnosis
```

Demo intake rule:

> Demo intake displays fictional field state; it does not collect clinical data.

---

## 13. Reasoning Map Screen Schema

```yaml
screen_id: V15_SCREEN_004
screen_name: Reasoning Map Screen
screen_category: reasoning_visibility
required_components:
  - reasoning_node_case_context
  - reasoning_node_missing_evidence
  - reasoning_node_mimic_visibility
  - reasoning_node_overlap
  - reasoning_node_source_status
  - reasoning_node_confidence_limiter
  - reasoning_node_review_prompt
  - reasoning_node_authority_envelope
  - reasoning_node_no_decision_object
  - text_governs_visual_meaning_label
  - audit_trace_hook
allowed_actions:
  - view
  - expand
  - collapse
  - inspect_missing_evidence
  - inspect_mimic_visibility
  - inspect_overlap
  - inspect_source_status
  - inspect_authority_envelope
  - inspect_no_decision_object
blocked_actions:
  - add_final_diagnosis_node
  - add_probability_edge
  - add_disease_winner_node
  - add_treatment_action_node
  - add_test_order_node
  - add_follow_up_node
  - add_triage_node
```

Reasoning map rule:

> The map shows governed relationships, not diagnostic proof.

---

## 14. Missing Evidence Panel Schema

```yaml
screen_id: V15_SCREEN_005
screen_name: Missing Evidence Panel
screen_category: evidence_visibility
required_components:
  - missing_evidence_item_card
  - missing_reason_label
  - interpretation_limiter_label
  - no_exclusion_from_missingness_label
  - related_review_prompt_link
  - audit_trace_hook
allowed_actions:
  - view
  - inspect_missing_evidence
  - expand
  - collapse
blocked_actions:
  - mark_missing_as_negative
  - mark_missing_as_excluded
  - infer_missing_value
  - schedule_follow_up
  - order_test
```

Missing evidence rule:

> Missing evidence limits interpretation; it never excludes disease.

---

## 15. Mimic Visibility Panel Schema

```yaml
screen_id: V15_SCREEN_006
screen_name: Mimic Visibility Panel
screen_category: evidence_visibility
required_components:
  - mimic_family_visibility_card
  - source_limited_prompt_badge
  - mimic_not_confirmed_label
  - mimic_not_excluded_label
  - missing_evidence_dependency_label
  - audit_trace_hook
allowed_actions:
  - view
  - inspect_mimic_visibility
  - inspect_source_status
  - expand
  - collapse
blocked_actions:
  - confirm_mimic
  - exclude_mimic
  - rank_mimics
  - hide_mimic_due_to_primary_pattern
  - recommend_treatment
  - recommend_procedure
```

Mimic visibility rule:

> Mimic visibility is a safety prompt, not a diagnosis or exclusion list.

---

## 16. Overlap Panel Schema

```yaml
screen_id: V15_SCREEN_007
screen_name: Overlap Panel
screen_category: evidence_visibility
required_components:
  - overlap_state_card
  - unresolved_boundary_label
  - no_winner_selected_label
  - source_limitation_label
  - missing_evidence_dependency_label
  - audit_trace_hook
allowed_actions:
  - view
  - inspect_overlap
  - inspect_missing_evidence
  - inspect_source_status
blocked_actions:
  - choose_winner
  - rank_overlap_entities
  - collapse_to_single_diagnosis
  - convert_overlap_to_treatment
  - convert_overlap_to_test_order
  - assign_triage
```

Overlap panel rule:

> Overlap remains unresolved until human clinical review outside the platform.

---

## 17. Source Status Panel Schema

```yaml
screen_id: V15_SCREEN_008
screen_name: Source Status Panel
screen_category: evidence_visibility
required_components:
  - source_role_card
  - source_status_badge
  - source_limitation_label
  - source_to_claim_mapping_link
  - source_does_not_grant_authority_label
  - audit_trace_hook
allowed_actions:
  - view
  - inspect_source_status
  - expand
  - collapse
blocked_actions:
  - mark_source_as_diagnostic_confirmation
  - mark_source_as_clinical_validation
  - override_missing_evidence_with_source
  - authorize_treatment_from_source
  - authorize_order_from_source
```

Source status rule:

> Sources support visibility and limitation; they do not grant authority.

---

## 18. Confidence Limiter Panel Schema

```yaml
screen_id: V15_SCREEN_009
screen_name: Confidence Limiter Panel
screen_category: reasoning_visibility
required_components:
  - confidence_limiter_card
  - no_probability_label
  - no_ranking_label
  - limitation_reason_list
  - missing_evidence_dependency_label
  - source_status_dependency_label
  - audit_trace_hook
allowed_actions:
  - view
  - expand
  - collapse
  - inspect_missing_evidence
  - inspect_source_status
blocked_actions:
  - show_confidence_score
  - show_probability
  - rank_diagnoses
  - display_auc_sensitivity_specificity
  - convert_limiter_to_diagnostic_certainty
```

Confidence limiter rule:

> A confidence limiter explains why certainty is limited; it does not estimate diagnostic probability.

---

## 19. Review Prompt Panel Schema

```yaml
screen_id: V15_SCREEN_010
screen_name: Review Prompt Panel
screen_category: reasoning_visibility
required_components:
  - review_prompt_card
  - prompt_reason_label
  - prompt_is_not_order_label
  - prompt_is_not_procedure_decision_label
  - prompt_is_not_follow_up_schedule_label
  - authority_envelope_footer
  - audit_trace_hook
allowed_actions:
  - view
  - expand
  - collapse
  - inspect_audit_trace
blocked_actions:
  - order_test
  - recommend_procedure
  - schedule_follow_up
  - assign_triage
  - bypass_mdd
  - mark_review_complete
```

Review prompt rule:

> A prompt preserves review visibility; it does not command clinical action.

---

## 20. Red-Team Fail-Closed Screen Schema

```yaml
screen_id: V15_SCREEN_011
screen_name: Red-Team Fail-Closed Screen
screen_category: safety_visibility
required_components:
  - unsafe_attempt_card
  - blocked_state_badge
  - failure_reason_card
  - repair_required_label
  - revalidation_required_label
  - authority_effect_none_label
  - audit_event_row
allowed_actions:
  - view
  - view_fail_closed_reason
  - inspect_audit_trace
blocked_actions:
  - bypass_block
  - export_unsafe_output
  - copy_unsafe_text_as_clinical_content
  - mark_red_team_as_clinical_validation
  - mark_failure_as_product_safe
```

Red-team fail-closed rule:

> Red-team UI demonstrates blocked unsafe behavior, not clinical advice.

---

## 21. Safe Export Preview Screen Schema

```yaml
screen_id: V15_SCREEN_012
screen_name: Safe Export Preview Screen
screen_category: export_preview
required_components:
  - synthetic_demo_export_label
  - non_clinical_export_label
  - mdd_preparation_not_mdd_consensus_label
  - safe_export_section_preview
  - source_status_section_preview
  - missing_evidence_section_preview
  - mimic_visibility_section_preview
  - overlap_section_preview
  - confidence_limiter_section_preview
  - authority_envelope_section
  - no_decision_object_section
  - audit_reference_section
allowed_actions:
  - view
  - preview_safe_export
  - inspect_authority_envelope
  - inspect_no_decision_object
  - inspect_audit_trace
blocked_actions:
  - generate_diagnostic_report
  - add_impression_heading
  - add_diagnosis_heading
  - add_probability_table
  - add_treatment_recommendation
  - add_test_order
  - add_follow_up_schedule
  - generate_patient_summary
```

Safe export preview rule:

> Export preview shows safe formatting behavior, not a clinical report.

---

## 22. Authority Envelope Display Schema

```yaml
screen_id: V15_SCREEN_013
screen_name: Authority Envelope Display
screen_category: safety_visibility
required_components:
  - diagnostic_authority_none_label
  - treatment_authority_none_label
  - order_authority_none_label
  - procedure_authority_none_label
  - follow_up_authority_none_label
  - triage_authority_none_label
  - patient_facing_not_allowed_label
  - public_ready_false_label
  - product_ready_false_label
  - clinical_validation_not_opened_label
allowed_actions:
  - view
  - inspect_authority_envelope
blocked_actions:
  - hide_authority_envelope
  - convert_authority_label_to_badge_only
  - mark_any_authority_active
```

Authority envelope display rule:

> The UI must show lack of authority before any user can mistake the prototype for a clinical tool.

---

## 23. No-Decision Object Display Schema

```yaml
screen_id: V15_SCREEN_014
screen_name: No-Decision Object Display
screen_category: safety_visibility
required_components:
  - diagnosis_made_false_row
  - disease_excluded_false_row
  - mimic_excluded_false_row
  - treatment_selected_false_row
  - test_ordered_false_row
  - procedure_decided_false_row
  - follow_up_scheduled_false_row
  - triage_assigned_false_row
  - mdd_consensus_generated_false_row
  - patient_facing_output_generated_false_row
allowed_actions:
  - view
  - inspect_no_decision_object
blocked_actions:
  - hide_no_decision_object
  - contradict_no_decision_object
  - mark_any_decision_true
```

No-decision display rule:

> The prototype must show what it did not decide as clearly as what it displayed.

---

## 24. Audit Trace Screen Schema

```yaml
screen_id: V15_SCREEN_015
screen_name: Audit Trace Screen
screen_category: audit_visibility
required_components:
  - audit_event_list
  - event_timestamp_or_sequence_id
  - event_source_screen_id
  - event_component_id
  - event_reason_label
  - authority_effect_none_label
  - correctness_not_proven_label
allowed_actions:
  - view
  - inspect_audit_trace
  - filter_audit_events
blocked_actions:
  - mark_audit_as_clinical_validation
  - mark_audit_as_correctness_proof
  - mark_audit_as_diagnostic_performance
  - edit_audit_to_hide_failure
```

Audit trace rule:

> Audit trace explains UI state, not medical truth.

---

## 25. Visual Safety Label Display Schema

```yaml
screen_id: V15_SCREEN_016
screen_name: Visual Safety Label Display
screen_category: safety_visibility
required_components:
  - visual_is_not_diagnosis_label
  - diagram_is_not_proof_label
  - color_is_not_probability_label
  - icon_is_not_authority_label
  - flow_is_not_treatment_pathway_label
  - text_governs_visual_meaning_label
allowed_actions:
  - view
  - inspect_authority_envelope
blocked_actions:
  - hide_visual_safety_label
  - use_color_as_probability
  - use_icon_as_authority
  - use_flow_as_treatment_pathway
```

Visual safety label rule:

> No strong visual may appear without a text safety boundary.

---

## 26. Disabled-State Semantics

Disabled controls must explain why they are disabled.

Allowed disabled-state examples:

| Disabled Control | Required Explanation |
|---|---|
| Upload real patient data | Real patient data is not allowed in prototype demo workspace |
| Import DICOM | Clinical imaging import is not opened |
| Generate diagnosis | Diagnostic authority is none |
| Recommend treatment | Treatment authority is none |
| Order test | Test-order authority is none |
| Schedule follow-up | Follow-up authority is none |
| Assign triage | Triage authority is none |
| Generate patient summary | Patient-facing use is not allowed |
| Publish public demo | Public readiness is false |
| Mark clinically validated | Clinical validation is not opened |

Disabled-state rule:

> A disabled control must teach the boundary; it must not tease a hidden clinical feature.

---

## 27. Fail-Closed UI States

The prototype workspace must support the following fail-closed states.

```yaml
fail_closed_states:
  unsafe_language_detected:
    export_allowed: false
    repair_required: true
    audit_required: true
  unsafe_heading_detected:
    export_allowed: false
    repair_required: true
    audit_required: true
  authority_envelope_missing:
    export_allowed: false
    repair_required: true
    audit_required: true
  no_decision_object_missing:
    export_allowed: false
    repair_required: true
    audit_required: true
  patient_facing_language_detected:
    export_allowed: false
    repair_required: true
    audit_required: true
  real_patient_data_attempted:
    intake_allowed: false
    workspace_allowed: false
    audit_required: true
  clinical_validation_claim_detected:
    display_allowed: false
    repair_required: true
    audit_required: true
  product_ready_claim_detected:
    display_allowed: false
    repair_required: true
    audit_required: true
```

Fail-closed rule:

> Unsafe UI state must close safely before it becomes visible as usable clinical content.

---

## 28. Component Copy and Language Safety

Prototype components must block unsafe copy paths.

Allowed copy behavior:

- copy synthetic demo case ID,
- copy non-clinical demo label,
- copy governance behavior label,
- copy authority envelope text,
- copy no-decision object text,
- copy audit trace event ID,
- copy safe export preview only when validation state is safe.

Blocked copy behavior:

- copy unsafe red-team phrase as usable output,
- copy diagnosis phrase,
- copy disease exclusion phrase,
- copy treatment recommendation,
- copy test order phrase,
- copy procedure recommendation,
- copy follow-up schedule,
- copy triage phrase,
- copy patient-facing summary,
- copy clinical validation claim,
- copy product-ready claim,
- copy public-ready claim.

Copy safety rule:

> A prototype component must not make unsafe language easier to reuse.

---

## 29. v0.15.1 Acceptance Criteria

v0.15.1 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| screen object schema defined | true |
| component object schema defined | true |
| authority envelope inheritance required | true |
| no-decision object inheritance required | true |
| global allowed actions defined | true |
| global blocked actions defined | true |
| screen registry defined | true |
| prototype landing screen schema defined | true |
| synthetic case selector schema defined | true |
| demo intake review screen schema defined | true |
| reasoning map screen schema defined | true |
| missing evidence panel schema defined | true |
| mimic visibility panel schema defined | true |
| overlap panel schema defined | true |
| source status panel schema defined | true |
| confidence limiter panel schema defined | true |
| review prompt panel schema defined | true |
| red-team fail-closed screen schema defined | true |
| safe export preview screen schema defined | true |
| authority envelope display schema defined | true |
| no-decision object display schema defined | true |
| audit trace screen schema defined | true |
| visual safety label display schema defined | true |
| disabled-state semantics defined | true |
| fail-closed UI states defined | true |
| unsafe copy behavior blocked | true |
| real patient data remains blocked | true |
| clinical validation remains blocked | true |
| product readiness remains blocked | true |
| public readiness remains blocked | true |
| patient-facing use remains blocked | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| order/procedure/follow-up/triage authority remains none | true |
| MDD replacement remains blocked | true |

v0.15.1 acceptance rule:

> Component behavior is accepted only if every screen remains a governance visibility surface, not a clinical decision surface.

---

## 30. Next Step

The next recommended step is:

- v0.15.2 — Demo Case Selection / Synthetic Intake UI Flow

v0.15.2 should define:

- prototype entry flow from landing screen to synthetic case selector,
- synthetic case selection state machine,
- synthetic intake review flow,
- supplied-vs-missing field interaction,
- synthetic fixture binding to workspace state,
- blocked real patient data flow,
- blocked DICOM/report import flow,
- audit trace for selection and intake review,
- transition into reasoning map and evidence panels.

v0.15.2 must not open clinical deployment, real patient data, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 31. Governance Statement

This document defines prototype screen and component behavior for the synthetic demo workspace.

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
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.15.1 governance discipline is:

> “Do not let a prototype component become a clinical control.”