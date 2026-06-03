# Fibrotic Hypersensitivity Pneumonitis Pattern Atlas — Gold Standard Datasheet v1

## Document Metadata

```yaml
id: pattern_fibrotic_hp_gold_standard_v1
title: Fibrotic Hypersensitivity Pneumonitis Pattern Atlas — Gold Standard Datasheet
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
  - uip_vs_fibrotic_hp_gray_zone_v1
  - nsip_vs_fibrotic_hp_gray_zone_v1
  - fibrotic_ild_with_air_trapping_v1
```

---

## 0. Platform Safety Statement

This platform does not diagnose patients, classify individual cases, or recommend treatment.

It is designed to support structured clinical reasoning in interstitial lung disease by helping users understand:

- why a pattern is being considered,
- which differential diagnoses remain on the table,
- which findings weaken a working diagnosis,
- what information is still missing,
- when uncertainty should be preserved,
- and when multidisciplinary discussion may be needed.

> **Core principle:**  
> Diagnosing ILD is not about finding the right answer. It is about asking the right next question — and knowing when you don’t have enough information yet.

---

## 1. Identity

```yaml
pattern_id: fibrotic_hp
full_name: Fibrotic Hypersensitivity Pneumonitis Pattern
short_name: Fibrotic HP
category: Fibrotic Interstitial Lung Disease Pattern with Airway-Centered / Exposure-Related Reasoning
primary_domain: HRCT Pattern Recognition + Exposure-Based Clinical Reasoning
clinical_role: Pattern-level reasoning, not disease-level diagnosis
important_distinction: Fibrotic HP is not diagnosed by imaging alone; it requires integration of exposure history, HRCT pattern, BAL/pathology when needed, and multidisciplinary discussion.
```

### Related Disease Contexts

```yaml
related_disease_contexts:
  - Fibrotic Hypersensitivity Pneumonitis
  - Chronic Hypersensitivity Pneumonitis
  - UIP mimic
  - NSIP mimic
  - Airway-centered fibrotic ILD
  - Exposure-related ILD
  - Unclassifiable fibrotic ILD
```

---

## 2. Pattern Summary

```yaml
one_sentence_summary: >
  Fibrotic HP is a fibrotic ILD pattern in which chronic immune-mediated
  exposure-related lung injury produces fibrosis, often with airway-centered
  clues such as mosaic attenuation, air trapping, centrilobular nodules,
  three-density pattern, or non-classic distribution.

danger_statement: >
  Fibrotic HP may mimic UIP/IPF or fibrotic NSIP; failure to investigate
  exposure history and expiratory HRCT can lead to premature IPF or NSIP labeling.
```

### Key Teaching Point

Fibrotic HP asks two questions at the same time:

```text
Is there fibrosis?
Is there evidence that the fibrosis is exposure-related and airway-centered?
```

A UIP-like fibrotic pattern with strong air-trapping, mosaic attenuation, three-density pattern, centrilobular nodules, or convincing exposure history should not be treated as “simple IPF reasoning.”

---

## 3. HRCT Imaging Anatomy

### 3.1 Distribution

```yaml
distribution:
  upper_or_mid_lung_predominance: supportive_when_present
  lower_lung_predominance: possible_and_can_mimic_uip_or_nsip
  diffuse_distribution: possible
  axial_distribution:
    subpleural: possible
    peribronchovascular_or_airway_centered: supportive
    random_patchy_distribution: possible
  zonal_heterogeneity: supportive
  lobular_air_trapping_distribution: high_value_when_seen_on_expiratory_ct
```

### 3.2 Core Fibrotic Features

```yaml
core_fibrotic_features:
  reticulation:
    role: fibrotic_feature
    importance: high

  traction_bronchiectasis_or_bronchiolectasis:
    role: fibrosis_marker
    importance: high

  architectural_distortion:
    role: chronic_fibrotic_remodeling_marker
    importance: high

  honeycombing:
    role: may_be_present
    importance: moderate_to_high
    caution: when_dominant_and_classic_basal_subpleural_consider_UIP_gray_zone

  volume_loss:
    role: chronic_fibrotic_remodeling_marker
    importance: moderate
```

