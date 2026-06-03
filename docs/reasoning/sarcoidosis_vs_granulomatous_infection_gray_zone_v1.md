# Sarcoidosis vs Granulomatous Infection — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_sarcoidosis_vs_granulomatous_infection_v1
title: Sarcoidosis vs Granulomatous Infection — Gray Zone Reasoning Map
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
  - infectious disease clinicians
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare sarcoidosis-like thoracic disease and granulomatous infection without forcing premature diagnostic certainty.

It does not diagnose sarcoidosis, tuberculosis, fungal infection, nontuberculous mycobacterial infection, opportunistic infection, malignancy, or other granulomatous diseases.

It helps users ask:

- Is the pattern truly sarcoidosis-like?
- Are there imaging features that raise concern for infection?
- Has microbiology been considered when relevant?
- Is the patient immunosuppressed?
- Are there TB, fungal, travel, endemic, occupational, or exposure clues?
- Is tissue needed, available, or potentially misleading without microbiologic context?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  sarcoidosis_pathway:
    reasoning_center: compatible_clinical_radiologic_context_with_noninfectious_granulomatous_reasoning
    classic_clues:
      - symmetric_bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_or_mid_lung_predominance
      - compatible_extrapulmonary_context
    danger_statement: sarcoidosis_should_not_be_called_before_relevant_infectious_mimics_are_considered

  granulomatous_infection_pathway:
    reasoning_center: granulomatous_disease_with_microbiologic_or_infectious_context
    classic_clues:
      - cavitation
      - tree_in_bud
      - necrotic_lymph_nodes
      - random_or_miliary_nodules
      - systemic_infectious_features
      - immunosuppression
      - TB_or_fungal_exposure_context
    danger_statement: treating_presumed_sarcoidosis_without_reviewing_infection_can_be_harmful
```

### Teaching Point

Sarcoidosis asks:

```text
Is this a compatible sarcoidosis-like clinical-radiologic pattern after relevant alternatives are considered?
```

Granulomatous infection asks:

```text
Is there microbiologic, immune, exposure, or imaging evidence that an infectious granulomatous process remains possible?
```

The key error is to see nonnecrotizing granulomas or bilateral hilar lymphadenopathy and stop thinking.

---

## 2. Features Supporting Sarcoidosis Pathway

```yaml
features_supporting_sarcoidosis_pathway:
  imaging_distribution:
    - bilateral_symmetric_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - perilymphatic_nodules
    - fissural_nodules
    - peribronchovascular_nodules
    - upper_or_mid_lung_predominance

  clinical_context:
    - compatible_multisystem_features
    - eye_or_skin_or_lymph_node_context
    - chronic_or_subacute_noninfectious_course
    - lack_of_strong_infectious_syndrome_when_appropriately_reviewed

  pathology_context_when_available:
    - nonnecrotizing_granulomatous_inflammation
    - compatible_clinical_radiologic_context
    - alternative_causes_reviewed

  reasoning_weight:
    symmetric_bilateral_hilar_lymphadenopathy: high_when_context_compatible
    perilymphatic_nodules: high
    compatible_extrapulmonary_features: moderate_to_high
    nonnecrotizing_granulomas: supportive_but_not_standalone
```

---

## 3. Features Supporting Granulomatous Infection Pathway

```yaml
features_supporting_granulomatous_infection_pathway:
  imaging_features:
    - cavitation
    - tree_in_bud
    - necrotic_lymph_nodes
    - random_nodules
    - miliary_pattern
    - endobronchial_spread_pattern
    - focal_or_lobar_consolidation
    - pleural_effusion_when_contextual

  clinical_context:
    - fever
    - night_sweats
    - weight_loss
    - immunosuppression
    - TB_exposure
    - fungal_exposure_or_endemic_context
    - occupational_or_environmental_infectious_exposure
    - travel_or_residence_risk_context

  pathology_or_microbiology_context:
    - necrotizing_granulomas
    - organisms_seen_when_available
    - positive_culture_or_molecular_test_when_available
    - microbiology_pending_or_not_performed

  reasoning_weight:
    cavitation: high
    tree_in_bud: high_for_airway_spread_or_bronchiolitis_context
    necrotic_nodes: high
    microbiologic_confirmation: very_high_when_available
    immunosuppression: high_contextual_weight
