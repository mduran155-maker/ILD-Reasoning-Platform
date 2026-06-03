# Superimposed Infection on ILD Background — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_superimposed_infection_on_ILD_background_v1
title: Superimposed Infection on ILD Background — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: superimposed_event_reasoning_map
diagnostic_authority: none
module_version: v0.3
linked_reasoning_maps:
  - superimposed_events_core_blueprint_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - fibrotic_ild_triage_map_v1
linked_future_modules:
  - opportunistic_infection_in_immunosuppressed_ILD_v1
  - aspiration_on_ILD_background_v1
  - infection_vs_organizing_pneumonia_on_ILD_background_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - infectious disease clinicians
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users evaluate suspected infection superimposed on a background of known or suspected interstitial lung disease.

It does not diagnose bacterial pneumonia, viral pneumonia, fungal infection, TB, NTM, aspiration pneumonia, opportunistic infection, acute exacerbation, organizing pneumonia, pulmonary edema, drug toxicity, or ILD progression.

It helps users ask:

- Is the new abnormality compatible with infection?
- Is infection focal, multifocal, diffuse, airway-centered, lobar, nodular, cavitary, or opportunistic?
- Could this instead be acute exacerbation, edema, OP, aspiration, hemorrhage, PE/infarct, drug toxicity, or malignancy?
- Is the patient immunosuppressed?
- What did the prior CT show?
- What clinical, laboratory, microbiologic, treatment, or exposure data are missing?
- Is urgent review or MDD needed?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    New opacity on an ILD background should not automatically be interpreted as infection,
    progression, organizing pneumonia, or acute exacerbation.

  platform_rule:
    - do_not_call_every_new_GGO_infection
    - do_not_call_every_new_consolidation_bacterial_pneumonia
    - do_not_call_every_diffuse_change_acute_exacerbation
    - do_not_call_every_airway_centered_change_aspiration
    - preserve_differential_until_clinical_microbiologic_and_temporal_context_are_reviewed
```

### Teaching Point

The first question is not:

```text
Is this pneumonia?
```

The better first question is:

```text
What type of new process is appearing on top of the ILD background, and what evidence would separate infection from its mimics?
```

---

## 2. Infection Pattern Families on ILD Background

```yaml
infection_pattern_families:
  focal_or_lobar_pneumonia:
    possible_imaging_features:
      - focal_consolidation
      - lobar_or_segmental_opacity
      - air_bronchograms
      - adjacent_GGO
    key_mimics:
      - organizing_pneumonia
      - malignancy
      - aspiration
      - atelectasis
      - infarct

  multifocal_bronchopneumonia:
    possible_imaging_features:
      - patchy_multifocal_consolidation
      - airway_centered_opacities
      - centrilobular_nodules
      - tree_in_bud
      - bronchial_wall_thickening
    key_mimics:
      - aspiration
      - bronchiolitis
      - HP_flare
      - airway_disease
      - drug_toxicity

  viral_or_atypical_pneumonia:
    possible_imaging_features:
      - bilateral_ground_glass_opacity
      - multifocal_GGO
      - crazy_paving_possible
      - patchy_consolidation_possible
    key_mimics:
      - acute_exacerbation
      - drug_toxicity
      - edema
      - hemorrhage
      - OP

  opportunistic_infection:
    possible_contexts:
      - corticosteroid_or_immunosuppressive_therapy
      - biologic_or_DMARD_context
      - transplant_context
      - malignancy_or_chemotherapy_context
      - HIV_or_primary_immunodeficiency_context
      - GLILD_or_CVID_context
    possible_imaging_features:
      - diffuse_GGO
      - nodules
      - cavitation
      - consolidation
      - halo_or_reverse_halo_context_dependent
    key_mimics:
      - drug_toxicity
      - hemorrhage
      - malignancy
      - inflammatory_flare

  TB_NTM_or_fungal_context:
    possible_imaging_features:
      - cavitation
      - tree_in_bud
      - nodules
      - miliary_or_random_nodules
      - lymphadenopathy
      - chronic_consolidation
    key_mimics:
      - GPA_or_vasculitis
      - malignancy
      - sarcoidosis
      - occupational_granulomatous_disease

  aspiration_related_infection:
    possible_imaging_features:
      - dependent_consolidation
      - lower_lobe_or_posterior_distribution
      - tree_in_bud
      - airway_impaction
      - recurrent_multifocal_opacity
    key_mimics:
      - OP
      - bacterial_pneumonia
      - bronchiolitis
      - edema