### 3.3 Airway-Centered / HP-Supportive Features

```yaml
hp_supportive_features:
  mosaic_attenuation:
    role: small_airway_or_vascular_regional_difference_clue
    importance: high
    caution: needs_context_and_expiratory_correlation

  air_trapping:
    role: small_airways_clue
    importance: very_high
    best_seen_on: expiratory_hrct

  three_density_pattern:
    role: highly_suggestive_hp_feature_when_present
    importance: very_high
    comment: Combination of normal lung, increased attenuation, and decreased attenuation/air trapping.

  poorly_defined_centrilobular_ground_glass_nodules:
    role: airway_centered_inflammatory_clue
    importance: high

  bronchiolocentric_distribution:
    role: airway_centered_fibrotic_reasoning_clue
    importance: high
```

### 3.4 Findings That Require Caution

```yaml
caution_features:
  classic_basal_subpleural_honeycombing_without_airway_features:
    concern:
      - UIP
      - IPF
      - RA_UIP
      - asbestosis

  symmetric_lower_lung_ground_glass_and_reticulation:
    concern:
      - fibrotic_NSIP
      - CTD_ILD

  dominant_consolidation:
    concern:
      - organizing_pneumonia
      - infection
      - drug_toxicity
      - malignancy

  profuse_perilymphatic_nodules_or_lymphadenopathy:
    concern:
      - sarcoidosis
      - pneumoconiosis
      - malignancy

  diffuse_cysts:
    concern:
      - LIP
      - LAM
      - PLCH
      - Birt_Hogg_Dube
```

---

## 4. Confidence Levels

```yaml
confidence_levels:
  typical_fibrotic_hp_pattern:
    supportive_features:
      - fibrotic_abnormality_present
      - mosaic_attenuation_or_air_trapping
      - three_density_pattern_when_present
      - centrilobular_ground_glass_nodules_when_present
      - distribution_not_classic_for_simple_uip
      - no_dominant_alternative_explanation
    interpretation: Strong fibrotic HP pattern; exposure history and MDD remain essential.

  compatible_fibrotic_hp_pattern:
    supportive_features:
      - fibrosis_present
      - some_airway_or_mosaic_features
      - distribution_partially_supportive
      - exposure_possible_or_unknown
    interpretation: Compatible but not definitive; missing pieces are high value.

  indeterminate_for_fibrotic_hp:
    supportive_features:
      - fibrosis_present
      - airway_features_absent_or_uncertain
      - exposure_unknown
      - overlaps_with_uip_or_nsip
    interpretation: Gray zone; compare against UIP, NSIP, CTD-ILD, and occupational ILD.

  alternative_diagnosis_suggested:
    supportive_features:
      - classic_UIP_without_HP_clues
      - strong_CTD_context
      - pleural_plaques_with_asbestos_exposure
      - dominant_sarcoid_pattern
      - infection_or_malignancy_pattern
    interpretation: Pause HP pathway and search for stronger alternative explanation.
```

---

## 5. Differential Field

```yaml
core_question_1: Is there fibrotic ILD?
core_question_2: Are there airway-centered or exposure-related clues?
core_question_3: Is this fibrotic HP, UIP/IPF, fibrotic NSIP, CTD-ILD, or another mimic?
```

### Main Disease Contexts

