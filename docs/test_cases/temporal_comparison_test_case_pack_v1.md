# Temporal Comparison Test Case Pack — v1

## Document Metadata

```yaml
id: test_cases_temporal_comparison_test_case_pack_v1
title: Temporal Comparison Test Case Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_pack
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
target_page:
  - docs/reasoning/temporal_comparison_methodology_v1.md
linked_claim_map:
  - docs/evidence/temporal_comparison_claim_map_v1.md
linked_coverage_matrix:
  - docs/data/schema/test_case_coverage_matrix_v1.md
last_updated: draft
```

---

## 0. Purpose

This test case pack stress-tests the Temporal Comparison Methodology page.

It verifies that the page can reason through:

- typical temporal comparison,
- indeterminate / gray-zone change,
- mimic-dominant change,
- red-flag / urgent-review change.

These test cases do not validate clinical correctness.

They verify whether the page preserves uncertainty, separates structural fibrosis from reversible opacity, requests prior CT and technical context, and routes superimposed events safely.

---

## 1. Test Case Coverage Status

```yaml
test_case_coverage_status:
  target_page: temporal_comparison_methodology_v1
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

## 2. Case 1 — Typical Scenario: Structural Fibrotic Progression with Separate New Airspace Opacity

```yaml
case_TEMP_001_typical_structural_progression_plus_airspace_opacity:
  case_id: TEMP_001
  case_type: typical_scenario
  target_page: docs/reasoning/temporal_comparison_methodology_v1.md

  linked_modules:
    - fibrotic_ild_triage_map_v1
    - superimposed_events_core_blueprint_v1
    - acute_exacerbation_vs_infection_vs_edema_v1

  input:
    patient_context:
      age: 69
      sex: female
      known_background:
        - fibrotic_ILD
        - probable_UIP_pattern
      clinical_time_course: dyspnea_worsening_over_12_months_with_recent_2_week_acceleration
      oxygen_requirement_change: mildly_increased
      treatment_or_medication_timeline: unknown
      exposure_context: unknown

    imaging_context:
      baseline_pattern: probable_UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 12_months
      prior_CT_findings:
        - basal_subpleural_reticulation
        - traction_bronchiectasis
        - no_honeycombing
        - minimal_ground_glass_opacity
      current_CT_findings:
        - increased_reticulation
        - increased_traction_bronchiectasis
        - early_honeycombing_now_visible
        - new_patchy_ground_glass_opacity
      temporal_change:
        - increased_structural_fibrosis
        - new_airspace_opacity

    labs_or_context:
      infection_data: unavailable
      cardiac_context: unavailable
      renal_context: unavailable
      medication_timeline: unavailable

  expected_output:
    reasoning_state: mixed_structural_fibrotic_progression_plus_possible_superimposed_event

    supports_target_pathway:
      - comparable_prior_CT_available
      - increased_reticulation
      - increased_traction_bronchiectasis
      - new_or_increased_honeycombing
      - change_interval_supports_structural_progression_assessment

    weakens_simple_progression_only:
      - new_patchy_ground_glass_opacity
      - recent_2_week_symptom_acceleration
      - infection_edema_drug_toxicity_and_hemorrhage_context_unavailable

    cannot_conclude:
      - pure_fibrotic_progression_only
      - acute_exacerbation
      - infection_excluded
      - edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded
      - treatment_response_or_failure

    missing_pieces:
      - infection_review
      - medication_and_treatment_timeline
      - cardiac_and_volume_status
      - hemoptysis_or_anemia_context
      - oxygen_requirement_trend_detail
      - MDD_review_if_management_depends_on_interpretation

    route_to:
      - fibrotic_ild_triage_map_v1
      - superimposed_events_core_blueprint_v1
      - acute_exacerbation_vs_infection_vs_edema_v1

    final_prompt:
      - What evidence separates true structural fibrotic progression from a new superimposed airspace process?
