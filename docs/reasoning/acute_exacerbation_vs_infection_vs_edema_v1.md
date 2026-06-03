# Acute Exacerbation vs Infection vs Edema — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_acute_exacerbation_vs_infection_vs_edema_v1
title: Acute Exacerbation vs Infection vs Edema — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: superimposed_event_reasoning_map
diagnostic_authority: none
module_version: v0.3
linked_reasoning_maps:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - fibrotic_ild_triage_map_v1
linked_future_modules:
  - pulmonary_edema_on_ILD_background_v1
  - acute_exacerbation_of_fibrotic_ILD_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - hemorrhage_on_ILD_background_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - emergency / acute care clinicians
  - intensivists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare acute exacerbation, infection, and pulmonary edema / volume overload on a background of known or suspected fibrotic interstitial lung disease.

It does not diagnose acute exacerbation, infection, pulmonary edema, heart failure, drug toxicity, hemorrhage, pulmonary embolism, aspiration, or ILD progression.

It helps users ask:

- Is this true acute exacerbation of fibrotic ILD?
- Is infection still possible?
- Is edema, heart failure, renal failure, or volume overload still possible?
- Is the new abnormality bilateral, focal, dependent, airway-centered, smooth-septal, or diffuse?
- Is the clinical time course acute, subacute, or chronic?
- What did the prior CT show?
- What clinical, laboratory, microbiologic, cardiac, medication, and oxygen-trend data are missing?
- Is urgent review or MDD needed?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    New bilateral ground-glass opacity or consolidation on fibrotic ILD background should not automatically
    be labeled acute exacerbation, infection, or edema without reviewing competing explanations.

  platform_rule:
    - do_not_call_every_new_bilateral_GGO_acute_exacerbation
    - do_not_call_every_new_GGO_infection
    - do_not_call_every_smooth_septal_GGO_edema_without_context
    - do_not_call_rapid_decline_simple_fibrotic_progression
    - preserve_infection_edema_drug_toxicity_hemorrhage_PE_and_OP_differential_until_context_is_reviewed
```

### Teaching Point

The first question is not:

```text
Is this acute exacerbation?
```

The better first question is:

```text
What acute process best explains the new alveolar abnormality on top of the ILD background?
```

---

## 2. Core Distinction

```yaml
core_distinction:
  acute_exacerbation_pathway:
    reasoning_center: acute_or_subacute_respiratory_deterioration_with_new_bilateral_GGO_or_consolidation_on_fibrotic_ILD_background_not_fully_explained_by_cardiac_failure_or_fluid_overload
    supportive_clues:
      - known_or_suspected_fibrotic_ILD
      - acute_or_subacute_worsening_typically_within_one_month
      - new_bilateral_ground_glass_opacity
      - new_bilateral_consolidation
      - abnormality_superimposed_on_fibrotic_background
      - no_dominant_focal_lobar_airway_centered_or_dependent_infectious_pattern_after_review
      - cardiac_failure_or_fluid_overload_not_sufficient_to_explain_findings
    danger_statement: acute_exacerbation_should_not_be_called_before_infection_edema_PE_drug_toxicity_hemorrhage_and_OP_are_reviewed

  infection_pathway:
    reasoning_center: new_opacity_with_clinical_microbiologic_airway_focal_multifocal_or_opportunistic_infectious_context
    supportive_clues:
      - fever_or_systemic_infectious_context
      - leukocytosis_or_inflammatory_marker_context
      - sputum_or_productive_cough
      - positive_microbiology_or_viral_testing_when_available
      - immunosuppression_or_opportunistic_risk
      - focal_lobar_or_airway_centered_opacity
      - tree_in_bud
      - cavitation
      - necrotic_nodes
    danger_statement: infection_should_not_be_excluded_just_because_CT_shows_bilateral_GGO_or_because_fever_is_absent_in_immunosuppression

  pulmonary_edema_or_volume_overload_pathway:
    reasoning_center: new_GGO_or_septal_thickening_with_cardiac_renal_volume_or_hydrostatic_context
    supportive_clues:
      - heart_failure_context
      - volume_overload_context
      - renal_failure_context
      - smooth_interlobular_septal_thickening
      - dependent_or_perihilar_GGO
      - pleural_effusions
      - cardiomegaly_or_vascular_congestion_context_when_available
      - improvement_after_diuresis_or_volume_management_when_known
    danger_statement: edema_can_mimic_infection_or_acute_exacerbation_and_requires_cardiac_volume_context
