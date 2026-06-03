# Test Case Coverage Matrix — v1

## Document Metadata

```yaml
id: data_schema_test_case_coverage_matrix_v1
title: Test Case Coverage Matrix
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_coverage_schema
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
last_updated: draft
```

---

## 0. Purpose

This matrix defines the minimum test-case coverage required for ILD Reasoning Platform pages.

It verifies that each major page is not only structurally written, but stress-tested against:

- typical presentations,
- indeterminate / gray-zone presentations,
- mimic-dominant presentations,
- red-flag / urgent-review presentations.

This does not validate clinical correctness.

It creates a structured test-case expansion plan for future expert review.

---

## 1. Core Rule

```yaml
core_rule:
  statement: >
    A page is not mature because it describes a disease or pattern.
    A page becomes mature when it survives representative, ambiguous, mimic-dominant, and red-flag cases.

  platform_must_not:
    - rely_on_one_test_case_per_page
    - test_only_typical_presentations
    - hide_mimic_dominant_cases
    - ignore_red_flag_or_urgent_review_cases
    - treat_test_case_pass_as_clinical_validation
    - declare_public_ready_from_blueprint_test_cases

  platform_must:
    - define_minimum_case_types_per_major_page
    - expose_missing_data_in_each_case
    - preserve_uncertainty
    - show_why_not_reasoning
    - include_mimics
    - include_temporal_context_when relevant
    - flag_MDD_or_specialist_review_when appropriate
```

---

## 2. Required Test Case Types

```yaml
required_test_case_types:
  typical_scenario:
    purpose: Demonstrates the expected teaching pathway.
    required_output:
      - pattern_support
      - key_supporting_features
      - missing_pieces
      - why_not_engine
      - final_uncertainty_prompt

  indeterminate_gray_zone_scenario:
    purpose: Tests whether the page preserves uncertainty when signals conflict.
    required_output:
      - competing_reasoning_paths
      - insufficient_data
      - gray_zone_flags
      - MDD_or_specialist_review_prompt
      - cannot_conclude_list

  alternative_diagnosis_mimic_dominant_scenario:
    purpose: Tests whether the page can weaken the assumed label and route to mimics.
    required_output:
      - mimic_support
      - target_diagnosis_weakening_features
      - route_to_related_module
      - missing_data_that_would_change_reasoning

  red_flag_urgent_review_scenario:
    purpose: Tests whether dangerous findings are not swallowed by baseline disease labels.
    required_output:
      - red_flags
      - urgent_or_specialist_review_prompt
      - cannot_call_benign_or_baseline
      - high_risk_missing_data
```

---

## 3. Minimum Coverage Standard

```yaml
minimum_coverage_standard:
  major_pattern_pages:
    required_cases_per_page: 4
    required_case_types:
      - typical_scenario
      - indeterminate_gray_zone_scenario
      - alternative_diagnosis_mimic_dominant_scenario
      - red_flag_urgent_review_scenario

  major_reasoning_maps:
    required_cases_per_page: 4
    required_case_types:
      - typical_scenario
      - indeterminate_gray_zone_scenario
      - mimic_dominant_scenario
      - red_flag_or_urgent_review_scenario

  seal_or_checklist_pages:
    required_cases_per_page: 0
    reason: governance documents do not require clinical scenario testing

  evidence_governance_pages:
    required_cases_per_page: 0
    reason: evidence documents require claim-mapping tests, not clinical case tests

  current_public_ready_policy:
    public_ready_allowed: false
    reason:
      - test_cases_are_blueprint_level
      - expert_review_not_completed
      - full_text_review_not_completed
```

---

## 4. Current Coverage Snapshot

```yaml
current_coverage_snapshot:
  known_issue:
    - many_pages_have_zero_or_one_test_case
    - most_pages_do_not_yet_have_four_case_types
    - typical_cases_are_overrepresented
    - mimic_dominant_and_red_flag_cases_need_expansion

  audit_blocker:
    test_coverage_score: low_to_moderate
    public_ready_impact: blocking
    next_action:
      - create_case_packs_for_high_priority_pages
```

---

