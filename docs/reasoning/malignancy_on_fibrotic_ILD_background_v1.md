# Malignancy on Fibrotic ILD Background — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_malignancy_on_fibrotic_ILD_background_v1
title: Malignancy on Fibrotic ILD Background — Reasoning Map
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
  - fibrotic_ild_triage_map_v1
linked_future_modules:
  - temporal_comparison_methodology_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - oncology_context_module_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - oncologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users evaluate suspected malignancy or focal neoplastic change on a background of known or suspected fibrotic interstitial lung disease.

It does not diagnose lung cancer, lymphoma, metastasis, infection, organizing pneumonia, scar carcinoma, drug toxicity, sarcoid-like reaction, pulmonary infarct, or ILD progression.

It helps users ask:

- Is this truly a new or growing focal lesion?
- Is the abnormality a nodule, mass, focal consolidation, lymphadenopathy, or scar-like change?
- Could fibrosis be hiding malignancy?
- Could apparent malignancy actually be infection, OP, infarct, drug toxicity, or inflammatory change?
- Is there prior CT or PET/CT comparison?
- Is the lesion persistent, growing, resolving, cavitary, solid, subsolid, or mass-like?
- Is tissue, follow-up imaging, PET/CT context, oncology review, or MDD needed?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    A new or changing focal abnormality on a fibrotic ILD background should not be hidden inside the baseline fibrosis label.

  platform_rule:
    - do_not_call_every_new_nodule_scar_or_fibrosis
    - do_not_call_every_persistent_consolidation_infection_or_OP
    - do_not_call_every_mass_like_fibrotic_distortion_benign_without_temporal_review
    - do_not_diagnose_malignancy_from_CT_or_PET_alone
    - preserve_infection_OP_infarct_drug_toxicity_sarcoid_like_reaction_and_malignancy_differential
```

### Teaching Point

The first question is not:

```text
Is this just the fibrotic ILD?
```

The better first question is:

```text
What focal process may be emerging within or adjacent to the fibrotic lung?
```

---

## 2. Malignancy Pattern Families on Fibrotic ILD Background

```yaml
malignancy_pattern_families:
  new_or_growing_solid_nodule:
    possible_features:
      - new_solid_nodule
      - interval_growth
      - irregular_or_spiculated_margin
      - lesion_near_fibrotic_area
      - upper_or_lower_lobe_context_dependent
    key_mimics:
      - infection
      - inflammatory_nodule
      - rheumatoid_nodule
      - organizing_pneumonia
      - scar_or_fibrotic_focus

  subsolid_or_part_solid_nodule:
    possible_features:
      - ground_glass_nodule
      - part_solid_component
      - slow_growth
      - persistent_subsolid_opacity
    key_mimics:
      - focal_inflammation
      - OP
      - infection
      - fibrosis_related_ground_glass
      - technical_or_inspiratory_difference

  persistent_focal_consolidation:
    possible_features:
      - persistent_consolidation
      - mass_like_consolidation
      - air_bronchograms_possible
      - asymmetric_or_nonresolving_opacity
    key_mimics:
      - organizing_pneumonia
      - infection
      - aspiration
      - atelectasis
      - pulmonary_infarct
      - drug_or_radiation_injury

  mass_like_fibrotic_distortion:
    possible_features:
      - focal_mass_like_distortion
      - architectural_distortion_with_growth
      - scar_adjacent_nodule
      - focal_volume_loss_or_retraction
    key_mimics:
      - progressive_fibrosis
      - rounded_atelectasis
      - post_infectious_scar
      - pneumoconiosis_or_PMF
      - fibrotic_sarcoidosis_complication

  lymphadenopathy_or_metastatic_context:
    possible_features:
      - new_or_progressive_lymphadenopathy
      - asymmetric_nodes
      - necrotic_nodes
      - FDG_avid_nodes_context_dependent
      - extrathoracic_malignancy_context
    key_mimics:
      - infection
      - sarcoidosis
      - sarcoid_like_reaction
      - GLILD
      - lymphoma

  pleural_or_chest_wall_context:
    possible_features:
      - pleural_nodularity
      - unilateral_pleural_effusion
      - chest_wall_invasion_context
      - focal_pleural_mass
    key_mimics:
      - infection
      - asbestos_related_disease
      - inflammatory_pleuritis
      - heart_failure_or_volume_context