```

---

## 3. Direct Comparison Matrix

| Feature | More Acute Exacerbation-like | More Infection-like | More Edema / Volume Overload-like | Reasoning Note |
|---|---|---|---|---|
| Time course | Acute/subacute respiratory worsening | Acute/subacute with infectious context | Acute/subacute with cardiac/volume context | Time course alone is insufficient |
| Distribution | New bilateral GGO/consolidation | Focal, lobar, airway-centered, multifocal, diffuse possible | Perihilar/dependent GGO, smooth septal thickening | Distribution guides but does not decide |
| Tree-in-bud | Not typical | Strong airway infection/aspiration clue | Not typical | High-value infection clue |
| Cavitation | Not typical | TB/fungal/abscess/septic emboli possible | Not typical | Also consider GPA/malignancy |
| Smooth septal thickening | Possible but not defining | Possible | Supports edema in correct context | Needs cardiac/volume data |
| Pleural effusion | Not classic driver | Can occur | Supports edema/volume context | Not standalone |
| Fever | Not defining | Supports infection | Can be absent | Fever absence does not exclude infection |
| BNP/echo/volume context | Helps exclude edema | Not central | High-value | Clinical data needed |
| Microbiology | Helps review triggers/mimics | Central when infection suspected | Usually not central | Absence of testing is not exclusion |
| Prior CT | Required for newness and baseline | Required | Required | High-yield for all pathways |

---

## 4. Entry Scenarios

### 4.1 New Bilateral GGO on Fibrotic ILD Background

```yaml
scenario_new_bilateral_GGO:
  problem:
    - background_fibrotic_ILD
    - new_bilateral_ground_glass_opacity
    - acute_or_subacute_worsening_possible

  acute_exacerbation_leaning_features:
    - acute_respiratory_deterioration
    - new_bilateral_GGO_or_consolidation
    - fibrotic_background
    - no_focal_lobar_airway_centered_or_dependent_dominant_pattern_after_review
    - edema_not_sufficient_to_explain_findings

  infection_leaning_features:
    - fever_or_infectious_symptoms
    - positive_viral_or_microbiologic_testing
    - immunosuppression
    - airway_centered_features
    - exposure_or_outbreak_context

  edema_leaning_features:
    - heart_failure_or_volume_overload_context
    - renal_failure_context
    - smooth_septal_thickening
    - pleural_effusions
    - dependent_or_perihilar_distribution
    - improvement_after_diuresis_when_known

  missing_pieces:
    - prior_CT
    - symptom_time_course
    - oxygen_requirement_trend
    - infection_labs_and_microbiology
    - medication_and_treatment_timeline
    - cardiac_status
    - volume_status
    - renal_function
    - BNP_or_echo_context_if_available
    - hemoptysis_or_anemia_context
    - MDD_or_urgent_review

  pitfall:
    - New_bilateral_GGO_is_not_specific_for_acute_exacerbation_infection_or_edema
```

### 4.2 Rapid Decline with Smooth Septal Thickening

```yaml
scenario_rapid_decline_smooth_septal_thickening:
  problem:
    - fibrotic_ILD_background
    - rapid_dyspnea_or_oxygen_worsening
    - new_GGO_with_smooth_septal_thickening

  edema_leaning_features:
    - smooth_interlobular_septal_thickening
    - pleural_effusions
    - dependent_or_perihilar_GGO
    - cardiac_failure_context
    - renal_failure_or_volume_overload_context
    - response_to_volume_management_when_known

  acute_exacerbation_leaning_features:
    - new_bilateral_GGO
    - no_sufficient_cardiac_or_volume_explanation
    - severe_respiratory_decline
    - fibrotic_background

  infection_leaning_features:
    - fever
    - leukocytosis
    - microbiologic_support
    - focal_or_airway_centered_component
    - immunosuppression

  missing_pieces:
    - BNP_or_cardiac_marker_context
    - echocardiography_or_clinical_heart_failure_context
    - renal_function_and_fluid_balance
    - infection_review
    - prior_CT
    - medication_timeline
    - oxygen_trend
    - MDD_review

  pitfall:
    - Smooth_septal_GGO_should_not_be_called_AE_without_edema_volume_review
