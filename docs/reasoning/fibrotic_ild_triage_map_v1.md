# Fibrotic ILD Triage Map — Reasoning Engine v1

## Document Metadata

```yaml
id: reasoning_fibrotic_ild_triage_map_v1
title: Fibrotic ILD Triage Map — Reasoning Engine
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: triage_reasoning_engine
linked_patterns:
  - pattern_uip_gold_standard_v1
  - pattern_nsip_gold_standard_v1
  - pattern_fibrotic_hp_gold_standard_v1
linked_reasoning_maps:
  - uip_vs_nsip_gray_zone_v1
  - uip_vs_fibrotic_hp_gray_zone_v1
  - nsip_vs_fibrotic_hp_gray_zone_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - rheumatologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This triage map is the first central reasoning engine of the ILD Reasoning Platform.

It does not diagnose IPF, NSIP, fibrotic HP, CTD-ILD, occupational ILD, drug-related ILD, or unclassifiable ILD.

It helps users start from a fibrotic HRCT pattern and ask:

- Is the fibrosis UIP-like?
- Is the fibrosis NSIP-like?
- Are there airway-centered HP clues?
- Is there autoimmune, exposure, occupational, or drug context?
- Is the disease progressive, stable, improving, or complicated by a superimposed event?
- What information is still missing?

---

## 1. Entry Point

```yaml
entry_point:
  user_question: What kind of fibrotic ILD pattern am I seeing?
  primary_inputs:
    - HRCT_distribution
    - HRCT_morphology
    - temporal_comparison
    - exposure_history
    - autoimmune_context
    - medication_history
    - occupational_history
    - PFT_trend
    - BAL_or_pathology_if_available
  output_type:
    - reasoning_state
    - pattern_support
    - competing_differentials
    - missing_pieces
    - gray_zone_links
    - final_uncertainty_prompt
```

---

## 2. First-Level Pattern Sorting

```yaml
first_level_pattern_sorting:
  uip_like_fibrosis:
    supportive_features:
      - basal_subpleural_predominance
      - reticulation
      - traction_bronchiectasis
      - honeycombing
      - patchy_heterogeneous_fibrosis
    immediate_questions:
      - Is this truly classic UIP?
      - Are known causes excluded?
      - Is there exposure, CTD, occupational, or drug context?
      - Is there air trapping or three-density pattern?

  nsip_like_fibrosis:
    supportive_features:
      - lower_lung_predominance
      - bilateral_symmetry
      - ground_glass_opacity
      - fine_reticulation
      - traction_bronchiectasis_in_fibrotic_cases
      - possible_subpleural_sparing
      - relative_homogeneity
    immediate_questions:
      - Is this idiopathic or secondary?
      - Is there CTD context?
      - Is there drug exposure?
      - Are HP clues present?

  fibrotic_hp_like_pattern:
    supportive_features:
      - fibrosis
      - air_trapping
      - mosaic_attenuation
      - three_density_pattern
      - poorly_defined_centrilobular_ground_glass_nodules
      - airway_centered_distribution
      - plausible_exposure_history
    immediate_questions:
      - Is expiratory HRCT available?
      - Is exposure history high-quality?
      - Is BAL lymphocytosis available or relevant?
      - Does it mimic UIP or NSIP?
