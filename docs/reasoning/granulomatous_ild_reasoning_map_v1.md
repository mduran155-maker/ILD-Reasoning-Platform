# Granulomatous ILD — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_granulomatous_ild_reasoning_map_v1
title: Granulomatous ILD — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
linked_future_patterns:
  - sarcoidosis_pattern_gold_standard_v1
  - granulomatous_infection_pattern_v1
  - hp_granulomatous_context_v1
  - glild_pattern_v1
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

This reasoning map helps users think through granulomatous interstitial lung disease without prematurely labeling the case as sarcoidosis.

It does not diagnose sarcoidosis, hypersensitivity pneumonitis, infection, GLILD, vasculitis, berylliosis, malignancy, or sarcoid-like reaction.

It helps users ask:

- Is this truly a granulomatous ILD pattern?
- Is the clinical-radiologic context compatible with sarcoidosis?
- Has infection been reasonably considered?
- Are there exposure, immune deficiency, occupational, vasculitic, or malignancy-related clues?
- Is tissue confirmation needed?
- What alternative granulomatous causes remain possible?
- What do we still not know?

---

## 1. Core Diagnostic Caution

```yaml
core_diagnostic_caution:
  key_statement: Sarcoidosis is a diagnosis of compatible context plus exclusion, not a single imaging label.
  ats_diagnostic_framework:
    - compatible_clinical_presentation
    - nonnecrotizing_granulomatous_inflammation_when_tissue_is_required_or_available
    - exclusion_of_alternative_causes_of_granulomatous_disease
  platform_rule:
    - do_not_call_sarcoidosis_from_imaging_alone
    - do_not_ignore_infection_or_occupational_mimics
    - preserve_uncertainty_when_tissue_or_exclusion_data_are_missing
```

---

## 2. Main Reasoning Pathways

```yaml
main_reasoning_pathways:
  sarcoidosis_pathway:
    reasoning_center: compatible_clinical_radiologic_context_with_granulomatous_inflammation_and_exclusion_of_mimics
    supportive_clues:
      - bilateral_hilar_or_mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_or_mid_lung_predominance
      - fissural_or_peribronchovascular_nodules
      - extrapulmonary_features_when_present
      - compatible_tissue_if_available
    danger_statement: sarcoidosis_should_not_be_diagnosed_without_considering_alternative_granulomatous_disease

  granulomatous_infection_pathway:
    reasoning_center: infection_can_mimic_sarcoidosis_and_must_be_considered
    supportive_clues:
      - necrotizing_granulomas_when_present
      - cavitation
      - tree_in_bud_or_endobronchial_spread
      - fever_or_systemic_infectious_context
      - immunosuppression
      - TB_or_fungal_exposure_context
    danger_statement: immunosuppression_for_presumed_sarcoidosis_can_be_harmful_if_infection_is_missed

  hypersensitivity_pneumonitis_pathway:
    reasoning_center: exposure_related_granulomatous_small_airway_ILD
    supportive_clues:
      - exposure_history
      - centrilobular_ground_glass_nodules
      - mosaic_attenuation
      - air_trapping
      - three_density_pattern
      - BAL_lymphocytosis_when_available
    danger_statement: HP_can_overlap_with_granulomatous_reasoning_and_should_not_be_missed

  berylliosis_or_occupational_pathway:
    reasoning_center: occupational_granulomatous_disease_can_mimic_sarcoidosis
    supportive_clues:
      - beryllium_exposure
      - aerospace_or_metal_industry_context
      - compatible_granulomatous_disease
      - BeLPT_when_available
    danger_statement: occupational_history_is_not_optional_in_granulomatous_ILD

  glild_pathway:
    reasoning_center: immune_deficiency_related_granulomatous_lymphocytic_ILD
    supportive_clues:
      - common_variable_immunodeficiency_context
      - recurrent_infections
      - lymphadenopathy
      - splenomegaly
      - nodules_ground_glass_or_consolidation
    danger_statement: GLILD_should_be_considered_when_granulomatous_ILD_occurs_in_CVID_or_immune_deficiency_context

  vasculitis_or_gpa_pathway:
    reasoning_center: granulomatous_vasculitic_disease_can_mimic_nodular_or_airway_sarcoid
    supportive_clues:
      - cavitating_nodules
      - sinonasal_or_renal_context
      - hematuria
      - ANCA_context
      - airway_stenosis_or_tracheobronchial_disease
    danger_statement: cavitary_or_destructive_airway_disease_should_not_be_called_typical_sarcoidosis

  malignancy_or_sarcoid_like_reaction_pathway:
    reasoning_center: malignancy_and_treatment_related_sarcoid_like_reactions_can_mimic_granulomatous_disease
    supportive_clues:
      - known_malignancy
      - asymmetric_or_progressive_lymphadenopathy
      - new_mass_or_nodule
      - therapy_related_context
      - discordant_clinical_course
    danger_statement: new_or_asymmetric_findings_require_malignancy_review
```