```

---

## 3. Case 2 — Indeterminate / Gray-zone Scenario: Apparent Progression with Limited Technical Comparability

```yaml
case_TEMP_002_indeterminate_technical_comparability_limited:
  case_id: TEMP_002
  case_type: indeterminate_gray_zone_scenario
  target_page: docs/reasoning/temporal_comparison_methodology_v1.md

  linked_modules:
    - superimposed_events_core_blueprint_v1
    - fibrotic_ild_triage_map_v1

  input:
    patient_context:
      age: 58
      sex: male
      known_background:
        - fibrotic_ILD_unclassifiable
      clinical_time_course: slowly_worsening_dyspnea_over_months
      oxygen_requirement_change: unknown
      treatment_or_medication_timeline: unknown

    imaging_context:
      baseline_pattern: unclassifiable_fibrotic_ILD
      prior_CT_status: reviewed_not_comparable
      prior_CT_interval: 18_months
      technical_comparability:
        slice_thickness: prior_5mm_current_1mm
        reconstruction_kernel: different
        inspiration: current_poor_inspiration
        motion_artifact: mild_current_motion
        contrast_status: prior_noncontrast_current_contrast
      prior_CT_findings:
        - lower_lung_reticulation
        - mild_traction_bronchiectasis
      current_CT_findings:
        - more_conspicuous_reticulation
        - apparent_increased_ground_glass_opacity
        - dependent_opacity
        - traction_bronchiectasis_difficult_to_compare
      temporal_change:
        - apparent_increase_uncertain
        - technical_uncertainty_present

    labs_or_context:
      infection_data: unavailable
      cardiac_context: unknown
      exposure_context: unknown

  expected_output:
    reasoning_state: technically_limited_temporal_comparison_gray_zone

    supports_target_pathway:
      - prior_CT_exists
      - apparent_interval_change_present
      - symptoms_reported_over_months

    weakens_confident_progression_claim:
      - CT_protocols_not_comparable
      - poor_current_inspiration
      - different_slice_thickness
      - different_reconstruction_kernel
      - contrast_status_difference
      - apparent_GGO_may_be_technical_or_dependent

    cannot_conclude:
      - definite_fibrotic_progression
      - definite_stability
      - definite_regression
      - new_superimposed_event
      - technical_artifact_only

    missing_pieces:
      - radiology_review_of_technical_comparability
      - comparable_follow_up_or_prior_HRCT
      - inspiratory_quality_assessment
      - oxygen_requirement_trend
      - clinical_time_course_detail
      - MDD_review_if_diagnostic_or_management_decision_depends_on_progression

    route_to:
      - temporal_comparison_methodology_v1
      - fibrotic_ild_triage_map_v1

    final_prompt:
      - Is the apparent interval change biological, technical, or still uncertain?
```

---

## 4. Case 3 — Alternative Diagnosis / Mimic-dominant Scenario: Apparent Progression Actually Edema-dominant

```yaml
case_TEMP_003_mimic_dominant_edema_not_progression:
  case_id: TEMP_003
  case_type: alternative_diagnosis_mimic_dominant_scenario
  target_page: docs/reasoning/temporal_comparison_methodology_v1.md

  linked_modules:
    - acute_exacerbation_vs_infection_vs_edema_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - superimposed_events_core_blueprint_v1

  input:
    patient_context:
      age: 75
      sex: male
      known_background:
        - fibrotic_ILD
        - UIP_like_pattern
      clinical_time_course: acute_dyspnea_worsening_over_4_days
      oxygen_requirement_change: increased
      treatment_or_medication_timeline: no_new_drug_reported
      cardiac_context: known_heart_failure
      renal_context: chronic_kidney_disease

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 6_months
      prior_CT_findings:
        - stable_basal_honeycombing
        - stable_traction_bronchiectasis
        - no_significant_ground_glass_opacity
        - no_pleural_effusion
      current_CT_findings:
        - stable_honeycombing
        - stable_traction_bronchiectasis
        - new_bilateral_ground_glass_opacity
        - smooth_interlobular_septal_thickening
        - small_bilateral_pleural_effusions
        - dependent_predominance
      temporal_change:
        - stable_structural_fibrosis
        - new_reversible_airspace_or_hydrostatic_pattern_possible

    labs_or_context:
      infection_data: fever_unknown_microbiology_unavailable
      cardiac_context: known_heart_failure_BNP_unavailable
      renal_context: creatinine_unavailable
      hemoptysis: unknown

  expected_output:
    reasoning_state: stable_fibrosis_with_edema_dominant_superimposed_mimic

    mimic_support:
      - stable_honeycombing_and_traction_bronchiectasis
      - new_smooth_interlobular_septal_thickening
      - new_small_bilateral_pleural_effusions
      - known_heart_failure
      - renal_context_present
      - acute_time_course_too_fast_for_simple_chronic_fibrotic_progression

    weakens_target_pathway:
      - no_clear_structural_fibrosis_increase
      - new_GGO_has_edema_features
      - dependent_distribution
      - pleural_effusions

    cannot_conclude:
      - pulmonary_edema_confirmed
      - infection_excluded
      - acute_exacerbation_excluded
      - hemorrhage_excluded
      - drug_toxicity_excluded
      - simple_fibrotic_progression

    missing_pieces:
      - BNP_or_echo_context
      - renal_function_and_fluid_balance
      - response_to_volume_management_if_known
      - infection_review
      - hemoptysis_or_anemia_context
      - medication_timeline_confirmation
      - urgent_review_if_clinically_unstable

    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - acute_exacerbation_vs_infection_vs_edema_v1

    final_prompt:
      - Is the new CT change structural progression, or a hydrostatic / edema-like superimposed process on stable fibrosis?