```

---

## 4. Direct Comparison Matrix

| Feature | More Sarcoidosis-like | More Infection-like | Reasoning Note |
|---|---|---|---|
| Lymphadenopathy | Symmetric hilar/mediastinal | Necrotic, asymmetric, progressive possible | Symmetry supports sarcoid-like reasoning but does not prove it |
| Nodules | Perilymphatic, fissural, peribronchovascular | Tree-in-bud, random, miliary | Nodule distribution is decisive |
| Cavitation | Atypical | Strong concern | Infection, GPA, malignancy should be reviewed |
| Tree-in-bud | Not classic | Strong concern | Suggests bronchiolitis/endobronchial spread context |
| Granuloma type | Nonnecrotizing supportive | Necrotizing more concerning | Nonnecrotizing does not fully exclude infection |
| Immune status | Variable | Immunosuppression increases concern | Opportunistic infection must remain visible |
| Microbiology | Often negative/not central | Central when suspected | Absence of testing is not negative evidence |
| Treatment implication | Immunosuppression may be considered clinically | Missing infection can be dangerous | Platform must not recommend treatment |

---

## 5. Gray Zone Scenarios

### 5.1 Typical Sarcoid-like Imaging but Infection Review Missing

```yaml
scenario_typical_sarcoid_like_imaging_infection_review_missing:
  problem:
    - bilateral_hilar_lymphadenopathy
    - perilymphatic_nodules
    - no_microbiology_available
    - infection_review_incomplete

  sarcoidosis_leaning_features:
    - symmetric_nodes
    - perilymphatic_distribution
    - upper_mid_lung_predominance
    - compatible_extrapulmonary_context_if_present

  infection_leaning_features:
    - fever_or_systemic_infectious_symptoms_if_present
    - immunosuppression
    - TB_or_fungal_exposure
    - atypical_nodes_or_cavitation_if_present

  missing_pieces:
    - infection_review
    - TB_risk_context
    - fungal_exposure_context
    - immune_status
    - prior_CT
    - microbiology_if_clinically_relevant
    - MDD_review

  pitfall:
    - Do_not_call_sarcoidosis_without_asking_whether_infection_review_is_needed
```

### 5.2 Nonnecrotizing Granulomas but Infection Not Excluded

```yaml
scenario_nonnecrotizing_granulomas_infection_not_excluded:
  problem:
    - tissue_shows_nonnecrotizing_granulomatous_inflammation
    - clinical_or_microbiologic_exclusion_incomplete

  sarcoidosis_leaning_features:
    - compatible_imaging
    - compatible_clinical_context
    - no_strong_infection_signal_after_review

  infection_leaning_features:
    - immunosuppression
    - positive_exposure_or_epidemiologic_risk
    - necrosis_absent_but_infection_still_possible_in_some_contexts
    - microbiology_not_performed_or_pending

  missing_pieces:
    - microbiology_review
    - stains_and_cultures_context
    - tissue_site_and_sampling_quality
    - clinical_infectious_context
    - MDD_review

  pitfall:
    - Nonnecrotizing_granulomas_support_sarcoidosis_but_do_not_replace_exclusion_of_alternatives
```

### 5.3 Sarcoid-like Nodes with Cavitation

```yaml
scenario_sarcoid_like_nodes_with_cavitation:
  problem:
    - lymphadenopathy_present
    - nodules_or_opacities_with_cavitation

  sarcoidosis_leaning_features:
    - symmetric_hilar_nodes
    - perilymphatic_background_nodules
    - known_sarcoidosis_context

  infection_leaning_features:
    - cavitation
    - systemic_infectious_features
    - TB_or_fungal_context
    - immunosuppression
    - new_or_rapid_change

  missing_pieces:
    - microbiology
    - TB_fungal_review
    - prior_CT
    - immune_status
    - tissue_or_sampling_context_if_needed

  pitfall:
    - Cavitation_should_trigger_infection_GPA_and_malignancy_review_not_simple_sarcoid_labeling