## 5. Priority Pages for Test Case Expansion

```yaml
priority_pages:
  tier_1_highest_priority:
    - docs/reasoning/temporal_comparison_methodology_v1.md
    - docs/reasoning/superimposed_events_core_blueprint_v1.md
    - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    - docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    - docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md

  tier_2_pattern_core:
    - docs/patterns/uip_pattern_gold_standard_v1.md
    - docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
    - docs/patterns/nsip_pattern_gold_standard_v1.md
    - docs/patterns/sarcoidosis_pattern_gold_standard_v1.md
    - docs/patterns/glild_pattern_gold_standard_v1.md

  tier_3_gray_zone_core:
    - docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md
    - docs/reasoning/fibrotic_ild_triage_map_v1.md
    - docs/reasoning/granulomatous_ild_reasoning_map_v1.md
    - docs/reasoning/sarcoidosis_vs_granulomatous_infection_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1.md

  tier_4_superimposed_expansion:
    - docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    - docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
    - docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
```

---

## 6. Test Case Schema

```yaml
test_case_schema:
  case_id: REQUIRED
  case_type:
    allowed:
      - typical_scenario
      - indeterminate_gray_zone_scenario
      - alternative_diagnosis_mimic_dominant_scenario
      - red_flag_urgent_review_scenario

  target_page: REQUIRED
  linked_modules:
    - optional

  input:
    patient_context:
      age: optional
      sex: optional
      known_background:
        - optional
      clinical_time_course: optional
      oxygen_requirement_change: optional
      treatment_or_medication_timeline: optional
      exposure_context: optional
      immune_status: optional
      cancer_history: optional

    imaging_context:
      baseline_pattern: optional
      current_CT_findings:
        - required
      prior_CT_status:
        allowed:
          - unavailable
          - available_not_reviewed
          - reviewed_comparable
          - reviewed_not_comparable
      temporal_change:
        - optional

    labs_or_context:
      infection_data: optional
      serology: optional
      renal_context: optional
      cardiac_context: optional
      pathology_context: optional
      microbiology: optional

  expected_output:
    reasoning_state: REQUIRED
    supports_target_pathway:
      - optional
    weakens_target_pathway:
      - optional
    mimic_support:
      - optional
    red_flags:
      - optional
    cannot_conclude:
      - REQUIRED
    missing_pieces:
      - REQUIRED
    route_to:
      - optional
    final_prompt:
      - REQUIRED
```

---

## 7. Coverage Matrix Template

```yaml
coverage_matrix_template:
  page_id: REQUIRED
  page_path: REQUIRED
  module_family: REQUIRED
  current_case_count: 0
  required_case_count: 4

  required_cases:
    typical_scenario:
      status: missing
      case_id: pending

    indeterminate_gray_zone_scenario:
      status: missing
      case_id: pending

    alternative_diagnosis_mimic_dominant_scenario:
      status: missing
      case_id: pending

    red_flag_urgent_review_scenario:
      status: missing
      case_id: pending

  coverage_status:
    allowed:
      - not_started
      - partial
      - structurally_complete
      - expert_review_pending
      - expert_reviewed

  public_ready_impact:
    - incomplete_test_coverage_blocks_public_ready
```

---

## 8. Initial Coverage Matrix — Tier 1