```

---

## 3. Core Distinction

```yaml
core_distinction:
  malignancy_pathway:
    reasoning_center: focal_persistent_or_growing_abnormality_on_fibrotic_background_with_morphologic_temporal_or_oncology_risk_context
    supportive_clues:
      - new_or_growing_nodule
      - persistent_focal_consolidation
      - mass_like_opacity
      - irregular_spiculated_or_asymmetric_morphology
      - suspicious_or_progressive_lymphadenopathy
      - known_cancer_history
      - smoking_or_other_risk_context
      - lesion_growth_on_prior_CT
      - FDG_avid_context_when_interpreted_with_timeline_and_distribution
    danger_statement: malignancy_should_not_be_missed_because_the_background_lung_is_already_fibrotic

  infection_pathway:
    reasoning_center: focal_or_multifocal_abnormality_with_clinical_microbiologic_airway_or_cavitary_infectious_context
    supportive_clues:
      - fever_or_systemic_infectious_context
      - leukocytosis_or_inflammatory_marker_context
      - productive_cough_or_sputum
      - tree_in_bud_or_airway_centered_pattern
      - cavitation_or_abscess_context
      - microbiology_support_when_available
      - improvement_with_appropriate_infectious_context
    danger_statement: infection_can_mimic_malignancy_but_should_not_hide_persistent_or_growing_focal_lesions

  organizing_pneumonia_or_inflammatory_pathway:
    reasoning_center: OP_like_or_inflammatory_focal_opacity_with_migratory_temporal_or_trigger_context
    supportive_clues:
      - peripheral_or_peribronchovascular_consolidation
      - perilobular_or_OP_like_pattern
      - migratory_or_waxing_waning_opacities
      - CTD_drug_radiation_or_post_infectious_context
      - improvement_of_airspace_component_when_context_fits
    danger_statement: OP_like_morphology_should_not_exclude_malignancy_when_opacity_is_focal_persistent_or_growing

  fibrosis_or_scar_pathway:
    reasoning_center: stable_structural_fibrotic_distortion_without_independent_focal_growth_or_mass_behavior
    supportive_clues:
      - stable_fibrotic_focus_over_time
      - no_new_focal_soft_tissue_component
      - no_interval_growth
      - morphology_matches_known_fibrotic_distribution
      - no_suspicious_lymphadenopathy_or_clinical_cancer_context
    danger_statement: scar_or_fibrosis_should_not_be_used_as_a_default_explanation_without_prior_CT_review
```

---

## 4. Direct Comparison Matrix

| Feature | More Malignancy-like | More Infection-like | More OP/Inflammatory-like | More Fibrosis/Scar-like |
|---|---|---|---|---|
| Temporal behavior | Growth or persistence | Acute/subacute, may improve | Migratory/waxing-waning | Stable over time |
| Morphology | Nodule, mass, spiculation, focal consolidation | Lobar/airway-centered/cavitary | Peripheral/perilobular/migratory | Architectural distortion without growth |
| Distribution | Focal or asymmetric | Focal, airway-centered, multifocal | Peripheral/peribronchovascular | Matches fibrotic background |
| Nodes | Progressive/asymmetric/necrotic | Reactive or infectious possible | Usually not dominant | Stable if pre-existing |
| PET/FDG | May be avid | May be avid | May be avid | May be variable | 
| Prior CT | Shows growth/new lesion | Shows acute onset/resolution | Shows migration/resolution | Shows stability |
| Clinical context | Cancer risk/history | Fever/microbiology | CTD/drug/post-infectious | Known chronic fibrosis |
| Sampling concern | Target lesion matters | Microbiology matters | OP may need exclusion of malignancy | Sampling may be unnecessary if stable |

---

## 5. Entry Scenarios

### 5.1 New Nodule within Fibrotic Lung

```yaml
scenario_new_nodule_within_fibrotic_lung:
  problem:
    - background_fibrotic_ILD
    - new_or_newly_visible_nodule

  malignancy_leaning_features:
    - interval_growth
    - irregular_or_spiculated_margin
    - solid_or_part_solid_component
    - smoking_or_cancer_risk_context
    - associated_progressive_lymphadenopathy
    - lesion_arising_in_or_adjacent_to_fibrotic_area

  infection_or_inflammatory_leaning_features:
    - acute_appearance_with_fever
    - surrounding_inflammatory_opacity
    - tree_in_bud_or_airway_centered_context
    - immunosuppression_or_opportunistic_context
    - short_interval_resolution_when_available

  missing_pieces:
    - prior_CT_review
    - growth_rate
    - solid_vs_subsolid_characterization
    - cancer_risk_context
    - infection_review
    - PET_CT_context_if_available
    - follow_up_or_sampling_discussion
    - MDD_review

  pitfall:
    - Do_not_call_a_new_nodule_fibrotic_scar_without_temporal_review
