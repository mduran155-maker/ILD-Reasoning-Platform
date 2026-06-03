# Sarcoidosis Pattern Atlas — Gold Standard Datasheet v1

## Document Metadata

```yaml
id: pattern_sarcoidosis_gold_standard_v1
title: Sarcoidosis Pattern Atlas — Gold Standard Datasheet
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: pattern_datasheet
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - rheumatologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
diagnostic_authority: none
last_updated: draft
linked_reasoning_maps:
  - granulomatous_ild_reasoning_map_v1
```

---

## 0. Platform Safety Statement

This platform does not diagnose patients, classify individual cases, or recommend treatment.

It supports structured clinical reasoning in sarcoidosis and granulomatous ILD by helping users understand:

- why sarcoidosis is being considered,
- which mimics remain possible,
- which findings weaken a sarcoidosis pathway,
- what information is missing,
- when tissue or microbiology may be needed,
- and when multidisciplinary discussion may be required.

> **Core principle:**  
> Diagnosing ILD is not about finding the right answer.  
> It is about asking the right next question — and knowing when you don’t have enough information yet.

---

## 1. Identity

```yaml
pattern_id: sarcoidosis
full_name: Thoracic Sarcoidosis Pattern
short_name: Sarcoidosis
category: Granulomatous Interstitial / Perilymphatic / Nodal Lung Disease Pattern
primary_domain: HRCT Pattern Recognition + Granulomatous ILD Reasoning
clinical_role: Pattern-level reasoning, not disease-level diagnosis
important_distinction: Sarcoidosis is not diagnosed by imaging alone; alternative granulomatous causes must be considered.
```

### Related Disease Contexts

```yaml
related_disease_contexts:
  - Pulmonary sarcoidosis
  - Fibrotic sarcoidosis
  - Nodular sarcoidosis
  - Alveolar sarcoidosis pattern
  - Airway sarcoidosis
  - Cardiac sarcoidosis context
  - Sarcoid-like reaction
  - Granulomatous infection mimic
  - Hypersensitivity Pneumonitis mimic
  - GLILD mimic
  - Berylliosis mimic
  - Pneumoconiosis mimic
  - Malignancy mimic
```

---

## 2. Pattern Summary

```yaml
one_sentence_summary: >
  Thoracic sarcoidosis most commonly presents with bilateral hilar and/or mediastinal
  lymphadenopathy and perilymphatic pulmonary nodules, often with upper or mid-lung
  predominance, but it can also present with atypical patterns including alveolar
  opacities, mass-like nodules, miliary nodules, airway disease, fibrotic distortion,
  cystic/fibrocystic change, and lower-lung involvement.

danger_statement: >
  Sarcoidosis-like imaging does not establish sarcoidosis; infection, occupational
  granulomatous disease, HP, GLILD, vasculitis, lymphoma, malignancy, and sarcoid-like
  reaction must remain visible when relevant.
```

### Key Teaching Point

Sarcoidosis reasoning starts with pattern recognition, but it should not end there.

```text
Sarcoidosis requires compatible context + exclusion of alternative granulomatous disease.
```

---

## 3. Diagnostic Framework

```yaml
diagnostic_framework:
  core_principles:
    - compatible_clinical_radiologic_context
    - nonnecrotizing_granulomatous_inflammation_when_tissue_is_required_or_available
    - exclusion_of_alternative_granulomatous_causes

  platform_rule:
    - imaging_can_support_sarcoidosis_reasoning
    - imaging_alone_should_not_be_used_as_final_diagnosis
    - tissue_may_not_be_required_in_every_classic_case_but_uncertainty_must_be_visible
    - infection_and_occupational_mimics_must_be_considered_when_relevant
```

---

## 4. Thoracic Pattern Family

### 4.1 Typical Nodal-Perilymphatic Pattern

```yaml
typical_nodal_perilymphatic_pattern:
  supportive_features:
    - bilateral_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - perilymphatic_micronodules
    - nodules_along_bronchovascular_bundles
    - fissural_nodules
    - subpleural_nodules
    - upper_or_mid_lung_predominance

  reasoning_note:
    - This is the classic thoracic sarcoidosis pattern, but mimics still exist.
```

