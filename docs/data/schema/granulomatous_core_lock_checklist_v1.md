# Granulomatous Core Lock Checklist — v1

## Document Metadata

```yaml
id: data_schema_granulomatous_core_lock_checklist_v1
title: Granulomatous Core Lock Checklist
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: validation_checklist
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This checklist defines the structural lock criteria for the Granulomatous ILD Core v0.2.

It verifies that the module is:

- cross-linked,
- evidence-aware,
- uncertainty-preserving,
- mimic-aware,
- safe from diagnostic overreach,
- and ready for future expert review.

This lock does not mean public clinical readiness.

It means the blueprint structure is internally coherent.

---

## 1. Required Granulomatous Core Files

```yaml
required_granulomatous_core_files:
  pattern_pages:
    - docs/patterns/sarcoidosis_pattern_gold_standard_v1.md
    - docs/patterns/sarcoidosis_pattern_taxonomy_v1.md
    - docs/patterns/glild_pattern_gold_standard_v1.md

  reasoning_maps:
    - docs/reasoning/granulomatous_ild_reasoning_map_v1.md
    - docs/reasoning/sarcoidosis_vs_granulomatous_infection_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_glild_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1.md
    - docs/reasoning/fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1.md

  navigation:
    - docs/navigation/granulomatous_crosslink_registry_v1.md

  evidence:
    - docs/evidence/guideline_registry_v1.md

  editorial_safety:
    - docs/editorial/editorial_policy_v1.md
    - docs/editorial/source_review_protocol_v1.md
```

---

## 2. Granulomatous Core Coverage

```yaml
granulomatous_core_coverage:
  sarcoidosis_pattern_model:
    required:
      - typical_nodal_perilymphatic_pattern
      - parenchymal_perilymphatic_nodular_pattern
      - alveolar_or_consolidative_pattern
      - nodular_or_mass_like_pattern
      - miliary_like_or_random_nodular_pattern
      - airway_dominant_pattern
      - fibrotic_sarcoidosis_pattern
      - fibrocystic_or_cystic_complication_pattern
      - atypical_or_mimic_dominant_pattern

  required_gray_zone_domains:
    - infection
    - hypersensitivity_pneumonitis
    - GLILD_or_immune_deficiency
    - occupational_mimics
    - malignancy_or_sarcoid_like_reaction
    - chronic_HP_vs_fibrotic_sarcoidosis
    - GPA_or_granulomatous_vasculitis
```

---

## 3. Safety Boundary Checks

```yaml
granulomatous_safety_boundary_checks:
  platform_must_not:
    - diagnose_sarcoidosis_from_imaging_alone
    - diagnose_GLILD_from_imaging_alone
    - diagnose_GPA_from_cavitating_nodules_alone
    - diagnose_malignancy_or_sarcoid_like_reaction_from_FDG_uptake_alone
    - ignore_infection
    - ignore_HP_clues
    - ignore_occupational_exposure
    - ignore_CVID_or_immune_deficiency_context
    - ignore_malignancy_or_lymphoma_context
    - ignore_vasculitic_red_flags
    - treat_granulomas_as_final_diagnosis
    - treat_unknown_exposure_as_negative_exposure
    - use_treatment_guidelines_as_diagnostic_authority

  platform_must:
    - preserve_uncertainty
    - expose_missing_data
    - show_mimics
    - identify_red_flags
    - link_to_evidence_registry
    - trigger_MDD_when_context_conflicts
