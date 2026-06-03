# UIP vs NSIP Gray Zone — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_uip_vs_nsip_gray_zone_v1
title: UIP vs NSIP Gray Zone — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
linked_patterns:
  - pattern_uip_gold_standard_v1
  - pattern_nsip_gold_standard_v1
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

This reasoning map is designed to help users compare UIP and NSIP patterns without forcing premature diagnostic certainty.

It does not decide whether a patient has UIP, NSIP, IPF, CTD-ILD, fibrotic HP, or another disease.

It helps users ask:

- Which features support UIP?
- Which features support NSIP?
- Which features argue against each pattern?
- What information is missing?
- When should uncertainty be preserved?
- When should multidisciplinary discussion be triggered?

---

## 1. Core Distinction

```yaml
core_distinction:
  uip:
    reasoning_center: patchy_heterogeneous_fibrosis
    classic_distribution: basal_subpleural
    strongest_feature: honeycombing
    disease_context_warning: UIP_pattern_does_not_equal_IPF

  nsip:
    reasoning_center: relatively_homogeneous_interstitial_abnormality
    classic_distribution: lower_lung_symmetric
    strongest_feature: ground_glass_reticulation_with_possible_subpleural_sparing
    disease_context_warning: NSIP_pattern_should_trigger_secondary_cause_search
```

### Teaching Point

UIP and NSIP are not simply two labels.

They represent different reasoning profiles:

```text
UIP asks: Is this patchy, irreversible, heterogeneous fibrosis?
NSIP asks: Is this more homogeneous, potentially CTD-related, inflammatory/fibrotic disease?
```

---

## 2. Features Supporting UIP

```yaml
features_supporting_uip:
  distribution:
    - basal_predominance
    - subpleural_predominance
    - peripheral_predominance

  morphology:
    - reticulation
    - traction_bronchiectasis
    - architectural_distortion
    - honeycombing

  behavior:
    - progressive_fibrotic_change
    - increasing_honeycombing
    - increasing_traction_bronchiectasis

  reasoning_weight:
    honeycombing: very_high
    basal_subpleural_distribution: high
    patchy_heterogeneity: high
    traction_bronchiectasis: moderate_to_high
```

---

## 3. Features Supporting NSIP

```yaml
features_supporting_nsip:
  distribution:
    - lower_lung_predominance
    - bilateral_symmetry
    - possible_subpleural_sparing

  morphology:
    - ground_glass_opacity
    - fine_reticulation
    - traction_bronchiectasis_in_fibrotic_cases
    - relative_homogeneity
    - minimal_or_absent_honeycombing

  behavior:
    - partial_improvement_of_ground_glass_possible
    - stabilization_possible
    - progression_possible_in_fibrotic_nsip

  reasoning_weight:
    subpleural_sparing: high_when_present
    bilateral_symmetry: moderate_to_high
    relative_homogeneity: high
    absence_of_honeycombing: supportive_but_not_definitive
```

---

## 4. Direct Comparison Matrix

| Feature | More UIP-like | More NSIP-like | Reasoning Note |
|---|---|---|---|
| Distribution | Basal + subpleural + patchy | Lower-lung + symmetric | Both can be lower-lung predominant |
| Fibrosis texture | Heterogeneous | Homogeneous | Heterogeneity is a major UIP clue |
| Honeycombing | Strongly supportive | Usually absent/minimal | Advanced fibrotic NSIP may blur this |
| Subpleural sparing | Unusual | Supportive | Strong NSIP clue when real |
| Ground-glass opacity | May be present but not dominant | Common | GGO is not always reversible inflammation |
| Traction bronchiectasis | Common | Common in fibrotic NSIP | Not enough alone |
| CTD association | Possible | Common context | NSIP should strongly prompt CTD review |
| Air trapping | Suggests alternative/HP | Suggests HP/airway component | Redirects away from simple UIP-vs-NSIP |

---

## 5. Gray Zone Scenarios

### 5.1 Fibrotic NSIP vs Probable UIP

```yaml
scenario_fibrotic_nsip_vs_probable_uip:
  problem:
    - honeycombing_absent
    - traction_bronchiectasis_present
    - basal_fibrosis_present

  uip_leaning_features:
    - subpleural_basal_distribution
    - patchy_fibrosis
    - architectural_distortion
    - progressive_fibrotic_behavior

  nsip_leaning_features:
    - symmetry
    - homogeneous_fibrosis
    - subpleural_sparing
    - CTD_context
    - persistent_ground_glass_component

  missing_pieces:
    - prior_ct
    - autoimmune_screen
    - clinical_ctd_review
    - expiratory_hrct
    - mdd_review
```

### 5.2 CTD-ILD with UIP-like Fibrosis

```yaml
scenario_ctd_uip_vs_ipf:
  problem:
    - UIP_like_pattern_present
    - autoimmune_context_possible

  key_question:
    - Is the UIP-like pattern idiopathic or CTD-related?

  high_value_clues:
    - inflammatory_arthritis
    - raynaud
    - sicca
    - mechanic_hands
    - skin_thickening
    - myositis_features
    - RF
    - anti_CCP
    - ANA
    - ENA_panel
    - myositis_panel

  pitfall:
    - Do_not_call_IPF_before_systemic_context_is_reviewed
```

### 5.3 NSIP-like Pattern with Air Trapping