```

---

## 3. Core Distinction

```yaml
core_distinction:
  infection_pathway:
    reasoning_center: new_or_changing_airspace_airway_nodular_or_cavitary_abnormality_with_clinical_microbiologic_or_risk_context_supporting_infection
    supportive_clues:
      - fever_or_systemic_infectious_symptoms
      - leukocytosis_or_inflammatory_marker_context
      - productive_cough_or_sputum_context
      - positive_microbiology_when_available
      - immunosuppression_or_opportunistic_risk
      - focal_or_airway_centered_opacity
      - tree_in_bud_or_cavitation_when_relevant
      - response_to_appropriate_antimicrobial_context_when_known
    danger_statement: infection_should_not_be_assumed_from_imaging_alone_and_should_not_hide_acute_exacerbation_malignancy_OP_edema_or_drug_toxicity

  acute_exacerbation_pathway:
    reasoning_center: acute_respiratory_worsening_with_new_bilateral_GGO_or_consolidation_on_ILD_background_after_reviewing_alternative_causes
    supportive_clues:
      - acute_or_subacute_dyspnea_worsening
      - new_bilateral_GGO_or_consolidation
      - background_fibrotic_ILD
      - no_dominant_focal_infectious_pattern_after_review
      - infection_edema_PE_drug_toxicity_hemorrhage_reviewed
    danger_statement: acute_exacerbation_should_not_be_called_before_infection_and_other_mimics_are_reviewed

  noninfectious_mimic_pathway:
    reasoning_center: new_opacity_on_ILD_background_due_to_edema_OP_drug_toxicity_hemorrhage_PE_aspiration_or_malignancy
    supportive_clues:
      - cardiac_or_volume_context
      - medication_or_treatment_timeline
      - hemoptysis_or_anemia_context
      - peripheral_infarct_like_opacity
      - persistent_focal_mass_like_opacity
      - migratory_OP_like_pattern
    danger_statement: noninfectious_superimposed_events_can_mimic_infection_and_require_context
```

---

## 4. Direct Comparison Matrix

| Feature | More Infection-like | More Acute Exacerbation-like | More Noninfectious Mimic-like | Reasoning Note |
|---|---|---|---|---|
| Distribution | Focal, lobar, airway-centered, multifocal | Bilateral diffuse new GGO/consolidation | Depends on edema, OP, drug, hemorrhage, PE | Distribution is key |
| Tree-in-bud | Strong infection/aspiration clue | Not typical | Airway disease/aspiration mimic possible | Airway-centered process |
| Cavitation | Infection, TB, fungal, septic emboli | Not typical | GPA/malignancy/rheumatoid nodules | High-risk red flag |
| Fever | Supports infection | Can be absent/present nonspecific | Drug fever or inflammation possible | Clinical context needed |
| Immunosuppression | Opportunistic infection risk | Also AE risk context | Drug toxicity/malignancy possible | Immune context changes differential |
| New diffuse GGO | Viral/opportunistic infection possible | Classic AE pattern context | Edema, hemorrhage, drug toxicity | Not specific |
| Persistent focal consolidation | Infection possible | Less typical | OP/malignancy/aspiration | Persistence matters |
| Prior CT | Determines newness and distribution | Required for change | Required for temporal reasoning | High-yield missing piece |
| Microbiology | Central when infection suspected | Helps exclude infection | May be needed if mimic uncertain | Absence of testing is not negative evidence |

---

## 5. Entry Scenarios

### 5.1 New Focal Consolidation on Fibrotic ILD Background

```yaml
scenario_new_focal_consolidation:
  problem:
    - background_fibrotic_ILD
    - new_focal_or_lobar_consolidation

  infection_leaning_features:
    - fever_or_infectious_symptoms
    - leukocytosis_or_inflammatory_marker_context
    - productive_cough
    - air_bronchogram_with_lobar_distribution
    - microbiologic_support_when_available

  competing_mimics:
    - organizing_pneumonia
    - malignancy
    - aspiration
    - pulmonary_infarct
    - atelectasis
    - drug_or_radiation_injury

  missing_pieces:
    - prior_CT
    - symptom_time_course
    - infection_labs_and_microbiology
    - aspiration_risk
    - cancer_history
    - treatment_or_radiation_timeline
    - follow_up_or_persistence_context
    - MDD_review_if_uncertain

  pitfall:
    - Do_not_call_new_focal_consolidation_simple_infection_if_persistent_asymmetric_or_mass_like