```

### 4.3 Focal Consolidation Plus Diffuse Background GGO

```yaml
scenario_focal_consolidation_plus_diffuse_GGO:
  problem:
    - fibrotic_ILD_background
    - focal_consolidation
    - additional_diffuse_or_multifocal_GGO

  infection_leaning_features:
    - focal_or_lobar_consolidation
    - air_bronchograms
    - fever_or_sputum
    - microbiologic_support
    - surrounding_GGO
    - aspiration_or_airway_context

  acute_exacerbation_leaning_features:
    - diffuse_bilateral_GGO
    - respiratory_deterioration
    - focal_component_not_sufficient_to_explain_entire_pattern
    - no_infectious_source_after_review

  edema_leaning_features:
    - smooth_septal_thickening
    - pleural_effusions
    - volume_overload_context
    - dependent_GGO

  competing_mimics:
    - organizing_pneumonia
    - aspiration
    - malignancy
    - pulmonary_infarct
    - drug_toxicity

  missing_pieces:
    - prior_CT
    - clinical_time_course
    - infection_labs_microbiology
    - aspiration_risk
    - cardiac_volume_context
    - cancer_history
    - follow_up_or_persistence_context
    - MDD_review

  pitfall:
    - A_focal_infectious_appearing_opacity_does_not_exclude_a_second_diffuse_process
```

### 4.4 Immunosuppressed Fibrotic ILD Patient with New Diffuse GGO

```yaml
scenario_immunosuppressed_new_diffuse_GGO:
  problem:
    - fibrotic_ILD_background
    - immunosuppression
    - new_diffuse_or_bilateral_GGO

  infection_leaning_features:
    - opportunistic_infection_risk
    - viral_or_PJP_like_context
    - fever_may_be_absent
    - microbiology_or_BAL_context_needed
    - immunosuppression_type_dose_duration_relevant

  acute_exacerbation_leaning_features:
    - acute_respiratory_deterioration
    - new_bilateral_GGO_or_consolidation
    - no_infectious_or_edema_explanation_after_review

  edema_or_drug_toxicity_leaning_features:
    - cardiac_or_volume_context
    - medication_or_treatment_timeline
    - ICI_chemotherapy_DMARD_amiodarone_nitrofurantoin_or_other_drug_context

  missing_pieces:
    - immunosuppression_type_dose_duration
    - prophylaxis_status_when_relevant
    - microbiology_and_viral_testing
    - BAL_context_if_clinically_relevant
    - medication_timeline
    - cardiac_volume_context
    - prior_CT
    - urgent_or_MDD_review

  pitfall:
    - Absence_of_fever_does_not_exclude_infection_in_immunosuppressed_ILD
```

---

## 5. Why Not Engine

### Why not acute exacerbation?

```yaml
why_not_acute_exacerbation:
  - dominant_focal_lobar_consolidation
  - tree_in_bud
  - cavitation
  - clear_microbiologic_support_for_infection
  - clear_cardiac_failure_or_volume_overload_explanation
  - smooth_septal_thickening_with_pleural_effusions_and_volume_context
  - drug_toxicity_timeline
  - hemoptysis_or_DAH_context
  - PE_or_infarct_context
  - prior_CT_not_reviewed
```

### Why not infection?

```yaml
why_not_infection:
  - no_clinical_infectious_context_after_review
  - microbiology_negative_when_appropriately_obtained_and_context_fits
  - diffuse_pattern_more_consistent_with_AE_edema_drug_toxicity_or_hemorrhage
  - strong_cardiac_volume_explanation
  - no_airway_centered_focal_lobar_or_cavitary_component
  - persistent_focal_lesion_suggesting_malignancy_or_OP
```

### Why not edema?

```yaml
why_not_edema:
  - no_cardiac_renal_or_volume_overload_context
  - no_pleural_effusions_or_smooth_septal_thickening_when_expected
  - focal_airway_centered_or_cavitary_pattern
  - microbiologic_or_infectious_context_stronger
  - new_bilateral_GGO_persists_despite_volume_management
  - medication_toxicity_or_AE_context_stronger
```

### Why not simple progression?

```yaml
why_not_simple_progression:
  - acute_or_subacute_time_course
  - new_GGO_or_consolidation
  - oxygen_requirement_change_too_fast_for_chronic_fibrosis
  - potentially_reversible_component
  - prior_CT_not_reviewed
  - infection_edema_drug_toxicity_hemorrhage_PE_or_OP_not_reviewed
