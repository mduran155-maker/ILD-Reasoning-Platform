# UIP Test Case Pack — v1

## Document Metadata

```yaml
id: test_cases_uip_test_case_pack_v1
title: UIP Test Case Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_pack
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
target_page:
  - docs/patterns/uip_pattern_gold_standard_v1.md
linked_modules:
  - docs/reasoning/fibrotic_ild_triage_map_v1.md
  - docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md
  - docs/reasoning/temporal_comparison_methodology_v1.md
  - docs/reasoning/superimposed_events_core_blueprint_v1.md
  - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
  - docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
linked_coverage_matrix:
  - docs/data/schema/test_case_coverage_matrix_v1.md
last_updated: draft
```

---

## 0. Purpose

This test case pack stress-tests the UIP Pattern page.

It verifies that the page can reason through:

- typical UIP-like pattern,
- indeterminate UIP / fibrotic ILD gray-zone,
- mimic-dominant fibrotic HP or alternative diagnosis scenario,
- red-flag superimposed event on UIP-like fibrosis.

These test cases do not validate clinical correctness.

They verify whether the page preserves uncertainty, avoids imaging-only diagnosis, exposes missing data, routes mimics, and prevents the UIP label from swallowing new findings.

---

## 1. Test Case Coverage Status

```yaml
test_case_coverage_status:
  target_page: uip_pattern_gold_standard_v1
  required_case_count: 4
  implemented_case_count: 4

  implemented_case_types:
    - typical_scenario
    - indeterminate_gray_zone_scenario
    - alternative_diagnosis_mimic_dominant_scenario
    - red_flag_urgent_review_scenario

  coverage_status: structurally_complete_blueprint
  public_ready: false
  expert_review_required: true
  full_text_review_required: true
```

---

## 2. Case 1 — Typical Scenario: UIP-like Fibrotic Pattern

```yaml
case_UIP_001_typical_UIP_like_pattern:
  case_id: UIP_001
  case_type: typical_scenario
  target_page: docs/patterns/uip_pattern_gold_standard_v1.md

  linked_modules:
    - fibrotic_ild_triage_map_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 74
      sex: male
      known_background:
        - suspected_fibrotic_ILD
      clinical_time_course: chronic_progressive_dyspnea_over_years
      exposure_context: unknown
      CTD_context: unknown
      medication_timeline: unknown
      smoking_history: unknown

    imaging_context:
      baseline_pattern: suspected_UIP_like_fibrotic_pattern
      prior_CT_status: unavailable
      current_CT_findings:
        - basal_predominant_subpleural_reticulation
        - traction_bronchiectasis
        - honeycombing
        - architectural_distortion
        - no_prominent_centrilobular_nodules_reported
        - no_marked_air_trapping_reported
        - no_extensive_consolidation_reported
      temporal_change:
        - cannot_assess_without_prior_CT

    labs_or_context:
      autoimmune_serology: unavailable
      exposure_history: incomplete
      BAL_or_pathology: unavailable
      MDD_context: not_documented

  expected_output:
    reasoning_state: UIP_like_fibrotic_pattern_support_without_final_diagnosis

    supports_target_pathway:
      - basal_subpleural_fibrotic_distribution
      - honeycombing
      - traction_bronchiectasis
      - architectural_distortion
      - chronic_symptom_time_course

    cannot_conclude:
      - IPF
      - definite_UIP_final_diagnosis
      - absence_of_CTD_ILD
      - absence_of_fibrotic_HP
      - absence_of_asbestosis_or_occupational_context
      - progression_status_without_prior_CT

    missing_pieces:
      - exposure_history
      - CTD_clinical_and_serologic_context
      - occupational_history
      - medication_history
      - prior_CT_for_temporal_behavior
      - MDD_review

    route_to:
      - fibrotic_ild_triage_map_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - What clinical, exposure, autoimmune, occupational, and temporal data are missing before moving from UIP-like pattern to disease-level interpretation?
```

---

## 3. Case 2 — Indeterminate / Gray-zone Scenario: Probable UIP vs Fibrotic NSIP / Unclassifiable Fibrotic ILD

