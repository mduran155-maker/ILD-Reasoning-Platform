# Vascular / Edema / Hemorrhage Test Case Pack — v1

## Document Metadata

```yaml
id: test_cases_vascular_edema_hemorrhage_test_case_pack_v1
title: Vascular / Edema / Hemorrhage Test Case Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_pack
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
target_page:
  - docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
linked_modules:
  - docs/reasoning/superimposed_events_core_blueprint_v1.md
  - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
  - docs/reasoning/superimposed_infection_on_ILD_background_v1.md
  - docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
  - docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
  - docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
  - docs/reasoning/temporal_comparison_methodology_v1.md
linked_coverage_matrix:
  - docs/data/schema/test_case_coverage_matrix_v1.md
last_updated: draft
```

---

## 0. Purpose

This test case pack stress-tests the Vascular / Edema / Hemorrhage Mimic Panel.

It verifies that the page can reason through acute or subacute worsening on an ILD background without prematurely labeling new GGO, septal thickening, consolidation, peripheral opacity, or clinical decline as acute exacerbation, infection, drug toxicity, OP, malignancy, or simple progression.

These cases do not validate clinical correctness.

They verify whether the page preserves uncertainty, exposes missing vascular/cardiac/renal/hemorrhagic data, routes mimics safely, and flags urgent-review presentations.

---

## 1. Test Case Coverage Status

```yaml
test_case_coverage_status:
  target_page: vascular_edema_hemorrhage_mimic_panel_v1
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

## 2. Case 1 — Typical Scenario: Edema-like Superimposed Process on Fibrotic ILD

```yaml
case_VASC_001_typical_edema_like_superimposed_process:
  case_id: VASC_001
  case_type: typical_scenario
  target_page: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md

  linked_modules:
    - acute_exacerbation_vs_infection_vs_edema_v1
    - temporal_comparison_methodology_v1
    - superimposed_events_core_blueprint_v1

  input:
    patient_context:
      age: 79
      sex: male
      known_background:
        - fibrotic_ILD
        - UIP_like_pattern
      clinical_time_course: acute_dyspnea_worsening_over_4_days
      oxygen_requirement_change: increased
      fever: absent_or_unknown
      cardiac_context: known_heart_failure
      renal_context: chronic_kidney_disease_possible
      fluid_balance: positive_fluid_balance_possible
      medication_timeline: unknown
      hemoptysis: absent_or_unknown

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 4_months
      prior_CT_findings:
        - basal_honeycombing
        - traction_bronchiectasis
        - no_diffuse_ground_glass_opacity
        - no_pleural_effusions
      current_CT_findings:
        - stable_background_honeycombing
        - stable_traction_bronchiectasis
        - new_dependent_or_perihilar_ground_glass_opacity
        - smooth_interlobular_septal_thickening
        - small_bilateral_pleural_effusions
        - no_tree_in_bud_reported
        - no_cavitation_reported
      temporal_change:
        - stable_structural_fibrosis
        - new_edema_like_airspace_or_interstitial_pattern

    labs_or_context:
      BNP: unavailable
      echocardiography_context: unavailable
      creatinine: unavailable
      infection_data: unavailable
      hemoglobin_trend: unavailable

  expected_output:
    reasoning_state: edema_like_superimposed_process_on_stable_fibrotic_ILD

    supports_edema_pathway:
      - known_heart_failure
      - renal_or_volume_context_possible
      - smooth_interlobular_septal_thickening
      - dependent_or_perihilar_GGO
      - bilateral_pleural_effusions
      - stable_background_fibrosis_on_comparable_CT
      - acute_time_course_too_fast_for_simple_chronic_fibrotic_progression

    competing_reasoning_paths:
      - acute_exacerbation
      - infection
      - drug_toxicity_or_treatment_related_lung_injury
      - hemorrhage_context_dependent
      - mixed_process_possible

    cannot_conclude:
      - pulmonary_edema_confirmed
      - acute_exacerbation_excluded
      - infection_excluded
      - hemorrhage_excluded
      - drug_toxicity_excluded
      - simple_fibrotic_progression

    missing_pieces:
      - BNP_or_echo_context
      - renal_function_and_fluid_balance
      - response_to_volume_management_if_known
      - infection_labs_and_microbiology
      - hemoptysis_and_hemoglobin_trend
      - medication_and_treatment_timeline
      - urgent_review_if_clinically_unstable

    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - Are the new findings better explained by edema / volume overload than by AE, infection, drug toxicity, hemorrhage, or progression?
