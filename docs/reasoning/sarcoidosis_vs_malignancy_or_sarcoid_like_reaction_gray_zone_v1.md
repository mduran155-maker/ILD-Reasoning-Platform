# Sarcoidosis vs Malignancy / Sarcoid-like Reaction — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_v1
title: Sarcoidosis vs Malignancy / Sarcoid-like Reaction — Gray Zone Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
diagnostic_authority: none
linked_patterns:
  - sarcoidosis_pattern_gold_standard_v1
linked_reasoning_maps:
  - granulomatous_ild_reasoning_map_v1
linked_navigation:
  - granulomatous_crosslink_registry_v1
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

This reasoning map helps users compare sarcoidosis-like thoracic disease with malignancy, lymphoma, metastatic disease, and sarcoid-like reaction without forcing premature diagnostic certainty.

It does not diagnose sarcoidosis, malignancy, lymphoma, metastatic disease, immune checkpoint inhibitor-related sarcoid-like reaction, infection, or treatment response.

It helps users ask:

- Is the pattern truly sarcoidosis-like?
- Is there known malignancy or prior cancer treatment?
- Is lymphadenopathy symmetric, asymmetric, necrotic, progressive, or discordant?
- Are there new nodules, masses, or focal lesions?
- Is FDG uptake being overinterpreted?
- Could this be sarcoid-like reaction rather than progression?
- Could this be progression rather than sarcoid-like reaction?
- Is tissue or oncologic review needed?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  sarcoidosis_pathway:
    reasoning_center: compatible_multisystem_granulomatous_context_with_mimics_reviewed
    classic_clues:
      - symmetric_bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_or_mid_lung_predominance
      - compatible_extrapulmonary_sarcoid_context
    danger_statement: sarcoidosis_should_not_be_called_without_reviewing_malignancy_context_when_cancer_signals_exist

  malignancy_pathway:
    reasoning_center: nodal_or_pulmonary_abnormality_in_cancer_or_lymphoma_context
    classic_clues:
      - known_malignancy
      - new_or_growing_nodule_or_mass
      - asymmetric_progressive_lymphadenopathy
      - necrotic_nodes
      - dominant_focal_lesion
      - discordant_clinical_course
      - systemic_B_symptoms_or_oncology_context
    danger_statement: malignancy_progression_should_not_be_missed_by_labeling_findings_as_sarcoidosis

  sarcoid_like_reaction_pathway:
    reasoning_center: noncaseating_granulomatous_reaction_in_malignancy_or_antineoplastic_treatment_context
    classic_context_clues:
      - known_or_recent_malignancy
      - immune_checkpoint_inhibitor_context
      - chemotherapy_or_radiotherapy_context
      - new_symmetric_or_multistation_lymphadenopathy
      - FDG_avid_nodes_or_lesions_that_mimic_progression
      - tissue_showing_granulomatous_reaction_without_malignancy_when_sampled
    danger_statement: sarcoid_like_reaction_can_mimic_progression_but_cannot_be_assumed_without_oncologic_and_tissue_context_when_needed
```

### Teaching Point

Sarcoidosis asks:

```text
Is this compatible granulomatous disease after relevant mimics are considered?
```

Malignancy asks:

```text
Is this new, asymmetric, progressive, focal, or oncologically discordant disease?
```

Sarcoid-like reaction asks:

```text
Could this be granulomatous immune reaction related to malignancy or therapy rather than cancer progression?
```

The key error is to assume that FDG-avid lymphadenopathy is either definitely malignancy or definitely sarcoidosis without context.

---

## 2. Features Supporting Sarcoidosis Pathway

```yaml
features_supporting_sarcoidosis_pathway:
  imaging_distribution:
    - symmetric_bilateral_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - perilymphatic_nodules
    - fissural_nodules
    - peribronchovascular_nodules
    - upper_or_mid_lung_predominance

  clinical_context:
    - compatible_eye_skin_or_lymph_node_features
    - compatible_multisystem_sarcoid_context
    - no_known_malignancy_or_oncology_context_after_review
    - no_new_dominant_mass_or_progressive_asymmetry
    - no_stronger_infection_or_occupational_mimic_context

  pathology_context_when_available:
    - nonnecrotizing_granulomatous_inflammation
    - no_malignancy_in_sampled_site_when_appropriately_sampled
    - alternative_causes_reviewed

  reasoning_weight:
    symmetric_bilateral_hilar_lymphadenopathy: high_when_context_compatible
    perilymphatic_nodules: high
    compatible_extrapulmonary_context: moderate_to_high
    absence_of_malignancy_context_after_review: supportive_but_not_absolute