```

---

## 6. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether GGO/consolidation is new, progressive, resolving, technical, or chronic.

    symptom_time_course:
      reason: Acute hours-days versus subacute weeks versus chronic months changes the differential.

    oxygen_requirement_trend:
      reason: Acute oxygen escalation raises urgency and supports acute process review.

    infection_review:
      reason: Fever, WBC, CRP, cultures, viral testing, sputum/BAL, exposure, and immunosuppression may separate infection from AE or edema.

    cardiac_and_volume_status:
      reason: Heart failure, renal failure, fluid balance, BNP, echo, and pleural effusions may support edema.

    renal_function:
      reason: Renal failure can support volume overload and may also trigger pulmonary-renal vasculitis review when paired with hemoptysis/GGO.

    medication_and_treatment_timeline:
      reason: Drug toxicity, ICI pneumonitis, chemotherapy injury, radiation injury, or immunosuppression complications may mimic AE/infection.

    hemoptysis_anemia_or_DAH_context:
      reason: Hemorrhage may mimic diffuse infection or acute exacerbation.

    PE_or_vascular_context:
      reason: PE or infarct may cause acute decline and focal/peripheral opacity.

    CT_technical_comparability:
      reason: Inspiration, motion, reconstruction kernel, slice thickness, contrast, and positioning can exaggerate change.

    urgent_or_MDD_review:
      reason: AE, infection, and edema frequently overlap and may require acute multidisciplinary assessment.
```

---

## 7. Red Flag Panel

```yaml
red_flags:
  acute_exacerbation_red_flags:
    - new_bilateral_GGO_or_consolidation_on_fibrotic_background
    - rapid_respiratory_deterioration
    - increased_oxygen_requirement
    - no_sufficient_cardiac_or_volume_explanation_after_review

  infection_red_flags:
    - fever_or_sepsis_context
    - immunosuppression
    - tree_in_bud
    - focal_lobar_consolidation
    - cavitation
    - positive_microbiology_when_available
    - opportunistic_infection_risk

  edema_red_flags:
    - smooth_interlobular_septal_thickening
    - pleural_effusions
    - dependent_or_perihilar_GGO
    - cardiomegaly_or_heart_failure_context
    - renal_failure_or_volume_overload_context
    - improvement_after_diuresis_when_known

  non_three_way_mimic_red_flags:
    - hemoptysis_or_anemia
    - medication_or_treatment_timeline
    - PE_risk_or_infarct_like_opacity
    - persistent_focal_opacity
    - new_or_growing_mass_or_nodule
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  hours_to_days:
    consider:
      - edema
      - aspiration
      - PE
      - hemorrhage
      - severe_infection
      - acute_drug_reaction
      - acute_exacerbation_context

  days_to_weeks:
    consider:
      - infection
      - acute_exacerbation
      - organizing_pneumonia
      - drug_toxicity
      - edema
      - aspiration
      - hemorrhage

  weeks_to_months:
    consider:
      - unresolved_infection
      - organizing_pneumonia
      - malignancy
      - drug_toxicity
      - fibrotic_progression
      - chronic_volume_or_cardiac_context

  rapid_improvement:
    possible_explanations:
      - edema_response_to_diuresis
      - infection_response_to_antimicrobials
      - inflammatory_component_response
      - technical_or_inspiratory_difference
    caution:
      - rapid_improvement_does_not_prove_baseline_fibrosis_reversal

  worsening_despite_antimicrobials_or_diuresis:
    consider:
      - acute_exacerbation
      - wrong_or_resistant_infection
      - drug_toxicity
      - OP
      - malignancy
      - PE_or_hemorrhage
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  urgent_review_high_value_if:
    - rapidly_increasing_oxygen_requirement
    - severe_bilateral_GGO_or_consolidation
    - hemodynamic_instability
    - severe_immunosuppression
    - hemoptysis_or_DAH_context
    - suspected_PE_or_pulmonary_hypertension_decompensation
    - infection_vs_AE_vs_edema_uncertain_in_unstable_patient

  infectious_disease_review_high_value_if:
    - immunosuppressed_ILD
    - opportunistic_infection_possible
    - microbiology_complex_or_negative_despite_high_suspicion
    - TB_NTM_fungal_or_unusual_pathogen_context

  cardiology_or_volume_review_high_value_if:
    - heart_failure_context
    - renal_failure_or_volume_overload
    - smooth_septal_thickening_with_effusions
    - response_to_diuresis_needed_to_interpret_pattern

  MDD_strongly_recommended_if:
    - acute_exacerbation_infection_edema_overlap
    - drug_toxicity_or_hemorrhage_mimic_possible
    - clinical_and_imaging_context_conflict
    - diagnosis_would_change_major_management
    - prior_CT_and_current_CT_suggest_multiple_processes

  sampling_or_BAL_discussion_if:
    - infection_remains_possible_and_result_would_change_management
    - immunosuppression_or_opportunistic_infection_context
    - focal_or_persistent_abnormality_requires_malignancy_or_OP_separation
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling new bilateral GGO acute exacerbation by default.
    correction: Infection, edema, drug toxicity, hemorrhage, OP, PE, and aspiration must remain visible.

  - title: Calling new bilateral GGO infection by default.
    correction: Acute exacerbation, edema, drug toxicity, and hemorrhage can look similar.

  - title: Calling smooth septal GGO acute exacerbation without volume review.
    correction: Heart failure, renal failure, and volume overload can mimic AE or infection.

  - title: Excluding infection because fever is absent.
    correction: Fever may be absent in older or immunosuppressed ILD patients.

  - title: Ignoring prior CT.
    correction: Prior CT is essential to distinguish new superimposed change from chronic background disease.

  - title: Ignoring medication timeline.
    correction: Drug toxicity and treatment-related pneumonitis can mimic AE or infection.

  - title: Forgetting hemorrhage.
    correction: Hemoptysis, anemia, anticoagulation, or vasculitis context can make diffuse GGO hemorrhagic.

  - title: Treating one explanation as exclusive.
    correction: Infection, edema, AE, and drug toxicity can overlap or trigger one another.
```