---

## 3. Imaging Pattern Clues

```yaml
imaging_pattern_clues:
  perilymphatic_nodules:
    supports:
      - sarcoidosis
      - pneumoconiosis
      - lymphangitic_malignancy_context_dependent
    questions:
      - Are nodules along fissures, pleura, and bronchovascular bundles?
      - Is there symmetric hilar/mediastinal lymphadenopathy?
      - Is there occupational dust exposure?

  centrilobular_ground_glass_nodules:
    supports:
      - hypersensitivity_pneumonitis
      - infectious_bronchiolitis
      - respiratory_bronchiolitis
    questions:
      - Is there air trapping?
      - Is there exposure history?
      - Is expiratory HRCT available?

  random_nodules:
    supports:
      - hematogenous_infection
      - metastases
      - miliary_TB
    questions:
      - Is the distribution truly random?
      - Is there systemic infection or malignancy context?

  lymphadenopathy:
    supports:
      - sarcoidosis
      - infection
      - lymphoma
      - malignancy
      - GLILD
    questions:
      - Is it symmetric or asymmetric?
      - Is there necrosis or calcification?
      - Is there known malignancy or immune deficiency?

  upper_lung_fibrosis:
    supports:
      - fibrotic_sarcoidosis
      - chronic_HP
      - pneumoconiosis
      - pleuroparenchymal_fibroelastosis
    questions:
      - Are there perilymphatic nodules or airway distortion?
      - Are there exposure clues?
      - Is there prior CT showing evolution?

  cavitation:
    supports:
      - infection
      - GPA
      - malignancy
      - rheumatoid_nodules
    questions:
      - Is this atypical for sarcoidosis?
      - Is infectious/vasculitic workup needed?
```

---

## 4. Direct Comparison Matrix

| Feature | Sarcoidosis-like | HP-like | Infection-like | GLILD-like | GPA/Vasculitis-like | Malignancy-like |
|---|---|---|---|---|---|---|
| Nodules | Perilymphatic | Centrilobular | Tree-in-bud/random | Nodules + GGO/consolidation | Nodules/cavitation | Random/asymmetric |
| Lymph nodes | Symmetric hilar/mediastinal | Variable | Necrotic possible | Common | Variable | Asymmetric/progressive possible |
| Air trapping | Can occur but not central | Strong clue | Bronchiolitis context | Possible | Airway disease possible | Not primary clue |
| Cavitation | Atypical | Not typical | Important clue | Not typical | Strong clue | Possible |
| Exposure history | Occupational mimic possible | Central | TB/fungal exposure | Not central | Not central | Cancer/therapy context |
| Immune context | Variable | Variable | Immunosuppression important | CVID/immune deficiency | Autoimmune/vasculitic | Cancer/immunotherapy context |
| Tissue role | Often important | Sometimes important | Microbiology critical | Often important | Often important | Often important |

---

## 5. Gray Zone Scenarios

### 5.1 Sarcoidosis vs Granulomatous Infection

```yaml
scenario_sarcoidosis_vs_infection:
  problem:
    - granulomatous_disease_suspected
    - imaging_may_show_nodules_or_lymphadenopathy

  sarcoidosis_leaning_features:
    - symmetric_bilateral_hilar_lymphadenopathy
    - perilymphatic_nodules
    - compatible_extrapulmonary_context
    - nonnecrotizing_granulomas_if_tissue_available

  infection_leaning_features:
    - necrotizing_granulomas
    - cavitation
    - tree_in_bud
    - fever_or_infectious_syndrome
    - immunosuppression
    - TB_or_fungal_exposure

  missing_pieces:
    - microbiology
    - tissue_context_if_needed
    - immune_status
    - exposure_and_travel_history
    - prior_CT
    - MDD_review

  pitfall:
    - Do_not_start_sarcoidosis_reasoning_without_excluding_relevant_infections
```

### 5.2 Sarcoidosis vs HP

