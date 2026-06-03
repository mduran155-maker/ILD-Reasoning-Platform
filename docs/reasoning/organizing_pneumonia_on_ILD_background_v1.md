# Organizing Pneumonia on ILD Background — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_organizing_pneumonia_on_ILD_background_v1
title: Organizing Pneumonia on ILD Background — Reasoning Map
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
  - acute_exacerbation_vs_infection_vs_edema_v1
  - fibrotic_ild_triage_map_v1
linked_future_modules:
  - drug_toxicity_treatment_related_lung_injury_v1
  - malignancy_on_fibrotic_ILD_background_v1
  - temporal_comparison_methodology_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - rheumatologists
  - oncologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users evaluate organizing pneumonia-like opacity superimposed on a background of known or suspected interstitial lung disease.

It does not diagnose cryptogenic organizing pneumonia, secondary organizing pneumonia, infection, malignancy, CTD-ILD flare, drug toxicity, radiation injury, aspiration, acute exacerbation, or treatment response.

It helps users ask:

- Is this truly organizing pneumonia-like?
- Is OP primary/cryptogenic, secondary, treatment-related, infection-related, CTD-related, aspiration-related, or malignancy-adjacent?
- Could this instead be infection, edema, drug toxicity, malignancy, pulmonary infarct, hemorrhage, or acute exacerbation?
- Is the opacity migratory, peripheral, perilobular, reverse-halo-like, focal, multifocal, or persistent?
- What did the prior CT show?
- What clinical, medication, oncology, immune, microbiologic, or temporal data are missing?
- Is follow-up, sampling, urgent review, or MDD needed?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    Organizing pneumonia-like opacity on an ILD background should not automatically be treated
    as infection, ILD progression, treatment response, or benign inflammation.

  platform_rule:
    - do_not_call_every_new_peripheral_consolidation_OP
    - do_not_call_every_migratory_opacity_infection
    - do_not_call_every_OP_like_pattern_steroid_responsive_without_context
    - do_not_hide_malignancy_inside_OP_like_persistent_focal_consolidation
    - preserve_infection_drug_toxicity_CTD_flare_malignancy_aspiration_radiation_and_AE_differential
```

### Teaching Point

The first question is not:

```text
Is this OP?
```

The better first question is:

```text
What injury, trigger, or mimic could be producing an OP-like pattern on top of the ILD background?
```

---

## 2. OP Pattern Families on ILD Background

```yaml
OP_pattern_families:
  peripheral_or_peribronchovascular_consolidation:
    possible_features:
      - patchy_consolidation
      - peripheral_distribution
      - peribronchovascular_distribution
      - air_bronchograms
      - associated_ground_glass_opacity
    key_mimics:
      - infection
      - malignancy
      - aspiration
      - pulmonary_infarct
      - drug_toxicity
      - radiation_injury

  perilobular_or_arcade_like_opacity:
    possible_features:
      - perilobular_opacity
      - curvilinear_or_arcade_like_consolidation
      - subpleural_or_peribronchovascular_bias
    key_mimics:
      - CTD_ILD_flare
      - drug_toxicity
      - infection
      - edema_or_hemorrhage_context_dependent

  reverse_halo_or_atoll_like_pattern:
    possible_features:
      - central_ground_glass_opacity
      - surrounding_ring_like_consolidation
    key_mimics:
      - fungal_infection
      - TB
      - infarct
      - vasculitis
      - malignancy
      - OP

  migratory_OP_like_opacity:
    possible_features:
      - opacities_resolve_in_one_region_and_appear_elsewhere
      - waxing_waning_consolidation
      - inflammatory_or_treatment_related_behavior
    key_mimics:
      - recurrent_aspiration
      - infection
      - eosinophilic_pneumonia
      - vasculitis
      - drug_reaction

  focal_persistent_OP_like_consolidation:
    possible_features:
      - localized_consolidation
      - mass_like_opacity
      - persistent_or_slowly_changing_focus
    key_mimics:
      - adenocarcinoma
      - lymphoma
      - chronic_infection
      - atelectasis
      - pulmonary_infarct
