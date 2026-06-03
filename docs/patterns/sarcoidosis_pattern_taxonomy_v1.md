# Sarcoidosis Pattern Taxonomy — v1

## Document Metadata

```yaml
id: pattern_sarcoidosis_taxonomy_v1
title: Sarcoidosis Pattern Taxonomy
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: pattern_taxonomy
diagnostic_authority: none
linked_pattern:
  - sarcoidosis_pattern_gold_standard_v1
linked_reasoning_maps:
  - granulomatous_ild_reasoning_map_v1
last_updated: draft
```

---

## 0. Purpose

This taxonomy defines the thoracic imaging pattern families of sarcoidosis for the ILD Reasoning Platform.

It does not diagnose sarcoidosis.

It helps users separate:

- typical sarcoidosis-like patterns,
- atypical sarcoidosis-like patterns,
- fibrotic sarcoidosis patterns,
- airway-dominant patterns,
- alveolar/consolidative patterns,
- nodular/mass-like patterns,
- miliary-like or random nodular mimics,
- and pattern-mimic red flags.

The taxonomy must preserve the central diagnostic rule:

```text
Sarcoidosis-like imaging supports reasoning, not diagnosis.
Alternative granulomatous causes must remain visible.
```

---

## 1. Source Backbone

```yaml
source_backbone:
  diagnostic_framework:
    primary_source: ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    role:
      - compatible_clinical_presentation
      - nonnecrotizing_granulomatous_inflammation_when_needed_or_available
      - exclusion_of_alternative_granulomatous_disease

  pulmonary_context:
    primary_source: BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    role:
      - pulmonary_sarcoidosis_diagnosis_context
      - evaluation_and_monitoring_context
      - clinical_practice_points

  imaging_pattern_context:
    sources:
      - CT_IMAGING_FEATURES_PULMONARY_SARCOIDOSIS_2025_REVIEW
      - classic_radiology_reviews_of_typical_and_atypical_sarcoidosis
    role:
      - typical_patterns
      - atypical_patterns
      - fibrotic_patterns
      - mimic_awareness
```

---

## 2. High-Level Pattern Families

```yaml
sarcoidosis_pattern_families:
  - typical_nodal_perilymphatic_pattern
  - parenchymal_perilymphatic_nodular_pattern
  - alveolar_or_consolidative_pattern
  - nodular_or_mass_like_pattern
  - miliary_like_or_random_nodular_pattern
  - airway_dominant_pattern
  - fibrotic_sarcoidosis_pattern
  - fibrocystic_or_cystic_complication_pattern
  - pleural_or_rare_manifestation_pattern
  - atypical_or_mimic_dominant_pattern
```

---

## 3. Typical Nodal-Perilymphatic Pattern

```yaml
typical_nodal_perilymphatic_pattern:
  core_signature:
    - bilateral_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - perilymphatic_micronodules
    - upper_or_mid_lung_predominance

  nodule_distribution:
    - peribronchovascular
    - fissural
    - subpleural
    - interlobular_septal_or_perilymphatic

  supports_sarcoidosis_reasoning:
    - symmetric_bilateral_hilar_or_mediastinal_nodes
    - nodules_along_fissures
    - nodules_along_bronchovascular_bundles
    - compatible_clinical_context

  weakens_simple_sarcoidosis_reasoning:
    - necrotic_nodes
    - asymmetric_progressive_nodes
    - cavitation
    - tree_in_bud
    - random_nodules
    - known_malignancy_context

  missing_pieces:
    - infection_review
    - occupational_exposure_history
    - extrapulmonary_review
    - prior_CT
    - tissue_context_if_needed
```

---

## 4. Parenchymal Perilymphatic Nodular Pattern

```yaml
parenchymal_perilymphatic_nodular_pattern:
  core_signature:
    - perilymphatic_micronodules
    - fissural_beading
    - peribronchovascular_nodularity
    - upper_mid_lung_bias_possible

  key_question:
    - Are the nodules truly perilymphatic?

  mimics:
    - pneumoconiosis
    - lymphangitic_malignancy_context_dependent
    - HP_if_centrilobular_not_perilymphatic
    - miliary_infection_if_random
    - metastases_if_random_or_variable_size

  pitfall:
    - Do_not_label_all_small_nodules_as_sarcoidosis_without_distribution_analysis
```

---

## 5. Alveolar or Consolidative Sarcoidosis-like Pattern

```yaml
alveolar_or_consolidative_pattern:
  core_signature:
    - patchy_airspace_opacities
    - consolidation_like_opacities
    - nodular_coalescence_possible
    - may_coexist_with_perilymphatic_nodules_or_nodes

  supports_sarcoidosis_reasoning:
    - coexisting_typical_lymphadenopathy
    - coexisting_perilymphatic_nodules
    - chronic_or_recurrent_context_consistent_with_sarcoidosis

  major_mimics:
    - organizing_pneumonia
    - infection
    - lymphoma
    - adenocarcinoma
    - drug_toxicity

  red_flags:
    - persistent_asymmetric_consolidation
    - rapid_new_consolidation
    - systemic_infectious_context
    - known_malignancy_context

  missing_pieces:
    - prior_CT
    - infection_review
    - malignancy_review_if_persistent
    - treatment_or_time_response_context
```