```

---

## 5. Case 4 — Red-flag / Urgent-review Scenario: New Persistent Focal Opacity Hidden by Fibrosis

```yaml
case_TEMP_004_red_flag_persistent_focal_opacity:
  case_id: TEMP_004
  case_type: red_flag_urgent_review_scenario
  target_page: docs/reasoning/temporal_comparison_methodology_v1.md

  linked_modules:
    - malignancy_on_fibrotic_ILD_background_v1
    - superimposed_infection_on_ILD_background_v1
    - organizing_pneumonia_on_ILD_background_v1

  input:
    patient_context:
      age: 72
      sex: male
      known_background:
        - fibrotic_ILD
        - UIP_like_pattern
      clinical_time_course: chronic_dyspnea_with_new_weight_loss_unknown
      oxygen_requirement_change: unknown
      cancer_history: unknown
      smoking_history: unknown
      infection_symptoms: unknown

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 9_months
      prior_CT_findings:
        - basal_subpleural_honeycombing
        - traction_bronchiectasis
        - no_discrete_mass
      current_CT_findings:
        - stable_background_honeycombing
        - new_left_lower_lobe_mass_like_focal_consolidation
        - possible_irregular_margin
        - no_diffuse_new_GGO
        - lymphadenopathy_status_unclear
      temporal_change:
        - stable_baseline_fibrosis
        - new_persistent_or_mass_like_focal_abnormality_possible

    labs_or_context:
      infection_data: unavailable
      PET_CT: unavailable
      tissue: unavailable
      prior_intermediate_follow_up: unavailable

  expected_output:
    reasoning_state: red_flag_new_focal_abnormality_on_fibrotic_background

    red_flags:
      - new_focal_mass_like_opacity
      - lesion_not_present_on_prior_comparable_CT
      - background_fibrosis_can_obscure_focal_malignancy
      - persistent_or_mass_like_character_requires_reassessment
      - cancer_history_and_smoking_context_unknown

    weakens_benign_baseline_label:
      - stable_baseline_fibrosis
      - focal_change_is_new
      - not_explained_by_diffuse_fibrotic_progression
      - no_prior_evidence_of_same_lesion

    cannot_conclude:
      - malignancy
      - infection_excluded
      - organizing_pneumonia_excluded
      - infarct_excluded
      - scar_or_fibrosis_only
      - need_for_sampling_or_followup

    missing_pieces:
      - lesion_size_and_density_characterization
      - cancer_and_smoking_risk_context
      - infection_review
      - lymphadenopathy_assessment
      - PET_CT_context_if_relevant
      - follow_up_or_persistence_context
      - tissue_sampling_target_discussion_if_needed
      - oncology_or_MDD_review

    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1

    final_prompt:
      - What evidence is missing before calling this scar, infection, OP, malignancy, or another focal superimposed process?
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
  MDD_or_specialist_review_prompt_present_when_needed: true
  public_ready: false
  expert_review_required: true
```

---

## 7. Coverage Completion Statement

```yaml
coverage_completion_statement:
  target_page: temporal_comparison_methodology_v1
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
    - real_case_validation_or_simulation_review
    - public_language_gate_review
```

---

## 8. Final Test Case Rule

```text
Temporal comparison is not safe because it can identify change.

It becomes safer when it can say:
the change is structural,
the change is reversible,
the change is technical,
or the change is still unknown.
```