```yaml
scenario_sarcoidosis_vs_hp:
  problem:
    - granulomatous_or_nodular_ILD_possible
    - small_nodules_and_ground_glass_present

  sarcoidosis_leaning_features:
    - perilymphatic_nodules
    - fissural_nodules
    - symmetric_hilar_lymphadenopathy
    - upper_mid_lung_distribution

  hp_leaning_features:
    - centrilobular_ground_glass_nodules
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - exposure_history
    - BAL_lymphocytosis_when_available

  missing_pieces:
    - expiratory_HRCT
    - exposure_history
    - BAL_if_relevant
    - lymph_node_or_lung_tissue_context_if_needed
    - MDD_review

  pitfall:
    - Do_not_call_all_small_nodules_sarcoidosis_without_distribution_analysis
```

### 5.3 Sarcoidosis vs GLILD

```yaml
scenario_sarcoidosis_vs_glild:
  problem:
    - granulomatous_ILD_with_lymphadenopathy_or_nodules

  sarcoidosis_leaning_features:
    - typical_sarcoid_distribution
    - compatible_extrapulmonary_sarcoid_context
    - no_known_immunodeficiency

  glild_leaning_features:
    - CVID_context
    - recurrent_infections
    - hypogammaglobulinemia
    - splenomegaly
    - lymphoproliferative_features

  missing_pieces:
    - immunoglobulin_levels
    - recurrent_infection_history
    - immune_deficiency_review
    - pathology_context
    - MDD_review

  pitfall:
    - Do_not_call_sarcoidosis_without_checking_immune_deficiency_context_when_clues_exist
```

### 5.4 Sarcoidosis vs Malignancy / Sarcoid-like Reaction

```yaml
scenario_sarcoidosis_vs_malignancy_or_sarcoid_like_reaction:
  problem:
    - lymphadenopathy_or_nodules_in_cancer_or_post_treatment_context

  sarcoidosis_or_sarcoid_like_supporting_features:
    - symmetric_nodes
    - granulomatous_tissue_when_available
    - therapy_related_context_possible

  malignancy_supporting_features:
    - asymmetric_progressive_lymphadenopathy
    - new_or_growing_mass
    - systemic_cancer_context
    - discordant_PET_or_clinical_course
    - tissue_suspicious_for_malignancy

  missing_pieces:
    - prior_imaging
    - cancer_history
    - treatment_history
    - tissue_confirmation_when_needed
    - oncology_context
    - MDD_review

  pitfall:
    - Do_not_dismiss_new_asymmetric_findings_as_sarcoidosis
```

---

## 6. Why Not Engine

