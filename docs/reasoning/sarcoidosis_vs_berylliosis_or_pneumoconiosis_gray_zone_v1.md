# Sarcoidosis vs Berylliosis / Pneumoconiosis — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_sarcoidosis_vs_berylliosis_or_pneumoconiosis_v1
title: Sarcoidosis vs Berylliosis / Pneumoconiosis — Gray Zone Reasoning Map
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
  - occupational medicine clinicians
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare sarcoidosis-like thoracic disease with berylliosis, silicosis, and other pneumoconiosis-related granulomatous or nodular occupational lung diseases.

It does not diagnose sarcoidosis, chronic beryllium disease, silicosis, coal workers’ pneumoconiosis, mixed dust pneumoconiosis, malignancy, infection, or other occupational lung disease.

It helps users ask:

- Is the pattern truly sarcoidosis-like?
- Has occupational exposure history been taken carefully?
- Is there beryllium, silica, coal, metal, stone, construction, mining, aerospace, ceramic, dental, or industrial exposure?
- Are nodules perilymphatic, centrilobular, random, or pneumoconiotic?
- Are there calcified lymph nodes or eggshell calcification?
- Is BeLPT or occupational testing relevant?
- Are infection, malignancy, and HP still visible?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  sarcoidosis_pathway:
    reasoning_center: nonoccupational_or_unclear_multisystem_granulomatous_disease_in_compatible_context
    classic_clues:
      - bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - fissural_nodules
      - upper_or_mid_lung_predominance
      - compatible_extrapulmonary_context
    danger_statement: sarcoidosis_should_not_be_called_before_relevant_occupational_granulomatous_mimics_are_reviewed

  berylliosis_pathway:
    reasoning_center: sarcoidosis_phenocopy_related_to_beryllium_exposure_and_beryllium_sensitization_context
    classic_context_clues:
      - beryllium_exposure
      - aerospace_or_defense_industry_context
      - nuclear_or_electronics_or_metal_industry_context
      - dental_alloy_or_ceramic_context
      - positive_or_abnormal_BeLPT_when_available
    danger_statement: chronic_beryllium_disease_can_mimic_sarcoidosis_and_requires_exposure_and_BeLPT_context

  pneumoconiosis_pathway:
    reasoning_center: dust_related_lung_disease_with_nodular_or_fibrotic_pattern_and_occupational_exposure_context
    classic_context_clues:
      - silica_exposure
      - mining_or_quarry_or_sandblasting_context
      - construction_or_stone_cutting_context
      - coal_dust_exposure
      - metal_or_mixed_dust_exposure
      - occupational_latency
    imaging_clues:
      - upper_lung_small_nodules
      - calcified_lymph_nodes
      - eggshell_calcification_when_present
      - progressive_massive_fibrosis_when_advanced
    danger_statement: pneumoconiosis_can_mimic_sarcoidosis_and_requires_occupational_exposure_review
```

### Teaching Point

Sarcoidosis asks:

```text
Is this a compatible noninfectious granulomatous disease pattern after relevant mimics are considered?
```

Berylliosis / pneumoconiosis asks:

```text
Is this sarcoidosis-like disease actually occupational or dust-related?
```

The key error is to document “no known exposure” without performing a high-quality occupational history.

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
    - no_identified_occupational_exposure_after_high_quality_review
    - no_stronger_infectious_or_malignancy_context

  pathology_context_when_available:
    - nonnecrotizing_granulomatous_inflammation
    - compatible_clinical_radiologic_context
    - alternative_causes_reviewed

  reasoning_weight:
    symmetric_bilateral_hilar_lymphadenopathy: high_when_context_compatible
    perilymphatic_nodules: high
    compatible_extrapulmonary_context: moderate_to_high
    absence_of_occupational_exposure_after_high_quality_review: supportive_but_not_absolute
```

---

## 3. Features Supporting Berylliosis Pathway