```

---

## 3. Core Distinction

```yaml
core_distinction:
  organizing_pneumonia_pathway:
    reasoning_center: OP_like_airspace_or_perilobular_opacity_with_inflammatory_temporal_behavior_and_contextual_trigger_review
    supportive_clues:
      - peripheral_or_peribronchovascular_consolidation
      - perilobular_opacity
      - migratory_or_waxing_waning_opacities
      - reverse_halo_pattern_context_dependent
      - CTD_or_autoimmune_context
      - drug_or_radiation_or_treatment_context
      - post_infectious_or_secondary_OP_context
      - improvement_of_airspace_component_when_context_fits
    danger_statement: OP_like_pattern_should_not_be_called_final_without_reviewing_infection_malignancy_drug_toxicity_aspiration_and_AE

  infection_pathway:
    reasoning_center: new_OP_like_opacity_with_fever_microbiology_airway_lobar_or_opportunistic_infectious_context
    supportive_clues:
      - fever_or_systemic_infectious_context
      - leukocytosis_or_inflammatory_marker_context
      - productive_cough_or_sputum
      - positive_microbiology_when_available
      - airway_centered_opacity
      - tree_in_bud
      - cavitation
      - immunosuppression_or_opportunistic_risk
    danger_statement: infection_can_mimic_OP_and_should_not_be_excluded_by_OP_like_morphology_alone

  malignancy_or_persistent_focal_opacity_pathway:
    reasoning_center: focal_persistent_or_mass_like_opacity_on_fibrotic_or_inflammatory_background
    supportive_clues:
      - persistent_focal_consolidation
      - growing_nodule_or_mass
      - asymmetric_mass_like_opacity
      - cancer_history
      - lymphadenopathy_or_metastatic_context
      - failure_to_resolve_when_expected
    danger_statement: OP_like_consolidation_should_not_hide_lung_cancer_lymphoma_or_metastatic_disease

  drug_toxicity_or_treatment_related_pathway:
    reasoning_center: OP_like_or_inflammatory_lung_abnormality_after_new_medication_cancer_therapy_or_radiation_context
    supportive_clues:
      - new_drug_or_dose_change
      - immune_checkpoint_inhibitor_context
      - chemotherapy_or_targeted_therapy_context
      - radiation_field_or_timing_context
      - temporal_relation_to_treatment
      - improvement_after_drug_context_change_when_known
    danger_statement: OP_like_pattern_can_be_drug_or_treatment_related_and_requires_timeline_review
```

---

## 4. Direct Comparison Matrix

| Feature | More OP-like | More Infection-like | More Malignancy-like | More Drug/Treatment-related |
|---|---|---|---|---|
| Distribution | Peripheral/peribronchovascular, perilobular, migratory | Focal, lobar, airway-centered, tree-in-bud | Focal persistent, mass-like, growing | Multifocal, OP/NSIP/DAD-like, treatment-timeline linked |
| Migration | Supports OP-like inflammatory behavior | Can occur but less typical | Less typical | Possible with drug/treatment reactions |
| Fever/microbiology | Not defining | Supports infection | May be absent | May be drug fever/inflammatory |
| Persistence | OP can persist | Unresolved infection possible | High concern if focal/growing | Depends on ongoing exposure/treatment |
| Reverse halo | OP possible | Fungal/TB possible | Malignancy/infarct possible | Possible context-dependent |
| CTD context | Secondary OP possible | Infection risk may coexist | Not central | Immunosuppressive meds may matter |
| Oncology context | Treatment-related OP possible | Opportunistic infection possible | Progression/malignancy possible | ICI/chemo/radiation pneumonitis possible |
| Prior CT | Shows migration, newness, persistence | Shows acute infection pattern | Shows growth/persistence | Shows relation to therapy timeline |

---

## 5. Entry Scenarios

### 5.1 New Peripheral Consolidation on Fibrotic ILD Background

```yaml
scenario_new_peripheral_consolidation:
  problem:
    - background_fibrotic_ILD
    - new_peripheral_or_subpleural_consolidation
    - OP_infection_malignancy_and_drug_toxicity_possible

  OP_leaning_features:
    - peripheral_or_peribronchovascular_consolidation
    - perilobular_opacity
    - migratory_or_waxing_waning_behavior
    - CTD_or_autoimmune_context
    - post_infectious_or_secondary_OP_context

  infection_leaning_features:
    - fever
    - productive_cough
    - leukocytosis_or_inflammatory_marker_context
    - microbiologic_support
    - focal_lobar_or_airway_centered_pattern

  malignancy_leaning_features:
    - persistent_focal_opacity
    - mass_like_morphology
    - growth_on_prior_CT
    - known_cancer_history
    - associated_suspicious_nodes

  missing_pieces:
    - prior_CT
    - clinical_time_course
    - infection_labs_and_microbiology
    - cancer_history
    - medication_and_treatment_timeline
    - follow_up_or_persistence_context
    - MDD_review

  pitfall:
    - Do_not_call_new_peripheral_consolidation_OP_without_infection_and_malignancy_review
