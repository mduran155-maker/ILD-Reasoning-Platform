# Drug Toxicity / Treatment-related Lung Injury — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_drug_toxicity_treatment_related_lung_injury_v1
title: Drug Toxicity / Treatment-related Lung Injury — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: superimposed_event_reasoning_map
diagnostic_authority: none
module_version: v0.3
linked_reasoning_maps:
  - superimposed_events_core_blueprint_v1
  - organizing_pneumonia_on_ILD_background_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - malignancy_on_fibrotic_ILD_background_v1
linked_future_modules:
  - vascular_edema_hemorrhage_mimic_panel_v1
  - temporal_comparison_methodology_v1
  - oncology_context_module_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - oncologists
  - rheumatologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users evaluate possible drug toxicity or treatment-related lung injury on a background of known or suspected interstitial lung disease.

It does not diagnose drug-induced ILD, immune checkpoint inhibitor pneumonitis, chemotherapy-related lung injury, radiation pneumonitis, radiation recall pneumonitis, DMARD toxicity, infection, acute exacerbation, edema, organizing pneumonia, malignancy progression, or ILD progression.

It helps users ask:

- Is there a relevant medication or treatment timeline?
- Did the new abnormality appear after a new drug, dose escalation, immunotherapy, chemotherapy, radiation, biologic, DMARD, antibiotic, antiarrhythmic, or antifibrotic change?
- Is the pattern OP-like, NSIP-like, HP-like, DAD/AIP-like, eosinophilic, hemorrhagic, bronchiolitic, radiation-field-related, or mixed?
- Could this instead be infection, acute exacerbation, edema, malignancy progression, OP, aspiration, hemorrhage, PE, or baseline ILD progression?
- Is the patient immunosuppressed?
- What did the prior CT show?
- What clinical, laboratory, microbiologic, oncology, medication, radiation, and temporal data are missing?
- Is urgent review, specialist review, follow-up, BAL, tissue discussion, or MDD needed?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    New lung abnormality after medication or cancer therapy should not automatically be labeled drug toxicity,
    infection, progression, or treatment response without timeline and mimic review.

  platform_rule:
    - do_not_call_every_new_GGO_drug_toxicity
    - do_not_call_every_OP_like_pattern_steroid_responsive_toxicity
    - do_not_call_every_post_therapy_opacity_tumor_progression
    - do_not_call_every_immunotherapy_opacity_immune_checkpoint_inhibitor_pneumonitis
    - do_not_ignore_infection_in_immunosuppressed_or_treated_patients
    - preserve_infection_AE_edema_OP_malignancy_radiation_hemorrhage_and_PE_differential
```

### Teaching Point

The first question is not:

```text
Is this drug toxicity?
```

The better first question is:

```text
Does the imaging pattern and timing fit a treatment-related injury better than infection, progression, edema, OP, AE, hemorrhage, or malignancy?
```

---

## 2. Treatment-related Pattern Families

```yaml
treatment_related_pattern_families:
  OP_like_drug_or_treatment_injury:
    possible_features:
      - peripheral_or_peribronchovascular_consolidation
      - patchy_ground_glass_opacity
      - perilobular_opacity
      - migratory_opacity
      - reverse_halo_context_dependent
    key_mimics:
      - organizing_pneumonia_unrelated_to_drug
      - infection
      - malignancy
      - aspiration
      - radiation_injury
      - CTD_ILD_flare

  NSIP_like_drug_or_treatment_injury:
    possible_features:
      - bilateral_ground_glass_opacity
      - reticulation
      - lower_lung_or_peripheral_distribution_possible
      - relative_homogeneity
      - traction_bronchiectasis_if_fibrotic_or_chronic
    key_mimics:
      - CTD_NSIP
      - fibrotic_ILD_progression
      - edema
      - infection
      - treatment_response_misread

  HP_like_drug_or_treatment_injury:
    possible_features:
      - centrilobular_ground_glass_nodules
      - mosaic_attenuation
      - air_trapping
      - diffuse_or_patchy_GGO
    key_mimics:
      - hypersensitivity_pneumonitis
      - bronchiolitis
      - aspiration
      - infection
      - small_airways_disease

  DAD_AIP_ARDS_like_pattern:
    possible_features:
      - diffuse_bilateral_GGO
      - consolidation
      - dependent_or_nondependent_diffuse_opacity
      - rapid_respiratory_deterioration
      - possible_crazy_paving
    key_mimics:
      - acute_exacerbation
      - severe_infection
      - edema
      - hemorrhage
      - ARDS_from_other_cause

  eosinophilic_or_transient_pulmonary_opacity_pattern:
    possible_features:
      - peripheral_GGO_or_consolidation
      - migratory_opacity
      - possible_blood_or_BAL_eosinophilia_context
    key_mimics:
      - OP
      - infection
      - vasculitis
      - asthma_or_eosinophilic_lung_disease

  hemorrhagic_or_DAH_like_pattern:
    possible_features:
      - diffuse_GGO
      - consolidation
      - crazy_paving_possible
      - hemoptysis_or_anemia_context
    key_mimics:
      - infection
      - acute_exacerbation
      - edema
      - vasculitis
      - anticoagulation_related_bleeding

  radiation_pneumonitis_or_radiation_recall:
    possible_features:
      - opacity_within_radiation_field
      - geographic_or_sharp_margin_field_related_change
      - delayed_recall_after_triggering_drug_possible
      - OP_like_opacity_outside_field_possible_context_dependent
    key_mimics:
      - infection
      - tumor_recurrence
      - OP
      - ICI_pneumonitis
      - lymphangitic_spread

  immune_checkpoint_inhibitor_pneumonitis:
    possible_patterns:
      - OP_like
      - NSIP_like
      - HP_like
      - DAD_AIP_ARDS_like
      - bronchiolitis_like
      - radiation_recall_like
    key_mimics:
      - infection
      - tumor_progression
      - sarcoid_like_reaction
      - edema
      - radiation_pneumonitis
      - acute_exacerbation_of_pre_existing_ILD