```yaml
features_supporting_berylliosis_pathway:
  exposure_context:
    - beryllium_exposure
    - aerospace_industry
    - defense_industry
    - nuclear_industry
    - electronics_manufacturing
    - metal_machining_or_alloy_work
    - dental_alloy_context
    - ceramics_or_high_tech_manufacturing
    - family_or_take_home_exposure_possible

  imaging_or_clinical_overlap:
    - sarcoidosis_like_lymphadenopathy
    - sarcoidosis_like_granulomatous_lung_disease
    - pulmonary_nodules_or_interstitial_abnormality
    - dyspnea_cough_or_fatigue_context

  diagnostic_context_when_available:
    - BeLPT_abnormal_or_positive
    - beryllium_sensitization_context
    - granulomatous_inflammation_with_beryllium_exposure_context
    - occupational_medicine_review

  reasoning_weight:
    confirmed_beryllium_exposure: very_high_contextual_weight
    abnormal_BeLPT_when_available: high_to_very_high_contextual_weight
    sarcoidosis_like_pattern_with_beryllium_exposure: high_gray_zone_weight
```

---

## 4. Features Supporting Pneumoconiosis Pathway

```yaml
features_supporting_pneumoconiosis_pathway:
  exposure_context:
    - silica_exposure
    - mining
    - quarrying
    - sandblasting
    - construction
    - stone_cutting_or_artificial_stone_work
    - foundry_work
    - ceramics
    - coal_mining
    - metal_or_mixed_dust_exposure

  imaging_features:
    - upper_lung_small_nodules
    - perilymphatic_or_centriacinar_nodules_context_dependent
    - calcified_lymph_nodes
    - eggshell_calcification_when_present
    - conglomerate_masses_or_progressive_massive_fibrosis
    - emphysema_or_airway_disease_overlap_possible
    - fibrotic_distortion_when_advanced

  clinical_context:
    - long_latency_after_exposure
    - occupational_cluster_or_known_workplace_risk
    - coexisting_COPD_or_dust_related_airway_disease_possible

  reasoning_weight:
    high_confidence_silica_or_dust_exposure: high
    calcified_or_eggshell_nodes: moderate_to_high_when_context_fits
    progressive_massive_fibrosis_pattern: high_for_advanced_pneumoconiosis_context
```

---

## 5. Direct Comparison Matrix

| Feature | More Sarcoidosis-like | More Berylliosis-like | More Pneumoconiosis-like | Reasoning Note |
|---|---|---|---|---|
| Exposure history | None or noncontributory after high-quality review | Beryllium exposure | Silica/coal/metal/mixed dust exposure | Exposure quality is central |
| Lymphadenopathy | Symmetric hilar/mediastinal | Can mimic sarcoidosis | May be calcified/eggshell | Nodes alone are not enough |
| Nodules | Perilymphatic/fissural | Sarcoid-like possible | Upper-lung dust-related nodules | Distribution + exposure context matter |
| Granulomas | Nonnecrotizing supportive in context | Granulomas possible | Dust-related granulomatous/nodular pathology possible | Tissue needs occupational context |
| BeLPT | Not part of sarcoidosis | High-value when beryllium exposure possible | Not relevant unless beryllium exposure | Test relevance depends on exposure |
| Calcified nodes | Possible but not defining | Not defining | Supportive in some pneumoconioses | Pattern and exposure matter |
| PMF / conglomerate masses | Not typical simple sarcoidosis | Not typical | Advanced pneumoconiosis clue | Malignancy/infection still need review |
| Occupational latency | Not defining | Important | Important | Work history timing matters |

---

## 6. Gray Zone Scenarios

### 6.1 Sarcoidosis-like Imaging with Beryllium Exposure

```yaml
scenario_sarcoidosis_like_imaging_with_beryllium_exposure:
  problem:
    - bilateral_hilar_or_mediastinal_lymphadenopathy
    - perilymphatic_or_sarcoidosis_like_nodules
    - possible_beryllium_exposure

  sarcoidosis_leaning_features:
    - no_confirmed_beryllium_exposure_after_review
    - compatible_extrapulmonary_sarcoid_context
    - BeLPT_not_supportive_when_appropriately_performed
    - no_occupational_cluster_or_relevant_industry_context

  berylliosis_leaning_features:
    - confirmed_or_plausible_beryllium_exposure
    - abnormal_or_positive_BeLPT_when_available
    - occupational_context_fits
    - sarcoidosis_like_granulomatous_disease_without_better_explanation

  missing_pieces:
    - detailed_occupational_history
    - beryllium_exposure_assessment
    - BeLPT_if_relevant_and_available
    - workplace_or_industry_context
    - prior_CT
    - MDD_or_occupational_medicine_review

  pitfall:
    - Do_not_call_sarcoidosis_without_beryllium_review_when_exposure_is_plausible
```