```yaml
differential_contexts:
  fibrotic_hp:
    supports:
      - relevant_exposure_history
      - air_trapping
      - mosaic_attenuation
      - three_density_pattern
      - poorly_defined_centrilobular_ground_glass_nodules
      - non_classic_uip_distribution
      - BAL_lymphocytosis_when_present
      - pathology_support_if_available
    weakens:
      - no_exposure_identified_but_does_not_exclude
      - no_airway_features
      - classic_basal_subpleural_UIP_without_HP_clues
      - strong_alternative_context

  ipf_or_uip_context:
    supports:
      - older_age
      - classic_basal_subpleural_UIP
      - honeycombing
      - absence_of_exposure_or_CTD_features
    weakens:
      - air_trapping
      - three_density_pattern
      - centrilobular_nodules
      - exposure_history
      - upper_or_mid_lung_predominance

  fibrotic_nsip:
    supports:
      - symmetric_lower_lung_ground_glass_and_reticulation
      - subpleural_sparing
      - relative_homogeneity
      - CTD_context
    weakens:
      - strong_air_trapping
      - three_density_pattern
      - centrilobular_nodules
      - convincing_exposure_history

  ctd_ild:
    supports:
      - raynaud
      - sicca
      - inflammatory_arthritis
      - mechanic_hands
      - skin_thickening
      - positive_autoantibodies
    weakens:
      - absent_systemic_features
      - strong_exposure_airway_pattern

  occupational_or_pneumoconiosis_related_fibrosis:
    supports:
      - asbestos_or_silica_or_metal_dust_exposure
      - pleural_plaques
      - upper_lobe_nodules_or_progressive_massive_fibrosis
    weakens:
      - no_exposure
      - no_pleural_or_pneumoconiotic_features
```

---

## 6. Exposure Reasoning Layer

```yaml
exposure_reasoning:
  default_question: Is there a plausible antigen exposure?

  exposure_domains:
    birds:
      examples:
        - pigeons
        - parrots
        - poultry
        - feather_bedding
    mold_or_water_damage:
      examples:
        - damp_home
        - visible_mold
        - humidifier
        - air_conditioning_system
    agriculture_or_farming:
      examples:
        - hay
        - grain
        - livestock
        - compost
    occupational:
      examples:
        - wood_dust
        - metalworking_fluids
        - isocyanates
        - mushroom_farming
        - textile_exposure
    recreational_or_domestic:
      examples:
        - hot_tub
        - sauna
        - musical_instruments
        - gardening_compost

  caution:
    - identified_exposure_supports_HP_but_does_not_prove_it
    - absent_exposure_history_does_not_exclude_HP
    - exposure_assessment_quality_matters
```

---

## 7. Gray Zone Links

```yaml
gray_zone_links:
  - fibrotic_hp_vs_uip
  - fibrotic_hp_vs_nsip
  - fibrotic_hp_vs_ctd_ild
  - fibrotic_hp_vs_asbestosis
  - fibrotic_hp_vs_sarcoidosis
  - fibrotic_ild_with_air_trapping
```

### Key Gray Zone Questions

- Is expiratory HRCT available?
- Is air trapping real and extensive?
- Is there a three-density pattern?
- Are centrilobular nodules present?
- Is exposure history convincing, incomplete, or absent?
- Is the pattern more airway-centered or subpleural?
- Is there CTD context that could explain NSIP/UIP-like fibrosis?
- Does prior CT show evolution from inflammatory HP to fibrotic disease?

---

## 8. Why Not Engine

### Why should this not automatically be called IPF?

```yaml
why_not_ipf:
  - exposure_history
  - air_trapping
  - mosaic_attenuation
  - three_density_pattern
  - poorly_defined_centrilobular_nodules
  - upper_or_mid_lung_predominance
  - non_classic_distribution
  - BAL_lymphocytosis_when_available
```

### Why should this not automatically be called NSIP?

```yaml
why_not_nsip:
  - strong_air_trapping
  - mosaic_attenuation
  - three_density_pattern
  - centrilobular_nodules
  - exposure_history
  - bronchiolocentric_pattern
  - patchy_zonal_heterogeneity
```

### Why might this not be HP?

```yaml
why_not_hp:
  - no_exposure_after_high_quality_assessment
  - no_airway_centered_features
  - classic_UIP_pattern_without_HP_clues
  - strong_CTD_context
  - pleural_plaques_with_asbestos_exposure
  - sarcoidosis_pattern
  - infection_or_malignancy_explains_new_findings
```

### Common False Assumptions

```yaml
false_assumptions:
  - No known exposure means HP is excluded.
  - Air trapping is incidental in fibrotic ILD.
  - UIP-like fibrosis automatically means IPF.
  - BAL lymphocytosis alone diagnoses HP.
  - Fibrotic HP must always be upper-lobe predominant.
  - Improvement after exposure avoidance proves the diagnosis.
```

