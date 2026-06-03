# NSIP vs Fibrotic HP Gray Zone — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_nsip_vs_fibrotic_hp_gray_zone_v1
title: NSIP vs Fibrotic HP Gray Zone — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
linked_patterns:
  - pattern_nsip_gold_standard_v1
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

This reasoning map is designed to help users compare NSIP-like fibrotic/inflammatory lung disease and fibrotic hypersensitivity pneumonitis without forcing premature diagnostic certainty.

It does not diagnose idiopathic NSIP, CTD-ILD, fibrotic HP, drug-related ILD, infection, or unclassifiable ILD.

It helps users ask:

- Is the pattern truly NSIP-like?
- Are there airway-centered clues suggesting HP?
- Is there a CTD context?
- Is there exposure history?
- Is expiratory HRCT available?
- Is the ground-glass component inflammatory, fibrotic, superimposed, or exposure-related?
- What information is missing before choosing a label?

---

## 1. Core Distinction

```yaml
core_distinction:
  nsip:
    reasoning_center: relatively_homogeneous_ground_glass_reticulation_with_or_without_fibrosis
    classic_clues:
      - lower_lung_predominance
      - bilateral_symmetry
      - possible_subpleural_sparing
      - absent_or_minimal_honeycombing
      - CTD_context_common
    danger_statement: NSIP_pattern_should_not_be_called_idiopathic_before_secondary_causes_are_reviewed

  fibrotic_hp:
    reasoning_center: fibrotic_ILD_with_airway_centered_or_exposure_related_clues
    classic_clues:
      - air_trapping
      - mosaic_attenuation
      - three_density_pattern
      - poorly_defined_centrilobular_ground_glass_nodules
      - exposure_history
      - BAL_lymphocytosis_when_available
    danger_statement: fibrotic_HP_can_look_NSIP_like_when_fibrosis_and_ground_glass_are_lower_lung_or_diffuse
```

### Teaching Point

NSIP asks:

```text
Is this relatively homogeneous interstitial abnormality, often CTD-related?
```

Fibrotic HP asks:

```text
Is this fibrosis part of an airway-centered, exposure-related process?
```

The key error is to see lower-lung ground-glass and reticulation and stop at “NSIP” without checking expiratory HRCT and exposure history.

---

## 2. Features Supporting NSIP Pathway

```yaml
features_supporting_nsip_pathway:
  distribution:
    - lower_lung_predominance
    - bilateral_symmetry
    - possible_subpleural_sparing
    - relatively_homogeneous_extent

  morphology:
    - ground_glass_opacity
    - fine_reticulation
    - traction_bronchiectasis_in_fibrotic_cases
    - volume_loss_in_fibrotic_cases
    - absent_or_minimal_honeycombing

  clinical_context:
    - systemic_sclerosis_features
    - myositis_features
    - Sjogren_features
    - MCTD_features
    - positive_autoantibodies
    - drug_related_context_possible

  reasoning_weight:
    subpleural_sparing: high_when_real
    bilateral_symmetry: moderate_to_high
    relative_homogeneity: high
    CTD_context: high
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
    - feather_bedding
    - mold_or_water_damage
    - humidifier_or_hot_tub_exposure
    - farming_or_agricultural_exposure
    - occupational_antigen_exposure

  distribution_features:
    - upper_or_mid_lung_predominance
    - diffuse_or_patchy_nonclassic_distribution
    - lobular_heterogeneity
    - airway_centered_fibrosis

  supportive_tests:
    - BAL_lymphocytosis_when_available
    - pathology_support_when_available
    - temporal_evolution_from_inflammatory_HP_to_fibrosis

  reasoning_weight:
    three_density_pattern: very_high_when_present
    expiratory_air_trapping: high
    centrilobular_ground_glass_nodules: high
    exposure_history: high_but_not_standalone
```

---

## 4. Direct Comparison Matrix