```

### 5.4 Random or Miliary Nodules in a Sarcoidosis-like Case

```yaml
scenario_random_or_miliary_nodules:
  problem:
    - numerous_tiny_nodules
    - distribution_uncertain_or_random

  sarcoidosis_leaning_features:
    - coexisting_perilymphatic_nodules
    - symmetric_nodes
    - compatible_multisystem_context

  infection_leaning_features:
    - random_distribution
    - miliary_pattern
    - fever_or_systemic_symptoms
    - TB_or_fungal_exposure
    - immune_suppression

  missing_pieces:
    - nodule_distribution_analysis
    - microbiology
    - immune_status
    - cancer_history
    - prior_CT
    - MDD_review

  pitfall:
    - Do_not_relabel_random_nodules_as_perilymphatic_without_distribution_analysis
```

---

## 6. Why Not Engine

### Why not sarcoidosis?

```yaml
why_not_sarcoidosis:
  - infection_review_incomplete
  - cavitation
  - tree_in_bud
  - necrotic_lymph_nodes
  - random_or_miliary_nodules
  - fever_or_systemic_infectious_syndrome
  - immunosuppression
  - TB_or_fungal_exposure_context
  - microbiology_pending_or_not_performed_when_relevant
  - rapid_new_change
```

### Why not infection?

```yaml
why_not_infection:
  - chronic_stable_typical_sarcoidosis_like_pattern
  - symmetric_bilateral_hilar_lymphadenopathy_without_necrosis
  - perilymphatic_nodules_without_tree_in_bud_or_random_pattern
  - no_infectious_context_after_appropriate_review
  - microbiology_negative_when_appropriately_obtained
  - compatible_extrapulmonary_sarcoidosis_context
```

### Why not stop at “granulomatous inflammation”?

```yaml
why_not_stop_at_granulomatous_inflammation:
  - granulomas_have_broad_differential
  - tissue_findings_require_clinical_and_microbiologic_context
  - nonnecrotizing_granulomas_are_supportive_not_absolute
  - infection_and_occupational_mimics_must_remain_visible
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    microbiology:
      reason: Infection cannot be considered excluded without clinically appropriate microbiologic review.

    immune_status:
      reason: Immunosuppression changes the infectious differential and risk profile.

    TB_risk_context:
      reason: TB can mimic sarcoidosis and may present with granulomatous disease.

    fungal_exposure_context:
      reason: Endemic or environmental fungal infections can mimic sarcoidosis.

    nodule_distribution_analysis:
      reason: Perilymphatic, centrilobular, and random nodules imply different pathways.

    lymph_node_characterization:
      reason: Symmetric, necrotic, asymmetric, or progressive nodes change reasoning.

    prior_CT:
      reason: Stability, progression, new cavitation, or new nodules may redirect reasoning.

    tissue_context:
      reason: Granulomas are not enough without clinical, radiologic, and exclusion context.

    MDD_review:
      reason: Sarcoidosis versus infection often requires radiology, pulmonology, pathology, microbiology, and clinical context integration.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  stable_typical_sarcoid_like_pattern:
    clues:
      - stable_symmetric_nodes
      - stable_perilymphatic_nodules
      - no_new_cavitation
      - no_new_random_nodules
    caution:
      - stability_supports_but_does_not_prove_noninfectious_context

  spontaneous_or_treatment_related_improvement:
    clues:
      - decreasing_nodes
      - decreasing_nodules
      - improving_opacities
    caution:
      - improvement_can_occur_in_inflammatory_or_treated_infectious_processes_too

  rapid_worsening:
    consider:
      - infection
      - superimposed_infection_on_sarcoidosis
      - drug_toxicity
      - malignancy
      - pulmonary_embolism
      - inflammatory_flare

  new_cavitation_or_tree_in_bud:
    consider:
      - TB_or_NTM
      - fungal_infection
      - bacterial_infection
      - aspiration_or_bronchiolitis
      - GPA_or_malignancy_context
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - sarcoidosis_like_pattern_but_infection_review_incomplete
    - tissue_shows_granulomas_but_microbiology_context_uncertain
    - cavitation_or_tree_in_bud_present
    - immunosuppression_present
    - TB_or_fungal_risk_context_present
    - rapid_change_or_systemic_infectious_features_present
    - treatment_decision_depends_on_confidence

  microbiology_review_high_value_if:
    - cavitation
    - tree_in_bud
    - necrotic_nodes
    - random_or_miliary_nodules
    - immunosuppression
    - TB_or_fungal_exposure
    - fever_or_systemic_symptoms

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_review
    - infection_or_malignancy_must_be_excluded
    - accessible_lymph_node_or_lung_target_exists
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling sarcoidosis before infection review.
    correction: Relevant infectious mimics must remain visible, especially TB, fungal infection, NTM, and opportunistic infection.

  - title: Treating nonnecrotizing granulomas as definitive.
    correction: Nonnecrotizing granulomas support sarcoidosis only in compatible context and after alternative causes are considered.

  - title: Ignoring cavitation.
    correction: Cavitation should trigger infection, GPA, and malignancy review.

  - title: Ignoring tree-in-bud.
    correction: Tree-in-bud suggests airway-centered spread or bronchiolitis context and is not classic simple sarcoidosis reasoning.

  - title: Forgetting immune status.
    correction: Immunosuppression changes the infectious differential and lowers the threshold for microbiology review.

  - title: Calling random nodules perilymphatic.
    correction: Nodule distribution must be actively analyzed, not assumed.

  - title: Starting from a treatment mindset.
    correction: The platform must not recommend treatment and must preserve diagnostic uncertainty.