---

## 9. Missing Piece Candidates

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  high_yield_missing_data:
    exposure_history:
      reason: HP reasoning cannot be mature without detailed environmental and occupational assessment.

    expiratory_hrct:
      reason: Air trapping and three-density pattern may be missed without expiratory imaging.

    prior_ct:
      reason: Evolution from inflammatory or airway-centered abnormality to fibrosis may support HP reasoning.

    bal_lymphocytosis:
      reason: Can increase diagnostic confidence when interpreted with HRCT and exposure context.
      caution: Absence_or_low_level_does_not_fully_exclude_fibrotic_HP.

    autoimmune_screen:
      reason: CTD-ILD can mimic fibrotic HP and must be assessed.

    occupational_history:
      reason: Pneumoconiosis and exposure-related fibrosis may mimic or overlap.

    mdd_review:
      reason: Needed when exposure, HRCT, BAL, and clinical context are incomplete or discordant.

    biopsy_discussion:
      reason: Consider only when noninvasive data remain insufficient and result would change management.
```

---

## 10. Temporal Behavior

```yaml
temporal_behavior:
  inflammatory_to_fibrotic_evolution:
    supportive_changes:
      - centrilobular_ground_glass_nodules_decrease_or_persist
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_fibrotic_distortion
      - persistent_air_trapping
    interpretation:
      - possible_evolution_from_nonfibrotic_or_mixed_HP_to_fibrotic_HP

  progression:
    supportive_changes:
      - increasing_fibrosis_extent
      - increasing_traction_bronchiectasis
      - increasing_honeycombing_if_present
      - progressive_volume_loss
      - worsening_pft_when_available
    interpretation:
      - progressive_fibrotic_HP_possible

  stabilization:
    supportive_changes:
      - stable_fibrosis_extent
      - stable_air_trapping
      - stable_pft_when_available
    interpretation:
      - stable_fibrotic_HP_or_controlled_exposure_state_possible

  partial_improvement:
    supportive_changes:
      - reduced_ground_glass
      - reduced_centrilobular_nodules
      - reduced_consolidation_if_OP_overlap
    caution:
      - established_fibrosis_may_persist
      - improvement_may_reflect_exposure_avoidance_or_resolution_of_superimposed_process

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation
      - drug_toxicity
      - pulmonary_edema
      - pulmonary_embolism
      - ongoing_or_new_exposure
      - malignancy
```

---

## 11. Pattern Interaction Atlas

```yaml
pattern_interactions:
  fibrosis_plus_air_trapping:
    consider:
      - fibrotic_HP
      - small_airways_disease
      - CTD_airway_disease
      - smoking_related_airway_disease
    questions:
      - Is expiratory HRCT available?
      - Is air trapping lobular and extensive?
      - Is there three-density pattern?
      - Is there exposure history?

  fibrosis_plus_nodules:
    consider:
      - fibrotic_HP
      - sarcoidosis
      - pneumoconiosis
      - infection
      - malignancy
    questions:
      - Are nodules centrilobular, perilymphatic, or random?
      - Are nodules poorly defined?
      - Are nodules new or chronic?

  fibrosis_plus_emphysema:
    consider:
      - CPFE
      - smoking_related_ILD
      - fibrotic_HP_with_smoking_related_emphysema
      - PLCH_spectrum
    questions:
      - Is emphysema explaining apparent cystic change?
      - Are there nodules or air-trapping beyond emphysema?
      - Is pulmonary hypertension suspected?

  fibrosis_plus_consolidation:
    consider:
      - organizing_pneumonia_overlap
      - infection
      - acute_exacerbation
      - malignancy
      - drug_toxicity
    questions:
      - Is consolidation new?
      - Is it migratory?
      - Does it respond to therapy?
      - Is malignancy excluded if persistent?

  fibrosis_plus_cysts:
    consider:
      - honeycombing
      - emphysema_mimic
      - LIP
      - PLCH
      - Birt_Hogg_Dube
      - amyloidosis
    questions:
      - Are these true cysts or honeycombing?
      - Is there nodular disease?
      - Is distribution upper-lobe or diffuse?
