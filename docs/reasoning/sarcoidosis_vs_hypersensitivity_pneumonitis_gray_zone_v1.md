# Sarcoidosis vs Hypersensitivity Pneumonitis — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_sarcoidosis_vs_hypersensitivity_pneumonitis_v1
title: Sarcoidosis vs Hypersensitivity Pneumonitis — Gray Zone Reasoning Map
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
  - fibrotic_ild_triage_map_v1
linked_navigation:
  - granulomatous_crosslink_registry_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare sarcoidosis-like thoracic disease and hypersensitivity pneumonitis without forcing premature diagnostic certainty.

It does not diagnose sarcoidosis, hypersensitivity pneumonitis, fibrotic HP, granulomatous infection, occupational granulomatous disease, GLILD, malignancy, or sarcoid-like reaction.

It helps users ask:

- Are the nodules perilymphatic, centrilobular, or random?
- Is lymphadenopathy symmetric and sarcoidosis-like?
- Is there air trapping, mosaic attenuation, or three-density pattern?
- Is there a plausible antigen exposure?
- Is expiratory HRCT available?
- Is BAL lymphocytosis available or relevant?
- Are infection, GLILD, occupational mimics, and malignancy still visible?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  sarcoidosis_pathway:
    reasoning_center: nodal_perilymphatic_granulomatous_pattern
    classic_clues:
      - bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - fissural_nodules
      - peribronchovascular_nodules
      - upper_or_mid_lung_predominance
      - compatible_extrapulmonary_context
    danger_statement: sarcoidosis_like_imaging_does_not_exclude_HP_or_other_granulomatous_mimics

  hypersensitivity_pneumonitis_pathway:
    reasoning_center: exposure_related_small_airway_granulomatous_or_fibrotic_ILD
    classic_clues:
      - exposure_history
      - poorly_defined_centrilobular_ground_glass_nodules
      - mosaic_attenuation
      - air_trapping
      - three_density_pattern
      - BAL_lymphocytosis_when_available
      - fibrotic_evolution_when_chronic_or_fibrotic
    danger_statement: HP_can_be_missed_if_air_trapping_and_exposure_history_are_not_actively_reviewed
```

### Teaching Point

Sarcoidosis asks:

```text
Is this a nodal-perilymphatic granulomatous pattern with compatible clinical context?
```

HP asks:

```text
Is this an exposure-related, airway-centered process with centrilobular nodules, air trapping, mosaic attenuation, or three-density pattern?
```

The key error is to treat all small nodules or all granulomatous inflammation as sarcoidosis.

---

## 2. Features Supporting Sarcoidosis Pathway

```yaml
features_supporting_sarcoidosis_pathway:
  nodal_features:
    - bilateral_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - symmetric_nodal_distribution
    - non_necrotic_nodes_when_characterized

  nodule_distribution:
    - perilymphatic_nodules
    - fissural_nodules
    - subpleural_nodules
    - peribronchovascular_nodules

  parenchymal_distribution:
    - upper_or_mid_lung_predominance
    - bronchovascular_bundle_distribution
    - perihilar_or_peribronchovascular_bias

  clinical_context:
    - compatible_eye_skin_or_lymph_node_features
    - compatible_multisystem_context
    - chronic_or_subacute_noninfectious_course

  reasoning_weight:
    symmetric_bilateral_hilar_nodes: high
    perilymphatic_nodules: high
    fissural_nodules: high
    compatible_extrapulmonary_context: moderate_to_high
```

---

## 3. Features Supporting HP Pathway

```yaml
features_supporting_hp_pathway:
  exposure_features:
    - birds_or_feather_exposure
    - mold_or_water_damage
    - humidifier_or_hot_tub_exposure
    - farming_or_agricultural_exposure
    - occupational_antigen_exposure
    - recurrent_symptoms_after_exposure

  small_airway_features:
    - poorly_defined_centrilobular_ground_glass_nodules
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - lobular_heterogeneity

  fibrotic_features_when_chronic_or_fibrotic:
    - reticulation
    - traction_bronchiectasis
    - architectural_distortion
    - nonclassic_distribution
    - persistent_air_trapping_with_fibrosis

  supportive_tests:
    - BAL_lymphocytosis_when_available
    - exposure_assessment_support
    - pathology_support_when_available
    - temporal_relationship_to_exposure

  reasoning_weight:
    three_density_pattern: very_high_when_present
    expiratory_air_trapping: high
    centrilobular_ground_glass_nodules: high
    exposure_history: high_but_not_standalone
    BAL_lymphocytosis: supportive_context_dependent