```

---

## 3. Direct Triage Matrix

| Question | UIP-like Pathway | NSIP-like Pathway | Fibrotic HP-like Pathway |
|---|---|---|---|
| Main morphology | Patchy fibrosis, honeycombing | Homogeneous GGO/reticulation | Fibrosis + airway-centered clues |
| Main distribution | Basal/subpleural | Lower-lung/symmetric | Upper/mid, diffuse, patchy, or airway-centered |
| Honeycombing | Strong clue | Usually absent/minimal | May occur |
| Subpleural sparing | Against classic UIP | Supportive | Not classic but context-dependent |
| Air trapping | Against simple UIP | Against simple NSIP | Strong clue |
| Three-density pattern | Against simple UIP | Against simple NSIP | Very strong clue |
| CTD context | Secondary UIP possible | Commonly relevant | Possible coexistence |
| Exposure context | Weakens idiopathic IPF | Redirects toward HP | Strongly relevant |
| Prior CT | Progression assessment | Response/progression assessment | Inflammatory-to-fibrotic evolution |
| MDD value | High in non-classic cases | High in CTD/overlap cases | High in discordant cases |

---

## 4. Reasoning States

```yaml
reasoning_states:
  classic_uip_low_competing_signal:
    criteria:
      - definite_honeycombing
      - basal_subpleural_distribution
      - patchy_heterogeneous_fibrosis
      - no_major_HP_clues
      - no_major_CTD_or_exposure_context_known
    output:
      - UIP_pattern_likely
      - IPF_possible_but_not_confirmed_by_pattern_alone
      - missing_known_cause_exclusion_data

  probable_uip_vs_fibrotic_nsip:
    criteria:
      - basal_or_lower_lung_fibrosis
      - traction_bronchiectasis
      - honeycombing_absent_or_uncertain
      - NSIP_features_possible
    output:
      - gray_zone_uip_vs_nsip
      - link_uip_vs_nsip_gray_zone_v1
      - missing_prior_CT_autoimmune_screen_MDD

  uip_like_fibrosis_with_HP_clues:
    criteria:
      - UIP_like_fibrosis
      - air_trapping_or_mosaic_attenuation_or_three_density_pattern
    output:
      - gray_zone_uip_vs_fibrotic_HP
      - link_uip_vs_fibrotic_hp_gray_zone_v1
      - missing_expiratory_HRCT_quality_exposure_BAL_MDD

  nsip_like_pattern_with_HP_clues:
    criteria:
      - lower_lung_ground_glass_reticulation
      - symmetric_or_NSIP_like_pattern
      - air_trapping_or_mosaic_attenuation
    output:
      - gray_zone_nsip_vs_fibrotic_HP
      - link_nsip_vs_fibrotic_hp_gray_zone_v1
      - missing_exposure_autoimmune_expiratory_HRCT_MDD

  nsip_like_pattern_with_CTD_clues:
    criteria:
      - NSIP_like_pattern
      - raynaud_or_sicca_or_inflammatory_arthritis_or_myositis_or_scleroderma_features
    output:
      - CTD_ILD_context_high_value
      - rheumatology_review_prompt
      - autoimmune_serology_prompt
      - treatment_response_and_PFT_trend_prompt

  fibrotic_ild_with_superimposed_event:
    criteria:
      - known_or_suspected_fibrotic_ILD
      - new_GGO_or_consolidation_or_nodule_or_rapid_worsening
    output:
      - superimposed_event_alert
      - do_not_call_simple_progression
      - consider_infection_edema_drug_toxicity_acute_exacerbation_malignancy
```

---

## 5. “Why Not?” Engine

```yaml
why_not_engine:
  why_not_ipf:
    - exposure_history_not_assessed
    - CTD_context_not_assessed
    - marked_air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - centrilobular_nodules
    - pleural_plaques_or_occupational_context
    - young_age_or_atypical_clinical_context
    - new_superimposed_process

  why_not_idiopathic_nsip:
    - CTD_review_incomplete
    - autoimmune_screen_unavailable
    - medication_history_unknown
    - exposure_history_unknown
    - HP_clues_present
    - prior_CT_unavailable

  why_not_fibrotic_hp:
    - exposure_assessment_high_quality_and_negative
    - no_air_trapping_on_adequate_expiratory_HRCT
    - no_mosaic_or_three_density_pattern
    - no_centrilobular_nodules
    - strong_classic_UIP_without_HP_clues
    - strong_CTD_or_occupational_alternative
```

---

## 6. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_ct:
      value: separates_progression_stability_regression_superimposed_change

    expiratory_hrct:
      value: detects_air_trapping_and_three_density_pattern

    detailed_exposure_history:
      value: essential_for_HP_reasoning

    autoimmune_screen:
      value: essential_for_CTD_ILD_reasoning

    clinical_ctd_review:
      value: serology_alone_is_not_enough

    medication_history:
      value: drug_related_ILD_can_mimic_NSIP_OP_or_HP_like_patterns

    occupational_history:
      value: identifies_asbestos_silica_metal_wood_or_organic_exposure_context

    pft_trend:
      value: supports_progression_or_stability_assessment

    bal_lymphocytosis:
      value: supportive_for_HP_when_contextualized

    mdd_review:
      value: required_when_pattern_context_and_tests_are_discordant
```

---

## 7. Temporal Triage

```yaml
temporal_triage:
  progression:
    imaging_clues:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_honeycombing
      - increasing_fibrosis_extent
      - increasing_volume_loss
    clinical_clues:
      - worsening_FVC
      - worsening_DLCO
      - increasing_oxygen_requirement
    prompt:
      - Is this progressive fibrotic ILD behavior?

  stabilization:
    imaging_clues:
      - stable_extent_of_fibrosis
      - stable_traction_bronchiectasis
      - stable_honeycombing_if_present
    clinical_clues:
      - stable_PFT
      - stable_symptoms
    prompt:
      - Is the diagnosis still uncertain despite stability?

  partial_improvement:
    imaging_clues:
      - reduced_ground_glass
      - reduced_consolidation
      - reduced_centrilobular_nodules
    caution:
      - established_fibrosis_may_persist
      - improvement_may_reflect_resolution_of_superimposed_inflammation_OP_infection_or_edema
    prompt:
      - What improved: inflammation, OP, infection, edema, or true fibrotic burden?

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation
      - pulmonary_edema
      - pulmonary_embolism
      - drug_toxicity
      - aspiration
      - exposure_rechallenge
      - malignancy
    prompt:
      - Do not call rapid change simple ILD progression without excluding superimposed events.
```

---

## 8. Red Flag Panel