### 4.2 Parenchymal Nodular Pattern

```yaml
parenchymal_nodular_pattern:
  supportive_features:
    - perilymphatic_nodules
    - clustered_nodules
    - larger_nodular_opacities_possible
    - upper_or_mid_lung_bias_possible

  key_question:
    - Are the nodules truly perilymphatic, centrilobular, or random?

  mimics:
    - hypersensitivity_pneumonitis
    - pneumoconiosis
    - miliary_infection
    - metastases
    - lymphangitic_carcinomatosis
```

### 4.3 Alveolar / Consolidative Sarcoidosis Pattern

```yaml
alveolar_or_consolidative_pattern:
  supportive_features:
    - patchy_airspace_opacities
    - consolidation_like_opacities
    - nodular_coalescence_possible
    - may_coexist_with_typical_nodes_or_perilymphatic_nodules

  caution:
    - This pattern can mimic organizing pneumonia, infection, lymphoma, or malignancy.

  missing_pieces:
    - prior_CT
    - symptoms_and_inflammatory_context
    - infection_review
    - malignancy_review_if_persistent_or_asymmetric
```

### 4.4 Fibrotic Sarcoidosis Pattern

```yaml
fibrotic_sarcoidosis_pattern:
  supportive_features:
    - upper_lung_or_perihilar_fibrosis
    - architectural_distortion
    - traction_bronchiectasis
    - volume_loss
    - hilar_retraction
    - bronchovascular_bundle_distortion
    - fibrocystic_change_possible

  complications_to_consider:
    - pulmonary_hypertension
    - aspergilloma_or_chronic_cavitary_complication
    - airway_distortion
    - recurrent_infection

  gray_zone:
    - chronic_HP
    - pneumoconiosis
    - PPFE
    - post_infectious_fibrosis
```

### 4.5 Airway Sarcoidosis Pattern

```yaml
airway_sarcoidosis_pattern:
  supportive_features:
    - bronchial_wall_thickening
    - airway_narrowing_or_stenosis
    - air_trapping_possible
    - mosaic_attenuation_possible
    - endobronchial_or_tracheobronchial_involvement_possible

  caution:
    - Air trapping should also trigger HP and small-airways disease review.
```

### 4.6 Atypical / Lower-Lung / Miliary-like Pattern

```yaml
atypical_pattern_group:
  possible_features:
    - lower_lung_predominance
    - miliary_or_random_appearing_nodules
    - unilateral_or_asymmetric_findings
    - pleural_involvement
    - cystic_or_fibrocystic_change
    - mass_like_opacity

  danger_statement:
    - Atypical patterns require stronger mimic review and often higher diagnostic caution.
```

---

## 5. HRCT Imaging Anatomy

```yaml
imaging_anatomy:
  lymph_nodes:
    supportive:
      - bilateral_hilar_lymphadenopathy
      - right_paratracheal_lymphadenopathy
      - mediastinal_lymphadenopathy
      - symmetric_distribution
    caution:
      - asymmetric_or_progressive_nodes_should_prompt_malignancy_infection_or_lymphoma_review
      - necrotic_nodes_are_not_typical_and_should_prompt_infection_or_malignancy_review

  nodules:
    supportive:
      - perilymphatic_distribution
      - fissural_distribution
      - peribronchovascular_distribution
      - subpleural_distribution
    caution:
      - centrilobular_nodules_prompt_HP_or_bronchiolitis_review
      - random_nodules_prompt_miliary_infection_or_metastatic_review

  parenchymal_opacities:
    supportive:
      - upper_mid_lung_predominance
      - peribronchovascular_opacities
      - nodular_coalescence
    caution:
      - dominant_consolidation_requires_OP_infection_malignancy_review

  fibrosis:
    supportive:
      - upper_lung_fibrosis
      - perihilar_fibrosis
      - bronchovascular_distortion
      - traction_bronchiectasis
      - volume_loss
    caution:
      - fibrotic_sarcoidosis_may_mimic_chronic_HP_or_pneumoconiosis
```