```

---

## 3. Features Supporting Malignancy / Lymphoma Pathway

```yaml
features_supporting_malignancy_pathway:
  oncology_context:
    - known_active_malignancy
    - prior_malignancy_with_recurrence_risk
    - lymphoma_history_or_suspicion
    - current_or_recent_cancer_treatment
    - tumor_marker_or_clinical_progression_context_when_available

  imaging_features:
    - new_or_growing_nodule
    - new_or_growing_mass
    - asymmetric_progressive_lymphadenopathy
    - necrotic_lymph_nodes
    - dominant_focal_lesion
    - random_nodules_or_metastatic_pattern
    - lymphangitic_carcinomatosis_pattern_when_present
    - pleural_or_bone_or_extrathoracic_metastatic_clues_when_available

  clinical_context:
    - weight_loss_or_B_symptoms_context
    - discordant_course_for_sarcoidosis
    - lack_of_typical_sarcoid_distribution
    - progressive_findings_despite_expected_sarcoid_stability_or_response

  reasoning_weight:
    known_active_malignancy: very_high_contextual_weight
    new_growing_mass_or_nodule: very_high
    asymmetric_progressive_nodes: high
    necrotic_nodes: high
    random_metastatic_pattern: high
```

---

## 4. Features Supporting Sarcoid-like Reaction Pathway

```yaml
features_supporting_sarcoid_like_reaction_pathway:
  oncology_or_treatment_context:
    - known_malignancy
    - recent_or_active_immune_checkpoint_inhibitor_therapy
    - anti_PD_1_or_anti_PD_L1_or_anti_CTLA_4_context
    - chemotherapy_or_radiation_or_targeted_therapy_context
    - new_FDG_avid_nodes_or_lesions_after_treatment

  imaging_context:
    - symmetric_or_multistation_lymphadenopathy
    - mediastinal_or_hilar_nodes_that_mimic_progression
    - pulmonary_nodules_or_granulomatous_pattern_possible
    - imaging_findings_discordant_with_other_markers_of_cancer_response

  pathology_context_when_available:
    - noncaseating_or_nonnecrotizing_granulomatous_reaction
    - no_malignancy_in_sampled_site_when_appropriately_sampled
    - microbiology_or_infection_review_when_relevant

  reasoning_weight:
    immune_checkpoint_inhibitor_context: high
    FDG_avid_nodes_with_other_disease_response: high_gray_zone_weight
    tissue_granulomatous_reaction_without_malignancy: high_when_sampling_context_adequate
```

---

## 5. Direct Comparison Matrix

| Feature | More Sarcoidosis-like | More Malignancy-like | More Sarcoid-like Reaction-like | Reasoning Note |
|---|---|---|---|---|
| Cancer history | Absent or not relevant | Active/recurrent cancer | Known cancer or treatment context | Cancer context changes everything |
| Lymph nodes | Symmetric hilar/mediastinal | Asymmetric/progressive/necrotic | Symmetric or multistation after therapy possible | Nodes alone are not enough |
| PET/FDG uptake | Can be FDG-avid | Can be FDG-avid | Can be FDG-avid | FDG avidity is not specific |
| Pulmonary nodules | Perilymphatic/fissural | Random/metastatic/growing | Variable granulomatous pattern | Distribution and growth matter |
| Dominant mass | Not typical | Strong concern | Not typical unless sampled/reaction context | Mass needs malignancy review |
| Treatment timing | Not defining | Progression possible | ICI/therapy-related timing possible | Timeline is high-yield |
| Tissue | Nonnecrotizing granulomas support in context | Malignant cells confirm sampled disease | Granulomas without malignancy may support SLR | Sampling target matters |
| Course | Stable/regressing possible | Progressive possible | May appear during response or after therapy | Prior imaging is essential |

---

## 6. Gray Zone Scenarios

### 6.1 FDG-avid Mediastinal Nodes in a Cancer Patient

```yaml
scenario_FDG_avid_nodes_in_cancer_patient:
  problem:
    - known_malignancy
    - FDG_avid_hilar_or_mediastinal_nodes
    - sarcoidosis_or_progression_or_sarcoid_like_reaction_possible

  sarcoidosis_or_sarcoid_like_leaning_features:
    - symmetric_bilateral_hilar_or_mediastinal_nodes
    - multistation_nodal_pattern
    - no_progression_elsewhere
    - granulomatous_tissue_without_malignancy_when_sampled
    - therapy_related_timing_possible

  malignancy_leaning_features:
    - asymmetric_progressive_nodes
    - known_nodal_drainage_pattern_matches_cancer
    - concurrent_progression_elsewhere
    - necrotic_nodes
    - rising_tumor_markers_or_clinical_progression_when_available

  missing_pieces:
    - oncology_history
    - treatment_timeline
    - prior_PET_CT_or_CT
    - distribution_of_FDG_avid_disease
    - tissue_or_sampling_context_if_needed
    - oncology_MDD_review

  pitfall:
    - Do_not_treat_FDG_avid_nodes_as_specific_for_malignancy_or_sarcoidosis_without_context