```

---

## 4. Required Red Flag Coverage

```yaml
required_red_flags:
  infection_red_flags:
    - cavitation
    - tree_in_bud
    - necrotic_lymph_nodes
    - random_or_miliary_nodules
    - immunosuppression
    - TB_or_fungal_context

  HP_red_flags:
    - centrilobular_ground_glass_nodules
    - air_trapping
    - mosaic_attenuation
    - three_density_pattern
    - antigen_exposure
    - recurrent_worsening_after_exposure

  GLILD_red_flags:
    - known_or_suspected_CVID
    - hypogammaglobulinemia
    - recurrent_sinopulmonary_infections
    - splenomegaly
    - cytopenias
    - lymphoproliferative_context

  occupational_red_flags:
    - beryllium_exposure
    - silica_or_dust_exposure
    - mining_quarry_sandblasting_stone_construction_foundry_context
    - calcified_or_eggshell_nodes
    - progressive_massive_fibrosis_pattern

  oncology_red_flags:
    - known_or_prior_malignancy
    - FDG_avid_nodes_without_context
    - immune_checkpoint_inhibitor_context
    - asymmetric_progressive_lymphadenopathy
    - new_or_growing_nodule_or_mass
    - lymphoma_context

  vasculitis_red_flags:
    - cavitating_nodules
    - destructive_sinonasal_disease
    - subglottic_or_tracheobronchial_stenosis
    - hemoptysis_or_DAH_context
    - hematuria_or_proteinuria
    - renal_dysfunction
    - ANCA_context
```

---

## 5. Missing Piece Engine Coverage

```yaml
required_missing_piece_items:
  universal:
    - prior_CT
    - tissue_context
    - infection_review
    - microbiology_when_relevant
    - MDD_review

  sarcoidosis_specific:
    - extrapulmonary_review
    - nodule_distribution_analysis
    - lymph_node_characterization

  HP_specific:
    - expiratory_HRCT
    - exposure_history
    - BAL_lymphocytosis_when_relevant

  GLILD_specific:
    - immunoglobulin_levels
    - CVID_or_antibody_deficiency_review
    - recurrent_infection_history
    - splenomegaly_and_cytopenia_review

  occupational_specific:
    - occupational_history
    - beryllium_exposure_assessment
    - BeLPT_when_relevant
    - exposure_duration_intensity_latency

  oncology_specific:
    - cancer_history
    - treatment_timeline
    - prior_CT_or_PET_CT
    - FDG_distribution_review
    - tissue_sampling_target

  vasculitis_specific:
    - ENT_and_airway_context
    - urinalysis
    - renal_function
    - ANCA_testing_context
    - pathology_detail_for_necrosis_or_vasculitis
```

---

## 6. Evidence Registry Integrity

```yaml
evidence_registry_integrity:
  required_source_groups:
    sarcoidosis:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT

    HP:
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS

    GLILD:
      - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT
      - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
      - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024

    occupational:
      - ATS_2014_BERYLLIUM_SENSITIVITY_AND_CHRONIC_BERYLLIUM_DISEASE_STATEMENT
      - occupational_lung_disease_review_sources

    oncology_sarcoid_like_reaction:
      - ICI_related_sarcoid_like_reaction_or_PET_CT_review_sources
      - oncology_candidate_sources_pending_review

    GPA_AAV:
      - ACR_VF_2021_ANCA_ASSOCIATED_VASCULITIS_GUIDELINE
      - EULAR_2022_ANCA_ASSOCIATED_VASCULITIS_RECOMMENDATIONS
      - GPA_thoracic_imaging_review_sources
```

### Evidence Safety Rule

```yaml
evidence_safety_rule:
  - diagnosis_guidelines_must_not_be_used_as_treatment_authority
  - treatment_or_management_guidelines_must_not_be_used_as_imaging_only_diagnostic_authority
  - imaging_reviews_support_pattern_awareness_not_final_diagnosis
  - candidate_sources_must_remain_labeled_needs_verification
  - public_ready_status_requires_full_source_and_expert_review