```

---

## 3. Core Distinction

```yaml
core_distinction:
  drug_toxicity_or_treatment_related_pathway:
    reasoning_center: new_or_worsening_lung_abnormality_with_plausible_medication_treatment_or_radiation_timeline_and_pattern_compatibility
    supportive_clues:
      - new_drug_or_recent_dose_change
      - immune_checkpoint_inhibitor_context
      - chemotherapy_or_targeted_therapy_context
      - radiation_field_or_radiation_recall_context
      - DMARD_biologic_or_immunosuppressive_context
      - antiarrhythmic_antibiotic_or_other_known_pulmonary_toxicity_context
      - onset_after_exposure
      - pattern_compatible_with_OP_NSIP_HP_DAD_eosinophilic_hemorrhagic_or_radiation_related_injury
      - improvement_after_contextual_drug_or_treatment_change_when_known
    danger_statement: drug_toxicity_should_not_be_diagnosed_without_timeline_mimic_and_infection_review

  infection_pathway:
    reasoning_center: new_opacity_in_treated_or_immunosuppressed_patient_with_clinical_microbiologic_or_airway_infectious_context
    supportive_clues:
      - fever_or_systemic_infectious_context
      - leukocytosis_or_inflammatory_marker_context
      - positive_microbiology_or_viral_testing_when_available
      - immunosuppression_or_neutropenia_context
      - tree_in_bud
      - cavitation
      - focal_lobar_or_airway_centered_opacity
    danger_statement: infection_may_be_absent_fever_or_atypical_in_immunosuppressed_patients_and_must_remain_visible

  malignancy_progression_or_oncology_mimic_pathway:
    reasoning_center: cancer_or_treatment_context_with_new_lung_abnormality_that_may_represent_progression_or_treatment_related_injury
    supportive_clues:
      - known_active_malignancy
      - new_or_growing_nodule_or_mass
      - progressive_lymphadenopathy
      - progression_at_other_tumor_sites
      - lymphangitic_or_metastatic_pattern
      - discordant_or_uncertain_response_status
    danger_statement: treatment_related_pneumonitis_and_progression_can_mimic_each_other_and_require_oncology_context

  acute_exacerbation_or_baseline_ILD_pathway:
    reasoning_center: acute_or_subacute_worsening_on_pre_existing_ILD_background_where_drug_toxicity_may_mimic_or_trigger_AE_like_behavior
    supportive_clues:
      - fibrotic_ILD_background
      - new_bilateral_GGO_or_consolidation
      - acute_respiratory_decline
      - no_stronger_infection_edema_or_treatment_toxicity_context_after_review
    danger_statement: acute_exacerbation_should_not_be_called_before_medication_and_treatment_timeline_review