```

### 5.2 Persistent Focal Consolidation on ILD Background

```yaml
scenario_persistent_focal_consolidation:
  problem:
    - focal_consolidation_on_fibrotic_background
    - persistence_or_growth_uncertain

  malignancy_leaning_features:
    - persistent_or_growing_focal_consolidation
    - mass_like_consolidation
    - known_cancer_or_smoking_risk_context
    - suspicious_nodes
    - no_expected_resolution

  OP_or_inflammatory_leaning_features:
    - peripheral_or_peribronchovascular_OP_like_pattern
    - migratory_behavior
    - CTD_drug_radiation_or_post_infectious_context
    - improvement_of_airspace_component_when_known

  infection_leaning_features:
    - fever_or_microbiologic_support
    - acute_lobar_pattern
    - aspiration_risk
    - immunosuppression
    - improvement_with_infectious_context

  missing_pieces:
    - prior_CT_or_follow_up_CT
    - persistence_duration
    - infection_labs_and_microbiology
    - OP_trigger_context
    - cancer_history_and_risk
    - tissue_or_sampling_context_if_needed
    - MDD_review

  pitfall:
    - Persistent_focal_consolidation_should_not_be_assumed_to_be_OP_or_infection_without_malignancy_review
```

### 5.3 Mass-like Fibrotic Distortion

```yaml
scenario_mass_like_fibrotic_distortion:
  problem:
    - fibrotic_ILD_background
    - focal_mass_like_distortion_or_scar_like_opacity

  fibrosis_or_scar_leaning_features:
    - stability_over_serial_CT
    - morphology_matches_known_fibrotic_distribution
    - no_new_soft_tissue_component
    - no_progressive_nodes
    - no_suspicious_clinical_context

  malignancy_leaning_features:
    - increasing_focal_soft_tissue_component
    - change_in_contour_or_density
    - progressive_growth
    - new_associated_lymphadenopathy
    - PET_CT_context_concerning_when_integrated
    - symptoms_or_risk_context

  competing_mimics:
    - rounded_atelectasis
    - pneumoconiosis_or_progressive_massive_fibrosis
    - chronic_infection
    - fibrotic_sarcoidosis_complication
    - post_radiation_change

  missing_pieces:
    - serial_CT_comparison
    - lesion_contour_and_density_change
    - cancer_risk_context
    - occupational_exposure_history
    - PET_CT_context_if_available
    - sampling_feasibility_and_risk
    - MDD_review

  pitfall:
    - Mass_like_fibrotic_distortion_requires_growth_and_soft_tissue_component_review
```

### 5.4 New or Progressive Lymphadenopathy

```yaml
scenario_new_or_progressive_lymphadenopathy:
  problem:
    - fibrotic_ILD_background
    - lymphadenopathy_present_or_progressive

  malignancy_or_lymphoma_leaning_features:
    - asymmetric_nodes
    - progressive_nodes
    - necrotic_nodes
    - known_malignancy
    - B_symptoms_or_lymphoma_context
    - FDG_avid_nodes_with_concerning_distribution

  benign_or_inflammatory_leaning_features:
    - stable_mild_nodes_in_chronic_ILD_context
    - infection_context
    - sarcoidosis_or_granulomatous_context
    - sarcoid_like_reaction_context_after_cancer_therapy

  missing_pieces:
    - prior_CT_or_PET_CT
    - nodal_growth_pattern
    - cancer_history
    - infection_review
    - granulomatous_disease_context
    - tissue_sampling_target_if_needed
    - oncology_or_MDD_review

  pitfall:
    - FDG_avid_or_enlarged_nodes_are_not_specific_but_progressive_asymmetry_requires_review