```

### 5.2 New Bilateral GGO on Fibrotic ILD Background

```yaml
scenario_new_bilateral_GGO:
  problem:
    - background_fibrotic_ILD
    - new_bilateral_ground_glass_opacity

  infection_leaning_features:
    - viral_or_atypical_infectious_context
    - fever_or_exposure_context
    - immunosuppression
    - positive_viral_or_microbiologic_testing_when_available
    - airway_or_centrilobular_features_when_present

  acute_exacerbation_leaning_features:
    - acute_or_subacute_respiratory_worsening
    - new_bilateral_GGO_or_consolidation
    - no_alternative_cause_after_review
    - severe_oxygen_requirement_change

  competing_mimics:
    - pulmonary_edema
    - drug_toxicity
    - diffuse_alveolar_hemorrhage
    - OP_or_inflammatory_flare
    - aspiration
    - PE_or_other_acute_process

  missing_pieces:
    - prior_CT_review
    - oxygen_requirement_trend
    - fever_and_infection_review
    - medication_and_treatment_timeline
    - cardiac_or_volume_status
    - hemoptysis_or_anemia_context
    - immune_status
    - MDD_or_urgent_review

  pitfall:
    - New_bilateral_GGO_is_not_specific_for_infection_or_acute_exacerbation
```

### 5.3 Tree-in-bud or Airway-centered Opacity

```yaml
scenario_tree_in_bud_airway_centered_opacity:
  problem:
    - ILD_background
    - new_tree_in_bud_or_airway_centered_nodules

  infection_or_aspiration_leaning_features:
    - tree_in_bud
    - bronchial_wall_thickening
    - dependent_distribution
    - sputum_or_infectious_symptoms
    - aspiration_risk
    - NTM_TB_or_bacterial_context

  competing_mimics:
    - aspiration_bronchiolitis
    - HP_or_airway_centered_ILD
    - airway_sarcoidosis_context
    - small_airways_disease
    - endobronchial_spread_malignancy_context_dependent

  missing_pieces:
    - aspiration_risk_assessment
    - sputum_or_microbiology
    - TB_NTM_context
    - exposure_history
    - expiratory_HRCT_if_air_trapping_present
    - prior_CT
    - MDD_review_if_uncertain

  pitfall:
    - Do_not_ignore_tree_in_bud_as_background_ILD_noise
