# UIP vs Fibrotic HP Gray Zone — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_uip_vs_fibrotic_hp_gray_zone_v1
title: UIP vs Fibrotic HP Gray Zone — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
linked_patterns:
  - pattern_uip_gold_standard_v1
  - pattern_fibrotic_hp_gold_standard_v1
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

This reasoning map is designed to help users compare UIP-like fibrosis and fibrotic hypersensitivity pneumonitis without forcing premature diagnostic certainty.

It does not diagnose IPF, fibrotic HP, CTD-ILD, asbestosis, or unclassifiable ILD.

It helps users ask:

- Is the fibrosis truly classic UIP?
- Are there airway-centered clues?
- Is expiratory HRCT available?
- Is there a plausible exposure history?
- Are mosaic attenuation, air trapping, or three-density pattern present?
- What information is missing before calling this idiopathic?

---

## 1. Core Distinction

```yaml
core_distinction:
  uip:
    reasoning_center: basal_subpleural_patchy_fibrosis
    strongest_feature: honeycombing
    classic_distribution: basal_subpleural
    danger_statement: UIP_pattern_does_not_equal_IPF

  fibrotic_hp:
    reasoning_center: fibrotic_ild_with_airway_centered_or_exposure_related_clues
    strongest_features:
      - air_trapping
      - mosaic_attenuation
      - three_density_pattern
      - centrilobular_ground_glass_nodules
      - exposure_history
    danger_statement: fibrotic_HP_can_mimic_UIP_or_IPF
```

### Teaching Point

UIP asks:

```text
Is this classic patchy basal-subpleural fibrosis?
```

Fibrotic HP asks:

```text
Is this fibrosis part of an airway-centered, exposure-related process?
```

The key error is to see honeycombing or basal fibrosis and stop thinking.

---

## 2. Features Supporting UIP/IPF Pathway

```yaml
features_supporting_uip_pathway:
  distribution:
    - basal_predominance
    - subpleural_predominance
    - peripheral_predominance

  morphology:
    - reticulation
    - traction_bronchiectasis
    - architectural_distortion
    - honeycombing

  context_support:
    - older_age
    - no_exposure_identified_after_high_quality_assessment
    - no_CTD_features
    - no_marked_air_trapping
    - no_three_density_pattern
    - no_profuse_centrilobular_nodules

  reasoning_weight:
    definite_honeycombing: very_high
    basal_subpleural_distribution: high
    absence_of_HP_clues: supportive_but_not_definitive
```

---

## 3. Features Supporting Fibrotic HP Pathway

```yaml
features_supporting_fibrotic_hp_pathway:
  airway_centered_features:
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - poorly_defined_centrilobular_ground_glass_nodules
    - bronchiolocentric_distribution

  exposure_features:
    - bird_exposure
    - mold_or_water_damage
    - farming_or_agricultural_exposure
    - humidifier_or_hot_tub_exposure
    - occupational_antigen_exposure

  distribution_features:
    - upper_or_mid_lung_predominance
    - diffuse_or_patchy_nonclassic_distribution
    - peribronchovascular_or_airway_centered_fibrosis
    - zonal_heterogeneity

  supportive_tests:
    - BAL_lymphocytosis_when_available
    - pathology_support_when_available
    - temporal_evolution_from_inflammatory_HP_to_fibrosis

  reasoning_weight:
    three_density_pattern: very_high_when_present
    expiratory_air_trapping: high
    centrilobular_nodules: high
    exposure_history: high_but_not_standalone
```

---

## 4. Direct Comparison Matrix

| Feature | More UIP/IPF-like | More Fibrotic HP-like | Reasoning Note |
|---|---|---|---|
| Distribution | Basal + subpleural | Upper/mid, diffuse, patchy, airway-centered | Fibrotic HP can still be lower-lung dominant |
| Honeycombing | Strong UIP feature | May occur | Honeycombing does not exclude HP |
| Air trapping | Not classic | Strong clue | Requires expiratory HRCT |
| Mosaic attenuation | Not classic if marked | Supportive | Must distinguish from vascular causes |
| Three-density pattern | Against simple UIP | Highly supportive | One of the strongest HP clues |
| Centrilobular nodules | Against classic UIP | Supportive | Especially poorly defined GGO nodules |
| Exposure history | Should be absent for IPF confidence | Supportive | Exposure supports but does not prove HP |
| BAL lymphocytosis | Not expected as UIP/IPF support | Supportive | Context-dependent, not standalone |
| Prior CT evolution | Progressive fibrosis | Inflammatory-to-fibrotic evolution possible | Temporal reasoning is high yield |