```yaml
case_UIP_002_indeterminate_probable_UIP_gray_zone:
  case_id: UIP_002
  case_type: indeterminate_gray_zone_scenario
  target_page: docs/patterns/uip_pattern_gold_standard_v1.md

  linked_modules:
    - fibrotic_ild_triage_map_v1
    - temporal_comparison_methodology_v1
    - superimposed_events_core_blueprint_v1

  input:
    patient_context:
      age: 62
      sex: female
      known_background:
        - fibrotic_ILD_under_evaluation
      clinical_time_course: dyspnea_over_18_months
      CTD_context: arthralgia_and_autoimmune_symptoms_unknown
      exposure_context: unknown
      medication_timeline: unknown

    imaging_context:
      baseline_pattern: indeterminate_or_probable_UIP_like_fibrotic_pattern
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - basal_reticulation
        - traction_bronchiectasis
        - no_definite_honeycombing
        - mild_ground_glass_opacity
        - possible_subpleural_sparing_uncertain
        - no_clear_three_density_pattern_reported
      temporal_change:
        - uncertain_without_prior_CT_review

    labs_or_context:
      autoimmune_serology: unavailable
      exposure_history: incomplete
      BAL_or_pathology: unavailable
      MDD_context: not_documented

  expected_output:
    reasoning_state: indeterminate_UIP_gray_zone_requiring_context

    competing_reasoning_paths:
      - probable_UIP_like_fibrotic_pattern
      - fibrotic_NSIP
      - fibrotic_HP_without_clear_air_trapping_data
      - CTD_ILD
      - unclassifiable_fibrotic_ILD

    supports_target_pathway:
      - basal_fibrotic_abnormality
      - traction_bronchiectasis
      - chronic_time_course

    weakens_confident_UIP_label:
      - no_definite_honeycombing
      - ground_glass_component_present
      - possible_subpleural_sparing_uncertain
      - autoimmune_and_exposure_context_missing
      - prior_CT_not_reviewed

    cannot_conclude:
      - UIP
      - IPF
      - fibrotic_NSIP_excluded
      - fibrotic_HP_excluded
      - CTD_ILD_excluded
      - disease_progression

    missing_pieces:
      - prior_CT_review
      - HRCT_technical_comparability
      - CTD_symptoms_and_serology
      - exposure_history
      - expiratory_imaging_or_air_trapping_assessment
      - MDD_review

    route_to:
      - fibrotic_ild_triage_map_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - Which missing context would move this from indeterminate fibrotic ILD toward UIP, NSIP, HP, CTD-ILD, or unclassifiable disease?
```

---

## 4. Case 3 — Mimic-dominant Scenario: Fibrotic HP Mimicking UIP

```yaml
case_UIP_003_mimic_dominant_fibrotic_HP:
  case_id: UIP_003
  case_type: alternative_diagnosis_mimic_dominant_scenario
  target_page: docs/patterns/uip_pattern_gold_standard_v1.md

  linked_modules:
    - uip_vs_fibrotic_hp_gray_zone_v1
    - fibrotic_hp_pattern_gold_standard_v1
    - fibrotic_ild_triage_map_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 59
      sex: male
      known_background:
        - fibrotic_ILD
      clinical_time_course: progressive_dyspnea_over_2_years
      exposure_context: bird_exposure_or_mold_exposure_possible
      CTD_context: unknown
      smoking_history: unknown

    imaging_context:
      baseline_pattern: fibrotic_ILD_with_UIP_mimic_features
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 14_months
      current_CT_findings:
        - fibrotic_reticulation
        - traction_bronchiectasis
        - patchy_geographic_lobular_attenuation
        - mosaic_attenuation
        - air_trapping_on_expiratory_images
        - centrilobular_ground_glass_nodules_possible
        - honeycombing_absent_or_limited
      temporal_change:
        - fibrotic_abnormality_slightly_increased
        - air_trapping_persistent

    labs_or_context:
      exposure_history: incomplete_but_suspicious
      BAL_lymphocytosis: unavailable
      pathology: unavailable
      MDD_context: not_documented

  expected_output:
    reasoning_state: UIP_mimic_with_fibrotic_HP_support

    mimic_support:
      - exposure_context_possible
      - mosaic_attenuation
      - air_trapping_on_expiratory_images
      - centrilobular_ground_glass_nodules_possible
      - patchy_geographic_distribution
      - honeycombing_absent_or_limited

    weakens_target_pathway:
      - small_airways_or_air_trapping_features
      - exposure_context_not_resolved
      - pattern_not_clean_typical_UIP

    cannot_conclude:
      - fibrotic_HP
      - UIP
      - IPF
      - exposure_causality
      - CTD_ILD_excluded
      - progression_status_as_IPF

    missing_pieces:
      - detailed_exposure_history
      - antigen_avoidance_context_if_any
      - BAL_context_when_relevant
      - pathology_context_if_available
      - CTD_context
      - MDD_review

    route_to:
      - uip_vs_fibrotic_hp_gray_zone_v1
      - fibrotic_hp_pattern_gold_standard_v1
      - fibrotic_ild_triage_map_v1

    final_prompt:
      - Are the small-airways and exposure signals strong enough to keep fibrotic HP above a simple UIP/IPF interpretation?
```