```yaml
red_flags:
  new_focal_nodule_or_mass:
    concern:
      - malignancy
      - infection
      - inflammatory_nodule
    prompt:
      - Do not let background fibrosis hide a focal lesion.

  new_diffuse_ground_glass:
    concern:
      - infection
      - acute_exacerbation
      - edema
      - drug_toxicity
      - hemorrhage
      - aspiration
    prompt:
      - New GGO is not automatically progression.

  new_or_persistent_consolidation:
    concern:
      - organizing_pneumonia
      - infection
      - malignancy
      - drug_toxicity
    prompt:
      - Persistent or asymmetric consolidation requires reassessment.

  rapid_clinical_decline:
    concern:
      - acute_exacerbation
      - infection
      - PE
      - edema
      - treatment_related_lung_injury
    prompt:
      - Escalate reasoning; do not rely on baseline ILD label alone.
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - UIP_NSIP_HP_signals_overlap
    - HRCT_pattern_and_clinical_context_conflict
    - exposure_history_positive_or_uncertain
    - autoimmune_context_positive_or_uncertain
    - rapid_change_or_superimposed_event_suspected
    - biopsy_decision_is_being_considered
    - treatment_response_is_unexpected

  rheumatology_review_high_value_if:
    - NSIP_like_pattern
    - CTD_symptoms_or_autoantibodies
    - UIP_like_pattern_in_younger_or_female_patient
    - myositis_or_scleroderma_features

  exposure_review_high_value_if:
    - air_trapping_or_three_density_pattern
    - recurrent_worsening_without_clear_cause
    - possible_bird_mold_humidifier_hot_tub_farming_or_workplace_exposure

  biopsy_discussion_if:
    - noninvasive_data_remain_indeterminate
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: UIP-like fibrosis equals IPF.
    correction: UIP-like fibrosis may reflect IPF, CTD-UIP, fibrotic HP, asbestosis, drug-related ILD, or unclassifiable ILD.

  - title: Ground-glass opacity equals NSIP.
    correction: GGO may reflect NSIP, HP, OP, infection, edema, drug toxicity, hemorrhage, or fine fibrosis.

  - title: Air trapping is incidental.
    correction: In fibrotic ILD, air trapping may be a key HP or airway-centered clue.

  - title: Exposure history is binary.
    correction: Exposure history has quality; unknown, incomplete, weak, and high-confidence exposure are different.

  - title: Stability resolves diagnostic uncertainty.
    correction: Stable disease can remain diagnostically uncertain.

  - title: Improvement means fibrosis reversed.
    correction: Improvement may reflect resolution of superimposed inflammatory or alveolar abnormality.

  - title: Missing CTD-ILD in UIP-like disease.
    correction: Autoimmune disease can present with UIP-like or NSIP-like fibrosis.

  - title: Missing malignancy in fibrotic lung.
    correction: New focal lesions require dedicated attention.
```

---

## 11. MVP Triage Case

```yaml
case_test_fibrotic_ild_triage_001:
  input:
    age: 58
    sex: female
    hrct:
      - lower_lung_reticulation
      - traction_bronchiectasis
      - ground_glass_opacity
      - no_definite_honeycombing
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
    history:
      raynaud: unknown
      sicca: unknown
      mechanic_hands: unknown
      bird_exposure: unknown
      mold_exposure: unknown
      medication_history: unknown
      occupational_exposure: unknown
      prior_ct: unavailable
    labs:
      autoimmune_screen: unavailable
      bal_lymphocytosis: unavailable
    pft:
      fvc_trend: unavailable
      dlco_trend: unavailable

  output:
    reasoning_state:
      - NSIP_like_pattern_vs_fibrotic_HP_gray_zone
      - probable_UIP_less_supported_due_to_no_definite_honeycombing_and_air_trapping
    pattern_support:
      nsip:
        - lower_lung_ground_glass
        - reticulation
        - no_definite_honeycombing
      fibrotic_hp:
        - mosaic_attenuation
        - air_trapping
      uip:
        - traction_bronchiectasis
        - fibrotic_reticulation
    cannot_conclude:
      - idiopathic_NSIP
      - fibrotic_HP
      - IPF
      - CTD_ILD
      - drug_related_ILD
    missing_pieces:
      - prior_CT
      - detailed_exposure_history
      - autoimmune_screen
      - clinical_CTD_review
      - medication_history
      - BAL_lymphocytosis_if_clinically_relevant
      - MDD_review
    final_prompt:
      - What do we still not know before choosing a fibrotic ILD label?
```

---

## 12. Final Page Prompt

Every fibrotic ILD triage page should end with:

```text
Do not force the label.

Ask:
1. What is the dominant fibrotic morphology?
2. Is the pattern UIP-like, NSIP-like, HP-like, or mixed?
3. Is there air trapping or three-density pattern?
4. Is there CTD, exposure, occupational, or drug context?
5. What did the prior CT show?
6. Is this progression, stability, partial improvement, or superimposed disease?
7. What do we still not know?
```