---

## 5. Gray Zone Scenarios

### 5.1 UIP-like Fibrosis with Air Trapping

```yaml
scenario_uip_like_fibrosis_with_air_trapping:
  problem:
    - basal_subpleural_fibrosis_present
    - traction_bronchiectasis_present
    - air_trapping_or_mosaic_attenuation_present

  uip_leaning_features:
    - definite_honeycombing
    - classic_basal_subpleural_distribution
    - patchy_subpleural_fibrosis
    - no_exposure_after_high_quality_assessment

  hp_leaning_features:
    - extensive_lobular_air_trapping
    - three_density_pattern
    - centrilobular_nodules
    - exposure_history
    - BAL_lymphocytosis_when_available

  missing_pieces:
    - expiratory_HRCT_quality
    - detailed_exposure_history
    - prior_CT
    - autoimmune_screen
    - MDD_review
```

### 5.2 Classic UIP Pattern but Exposure History Exists

```yaml
scenario_classic_uip_with_exposure:
  problem:
    - definite_or_probable_UIP_pattern
    - relevant_exposure_history_present

  key_question:
    - Is the exposure causal, incidental, or insufficiently characterized?

  hp_supporting_clues:
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - centrilobular_nodules
    - inflammatory_to_fibrotic_temporal_evolution

  uip_supporting_clues:
    - classic_basal_subpleural_honeycombing
    - no_airway_centered_features
    - exposure_weak_or_uncertain
    - no_BAL_or_pathologic_support_for_HP

  pitfall:
    - Do_not_accept_or_reject_HP_based_on_exposure_history_alone
```

### 5.3 Fibrotic HP Without Identified Exposure

```yaml
scenario_fibrotic_hp_without_identified_exposure:
  problem:
    - imaging_suggests_HP
    - exposure_history_negative_or_incomplete

  key_question:
    - Was the exposure assessment truly high quality?

  actions_to_consider:
    - repeat_structured_exposure_history
    - home_or_occupational_review_when_available
    - ask_about_birds_feathers_mold_humidifier_hot_tub_farming_workplace
    - review_expiratory_HRCT
    - consider_BAL_if_clinically_relevant
    - MDD_review

  pitfall:
    - No_known_exposure_does_not_equal_no_HP
```

---

## 6. Why Not Engine

### Why not IPF?

```yaml
why_not_ipf:
  - marked_air_trapping
  - mosaic_attenuation
  - three_density_pattern
  - centrilobular_ground_glass_nodules
  - relevant_exposure_history
  - upper_or_mid_lung_predominance
  - bronchiolocentric_fibrotic_pattern
  - BAL_lymphocytosis_when_available
  - inflammatory_to_fibrotic_temporal_evolution
```

### Why not Fibrotic HP?

```yaml
why_not_fibrotic_hp:
  - no_exposure_after_high_quality_assessment
  - no_air_trapping_on_good_expiratory_HRCT
  - no_mosaic_or_three_density_pattern
  - no_centrilobular_nodules
  - classic_basal_subpleural_UIP_with_honeycombing
  - strong_alternative_context_such_as_CTD_or_asbestosis
```

### Why not stop at “UIP-like fibrosis”?