```

---

## 4. Direct Comparison Matrix

| Feature | More Drug/Treatment-related | More Infection-like | More Malignancy Progression-like | More AE/ILD Progression-like |
|---|---|---|---|---|
| Timeline | After new drug, dose change, ICI, chemo, radiation | After exposure/infectious symptoms | During known tumor progression | Acute/subacute or chronic ILD trajectory |
| Pattern | OP, NSIP, HP, DAD, eosinophilic, hemorrhagic, radiation-field | Focal, airway-centered, cavitary, diffuse viral/opportunistic | Nodule, mass, lymphangitic, progressive nodes | Bilateral GGO for AE, fibrosis growth for progression |
| Fever | Possible drug fever | Supports infection | Not defining | Not defining |
| Immunosuppression | Raises drug and infection complexity | Raises opportunistic infection risk | Cancer therapy context | May trigger AE risk |
| Radiation field | Supports radiation pneumonitis/recall | Not defining | Tumor recurrence possible | Not typical |
| ICI context | Supports ICI pneumonitis or sarcoid-like reaction | Infection still possible | Progression/pseudoprogression possible | AE possible if ILD background |
| Prior CT | Shows temporal relation and newness | Shows acute infection/resolution | Shows tumor growth/progression | Shows fibrosis progression or AE |
| Microbiology | Helps exclude infection | Central | May be needed if mimic | Helps exclude competing cause |
| PET/FDG | Inflammation may be avid | Infection may be avid | Malignancy may be avid | Nonspecific | 

---

## 5. Entry Scenarios

### 5.1 New Bilateral GGO after New Medication

```yaml
scenario_new_bilateral_GGO_after_new_medication:
  problem:
    - ILD_background_or_unknown_baseline
    - new_bilateral_ground_glass_opacity
    - recent_new_medication_or_dose_change

  drug_toxicity_leaning_features:
    - onset_after_new_drug_or_dose_change
    - compatible_OP_NSIP_HP_or_DAD_like_pattern
    - no_stronger_infectious_or_edema_context_after_review
    - improvement_after_drug_context_change_when_known

  infection_leaning_features:
    - fever_or_systemic_infectious_context
    - positive_microbiology_or_viral_testing
    - immunosuppression
    - focal_or_airway_centered_component

  acute_exacerbation_or_edema_mimics:
    - fibrotic_ILD_background_with_acute_decline
    - smooth_septal_thickening_or_effusions
    - cardiac_or_volume_context
    - hemoptysis_or_anemia_context

  missing_pieces:
    - medication_start_date_dose_and_duration
    - prior_CT
    - symptom_time_course
    - infection_labs_and_microbiology
    - cardiac_and_volume_status
    - oxygen_requirement_trend
    - MDD_review

  pitfall:
    - New_bilateral_GGO_after_medication_is_not_specific_for_drug_toxicity
```

### 5.2 Immune Checkpoint Inhibitor Pneumonitis vs Progression vs Infection

```yaml
scenario_ICI_pneumonitis_vs_progression_vs_infection:
  problem:
    - known_malignancy
    - immune_checkpoint_inhibitor_context
    - new_lung_opacity

  ICI_pneumonitis_leaning_features:
    - OP_like_NSIP_like_HP_like_or_DAD_like_pattern
    - onset_after_ICI_exposure
    - other_tumor_sites_stable_or_responding_context
    - no_stronger_infection_or_progression_signal_after_review

  malignancy_progression_leaning_features:
    - new_or_growing_mass_or_nodule
    - progressive_lymphadenopathy
    - progression_at_known_tumor_sites
    - lymphangitic_or_metastatic_pattern
    - tissue_positive_when_sampled

  infection_leaning_features:
    - immunosuppression
    - fever_or_microbiology_support
    - airway_centered_or_cavitary_pattern
    - opportunistic_infection_risk

  missing_pieces:
    - exact_ICI_agent_and_treatment_dates
    - prior_CT_or_PET_CT
    - response_status_of_known_tumor_sites
    - infection_review
    - radiation_history
    - tissue_or_sampling_context_if_needed
    - oncology_MDD_review

  pitfall:
    - ICI_context_requires_pneumonitis_progression_infection_sarcoid_like_reaction_and_radiation_recall_review