```

---

## 11. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT

  supportive_review_sources:
    - DIFFERENTIAL_DIAGNOSIS_OF_PULMONARY_SARCOIDOSIS_2023_REVIEW
    - GRANULOMATOUS_LUNG_DISEASE_REVIEW_SOURCES_PENDING

  evidence_notes:
    - ATS diagnostic framework requires compatible context and exclusion of alternative granulomatous causes.
    - BTS supports pulmonary sarcoidosis clinical context but does not remove mimic review.
    - Infection review must remain visible before increasing sarcoidosis confidence.
```

---

## 12. MVP Test Case

```yaml
case_test_sarcoidosis_vs_infection_001:
  input:
    age: 45
    sex: male
    hrct:
      - bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_lung_predominance
      - no_cavitation_reported
      - no_tree_in_bud_reported
    history:
      fever: unknown
      night_sweats: unknown
      weight_loss: unknown
      TB_exposure: unknown
      fungal_exposure: unknown
      immunosuppression: unknown
      prior_CT: unavailable
    tissue:
      nonnecrotizing_granulomas: unavailable
    microbiology:
      unavailable

  output:
    reasoning_state: sarcoidosis_like_pattern_vs_infection_not_excluded
    sarcoidosis_support:
      - bilateral_hilar_lymphadenopathy
      - perilymphatic_nodules
      - upper_lung_predominance
    infection_support:
      - infection_review_incomplete
      - microbiology_unavailable
      - TB_and_fungal_context_unknown
      - immune_status_unknown
    cannot_conclude:
      - sarcoidosis
      - infection_excluded
      - granulomatous_infection
    missing_pieces:
      - infection_review
      - microbiology_if_clinically_relevant
      - TB_risk_context
      - fungal_exposure_context
      - immune_status
      - prior_CT
      - tissue_context_if_needed
      - MDD_review
    final_prompt:
      - What infectious granulomatous mimics remain possible before calling this sarcoidosis?
```

---

## 13. Final Page Prompt

Every Sarcoidosis vs Granulomatous Infection page should end with:

```text
Do not force the label.

Ask:
1. Is the pattern truly sarcoidosis-like?
2. Are there cavitation, tree-in-bud, necrotic nodes, or random/miliary nodules?
3. Is the patient immunosuppressed?
4. Is there TB, fungal, NTM, travel, or exposure context?
5. Has microbiology been considered when relevant?
6. Is tissue needed, available, or misleading without microbiologic context?
7. What does the prior CT show?
8. What do we still not know?
```