```

### 5.2 Migratory Consolidation on CTD-ILD Background

```yaml
scenario_migratory_consolidation_CTD_ILD:
  problem:
    - CTD_ILD_or_NSIP_like_background
    - waxing_waning_or_migratory_consolidation
    - OP_flare_infection_drug_toxicity_possible

  OP_or_inflammatory_flare_leaning_features:
    - migratory_opacities
    - perilobular_or_peripheral_pattern
    - CTD_context
    - inflammatory_symptoms_or_flare_context
    - response_of_airspace_component_when_known

  infection_leaning_features:
    - fever_or_sepsis_context
    - immunosuppression
    - positive_microbiology
    - focal_airway_centered_pattern
    - opportunistic_infection_risk

  drug_toxicity_leaning_features:
    - new_DMARD_biologic_or_immunosuppressive_medication
    - chemotherapy_or_immune_checkpoint_inhibitor_context
    - medication_timeline_matches_onset
    - multi_pattern_drug_pneumonitis_context

  missing_pieces:
    - CTD_activity_context
    - medication_timeline
    - infection_review
    - immune_status
    - prior_CT_series
    - MDD_or_rheumatology_review

  pitfall:
    - Migratory_opacity_supports_OP_like_behavior_but_does_not_exclude_infection_or_drug_toxicity
```

### 5.3 Reverse Halo / Atoll-like Opacity

```yaml
scenario_reverse_halo_or_atoll_like_opacity:
  problem:
    - reverse_halo_or_ring_like_consolidation
    - OP_infection_infarct_vasculitis_malignancy_possible

  OP_leaning_features:
    - compatible_OP_pattern_context
    - other_migratory_or_peripheral_consolidations
    - CTD_or_drug_or_post_infectious_context
    - no_high_risk_infection_or_vascular_context_after_review

  infection_leaning_features:
    - immunosuppression
    - fungal_or_TB_context
    - fever_or_microbiology_support
    - cavitation_or_nodular_component

  vascular_or_malignancy_leaning_features:
    - PE_risk_or_infarct_context
    - hemoptysis
    - known_malignancy
    - persistent_or_growing_focal_lesion

  missing_pieces:
    - immune_status
    - fungal_TB_microbiology_context
    - PE_or_vascular_context
    - cancer_history
    - prior_CT
    - tissue_or_sampling_context_if_needed

  pitfall:
    - Reverse_halo_is_not_specific_for_OP
```

### 5.4 Persistent Focal OP-like Consolidation

```yaml
scenario_persistent_focal_OP_like_consolidation:
  problem:
    - focal_consolidation_or_mass_like_opacity
    - OP_like_morphology_possible
    - persistence_or_growth_uncertain

  OP_leaning_features:
    - prior_migratory_OP_like_behavior
    - peripheral_or_peribronchovascular_pattern
    - inflammatory_context
    - partial_response_when_context_fits

  malignancy_leaning_features:
    - persistent_or_growing_focal_opacity
    - mass_like_shape
    - associated_suspicious_nodes
    - cancer_or_smoking_risk_context
    - no_expected_resolution

  infection_leaning_features:
    - unresolved_infection_context
    - immunosuppression
    - cavitation_or_airway_centered_component
    - microbiology_pending_or_positive

  missing_pieces:
    - prior_CT_or_follow_up_CT
    - growth_or_persistence_context
    - cancer_history_and_risk
    - infection_review
    - tissue_or_sampling_context_if_needed
    - MDD_review

  pitfall:
    - Persistent_focal_OP_like_opacity_should_not_be_assumed_benign_inflammation