```

### 6.2 Immune Checkpoint Inhibitor Context

```yaml
scenario_immune_checkpoint_inhibitor_sarcoid_like_reaction:
  problem:
    - patient_on_or_after_immune_checkpoint_inhibitor
    - new_lymphadenopathy_or_granulomatous_pattern
    - progression_vs_sarcoid_like_reaction_uncertain

  sarcoid_like_reaction_leaning_features:
    - anti_PD_1_PD_L1_or_CTLA_4_context
    - symmetric_hilar_or_mediastinal_nodes
    - granulomatous_tissue_when_sampled
    - other_known_tumor_sites_stable_or_responding
    - compatible_timing_after_therapy

  malignancy_progression_leaning_features:
    - new_or_growing_mass
    - progression_at_multiple_known_tumor_sites
    - asymmetric_or_necrotic_nodes
    - clinical_deterioration_consistent_with_cancer
    - tissue_positive_for_malignancy_when_sampled

  missing_pieces:
    - exact_immunotherapy_agent_and_timeline
    - prior_CT_or_PET_CT
    - response_status_of_known_tumor_sites
    - tissue_sampling_target_if_needed
    - oncology_review
    - infection_review_if_granulomatous

  pitfall:
    - Sarcoid_like_reaction_can_mimic_progression_but_should_not_be_assumed_without_oncology_context
```

### 6.3 New Nodule or Mass in Known Sarcoidosis

```yaml
scenario_new_nodule_or_mass_in_known_sarcoidosis:
  problem:
    - known_or_suspected_sarcoidosis
    - new_or_growing_nodule_or_mass

  sarcoidosis_leaning_features:
    - multiple_perilymphatic_nodules
    - stable_typical_sarcoid_background
    - no_dominant_new_growth_pattern
    - prior_similar_inflammatory_fluctuation

  malignancy_or_infection_leaning_features:
    - solitary_or_dominant_growing_nodule
    - mass_like_lesion
    - cavitation_or_necrosis
    - smoking_or_cancer_risk_context
    - discordant_growth_compared_with_sarcoid_background

  missing_pieces:
    - prior_CT
    - growth_rate
    - morphology_review
    - cancer_risk_context
    - infection_review_if_cavitary_or_consolidative
    - tissue_or_sampling_discussion_if_needed

  pitfall:
    - Do_not_hide_a_new_focal_lesion_inside_a_known_sarcoidosis_label
```

### 6.4 Asymmetric or Progressive Lymphadenopathy

```yaml
scenario_asymmetric_or_progressive_lymphadenopathy:
  problem:
    - lymphadenopathy_present
    - asymmetry_or_progression_reported

  sarcoidosis_leaning_features:
    - symmetric_hilar_mediastinal_pattern
    - stable_nodes_over_time
    - typical_perilymphatic_nodules
    - compatible_multisystem_sarcoid_context

  malignancy_or_lymphoma_leaning_features:
    - asymmetric_progression
    - dominant_node
    - necrotic_node
    - B_symptoms
    - cancer_history
    - lymphoma_risk_context
    - discordant_PET_or_CT_progression

  missing_pieces:
    - prior_CT_or_PET_CT
    - nodal_growth_pattern
    - systemic_symptoms
    - cancer_history
    - tissue_or_sampling_context_if_needed
    - oncology_or_hematology_review

  pitfall:
    - Asymmetric_progressive_nodes_should_not_be_dismissed_as_sarcoidosis_without_review
```

---

## 7. Why Not Engine

### Why not sarcoidosis?

```yaml
why_not_sarcoidosis:
  - known_active_malignancy
  - prior_malignancy_with_recurrence_risk
  - asymmetric_progressive_lymphadenopathy
  - necrotic_nodes
  - new_or_growing_nodule_or_mass
  - random_nodules_or_metastatic_pattern
  - lymphoma_or_B_symptom_context
  - FDG_avid_findings_without_context
  - discordant_clinical_course
