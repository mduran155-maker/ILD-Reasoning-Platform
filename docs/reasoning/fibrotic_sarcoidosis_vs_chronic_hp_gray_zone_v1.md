# Fibrotic Sarcoidosis vs Chronic / Fibrotic Hypersensitivity Pneumonitis — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_fibrotic_sarcoidosis_vs_chronic_hp_v1
title: Fibrotic Sarcoidosis vs Chronic / Fibrotic Hypersensitivity Pneumonitis — Gray Zone Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
diagnostic_authority: none
linked_patterns:
  - sarcoidosis_pattern_gold_standard_v1
  - fibrotic_hp_pattern_gold_standard_v1
linked_reasoning_maps:
  - granulomatous_ild_reasoning_map_v1
  - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1
  - fibrotic_ild_triage_map_v1
linked_navigation:
  - granulomatous_crosslink_registry_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - occupational / environmental lung disease clinicians
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare fibrotic sarcoidosis and chronic / fibrotic hypersensitivity pneumonitis without forcing premature diagnostic certainty.

It does not diagnose fibrotic sarcoidosis, chronic HP, fibrotic HP, pneumoconiosis, PPFE, infection, malignancy, or unclassifiable fibrotic ILD.

It helps users ask:

- Is the fibrosis upper/perihilar and bronchovascular, or airway-centered/exposure-related?
- Is there prior evidence of typical sarcoidosis?
- Is there exposure history supporting HP?
- Is there air trapping, mosaic attenuation, or three-density pattern?
- Are residual perilymphatic nodules present?
- Are centrilobular nodules present?
- Is the fibrotic pattern stable, progressive, or complicated by infection / aspergilloma / malignancy?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  fibrotic_sarcoidosis_pathway:
    reasoning_center: chronic_sarcoid_related_fibrotic_distortion_often_upper_or_perihilar_with_bronchovascular_distortion
    classic_clues:
      - prior_typical_sarcoidosis_pattern
      - upper_lung_or_perihilar_fibrosis
      - bronchovascular_bundle_distortion
      - hilar_retraction
      - traction_bronchiectasis
      - volume_loss
      - residual_perilymphatic_nodules
      - fibrocystic_or_cavitary_complication_possible
    danger_statement: fibrotic_sarcoidosis_should_not_be_called_without_reviewing_HP_pneumoconiosis_infection_and_malignancy_mimics

  chronic_or_fibrotic_hp_pathway:
    reasoning_center: exposure_related_fibrotic_ILD_with_airway_centered_small_airway_or_three_density_pattern_clues
    classic_clues:
      - detailed_antigen_exposure_history
      - persistent_air_trapping
      - mosaic_attenuation
      - three_density_pattern
      - poorly_defined_centrilobular_ground_glass_nodules
      - nonclassic_fibrosis_distribution
      - inflammatory_to_fibrotic_temporal_evolution
      - BAL_lymphocytosis_when_available
    danger_statement: fibrotic_HP_can_mimic_fibrotic_sarcoidosis_when_upper_mid_lung_or_airway_distortion_is_present
```

### Teaching Point

Fibrotic sarcoidosis asks:

```text
Is this chronic sarcoid-related upper/perihilar bronchovascular fibrosis with supportive sarcoidosis context?
```

Chronic / fibrotic HP asks:

```text
Is this exposure-related fibrotic ILD with air trapping, mosaic attenuation, three-density pattern, or centrilobular nodules?
```

The key error is to assume that upper-lung fibrosis automatically means sarcoidosis or that air trapping is incidental.

---

## 2. Features Supporting Fibrotic Sarcoidosis Pathway

```yaml
features_supporting_fibrotic_sarcoidosis_pathway:
  prior_context:
    - prior_typical_sarcoidosis_pattern
    - known_sarcoidosis_history
    - prior_bilateral_hilar_or_mediastinal_lymphadenopathy
    - prior_perilymphatic_nodules
    - compatible_extrapulmonary_sarcoid_context

  fibrosis_distribution:
    - upper_lung_predominance
    - perihilar_predominance
    - peribronchovascular_or_bronchovascular_bundle_distribution
    - hilar_retraction
    - upper_lobe_volume_loss

  morphology:
    - bronchovascular_distortion
    - traction_bronchiectasis
    - architectural_distortion
    - fibrocystic_change_possible
    - residual_perilymphatic_nodules_possible
    - airway_distortion_possible

  complications_to_consider:
    - pulmonary_hypertension
    - aspergilloma
    - chronic_cavitary_complication
    - recurrent_infection
    - airway_stenosis_or_distortion

  reasoning_weight:
    prior_typical_sarcoidosis_pattern: very_high_contextual_weight
    upper_perihilar_bronchovascular_fibrosis: high
    residual_perilymphatic_nodules: high
    hilar_retraction_or_bronchovascular_distortion: moderate_to_high