```

### 5.5 OP-like Pattern after Drug, ICI, Chemotherapy, or Radiation

```yaml
scenario_OP_like_pattern_after_treatment:
  problem:
    - OP_like_opacity_on_ILD_background
    - new_or_recent_medication_or_cancer_therapy_possible

  treatment_related_OP_leaning_features:
    - immune_checkpoint_inhibitor_context
    - chemotherapy_or_targeted_therapy_context
    - radiation_field_or_timing_context
    - new_DMARD_biologic_or_immunosuppressive_medication
    - temporal_relationship_to_treatment
    - multifocal_inflammatory_pattern

  infection_leaning_features:
    - immunosuppression
    - fever_or_microbiology_support
    - airway_centered_or_cavitary_pattern
    - opportunistic_risk

  malignancy_leaning_features:
    - known_active_cancer
    - progression_elsewhere
    - persistent_focal_mass_like_opacity
    - suspicious_nodes

  missing_pieces:
    - medication_and_treatment_timeline
    - oncology_context
    - radiation_field_map_if_relevant
    - infection_review
    - prior_CT
    - MDD_or_oncology_review

  pitfall:
    - OP_like_pattern_after_treatment_requires_both_toxicity_and_progression_review
```

---

## 6. Why Not Engine

### Why not OP?

```yaml
why_not_OP:
  - fever_or_microbiologic_support_for_infection
  - airway_centered_tree_in_bud_pattern
  - cavitation
  - persistent_or_growing_focal_mass_like_opacity
  - known_malignancy_with_progression_context
  - cardiac_or_volume_edema_context_stronger
  - PE_or_infarct_context
  - drug_toxicity_pattern_broader_than_OP
  - prior_CT_not_reviewed
```

### Why not infection?

```yaml
why_not_infection:
  - migratory_peripheral_or_perilobular_pattern
  - no_infectious_context_after_review
  - microbiology_negative_when_appropriately_obtained_and_context_fits
  - CTD_flare_or_secondary_OP_context_stronger
  - treatment_related_OP_context_stronger
  - persistent_pattern_without_infectious_support
```

### Why not malignancy?

```yaml
why_not_malignancy:
  - migratory_behavior
  - multifocal_OP_like_pattern_with_inflammatory_context
  - no_growth_or_mass_like_persistence_on_prior_CT
  - no_suspicious_nodes_or_cancer_context_after_review
  - tissue_or_follow_up_context_not_supportive_when_available
```

### Why not drug/treatment-related lung injury?

```yaml
why_not_drug_treatment_related_lung_injury:
  - no_relevant_medication_or_treatment_timeline
  - onset_precedes_drug_exposure
  - infection_or_malignancy_context_stronger
  - OP_like_pattern_follows_CTD_flare_or_post_infectious_context_better
```

### Why not simple ILD progression?

```yaml
why_not_simple_ILD_progression:
  - new_airspace_opacity
  - migratory_or_waxing_waning_consolidation
  - potentially_reversible_GGO_or_consolidation
  - acute_or_subacute_time_course
  - prior_CT_not_reviewed
  - superimposed_event_differential_not_reviewed
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether opacity is new, migratory, persistent, resolving, growing, or technical.

    temporal_behavior:
      reason: Migration, waxing/waning change, persistence, or growth changes the differential.

    infection_review:
      reason: OP-like consolidation can mimic or follow infection; microbiology and clinical context matter.

    medication_and_treatment_timeline:
      reason: Drug toxicity, ICI pneumonitis, chemotherapy injury, radiation injury, and DMARD-related lung injury can present with OP-like patterns.

    CTD_or_autoimmune_activity_context:
      reason: OP may occur with CTD-ILD flare or inflammatory disease activity.

    cancer_history:
      reason: Persistent focal opacity or mass-like consolidation may represent malignancy.

    aspiration_risk:
      reason: Aspiration can mimic OP or infection with dependent/recurrent opacities.

    radiation_field_and_timing:
      reason: Radiation-related lung injury may produce OP-like or field-related opacities.

    immune_status:
      reason: Immunosuppression changes infection and drug toxicity risk.

    follow_up_or_sampling_context:
      reason: Persistence, growth, or discordant clinical course may require follow-up or tissue discussion.

    MDD_review:
      reason: OP on ILD background often requires radiology, pulmonary, rheumatology, oncology, infectious disease, and sometimes pathology integration.