```

### Why not malignancy progression?

```yaml
why_not_malignancy_progression:
  - symmetric_bilateral_hilar_or_mediastinal_nodes
  - no_progression_elsewhere
  - other_tumor_sites_stable_or_responding
  - recent_immune_checkpoint_inhibitor_or_antineoplastic_therapy_context
  - granulomatous_reaction_without_malignancy_when_appropriately_sampled
  - compatible_sarcoid_like_distribution
```

### Why not sarcoid-like reaction?

```yaml
why_not_sarcoid_like_reaction:
  - no_malignancy_or_treatment_context
  - progressive_known_tumor_sites
  - malignant_cells_in_sampled_site
  - asymmetric_necrotic_or_mass_like_progression
  - infection_or_lymphoma_explains_findings_better
  - insufficient_sampling_or_follow_up_context
```

### Why not stop at PET positivity?

```yaml
why_not_stop_at_PET_positivity:
  - FDG_uptake_is_not_specific
  - sarcoidosis_can_be_FDG_avid
  - malignancy_can_be_FDG_avid
  - sarcoid_like_reaction_can_be_FDG_avid
  - distribution_timeline_and_tissue_context_matter
```

---

## 8. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    cancer_history:
      reason: Known, prior, or suspected malignancy changes interpretation of lymphadenopathy and nodules.

    treatment_timeline:
      reason: Immune checkpoint inhibitors and other cancer therapies can be associated with sarcoid-like reactions.

    prior_CT_or_PET_CT:
      reason: Growth, stability, symmetry, and response/progression pattern are central.

    distribution_of_FDG_avid_disease:
      reason: FDG uptake is nonspecific; distribution and concordance with known cancer pattern matter.

    nodal_characterization:
      reason: Symmetric, asymmetric, necrotic, dominant, or progressive nodes imply different pathways.

    nodule_or_mass_growth_pattern:
      reason: New or growing focal lesions require malignancy and infection review.

    tissue_or_sampling_context:
      reason: Granulomatous reaction, malignancy, and sampling error must be interpreted with target and adequacy.

    oncology_or_hematology_review:
      reason: Cancer progression, lymphoma, and sarcoid-like reaction often require oncology-integrated review.

    infection_review:
      reason: Infection can mimic both malignancy and sarcoidosis-like granulomatous disease.
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  behavior_supporting_sarcoidosis_or_sarcoid_like_reaction:
    clues:
      - symmetric_nodal_appearance
      - stable_or_regressing_nodes
      - granulomatous_findings_without_malignancy_when_sampled
      - emergence_after_immune_checkpoint_inhibitor_or_antineoplastic_therapy
      - discordance_with_other_tumor_sites_that_are_responding
    caution:
      - apparent_response_or_stability_does_not_exclude_malignancy_without_context

  behavior_supporting_malignancy_progression:
    clues:
      - new_or_growing_mass
      - progressive_asymmetric_nodes
      - progression_at_known_tumor_sites
      - new_random_nodules_or_metastatic_pattern
      - worsening_clinical_or_tumor_marker_context_when_available
    caution:
      - sarcoid_like_reaction_can_mimic_progression_in_some_treatment_contexts

  unexpectedly_fast_change:
    consider:
      - malignancy_progression
      - infection
      - immune_related_sarcoid_like_reaction
      - drug_toxicity
      - inflammatory_sarcoidosis_activity
      - pulmonary_embolism_or_other_superimposed_event
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  oncology_MDD_strongly_recommended_if:
    - known_malignancy_with_new_FDG_avid_nodes
    - immune_checkpoint_inhibitor_context_with_new_nodes_or_nodules
    - sarcoid_like_reaction_vs_progression_uncertainty
    - new_or_growing_nodule_or_mass
    - asymmetric_or_necrotic_lymphadenopathy
    - tissue_result_and_oncology_context_conflict
    - treatment_decision_depends_on_distinguishing_progression_from_reaction

  hematology_review_high_value_if:
    - lymphoma_context_possible
    - progressive_lymphadenopathy
    - B_symptoms
    - splenomegaly_or_cytopenias
    - dominant_node_or_mass

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_imaging_oncology_review
    - result_would_change_management
    - accessible_node_or_lesion_exists
    - sampling_target_can_address_key_uncertainty
    - patient_risk_is_acceptable
    - MDD_supports_need

  follow_up_imaging_context_high_value_if:
    - findings_indeterminate
    - other_tumor_sites_are_stable_or_responding
    - biopsy_not_immediately_feasible
    - clinical_risk_allows_contextual_follow_up
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Calling FDG-avid nodes metastatic disease by default.
    correction: Sarcoidosis and sarcoid-like reactions can be FDG-avid; distribution, timing, and tissue context matter.

  - title: Calling FDG-avid nodes sarcoid-like reaction by default.
    correction: Cancer progression and lymphoma must remain visible, especially with asymmetry, necrosis, growth, or progression elsewhere.

  - title: Ignoring immune checkpoint inhibitor context.
    correction: ICI-associated sarcoid-like reactions are recognized and can mimic progression.

  - title: Hiding a new mass under a sarcoidosis label.
    correction: New or growing focal lesions require malignancy and infection review.

  - title: Ignoring sampling target.
    correction: A sampled benign granulomatous node may not explain a separate growing mass.

  - title: Forgetting lymphoma.
    correction: Progressive lymphadenopathy, B symptoms, splenomegaly, or cytopenias require hematology/oncology review.

  - title: Treating tissue granulomas as the whole answer.
    correction: Granulomatous reaction must be interpreted with oncologic, infectious, and sampling context.
```