```

### 5.3 OP-like Pattern after DMARD / Biologic / Immunosuppression

```yaml
scenario_OP_like_pattern_after_DMARD_or_biologic:
  problem:
    - CTD_ILD_or_inflammatory_disease_background
    - OP_like_opacity
    - DMARD_biologic_or_immunosuppressive_treatment_context

  drug_or_treatment_related_leaning_features:
    - onset_after_new_DMARD_biologic_or_dose_change
    - OP_like_or_NSIP_like_pattern
    - no_stronger_infection_signal_after_review
    - temporal_relation_to_treatment

  CTD_flare_or_secondary_OP_leaning_features:
    - systemic_autoimmune_activity
    - migratory_OP_like_opacity
    - CTD_ILD_background
    - inflammatory_context_independent_of_drug_timing

  infection_leaning_features:
    - immunosuppression
    - fever_or_microbiology
    - tree_in_bud_or_cavitation
    - opportunistic_risk

  missing_pieces:
    - medication_timeline
    - CTD_activity_context
    - infection_review
    - immune_status
    - prior_CT_series
    - rheumatology_or_MDD_review

  pitfall:
    - OP_like_pattern_in_CTD_patient_may_be_drug_toxicity_CTD_flare_infection_or_secondary_OP
```

### 5.4 Radiation Pneumonitis / Radiation Recall vs Infection / Recurrence

```yaml
scenario_radiation_pneumonitis_or_recall:
  problem:
    - prior_radiation_or_radiation_field_context
    - new_opacity_near_or_beyond_field
    - infection_recurrence_OP_or_drug_recall_possible

  radiation_related_leaning_features:
    - opacity_within_radiation_field
    - geographic_or_field_related_margin
    - timing_matches_radiation_pneumonitis_or_recall
    - recall_after_triggering_drug_possible
    - OP_like_opacity_outside_field_context_dependent

  recurrence_or_progression_leaning_features:
    - growing_mass_or_nodule
    - progressive_nodes
    - progression_outside_expected_radiation_context
    - cancer_markers_or_clinical_progression_context

  infection_or_OP_leaning_features:
    - fever_or_microbiology
    - migratory_OP_like_opacity
    - immunosuppression
    - airway_centered_or_lobar_component

  missing_pieces:
    - radiation_field_map
    - radiation_dates_and_dose_context
    - new_drug_or_recall_trigger_timeline
    - prior_CT_or_PET_CT
    - infection_review
    - oncology_review
    - MDD_review

  pitfall:
    - Radiation_field_context_does_not_exclude_infection_recurrence_or_treatment_related_OP
```

### 5.5 DAD / ARDS-like Drug Injury vs Acute Exacerbation

```yaml
scenario_DAD_like_drug_injury_vs_AE:
  problem:
    - fibrotic_ILD_background
    - acute_respiratory_deterioration
    - diffuse_bilateral_GGO_or_consolidation
    - medication_or_treatment_context_possible

  drug_DAD_like_leaning_features:
    - high_risk_drug_or_treatment_timeline
    - onset_after_exposure
    - diffuse_GGO_consolidation_DAD_like_pattern
    - no_stronger_infection_edema_or_AE_context_after_review

  acute_exacerbation_leaning_features:
    - fibrotic_ILD_background
    - acute_or_subacute_worsening
    - new_bilateral_GGO_or_consolidation
    - no_sufficient_alternative_explanation_after_review

  infection_edema_hemorrhage_mimics:
    - fever_or_microbiology
    - smooth_septal_thickening_effusions_volume_context
    - hemoptysis_or_anemia
    - PE_or_shock_context

  missing_pieces:
    - medication_and_treatment_timeline
    - prior_CT
    - infection_review
    - cardiac_volume_status
    - hemoptysis_anemia_context
    - oxygen_requirement_trend
    - urgent_or_MDD_review

  pitfall:
    - DAD_like_drug_injury_and_AE_can_be_indistinguishable_without_timeline_and_exclusion_context
```

---

## 6. Why Not Engine

### Why not drug toxicity / treatment-related lung injury?

```yaml
why_not_drug_toxicity_or_treatment_related_lung_injury:
  - no_relevant_drug_treatment_or_radiation_timeline
  - onset_precedes_exposure
  - infection_microbiology_or_airway_pattern_stronger
  - cardiac_volume_context_explains_findings_better
  - malignancy_progression_or_lymphangitic_pattern_stronger
  - baseline_ILD_progression_supported_by_serial_CT
  - prior_CT_or_treatment_timeline_not_reviewed