```

### 5.5 Known Cancer with New Fibrotic Lung Opacity

```yaml
scenario_known_cancer_new_fibrotic_lung_opacity:
  problem:
    - known_or_prior_malignancy
    - new_opacity_on_fibrotic_ILD_background

  malignancy_progression_leaning_features:
    - new_or_growing_mass
    - random_nodules_or_metastatic_pattern
    - progressive_nodes
    - progression_at_other_tumor_sites
    - tissue_positive_when_sampled

  treatment_related_or_inflammatory_leaning_features:
    - immune_checkpoint_inhibitor_context
    - chemotherapy_or_radiation_timeline
    - OP_like_or_pneumonitis_pattern
    - other_tumor_sites_stable_or_responding
    - sarcoid_like_reaction_context

  infection_leaning_features:
    - immunosuppression
    - fever_or_microbiology
    - airway_centered_or_cavitary_pattern
    - opportunistic_infection_risk

  missing_pieces:
    - oncology_history
    - treatment_timeline
    - prior_CT_or_PET_CT
    - response_status_of_known_tumor_sites
    - infection_review
    - tissue_or_sampling_context_if_needed
    - oncology_MDD_review

  pitfall:
    - Cancer_context_requires_progression_treatment_reaction_infection_and_sarcoid_like_reaction_review
```

---

## 6. Why Not Engine

### Why not malignancy?

```yaml
why_not_malignancy:
  - lesion_resolves_on_short_interval_follow_up
  - migratory_OP_like_behavior
  - microbiology_or_infection_context_stronger
  - morphology_matches_stable_fibrotic_scar_over_time
  - no_growth_on_serial_CT
  - no_suspicious_nodes_or_oncology_context_after_review
  - inflammatory_or_treatment_related_context_stronger
```

### Why not infection?

```yaml
why_not_infection:
  - persistent_or_growing_focal_opacity
  - no_infectious_symptoms_after_review
  - microbiology_negative_when_appropriately_obtained_and_context_fits
  - spiculated_or_mass_like_morphology
  - progressive_nodes_or_cancer_context
  - failure_to_resolve_when_expected
```

### Why not OP / inflammatory opacity?

```yaml
why_not_OP_or_inflammatory_opacity:
  - persistent_focal_growth
  - mass_like_or_spiculated_morphology
  - suspicious_nodes
  - known_cancer_progression_context
  - no_migratory_or_inflammatory_temporal_behavior
  - tissue_or_follow_up_context_not_supportive_when_available
```

### Why not fibrosis / scar?

```yaml
why_not_fibrosis_or_scar:
  - new_or_growing_focal_soft_tissue_component
  - new_nodule_or_mass
  - change_in_contour_density_or_margin
  - persistent_focal_consolidation
  - progressive_lymphadenopathy
  - prior_CT_not_reviewed
```

### Why not rely on PET alone?

```yaml
why_not_rely_on_PET_alone:
  - FDG_uptake_is_not_specific
  - infection_can_be_FDG_avid
  - OP_or_inflammation_can_be_FDG_avid
  - sarcoidosis_or_sarcoid_like_reaction_can_be_FDG_avid
  - fibrotic_inflammation_may_confound_interpretation
  - distribution_timeline_and_sampling_target_matter
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether the lesion is new, stable, growing, resolving, or technical.

    growth_rate:
      reason: Interval growth or persistence strongly changes malignancy reasoning.

    lesion_characterization:
      reason: Solid, subsolid, part-solid, cavitary, spiculated, mass-like, or consolidation-like morphology changes the differential.

    focal_vs_diffuse_context:
      reason: Focal processes require different reasoning from diffuse superimposed events.

    cancer_history_and_risk:
      reason: Smoking, prior cancer, occupational exposure, family history, and treatment history affect interpretation.

    PET_CT_context:
      reason: FDG uptake requires distribution, timeline, and inflammatory/infectious context.

    infection_review:
      reason: Infection may mimic malignancy, especially with cavitation or consolidation.

    OP_or_inflammatory_context:
      reason: OP-like patterns may mimic focal malignancy and require temporal review.

    treatment_timeline:
      reason: ICI, chemotherapy, radiation, or drug-related lung injury may mimic progression.

    tissue_sampling_target:
      reason: Sampling must target the lesion causing uncertainty; benign tissue elsewhere may not explain a growing focal lesion.

    MDD_or_oncology_review:
      reason: Malignancy on fibrotic background often requires thoracic radiology, pulmonary, oncology, pathology, and sometimes infectious disease integration.