```yaml
why_not_sarcoidosis:
  - infection_not_excluded
  - occupational_mimic_not_reviewed
  - HP_clues_present
  - immune_deficiency_context
  - cavitation_or_tree_in_bud
  - asymmetric_progressive_nodes
  - known_malignancy_context
  - destructive_sinonasal_or_renal_vasculitic_context
  - atypical_distribution_without_supporting_context

why_not_HP:
  - no_exposure_after_high_quality_assessment
  - no_air_trapping_or_mosaic_attenuation
  - perilymphatic_distribution_instead_of_centrilobular
  - symmetric_hilar_lymphadenopathy_dominates
  - alternative_granulomatous_context_stronger

why_not_infection:
  - no_systemic_or_microbiologic_support
  - chronic_stable_typical_sarcoid_pattern
  - negative_relevant_microbiology_when_appropriately_tested
  - no_immunosuppression_or_exposure_context
  - tissue_and_clinical_context_support_noninfectious_disease

why_not_stop_at_granulomatous_ILD:
  - granulomas_have_a_broad_differential
  - imaging_pattern_distribution_matters
  - microbiology_and_exposure_context_matter
  - tissue_without_context_can_mislead
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    distribution_analysis:
      reason: Perilymphatic, centrilobular, and random nodules imply different reasoning paths.

    microbiology:
      reason: Infection must be considered before labeling granulomatous disease as sarcoidosis.

    tissue_context:
      reason: Nonnecrotizing granulomas support sarcoidosis only in compatible context and after exclusions.

    exposure_history:
      reason: HP, berylliosis, and occupational mimics require exposure review.

    immune_status:
      reason: CVID/GLILD and opportunistic infections may mimic sarcoidosis.

    cancer_history:
      reason: Malignancy and sarcoid-like reactions can mimic granulomatous disease.

    extrapulmonary_review:
      reason: Eye, skin, cardiac, neurologic, hepatic, and calcium-related clues may change reasoning.

    prior_CT:
      reason: Temporal behavior can reveal stability, progression, infection, malignancy, or fibrotic evolution.

    MDD_review:
      reason: Granulomatous ILD often requires radiology, pulmonary, pathology, microbiology, and sometimes rheumatology/oncology integration.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  spontaneous_improvement_or_stability:
    supports:
      - sarcoidosis_possible_in_compatible_context
      - resolving_inflammatory_process_possible
    caution:
      - improvement_does_not_exclude_infection_or_treatment_effect_without_context

  progressive_fibrosis:
    consider:
      - fibrotic_sarcoidosis
      - chronic_HP
      - pneumoconiosis
      - PPFE
      - other_fibrotic_ILD

  rapid_worsening:
    consider:
      - infection
      - acute_inflammatory_flare
      - drug_toxicity
      - malignancy
      - pulmonary_embolism
      - cardiac_or_pulmonary_vascular_complication

  new_asymmetric_node_or_mass:
    consider:
      - malignancy
      - infection
      - lymphoma
      - atypical_sarcoid_course
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - infection_vs_sarcoidosis_uncertainty
    - malignancy_context_present
    - immune_deficiency_context_present
    - occupational_granulomatous_mimic_possible
    - vasculitic_features_present
    - tissue_result_and_imaging_context_conflict
    - treatment_decision_depends_on_diagnostic_confidence

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_review
    - infection_or_malignancy_must_be_excluded
    - result_would_change_management
    - accessible_lymph_node_or_organ_target_exists
    - patient_risk_is_acceptable

  microbiology_review_high_value_if:
    - cavitation
    - tree_in_bud
    - necrotizing_granuloma
    - immunosuppression
    - TB_or_fungal_exposure_context
    - systemic_infectious_features

  immunology_review_high_value_if:
    - recurrent_infections
    - hypogammaglobulinemia
    - splenomegaly
    - CVID_context
    - GLILD_suspected
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling sarcoidosis from bilateral hilar lymphadenopathy alone.
    correction: Typical imaging supports sarcoidosis but does not replace clinical context and exclusion of mimics.

  - title: Ignoring infection before sarcoidosis treatment.
    correction: TB, fungal infection, and opportunistic infection must be considered when relevant.

  - title: Treating all small nodules as sarcoid nodules.
    correction: Nodule distribution matters: perilymphatic, centrilobular, and random patterns imply different pathways.

  - title: Missing HP in granulomatous reasoning.
    correction: Centrilobular nodules, air trapping, mosaic attenuation, and exposure history should redirect toward HP.

  - title: Missing GLILD.
    correction: Granulomatous ILD in immune deficiency or CVID context should not be called simple sarcoidosis.

  - title: Missing malignancy or sarcoid-like reaction.
    correction: Cancer history, asymmetric nodes, new masses, or discordant course require malignancy review.

  - title: Ignoring occupational mimics.
    correction: Berylliosis and pneumoconiosis can mimic sarcoidosis and require occupational history.
```

---

## 11. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - ATS_JRS_ALAT_2020_HP_DIAGNOSIS

  secondary_sources:
    - ERS_2021_SARCOIDOSIS_TREATMENT
    - BTS_SARCOIDOSIS_CLINICAL_STATEMENT
    - future_GLILD_consensus_sources
    - future_granulomatous_infection_sources

  evidence_notes:
    - Sarcoidosis diagnosis requires compatible context, granulomatous inflammation when needed/available, and exclusion of alternatives.
    - Treatment guidelines must not be used as diagnostic authority.
    - HP diagnostic reasoning requires exposure, HRCT, BAL/pathology when appropriate, and MDD.
    - Granulomatous infection and malignancy must remain visible mimics.
```

---

## 12. MVP Test Case

```yaml
case_test_granulomatous_ild_001:
  input:
    age: 42
    sex: female
    hrct:
      - bilateral_hilar_lymphadenopathy
      - perilymphatic_nodules
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
      prior_CT: unavailable
    tissue:
      granulomas: unavailable
    microbiology:
      unavailable

  output:
    reasoning_state: sarcoidosis_like_granulomatous_ILD_pattern_but_not_diagnostic
    sarcoidosis_support:
      - bilateral_hilar_lymphadenopathy
      - perilymphatic_nodules
      - upper_lung_predominance
    cannot_conclude:
      - sarcoidosis
      - infection_excluded
      - HP_excluded
      - malignancy_excluded
      - GLILD_excluded
    missing_pieces:
      - infection_review
      - exposure_history
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

## 13. Final Page Prompt

Every granulomatous ILD reasoning page should end with:

```text
Do not force the label.

Ask:
1. Is the nodule distribution perilymphatic, centrilobular, or random?
2. Is the lymphadenopathy symmetric, asymmetric, necrotic, or progressive?
3. Has infection been considered?
4. Is there exposure, occupational, immune deficiency, vasculitic, or malignancy context?
5. Is tissue needed, available, or misleading without context?
6. What does the prior CT show?
7. What do we still not know?
```