### 6.2 Sarcoidosis-like Pattern with Silica or Dust Exposure

```yaml
scenario_sarcoidosis_like_pattern_with_silica_or_dust_exposure:
  problem:
    - thoracic_lymphadenopathy_or_nodules_present
    - silica_or_dust_exposure_possible

  sarcoidosis_leaning_features:
    - classic_perilymphatic_sarcoid_distribution
    - compatible_extrapulmonary_sarcoid_context
    - no_high_confidence_dust_exposure_after_review
    - no_pneumoconiotic_nodal_or_fibrotic_clues

  pneumoconiosis_leaning_features:
    - mining_quarry_sandblasting_stone_cutting_or_construction_history
    - upper_lung_small_nodules
    - calcified_or_eggshell_nodes
    - progressive_massive_fibrosis_pattern
    - occupational_latency_fits

  missing_pieces:
    - occupational_exposure_history
    - exposure_duration_intensity_and_latency
    - lymph_node_calcification_review
    - nodule_distribution_analysis
    - prior_CT
    - occupational_medicine_review

  pitfall:
    - Silica_or_dust_exposure_should_not_be_ignored_in_sarcoidosis_like_disease
```

### 6.3 Granulomas on Tissue but Occupational History Missing

```yaml
scenario_granulomas_tissue_occupational_history_missing:
  problem:
    - nonnecrotizing_or_granulomatous_inflammation_reported
    - occupational_history_incomplete

  sarcoidosis_leaning_features:
    - compatible_sarcoid_imaging
    - compatible_extrapulmonary_context
    - occupational_and_infectious_mimics_reviewed

  occupational_mimic_leaning_features:
    - beryllium_or_silica_or_dust_context_possible
    - workplace_risk_unknown
    - nodal_or_nodular_pattern_overlaps
    - tissue_without_exposure_context

  missing_pieces:
    - detailed_work_history
    - hobby_and_environmental_exposure_history
    - BeLPT_if_beryllium_relevant
    - dust_exposure_review
    - pathology_context
    - MDD_review

  pitfall:
    - Granulomas_do_not_define_sarcoidosis_when_occupational_mimics_have_not_been_reviewed
```

### 6.4 Upper-Lung Fibrotic Disease: Fibrotic Sarcoidosis vs Pneumoconiosis

```yaml
scenario_upper_lung_fibrosis_sarcoidosis_vs_pneumoconiosis:
  problem:
    - upper_lung_or_perihilar_fibrotic_disease
    - sarcoidosis_and_pneumoconiosis_both_possible

  fibrotic_sarcoidosis_leaning_features:
    - prior_typical_sarcoid_pattern
    - residual_perilymphatic_nodules
    - hilar_retraction
    - bronchovascular_bundle_distortion
    - compatible_systemic_sarcoid_context

  pneumoconiosis_leaning_features:
    - high_confidence_dust_exposure
    - upper_lung_small_nodules
    - calcified_or_eggshell_nodes
    - progressive_massive_fibrosis
    - occupational_latency_fits

  missing_pieces:
    - prior_CT
    - occupational_history
    - nodule_and_node_calcification_review
    - exposure_duration_intensity_latency
    - infection_or_malignancy_review_if_mass_like

  pitfall:
    - Upper_lung_fibrosis_should_not_be_assigned_to_sarcoidosis_without_exposure_review
```

---

## 7. Why Not Engine

### Why not sarcoidosis?

```yaml
why_not_sarcoidosis:
  - beryllium_exposure_possible_or_confirmed
  - abnormal_BeLPT_when_available
  - silica_or_dust_exposure_possible
  - mining_quarry_sandblasting_stone_cutting_construction_or_foundry_context
  - calcified_or_eggshell_nodes
  - progressive_massive_fibrosis_pattern
  - occupational_latency_fits
  - occupational_history_incomplete
```

### Why not berylliosis?

```yaml
why_not_berylliosis:
  - no_beryllium_exposure_after_high_quality_review
  - BeLPT_not_supportive_when_appropriately_performed
  - stronger_classic_sarcoidosis_context
  - infection_malignancy_or_other_mimic_stronger
```