```

---

## 3. Features Supporting Chronic / Fibrotic HP Pathway

```yaml
features_supporting_chronic_or_fibrotic_hp_pathway:
  exposure_context:
    - bird_or_feather_exposure
    - mold_or_water_damage
    - humidifier_or_hot_tub_exposure
    - farming_or_agricultural_exposure
    - compost_or_organic_dust_exposure
    - occupational_antigen_exposure
    - recurrent_symptoms_after_exposure
    - improvement_or_stabilization_after_exposure_control_possible

  airway_centered_features:
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - poorly_defined_centrilobular_ground_glass_nodules
    - bronchiolocentric_or_airway_centered_distribution
    - lobular_heterogeneity

  fibrotic_features:
    - reticulation
    - traction_bronchiectasis
    - architectural_distortion
    - honeycombing_possible
    - nonclassic_distribution
    - persistent_air_trapping_with_fibrosis

  supportive_tests:
    - BAL_lymphocytosis_when_available
    - exposure_assessment_support
    - pathology_support_when_available
    - temporal_relationship_to_exposure

  reasoning_weight:
    three_density_pattern: very_high_when_present
    persistent_expiratory_air_trapping: high
    centrilobular_ground_glass_nodules: high
    convincing_exposure_history: high_but_not_standalone
    BAL_lymphocytosis: supportive_context_dependent
```

---

## 4. Direct Comparison Matrix

| Feature | More Fibrotic Sarcoidosis-like | More Chronic / Fibrotic HP-like | Reasoning Note |
|---|---|---|---|
| Prior disease context | Prior typical sarcoidosis | Prior exposure-related inflammatory HP possible | Prior CT is high-yield |
| Fibrosis location | Upper/perihilar, bronchovascular | Upper/mid/diffuse/lower possible, often nonclassic | Location alone is not enough |
| Nodule pattern | Residual perilymphatic/fissural nodules | Centrilobular GGO nodules | Distribution is central |
| Air trapping | Can occur with airway sarcoid | Strong HP clue when extensive/lobular | Expiratory HRCT is essential |
| Three-density pattern | Against simple sarcoidosis | Strongly supportive | High-value discriminator |
| Exposure history | Occupational mimic possible but not central | Central | Exposure quality matters |
| Lymphadenopathy | Sarcoid context may persist | Variable | Nodes alone do not decide |
| Bronchovascular distortion | Strong sarcoid-fibrotic clue | Less central | Look for perihilar retraction |
| BAL lymphocytosis | Not defining | Supportive in context | Not standalone |
| Complications | PH, aspergilloma, chronic cavities | Progressive fibrotic ILD, recurrent exposure/inflammation | Complication review differs |

---

## 5. Gray Zone Scenarios

### 5.1 Upper-Lung Fibrosis with Air Trapping

```yaml
scenario_upper_lung_fibrosis_with_air_trapping:
  problem:
    - upper_lung_or_perihilar_fibrosis_present
    - air_trapping_or_mosaic_attenuation_present
    - sarcoidosis_and_HP_both_possible

  fibrotic_sarcoidosis_leaning_features:
    - prior_typical_sarcoidosis
    - residual_perilymphatic_nodules
    - perihilar_bronchovascular_distortion
    - hilar_retraction
    - upper_lobe_volume_loss
    - compatible_extrapulmonary_sarcoid_context

  fibrotic_hp_leaning_features:
    - extensive_lobular_air_trapping
    - three_density_pattern
    - centrilobular_ground_glass_nodules
    - exposure_history
    - BAL_lymphocytosis_when_available
    - recurrent_worsening_after_exposure

  missing_pieces:
    - prior_CT
    - expiratory_HRCT_quality
    - detailed_exposure_history
    - nodule_distribution_analysis
    - BAL_if_clinically_relevant
    - MDD_review

  pitfall:
    - Air_trapping_should_not_be_dismissed_as_incidental_in_fibrotic_sarcoidosis_like_cases