---

## 6. Nodular or Mass-like Sarcoidosis-like Pattern

```yaml
nodular_or_mass_like_pattern:
  core_signature:
    - large_nodules
    - mass_like_opacities
    - clustered_or_coalescent_nodules
    - possible_galaxy_like_or_clustered_pattern

  supports_sarcoidosis_reasoning:
    - typical_nodes_or_perilymphatic_background
    - multiplicity_with_sarcoid_distribution
    - compatible_multisystem_context

  major_mimics:
    - malignancy
    - lymphoma
    - fungal_infection
    - TB
    - GPA_or_vasculitis
    - rheumatoid_nodules

  red_flags:
    - solitary_dominant_mass
    - rapid_growth
    - cavitation
    - known_cancer_history
    - asymmetric_progressive_nodes

  missing_pieces:
    - prior_CT
    - cancer_history
    - microbiology_when_relevant
    - tissue_context_if_needed
    - MDD_review
```

---

## 7. Miliary-like or Random Nodular Pattern

```yaml
miliary_like_or_random_nodular_pattern:
  core_signature:
    - numerous_tiny_nodules
    - random_or_miliary_like_distribution_possible

  caution:
    - This is atypical for classic sarcoidosis reasoning and requires strong mimic review.

  major_mimics:
    - miliary_TB
    - fungal_infection
    - hematogenous_metastases
    - pneumoconiosis
    - HP_if_centrilobular_distribution

  key_question:
    - Is the distribution truly random, perilymphatic, or centrilobular?

  missing_pieces:
    - infection_review
    - immune_status
    - cancer_history
    - occupational_exposure_history
    - nodule_distribution_analysis
```

---

## 8. Airway-Dominant Sarcoidosis Pattern

```yaml
airway_dominant_pattern:
  core_signature:
    - bronchial_wall_thickening
    - airway_narrowing
    - tracheobronchial_involvement_possible
    - air_trapping_possible
    - mosaic_attenuation_possible

  supports_sarcoidosis_reasoning:
    - coexisting_typical_nodes_or_perilymphatic_nodules
    - endobronchial_sarcoid_context
    - compatible_clinical_context

  major_mimics:
    - HP
    - asthma_or_small_airways_disease
    - infection
    - GPA_or_tracheobronchial_disease
    - relapsing_polychondritis_context

  key_question:
    - Is air trapping part of sarcoidosis airway involvement, HP, or another airway disease?

  missing_pieces:
    - expiratory_HRCT
    - exposure_history
    - airway_symptoms
    - bronchoscopy_context_if_relevant
```

---

## 9. Fibrotic Sarcoidosis Pattern

```yaml
fibrotic_sarcoidosis_pattern:
  core_signature:
    - upper_lung_or_perihilar_fibrosis
    - architectural_distortion
    - traction_bronchiectasis
    - volume_loss
    - hilar_retraction
    - bronchovascular_distortion
    - fibrocystic_change_possible

  supports_sarcoidosis_reasoning:
    - prior_typical_sarcoid_pattern
    - residual_perilymphatic_nodularity
    - upper_or_perihilar_fibrotic_distribution
    - compatible_clinical_history

  major_mimics:
    - chronic_HP
    - pneumoconiosis
    - PPFE
    - post_infectious_fibrosis
    - fibrotic_ILD_with_upper_lobe_bias

  complications_to_consider:
    - pulmonary_hypertension
    - aspergilloma
    - chronic_cavitary_complication
    - recurrent_infection
    - airway_distortion

  missing_pieces:
    - prior_CT
    - exposure_occupational_history
    - pulmonary_hypertension_assessment_context
    - infection_or_aspergilloma_review_when_cavitary_change_present
```

---

## 10. Fibrocystic or Cystic Complication Pattern

```yaml
fibrocystic_or_cystic_complication_pattern:
  core_signature:
    - fibrotic_distortion_with_cystic_or_cavitary_appearing_spaces
    - upper_lung_bias_possible
    - traction_related_airway_distortion
    - chronic_complication_context

  caution:
    - Cystic or cavitary-appearing change in sarcoidosis requires careful separation from infection, aspergilloma, emphysema, and other cystic lung disease.

  major_mimics:
    - chronic_cavitary_infection
    - aspergilloma
    - PLCH
    - emphysema
    - honeycombing_like_fibrosis
    - malignancy_with_cavitation

  missing_pieces:
    - prior_CT
    - microbiology_when_relevant
    - fungal_or_aspergillus_context
    - smoking_history
    - malignancy_review_if_new_or_asymmetric
```

---

## 11. Pleural or Rare Manifestation Pattern

```yaml
pleural_or_rare_manifestation_pattern:
  possible_features:
    - pleural_effusion
    - pleural_thickening
    - pneumothorax_context
    - rare_manifestations

  caution:
    - Pleural-dominant disease is not typical simple sarcoidosis reasoning and should trigger mimic review.

  mimics:
    - infection
    - malignancy
    - heart_failure_or_systemic_cause
    - connective_tissue_disease
```