```

---

## 8. Red Flag Panel

```yaml
red_flags:
  infection_red_flags:
    - fever_or_sepsis_context
    - immunosuppression
    - positive_microbiology
    - tree_in_bud
    - cavitation
    - focal_lobar_airway_centered_opacity

  malignancy_red_flags:
    - persistent_focal_consolidation
    - mass_like_opacity
    - growth_on_prior_CT
    - known_cancer_history
    - suspicious_or_asymmetric_nodes
    - failure_to_resolve_when_expected

  drug_treatment_red_flags:
    - immune_checkpoint_inhibitor_context
    - chemotherapy_or_targeted_therapy_context
    - radiation_timing_or_field_context
    - new_DMARD_biologic_or_immunosuppressive_medication
    - multiple_HRCT_patterns_after_treatment

  vascular_or_hemorrhage_red_flags:
    - PE_risk
    - infarct_like_peripheral_opacity
    - hemoptysis
    - anemia
    - anticoagulation_context

  baseline_ILD_red_flags:
    - acute_or_subacute_change_too_fast_for_fibrosis
    - new_airspace_opacity_not_structural_fibrosis
    - prior_CT_unavailable
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  migratory_behavior:
    supports:
      - OP_like_inflammatory_behavior
      - recurrent_aspiration_context_dependent
      - eosinophilic_or_drug_reaction_context_dependent
    caution:
      - migration_does_not_exclude_infection_or_drug_toxicity

  rapid_appearance_days_to_weeks:
    consider:
      - infection
      - OP
      - drug_toxicity
      - aspiration
      - edema
      - hemorrhage
      - acute_exacerbation

  persistence_weeks_to_months:
    consider:
      - OP
      - unresolved_infection
      - malignancy
      - radiation_or_drug_related_injury
      - chronic_aspiration
      - atelectasis

  growth_or_mass_like_evolution:
    consider:
      - malignancy
      - lymphoma
      - chronic_infection
      - inflammatory_pseudotumor_context_dependent
      - OP_mimic_but_requires_caution

  improvement:
    possible_explanations:
      - resolving_OP_like_inflammation
      - resolving_infection
      - resolving_edema
      - exposure_or_drug_context_change
      - treatment_response
    caution:
      - improvement_of_airspace_opacity_does_not_prove_fibrosis_reversal
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  urgent_review_high_value_if:
    - rapidly_increasing_oxygen_requirement
    - severe_diffuse_opacity
    - hemoptysis_or_DAH_context
    - severe_immunosuppression
    - suspected_PE_or_infarct
    - unstable_patient_with_OP_infection_AE_overlap

  infectious_disease_review_high_value_if:
    - immunosuppression_or_opportunistic_infection_possible
    - fever_or_microbiologic_context
    - cavitation_or_tree_in_bud
    - TB_NTM_or_fungal_context
    - OP_vs_infection_uncertain

  oncology_review_high_value_if:
    - persistent_focal_OP_like_opacity
    - known_malignancy
    - suspicious_nodes
    - mass_like_growth
    - cancer_therapy_timeline

  rheumatology_review_high_value_if:
    - CTD_ILD_background
    - autoimmune_flare_context
    - new_OP_like_opacity_with_systemic_activity
    - medication_or_DMARD_context

  MDD_strongly_recommended_if:
    - OP_vs_infection_vs_malignancy_uncertain
    - OP_like_pattern_after_cancer_therapy
    - OP_like_pattern_on_fibrotic_background_with_progression_question
    - persistence_or_growth_conflicts_with_expected_behavior
    - tissue_or_sampling_decision_is_being_considered

  tissue_or_sampling_discussion_if:
    - persistent_or_growing_focal_opacity
    - malignancy_or_chronic_infection_must_be_excluded
    - diagnosis_uncertain_after_clinical_imaging_review
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Calling OP from morphology alone.
    correction: OP-like imaging requires trigger, mimic, time-course, infection, malignancy, and treatment-context review.

  - title: Calling OP infection because it consolidates.
    correction: Peripheral or migratory consolidation may be OP-like, but infection still requires clinical and microbiologic context.

  - title: Missing malignancy in OP-like consolidation.
    correction: Persistent focal or mass-like opacity requires malignancy review.

  - title: Ignoring drug or cancer treatment timeline.
    correction: Drug-related pneumonitis and ICI/radiation-related injury can present with OP-like patterns.

  - title: Treating improvement as proof of diagnosis.
    correction: Infection, edema, OP, drug toxicity, and inflammatory flare can all improve.

  - title: Ignoring aspiration.
    correction: Dependent or recurrent consolidations may be aspiration-related, not OP.

  - title: Treating OP as separate from the baseline ILD.
    correction: OP-like opacity can coexist with CTD-ILD, HP, drug toxicity, infection, and fibrotic ILD.