```

### 5.2 Known Sarcoidosis with Progressive Fibrosis

```yaml
scenario_known_sarcoidosis_with_progressive_fibrosis:
  problem:
    - known_or_prior_sarcoidosis
    - increasing_fibrotic_abnormality

  fibrotic_sarcoidosis_leaning_features:
    - fibrosis_extending_from_prior_sarcoid_distribution
    - upper_perihilar_distortion
    - residual_perilymphatic_nodules
    - hilar_retraction
    - no_new_exposure_or_HP_clues

  fibrotic_hp_or_other_mimic_leaning_features:
    - new_or_unrecognized_antigen_exposure
    - new_air_trapping_or_three_density_pattern
    - new_centrilobular_nodules
    - fibrosis_pattern_not_matching_prior_sarcoid_distribution
    - occupational_dust_or_HP_context

  missing_pieces:
    - old_CT_series
    - exposure_history_update
    - occupational_history_update
    - expiratory_HRCT
    - superimposed_event_review
    - MDD_review

  pitfall:
    - Known_sarcoidosis_does_not_prove_all_future_fibrosis_is_sarcoidosis
```

### 5.3 Exposure History in Fibrotic Sarcoidosis-like Disease

```yaml
scenario_exposure_history_in_fibrotic_sarcoidosis_like_disease:
  problem:
    - fibrotic_sarcoidosis_like_pattern
    - antigen_or_environmental_exposure_possible

  fibrotic_sarcoidosis_leaning_features:
    - classic_prior_sarcoid_pattern
    - perilymphatic_residual_nodules
    - upper_perihilar_bronchovascular_distortion
    - no_airway_centered_HP_features
    - exposure_weak_or_incidental_after_review

  fibrotic_hp_leaning_features:
    - strong_or_recurrent_antigen_exposure
    - symptom_timing_related_to_exposure
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - centrilobular_nodules
    - BAL_lymphocytosis_when_available

  missing_pieces:
    - exposure_quality_review
    - antigen_type_and_intensity
    - symptom_timing_relative_to_exposure
    - expiratory_HRCT
    - prior_CT
    - MDD_review

  pitfall:
    - Exposure_history_supports_HP_but_does_not_prove_HP_without_integrated_context
```

### 5.4 Fibrocystic / Cavitary Change in Fibrotic Sarcoidosis-like Pattern

```yaml
scenario_fibrocystic_or_cavitary_change:
  problem:
    - fibrotic_sarcoidosis_like_pattern
    - cystic_or_cavitary_appearing_abnormality_present

  sarcoidosis_complication_leaning_features:
    - chronic_upper_lung_fibrocystic_distortion
    - known_fibrotic_sarcoidosis
    - aspergilloma_or_chronic_cavitary_complication_possible
    - airway_distortion_context

  alternative_or_superimposed_leaning_features:
    - new_cavitation
    - infection_context
    - fungal_or_aspergillus_context
    - malignancy_or_new_mass_like_change
    - GPA_or_vasculitic_context
    - emphysema_or_cystic_lung_disease_mimic

  missing_pieces:
    - prior_CT
    - microbiology_if_relevant
    - fungal_or_aspergillus_review
    - malignancy_review_if_new_or_asymmetric
    - vascular_or_hemoptysis_context
    - MDD_review

  pitfall:
    - Cavitary_or_cystic_change_should_not_be_called_simple_fibrotic_sarcoidosis_without_complication_review
```

---

## 6. Why Not Engine

### Why not fibrotic sarcoidosis?

```yaml
why_not_fibrotic_sarcoidosis:
  - no_prior_typical_sarcoidosis_context
  - no_residual_perilymphatic_nodules
  - dominant_centrilobular_ground_glass_nodules
  - marked_or_extensive_air_trapping
  - three_density_pattern
  - convincing_antigen_exposure
  - BAL_lymphocytosis_when_available
  - recurrent_worsening_after_exposure
  - occupational_dust_or_pneumoconiosis_context
  - fibrosis_distribution_not_matching_sarcoid_context
```

### Why not chronic / fibrotic HP?

```yaml
why_not_chronic_or_fibrotic_HP:
  - no_exposure_after_high_quality_assessment
  - no_air_trapping_on_adequate_expiratory_HRCT
  - no_mosaic_or_three_density_pattern
  - no_centrilobular_nodules
  - strong_prior_typical_sarcoidosis_context
  - upper_perihilar_bronchovascular_distortion_with_residual_perilymphatic_nodules
  - infection_malignancy_or_pneumoconiosis_explains_findings_better