| Feature | More NSIP-like | More Fibrotic HP-like | Reasoning Note |
|---|---|---|---|
| Distribution | Lower-lung, symmetric | Upper/mid, diffuse, patchy, airway-centered | Fibrotic HP can still be lower-lung dominant |
| Texture | Homogeneous | Heterogeneous/lobular | Heterogeneity should trigger HP review |
| Ground-glass | Common | Common, especially airway-centered/inflammatory component | GGO alone is not decisive |
| Reticulation | Fine, symmetric | Patchy, mixed with airway clues | Pattern context matters |
| Subpleural sparing | Strong NSIP clue | Not classic HP clue | Must be real, not technical artifact |
| Air trapping | Not classic simple NSIP | Strong HP clue | Requires expiratory HRCT |
| Mosaic attenuation | Not classic if marked | Supportive | Consider vascular causes too |
| Three-density pattern | Against simple NSIP | Highly supportive | One of the strongest HP clues |
| Centrilobular nodules | Against classic NSIP | Supportive | Especially poorly defined GGO nodules |
| CTD context | Strongly supportive | May coexist but redirects complexity | CTD and exposure can coexist |
| Exposure history | Not NSIP-specific | Supportive | Supports but does not prove HP |
| BAL lymphocytosis | Not defining | Supportive | Context-dependent, not standalone |

---

## 5. Gray Zone Scenarios

### 5.1 NSIP-like Pattern with Air Trapping

```yaml
scenario_nsip_like_pattern_with_air_trapping:
  problem:
    - lower_lung_ground_glass_and_reticulation_present
    - possible_symmetry
    - air_trapping_or_mosaic_attenuation_present

  nsip_leaning_features:
    - bilateral_symmetry
    - relative_homogeneity
    - subpleural_sparing
    - CTD_context
    - absent_centrilobular_nodules
    - no_exposure_after_high_quality_assessment

  hp_leaning_features:
    - extensive_lobular_air_trapping
    - three_density_pattern
    - centrilobular_ground_glass_nodules
    - exposure_history
    - BAL_lymphocytosis_when_available
    - nonclassic_patchy_distribution

  missing_pieces:
    - expiratory_HRCT_quality
    - detailed_exposure_history
    - autoimmune_screen
    - clinical_CTD_review
    - prior_CT
    - MDD_review
```

### 5.2 Fibrotic HP Mimicking Fibrotic NSIP

```yaml
scenario_fibrotic_hp_mimicking_fibrotic_nsip:
  problem:
    - ground_glass_opacity_present
    - reticulation_present
    - traction_bronchiectasis_present
    - honeycombing_absent_or_minimal

  hp_supporting_clues:
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - centrilobular_nodules
    - exposure_history
    - inflammatory_to_fibrotic_temporal_evolution

  nsip_supporting_clues:
    - homogeneous_fibrosis
    - lower_lung_symmetry
    - subpleural_sparing
    - CTD_context
    - lack_of_airway_centered_findings

  pitfall:
    - Do_not_call_fibrotic_NSIP_before_checking_exposure_and_expiratory_HRCT
```

### 5.3 CTD-NSIP with Incidental Exposure

```yaml
scenario_ctd_nsip_with_incidental_exposure:
  problem:
    - NSIP_pattern_present
    - CTD_features_present
    - exposure_history_also_present

  key_question:
    - Is the exposure causal, contributory, incidental, or insufficiently characterized?

  ctd_supporting_clues:
    - systemic_sclerosis_features
    - myositis_features
    - Sjogren_features
    - positive_autoantibodies
    - symmetric_NSIP_pattern
    - OP_overlap_in_myositis_context

  hp_supporting_clues:
    - air_trapping
    - three_density_pattern
    - centrilobular_nodules
    - recurrent_worsening_after_exposure
    - BAL_lymphocytosis_when_available

  pitfall:
    - Do_not_accept_or_reject_HP_based_on_exposure_history_alone
```

