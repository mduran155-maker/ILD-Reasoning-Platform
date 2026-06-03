# Superimposed Infection Test Case Pack — v1

## Document Metadata

```yaml
id: test_cases_superimposed_infection_test_case_pack_v1
title: Superimposed Infection Test Case Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_pack
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
target_page:
  - docs/reasoning/superimposed_infection_on_ILD_background_v1.md
linked_modules:
  - docs/reasoning/superimposed_events_core_blueprint_v1.md
  - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
  - docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
  - docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
  - docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
  - docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
  - docs/reasoning/temporal_comparison_methodology_v1.md
linked_coverage_matrix:
  - docs/data/schema/test_case_coverage_matrix_v1.md
last_updated: draft
```

---

## 0. Purpose

This test case pack stress-tests the Superimposed Infection on ILD Background reasoning map.

It verifies that the page can reason through suspected infection on a background of known or suspected ILD without prematurely labeling every new opacity as infection, progression, OP, acute exacerbation, or malignancy.

These test cases do not validate clinical correctness.

They verify whether the page preserves uncertainty, exposes missing microbiologic and clinical data, routes mimics safely, and flags high-risk immunosuppressed or cavitary presentations.

---

## 1. Test Case Coverage Status

```yaml
test_case_coverage_status:
  target_page: superimposed_infection_on_ILD_background_v1
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

## 2. Case 1 — Typical Scenario: Airway-centered Infection on Fibrotic ILD Background

```yaml
case_INF_001_typical_airway_centered_infection:
  case_id: INF_001
  case_type: typical_scenario
  target_page: docs/reasoning/superimposed_infection_on_ILD_background_v1.md

  linked_modules:
    - superimposed_events_core_blueprint_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 68
      sex: male
      known_background:
        - fibrotic_ILD
        - probable_UIP_pattern
      clinical_time_course: cough_and_fever_over_6_days
      oxygen_requirement_change: mildly_increased
      fever: present
      sputum: present
      immune_status: not_known_to_be_immunosuppressed
      aspiration_risk: unknown
      medication_timeline: unknown

    imaging_context:
      baseline_pattern: probable_UIP_like_fibrotic_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 4_months
      prior_CT_findings:
        - basal_reticulation
        - traction_bronchiectasis
        - no_tree_in_bud
        - no_focal_consolidation
      current_CT_findings:
        - background_fibrotic_abnormality
        - new_airway_centered_nodules
        - tree_in_bud_opacity
        - focal_right_lower_lobe_consolidation
        - mild_surrounding_ground_glass_opacity
        - no_new_mass_reported
      temporal_change:
        - new_airway_centered_and_focal_airspace_opacity

    labs_or_context:
      WBC_CRP: elevated_possible_but_values_unavailable
      microbiology: unavailable
      viral_testing: unavailable
      blood_cultures: unavailable

  expected_output:
    reasoning_state: infection_supported_but_not_final_on_ILD_background

    supports_infection_pathway:
      - fever
      - sputum
      - new_tree_in_bud_opacity
      - airway_centered_nodules
      - focal_consolidation
      - acute_time_course
      - prior_CT_confirms_new_airway_centered_change

    competing_reasoning_paths:
      - aspiration
      - organizing_pneumonia_if_persistent_or_migratory
      - malignancy_if_focal_opacity_persists_or_grows
      - acute_exacerbation_if_diffuse_bilateral_GGO_develops
      - edema_or_hemorrhage_context_dependent

    cannot_conclude:
      - specific_infectious_organism
      - infection_confirmed
      - aspiration_excluded
      - OP_excluded
      - malignancy_excluded_if_persistent
      - simple_ILD_progression

    missing_pieces:
      - microbiology
      - viral_testing
      - WBC_CRP_values
      - aspiration_risk
      - immune_status
      - response_or_persistence_context
      - MDD_or_clinical_review_if_course_conflicts

    route_to:
      - superimposed_events_core_blueprint_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - What microbiologic, aspiration, temporal, and persistence evidence is missing before calling this infection rather than another superimposed process?