---

## 12. Atypical or Mimic-Dominant Pattern

```yaml
atypical_or_mimic_dominant_pattern:
  atypical_features:
    - unilateral_lymphadenopathy
    - asymmetric_progressive_lymphadenopathy
    - necrotic_nodes
    - cavitation
    - random_nodules
    - dominant_mass
    - lower_lung_dominance
    - dominant_consolidation
    - pleural_dominance

  required_response:
    - preserve_uncertainty
    - strengthen_mimic_review
    - review_infection
    - review_malignancy
    - review_occupational_exposure
    - review_HP_and_GLILD_when_relevant
    - consider_tissue_or_sampling_context_if_needed
```

---

## 13. Pattern-to-Mimic Matrix

| Pattern family | Key mimics to keep visible |
|---|---|
| Typical nodal-perilymphatic | Infection, lymphoma, berylliosis, pneumoconiosis, malignancy |
| Perilymphatic nodular | Pneumoconiosis, lymphangitic malignancy, HP if centrilobular |
| Alveolar/consolidative | OP, infection, lymphoma, adenocarcinoma, drug toxicity |
| Nodular/mass-like | Malignancy, fungal infection, TB, GPA, lymphoma |
| Miliary-like/random nodular | Miliary TB, fungal infection, metastases |
| Airway-dominant | HP, small-airways disease, infection, GPA |
| Fibrotic sarcoidosis | Chronic HP, pneumoconiosis, PPFE, post-infectious fibrosis |
| Fibrocystic/cystic | Aspergilloma, cavitary infection, PLCH, emphysema, malignancy |

---

## 14. Why Not Engine

```yaml
why_not_sarcoidosis:
  - atypical_distribution_without_supporting_context
  - necrotic_nodes
  - cavitation
  - tree_in_bud
  - random_nodules
  - dominant_mass_or_asymmetric_growth
  - known_malignancy_context
  - immune_deficiency_context
  - strong_HP_air_trapping_exposure_pattern
  - occupational_beryllium_silica_or_dust_context
```

---

## 15. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  high_yield_missing_data:
    nodule_distribution_analysis:
      reason: Perilymphatic, centrilobular, and random nodules imply different pathways.

    lymph_node_characterization:
      reason: Symmetric, asymmetric, necrotic, calcified, or progressive nodes carry different implications.

    infection_review:
      reason: TB, fungal infection, and opportunistic infection can mimic sarcoidosis.

    occupational_exposure_history:
      reason: Berylliosis, silicosis, and pneumoconiosis can mimic sarcoidosis.

    exposure_history_for_HP:
      reason: HP may mimic or overlap with granulomatous ILD reasoning.

    immune_status:
      reason: GLILD and opportunistic infections require immune deficiency review.

    cancer_history:
      reason: Malignancy and sarcoid-like reaction can mimic sarcoidosis.

    prior_CT:
      reason: Stability, progression, regression, or new focal change may redirect reasoning.

    tissue_context_if_needed:
      reason: Granulomas require context and exclusion of alternatives.
```

---

## 16. Taxonomy Output Rule

This taxonomy should help the user output:

```yaml
taxonomy_output:
  pattern_family: string
  typicality_level:
    - typical
    - compatible
    - atypical
    - mimic_dominant
  key_supporting_features: list[string]
  key_mimics: list[string]
  missing_pieces: list[string]
  final_prompt: What do we still not know?
```

---

## 17. MVP Test Case

```yaml
case_test_sarcoidosis_taxonomy_001:
  input:
    hrct:
      - bilateral_hilar_lymphadenopathy
      - perilymphatic_micronodules
      - fissural_nodules
      - upper_lung_predominance
    history:
      infection_review: unavailable
      occupational_exposure: unknown
      immune_status: unknown
      cancer_history: unknown
      prior_CT: unavailable

  output:
    pattern_family: typical_nodal_perilymphatic_pattern
    typicality_level: typical_sarcoidosis_like_pattern
    key_supporting_features:
      - bilateral_hilar_lymphadenopathy
      - perilymphatic_micronodules
      - fissural_nodules
      - upper_lung_predominance
    key_mimics:
      - granulomatous_infection
      - berylliosis_or_pneumoconiosis
      - lymphoma_or_malignancy_context_dependent
      - HP_if_distribution_reinterpreted_as_centrilobular
    missing_pieces:
      - infection_review
      - occupational_exposure_history
      - immune_status
      - cancer_history
      - prior_CT
    final_prompt:
      - What alternative granulomatous causes remain possible?
```

---

## 18. Final Taxonomy Prompt

Every sarcoidosis taxonomy page should end with:

```text
Do not force the label.

Ask:
1. Which sarcoidosis-like pattern family is present?
2. Is it typical, compatible, atypical, or mimic-dominant?
3. Are nodules perilymphatic, centrilobular, or random?
4. Are nodes symmetric, asymmetric, necrotic, calcified, or progressive?
5. Is there infection, HP, occupational, immune deficiency, vasculitic, or malignancy context?
6. What does the prior CT show?
7. What do we still not know?
```