---

## 6. Confidence Levels

```yaml
confidence_levels:
  typical_sarcoidosis_pattern:
    supportive_features:
      - bilateral_hilar_or_mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_or_mid_lung_predominance
      - compatible_clinical_context
      - no_major_mimic_signal
    interpretation: Strong sarcoidosis-like pattern, but not a final diagnosis.

  compatible_sarcoidosis_pattern:
    supportive_features:
      - lymphadenopathy_or_perilymphatic_nodules_present
      - distribution_partially_supportive
      - atypical_features_absent_or_limited
    interpretation: Sarcoidosis remains possible; missing clinical, tissue, infection, or exposure data may be decisive.

  atypical_or_gray_zone_sarcoidosis_pattern:
    supportive_features:
      - atypical_distribution
      - consolidation_or_mass_like_opacity
      - lower_lung_involvement
      - miliary_or_random_appearing_nodules
      - airway_or_fibrotic_dominance
    interpretation: Preserve uncertainty and compare against infection, HP, GLILD, malignancy, and occupational mimics.

  alternative_diagnosis_suggested:
    supportive_features:
      - necrotic_lymph_nodes
      - cavitation
      - tree_in_bud
      - strong_exposure_HP_pattern
      - known_malignancy_with_new_asymmetric_nodes_or_mass
      - immune_deficiency_context
    interpretation: Pause sarcoidosis pathway and evaluate stronger alternatives.
```

---

## 7. Differential Field

```yaml
core_question_1: Is the imaging pattern sarcoidosis-like?
core_question_2: Are there granulomatous mimics that remain possible?
core_question_3: Is tissue or microbiology needed before confidence increases?
```

```yaml
differential_contexts:
  sarcoidosis:
    supports:
      - bilateral_hilar_or_mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_or_mid_lung_predominance
      - compatible_extrapulmonary_features
      - nonnecrotizing_granulomas_if_available
    weakens:
      - cavitation
      - necrotic_nodes
      - tree_in_bud
      - random_nodules
      - strong_infection_context
      - strong_occupational_or_HP_context
      - known_malignancy_with_asymmetric_progression

  granulomatous_infection:
    supports:
      - fever_or_infectious_syndrome
      - cavitation
      - tree_in_bud
      - necrotizing_granulomas
      - immunosuppression
      - TB_or_fungal_exposure
    weakens:
      - chronic_stable_typical_sarcoid_pattern
      - no_microbiologic_or_clinical_support_when_appropriately_reviewed

  hypersensitivity_pneumonitis:
    supports:
      - exposure_history
      - centrilobular_ground_glass_nodules
      - air_trapping
      - mosaic_attenuation
      - three_density_pattern
      - BAL_lymphocytosis_when_available
    weakens:
      - perilymphatic_distribution
      - symmetric_hilar_lymphadenopathy_dominant
      - absent_airway_centered_features

  berylliosis_or_pneumoconiosis:
    supports:
      - occupational_exposure
      - metal_or_beryllium_context
      - silica_or_dust_context
      - nodal_or_perilymphatic_mimic
    weakens:
      - no_occupational_exposure_after_high_quality_review

  glild:
    supports:
      - CVID_or_immune_deficiency_context
      - recurrent_infections
      - hypogammaglobulinemia
      - splenomegaly
      - lymphadenopathy
      - nodules_GGO_or_consolidation
    weakens:
      - no_immune_deficiency_context

  gpa_or_vasculitis:
    supports:
      - cavitating_nodules
      - sinonasal_disease
      - renal_findings
      - hematuria
      - ANCA_context
      - airway_stenosis
    weakens:
      - classic_symmetric_sarcoid_pattern_without_vasculitic_context

  malignancy_or_sarcoid_like_reaction:
    supports:
      - known_malignancy
      - new_or_progressive_asymmetric_lymphadenopathy
      - new_mass_or_nodule
      - therapy_related_context
      - discordant_clinical_course
    weakens:
      - stable_typical_sarcoid_pattern_without_cancer_context
```