```yaml
scenario_nsip_like_with_air_trapping:
  problem:
    - lower_lung_ground_glass_and_reticulation
    - air_trapping_or_mosaic_attenuation_present

  consider:
    - fibrotic_hypersensitivity_pneumonitis
    - small_airways_disease
    - mixed_CT_D_airway_disease

  missing_pieces:
    - expiratory_hrct_quality
    - exposure_history
    - BAL_lymphocytosis_if_clinically_relevant
    - MDD_review
```

---

## 6. Why Not Engine

### Why not UIP?

```yaml
why_not_uip:
  - homogeneous_fibrosis
  - bilateral_symmetry
  - true_subpleural_sparing
  - dominant_ground_glass_without_honeycombing
  - CTD_context_with_NSIP_pattern
  - improvement_of_inflammatory_component
```

### Why not NSIP?

```yaml
why_not_nsip:
  - definite_honeycombing
  - patchy_heterogeneous_fibrosis
  - strong_subpleural_basal_UIP_distribution
  - progressive_honeycombing
  - extensive_architectural_distortion
  - absence_of_CT_D_or_secondary_context_does_not_exclude_but_weakens_secondary_NSIP
```

### Why not IPF?

```yaml
why_not_ipf_even_if_uip_like:
  - autoimmune_features
  - positive_CTD_serology
  - exposure_history
  - air_trapping
  - pleural_plaques
  - young_age
  - atypical_distribution
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_ct:
      reason: Needed to determine progression, stability, or partial improvement.

    autoimmune_screen:
      reason: CTD-ILD can produce both UIP-like and NSIP-like patterns.

    clinical_ctd_review:
      reason: Serology alone is not enough.

    exposure_history:
      reason: Fibrotic HP may mimic both UIP and NSIP.

    expiratory_hrct:
      reason: Air trapping can redirect reasoning toward HP or airway-centered disease.

    pft_trend:
      reason: Helps interpret clinical progression and treatment response.

    mdd_review:
      reason: Required when pattern and clinical context conflict.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  progression_toward_uip_like_behavior:
    clues:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - new_or_increasing_honeycombing
      - increasing_architectural_distortion

  partial_improvement_supporting_inflammatory_or_op_component:
    clues:
      - reduced_ground_glass
      - reduced_consolidation
      - improved_symptoms
      - improved_pft_when_available
    caution:
      - fibrosis_may_remain_even_when_inflammation_improves

  stable_fibrotic_pattern:
    clues:
      - stable_reticulation
      - stable_traction_bronchiectasis
      - stable_extent
    caution:
      - stable_disease_does_not_necessarily_resolve_diagnostic_uncertainty

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation
      - drug_toxicity
      - edema
      - pulmonary_embolism
      - rapidly_progressive_CTD_ILD
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - probable_uip_vs_fibrotic_nsip_uncertainty
    - CTD_features_present_or_uncertain
    - HP_features_present_or_uncertain
    - temporal_behavior_conflicts_with_initial_label
    - biopsy_decision_is_being_considered
    - treatment_response_is_unexpected

  rheumatology_review_high_value_if:
    - NSIP_pattern
    - female_patient_with_fibrotic_ILD
    - raynaud_or_sicca_or_inflammatory_arthritis
    - positive_or_borderline_autoantibodies
    - myositis_features

  biopsy_discussion_if:
    - imaging_and_clinical_data_remain_indeterminate
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling UIP because fibrosis is present.
    correction: Fibrosis alone is not UIP; distribution, heterogeneity, honeycombing, and context matter.

  - title: Calling NSIP because ground-glass opacity is present.
    correction: GGO may represent fine fibrosis, infection, edema, drug toxicity, OP, or acute exacerbation.

  - title: Ignoring CTD context.
    correction: Both UIP-like and NSIP-like patterns may be CTD-related.

  - title: Treating probable UIP and fibrotic NSIP as the same.
    correction: They overlap but carry different diagnostic implications.

  - title: Forgetting fibrotic HP.
    correction: Air trapping, mosaic attenuation, centrilobular nodules, and exposure history may redirect the case.

  - title: Assuming improvement means NSIP.
    correction: Improvement may reflect resolution of superimposed inflammation, OP, infection, or edema.
```

---

## 11. MVP Test Case

```yaml
case_test_uip_vs_nsip_001:
  input:
    age: 52
    sex: female
    hrct:
      - lower_lung_reticulation
      - traction_bronchiectasis
      - ground_glass_opacity
      - no_definite_honeycombing
      - possible_subpleural_sparing
    history:
      raynaud: unknown
      sicca: unknown
      exposure_history: unknown
      prior_ct: unavailable
    labs:
      autoimmune_screen: unavailable

  output:
    reasoning_state: UIP_vs_fibrotic_NSIP_gray_zone
    uip_support:
      - lower_lung_fibrosis
      - traction_bronchiectasis
    nsip_support:
      - ground_glass_component
      - possible_subpleural_sparing
      - no_definite_honeycombing
    cannot_conclude:
      - idiopathic_NSIP
      - IPF
      - CTD_ILD
      - fibrotic_HP
    missing_pieces:
      - prior_ct
      - autoimmune_screen
      - clinical_CTD_review
      - exposure_history
      - expiratory_HRCT
    final_prompt:
      - What do we still not know before choosing between UIP-like fibrosis and fibrotic NSIP?
```

---

## 12. Final Page Prompt

Every UIP vs NSIP gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Is the fibrosis heterogeneous or homogeneous?
2. Is honeycombing truly present?
3. Is subpleural sparing real?
4. Is there CTD, exposure, or drug context?
5. What does the prior CT show?
6. What do we still not know?
```