```

---

## 4. Direct Comparison Matrix

| Feature | More Sarcoidosis-like | More HP-like | Reasoning Note |
|---|---|---|---|
| Nodule distribution | Perilymphatic, fissural, peribronchovascular | Poorly defined centrilobular GGO nodules | Distribution is central |
| Lymphadenopathy | Symmetric hilar/mediastinal common | Variable, not usually dominant | Dominant symmetric nodes favor sarcoid-like reasoning |
| Air trapping | Can occur, especially airway sarcoid | Strong HP clue | Expiratory HRCT is critical |
| Mosaic attenuation | Possible but not central | Supportive | Must be interpreted with expiratory imaging |
| Three-density pattern | Against simple sarcoidosis | Highly supportive | Strong HP clue when present |
| Exposure history | Occupational mimic possible | Central | Exposure supports HP but does not prove it |
| BAL lymphocytosis | Not defining | Supportive | Not standalone diagnostic authority |
| Fibrosis | Upper/perihilar sarcoid fibrosis possible | Fibrotic HP can be diffuse/mid/lower or UIP-like | Prior CT and distribution matter |
| Tissue granulomas | Supportive in context | HP may also have granulomatous features | Tissue without context can mislead |

---

## 5. Gray Zone Scenarios

### 5.1 Small Nodules: Perilymphatic vs Centrilobular

```yaml
scenario_small_nodules_distribution_uncertain:
  problem:
    - small_pulmonary_nodules_present
    - distribution_uncertain
    - sarcoidosis_and_HP_both_possible

  sarcoidosis_leaning_features:
    - nodules_along_fissures
    - nodules_along_bronchovascular_bundles
    - subpleural_nodules
    - symmetric_hilar_or_mediastinal_nodes

  hp_leaning_features:
    - poorly_defined_centrilobular_ground_glass_nodules
    - subpleural_sparing_of_nodules
    - air_trapping
    - mosaic_attenuation
    - exposure_history

  missing_pieces:
    - detailed_nodule_distribution_analysis
    - expiratory_HRCT
    - exposure_history
    - prior_CT
    - MDD_review

  pitfall:
    - Do_not_call_all_small_nodules_sarcoidosis_without_distribution_analysis
```

### 5.2 Sarcoid-like Nodes with Air Trapping

```yaml
scenario_sarcoid_like_nodes_with_air_trapping:
  problem:
    - bilateral_hilar_or_mediastinal_nodes_present
    - air_trapping_or_mosaic_attenuation_present

  sarcoidosis_leaning_features:
    - symmetric_nodes
    - perilymphatic_nodules
    - compatible_extrapulmonary_context
    - airway_sarcoidosis_context_possible

  hp_leaning_features:
    - extensive_lobular_air_trapping
    - three_density_pattern
    - centrilobular_ground_glass_nodules
    - exposure_history
    - BAL_lymphocytosis_when_available

  missing_pieces:
    - expiratory_HRCT_quality
    - exposure_history
    - BAL_if_clinically_relevant
    - immune_status
    - infection_review
    - MDD_review

  pitfall:
    - Air_trapping_should_not_be_dismissed_as_incidental_when_HP_is_possible
```

### 5.3 Fibrotic Sarcoidosis vs Fibrotic HP

```yaml
scenario_fibrotic_sarcoidosis_vs_fibrotic_hp:
  problem:
    - fibrotic_granulomatous_ILD_pattern_possible
    - sarcoidosis_and_HP_both_remain_possible

  fibrotic_sarcoidosis_leaning_features:
    - prior_typical_sarcoidosis_pattern
    - upper_or_perihilar_fibrosis
    - hilar_retraction
    - bronchovascular_distortion
    - residual_perilymphatic_nodules
    - compatible_systemic_sarcoid_context

  fibrotic_hp_leaning_features:
    - exposure_history
    - persistent_air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - centrilobular_nodules
    - inflammatory_to_fibrotic_evolution

  missing_pieces:
    - prior_CT
    - exposure_history
    - expiratory_HRCT
    - occupational_history
    - BAL_if_clinically_relevant
    - MDD_review

  pitfall:
    - Do_not_assume_upper_lobe_fibrosis_is_automatically_sarcoidosis_or_HP_without_context