```

### Why not infection?

```yaml
why_not_infection:
  - no_infectious_context_after_review
  - microbiology_negative_when_appropriately_obtained_and_context_fits
  - imaging_pattern_and_timing_stronger_for_drug_or_treatment_related_injury
  - no_airway_centered_focal_lobar_tree_in_bud_or_cavitary_pattern
  - improvement_after_drug_context_change_when_known
```

### Why not malignancy progression?

```yaml
why_not_malignancy_progression:
  - OP_NSIP_HP_or_DAD_like_inflammatory_pattern_after_treatment
  - other_tumor_sites_stable_or_responding
  - no_growing_nodule_mass_or_progressive_nodes
  - tissue_or_follow_up_context_not_supportive_when_available
  - infection_or_drug_toxicity_context_stronger
```

### Why not acute exacerbation?

```yaml
why_not_acute_exacerbation:
  - strong_drug_or_treatment_timeline
  - OP_NSIP_HP_or_DAD_like_pattern_after_exposure
  - infection_or_edema_not_reviewed
  - cardiac_volume_or_hemorrhage_context_present
  - no_confirmed_baseline_fibrotic_ILD_context
```

### Why not simple ILD progression?

```yaml
why_not_simple_ILD_progression:
  - acute_or_subacute_time_course
  - new_GGO_or_consolidation
  - medication_treatment_or_radiation_timeline
  - potentially_reversible_airspace_component
  - prior_CT_not_reviewed
  - superimposed_event_differential_not_reviewed
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    medication_and_treatment_timeline:
      reason: Drug toxicity reasoning requires exact start date, dose, dose change, duration, combination therapy, and temporal relationship.

    oncology_treatment_context:
      reason: ICI, chemotherapy, targeted therapy, radiation, and response/progression status change interpretation.

    radiation_field_and_timing:
      reason: Radiation pneumonitis and recall require field, dose, timing, and trigger context.

    prior_CT_or_PET_CT:
      reason: Determines newness, distribution, progression, treatment response, and mimic behavior.

    baseline_ILD_pattern:
      reason: Pre-existing ILD can increase complexity and mimic treatment-related injury.

    infection_review:
      reason: Treated and immunosuppressed patients may have atypical or opportunistic infection.

    immune_status:
      reason: Steroids, biologics, chemotherapy, neutropenia, transplant, CVID, or immunosuppression change infection and toxicity risk.

    cardiac_and_volume_status:
      reason: Edema can mimic pneumonitis or AE with new GGO/septal thickening.

    hemoptysis_anemia_or_DAH_context:
      reason: Hemorrhage can mimic diffuse drug injury, infection, or AE.

    tumor_response_context:
      reason: Progression, pseudoprogression, sarcoid-like reaction, and pneumonitis require oncology-integrated reasoning.

    sampling_or_BAL_context:
      reason: Infection, malignancy, OP, and drug toxicity may require targeted diagnostic discussion when uncertainty remains.

    MDD_review:
      reason: Drug/treatment-related lung injury often requires radiology, pulmonary, oncology, rheumatology, infectious disease, and pharmacy/medication review.