---

## 8. Gray Zone Links

```yaml
gray_zone_links:
  - sarcoidosis_vs_granulomatous_infection
  - sarcoidosis_vs_hp
  - sarcoidosis_vs_glild
  - sarcoidosis_vs_berylliosis_or_pneumoconiosis
  - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction
  - fibrotic_sarcoidosis_vs_chronic_hp
```

---

## 9. Why Not Engine

```yaml
why_not_sarcoidosis:
  - infection_not_reviewed
  - necrotic_nodes
  - cavitation
  - tree_in_bud
  - random_nodules
  - strong_HP_exposure_or_air_trapping_pattern
  - immune_deficiency_context
  - occupational_beryllium_or_silica_context
  - known_malignancy_or_asymmetric_progression
  - vasculitic_sinonasal_or_renal_context

why_not_infection:
  - no_infectious_syndrome
  - no_microbiologic_support_after_appropriate_review
  - chronic_stable_typical_sarcoid_pattern
  - noninfectious_multisystem_context_stronger

why_not_HP:
  - perilymphatic_nodules_dominate
  - symmetric_hilar_lymphadenopathy_dominates
  - no_air_trapping_on_expiratory_HRCT
  - no_exposure_after_high_quality_review
```

---

## 10. Missing Piece Candidates

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  high_yield_missing_data:
    infection_review:
      reason: Granulomatous infection can mimic sarcoidosis and may change management risk.

    microbiology:
      reason: TB, fungal infection, and opportunistic infection may need exclusion when clinically relevant.

    tissue_context:
      reason: Granulomas require clinical and microbiologic context; tissue alone may not be enough.

    exposure_and_occupational_history:
      reason: HP, berylliosis, silicosis, and pneumoconiosis can mimic sarcoidosis.

    immune_status:
      reason: GLILD and opportunistic infections require immune deficiency review.

    cancer_history:
      reason: Malignancy and sarcoid-like reaction can mimic nodal or nodular sarcoidosis.

    extrapulmonary_review:
      reason: Eye, skin, cardiac, neurologic, hepatic, calcium, and constitutional features may change reasoning.

    prior_CT:
      reason: Stability, progression, spontaneous regression, infection, malignancy, or fibrotic evolution may become visible over time.

    MDD_review:
      reason: Granulomatous ILD often requires integration of imaging, pulmonology, pathology, microbiology, exposure, and sometimes oncology/immunology.
```

---

## 11. Temporal Behavior

```yaml
temporal_behavior:
  spontaneous_improvement_or_regression:
    supportive_changes:
      - decreasing_lymphadenopathy
      - decreasing_nodular_burden
      - improving_parenchymal_opacities
    caution:
      - improvement_does_not_prove_sarcoidosis_without_context

  stabilization:
    supportive_changes:
      - stable_nodes
      - stable_perilymphatic_nodules
      - stable_fibrotic_distortion
    caution:
      - stable_disease_can_remain_diagnostically_uncertain

  progression:
    supportive_changes:
      - increasing_fibrosis
      - increasing_airway_distortion
      - increasing_volume_loss
      - increasing_pulmonary_hypertension_clues
    consider:
      - fibrotic_sarcoidosis
      - chronic_HP
      - pneumoconiosis
      - alternative_fibrotic_ILD

  unexpectedly_fast_worsening:
    consider:
      - infection
      - drug_toxicity
      - pulmonary_embolism
      - pulmonary_edema
      - malignancy
      - inflammatory_flare
