# Superimposed Events Test Case Pack — v1

## Document Metadata

```yaml
id: test_cases_superimposed_events_test_case_pack_v1
title: Superimposed Events Test Case Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: test_case_pack
diagnostic_authority: none
treatment_authority: none
module_version: v0.5
target_page:
  - docs/reasoning/superimposed_events_core_blueprint_v1.md
linked_modules:
  - docs/reasoning/superimposed_infection_on_ILD_background_v1.md
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

This test case pack stress-tests the Superimposed Events Core.

It verifies that the platform can reason through new findings on a background of known or suspected ILD without allowing the baseline ILD label to swallow the new process.

These test cases do not validate clinical correctness.

They verify whether the page preserves uncertainty, exposes missing data, routes mimics, identifies red flags, and avoids diagnostic or treatment overreach.

---

## 1. Test Case Coverage Status

```yaml
test_case_coverage_status:
  target_page: superimposed_events_core_blueprint_v1
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

## 2. Case 1 — Typical Scenario: New Focal Consolidation on Fibrotic ILD Background

```yaml
case_SUPER_001_typical_new_focal_consolidation:
  case_id: SUPER_001
  case_type: typical_scenario
  target_page: docs/reasoning/superimposed_events_core_blueprint_v1.md

  linked_modules:
    - superimposed_infection_on_ILD_background_v1
    - organizing_pneumonia_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 70
      sex: male
      known_background:
        - fibrotic_ILD
        - UIP_like_pattern
      clinical_time_course: new_cough_and_dyspnea_over_10_days
      oxygen_requirement_change: mildly_increased
      fever: unknown
      cancer_history: unknown
      aspiration_risk: unknown
      treatment_or_medication_timeline: unknown

    imaging_context:
      baseline_pattern: UIP_like_fibrotic_pattern
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - background_honeycombing
        - traction_bronchiectasis
        - new_right_lower_lobe_focal_consolidation
        - surrounding_ground_glass_opacity
        - no_reported_new_mass
      temporal_change:
        - new_focal_airspace_opacity_possible

    labs_or_context:
      infection_data: unavailable
      microbiology: unavailable
      WBC_CRP: unavailable
      cardiac_context: unknown

  expected_output:
    reasoning_state: new_focal_consolidation_on_fibrotic_ILD_background

    supports_superimposed_event_pathway:
      - new_focal_consolidation
      - background_ILD_label_does_not_explain_new_opacity_by_default
      - acute_subacute_symptom_change
      - prior_CT_not_reviewed

    competing_reasoning_paths:
      - infection
      - organizing_pneumonia
      - aspiration
      - malignancy_if_persistent_or_mass_like
      - pulmonary_infarct_context_dependent
      - drug_or_treatment_related_change_if_timeline_supports

    cannot_conclude:
      - bacterial_pneumonia
      - organizing_pneumonia
      - malignancy_excluded
      - aspiration_excluded
      - simple_fibrotic_progression
      - acute_exacerbation_excluded

    missing_pieces:
      - prior_CT_review
      - fever_and_infection_context
      - WBC_CRP_and_microbiology
      - aspiration_risk
      - cancer_history_and_risk
      - medication_and_treatment_timeline
      - follow_up_or_persistence_context
      - MDD_review_if_uncertain

    route_to:
      - superimposed_infection_on_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - temporal_comparison_methodology_v1

    final_prompt:
      - What new process may have appeared on top of the fibrotic ILD background, and what evidence is missing before naming it?
```

---

## 3. Case 2 — Indeterminate / Gray-zone Scenario: New Bilateral GGO with Infection, AE, Edema, and Drug Toxicity Overlap