### Why not pneumoconiosis?

```yaml
why_not_pneumoconiosis:
  - no_silica_coal_metal_or_mixed_dust_exposure_after_high_quality_review
  - no_latency_or_workplace_context
  - no_supportive_pneumoconiotic_imaging_pattern
  - stronger_sarcoidosis_or_other_granulomatous_context
```

### Why not stop at “sarcoidosis-like”?

```yaml
why_not_stop_at_sarcoidosis_like:
  - occupational_mimics_can_present_similarly
  - exposure_history_quality_matters
  - beryllium_requires_dedicated_testing_context
  - dust_disease_requires_work_history_latency_and_imaging_pattern_review
  - tissue_without_exposure_context_can_mislead
```

---

## 8. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    occupational_history:
      reason: Berylliosis, silicosis, coal workers’ pneumoconiosis, and mixed dust disease require exposure review.

    beryllium_exposure_assessment:
      reason: Chronic beryllium disease can mimic sarcoidosis and requires beryllium-specific exposure context.

    BeLPT_when_relevant:
      reason: BeLPT may support beryllium sensitization or chronic beryllium disease reasoning when exposure is plausible.

    silica_and_dust_exposure_review:
      reason: Silicosis and other pneumoconioses can mimic sarcoidosis-like nodal/nodular disease.

    exposure_duration_intensity_latency:
      reason: Occupational lung disease reasoning depends on exposure timing, intensity, and latency.

    nodule_distribution_analysis:
      reason: Sarcoid-like, pneumoconiotic, and malignant/infectious nodular patterns can overlap.

    lymph_node_calcification_review:
      reason: Calcified or eggshell nodes may redirect toward pneumoconiosis in the right context.

    prior_CT:
      reason: Temporal progression, stability, PMF evolution, or new mass-like change may redirect reasoning.

    occupational_medicine_review:
      reason: Work-related lung disease often requires specialized exposure reconstruction.

    MDD_review:
      reason: Sarcoidosis-vs-occupational mimic reasoning requires radiology, pulmonary, occupational medicine, pathology, and sometimes microbiology/oncology integration.
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  stable_sarcoidosis_like_course:
    clues:
      - stable_symmetric_nodes
      - stable_perilymphatic_nodules
      - compatible_multisystem_sarcoid_context
    caution:
      - stability_does_not_remove_need_for_occupational_review_if_exposure_context_exists

  occupational_latency_pattern:
    clues:
      - symptoms_or_imaging_after_relevant_work_exposure
      - long_latency_after_silica_or_dust_exposure
      - persistent_or_progressive_abnormalities_after_exposure
    caution:
      - exposure_timing_must_be_reconstructed_carefully

  pneumoconiosis_progression:
    clues:
      - increasing_upper_lung_nodularity
      - increasing_fibrotic_distortion
      - evolving_conglomerate_masses_or_PMF
      - increasing_calcified_nodes_or_dust_related_features
    consider:
      - pneumoconiosis
      - malignancy_or_infection_if_new_mass_like_change

  unexpectedly_fast_worsening:
    consider:
      - infection
      - malignancy
      - acute_exposure_related_injury
      - sarcoid_inflammatory_activity
      - pulmonary_embolism
      - superimposed_process
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - sarcoidosis_like_pattern_with_plausible_beryllium_exposure
    - sarcoidosis_like_pattern_with_silica_or_dust_exposure
    - granulomas_present_but_occupational_history_incomplete
    - upper_lung_fibrosis_with_dust_exposure_context
    - BeLPT_or_exposure_data_conflict_with_imaging
    - malignancy_or_infection_mimic_not_excluded

  occupational_medicine_review_high_value_if:
    - beryllium_or_silica_or_metal_dust_possible
    - work_history_complex_or_incomplete
    - latency_or_exposure_intensity_unclear
    - compensation_or_workplace_cluster_context_exists

  BeLPT_discussion_if:
    - beryllium_exposure_possible
    - sarcoidosis_like_granulomatous_disease_present
    - occupational_medicine_or_pulmonary_review_supports_relevance

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_exposure_review
    - infection_or_malignancy_must_be_excluded
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Calling sarcoidosis without occupational history.
    correction: Berylliosis and silicosis can mimic sarcoidosis; exposure history is not optional.

  - title: Treating “no known exposure” as high-quality negative exposure history.
    correction: Unknown, incomplete, and high-quality negative exposure histories are different.

  - title: Ignoring beryllium-specific testing context.
    correction: BeLPT may be high value when beryllium exposure is plausible.

  - title: Ignoring silica or dust exposure.
    correction: Mining, quarrying, sandblasting, stone cutting, construction, foundry, ceramics, coal, and mixed dust exposures should be reviewed.

  - title: Letting granulomas override exposure context.
    correction: Granulomas require occupational, microbiologic, malignancy, and imaging context.

  - title: Missing pneumoconiosis in upper-lung nodular/fibrotic disease.
    correction: Upper-lung nodules, calcified nodes, and PMF-like changes require dust exposure review.

  - title: Ignoring malignancy or infection in mass-like occupational lung disease.
    correction: New or progressive mass-like change requires infection and malignancy review.