```

---

## 7. Crosslink Integrity

```yaml
crosslink_integrity:
  required:
    - sarcoidosis_pattern_links_to_granulomatous_reasoning_map
    - sarcoidosis_pattern_links_to_all_gray_zone_modules
    - glild_pattern_links_to_sarcoidosis_vs_glild
    - granulomatous_reasoning_map_links_to_sarcoidosis_GLILD_HP_infection_occupational_oncology_GPA_contexts
    - crosslink_registry_lists_all_implemented_modules
    - remaining_high_priority_modules_marked_none_for_v0_2_core

  required_existing_links:
    - sarcoidosis_vs_granulomatous_infection
    - sarcoidosis_vs_hypersensitivity_pneumonitis
    - sarcoidosis_vs_GLILD
    - sarcoidosis_vs_berylliosis_or_pneumoconiosis
    - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction
    - fibrotic_sarcoidosis_vs_chronic_HP
    - sarcoidosis_vs_GPA_or_granulomatous_vasculitis
```

---

## 8. Temporal Reasoning Integrity

```yaml
temporal_reasoning_integrity:
  required_states:
    - stability
    - progression
    - regression_or_improvement
    - unexpectedly_fast_worsening
    - new_focal_change
    - treatment_timeline_dependent_change
    - exposure_related_recurrence
    - immune_deficiency_related_waxing_waning_behavior

  safety_rule:
    - A_single_CT_snapshot_must_not_be_treated_as_proof_of_progression_or_regression.
    - Prior_CT_or_longitudinal_context_should_be_requested_when_temporal_reasoning_is_needed.
```

---

## 9. MDD / Specialist Review Coverage

```yaml
MDD_and_specialist_review_coverage:
  required_review_prompts:
    - pulmonary_review
    - thoracic_radiology_review
    - pathology_review
    - microbiology_review
    - infectious_disease_review_when_relevant
    - immunology_review_when_GLILD_or_CVID_possible
    - occupational_medicine_review_when_exposure_possible
    - oncology_or_hematology_review_when_malignancy_or_lymphoma_possible
    - rheumatology_review_when_GPA_or_AAV_possible
    - nephrology_review_when_renal_or_pulmonary_renal_context_possible
    - ENT_review_when_destructive_sinonasal_or_airway_stenosis_context_possible
```

---

## 10. v0.2 Granulomatous Core Lock Criteria

```yaml
v0_2_granulomatous_core_lock_criteria:
  pattern_core:
    - sarcoidosis_pattern_gold_standard_v1
    - sarcoidosis_pattern_taxonomy_v1
    - glild_pattern_gold_standard_v1

  reasoning_core:
    - granulomatous_ild_reasoning_map_v1
    - sarcoidosis_vs_granulomatous_infection_gray_zone_v1
    - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1
    - sarcoidosis_vs_glild_gray_zone_v1
    - sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1
    - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
    - fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1
    - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1

  evidence_core:
    - sarcoidosis_sources_registered
    - HP_sources_registered
    - GLILD_sources_registered
    - occupational_sources_registered
    - oncology_sarcoid_like_reaction_sources_registered
    - GPA_AAV_sources_registered

  navigation_core:
    - granulomatous_crosslink_registry_v1
    - all_implemented_modules_listed
    - remaining_high_priority_modules_none_for_v0_2_core

  safety_core:
    - no_imaging_only_diagnosis
    - no_treatment_recommendation
    - no_final_patient_classification
    - uncertainty_preserved
    - missing_data_visible
    - mimics_visible
    - MDD_prompts_present
```

---

## 11. v0.2 Lock Statement

```yaml
v0_2_lock_statement:
  status: structurally_locked_blueprint
  public_ready: false
  clinical_use: educational_reasoning_support_only
  expert_review_required: true
  source_full_text_review_required: true
  diagnostic_authority: none
```

---

## 12. Final Lock Rule

A valid Granulomatous ILD Core page must answer:

```text
1. What granulomatous pattern is being considered?
2. What supports sarcoidosis-like reasoning?
3. What weakens sarcoidosis-like reasoning?
4. What infection, HP, GLILD, occupational, oncology, or vasculitis mimic remains possible?
5. What missing data would change the reasoning?
6. What does the prior CT show?
7. Is tissue available, needed, or potentially misleading without context?
8. Is MDD or specialist review needed?
9. What do we still not know?
```