```

---

## 8. Red Flag Panel

```yaml
red_flags:
  treatment_toxicity_red_flags:
    - new_drug_or_recent_dose_change
    - immune_checkpoint_inhibitor_context
    - chemotherapy_or_targeted_therapy_context
    - radiation_field_or_recall_context
    - DMARD_biologic_or_immunosuppressive_context
    - new_bilateral_GGO_or_OP_like_pattern_after_treatment
    - rapid_respiratory_decline_after_exposure

  infection_red_flags:
    - fever_or_sepsis_context
    - immunosuppression_or_neutropenia
    - positive_microbiology_or_viral_testing
    - tree_in_bud
    - cavitation
    - focal_lobar_or_airway_centered_opacity
    - opportunistic_infection_risk

  malignancy_progression_red_flags:
    - new_or_growing_nodule_or_mass
    - progressive_lymphadenopathy
    - lymphangitic_or_metastatic_pattern
    - progression_at_other_tumor_sites
    - suspicious_PET_CT_context
    - tissue_positive_for_malignancy_when_available

  acute_or_life_threatening_red_flags:
    - rapidly_increasing_oxygen_requirement
    - diffuse_bilateral_GGO_or_consolidation
    - hemoptysis_or_anemia
    - severe_immunosuppression
    - shock_or_critical_illness
    - PE_or_pulmonary_hypertension_decompensation_context
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  onset_after_exposure:
    supports:
      - drug_toxicity_or_treatment_related_injury
      - radiation_recall_if_trigger_and_field_context_fit
    caution:
      - temporal_association_alone_does_not_prove_causality

  early_acute_days_to_weeks:
    consider:
      - infection
      - DAD_like_drug_injury
      - acute_exacerbation
      - edema
      - hemorrhage
      - aspiration
      - severe_ICI_pneumonitis

  subacute_weeks_to_months:
    consider:
      - OP_like_drug_injury
      - NSIP_like_pneumonitis
      - ICI_pneumonitis
      - radiation_pneumonitis
      - infection_or_OP
      - malignancy_progression

  chronic_months_to_years:
    consider:
      - chronic_drug_related_fibrosis
      - progressive_fibrotic_ILD
      - radiation_fibrosis
      - malignancy
      - chronic_infection

  improvement_after_drug_context_change:
    possible_explanations:
      - drug_or_treatment_related_injury
      - resolving_infection
      - resolving_OP
      - edema_or_inflammatory_response
    caution:
      - improvement_does_not_prove_drug_causality_without_context

  worsening_despite_drug_change:
    consider:
      - infection
      - malignancy_progression
      - severe_drug_pneumonitis
      - acute_exacerbation
      - edema_PE_or_hemorrhage
      - wrong_initial_assumption
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  urgent_review_high_value_if:
    - rapidly_increasing_oxygen_requirement
    - severe_bilateral_GGO_or_consolidation
    - DAD_ARDS_like_pattern
    - severe_immunosuppression_or_neutropenia
    - hemoptysis_or_DAH_context
    - infection_vs_toxicity_vs_AE_uncertain_in_unstable_patient

  oncology_review_high_value_if:
    - ICI_or_cancer_therapy_context
    - progression_vs_pneumonitis_uncertain
    - new_or_growing_mass_or_nodes
    - radiation_field_or_recall_context
    - treatment_decision_depends_on_differentiation

  infectious_disease_review_high_value_if:
    - immunosuppression_or_opportunistic_infection_possible
    - microbiology_complex_or_negative_despite_high_suspicion
    - TB_NTM_fungal_or_unusual_pathogen_context
    - infection_vs_drug_toxicity_uncertain

  rheumatology_review_high_value_if:
    - CTD_ILD_background
    - DMARD_biologic_or_immunosuppressive_context
    - flare_vs_drug_toxicity_vs_infection_uncertain

  cardiology_or_volume_review_high_value_if:
    - smooth_septal_thickening_effusions_or_volume_context
    - heart_failure_or_renal_failure_context
    - edema_vs_pneumonitis_uncertain

  MDD_strongly_recommended_if:
    - drug_toxicity_vs_infection_vs_AE_uncertain
    - ICI_pneumonitis_vs_progression_uncertain
    - radiation_injury_vs_recurrence_uncertain
    - CTD_flare_vs_DMARD_toxicity_vs_infection_uncertain
    - tissue_BAL_or_treatment_decision_is_being_considered

  sampling_or_BAL_discussion_if:
    - infection_malignancy_or_OP_need_separation
    - immunosuppression_or_opportunistic_infection_context
    - persistent_or_focal_opacity
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Calling pneumonitis from timing alone.
    correction: Temporal association supports suspicion but does not prove drug or treatment causality.

  - title: Ignoring infection in treated patients.
    correction: Immunosuppression and cancer therapy can blunt fever and create opportunistic infection risk.

  - title: Calling all ICI lung opacities immune checkpoint inhibitor pneumonitis.
    correction: Infection, progression, sarcoid-like reaction, edema, radiation recall, and AE remain possible.

  - title: Missing malignancy progression.
    correction: New mass, growing nodule, progressive nodes, or progression elsewhere require oncology review.

  - title: Ignoring radiation field.
    correction: Radiation pneumonitis, radiation recall, OP-like injury, recurrence, and infection require field/timing review.

  - title: Treating OP-like pattern as benign toxicity.
    correction: OP-like morphology can overlap with infection, malignancy, CTD flare, aspiration, and radiation injury.

  - title: Calling diffuse GGO acute exacerbation without medication review.
    correction: Drug toxicity and treatment-related pneumonitis can mimic AE on fibrotic ILD background.

  - title: Treating improvement as proof of drug toxicity.
    correction: Infection, OP, edema, and inflammatory disease can also improve.