### 5.4 Myositis NSIP/OP vs HP Flare

```yaml
scenario_myositis_nsip_op_vs_hp_flare:
  problem:
    - ground_glass_opacity_present
    - consolidation_or_OP_like_component_present
    - rapid_or_subacute_worsening_possible

  myositis_or_ctd_supporting_clues:
    - mechanic_hands
    - proximal_muscle_weakness
    - elevated_CK
    - antisynthetase_antibodies
    - NSIP_OP_overlap
    - systemic_symptoms

  hp_supporting_clues:
    - exposure_history
    - air_trapping
    - mosaic_attenuation
    - centrilobular_nodules
    - BAL_lymphocytosis_when_available
    - worsening_after_exposure_rechallenge

  missing_pieces:
    - myositis_panel
    - CK_or_aldolase
    - exposure_history
    - expiratory_HRCT
    - infection_exclusion_when_rapid_worsening
    - MDD_review
```

---

## 6. Why Not Engine

### Why not idiopathic NSIP?

```yaml
why_not_idiopathic_nsip:
  - exposure_history
  - air_trapping
  - mosaic_attenuation
  - three_density_pattern
  - centrilobular_ground_glass_nodules
  - occupational_or_environmental_antigen_context
  - BAL_lymphocytosis_when_available
  - CTD_features_or_positive_serology
  - drug_exposure
```

### Why not fibrotic HP?

```yaml
why_not_fibrotic_hp:
  - no_exposure_after_high_quality_assessment
  - no_air_trapping_on_good_expiratory_HRCT
  - no_mosaic_or_three_density_pattern
  - no_centrilobular_nodules
  - strong_symmetric_homogeneous_NSIP_pattern
  - strong_CTD_context
  - medication_history_explains_pattern
```

### Why not stop at “NSIP-like ILD”?

```yaml
why_not_stop_at_nsip_like_ild:
  - NSIP_like_pattern_is_not_a_final_cause
  - CTD_ILD_must_be_reviewed
  - fibrotic_HP_can_be_NSIP_like
  - drug_related_ILD_can_be_NSIP_or_NSIP_OP_like
  - temporal_and_exposure_context_may_change_reasoning
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    expiratory_hrct:
      reason: Air trapping and three-density pattern may redirect from NSIP toward HP.

    exposure_history:
      reason: HP reasoning cannot mature without detailed environmental and occupational assessment.

    autoimmune_screen:
      reason: CTD-ILD is a major NSIP context and may coexist with airway disease.

    clinical_ctd_review:
      reason: Serology alone is not enough; symptoms and exam matter.

    prior_ct:
      reason: Temporal behavior may reveal inflammatory-to-fibrotic HP, CTD-ILD progression, or treatment response.

    medication_history:
      reason: Drug-related ILD may mimic NSIP or NSIP/OP overlap.

    bal_lymphocytosis:
      reason: May support HP when interpreted with HRCT and exposure context.

    pft_trend:
      reason: Helps interpret progression, stability, and treatment response.

    mdd_review:
      reason: Required when NSIP-like pattern and HP clues coexist.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  behavior_supporting_nsip_or_ctd_ild:
    clues:
      - stable_or_slowly_progressive_symmetric_fibrosis
      - partial_improvement_of_ground_glass_after_anti_inflammatory_treatment
      - OP_component_improves_but_fibrosis_persists
      - evolution_linked_to_autoimmune_activity

  behavior_supporting_fibrotic_hp:
    clues:
      - recurrent_worsening_after_exposure
      - prior_centrilobular_ground_glass_nodules
      - persistent_or_increasing_air_trapping
      - transition_from_nonfibrotic_or_mixed_HP_to_fibrotic_disease
      - stabilization_or_partial_improvement_after_exposure_control

  progression_in_either_pathway:
    clues:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_fibrosis_extent
      - declining_FVC_or_DLCO_when_available

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation
      - drug_toxicity
      - pulmonary_edema
      - pulmonary_embolism
      - rapidly_progressive_CTD_ILD
      - exposure_rechallenge
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - NSIP_like_pattern_with_HP_clues
    - CTD_features_and_exposure_history_both_present
    - expiratory_HRCT_and_inspiratory_HRCT_are_discordant
    - BAL_and_HRCT_are_discordant
    - biopsy_decision_is_being_considered
    - treatment_or_exposure_response_is_unexpected

  rheumatology_review_high_value_if:
    - NSIP_pattern
    - positive_or_borderline_autoantibodies
    - raynaud_or_sicca_or_inflammatory_arthritis
    - mechanic_hands_or_myositis_features
    - NSIP_OP_overlap

  exposure_review_high_value_if:
    - air_trapping_or_three_density_pattern_present
    - recurrent_worsening_without_clear_cause
    - possible_bird_mold_humidifier_hot_tub_farming_or_workplace_exposure
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
  - title: Calling NSIP because ground-glass opacity is present.
    correction: Ground-glass opacity may occur in NSIP, HP, OP, infection, edema, drug toxicity, or acute exacerbation.

  - title: Calling idiopathic NSIP before CTD review.
    correction: NSIP commonly raises the question of CTD-ILD or drug-related ILD.

  - title: Ignoring air trapping in an NSIP-like case.
    correction: Air trapping may redirect reasoning toward HP or airway-centered disease.

  - title: Treating exposure history as binary.
    correction: Exposure assessment quality matters; unknown, incomplete, and negative are not equivalent.

  - title: Overcalling HP from exposure alone.
    correction: Exposure supports HP only when integrated with HRCT, BAL/pathology, and clinical context.

  - title: Assuming improvement proves NSIP.
    correction: Improvement may reflect resolution of inflammation, OP, infection, edema, or exposure-related activity.

  - title: Forgetting CTD-ILD and HP can coexist or compete.
    correction: Real patients may carry overlapping risk signals; MDD is often necessary.
```