```

---

## 3. Case 2 — Indeterminate / Gray-zone Scenario: AE vs Edema vs Infection vs Hemorrhage

```yaml
case_VASC_002_gray_zone_AE_edema_infection_hemorrhage_overlap:
  case_id: VASC_002
  case_type: indeterminate_gray_zone_scenario
  target_page: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md

  linked_modules:
    - acute_exacerbation_vs_infection_vs_edema_v1
    - superimposed_infection_on_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 74
      sex: female
      known_background:
        - fibrotic_ILD
        - probable_UIP_pattern
      clinical_time_course: worsening_dyspnea_over_7_days
      oxygen_requirement_change: increased
      fever: low_grade_possible
      cough: present
      cardiac_context: heart_failure_history_uncertain
      renal_context: renal_function_unknown
      hemoptysis: unknown
      anticoagulation: unknown
      medication_timeline: unknown

    imaging_context:
      baseline_pattern: probable_UIP_like_fibrotic_pattern
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - background_reticulation
        - traction_bronchiectasis
        - new_bilateral_ground_glass_opacity
        - mild_smooth_interlobular_septal_thickening
        - patchy_consolidation
        - small_pleural_effusions_possible
        - no_dominant_lobar_consolidation_reported
      temporal_change:
        - new_bilateral_airspace_opacity_possible
        - edema_like_features_possible
        - structural_progression_unknown

    labs_or_context:
      WBC_CRP: unavailable
      microbiology: unavailable
      viral_testing: unavailable
      BNP: unavailable
      creatinine: unavailable
      hemoglobin_trend: unavailable
      urinalysis: unavailable

  expected_output:
    reasoning_state: vascular_edema_hemorrhage_gray_zone_with_AE_infection_overlap

    competing_reasoning_paths:
      - pulmonary_edema_or_volume_overload
      - acute_exacerbation_or_acute_lung_injury
      - infection
      - diffuse_alveolar_hemorrhage
      - drug_toxicity_or_treatment_related_lung_injury
      - mixed_process_possible

    supports_gray_zone:
      - new_bilateral_GGO
      - acute_worsening
      - increased_oxygen_requirement
      - mild_smooth_septal_thickening
      - possible_effusions
      - possible_low_grade_fever
      - prior_CT_not_reviewed
      - cardiac_renal_hemorrhage_and_infection_context_missing

    cannot_conclude:
      - pulmonary_edema
      - acute_exacerbation
      - infection
      - diffuse_alveolar_hemorrhage
      - drug_toxicity
      - simple_fibrotic_progression

    missing_pieces:
      - prior_CT_review
      - BNP_echo_or_heart_failure_context
      - renal_function_and_fluid_balance
      - infection_labs_microbiology_and_viral_testing
      - hemoptysis_detail
      - hemoglobin_trend
      - anticoagulation_and_coagulation_status
      - urinalysis_and_autoimmune_context
      - medication_and_treatment_timeline
      - urgent_or_MDD_review

    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - What cardiac, renal, infectious, hemorrhagic, medication, and temporal evidence is missing before choosing one dominant pathway?
```

---

## 4. Case 3 — Mimic-dominant Scenario: PE / Pulmonary Infarct Mimicking Infection, OP, or Malignancy

```yaml
case_VASC_003_mimic_dominant_PE_infarct:
  case_id: VASC_003
  case_type: alternative_diagnosis_mimic_dominant_scenario
  target_page: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md

  linked_modules:
    - organizing_pneumonia_on_ILD_background_v1
    - superimposed_infection_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 69
      sex: male
      known_background:
        - fibrotic_ILD
        - probable_UIP_pattern
      clinical_time_course: sudden_pleuritic_chest_pain_and_dyspnea_over_1_day
      oxygen_requirement_change: increased
      fever: absent_or_unknown
      PE_risk_context: recent_immobility_or_malignancy_risk_unknown
      cancer_history: unknown
      infection_symptoms: minimal_or_unknown
      medication_timeline: unknown

    imaging_context:
      baseline_pattern: probable_UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 4_months
      prior_CT_findings:
        - stable_basal_reticulation
        - traction_bronchiectasis
        - no_focal_peripheral_opacity
      current_CT_findings:
        - stable_background_fibrosis
        - new_peripheral_pleural_based_wedge_like_opacity
        - small_adjacent_pleural_effusion_possible
        - no_tree_in_bud_reported
        - no_diffuse_new_GGO_reported
        - no_definite_mass_reported
      temporal_change:
        - new_peripheral_focal_opacity
        - stable_structural_fibrosis

    labs_or_context:
      D_dimer_or_CTPA_context: unavailable
      infection_data: unavailable
      microbiology: unavailable
      cancer_context: unavailable
      anticoagulation: unknown

  expected_output:
    reasoning_state: PE_or_pulmonary_infarct_mimic_dominant_on_fibrotic_background

    mimic_support:
      - sudden_pleuritic_chest_pain
      - acute_dyspnea
      - increased_oxygen_requirement
      - peripheral_pleural_based_wedge_like_opacity
      - small_adjacent_pleural_effusion_possible
      - stable_background_fibrosis
      - no_tree_in_bud_reported
      - no_diffuse_fibrotic_progression_signal

    weakens_infection_OP_or_malignancy_default:
      - acute_vascular_time_course_possible
      - wedge_like_pleural_based_morphology
      - fever_absent_or_unknown
      - focal_opacity_new_but_not_yet_persistent
      - prior_CT_confirms_new_focal_event

    cannot_conclude:
      - pulmonary_embolism
      - pulmonary_infarct
      - infection_excluded
      - organizing_pneumonia_excluded
      - malignancy_excluded
      - simple_ILD_progression

    missing_pieces:
      - PE_risk_assessment
      - CTPA_or_vascular_imaging_context_if_available
      - chest_pain_and_acuity_detail
      - oxygen_trend
      - infection_review
      - malignancy_risk_and_persistence_context
      - follow_up_or_resolution_context
      - urgent_review_if_unstable

    route_to:
      - temporal_comparison_methodology_v1
      - superimposed_infection_on_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1

    final_prompt:
      - Does the time course and morphology raise vascular event / infarct above infection, OP, malignancy, or baseline ILD progression?