```yaml
why_not_stop_at_uip_like_fibrosis:
  - UIP_like_pattern_is_not_a_final_cause
  - IPF_requires_exclusion_of_known_causes
  - fibrotic_HP_can_be_UIP_like
  - CTD_UIP_and_asbestosis_can_be_UIP_like
  - temporal_and_exposure_context_may_change_reasoning
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    expiratory_hrct:
      reason: Air trapping and three-density pattern may be decisive.

    exposure_history:
      reason: HP reasoning cannot mature without detailed exposure assessment.

    prior_ct:
      reason: Temporal evolution may reveal inflammatory-to-fibrotic HP or progressive UIP-like behavior.

    autoimmune_screen:
      reason: CTD-UIP can mimic both IPF and fibrotic HP.

    bal_lymphocytosis:
      reason: May increase confidence for HP when interpreted with HRCT and exposure context.

    occupational_history:
      reason: Asbestos, silica, metal, and organic exposures may redirect the case.

    mdd_review:
      reason: Required when UIP-like fibrosis and HP clues coexist.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  progression_supporting_uip_like_behavior:
    clues:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_honeycombing
      - increasing_subpleural_fibrosis

  evolution_supporting_fibrotic_hp:
    clues:
      - prior_centrilobular_ground_glass_nodules
      - prior_mosaic_attenuation
      - persistent_or_increasing_air_trapping
      - transition_from_inflammatory_HP_like_pattern_to_fibrosis
      - recurrent_worsening_after_exposure

  stabilization_after_exposure_control:
    clues:
      - stable_fibrosis_extent
      - reduced_ground_glass_or_nodules
      - stable_or_improved_pft_when_available
    caution:
      - established_fibrosis_may_persist

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation
      - exposure_rechallenge
      - drug_toxicity
      - pulmonary_edema
      - pulmonary_embolism
      - malignancy
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - definite_or_probable_UIP_pattern_with_HP_clues
    - fibrotic_HP_suspected_but_exposure_unknown
    - BAL_and_HRCT_are_discordant
    - biopsy_decision_is_being_considered
    - temporal_behavior_conflicts_with_initial_label
    - treatment_or_exposure_response_is_unexpected

  exposure_review_high_value_if:
    - air_trapping_or_three_density_pattern_present
    - recurrent_worsening_without_clear_cause
    - suspected_bird_mold_or_occupational_antigen
    - patient_initially_reports_no_exposure_but_HRCT_suggests_HP

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
  - title: Calling IPF from UIP-like fibrosis alone.
    correction: UIP-like fibrosis can be caused by HP, CTD-ILD, asbestosis, and other processes.

  - title: Ignoring expiratory HRCT.
    correction: Air trapping may be invisible or underestimated without expiratory imaging.

  - title: Treating exposure history as binary.
    correction: Exposure assessment has quality; “unknown” and “negative” are not the same.

  - title: Assuming no identified exposure excludes HP.
    correction: Many HP cases have incomplete or difficult exposure identification.

  - title: Overcalling HP from exposure alone.
    correction: Exposure supports HP only when integrated with imaging, BAL/pathology, and clinical context.

  - title: Dismissing air trapping as incidental.
    correction: In fibrotic ILD, extensive lobular air trapping may be diagnostically important.

  - title: Forgetting CTD-UIP.
    correction: Autoimmune disease can produce UIP-like fibrosis and must be reviewed.
```

---

## 11. MVP Test Case

```yaml
case_test_uip_vs_fibrotic_hp_001:
  input:
    age: 64
    sex: male
    hrct:
      - basal_subpleural_reticulation
      - traction_bronchiectasis
      - possible_honeycombing
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
    history:
      bird_exposure: unknown
      mold_exposure: unknown
      occupational_exposure: unknown
      autoimmune_features: unknown
      prior_ct: unavailable
    labs:
      autoimmune_screen: unavailable
      bal_lymphocytosis: unavailable

  output:
    reasoning_state: UIP_like_fibrosis_vs_fibrotic_HP_gray_zone
    uip_support:
      - basal_subpleural_reticulation
      - traction_bronchiectasis
      - possible_honeycombing
    hp_support:
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
    cannot_conclude:
      - IPF
      - fibrotic_HP
      - CTD_UIP
      - asbestosis
    missing_pieces:
      - detailed_exposure_history
      - prior_CT
      - autoimmune_screen
      - BAL_lymphocytosis_if_clinically_relevant
      - MDD_review
    final_prompt:
      - What do we still not know before calling this idiopathic UIP/IPF or fibrotic HP?
```

---

## 12. Final Page Prompt

Every UIP vs Fibrotic HP gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Is the fibrosis classic basal-subpleural UIP?
2. Is there air trapping, mosaic attenuation, or three-density pattern?
3. Is expiratory HRCT available and technically adequate?
4. Is exposure history high-quality or incomplete?
5. Is there CTD, occupational, or drug context?
6. What does the prior CT show?
7. What do we still not know?
```