---

## 12. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT

  supportive_sources:
    - SARCOID_LIKE_REACTION_MALIGNANCY_REVIEW_2023
    - SARCOID_LIKE_REACTION_CHECKPOINT_INHIBITOR_REVIEW_2024
    - FDG_PET_CT_SARCOID_REACTION_REVIEW
    - SARCOID_LIKE_REACTION_ONCOLOGY_CASE_SERIES

  evidence_notes:
    - Sarcoidosis diagnosis requires exclusion of alternative granulomatous causes.
    - Sarcoid-like reaction can occur in malignancy and treatment contexts.
    - Immune checkpoint inhibitor-associated sarcoid-like reaction is increasingly recognized.
    - FDG avidity is not specific for malignancy, sarcoidosis, or sarcoid-like reaction.
    - Oncology-integrated review is essential when cancer context exists.
```

---

## 13. MVP Test Case

```yaml
case_test_sarcoidosis_vs_malignancy_slr_001:
  input:
    age: 62
    sex: female
    hrct_or_pet_ct:
      - FDG_avid_mediastinal_lymphadenopathy
      - bilateral_hilar_lymphadenopathy
      - small_pulmonary_nodules
      - no_dominant_mass_reported
    history:
      known_malignancy: breast_cancer_history
      active_treatment: immune_checkpoint_inhibitor_unknown
      treatment_timeline: unavailable
      prior_CT_or_PET_CT: unavailable
      systemic_B_symptoms: unknown
      extrapulmonary_sarcoid_features: unknown
      infection_review: unknown
    tissue:
      sampled_node_result: unavailable
    oncology_context:
      other_tumor_sites_response_status: unavailable

  output:
    reasoning_state: sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone
    sarcoidosis_or_sarcoid_like_support:
      - bilateral_hilar_lymphadenopathy
      - possible_multistation_nodal_pattern
      - small_pulmonary_nodules
    malignancy_support:
      - known_malignancy_history
      - FDG_avid_lymphadenopathy
      - prior_imaging_unavailable
      - treatment_timeline_unavailable
    cannot_conclude:
      - sarcoidosis
      - malignancy_progression
      - sarcoid_like_reaction
      - infection_excluded
    missing_pieces:
      - cancer_history_detail
      - treatment_timeline
      - immune_checkpoint_inhibitor_context
      - prior_CT_or_PET_CT
      - distribution_of_FDG_avid_disease
      - other_tumor_sites_response_status
      - tissue_or_sampling_context_if_needed
      - oncology_MDD_review
    final_prompt:
      - What oncologic and temporal evidence is missing before calling this sarcoidosis, progression, or sarcoid-like reaction?
```

---

## 14. Final Page Prompt

Every Sarcoidosis vs Malignancy / Sarcoid-like Reaction gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Is there known or prior malignancy?
2. Is the patient receiving or recently exposed to immunotherapy, chemotherapy, radiation, or targeted therapy?
3. Are lymph nodes symmetric, asymmetric, necrotic, progressive, or discordant?
4. Are there new or growing nodules, masses, or focal lesions?
5. Is FDG uptake being overinterpreted without distribution and timeline context?
6. Are other tumor sites responding, stable, or progressing?
7. Is tissue needed, available, or potentially misleading because of sampling target?
8. Has infection or lymphoma been considered?
9. What do we still not know?
```