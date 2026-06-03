# Acute Exacerbation vs Infection vs Edema Test Case Pack — v1

## Document Metadata

```yaml
id: test_cases_acute_exacerbation_infection_edema_test_case_pack_v1
title: Acute Exacerbation vs Infection vs Edema Test Case Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_pack
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
target_page:
  - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
linked_modules:
  - docs/reasoning/superimposed_events_core_blueprint_v1.md
  - docs/reasoning/superimposed_infection_on_ILD_background_v1.md
  - docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
  - docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
  - docs/reasoning/temporal_comparison_methodology_v1.md
linked_coverage_matrix:
  - docs/data/schema/test_case_coverage_matrix_v1.md
last_updated: draft
```

---

## 0. Purpose

This test case pack stress-tests the Acute Exacerbation vs Infection vs Edema reasoning map.

It verifies that the page can reason through acute or subacute worsening on a fibrotic ILD background without prematurely labeling new bilateral GGO or consolidation as acute exacerbation, infection, or edema.

These cases do not validate clinical correctness.

They test whether the page preserves uncertainty, exposes missing data, separates competing acute pathways, and routes high-risk mimics safely.

---

## 1. Test Case Coverage Status

```yaml
test_case_coverage_status:
  target_page: acute_exacerbation_vs_infection_vs_edema_v1
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

## 2. Case 1 — Typical Scenario: Acute Exacerbation-like Pattern, Alternatives Still Visible

```yaml
case_AEIE_001_typical_AE_like_but_not_final:
  case_id: AEIE_001
  case_type: typical_scenario
  target_page: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md

  linked_modules:
    - superimposed_events_core_blueprint_v1
    - temporal_comparison_methodology_v1
    - superimposed_infection_on_ILD_background_v1
    - vascular_edema_hemorrhage_mimic_panel_v1

  input:
    patient_context:
      age: 73
      sex: male
      known_background:
        - fibrotic_ILD
        - UIP_like_pattern
      clinical_time_course: acute_worsening_over_12_days
      oxygen_requirement_change: increased
      fever: absent_or_unknown
      cough: present
      medication_timeline: unknown
      cardiac_context: no_known_heart_failure_but_not_fully_reviewed
      renal_context: unknown
      hemoptysis: absent_or_unknown

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 5_months
      prior_CT_findings:
        - basal_honeycombing
        - traction_bronchiectasis
        - no_diffuse_ground_glass_opacity
      current_CT_findings:
        - background_honeycombing
        - traction_bronchiectasis
        - new_bilateral_ground_glass_opacity
        - patchy_bilateral_consolidation
        - no_dominant_focal_lobar_consolidation
        - no_pleural_effusions_reported
        - no_tree_in_bud_reported
      temporal_change:
        - new_bilateral_airspace_opacity_on_fibrotic_background

    labs_or_context:
      WBC_CRP: unavailable
      microbiology: unavailable
      viral_testing: unavailable
      BNP: unavailable
      creatinine: unavailable
      hemoglobin_trend: unavailable

  expected_output:
    reasoning_state: acute_exacerbation_like_pattern_with_required_mimic_review

    supports_AE_like_pathway:
      - fibrotic_ILD_background
      - acute_subacute_respiratory_worsening
      - increased_oxygen_requirement
      - new_bilateral_GGO_or_consolidation
      - no_dominant_focal_lobar_or_airway_centered_pattern_reported

    competing_reasoning_paths:
      - infection
      - edema_or_volume_overload
      - drug_toxicity_or_treatment_related_lung_injury
      - diffuse_alveolar_hemorrhage
      - PE_or_other_acute_process

    cannot_conclude:
      - acute_exacerbation
      - infection_excluded
      - edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded
      - PE_excluded
      - simple_fibrotic_progression

    missing_pieces:
      - infection_labs_and_microbiology
      - viral_testing
      - cardiac_and_volume_status
      - renal_function
      - medication_and_treatment_timeline
      - hemoptysis_and_hemoglobin_trend
      - oxygen_requirement_trend_detail
      - urgent_or_MDD_review_if_clinically_unstable

    route_to:
      - superimposed_infection_on_ILD_background_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - What alternative acute causes must be reviewed before calling this acute exacerbation?