```

---

## 5. Case 4 — Red-flag / Urgent-review Scenario: DAH / Pulmonary-renal Vasculitis Context

```yaml
case_VASC_004_red_flag_DAH_pulmonary_renal_context:
  case_id: VASC_004
  case_type: red_flag_urgent_review_scenario
  target_page: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md

  linked_modules:
    - acute_exacerbation_vs_infection_vs_edema_v1
    - superimposed_infection_on_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 62
      sex: female
      known_background:
        - CTD_ILD_or_granulomatous_ILD_possible
      clinical_time_course: acute_worsening_over_5_days
      oxygen_requirement_change: markedly_increased
      fever: unknown
      hemoptysis: possible
      renal_context: rising_creatinine_possible
      urinalysis_context: unknown
      anticoagulation: unknown
      coagulopathy: unknown
      medication_timeline: immunosuppression_or_new_drug_unknown

    imaging_context:
      baseline_pattern: fibrotic_or_granulomatous_ILD_background
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - new_diffuse_or_patchy_ground_glass_opacity
        - patchy_consolidation
        - possible_crazy_paving
        - no_dominant_lobar_consolidation_reported
        - no_new_mass_reported
      temporal_change:
        - acute_new_alveolar_opacity_possible

    labs_or_context:
      hemoglobin_trend: unavailable
      urinalysis: unavailable
      creatinine: unavailable
      ANCA_or_autoimmune_context: unavailable
      infection_data: unavailable
      microbiology: unavailable
      WBC_CRP: unavailable

  expected_output:
    reasoning_state: red_flag_DAH_or_pulmonary_renal_mimic_of_AE_infection_or_drug_toxicity

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
      - immunosuppression_or_new_drug_context_unknown

    competing_high_risk_pathways:
      - diffuse_alveolar_hemorrhage
      - pulmonary_renal_vasculitis
      - infection
      - acute_exacerbation
      - drug_toxicity_or_treatment_related_lung_injury
      - edema_or_volume_overload

    cannot_conclude:
      - diffuse_alveolar_hemorrhage
      - vasculitis
      - acute_exacerbation
      - infection
      - drug_toxicity
      - edema_excluded
      - benign_or_baseline_ILD_change

    missing_pieces:
      - hemoptysis_detail
      - hemoglobin_trend
      - urinalysis
      - renal_function_trend
      - ANCA_or_autoimmune_context_if_relevant
      - anticoagulation_or_coagulation_status
      - infection_labs_and_microbiology
      - medication_and_treatment_timeline
      - prior_CT_review
      - urgent_review
      - rheumatology_nephrology_or_MDD_review_if_context_supports

    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - What hemorrhagic, renal, vasculitic, infectious, medication, and temporal evidence is missing before calling this AE, infection, or drug toxicity?
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
  target_page: vascular_edema_hemorrhage_mimic_panel_v1
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
    - pulmonary_edema_CT_source_verification
    - DAH_clinical_imaging_source_verification
    - PE_infarct_CT_source_verification
    - real_case_validation_or_simulation_review
```

---

## 8. Final Test Case Rule

```text
The vascular / edema / hemorrhage panel succeeds only if acute ILD worsening is not reduced to AE or infection.

Edema, PE/infarct, pulmonary hypertension decompensation, DAH, and pulmonary-renal disease must remain visible until context closes them.

The safest output is the one that keeps the dangerous vascular or hemorrhagic mimic alive.
```