```

---

## 12. Superimposed Event Atlas

```yaml
superimposed_events:
  new_ground_glass_on_fibrotic_hp_background:
    consider:
      - recurrent_or_ongoing_exposure
      - inflammatory_HP_flare
      - infection
      - acute_exacerbation
      - pulmonary_edema
      - drug_toxicity
      - hemorrhage
    warning: New GGO does not automatically mean HP flare.

  new_consolidation:
    consider:
      - organizing_pneumonia_overlap
      - infection
      - aspiration
      - drug_toxicity
      - malignancy
    warning: Persistent focal consolidation should not be dismissed as HP alone.

  new_nodule_or_mass:
    consider:
      - malignancy
      - infection
      - sarcoid_like_reaction
      - pneumoconiosis_related_nodule
      - rheumatoid_nodule_if_context
    warning: Background fibrosis can hide focal malignancy.

  rapid_diffuse_worsening:
    consider:
      - acute_exacerbation
      - infection
      - exposure_rechallenge
      - pulmonary_edema
      - pulmonary_embolism
      - treatment_related_lung_injury
```

---

## 13. Diagnostic Escalation

```yaml
diagnostic_escalation:
  mdd_needed_if:
    - UIP_vs_fibrotic_HP_uncertainty
    - NSIP_vs_fibrotic_HP_uncertainty
    - exposure_history_incomplete_or_conflicting
    - BAL_and_HRCT_discordant
    - suspected_superimposed_event
    - biopsy_decision_is_being_considered
    - treatment_response_is_unexpected

  exposure_specialist_or_environmental_review_high_value_if:
    - suspected_hidden_home_or_workplace_exposure
    - recurrent_worsening_without_clear_cause
    - possible_bird_or_mold_or_occupational_antigen

  bal_may_help_if:
    - hp_suspected
    - infection_suspected
    - immunosuppressed_patient
    - alveolar_process_suspected

  biopsy_discussion_if:
    - diagnosis_remains_uncertain_after_exposure_hrct_bal_review
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need

  follow_up_ct_reasonable_if:
    - exposure_avoidance_or_intervention_has_occurred
    - early_or_mild_fibrotic_disease
    - uncertainty_between_active_inflammation_and_established_fibrosis
    - treatment_response_or_progression_needs_assessment
```

---

## 14. Treatment / Exposure Response Reasoning

```yaml
response_reasoning:
  exposure_avoidance_response:
    possible_improvement:
      - reduced_ground_glass
      - reduced_centrilobular_nodules
      - reduced_symptoms
      - stabilization_of_fibrosis
    caution:
      - established_fibrosis_may_not_resolve
      - lack_of_improvement_does_not_fully_exclude_HP

  anti_inflammatory_response:
    possible_improvement:
      - reduced_ground_glass
      - reduced_consolidation_if_OP_overlap
      - improved_symptoms_or_pft_when_available
    caution:
      - improvement_may_reflect_treatment_of_superimposed_inflammation_not_reversal_of_fibrosis

  progressive_fibrotic_behavior:
    possible_markers:
      - increasing_fibrosis_extent
      - increasing_traction_bronchiectasis
      - worsening_FVC_or_DLCO_when_available
      - increasing_oxygen_requirement
    reasoning_note:
      - consider_progressive_fibrotic_ILD_framework_when_criteria_are_met
```

---

## 15. Pitfall Library

```yaml
pitfalls:
  - title: Calling UIP/IPF before checking exposure.
    correction: Fibrotic HP can mimic UIP and requires exposure assessment.

  - title: Ignoring expiratory HRCT.
    correction: Air trapping and three-density pattern may be decisive.

  - title: Assuming no exposure means no HP.
    correction: Exposure history is often incomplete; absence of identified exposure does not exclude HP.

  - title: Overrelying on BAL lymphocytosis.
    correction: BAL supports reasoning but should not be interpreted alone.

  - title: Treating air trapping as incidental emphysema.
    correction: Lobular air trapping in fibrotic ILD can redirect toward HP or airway-centered disease.

  - title: Missing malignancy in fibrotic lung.
    correction: New nodules or focal masses require dedicated evaluation.

  - title: Assuming improvement means fibrosis reversed.
    correction: Improvement may reflect reduced inflammation or superimposed OP/infection/edema.