```

---

## 3. Case 2 — Indeterminate / Gray-zone Scenario: AE vs Infection vs Edema All Plausible

```yaml
case_AEIE_002_gray_zone_AE_infection_edema_overlap:
  case_id: AEIE_002
  case_type: indeterminate_gray_zone_scenario
  target_page: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md

  linked_modules:
    - superimposed_infection_on_ILD_background_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 78
      sex: female
      known_background:
        - fibrotic_ILD
        - probable_UIP_pattern
      clinical_time_course: worsening_dyspnea_over_8_days
      oxygen_requirement_change: increased
      fever: low_grade_possible
      cough: present
      cardiac_context: heart_failure_history_possible
      renal_context: chronic_kidney_disease_possible
      medication_timeline: unknown
      hemoptysis: unknown

    imaging_context:
      baseline_pattern: probable_UIP_like_fibrotic_pattern
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - background_reticulation
        - traction_bronchiectasis
        - new_bilateral_ground_glass_opacity
        - mild_smooth_interlobular_septal_thickening
        - small_bilateral_pleural_effusions
        - patchy_consolidation
      temporal_change:
        - new_bilateral_GGO_possible
        - edema_like_features_possible
        - structural_progression_unknown

    labs_or_context:
      WBC_CRP: unavailable
      microbiology: unavailable
      viral_testing: unavailable
      BNP: unavailable
      creatinine: unavailable
      fluid_balance: unavailable

  expected_output:
    reasoning_state: AE_infection_edema_gray_zone

    competing_reasoning_paths:
      - acute_exacerbation
      - infection
      - pulmonary_edema_or_volume_overload
      - drug_toxicity
      - hemorrhage
      - mixed_process_possible

    supports_gray_zone:
      - new_bilateral_GGO
      - acute_worsening
      - possible_low_grade_fever
      - smooth_septal_thickening
      - small_pleural_effusions
      - cardiac_and_renal_context_incomplete
      - prior_CT_not_reviewed

    cannot_conclude:
      - acute_exacerbation
      - infection
      - pulmonary_edema
      - infection_excluded
      - edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded

    missing_pieces:
      - prior_CT_review
      - infection_labs_microbiology_and_viral_testing
      - BNP_echo_or_heart_failure_context
      - renal_function_and_fluid_balance
      - medication_and_treatment_timeline
      - hemoptysis_or_anemia_context
      - urgent_or_MDD_review

    route_to:
      - superimposed_infection_on_ILD_background_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - drug_toxicity_treatment_related_lung_injury_v1

    final_prompt:
      - What evidence is missing before assigning the dominant pathway among AE, infection, edema, drug toxicity, and hemorrhage?
```

---

## 4. Case 3 — Mimic-dominant Scenario: Edema Dominates Over Acute Exacerbation

```yaml
case_AEIE_003_mimic_dominant_edema:
  case_id: AEIE_003
  case_type: alternative_diagnosis_mimic_dominant_scenario
  target_page: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md

  linked_modules:
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1
    - superimposed_events_core_blueprint_v1

  input:
    patient_context:
      age: 81
      sex: male
      known_background:
        - fibrotic_ILD
        - UIP_like_pattern
      clinical_time_course: acute_dyspnea_over_3_days
      oxygen_requirement_change: increased
      fever: absent
      cough: chronic_baseline
      cardiac_context: known_heart_failure
      renal_context: acute_on_chronic_renal_failure_possible
      fluid_balance: positive_fluid_balance_possible

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 3_months
      prior_CT_findings:
        - stable_basal_honeycombing
        - stable_traction_bronchiectasis
        - no_diffuse_GGO
        - no_pleural_effusion
      current_CT_findings:
        - stable_background_honeycombing
        - stable_traction_bronchiectasis
        - new_dependent_and_perihilar_ground_glass_opacity
        - smooth_interlobular_septal_thickening
        - bilateral_pleural_effusions
        - no_tree_in_bud
        - no_cavitation
      temporal_change:
        - stable_structural_fibrosis
        - new_edema_like_airspace_pattern

    labs_or_context:
      BNP: elevated_possible_but_value_unavailable
      creatinine: unavailable
      infection_data: no_fever_but_microbiology_unavailable
      hemoglobin_trend: unavailable

  expected_output:
    reasoning_state: edema_dominant_mimic_of_AE_on_fibrotic_background

    mimic_support:
      - known_heart_failure
      - renal_failure_or_volume_context_possible
      - dependent_or_perihilar_GGO
      - smooth_interlobular_septal_thickening
      - bilateral_pleural_effusions
      - stable_structural_fibrosis_on_comparable_CT
      - acute_time_course_too_fast_for_simple_fibrotic_progression

    weakens_AE_primary_pathway:
      - edema_like_distribution
      - effusions
      - volume_context
      - no_clear_exclusion_of_hydrostatic_cause

    cannot_conclude:
      - pulmonary_edema_confirmed
      - acute_exacerbation_excluded
      - infection_excluded
      - hemorrhage_excluded
      - drug_toxicity_excluded

    missing_pieces:
      - BNP_or_echo_context
      - renal_function_and_fluid_balance
      - response_to_volume_management_if_known
      - infection_review
      - hemoptysis_or_anemia_context
      - medication_timeline
      - urgent_review_if_clinically_unstable

    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - Are the new findings better explained by edema / volume overload than by acute exacerbation, and what data are still missing?