---

## 11. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - superimposed_events_core_blueprint_v1
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - AE_IPF_revised_definition_and_review_sources
    - acute_exacerbation_non_IPF_fibrotic_ILD_review_sources

  supportive_sources:
    - GGO_differential_diagnosis_review
    - infection_on_ILD_background_review_sources_pending
    - pulmonary_edema_GGO_review_sources_pending
    - ICU_ILD_acute_respiratory_failure_review_sources
    - drug_induced_ILD_HRCT_pattern_review_sources

  evidence_notes:
    - Acute exacerbation reasoning requires acute clinical worsening and new bilateral alveolar abnormality on ILD background.
    - Cardiac failure or fluid overload must be reviewed before increasing acute exacerbation confidence.
    - Infection may be a competing process or trigger and should remain visible.
    - GGO differential includes infection, edema, hemorrhage, drug toxicity, and exacerbation of pre-existing ILD.
```

---

## 12. MVP Test Case

```yaml
case_test_AE_vs_infection_vs_edema_001:
  input:
    age: 74
    sex: male
    known_background:
      - fibrotic_ILD
      - UIP_like_pattern
    new_hrct:
      - new_bilateral_ground_glass_opacity
      - background_reticulation
      - traction_bronchiectasis
      - mild_smooth_interlobular_septal_thickening
      - small_bilateral_pleural_effusions
    history:
      dyspnea_worsening: 10_days
      fever: unknown
      cough: present
      oxygen_requirement_change: increased
      heart_failure_history: unknown
      renal_function: unavailable
      medication_timeline: unavailable
      infection_testing: unavailable
      prior_CT: available_but_not_reviewed
    labs:
      WBC: unavailable
      CRP: unavailable
      BNP: unavailable
      creatinine: unavailable
    microbiology:
      viral_testing: unavailable
      cultures: unavailable

  output:
    reasoning_state: acute_exacerbation_vs_infection_vs_edema_gray_zone
    acute_exacerbation_support:
      - fibrotic_ILD_background
      - acute_subacute_worsening
      - new_bilateral_GGO
    infection_support:
      - cough_present
      - fever_and_microbiology_unknown
      - infection_testing_unavailable
    edema_support:
      - smooth_interlobular_septal_thickening
      - small_pleural_effusions
      - cardiac_and_renal_context_unknown
    cannot_conclude:
      - acute_exacerbation
      - infection_excluded
      - pulmonary_edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded
      - simple_fibrotic_progression
    missing_pieces:
      - prior_CT_review
      - oxygen_requirement_trend
      - infection_labs_and_microbiology
      - BNP_echo_or_heart_failure_context
      - renal_function_and_fluid_balance
      - medication_and_treatment_timeline
      - hemoptysis_or_anemia_context
      - MDD_or_urgent_review
    final_prompt:
      - What evidence is missing before calling this acute exacerbation, infection, or edema?
```

---

## 13. Final Page Prompt

Every Acute Exacerbation vs Infection vs Edema page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. Is the new abnormality bilateral diffuse, focal, airway-centered, dependent, smooth-septal, or cavitary?
4. Is there acute respiratory deterioration and increased oxygen requirement?
5. Is infection still possible?
6. Is cardiac failure, renal failure, or volume overload still possible?
7. Is drug toxicity, hemorrhage, PE, OP, aspiration, or malignancy still possible?
8. What clinical, microbiologic, cardiac, renal, medication, and temporal data are missing?
9. Is urgent review or MDD needed?
10. What do we still not know?
```