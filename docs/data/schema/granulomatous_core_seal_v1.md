# Granulomatous Core Seal — v1

## Document Metadata

```yaml
id: data_schema_granulomatous_core_seal_v1
title: Granulomatous Core Seal
version: v1
language: English
status: blueprint_seal
project: ILD Reasoning Platform
content_type: module_seal
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This document seals the Granulomatous ILD Core v0.2 blueprint.

The seal confirms that the module has reached structural coherence across:

- pattern atlas pages,
- granulomatous reasoning maps,
- gray-zone safety modules,
- evidence registry entries,
- crosslink registry routing,
- editorial safety rules,
- missing data logic,
- mimic awareness,
- and MDD escalation prompts.

This seal does not mean public clinical readiness.

It means the v0.2 Granulomatous ILD Core blueprint is structurally locked for future expert review and implementation planning.

---

## 1. Seal Scope

```yaml
seal_scope:
  module: Granulomatous ILD Core
  version: v0.2
  seal_type: structural_blueprint_lock
  public_ready: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  expert_review_required: true
  full_source_review_required: true
```

---

## 2. Locked Pattern Core

```yaml
locked_pattern_core:
  sarcoidosis_pattern:
    path: docs/patterns/sarcoidosis_pattern_gold_standard_v1.md
    role: primary_sarcoidosis_pattern_datasheet
    status: locked_blueprint

  sarcoidosis_pattern_taxonomy:
    path: docs/patterns/sarcoidosis_pattern_taxonomy_v1.md
    role: thoracic_sarcoidosis_pattern_family_taxonomy
    status: locked_blueprint

  glild_pattern:
    path: docs/patterns/glild_pattern_gold_standard_v1.md
    role: immune_deficiency_granulomatous_pattern_datasheet
    status: locked_blueprint
```

---

## 3. Locked Reasoning Core

```yaml
locked_reasoning_core:
  central_reasoning_map:
    path: docs/reasoning/granulomatous_ild_reasoning_map_v1.md
    role: central_granulomatous_reasoning_engine
    status: locked_blueprint

  gray_zone_modules:
    sarcoidosis_vs_infection:
      path: docs/reasoning/sarcoidosis_vs_granulomatous_infection_gray_zone_v1.md
      role: infection_safety_gray_zone

    sarcoidosis_vs_HP:
      path: docs/reasoning/sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1.md
      role: airway_exposure_granulomatous_gray_zone

    sarcoidosis_vs_GLILD:
      path: docs/reasoning/sarcoidosis_vs_glild_gray_zone_v1.md
      role: immune_deficiency_gray_zone

    sarcoidosis_vs_occupational_mimic:
      path: docs/reasoning/sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1.md
      role: occupational_granulomatous_mimic_gray_zone

    sarcoidosis_vs_malignancy_or_sarcoid_like_reaction:
      path: docs/reasoning/sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1.md
      role: oncology_sarcoid_like_reaction_gray_zone

    fibrotic_sarcoidosis_vs_chronic_HP:
      path: docs/reasoning/fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1.md
      role: advanced_fibrotic_overlap_gray_zone

    sarcoidosis_vs_GPA_or_granulomatous_vasculitis:
      path: docs/reasoning/sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1.md
      role: vasculitis_red_flag_gray_zone
```

---

## 4. Locked Navigation Core

```yaml
locked_navigation_core:
  granulomatous_crosslink_registry:
    path: docs/navigation/granulomatous_crosslink_registry_v1.md
    role: module_crosslink_and_routing_contract
    status: locked_blueprint

  routing_principle:
    - granulomatous_pages_must_not_behave_as_isolated_articles
    - sarcoidosis_like_patterns_must_route_to_relevant_mimic_review
    - missing_data_and_red_flags_must_remain_visible
```

---

## 5. Locked Evidence Core

```yaml
locked_evidence_core:
  guideline_registry:
    path: docs/evidence/guideline_registry_v1.md
    role: evidence_backbone
    status: updated_for_granulomatous_core

  evidence_domains_registered:
    - sarcoidosis
    - hypersensitivity_pneumonitis
    - GLILD
    - occupational_granulomatous_mimics
    - oncology_sarcoid_like_reaction
    - GPA_ANCA_associated_vasculitis

  evidence_safety_rule:
    - guidelines_must_remain_scope_bound
    - treatment_guidelines_must_not_be_used_as_imaging_only_diagnostic_authority
    - imaging_reviews_support_pattern_awareness_not_final_diagnosis
    - candidate_sources_must_remain_labeled_until_reviewed
    - public_ready_status_requires_full_source_review_and_expert_review
```

---

## 6. Safety Invariants

```yaml
safety_invariants:
  platform_must_not:
    - diagnose_sarcoidosis_from_imaging_alone
    - diagnose_GLILD_from_imaging_alone
    - diagnose_GPA_from_cavitation_or_ANCA_alone
    - diagnose_malignancy_or_sarcoid_like_reaction_from_FDG_uptake_alone
    - treat_granulomas_as_final_diagnosis
    - ignore_infection
    - ignore_HP_clues
    - ignore_occupational_exposure
    - ignore_CVID_or_immune_deficiency_context
    - ignore_malignancy_or_lymphoma_context
    - ignore_vasculitic_red_flags
    - treat_unknown_exposure_as_negative_exposure
    - recommend_treatment
    - replace_MDD_or_clinician_judgment

  platform_must:
    - preserve_uncertainty
    - expose_missing_data
    - show_mimics
    - identify_red_flags
    - link_evidence_scope
    - trigger_MDD_or_specialist_review_when_context_conflicts
    - end_major_reasoning_pages_with_what_do_we_still_not_know
```

---

## 7. Core Mimic Coverage

```yaml
core_mimic_coverage:
  infection:
    status: covered
    module: sarcoidosis_vs_granulomatous_infection_gray_zone_v1

  HP:
    status: covered
    modules:
      - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1
      - fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1

  GLILD:
    status: covered
    modules:
      - sarcoidosis_vs_glild_gray_zone_v1
      - glild_pattern_gold_standard_v1

  occupational_mimics:
    status: covered
    module: sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1

  malignancy_or_sarcoid_like_reaction:
    status: covered
    module: sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1

  GPA_or_granulomatous_vasculitis:
    status: covered
    module: sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
```

---

## 8. Missing Piece Engine Coverage

```yaml
missing_piece_engine_coverage:
  universal:
    - prior_CT
    - tissue_context
    - infection_review
    - microbiology_when_relevant
    - MDD_review

  granulomatous_specific:
    - nodule_distribution_analysis
    - lymph_node_characterization
    - extrapulmonary_review
    - tissue_sampling_target

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

## 9. Lock Statement

```yaml
granulomatous_core_v0_2_lock_statement:
  status: structurally_locked_blueprint
  public_ready: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  source_review_required: true
  expert_review_required: true
  next_phase_allowed: implementation_or_content_expansion_planning_only
```

---

## 10. Final Seal Rule

A valid Granulomatous ILD Core pathway must ask:

```text
Do not force the label.

Ask:
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