```

---

## 5. Case 4 — Red-flag / Urgent-review Scenario: DAH or Pulmonary-renal Context Hidden as AE/Infection

```yaml
case_AEIE_004_red_flag_DAH_pulmonary_renal_context:
  case_id: AEIE_004
  case_type: red_flag_urgent_review_scenario
  target_page: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md

  linked_modules:
    - vascular_edema_hemorrhage_mimic_panel_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - superimposed_infection_on_ILD_background_v1
    - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1

  input:
    patient_context:
      age: 64
      sex: female
      known_background:
        - CTD_ILD_or_granulomatous_ILD_possible
      clinical_time_course: acute_worsening_over_5_days
      oxygen_requirement_change: markedly_increased
      fever: unknown
      hemoptysis: possible
      renal_context: rising_creatinine_possible
      anticoagulation: unknown
      medication_timeline: immunosuppression_or_new_drug_unknown

    imaging_context:
      baseline_pattern: fibrotic_or_granulomatous_ILD_background
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - new_diffuse_or_patchy_ground_glass_opacity
        - patchy_consolidation
        - possible_crazy_paving
        - no_dominant_lobar_consolidation_reported
        - no_mass_reported
      temporal_change:
        - acute_new_alveolar_opacity_possible

    labs_or_context:
      hemoglobin_trend: unavailable
      urinalysis: unavailable
      creatinine: unavailable
      ANCA_or_autoimmune_context: unavailable
      microbiology: unavailable
      WBC_CRP: unavailable

  expected_output:
    reasoning_state: red_flag_acute_GGO_with_DAH_pulmonary_renal_mimic_visible

    red_flags:
      - acute_worsening
      - markedly_increased_oxygen_requirement
      - possible_hemoptysis
      - diffuse_or_patchy_GGO
      - possible_crazy_paving
      - renal_context_possible
      - hemoglobin_trend_missing
      - urinalysis_missing
      - anticoagulation_status_unknown

    competing_high_risk_pathways:
      - diffuse_alveolar_hemorrhage
      - vasculitis_or_pulmonary_renal_syndrome
      - infection
      - acute_exacerbation
      - drug_toxicity_or_treatment_related_lung_injury
      - edema

    cannot_conclude:
      - acute_exacerbation
      - infection
      - diffuse_alveolar_hemorrhage
      - vasculitis
      - edema_excluded
      - drug_toxicity_excluded

    missing_pieces:
      - hemoptysis_detail
      - hemoglobin_trend
      - urinalysis
      - renal_function_trend
      - ANCA_or_autoimmune_context_if_relevant
      - anticoagulation_or_coagulation_status
      - infection_review
      - medication_and_treatment_timeline
      - urgent_review
      - rheumatology_nephrology_or_MDD_review_if_context_supports

    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - superimposed_infection_on_ILD_background_v1

    final_prompt:
      - What hemorrhagic, renal, vasculitic, infectious, and treatment-related evidence is missing before calling this AE or infection?
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
  urgent_or_specialist_review_prompt_present_when_needed: true
  public_ready: false
  expert_review_required: true
```

---

## 7. Coverage Completion Statement

```yaml
coverage_completion_statement:
  target_page: acute_exacerbation_vs_infection_vs_edema_v1
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
    - AE_source_verification
    - vascular_DAH_PE_source_verification
    - real_case_validation_or_simulation_review
```

---

## 8. Final Test Case Rule

```text
The AE vs infection vs edema page succeeds only if it refuses premature closure.

New bilateral GGO is not the answer.

It is the beginning of the safety review.
```