---

## 5. Case 4 — Red-flag / Urgent-review Scenario: New Bilateral GGO on UIP-like Background

```yaml
case_UIP_004_red_flag_new_GGO_on_UIP_background:
  case_id: UIP_004
  case_type: red_flag_urgent_review_scenario
  target_page: docs/patterns/uip_pattern_gold_standard_v1.md

  linked_modules:
    - temporal_comparison_methodology_v1
    - superimposed_events_core_blueprint_v1
    - acute_exacerbation_vs_infection_vs_edema_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - drug_toxicity_treatment_related_lung_injury_v1

  input:
    patient_context:
      age: 77
      sex: male
      known_background:
        - UIP_like_fibrotic_ILD
      clinical_time_course: acute_worsening_over_9_days
      oxygen_requirement_change: increased
      fever: unknown
      medication_timeline: recent_new_drug_unknown
      cardiac_context: unknown
      renal_context: unknown
      hemoptysis: unknown

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 5_months
      prior_CT_findings:
        - basal_honeycombing
        - traction_bronchiectasis
        - reticulation
        - no_diffuse_GGO
      current_CT_findings:
        - stable_background_honeycombing
        - stable_or_mildly_increased_traction_bronchiectasis
        - new_bilateral_ground_glass_opacity
        - patchy_consolidation
        - no_new_mass_reported
      temporal_change:
        - new_bilateral_airspace_opacity
        - background_structural_fibrosis_not_enough_to_explain_acute_change

    labs_or_context:
      infection_data: unavailable
      viral_testing: unavailable
      BNP: unavailable
      creatinine: unavailable
      hemoglobin_trend: unavailable
      microbiology: unavailable

  expected_output:
    reasoning_state: red_flag_new_airspace_opacity_on_UIP_like_background

    red_flags:
      - acute_clinical_worsening
      - increased_oxygen_requirement
      - new_bilateral_GGO
      - patchy_consolidation
      - baseline_UIP_label_cannot_explain_new_airspace_opacity_by_default
      - infection_edema_drug_toxicity_hemorrhage_and_AE_context_missing

    competing_high_risk_pathways:
      - acute_exacerbation_or_acute_lung_injury
      - infection
      - pulmonary_edema_or_volume_overload
      - drug_or_treatment_related_lung_injury
      - diffuse_alveolar_hemorrhage
      - aspiration_context_dependent

    cannot_conclude:
      - acute_exacerbation
      - infection_excluded
      - edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded
      - simple_UIP_progression
      - treatment_response_or_failure

    missing_pieces:
      - infection_labs_and_microbiology
      - viral_testing
      - cardiac_volume_status
      - renal_function
      - medication_and_treatment_timeline
      - hemoptysis_and_hemoglobin_trend
      - oxygen_requirement_trend_detail
      - urgent_or_MDD_review_if_clinically_unstable

    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_events_core_blueprint_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - drug_toxicity_treatment_related_lung_injury_v1

    final_prompt:
      - What superimposed process must be reviewed before calling new bilateral GGO on UIP-like fibrosis progression or acute exacerbation?
```

---

## 6. Case Pack Safety Review

```yaml
case_pack_safety_review:
  no_final_diagnosis_given: true
  no_treatment_recommendation_given: true
  no_follow_up_interval_recommended: true
  uncertainty_preserved: true
  missing_data_visible: true
  mimics_visible: true
  red_flags_visible: true
  urgent_or_MDD_review_prompt_present_when_needed: true
  public_ready: false
  expert_review_required: true
```

---

## 7. Coverage Completion Statement

```yaml
coverage_completion_statement:
  target_page: uip_pattern_gold_standard_v1
  required_cases: 4
  implemented_cases: 4
  coverage_status: structurally_complete_blueprint
  public_ready: false

  completed_case_types:
    - typical_scenario
    - indeterminate_gray_zone_scenario
    - alternative_diagnosis_mimic_dominant_scenario
    - red_flag_urgent_review_scenario

  remaining_requirements:
    - expert_review
    - source_full_text_review
    - UIP_parity_upgrade
    - real_case_validation_or_simulation_review
    - public_language_gate_review
```

---

## 8. Final Test Case Rule

```text
UIP testing succeeds only if the page can resist two opposite errors:

calling every basal fibrosis UIP/IPF,

and letting a UIP-like baseline swallow new disease.

The safe output is not a faster label.

The safe output is a better next question.
```