```yaml
case_SUPER_002_gray_zone_bilateral_GGO_multiple_overlap:
  case_id: SUPER_002
  case_type: indeterminate_gray_zone_scenario
  target_page: docs/reasoning/superimposed_events_core_blueprint_v1.md

  linked_modules:
    - acute_exacerbation_vs_infection_vs_edema_v1
    - superimposed_infection_on_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1

  input:
    patient_context:
      age: 66
      sex: female
      known_background:
        - CTD_ILD
        - fibrotic_NSIP_like_pattern
      clinical_time_course: worsening_dyspnea_over_2_weeks
      oxygen_requirement_change: increased
      fever: unknown
      cough: present
      immune_status: immunosuppression_possible
      treatment_or_medication_timeline: biologic_started_8_weeks_ago
      cardiac_context: unknown
      renal_context: unknown

    imaging_context:
      baseline_pattern: fibrotic_NSIP_like_pattern
      prior_CT_status: reviewed_comparable
      prior_CT_interval: 8_months
      prior_CT_findings:
        - lower_lung_ground_glass_opacity
        - mild_reticulation
        - traction_bronchiectasis
      current_CT_findings:
        - increased_bilateral_ground_glass_opacity
        - patchy_consolidation
        - background_reticulation
        - traction_bronchiectasis_similar_or_slightly_increased
        - no_mass_reported
      temporal_change:
        - new_or_increased_airspace_opacity
        - structural_progression_uncertain

    labs_or_context:
      infection_data: unavailable
      viral_testing: unavailable
      WBC_CRP: unavailable
      BNP: unavailable
      creatinine: unavailable
      hemoptysis: unknown

  expected_output:
    reasoning_state: superimposed_event_gray_zone_with_AE_infection_edema_drug_overlap

    competing_reasoning_paths:
      - acute_exacerbation_or_acute_lung_injury
      - infection
      - drug_or_treatment_related_lung_injury
      - edema_or_volume_overload
      - organizing_pneumonia_or_CTD_flare
      - hemorrhage_context_dependent

    supports_gray_zone:
      - new_bilateral_GGO
      - acute_subacute_worsening
      - increased_oxygen_requirement
      - recent_biologic_or_treatment_timeline
      - infection_data_missing
      - cardiac_and_renal_context_missing

    cannot_conclude:
      - acute_exacerbation
      - infection_excluded
      - drug_toxicity
      - edema_excluded
      - hemorrhage_excluded
      - CTD_flare
      - pure_fibrotic_progression

    missing_pieces:
      - prior_CT_detailed_structural_comparison
      - infection_labs_and_microbiology
      - viral_testing
      - exact_medication_timeline_dose_and_duration
      - CTD_activity_context
      - cardiac_volume_status
      - renal_function
      - hemoptysis_and_hemoglobin_trend
      - MDD_or_urgent_review_if_clinically_unstable

    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - superimposed_infection_on_ILD_background_v1

    final_prompt:
      - Which competing acute process remains possible before calling this AE, infection, drug toxicity, edema, or progression?
```

---

## 4. Case 3 — Mimic-dominant Scenario: Peripheral Wedge-like Opacity Suggesting Vascular Event Rather Than Pneumonia or OP

```yaml
case_SUPER_003_mimic_dominant_PE_infarct_like_opacity:
  case_id: SUPER_003
  case_type: alternative_diagnosis_mimic_dominant_scenario
  target_page: docs/reasoning/superimposed_events_core_blueprint_v1.md

  linked_modules:
    - vascular_edema_hemorrhage_mimic_panel_v1
    - organizing_pneumonia_on_ILD_background_v1
    - superimposed_infection_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1

  input:
    patient_context:
      age: 73
      sex: male
      known_background:
        - fibrotic_ILD
        - probable_UIP_pattern
      clinical_time_course: sudden_pleuritic_chest_pain_and_dyspnea_over_1_day
      oxygen_requirement_change: increased
      fever: absent_or_unknown
      PE_risk_context: recent_immobility_possible
      cancer_history: unknown
      infection_symptoms: minimal_or_unknown

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
        - no_diffuse_new_GGO
        - no_tree_in_bud_reported
      temporal_change:
        - new_peripheral_focal_opacity
        - stable_structural_fibrosis

    labs_or_context:
      infection_data: unavailable
      D_dimer_or_CTPA_context: unavailable
      cardiac_context: unknown
      anticoagulation: unknown

  expected_output:
    reasoning_state: vascular_mimic_dominant_superimposed_event

    mimic_support:
      - acute_pleuritic_chest_pain
      - sudden_dyspnea
      - peripheral_pleural_based_wedge_like_opacity
      - stable_background_fibrosis
      - possible_PE_risk_context
      - no_diffuse_fibrotic_progression_signal

    weakens_pneumonia_or_OP_default:
      - fever_absent_or_unknown
      - no_tree_in_bud_reported
      - wedge_like_pleural_based_morphology
      - acute_vascular_time_course_possible

    cannot_conclude:
      - pulmonary_embolism
      - pulmonary_infarct
      - infection_excluded
      - organizing_pneumonia_excluded
      - malignancy_excluded
      - simple_ILD_progression

    missing_pieces:
      - PE_risk_assessment
      - vascular_imaging_or_CTPA_context_if_available
      - chest_pain_and_acuity_detail
      - infection_review
      - follow_up_or_persistence_context
      - cancer_history
      - MDD_or_urgent_review_if_unstable

    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1

    final_prompt:
      - Is this focal opacity infection or OP, or could a vascular event such as PE/infarct better explain the acute change?
```