```

---

## 3. Case 2 — Indeterminate / Gray-zone Scenario: Infection vs AE vs Drug Toxicity

```yaml
case_INF_002_gray_zone_infection_AE_drug_overlap:
  case_id: INF_002
  case_type: indeterminate_gray_zone_scenario
  target_page: docs/reasoning/superimposed_infection_on_ILD_background_v1.md

  linked_modules:
    - acute_exacerbation_vs_infection_vs_edema_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 65
      sex: female
      known_background:
        - CTD_ILD
        - fibrotic_NSIP_like_pattern
      clinical_time_course: worsening_dyspnea_and_cough_over_12_days
      oxygen_requirement_change: increased
      fever: low_grade_or_unknown
      immune_status: immunosuppression_possible
      treatment_or_medication_timeline: new_biologic_started_6_weeks_ago
      cardiac_context: unknown
      hemoptysis: unknown

    imaging_context:
      baseline_pattern: fibrotic_NSIP_like_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 7_months
      prior_CT_findings:
        - lower_lung_ground_glass_opacity
        - mild_reticulation
        - traction_bronchiectasis
      current_CT_findings:
        - increased_bilateral_ground_glass_opacity
        - patchy_consolidation
        - no_clear_tree_in_bud
        - no_cavitation
        - background_fibrosis_similar_or_slightly_increased
      temporal_change:
        - new_or_increased_bilateral_airspace_opacity

    labs_or_context:
      WBC_CRP: unavailable
      microbiology: unavailable
      viral_testing: unavailable
      BNP: unavailable
      creatinine: unavailable
      hemoglobin_trend: unavailable

  expected_output:
    reasoning_state: infection_vs_AE_vs_drug_toxicity_gray_zone

    competing_reasoning_paths:
      - infection
      - acute_exacerbation_or_acute_lung_injury
      - drug_or_treatment_related_lung_injury
      - CTD_flare_or_OP_like_inflammation
      - edema_or_volume_overload
      - hemorrhage_context_dependent

    supports_infection_possibility:
      - cough
      - possible_low_grade_fever
      - immunosuppression_possible
      - microbiology_unavailable

    weakens_infection_as_only_pathway:
      - no_clear_tree_in_bud
      - no_cavitation
      - bilateral_GGO_pattern_not_specific
      - recent_biologic_timeline
      - AE_and_drug_toxicity_remain_plausible

    cannot_conclude:
      - infection
      - infection_excluded
      - acute_exacerbation
      - drug_toxicity
      - edema_excluded
      - CTD_flare
      - simple_fibrotic_progression

    missing_pieces:
      - microbiology_and_viral_testing
      - WBC_CRP_and_clinical_infection_markers
      - exact_medication_timeline_dose_and_duration
      - CTD_activity_context
      - cardiac_volume_status
      - renal_function
      - hemoptysis_and_hemoglobin_trend
      - MDD_or_urgent_review_if_unstable

    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - vascular_edema_hemorrhage_mimic_panel_v1

    final_prompt:
      - What evidence would separate infection from acute exacerbation, drug toxicity, CTD flare, edema, or hemorrhage?
```

---

## 4. Case 3 — Mimic-dominant Scenario: OP or Malignancy Mimicking Infection

```yaml
case_INF_003_mimic_dominant_OP_or_malignancy:
  case_id: INF_003
  case_type: alternative_diagnosis_mimic_dominant_scenario
  target_page: docs/reasoning/superimposed_infection_on_ILD_background_v1.md

  linked_modules:
    - organizing_pneumonia_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - temporal_comparison_methodology_v1
    - superimposed_events_core_blueprint_v1

  input:
    patient_context:
      age: 71
      sex: female
      known_background:
        - fibrotic_ILD
      clinical_time_course: subacute_cough_over_5_weeks
      oxygen_requirement_change: unknown
      fever: absent
      sputum: absent_or_minimal
      cancer_history: unknown
      medication_timeline: unknown
      CTD_context: unknown

    imaging_context:
      baseline_pattern: fibrotic_ILD_background
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 3_months
      prior_CT_findings:
        - stable_reticulation
        - traction_bronchiectasis
        - no_focal_consolidation
      current_CT_findings:
        - new_peripheral_focal_consolidation
        - OP_like_morphology_possible
        - no_tree_in_bud
        - no_cavitation
        - no_airway_centered_nodules
        - focal_persistence_unknown
      temporal_change:
        - new_focal_peripheral_opacity

    labs_or_context:
      WBC_CRP: normal_or_unavailable
      microbiology: unavailable
      viral_testing: unavailable
      PET_CT: unavailable
      follow_up_CT: unavailable

  expected_output:
    reasoning_state: infection_weakened_OP_or_malignancy_mimic_visible

    mimic_support:
      - fever_absent
      - sputum_absent_or_minimal
      - no_tree_in_bud
      - no_cavitation
      - peripheral_OP_like_consolidation
      - focal_opacity_requires_persistence_and_malignancy_review_if_it_does_not_resolve

    weakens_infection_primary_pathway:
      - no_airway_centered_pattern
      - no_clear_systemic_infectious_context
      - subacute_time_course
      - microbiology_missing

    cannot_conclude:
      - organizing_pneumonia
      - malignancy
      - infection_excluded
      - aspiration_excluded
      - infarct_excluded
      - drug_toxicity_excluded
      - benign_fibrotic_change

    missing_pieces:
      - follow_up_or_persistence_context
      - malignancy_risk_and_cancer_history
      - infection_labs_and_microbiology
      - CTD_or_autoimmune_context
      - medication_and_treatment_timeline
      - aspiration_risk
      - MDD_review_if_persistent_or_discordant

    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - Is this truly infection, or could OP, malignancy, aspiration, infarct, or treatment-related opacity better explain the focal abnormality?