```

### 5.4 Cavitation on ILD Background

```yaml
scenario_new_cavitation:
  problem:
    - ILD_background
    - new_cavitary_nodule_mass_or_opacity

  infection_leaning_features:
    - TB_or_NTM_context
    - fungal_context
    - bacterial_abscess_context
    - septic_emboli_context
    - immunosuppression
    - microbiologic_support_when_available

  competing_mimics:
    - GPA_or_granulomatous_vasculitis
    - malignancy
    - rheumatoid_nodule_context
    - aspergilloma_or_chronic_cavity_context
    - pulmonary_infarct

  missing_pieces:
    - microbiology
    - immune_status
    - TB_fungal_risk_context
    - vasculitis_review
    - cancer_history
    - prior_CT
    - tissue_or_sampling_context_if_needed
    - urgent_or_MDD_review

  pitfall:
    - Cavitation_is_high_risk_and_should_not_be_called_simple_ILD_change
```

### 5.5 Immunosuppressed ILD Patient with New Opacity

```yaml
scenario_immunosuppressed_ILD_patient_new_opacity:
  problem:
    - known_or_suspected_ILD
    - immunosuppression_or_biologic_or_steroid_context
    - new_GGO_consolidation_or_nodules

  infection_leaning_features:
    - opportunistic_infection_risk
    - diffuse_or_multifocal_GGO
    - nodules_or_cavitation
    - fever_may_be_absent_or_blunted
    - microbiology_needed_or_pending

  competing_mimics:
    - drug_toxicity
    - ILD_flare
    - acute_exacerbation
    - malignancy_or_lymphoproliferative_process
    - edema_or_PE

  missing_pieces:
    - immunosuppression_type_dose_duration
    - prophylaxis_status_when_relevant
    - immune_status
    - microbiology_and_viral_testing
    - medication_timeline
    - prior_CT
    - infectious_disease_or_MDD_review

  pitfall:
    - Absence_of_fever_does_not_exclude_infection_in_immunosuppressed_ILD
```

---

## 6. Why Not Engine

### Why not infection?

```yaml
why_not_infection:
  - no_infectious_symptoms_after_review
  - microbiology_negative_when_appropriately_obtained
  - no_immunosuppression_or_exposure_context
  - new_opacity_distribution_more_consistent_with_edema_OP_drug_toxicity_or_AE
  - focal_opacity_persistent_or_growing_despite_context
  - prior_CT_shows_slow_mass_like_growth
  - cardiac_or_volume_context_stronger
  - medication_timeline_stronger_for_drug_toxicity
```

### Why not acute exacerbation?

```yaml
why_not_acute_exacerbation:
  - focal_lobar_or_airway_centered_pattern
  - tree_in_bud
  - cavitation
  - strong_fever_or_microbiologic_support
  - clear_aspiration_event
  - cardiac_or_volume_overload_context
  - drug_toxicity_timeline
  - PE_or_vascular_context
```

### Why not simple ILD progression?

```yaml
why_not_simple_ILD_progression:
  - acute_or_subacute_time_course
  - new_GGO_or_consolidation
  - new_cavitation
  - new_focal_nodule_or_mass
  - fever_or_infectious_context
  - oxygen_requirement_change_too_fast_for_chronic_fibrosis
  - prior_CT_not_reviewed
```

### Why not OP / inflammatory flare?

```yaml
why_not_OP_or_inflammatory_flare:
  - fever_or_microbiologic_support
  - airway_centered_tree_in_bud
  - cavitation
  - dependent_aspiration_pattern
  - focal_persistent_growth_suggesting_malignancy
  - edema_or_hemorrhage_context_stronger
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether the opacity is new, chronic, resolving, progressive, or technical.

    clinical_time_course:
      reason: Hours, days, weeks, or months strongly changes the differential.

    fever_and_systemic_infectious_context:
      reason: Supports infection but absence may not exclude infection in immunosuppression.

    oxygen_requirement_trend:
      reason: Acute oxygen increase raises urgency and broadens differential.

    microbiology:
      reason: Cultures, viral testing, sputum/BAL context, and organism-specific testing may clarify infection.

    immune_status:
      reason: Immunosuppression changes likely organisms and lowers threshold for opportunistic infection review.

    medication_and_treatment_timeline:
      reason: Drug toxicity, ICI pneumonitis, chemotherapy/radiation injury, and immunosuppression complications can mimic infection.

    aspiration_risk:
      reason: Aspiration can create dependent consolidation, tree-in-bud, or recurrent infection-like change.

    cardiac_or_volume_status:
      reason: Edema can mimic infection or AE with new GGO/septal thickening.

    hemoptysis_or_anemia_context:
      reason: Hemorrhage may mimic infection or AE with diffuse GGO/consolidation.

    cancer_history:
      reason: New focal opacity, nodules, or lymphadenopathy may represent malignancy rather than infection.

    CT_technical_comparability:
      reason: Inspiration, motion, slice thickness, contrast, and reconstruction differences can create false change.

    MDD_or_urgent_review:
      reason: Superimposed infection often overlaps with AE, OP, edema, drug toxicity, and malignancy.