```

---

## 12. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - superimposed_events_core_blueprint_v1
    - CRYPTOGENIC_ORGANIZING_PNEUMONIA_CURRENT_UNDERSTANDING_ERS_REVIEW_2021
    - ALGORITHMIC_APPROACH_TO_ORGANIZING_PNEUMONIA_2022

  supportive_sources:
    - drug_induced_ILD_HRCT_pattern_review_sources
    - Fleischner_drug_related_pneumonitis_position_paper
    - CTD_ILD_OP_overlap_sources_pending
    - malignancy_mimic_OP_sources_pending
    - infection_vs_OP_sources_pending

  evidence_notes:
    - OP may be cryptogenic or secondary to infection, CTD, drugs, HP, aspiration, malignancy, radiation, or treatment context.
    - OP-like imaging is not diagnostic by itself.
    - Drug-related pneumonitis can show OP-like patterns and requires treatment timeline.
    - Persistent focal OP-like opacity requires malignancy and chronic infection review.
```

---

## 13. MVP Test Case

```yaml
case_test_OP_on_ILD_background_001:
  input:
    age: 63
    sex: female
    known_background:
      - CTD_ILD
      - NSIP_like_pattern
    new_hrct:
      - new_peripheral_consolidation
      - patchy_ground_glass_opacity
      - background_reticulation
      - mild_traction_bronchiectasis
      - no_cavitation_reported
    history:
      symptom_time_course: subacute_3_weeks
      fever: unknown
      cough: present
      medication_timeline: recent_DMARD_change_unknown
      infection_testing: unavailable
      cancer_history: unknown
      aspiration_risk: unknown
      prior_CT: available_but_not_reviewed
    labs_microbiology:
      WBC: unavailable
      CRP: unavailable
      cultures: unavailable
      viral_testing: unavailable

  output:
    reasoning_state: OP_like_opacity_on_ILD_background
    OP_support:
      - new_peripheral_consolidation
      - CTD_ILD_background
      - subacute_time_course
    infection_support:
      - cough_present
      - fever_and_microbiology_unknown
      - infection_testing_unavailable
    drug_toxicity_support:
      - recent_DMARD_change_unknown
      - medication_timeline_incomplete
    cannot_conclude:
      - organizing_pneumonia
      - infection_excluded
      - drug_toxicity_excluded
      - malignancy_excluded
      - aspiration_excluded
      - simple_ILD_progression
    missing_pieces:
      - prior_CT_review
      - infection_labs_and_microbiology
      - medication_and_DMARD_timeline
      - CTD_activity_context
      - cancer_history
      - aspiration_risk
      - follow_up_or_persistence_context
      - MDD_review
    final_prompt:
      - What evidence is missing before calling this organizing pneumonia rather than infection, drug toxicity, malignancy, aspiration, or ILD progression?
```

---

## 14. Final Page Prompt

Every Organizing Pneumonia on ILD Background page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. Is the opacity peripheral, peribronchovascular, perilobular, reverse-halo-like, migratory, focal, or mass-like?
4. Is infection still possible?
5. Is drug toxicity, ICI pneumonitis, chemotherapy injury, radiation injury, CTD flare, aspiration, malignancy, edema, PE, hemorrhage, or acute exacerbation still possible?
6. Is the opacity persistent, growing, resolving, or migratory?
7. What medication, treatment, oncology, immune, microbiologic, aspiration, or temporal data are missing?
8. Is follow-up, sampling, urgent review, or MDD needed?
9. What do we still not know?
```