```

---

## 12. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    - ATS_2014_BERYLLIUM_SENSITIVITY_AND_CHRONIC_BERYLLIUM_DISEASE_STATEMENT

  supportive_sources:
    - OCCUPATIONAL_LUNG_DISEASE_REVIEW_2023
    - DIFFERENTIAL_DIAGNOSIS_OF_PULMONARY_SARCOIDOSIS_2023_REVIEW
    - PNEUMOCONIOSIS_IMAGING_REVIEW_2023
    - BE_LPT_SARCOIDOSIS_CBD_DIFFERENTIAL_2025_REVIEW

  evidence_notes:
    - BTS highlights berylliosis and silicosis as sarcoidosis mimics requiring exposure and occupational history.
    - ATS beryllium statement supports BeLPT context for beryllium sensitization and CBD reasoning.
    - Occupational lung disease reasoning requires integration of exposure type, timing, latency, imaging pattern, and MDD/occupational review.
```

---

## 13. MVP Test Case

```yaml
case_test_sarcoidosis_vs_occupational_mimic_001:
  input:
    age: 56
    sex: male
    hrct:
      - bilateral_hilar_lymphadenopathy
      - upper_lung_small_nodules
      - mediastinal_lymphadenopathy
      - possible_node_calcification
    history:
      occupation: construction_and_stone_work
      beryllium_exposure: unknown
      silica_exposure: possible
      dust_exposure_duration: unknown
      latency: unknown
      extrapulmonary_sarcoid_features: unknown
      infection_review: unknown
      prior_CT: unavailable
    laboratory:
      BeLPT: unavailable
    tissue:
      granulomas: unavailable

  output:
    reasoning_state: sarcoidosis_vs_occupational_granulomatous_mimic_gray_zone
    sarcoidosis_support:
      - bilateral_hilar_lymphadenopathy
      - sarcoidosis_like_nodal_pattern
    occupational_mimic_support:
      - upper_lung_small_nodules
      - construction_and_stone_work_context
      - possible_silica_exposure
      - possible_node_calcification
    cannot_conclude:
      - sarcoidosis
      - silicosis_or_pneumoconiosis
      - chronic_beryllium_disease
      - infection_or_malignancy_excluded
    missing_pieces:
      - detailed_occupational_history
      - silica_and_dust_exposure_review
      - beryllium_exposure_assessment
      - BeLPT_if_relevant
      - exposure_duration_intensity_latency
      - prior_CT
      - occupational_medicine_review
      - MDD_review
    final_prompt:
      - What occupational exposure evidence is missing before calling this sarcoidosis?
```

---

## 14. Final Page Prompt

Every Sarcoidosis vs Berylliosis / Pneumoconiosis gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Has a high-quality occupational history been taken?
2. Is beryllium exposure possible?
3. Is silica, coal, metal, construction, mining, quarry, sandblasting, stone, ceramic, or mixed dust exposure possible?
4. Are lymph nodes calcified or eggshell-calcified?
5. Are nodules perilymphatic, pneumoconiotic, random, or mixed?
6. Is BeLPT relevant?
7. What does the prior CT show?
8. Is occupational medicine or MDD review needed?
9. What do we still not know?
```