```

---

## 8. Red Flag Panel

```yaml
red_flags:
  malignancy_red_flags:
    - new_or_growing_nodule
    - persistent_focal_consolidation
    - mass_like_opacity
    - spiculated_or_irregular_margin
    - new_soft_tissue_component_within_fibrosis
    - progressive_or_asymmetric_lymphadenopathy
    - known_or_prior_malignancy
    - smoking_or_high_risk_context
    - unexplained_weight_loss_or_B_symptoms_context

  mimic_red_flags:
    - fever_or_microbiology_support
    - tree_in_bud
    - cavitation
    - OP_like_migratory_behavior
    - immune_checkpoint_inhibitor_or_cancer_therapy_context
    - radiation_field_context
    - PE_or_infarct_like_peripheral_opacity

  technical_red_flags:
    - prior_CT_unavailable
    - different_slice_thickness_or_reconstruction
    - poor_inspiration_or_motion
    - contrast_vs_noncontrast_difference
    - lesion_visibility_limited_by_fibrotic_distortion
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  new_lesion:
    consider:
      - malignancy
      - infection
      - OP
      - inflammatory_nodule
      - infarct
      - treatment_related_lung_injury
    caution:
      - new_visibility_may_reflect_technical_difference_or_prior_obscuration

  interval_growth:
    consider:
      - malignancy
      - chronic_infection
      - inflammatory_mass_like_process
      - progressive_fibrotic_distortion_with_new_soft_tissue_component
    caution:
      - growth_requires_comparable_imaging_and_precise_measurement

  stability:
    supports:
      - scar_or_fibrotic_focus
      - benign_chronic_abnormality_context_dependent
    caution:
      - stability_duration_and_lesion_type_matter

  resolution_or_improvement:
    supports:
      - infection
      - OP
      - edema_or_inflammatory_process
      - treatment_related_reversible_change
    caution:
      - improvement_does_not_exclude_underlying_malignancy_if_focal_residual_persists

  persistence:
    consider:
      - malignancy
      - OP
      - chronic_infection
      - atelectasis
      - radiation_or_drug_injury
    caution:
      - persistent_focal_opacity_requires_reassessment
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  oncology_review_high_value_if:
    - new_or_growing_nodule_or_mass
    - persistent_focal_consolidation
    - known_or_prior_malignancy
    - suspicious_or_progressive_lymphadenopathy
    - PET_CT_or_CT_context_uncertain

  MDD_strongly_recommended_if:
    - malignancy_vs_OP_vs_infection_uncertain
    - lesion_arises_within_dense_fibrosis
    - sampling_risk_high_due_to_fibrotic_lung
    - PET_CT_findings_conflict_with_CT_or_clinical_context
    - treatment_decision_depends_on_distinguishing_malignancy_from_mimic

  infectious_disease_review_high_value_if:
    - cavitary_or_nodular_infection_possible
    - immunosuppression_or_opportunistic_context
    - microbiology_complex_or_pending
    - chronic_infection_vs_malignancy_uncertain

  tissue_or_sampling_discussion_if:
    - persistent_or_growing_focal_abnormality
    - result_would_change_management
    - lesion_is_accessible
    - sampling_target_can_answer_key_question
    - patient_risk_is_acceptable
    - MDD_supports_need

  follow_up_imaging_context_high_value_if:
    - lesion_indeterminate
    - infection_or_OP_possible
    - immediate_sampling_risk_high
    - short_interval_change_would_clarify_reasoning
    - clinical_risk_allows_follow_up_strategy
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Hiding a new nodule inside fibrosis.
    correction: A new or growing nodule requires temporal and malignancy review.

  - title: Calling persistent focal consolidation infection or OP indefinitely.
    correction: Persistence or growth should trigger malignancy and chronic infection review.

  - title: Relying on PET positivity alone.
    correction: FDG uptake is not specific; infection, OP, sarcoidosis, sarcoid-like reaction, and malignancy may all be FDG-avid.

  - title: Sampling the wrong target.
    correction: A benign sample from one site may not explain a separate growing lesion.

  - title: Ignoring treatment timeline.
    correction: Immunotherapy, chemotherapy, radiation, and drug toxicity can mimic progression or malignancy.

  - title: Assuming stable fibrosis explains new soft tissue.
    correction: Fibrosis may be stable while malignancy develops within or adjacent to it.

  - title: Ignoring technical comparability.
    correction: Apparent growth or new visibility may be affected by slice thickness, reconstruction, inspiration, or contrast.