```yaml
tier_1_initial_coverage:
  temporal_comparison_methodology_v1:
    page_path: docs/reasoning/temporal_comparison_methodology_v1.md
    current_case_count: 1
    required_case_count: 4
    missing_case_types:
      - typical_scenario_expansion
      - indeterminate_gray_zone_scenario
      - alternative_diagnosis_mimic_dominant_scenario
      - red_flag_urgent_review_scenario
    priority: very_high

  superimposed_events_core_blueprint_v1:
    page_path: docs/reasoning/superimposed_events_core_blueprint_v1.md
    current_case_count: 1
    required_case_count: 4
    missing_case_types:
      - typical_scenario_expansion
      - gray_zone_scenario
      - mimic_dominant_scenario
      - red_flag_scenario
    priority: very_high

  acute_exacerbation_vs_infection_vs_edema_v1:
    page_path: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    current_case_count: 1
    required_case_count: 4
    missing_case_types:
      - typical_scenario_expansion
      - indeterminate_gray_zone_scenario
      - infection_dominant_mimic_scenario
      - edema_or_DAH_red_flag_scenario
    priority: very_high

  superimposed_infection_on_ILD_background_v1:
    page_path: docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    current_case_count: 1
    required_case_count: 4
    missing_case_types:
      - typical_infection_scenario
      - infection_vs_AE_gray_zone
      - OP_or_malignancy_mimic_dominant
      - immunosuppressed_red_flag_scenario
    priority: very_high

  vascular_edema_hemorrhage_mimic_panel_v1:
    page_path: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
    current_case_count: 1
    required_case_count: 4
    missing_case_types:
      - typical_edema_scenario
      - PE_or_infarct_gray_zone
      - DAH_mimic_dominant
      - pulmonary_renal_red_flag_scenario
    priority: very_high
```

---

## 9. Initial Coverage Matrix — Pattern Pages

```yaml
pattern_page_initial_coverage:
  uip_pattern_gold_standard_v1:
    page_path: docs/patterns/uip_pattern_gold_standard_v1.md
    current_case_count: needs_audit
    required_case_count: 4
    priority: very_high
    reason:
      - UIP_page_identified_as_parity_gap
      - needs_typical_indeterminate_mimic_and_red_flag_cases

  fibrotic_hp_pattern_gold_standard_v1:
    page_path: docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
    current_case_count: needs_audit
    required_case_count: 4
    priority: high

  nsip_pattern_gold_standard_v1:
    page_path: docs/patterns/nsip_pattern_gold_standard_v1.md
    current_case_count: needs_audit
    required_case_count: 4
    priority: high

  sarcoidosis_pattern_gold_standard_v1:
    page_path: docs/patterns/sarcoidosis_pattern_gold_standard_v1.md
    current_case_count: needs_audit
    required_case_count: 4
    priority: high

  glild_pattern_gold_standard_v1:
    page_path: docs/patterns/glild_pattern_gold_standard_v1.md
    current_case_count: needs_audit
    required_case_count: 4
    priority: high
```

---

## 10. Test Case Safety Boundaries

```yaml
test_case_safety_boundaries:
  platform_must_not:
    - write_test_cases_that_give_final_diagnosis
    - write_test_cases_that_recommend_treatment
    - write_test_cases_that_replace_clinician_judgment
    - use_test_case_output_as_ground_truth_clinical_validation
    - hide_uncertainty
    - omit_missing_data
    - omit_mimics

  platform_must:
    - use_reasoning_state_not_final_diagnosis
    - include_cannot_conclude
    - include_missing_pieces
    - include_why_not_or_mimic_pathways
    - include_review_prompt_when_risk_is_high
    - mark_all_cases_as_educational_blueprint
```

---

## 11. v0.5 Test Case Expansion Plan

```yaml
v0_5_test_case_expansion_plan:
  step_v0_5_0:
    title: Test Case Coverage Matrix
    path: docs/data/schema/test_case_coverage_matrix_v1.md
    status: current_step

  step_v0_5_1:
    title: Temporal Comparison Test Case Pack
    path: docs/test_cases/temporal_comparison_test_case_pack_v1.md
    reason:
      - first_public_candidate_page
      - cross_cutting_reasoning_value
      - already_claim_mapped_in_v0_4

  step_v0_5_2:
    title: Superimposed Events Test Case Pack
    path: docs/test_cases/superimposed_events_test_case_pack_v1.md
    reason:
      - v0_3_core_recently_sealed
      - high_clinical_gray_zone_value

  step_v0_5_3:
    title: UIP Test Case Pack
    path: docs/test_cases/uip_test_case_pack_v1.md
    reason:
      - UIP_identified_as_parity_gap
      - prepares_v0_6_UIP_parity_upgrade
```

---

## 12. Final Test Coverage Rule

```text
A page has not been tested until it has failed safely.

Typical cases show what the page knows.

Gray-zone, mimic, and red-flag cases show whether the page can stay honest.
```