```

---

## 8. Red Flag Panel

```yaml
red_flags:
  infection_red_flags:
    - fever_or_sepsis_context
    - immunosuppression
    - tree_in_bud
    - cavitation
    - necrotic_nodes
    - rapid_new_consolidation
    - opportunistic_infection_risk
    - TB_NTM_or_fungal_context

  mimic_red_flags:
    - new_bilateral_GGO_without_clear_infection_source
    - cardiac_or_volume_context
    - hemoptysis_or_anemia
    - medication_or_therapy_timeline
    - persistent_focal_consolidation
    - new_or_growing_nodule_or_mass
    - PE_risk_or_infarct_like_opacity
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  acute_hours_to_days:
    consider:
      - infection
      - edema
      - PE
      - hemorrhage
      - aspiration
      - acute_drug_reaction
      - acute_exacerbation_context

  subacute_days_to_weeks:
    consider:
      - infection
      - acute_exacerbation
      - OP
      - drug_toxicity
      - aspiration
      - malignancy_if_focal_persistent

  chronic_weeks_to_months:
    consider:
      - unresolved_infection
      - OP
      - malignancy
      - fibrotic_progression
      - recurrent_aspiration
      - chronic_opportunistic_infection

  improvement_after_contextual_treatment_or_time:
    caution:
      - improvement_may_reflect_resolving_infection_edema_OP_or_inflammatory_component
      - improvement_does_not_prove_fibrosis_reversal
      - treatment_response_without_microbiology_can_mislead

  worsening_despite_infection_treatment:
    consider:
      - wrong_or_resistant_infection
      - acute_exacerbation
      - drug_toxicity
      - OP
      - malignancy
      - edema_or_PE
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  urgent_review_high_value_if:
    - rapidly_increasing_oxygen_requirement
    - sepsis_or_hemodynamic_instability
    - severe_immunosuppression
    - hemoptysis_or_DAH_context
    - new_cavitation
    - diffuse_bilateral_GGO_with_acute_decline
    - PE_or_pulmonary_hypertension_decompensation_context

  infectious_disease_review_high_value_if:
    - opportunistic_infection_possible
    - TB_NTM_or_fungal_context
    - immunosuppressed_ILD
    - microbiology_complex_or_negative_despite_high_suspicion
    - recurrent_or_unusual_infections

  MDD_strongly_recommended_if:
    - infection_vs_acute_exacerbation_uncertain
    - infection_vs_OP_or_drug_toxicity_uncertain
    - infection_vs_malignancy_uncertain
    - new_opacity_does_not_fit_single_pathway
    - treatment_decision_depends_on_distinguishing_infection_from_noninfectious_process

  tissue_or_sampling_discussion_if:
    - persistent_or_growing_focal_opacity
    - cavitary_or_nodular_process_uncertain
    - infection_malignancy_or_OP_need_separation
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Calling every new opacity pneumonia.
    correction: New GGO or consolidation may reflect AE, OP, edema, hemorrhage, drug toxicity, aspiration, or malignancy.

  - title: Calling every acute decline acute exacerbation.
    correction: Infection, PE, edema, hemorrhage, aspiration, and drug toxicity must remain visible.

  - title: Ignoring immunosuppression.
    correction: Opportunistic infection may present atypically and fever may be absent.

  - title: Ignoring tree-in-bud.
    correction: Tree-in-bud should trigger airway-centered infection, aspiration, TB/NTM, or bronchiolitis review.

  - title: Missing malignancy in background fibrosis.
    correction: Persistent focal opacity, new nodule, or mass requires malignancy review.

  - title: Treating negative early microbiology as exclusion.
    correction: Negative or unavailable testing does not always exclude infection; sampling context matters.

  - title: Forgetting CT technical comparability.
    correction: Apparent new GGO may be affected by inspiration, motion, slice thickness, or reconstruction differences.