```

---

## 12. Pattern Interactions

```yaml
pattern_interactions:
  lymphadenopathy_plus_perilymphatic_nodules:
    consider:
      - sarcoidosis
      - pneumoconiosis
      - lymphangitic_malignancy_context_dependent
    questions:
      - Is nodal disease symmetric?
      - Are nodules along fissures and bronchovascular bundles?
      - Is there occupational exposure?

  granulomatous_pattern_plus_air_trapping:
    consider:
      - HP
      - airway_sarcoidosis
      - small_airways_disease
    questions:
      - Is expiratory HRCT available?
      - Are nodules centrilobular or perilymphatic?
      - Is there exposure history?

  sarcoid_like_pattern_plus_cavitation:
    consider:
      - infection
      - GPA
      - malignancy
      - rheumatoid_nodule_context
    questions:
      - Is this atypical for sarcoidosis?
      - Is microbiology or vasculitis review needed?

  sarcoid_like_pattern_plus_fibrosis:
    consider:
      - fibrotic_sarcoidosis
      - chronic_HP
      - pneumoconiosis
      - PPFE
    questions:
      - Is fibrosis upper/perihilar or lower/subpleural?
      - Are there residual perilymphatic nodules?
      - Is exposure history relevant?
```

---

## 13. Superimposed Events

```yaml
superimposed_events:
  new_ground_glass_or_consolidation:
    consider:
      - infection
      - organizing_pneumonia
      - drug_toxicity
      - inflammatory_flare
      - malignancy
    warning: New opacity should not automatically be called sarcoid progression.

  new_nodule_or_mass:
    consider:
      - malignancy
      - infection
      - sarcoid_nodule
      - sarcoid_like_reaction
    warning: New focal lesions require dedicated review.

  new_or_progressive_asymmetric_lymphadenopathy:
    consider:
      - lymphoma
      - malignancy
      - infection
      - atypical_sarcoid_course
    warning: Asymmetry and progression should not be dismissed.

  rapid_clinical_decline:
    consider:
      - infection
      - pulmonary_embolism
      - pulmonary_hypertension
      - cardiac_sarcoidosis_context
      - treatment_related_complication
```

---

## 14. Diagnostic Escalation

```yaml
diagnostic_escalation:
  mdd_needed_if:
    - infection_vs_sarcoidosis_uncertainty
    - malignancy_context_present
    - occupational_mimic_possible
    - immune_deficiency_context_present
    - vasculitis_context_present
    - tissue_result_and_imaging_context_conflict
    - treatment_decision_depends_on_diagnostic_confidence

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_review
    - infection_or_malignancy_must_be_excluded
    - accessible_lymph_node_or_organ_target_exists
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need

  microbiology_review_high_value_if:
    - cavitation
    - tree_in_bud
    - necrotizing_granuloma
    - immunosuppression
    - TB_or_fungal_exposure_context
    - systemic_infectious_features

  occupational_review_high_value_if:
    - beryllium_or_metal_exposure_possible
    - silica_or_dust_exposure_possible
    - pneumoconiosis_mimic_possible

  immunology_review_high_value_if:
    - recurrent_infections
    - hypogammaglobulinemia
    - CVID_context
    - GLILD_suspected
```

---

## 15. Pitfall Library

```yaml
pitfalls:
  - title: Calling sarcoidosis from imaging alone.
    correction: Imaging may support sarcoidosis, but alternative granulomatous causes must remain visible.

  - title: Ignoring infection.
    correction: TB, fungal infection, and opportunistic infection must be considered when relevant.

  - title: Treating all small nodules as sarcoid nodules.
    correction: Nodule distribution matters: perilymphatic, centrilobular, and random patterns imply different pathways.

  - title: Missing HP.
    correction: Air trapping, mosaic attenuation, centrilobular nodules, and exposure history should prompt HP review.

  - title: Missing occupational mimics.
    correction: Berylliosis and silicosis can mimic sarcoidosis and require occupational history.

  - title: Missing GLILD.
    correction: Immune deficiency or CVID context should redirect granulomatous ILD reasoning.

  - title: Missing malignancy or sarcoid-like reaction.
    correction: Cancer history, asymmetric nodes, new mass, or discordant course require malignancy review.

  - title: Using treatment guideline as diagnostic authority.
    correction: Treatment guidance should not be used to establish diagnosis.