```

### Why not stop at “upper-lobe fibrosis”?

```yaml
why_not_stop_at_upper_lobe_fibrosis:
  - upper_lobe_fibrosis_has_broad_differential
  - sarcoidosis_HP_pneumoconiosis_PPFE_TB_and_other_mimics_can_overlap
  - prior_CT_and_exposure_history_are_high_yield
  - nodule_distribution_and_airway_clues_matter
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether fibrosis evolved from typical sarcoidosis, inflammatory HP, exposure-related disease, or another process.

    expiratory_HRCT:
      reason: Air trapping and three-density pattern are high-value HP clues.

    exposure_history:
      reason: Chronic / fibrotic HP cannot be reasonably assessed without high-quality antigen review.

    occupational_history:
      reason: Pneumoconiosis and occupational granulomatous disease can mimic fibrotic sarcoidosis.

    nodule_distribution_analysis:
      reason: Residual perilymphatic nodules support sarcoidosis; centrilobular nodules support HP-like reasoning.

    lymph_node_and_hilar_retraction_review:
      reason: Symmetric nodes, calcified nodes, hilar retraction, and perihilar distortion change reasoning.

    BAL_lymphocytosis_if_relevant:
      reason: May support HP when interpreted with HRCT and exposure context.

    complication_review:
      reason: Fibrotic sarcoidosis may be complicated by pulmonary hypertension, aspergilloma, chronic cavitary change, infection, or malignancy.

    MDD_review:
      reason: Fibrotic sarcoidosis-vs-chronic HP often requires radiology, pulmonary, exposure, pathology, and sometimes occupational/infectious disease input.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  behavior_supporting_fibrotic_sarcoidosis:
    clues:
      - fibrosis_evolves_from_prior_typical_sarcoidosis_distribution
      - increasing_upper_perihilar_bronchovascular_distortion
      - residual_or_prior_perilymphatic_nodules
      - hilar_retraction_over_time
      - chronic_fibrocystic_complication_context
    caution:
      - known_sarcoidosis_does_not_exclude_new_HP_or_superimposed_process

  behavior_supporting_fibrotic_HP:
    clues:
      - recurrent_worsening_after_exposure
      - transition_from_centrilobular_GGO_nodules_or_mosaic_attenuation_to_fibrosis
      - persistent_or_increasing_air_trapping
      - stabilization_or_partial_improvement_after_exposure_control
      - progression_with_ongoing_or_unrecognized_antigen_exposure
    caution:
      - exposure_response_supports_HP_but_does_not_prove_it

  progression_in_either_pathway:
    clues:
      - increasing_fibrosis_extent
      - increasing_traction_bronchiectasis
      - increasing_architectural_distortion
      - worsening_PFT_when_available
      - increasing_oxygen_requirement_when_available
    prompt:
      - Is this disease progression, exposure recurrence, sarcoid fibrosis evolution, or superimposed disease?

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation_or_inflammatory_flare
      - exposure_rechallenge
      - pulmonary_embolism
      - pulmonary_edema
      - aspergilloma_or_cavitary_complication
      - malignancy
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - upper_lung_fibrosis_with_air_trapping_or_mosaic_attenuation
    - fibrotic_sarcoidosis_known_but_new_HP_clues_present
    - exposure_history_positive_but_sarcoid_pattern_classic
    - prior_CT_and_current_CT_suggest_different_pathways
    - cavitary_or_fibrocystic_complication_present
    - infection_malignancy_or_pneumoconiosis_not_excluded
    - treatment_or_exposure_response_is_unexpected

  exposure_review_high_value_if:
    - air_trapping_or_three_density_pattern_present
    - centrilobular_nodules_present
    - recurrent_worsening_without_clear_cause
    - possible_bird_mold_humidifier_hot_tub_farming_compost_or_workplace_exposure

  occupational_review_high_value_if:
    - upper_lung_fibrosis_with_dust_exposure_possible
    - calcified_nodes_or_pneumoconiosis_features
    - mining_quarry_stone_sandblasting_construction_ceramic_or_metal_exposure_possible

  complication_review_high_value_if:
    - cavitary_or_fibrocystic_change
    - hemoptysis
    - pulmonary_hypertension_clues
    - chronic_infection_or_aspergilloma_possible

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_exposure_review
    - infection_or_malignancy_must_be_excluded
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling all upper-lung fibrosis fibrotic sarcoidosis.
    correction: Chronic HP, pneumoconiosis, PPFE, TB-related fibrosis, and other mimics can involve upper lungs.

  - title: Ignoring air trapping in sarcoidosis-like fibrosis.
    correction: Air trapping may occur in sarcoidosis, but extensive lobular air trapping or three-density pattern should trigger HP review.

  - title: Ignoring exposure history because sarcoidosis is already known.
    correction: Known sarcoidosis does not exclude HP, occupational disease, infection, or malignancy.

  - title: Calling fibrosis progression without prior CT review.
    correction: Temporal evolution is central to distinguishing sarcoid fibrosis from HP evolution or superimposed disease.

  - title: Missing aspergilloma or chronic infection in fibrocystic sarcoidosis.
    correction: Cavitary/fibrocystic change requires complication and microbiology review when relevant.

  - title: Missing pneumoconiosis.
    correction: Upper-lung fibrosis and nodules require dust/occupational exposure review.

  - title: Treating BAL lymphocytosis as standalone HP diagnosis.
    correction: BAL supports HP only when integrated with exposure, HRCT, pathology, and MDD context.