---

## 5. Case 4 — Red-flag / Urgent-review Scenario: Cavitation with Immunosuppression and Pulmonary-renal / Hemorrhage Context

```yaml
case_SUPER_004_red_flag_cavitation_DAH_vasculitis_infection_overlap:
  case_id: SUPER_004
  case_type: red_flag_urgent_review_scenario
  target_page: docs/reasoning/superimposed_events_core_blueprint_v1.md

  linked_modules:
    - superimposed_infection_on_ILD_background_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1

  input:
    patient_context:
      age: 61
      sex: female
      known_background:
        - granulomatous_ILD_or_sarcoidosis_like_history
        - immunosuppression_possible
      clinical_time_course: acute_worsening_over_1_week
      oxygen_requirement_change: increased
      fever: unknown
      hemoptysis: possible
      renal_context: rising_creatinine_or_urinalysis_unknown
      medication_or_treatment_timeline: steroids_or_immunosuppressive_therapy_unknown_duration
      cancer_history: unknown

    imaging_context:
      baseline_pattern: sarcoidosis_like_or_granulomatous_background
      prior_CT_status: available_not_reviewed
      current_CT_findings:
        - new_cavitary_nodule_or_cavitary_opacity
        - patchy_ground_glass_opacity
        - possible_multifocal_nodules
        - lymphadenopathy_status_unclear
      temporal_change:
        - new_cavitation_possible
        - new_GGO_possible

    labs_or_context:
      infection_data: unavailable
      microbiology: unavailable
      hemoglobin_trend: unavailable
      urinalysis: unavailable
      ANCA_context: unavailable
      immune_status: incomplete

  expected_output:
    reasoning_state: red_flag_superimposed_event_with_cavitation_hemorrhage_vasculitis_infection_overlap

    red_flags:
      - new_cavitation
      - immunosuppression_possible
      - possible_hemoptysis
      - patchy_GGO
      - renal_or_urinalysis_context_missing
      - granulomatous_background_may_hide_infection_or_vasculitis
      - oxygen_requirement_increased

    competing_high_risk_pathways:
      - TB_NTM_fungal_or_bacterial_infection
      - GPA_or_granulomatous_vasculitis
      - diffuse_alveolar_hemorrhage_context_dependent
      - malignancy_or_cavitary_metastasis_context_dependent
      - drug_or_treatment_related_lung_injury_context_dependent
      - sarcoidosis_complication_not_assumed

    cannot_conclude:
      - sarcoidosis_progression
      - infection_excluded
      - GPA_or_vasculitis_excluded
      - diffuse_alveolar_hemorrhage_excluded
      - malignancy_excluded
      - drug_toxicity_excluded
      - benign_granulomatous_change

    missing_pieces:
      - prior_CT_review
      - microbiology_TB_NTM_fungal_bacterial_context
      - immune_status_and_immunosuppression_timeline
      - hemoptysis_detail_and_hemoglobin_trend
      - urinalysis_and_renal_function
      - ANCA_or_autoimmune_context_if_relevant
      - lymphadenopathy_and_cancer_context
      - urgent_review_or_MDD
      - infectious_disease_and_rheumatology_review_if_clinically_relevant

    route_to:
      - superimposed_infection_on_ILD_background_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - malignancy_on_fibrotic_ILD_background_v1

    final_prompt:
      - What high-risk mimic must be reviewed before attributing new cavitation and GGO to the baseline granulomatous ILD label?
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
  target_page: superimposed_events_core_blueprint_v1
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
A superimposed event page succeeds only if it prevents the baseline ILD label from swallowing the new process.

The safest output is not the fastest label.

The safest output is the next missing question.
```