```

---

## 5. Case 4 — Red-flag / Urgent-review Scenario: Immunosuppressed Patient with Cavitation

```yaml
case_INF_004_red_flag_immunosuppressed_cavitary_opacity:
  case_id: INF_004
  case_type: red_flag_urgent_review_scenario
  target_page: docs/reasoning/superimposed_infection_on_ILD_background_v1.md

  linked_modules:
    - vascular_edema_hemorrhage_mimic_panel_v1
    - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - superimposed_events_core_blueprint_v1

  input:
    patient_context:
      age: 60
      sex: male
      known_background:
        - granulomatous_ILD_or_sarcoidosis_like_history
      clinical_time_course: acute_subacute_worsening_over_2_weeks
      oxygen_requirement_change: increased
      fever: unknown_or_present
      immune_status: immunosuppressed
      medication_timeline: steroids_or_biologic_possible
      hemoptysis: unknown
      renal_context: unknown
      cancer_history: unknown

    imaging_context:
      baseline_pattern: granulomatous_or_fibrotic_ILD_background
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - new_cavitary_nodule_or_cavitary_consolidation
        - surrounding_ground_glass_opacity
        - possible_multifocal_nodules
        - lymphadenopathy_status_unclear
        - baseline_nodularity_or_fibrosis_possible
      temporal_change:
        - new_cavitary_process_possible

    labs_or_context:
      microbiology: unavailable
      TB_NTM_fungal_testing: unavailable
      WBC_CRP: unavailable
      hemoglobin_trend: unavailable
      urinalysis: unavailable
      ANCA_context: unavailable

  expected_output:
    reasoning_state: red_flag_cavitary_superimposed_process_in_immunosuppressed_ILD

    red_flags:
      - immunosuppression
      - new_cavitation
      - increased_oxygen_requirement
      - possible_multifocal_nodules
      - TB_NTM_fungal_or_bacterial_infection_possible
      - vasculitis_or_malignancy_mimics_not_excluded
      - baseline_granulomatous_label_cannot_explain_new_cavitation_by_default

    competing_high_risk_pathways:
      - TB_NTM_fungal_or_bacterial_infection
      - GPA_or_granulomatous_vasculitis
      - malignancy_or_cavitary_metastatic_disease_context_dependent
      - septic_emboli_context_dependent
      - drug_or_treatment_related_lung_injury_context_dependent
      - hemorrhage_context_dependent

    cannot_conclude:
      - infection_confirmed
      - infection_excluded
      - sarcoidosis_progression
      - GPA_or_vasculitis_excluded
      - malignancy_excluded
      - drug_toxicity_excluded
      - benign_granulomatous_change

    missing_pieces:
      - prior_CT_review
      - TB_NTM_fungal_bacterial_microbiology
      - immune_status_and_treatment_timeline
      - blood_culture_or_septic_emboli_context_if_relevant
      - hemoptysis_and_hemoglobin_trend
      - urinalysis_and_renal_function
      - ANCA_or_autoimmune_context_if_relevant
      - lymphadenopathy_and_cancer_context
      - urgent_review_or_MDD
      - infectious_disease_review_if_clinically_relevant

    route_to:
      - superimposed_events_core_blueprint_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - malignancy_on_fibrotic_ILD_background_v1

    final_prompt:
      - What high-risk infectious and noninfectious mimics must be reviewed before attributing new cavitation to baseline granulomatous ILD?
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
  target_page: superimposed_infection_on_ILD_background_v1
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
    - infection_on_ILD_background_source_verification
    - opportunistic_infection_source_mapping
    - real_case_validation_or_simulation_review
```

---

## 8. Final Test Case Rule

```text
The infection page succeeds only if it can do two things at once:

keep infection visible when the clues matter,

and refuse to call every new opacity infection.

The safest output is the one that keeps the dangerous mimic visible.
```