```

---

## 12. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - superimposed_events_core_blueprint_v1
    - Fleischner_2021_drug_related_pneumonitis_position_paper
    - drug_induced_ILD_HRCT_pattern_review_2020
    - drug_induced_ILD_review_2022

  supportive_sources:
    - immune_checkpoint_inhibitor_pneumonitis_radiographics_review_2019
    - ICI_pneumonitis_review_2024
    - drug_induced_lung_disease_narrative_review_2024
    - radiation_pneumonitis_and_radiation_recall_sources_pending
    - DMARD_biologic_pneumonitis_sources_pending
    - oncology_progression_vs_pneumonitis_sources_pending

  evidence_notes:
    - Drug-related pneumonitis requires pattern-based CT assessment plus clinical and treatment timeline.
    - Recognized treatment-related patterns include OP-like, NSIP-like, HP-like, DAD/AIP-like, eosinophilic, hemorrhagic, bronchiolitic, and radiation-related patterns.
    - ICI pneumonitis has multiple CT patterns and can mimic infection or tumor progression.
    - Public-ready use requires full source review and expert review.
```

---

## 13. MVP Test Case

```yaml
case_test_drug_toxicity_treatment_related_lung_injury_001:
  input:
    age: 67
    sex: female
    known_background:
      - NSIP_like_CTD_ILD
    new_hrct:
      - new_bilateral_ground_glass_opacity
      - patchy_peripheral_consolidation
      - background_reticulation
      - mild_traction_bronchiectasis
      - no_cavitation_reported
    history:
      recent_medication_change: biologic_started_6_weeks_ago
      immune_checkpoint_inhibitor: no_known
      chemotherapy: no_known
      radiation_history: no_known
      fever: unknown
      cough: present
      oxygen_requirement_change: increased
      CTD_activity_context: unknown
      prior_CT: available_but_not_reviewed
    labs_microbiology:
      WBC: unavailable
      CRP: unavailable
      viral_testing: unavailable
      cultures: unavailable
    oncology_context:
      cancer_history: unknown

  output:
    reasoning_state: drug_toxicity_vs_infection_vs_CTD_flare_OP_gray_zone
    drug_toxicity_support:
      - recent_biologic_started_6_weeks_ago
      - new_bilateral_GGO
      - patchy_peripheral_consolidation
    infection_support:
      - cough_present
      - fever_and_microbiology_unknown
      - immunosuppression_context_possible
    OP_or_flare_support:
      - CTD_ILD_background
      - OP_like_peripheral_consolidation
      - CTD_activity_context_unknown
    cannot_conclude:
      - drug_toxicity
      - infection_excluded
      - CTD_ILD_flare_excluded
      - organizing_pneumonia
      - acute_exacerbation
      - edema_or_hemorrhage_excluded
    missing_pieces:
      - prior_CT_review
      - exact_medication_timeline_dose_and_duration
      - CTD_activity_context
      - infection_labs_and_microbiology
      - immune_status
      - cardiac_volume_context
      - oxygen_requirement_trend
      - MDD_or_rheumatology_pulmonary_review
    final_prompt:
      - What medication, infection, autoimmune activity, temporal, and mimic evidence is missing before calling this drug toxicity?
```

---

## 14. Final Page Prompt

Every Drug Toxicity / Treatment-related Lung Injury page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. What drug, dose, treatment, radiation, or immunotherapy timeline exists?
4. Is the pattern OP-like, NSIP-like, HP-like, DAD/AIP-like, eosinophilic, hemorrhagic, bronchiolitic, radiation-field-related, or mixed?
5. Is infection still possible, especially in immunosuppression or cancer therapy context?
6. Is malignancy progression, sarcoid-like reaction, edema, PE, hemorrhage, OP, CTD flare, aspiration, or acute exacerbation still possible?
7. Is PET/CT or treatment response being interpreted with inflammatory context?
8. Is BAL, microbiology, follow-up, tissue, urgent review, oncology review, rheumatology review, or MDD needed?
9. What do we still not know?
```