```

---

## 11. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    - ATS_JRS_ALAT_2020_HP_DIAGNOSIS

  supportive_sources:
    - FIBROTIC_PULMONARY_SARCOIDOSIS_REVIEW_2025
    - CT_IMAGING_FEATURES_PULMONARY_SARCOIDOSIS_2025_REVIEW
    - HRCT_FIBROTIC_ILD_COMPARATIVE_REVIEW
    - HP_DIAGNOSIS_COURSE_MANAGEMENT_REVIEW_2022

  evidence_notes:
    - Fibrotic sarcoidosis reasoning requires sarcoidosis context and mimic review.
    - Fibrotic HP reasoning requires exposure, HRCT, BAL/pathology when relevant, and MDD integration.
    - Upper/perihilar fibrosis supports fibrotic sarcoidosis only in the correct context.
    - Air trapping, mosaic attenuation, centrilobular nodules, and three-density pattern should keep HP visible.
```

---

## 12. MVP Test Case

```yaml
case_test_fibrotic_sarcoidosis_vs_chronic_hp_001:
  input:
    age: 59
    sex: male
    hrct:
      - upper_lung_fibrosis
      - perihilar_architectural_distortion
      - traction_bronchiectasis
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
      - no_definite_current_perilymphatic_nodules_reported
    history:
      prior_sarcoidosis: unknown
      prior_CT: unavailable
      bird_exposure: unknown
      mold_exposure: unknown
      occupational_exposure: unknown
      recurrent_worsening_after_exposure: unknown
      pulmonary_hypertension_context: unknown
      hemoptysis_or_aspergilloma_context: unknown
    laboratory:
      BAL_lymphocytosis: unavailable

  output:
    reasoning_state: fibrotic_sarcoidosis_vs_chronic_HP_gray_zone
    fibrotic_sarcoidosis_support:
      - upper_lung_fibrosis
      - perihilar_architectural_distortion
      - traction_bronchiectasis
    chronic_HP_support:
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
      - exposure_history_unknown
    cannot_conclude:
      - fibrotic_sarcoidosis
      - chronic_or_fibrotic_HP
      - pneumoconiosis
      - infection_or_cavitary_complication
      - malignancy_excluded
    missing_pieces:
      - prior_CT
      - prior_sarcoidosis_context
      - detailed_exposure_history
      - occupational_history
      - expiratory_HRCT_quality_review
      - nodule_distribution_analysis
      - BAL_lymphocytosis_if_clinically_relevant
      - complication_review
      - MDD_review
    final_prompt:
      - What temporal, exposure, and distribution evidence is missing before calling this fibrotic sarcoidosis or chronic HP?
```

---

## 13. Final Page Prompt

Every Fibrotic Sarcoidosis vs Chronic / Fibrotic HP gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Did this fibrosis evolve from a prior typical sarcoidosis pattern?
2. Is the fibrosis upper/perihilar with bronchovascular distortion, or airway-centered/exposure-related?
3. Are residual perilymphatic nodules or centrilobular nodules present?
4. Is there air trapping, mosaic attenuation, or three-density pattern?
5. Is exposure history high-quality or incomplete?
6. Is occupational dust exposure possible?
7. What does the prior CT show?
8. Is there pulmonary hypertension, aspergilloma, infection, cavitary complication, or malignancy concern?
9. Is MDD needed?
10. What do we still not know?
```