```

### 5.4 Exposure History Present in a Sarcoidosis-like Pattern

```yaml
scenario_exposure_present_in_sarcoidosis_like_pattern:
  problem:
    - sarcoidosis_like_pattern_present
    - exposure_history_present_or_possible

  key_question:
    - Is the exposure causal, incidental, weak, or incompletely characterized?

  sarcoidosis_leaning_features:
    - classic_perilymphatic_nodules
    - symmetric_bilateral_hilar_lymphadenopathy
    - no_air_trapping_or_three_density_pattern
    - compatible_extrapulmonary_sarcoid_context

  hp_leaning_features:
    - recurrent_worsening_after_exposure
    - centrilobular_nodules
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - BAL_lymphocytosis_when_available

  missing_pieces:
    - exposure_quality_review
    - antigen_type
    - symptom_timing_relative_to_exposure
    - expiratory_HRCT
    - prior_CT
    - MDD_review

  pitfall:
    - Exposure_history_supports_HP_but_does_not_prove_HP
```

---

## 6. Why Not Engine

### Why not sarcoidosis?

```yaml
why_not_sarcoidosis:
  - centrilobular_ground_glass_nodules
  - marked_air_trapping
  - mosaic_attenuation
  - three_density_pattern
  - convincing_antigen_exposure
  - BAL_lymphocytosis_when_available
  - recurrent_worsening_after_exposure
  - nodule_distribution_not_perilymphatic
  - infection_review_incomplete
```

### Why not HP?

```yaml
why_not_hp:
  - perilymphatic_nodules_dominate
  - fissural_nodules
  - symmetric_bilateral_hilar_lymphadenopathy_dominates
  - no_air_trapping_on_good_expiratory_HRCT
  - no_exposure_after_high_quality_review
  - compatible_extrapulmonary_sarcoid_context
  - occupational_or_malignancy_mimic_stronger_than_HP
```

### Why not stop at “granulomatous ILD”?

```yaml
why_not_stop_at_granulomatous_ild:
  - granulomatous_ILD_has_broad_differential
  - nodule_distribution_changes_reasoning
  - exposure_history_changes_reasoning
  - airway_centered_findings_change_reasoning
  - infection_and_occupational_mimics_must_remain_visible
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    nodule_distribution_analysis:
      reason: Perilymphatic versus centrilobular distribution is central to sarcoidosis-vs-HP reasoning.

    expiratory_HRCT:
      reason: Air trapping and three-density pattern may redirect toward HP.

    exposure_history:
      reason: HP reasoning requires high-quality antigen and occupational/environmental assessment.

    BAL_lymphocytosis:
      reason: May support HP when interpreted with exposure and HRCT context.

    infection_review:
      reason: Infection remains a granulomatous mimic and should be visible when relevant.

    immune_status:
      reason: GLILD and opportunistic infection can complicate granulomatous reasoning.

    prior_CT:
      reason: Temporal behavior may distinguish sarcoid stability, HP recurrence, fibrotic evolution, or superimposed disease.

    tissue_context:
      reason: Granulomas require clinical, radiologic, exposure, and microbiologic context.

    MDD_review:
      reason: Sarcoidosis-vs-HP often requires integrated radiology, pulmonary, exposure, pathology, and microbiology context.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  behavior_supporting_sarcoidosis_like_course:
    clues:
      - stable_or_regressing_symmetric_nodes
      - stable_or_regressing_perilymphatic_nodules
      - prior_typical_sarcoid_distribution
      - upper_perihilar_fibrotic_evolution_in_known_context
    caution:
      - stability_or_regression_does_not_alone_prove_sarcoidosis

  behavior_supporting_HP_like_course:
    clues:
      - recurrent_worsening_after_exposure
      - improvement_after_exposure_control
      - persistent_or_increasing_air_trapping
      - transition_from_centrilobular_GGO_nodules_to_fibrosis
      - fluctuating_inflammatory_component
    caution:
      - exposure_response_supports_HP_but_does_not_prove_it

  rapid_worsening:
    consider:
      - infection
      - HP_flare_or_exposure_rechallenge
      - sarcoidosis_inflammatory_activity
      - drug_toxicity
      - pulmonary_embolism
      - malignancy_or_superimposed_event
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - sarcoidosis_like_pattern_with_air_trapping
    - small_nodule_distribution_uncertain
    - exposure_history_positive_but_sarcoid_pattern_classic
    - fibrotic_sarcoidosis_vs_fibrotic_HP_uncertainty
    - tissue_result_and_HRCT_context_conflict
    - infection_or_malignancy_mimic_not_excluded

  exposure_review_high_value_if:
    - centrilobular_nodules
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - recurrent_worsening
    - suspected_bird_mold_humidifier_hot_tub_farming_or_workplace_exposure

  microbiology_review_high_value_if:
    - infection_context_present
    - tree_in_bud
    - cavitation
    - immune_suppression
    - granulomatous_tissue_context_without_exclusion

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
  - title: Calling sarcoidosis from small nodules alone.
    correction: Nodule distribution must be analyzed; HP often produces centrilobular ground-glass nodules.

  - title: Ignoring air trapping.
    correction: Air trapping and three-density pattern are high-value HP clues.

  - title: Treating exposure history as proof of HP.
    correction: Exposure supports HP only when integrated with HRCT, BAL/pathology, clinical context, and MDD.

  - title: Treating lymphadenopathy as proof of sarcoidosis.
    correction: Lymphadenopathy can also occur in infection, malignancy, GLILD, and occupational mimics.

  - title: Ignoring infection in granulomatous disease.
    correction: Infection must remain visible before increasing sarcoidosis confidence.

  - title: Assuming fibrotic upper-lung disease means sarcoidosis.
    correction: Chronic HP, pneumoconiosis, PPFE, and post-infectious fibrosis may mimic fibrotic sarcoidosis.

  - title: Letting tissue override context.
    correction: Granulomas require clinical, radiologic, microbiologic, and exposure context.