---

## 11. MVP Test Case

```yaml
case_test_nsip_vs_fibrotic_hp_001:
  input:
    age: 55
    sex: female
    hrct:
      - bilateral_lower_lung_ground_glass
      - fine_reticulation
      - traction_bronchiectasis
      - possible_subpleural_sparing
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
      - no_definite_honeycombing
    history:
      raynaud: unknown
      sicca: unknown
      mechanic_hands: unknown
      bird_exposure: unknown
      mold_exposure: unknown
      occupational_exposure: unknown
      medication_history: unknown
      prior_ct: unavailable
    labs:
      autoimmune_screen: unavailable
      bal_lymphocytosis: unavailable

  output:
    reasoning_state: NSIP_like_pattern_vs_fibrotic_HP_gray_zone
    nsip_support:
      - bilateral_lower_lung_ground_glass
      - fine_reticulation
      - possible_subpleural_sparing
      - no_definite_honeycombing
    hp_support:
      - mosaic_attenuation
      - air_trapping_on_expiratory_ct
    cannot_conclude:
      - idiopathic_NSIP
      - CTD_ILD
      - fibrotic_HP
      - drug_related_ILD
    missing_pieces:
      - autoimmune_screen
      - clinical_CTD_review
      - detailed_exposure_history
      - medication_history
      - prior_CT
      - BAL_lymphocytosis_if_clinically_relevant
      - MDD_review
    final_prompt:
      - What do we still not know before choosing between NSIP-like ILD and fibrotic HP?
```

---

## 12. Final Page Prompt

Every NSIP vs Fibrotic HP gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Is this truly homogeneous NSIP-like disease?
2. Is there real air trapping, mosaic attenuation, or three-density pattern?
3. Is expiratory HRCT available and technically adequate?
4. Is there CTD, drug, or exposure context?
5. Is exposure history high-quality or incomplete?
6. What does the prior CT show?
7. What do we still not know?
```