```

---

## 16. Evidence and Guideline Registry

```yaml
evidence_and_guideline_registry:
  primary_guidelines_to_link:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - BTS_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT

  secondary_guidelines_to_link:
    - ERS_2021_SARCOIDOSIS_TREATMENT

  imaging_reviews_to_link:
    - CT_IMAGING_FEATURES_PULMONARY_SARCOIDOSIS_2025_REVIEW
    - IMAGING_OF_PULMONARY_SARCOIDOSIS_2024_REVIEW

  evidence_notes:
    - ATS diagnostic framework anchors sarcoidosis reasoning.
    - BTS statement supports pulmonary sarcoidosis diagnosis/management context and highlights diagnostic complexity.
    - ERS treatment guideline should not be used as diagnostic authority.
    - Contemporary imaging reviews support the typical/atypical thoracic pattern taxonomy.
```

---

## 17. Narrative Questions

Every sarcoidosis page should end with these questions:

```yaml
narrative_questions:
  - Is this truly a sarcoidosis-like thoracic pattern?
  - Is the dominant pattern nodal, perilymphatic, alveolar, nodular, airway, fibrotic, or atypical?
  - Are nodules perilymphatic, centrilobular, or random?
  - Has infection been considered?
  - Is there occupational exposure suggesting berylliosis, silicosis, or pneumoconiosis?
  - Is HP still possible?
  - Is GLILD possible in an immune deficiency context?
  - Is malignancy or sarcoid-like reaction possible?
  - Is tissue needed, available, or potentially misleading without context?
  - What does the prior CT show?
  - What is the single most important missing piece of information?
```

---

## 18. MVP Screen Behavior

```yaml
mvp_screen_behavior:
  main_panel:
    - pattern_summary
    - thoracic_pattern_family
    - hrct_imaging_anatomy
    - confidence_levels
    - differential_field

  right_sidebar:
    - why_not_sarcoidosis
    - missing_piece_candidates
    - gray_zone_links
    - pitfall_library
    - superimposed_event_alerts
    - evidence_registry

  bottom_panel:
    - infection_review_prompt
    - exposure_occupational_prompt
    - tissue_or_sampling_prompt
    - mdd_prompt
    - what_do_we_still_not_know_prompt
```

---

## 19. MVP Test Case

```yaml
case_test_sarcoidosis_001:
  input:
    age: 42
    sex: female
    hrct:
      - bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_micronodules
      - upper_lung_predominance
      - no_cavitation
      - no_tree_in_bud
    history:
      fever: unknown
      TB_exposure: unknown
      fungal_exposure: unknown
      occupational_exposure: unknown
      bird_or_mold_exposure: unknown
      immune_deficiency: unknown
      cancer_history: unknown
      extrapulmonary_symptoms: unknown
      prior_ct: unavailable
    tissue:
      granulomas: unavailable
    microbiology:
      unavailable

  system_output:
    pattern_confidence: typical_sarcoidosis_like_pattern
    disease_statement: Sarcoidosis is possible, but not confirmed by imaging alone.
    why_not_sarcoidosis:
      - infection_review_incomplete
      - occupational_exposure_unknown
      - immune_status_unknown
      - cancer_history_unknown
      - tissue_context_unavailable
    missing_pieces:
      - infection_review
      - occupational_exposure_history
      - immune_status
      - cancer_history
      - extrapulmonary_review
      - prior_CT
      - tissue_or_sampling_context_if_needed
      - MDD_review
    final_prompt:
      - What alternative granulomatous causes remain possible before calling this sarcoidosis?
```

---

## 20. Final Page Prompt

Every Sarcoidosis Pattern page should end with:

```text
Do not force the label.

Ask:
1. Is this truly a sarcoidosis-like pattern?
2. Which thoracic pattern is dominant?
3. Are the nodules perilymphatic, centrilobular, or random?
4. Is lymphadenopathy symmetric, asymmetric, necrotic, or progressive?
5. Has infection been considered?
6. Is there occupational, exposure, immune deficiency, vasculitic, or malignancy context?
7. Is tissue needed, available, or misleading without context?
8. What does the prior CT show?
9. What do we still not know?
```