```

---

## 11. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - ATS_JRS_ALAT_2020_HP_DIAGNOSIS

  secondary_sources:
    - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    - CT_IMAGING_FEATURES_PULMONARY_SARCOIDOSIS_REVIEW
    - HP_IMAGING_AND_DIAGNOSIS_REVIEW_SOURCES

  evidence_notes:
    - Sarcoidosis reasoning requires compatible context and exclusion of alternative granulomatous disease.
    - HP reasoning requires exposure assessment, HRCT pattern, BAL/pathology when appropriate, and MDD integration.
    - Imaging pattern distribution is central: perilymphatic favors sarcoidosis-like reasoning, centrilobular/air-trapping favors HP-like reasoning.
```

---

## 12. MVP Test Case

```yaml
case_test_sarcoidosis_vs_hp_001:
  input:
    age: 50
    sex: female
    hrct:
      - small_pulmonary_nodules
      - mediastinal_lymphadenopathy
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
      - no_cavitation_reported
    history:
      bird_exposure: unknown
      mold_exposure: unknown
      occupational_exposure: unknown
      extrapulmonary_sarcoid_features: unknown
      infection_review: unknown
      prior_CT: unavailable
    laboratory:
      BAL_lymphocytosis: unavailable
      immune_status: unknown
    tissue:
      granulomas: unavailable

  output:
    reasoning_state: sarcoidosis_vs_HP_gray_zone
    sarcoidosis_support:
      - mediastinal_lymphadenopathy
      - possible_granulomatous_pattern
    hp_support:
      - mosaic_attenuation
      - air_trapping_on_expiratory_CT
    cannot_conclude:
      - sarcoidosis
      - hypersensitivity_pneumonitis
      - granulomatous_infection_excluded
      - GLILD_excluded
    missing_pieces:
      - nodule_distribution_analysis
      - detailed_exposure_history
      - expiratory_HRCT_quality_review
      - BAL_lymphocytosis_if_clinically_relevant
      - infection_review
      - immune_status
      - prior_CT
      - MDD_review
    final_prompt:
      - What do we still not know before choosing between sarcoidosis-like and HP-like granulomatous ILD?
```

---

## 13. Final Page Prompt

Every Sarcoidosis vs HP gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Are nodules perilymphatic, centrilobular, or random?
2. Is lymphadenopathy dominant, symmetric, necrotic, asymmetric, or progressive?
3. Is there air trapping, mosaic attenuation, or three-density pattern?
4. Is exposure history high-quality or incomplete?
5. Is BAL lymphocytosis available or relevant?
6. Has infection, GLILD, occupational mimic, and malignancy context been considered?
7. What does the prior CT show?
8. What do we still not know?
```