```

---

## 12. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - superimposed_events_core_blueprint_v1
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - AE_IPF_revised_definition_and_review_sources
    - acute_exacerbation_non_IPF_fibrotic_ILD_review_sources

  supportive_sources:
    - infection_on_ILD_background_review_sources_pending
    - opportunistic_infection_in_immunosuppressed_ILD_sources_pending
    - COVID_or_viral_pneumonia_vs_IIP_imaging_review_sources
    - drug_induced_ILD_HRCT_pattern_review_sources
    - ICU_ILD_acute_respiratory_failure_review_sources

  evidence_notes:
    - Infection is a major superimposed event and mimic of acute exacerbation.
    - New bilateral GGO/consolidation on fibrotic ILD background is not specific.
    - Viral pneumonia and ILD patterns may overlap radiologically.
    - Immunosuppression, microbiology, time course, and prior CT are high-yield context.
```

---

## 13. MVP Test Case

```yaml
case_test_superimposed_infection_on_ILD_001:
  input:
    age: 71
    sex: male
    known_background:
      - fibrotic_ILD
      - probable_UIP_pattern
    new_hrct:
      - new_right_lower_lobe_consolidation
      - surrounding_ground_glass_opacity
      - background_reticulation
      - traction_bronchiectasis
      - no_new_mass_reported
    history:
      fever: unknown
      cough: worsened
      sputum: unknown
      oxygen_requirement_change: increased
      aspiration_risk: unknown
      immunosuppression: low_dose_steroids_unknown_duration
      medication_timeline: unknown
      cardiac_status: unknown
      cancer_history: unknown
      prior_CT: available_but_not_reviewed
    labs_microbiology:
      WBC: unavailable
      CRP: unavailable
      cultures: unavailable
      viral_testing: unavailable

  output:
    reasoning_state: new_focal_consolidation_on_fibrotic_ILD_background
    infection_support:
      - new_focal_consolidation
      - worsened_cough
      - oxygen_requirement_increased
    cannot_conclude:
      - bacterial_pneumonia
      - aspiration_excluded
      - organizing_pneumonia_excluded
      - malignancy_excluded
      - acute_exacerbation_excluded
      - simple_ILD_progression
    missing_pieces:
      - prior_CT_review
      - fever_and_infection_context
      - WBC_CRP_and_microbiology
      - aspiration_risk
      - medication_and_steroid_timeline
      - cancer_history
      - follow_up_or_persistence_context
      - MDD_or_urgent_review_if_clinically_worsening
    final_prompt:
      - What evidence is missing before calling this infection rather than OP, aspiration, malignancy, AE, or another superimposed process?
```

---

## 14. Final Page Prompt

Every Superimposed Infection on ILD page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with the prior CT?
3. Is the new process focal, multifocal, diffuse, airway-centered, dependent, nodular, or cavitary?
4. Is there fever, sputum, leukocytosis, positive microbiology, immunosuppression, or exposure context?
5. Is acute exacerbation, OP, edema, hemorrhage, PE, aspiration, drug toxicity, or malignancy still possible?
6. Is microbiology, viral testing, BAL, follow-up imaging, or tissue discussion needed?
7. Is urgent review, infectious disease review, or MDD needed?
8. What do we still not know?
```