```

---

## 16. Evidence and Guideline Registry

```yaml
evidence_and_guideline_registry:
  primary_guidelines_to_link:
    - ATS_JRS_ALAT_Hypersensitivity_Pneumonitis_Diagnosis_Guideline
    - CHEST_Hypersensitivity_Pneumonitis_Diagnosis_Evaluation_Guideline
    - ATS_Exposure_Assessment_Tools_HP_Workshop_Report
    - ATS_ERS_JRS_ALAT_IPF_PPF_Guideline

  evidence_notes:
    - HP diagnosis requires integration of exposure assessment, HRCT pattern, BAL/pathology when appropriate, and MDD.
    - Fibrotic HP can overlap with UIP and NSIP imaging patterns.
    - Expiratory HRCT is important for air trapping assessment.
    - Exposure history can be absent or incomplete and should be actively investigated.
    - BAL lymphocytosis may increase diagnostic confidence but does not work as a standalone diagnostic authority.

  consensus_strength:
    exposure_assessment_importance: high
    HRCT_pattern_importance: high
    BAL_as_supportive_evidence: moderate_to_high_context_dependent
    fibrotic_HP_vs_UIP_gray_zone: high_complexity
    fibrotic_HP_vs_NSIP_gray_zone: high_complexity
    biopsy_decision: context_dependent
```

---

## 17. Narrative Questions

Every fibrotic HP page should end with these questions:

```yaml
narrative_questions:
  - Is there fibrotic ILD?
  - Are there airway-centered clues?
  - Is expiratory HRCT available?
  - Is there mosaic attenuation, air trapping, or three-density pattern?
  - Is there a plausible exposure history?
  - If exposure history is negative, was it truly high-quality?
  - Does this mimic UIP/IPF?
  - Does this mimic fibrotic NSIP?
  - What does the prior CT show?
  - Is the disease improving, stable, or progressing?
  - Is there evidence of ongoing exposure or superimposed event?
  - What is the single most important missing piece of information?
```

---

## 18. MVP Screen Behavior

```yaml
mvp_screen_behavior:
  main_panel:
    - pattern_summary
    - hrct_imaging_anatomy
    - exposure_reasoning_layer
    - confidence_levels
    - differential_field

  right_sidebar:
    - why_not_ipf
    - why_not_nsip
    - missing_piece_candidates
    - gray_zone_links
    - pitfall_library
    - superimposed_event_alerts
    - guideline_registry

  bottom_panel:
    - temporal_comparison_prompt
    - exposure_quality_prompt
    - mdd_prompt
    - what_do_we_still_not_know_prompt
```

---

## 19. MVP Test Case

```yaml
case_test_fibrotic_hp_001:
  input:
    age: 61
    sex: female
    hrct:
      - fibrotic_reticulation
      - traction_bronchiectasis
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
      - no_definite_honeycombing
      - possible_centrilobular_ground_glass_nodules
    history:
      bird_exposure: unknown
      mold_exposure: unknown
      occupational_exposure: unknown
      autoimmune_features: unknown
      prior_ct: unavailable
    laboratory:
      autoimmune_screen: unavailable
      bal_lymphocytosis: unavailable

  system_output:
    pattern_confidence: compatible_fibrotic_hp_pattern
    disease_statement: Fibrotic HP is possible, but not confirmed by imaging alone.
    why_not_ipf:
      - air_trapping_present
      - mosaic_attenuation_present
      - possible_centrilobular_nodules
      - exposure_history_unknown
    why_not_nsip:
      - airway_centered_features_present
      - mosaic_attenuation_present
      - exposure_history_unknown
    missing_pieces:
      - detailed_exposure_history
      - prior_ct
      - autoimmune_screen
      - BAL_lymphocytosis_if_clinically_relevant
      - MDD_review
    final_prompt:
      - What exposure or airway-centered evidence is still missing before calling this fibrotic HP?
```