```

---

## 12. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - superimposed_events_core_blueprint_v1
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - Fleischner_2017_pulmonary_nodule_guidelines_context
    - ILD_lung_cancer_risk_review_sources

  supportive_sources:
    - lung_cancer_in_IPF_review_2025
    - ILD_and_lung_cancer_risk_cohort_2025
    - lung_cancer_on_fibrotic_background_review_sources_pending
    - focal_opacity_on_fibrotic_ILD_review_sources_pending
    - PET_CT_fibrotic_lung_and_inflammation_context_sources_pending
    - OP_vs_malignancy_sources_pending

  evidence_notes:
    - ILD and IPF are associated with increased lung cancer risk in contemporary literature.
    - Fibrotic background may obscure or mimic focal malignancy.
    - Pulmonary nodule guidelines provide useful context but do not replace ILD-specific reasoning.
    - PET/CT findings require timeline, distribution, infection, inflammatory, and oncology context.
    - Public-ready use requires full source review and expert review.
```

---

## 13. MVP Test Case

```yaml
case_test_malignancy_on_fibrotic_ILD_001:
  input:
    age: 72
    sex: male
    known_background:
      - fibrotic_ILD
      - UIP_like_pattern
    new_hrct:
      - new_left_lower_lobe_solid_nodule
      - background_honeycombing
      - traction_bronchiectasis
      - no_new_diffuse_GGO_reported
      - no_cavitation_reported
    history:
      smoking_history: unknown
      cancer_history: unknown
      fever: unknown
      cough: chronic
      weight_loss: unknown
      medication_timeline: unknown
      prior_CT: available_but_not_reviewed
    labs_microbiology:
      infection_testing: unavailable
    oncology_context:
      PET_CT: unavailable
      tissue: unavailable

  output:
    reasoning_state: new_focal_nodule_on_fibrotic_ILD_background
    malignancy_support:
      - new_solid_nodule
      - fibrotic_ILD_background
      - prior_CT_available_but_not_reviewed
    infection_or_inflammatory_support:
      - fever_unknown
      - infection_testing_unavailable
      - medication_timeline_unknown
    cannot_conclude:
      - lung_cancer
      - infection_excluded
      - OP_or_inflammatory_nodule_excluded
      - scar_or_fibrosis_only
      - metastatic_disease_excluded
    missing_pieces:
      - prior_CT_review
      - growth_rate
      - nodule_size_morphology_and_density
      - smoking_and_cancer_risk_context
      - infection_review
      - PET_CT_context_if_relevant
      - tissue_or_sampling_discussion_if_needed
      - oncology_or_MDD_review
    final_prompt:
      - What temporal, morphologic, infectious, and oncology evidence is missing before calling this malignancy, infection, OP, or scar?
```

---

## 14. Final Page Prompt

Every Malignancy on Fibrotic ILD Background page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. Is the abnormality a new nodule, growing nodule, mass, persistent focal consolidation, lymphadenopathy, or scar-like distortion?
4. Is the lesion solid, subsolid, part-solid, cavitary, spiculated, mass-like, or consolidation-like?
5. Is infection, OP, infarct, drug toxicity, sarcoid-like reaction, or fibrosis/scar still possible?
6. Is there known cancer history, smoking risk, treatment timeline, or suspicious lymphadenopathy?
7. Is PET/CT being interpreted with timeline and inflammatory context?
8. Is follow-up, tissue sampling, oncology review, or MDD needed?
9. What do we still not know?
```