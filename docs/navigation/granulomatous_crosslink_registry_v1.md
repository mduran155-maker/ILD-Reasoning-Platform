# Granulomatous ILD Crosslink Registry — v1

## Document Metadata

```yaml
id: navigation_granulomatous_crosslink_registry_v1
title: Granulomatous ILD Crosslink Registry
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: navigation_and_crosslink_contract
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This registry defines how the Granulomatous ILD module links across the platform.

It connects:

- Sarcoidosis Pattern Atlas
- Granulomatous ILD Reasoning Map
- HP reasoning
- infection mimic review
- GLILD / immune deficiency context
- occupational granulomatous mimics
- malignancy / sarcoid-like reaction review

The module must not behave like an isolated sarcoidosis article.

It must remain a reasoning network.

---

## 1. Core Granulomatous Module Pages

```yaml
core_granulomatous_pages:
  sarcoidosis_pattern:
    path: docs/patterns/sarcoidosis_pattern_gold_standard_v1.md
    role: pattern_datasheet

  granulomatous_ild_reasoning_map:
    path: docs/reasoning/granulomatous_ild_reasoning_map_v1.md
    role: central_granulomatous_reasoning_map

  guideline_registry:
    path: docs/evidence/guideline_registry_v1.md
    role: evidence_backbone

  source_review_protocol:
    path: docs/editorial/source_review_protocol_v1.md
    role: evidence_safety_protocol

  editorial_policy:
    path: docs/editorial/editorial_policy_v1.md
    role: language_and_safety_boundary
```

---

## 2. Sarcoidosis Page Sidebar Contract

```yaml
sarcoidosis_sidebar_contract:
  required_sidebar_sections:
    - why_not_sarcoidosis
    - granulomatous_mimics
    - missing_piece_candidates
    - infection_review_prompt
    - occupational_exposure_prompt
    - immune_deficiency_prompt
    - malignancy_or_sarcoid_like_reaction_prompt
    - tissue_or_sampling_prompt
    - evidence_registry

  final_question:
    - What do we still not know?
```

---

## 3. Sarcoidosis Pattern Crosslinks

```yaml
sarcoidosis_pattern_crosslinks:
  primary_reasoning_map:
    - granulomatous_ild_reasoning_map_v1

  major_gray_zones:
    - sarcoidosis_vs_granulomatous_infection
    - sarcoidosis_vs_hypersensitivity_pneumonitis
    - sarcoidosis_vs_glild
    - sarcoidosis_vs_berylliosis_or_pneumoconiosis
    - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction
    - fibrotic_sarcoidosis_vs_chronic_hp

  related_existing_mvp_modules:
    - fibrotic_hp_pattern_gold_standard_v1
    - fibrotic_ild_triage_map_v1
    - guideline_registry_v1

  sidebar_alerts:
    why_not:
      - Why not granulomatous infection?
      - Why not HP?
      - Why not GLILD?
      - Why not berylliosis or pneumoconiosis?
      - Why not malignancy or sarcoid-like reaction?
      - Why not GPA or vasculitis?

    missing_pieces:
      - infection_review
      - microbiology
      - tissue_context
      - exposure_and_occupational_history
      - immune_status
      - cancer_history
      - extrapulmonary_review
      - prior_CT
      - MDD_review

    red_flags:
      - necrotic_lymph_nodes
      - cavitation
      - tree_in_bud
      - random_nodules
      - new_or_progressive_asymmetric_lymphadenopathy
      - new_mass_or_nodule
      - immune_deficiency_context
      - known_malignancy_context
```

---

## 4. Granulomatous Reasoning Map Crosslinks

```yaml
granulomatous_reasoning_map_crosslinks:
  primary_pattern_pages:
    - sarcoidosis_pattern_gold_standard_v1

  future_pattern_pages:
    - granulomatous_infection_pattern_v1
    - glild_pattern_v1
    - berylliosis_pattern_v1
    - gpa_granulomatous_vasculitis_pattern_v1

  existing_related_pages:
    - fibrotic_hp_pattern_gold_standard_v1
    - guideline_registry_v1
    - source_review_protocol_v1

  crosslink_logic:
    sarcoidosis_like_pattern:
      route_to:
        - sarcoidosis_pattern_gold_standard_v1
        - granulomatous_ild_reasoning_map_v1

    granulomatous_pattern_with_air_trapping:
      route_to:
        - granulomatous_ild_reasoning_map_v1
        - fibrotic_hp_pattern_gold_standard_v1

    granulomatous_pattern_with_cavitation:
      route_to:
        - granulomatous_ild_reasoning_map_v1
      red_flag:
        - infection_or_vasculitis_review

    granulomatous_pattern_with_immune_deficiency:
      route_to:
        - granulomatous_ild_reasoning_map_v1
      red_flag:
        - glild_or_opportunistic_infection_review

    granulomatous_pattern_with_known_malignancy:
      route_to:
        - granulomatous_ild_reasoning_map_v1
      red_flag:
        - malignancy_or_sarcoid_like_reaction_review
```

---

## 5. Granulomatous Entry Logic

```yaml
granulomatous_entry_logic:
  if_user_starts_with_bilateral_hilar_lymphadenopathy:
    route_to:
      - sarcoidosis_pattern_gold_standard_v1
      - granulomatous_ild_reasoning_map_v1

  if_user_starts_with_perilymphatic_nodules:
    route_to:
      - sarcoidosis_pattern_gold_standard_v1
      - granulomatous_ild_reasoning_map_v1

  if_user_starts_with_centrilobular_nodules_and_air_trapping:
    route_to:
      - granulomatous_ild_reasoning_map_v1
      - fibrotic_hp_pattern_gold_standard_v1

  if_user_starts_with_cavitary_nodules:
    route_to:
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - infection_GPA_malignancy_review

  if_user_starts_with_granulomas_on_pathology:
    route_to:
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - tissue_context_and_exclusion_review

  if_user_starts_with_sarcoidosis_but_uncertain:
    route_to:
      - sarcoidosis_pattern_gold_standard_v1
      - granulomatous_ild_reasoning_map_v1
```

---

## 6. Missing Piece Priority for Granulomatous ILD

```yaml
granulomatous_missing_piece_priority:
  essential:
    - infection_review
    - nodule_distribution_analysis
    - lymph_node_characterization
    - exposure_and_occupational_history
    - immune_status
    - cancer_history
    - prior_CT

  high_yield:
    - microbiology_when_relevant
    - extrapulmonary_review
    - tissue_or_sampling_context
    - MDD_review

  context_dependent:
    - vasculitis_review
    - immunology_review
    - oncology_review
    - occupational_medicine_review
```

---

## 7. Required Red Flag Panel

```yaml
granulomatous_red_flags:
  necrotic_lymph_nodes:
    concern:
      - infection
      - malignancy
    prompt:
      - Necrotic nodes are not typical simple sarcoidosis reasoning.

  cavitation:
    concern:
      - infection
      - GPA_or_vasculitis
      - malignancy
      - rheumatoid_nodule_context
    prompt:
      - Cavitation should trigger alternative review.

  tree_in_bud:
    concern:
      - infection
      - endobronchial_spread
      - aspiration_or_bronchiolitis_context
    prompt:
      - Tree-in-bud should not be ignored in granulomatous reasoning.

  random_nodules:
    concern:
      - miliary_TB
      - fungal_infection
      - hematogenous_metastases
    prompt:
      - Random nodules are not classic perilymphatic sarcoidosis.

  asymmetric_progressive_lymphadenopathy:
    concern:
      - malignancy
      - lymphoma
      - infection
      - atypical_sarcoid_course
    prompt:
      - Asymmetry and progression require review.

  immune_deficiency_context:
    concern:
      - GLILD
      - opportunistic_infection
    prompt:
      - Do not call simple sarcoidosis when immune deficiency clues exist.
```

---

## 8. Evidence Crosslinks

```yaml
evidence_crosslinks:
  sarcoidosis_pattern_gold_standard_v1:
    primary:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - BTS_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    secondary:
      - ERS_2021_SARCOIDOSIS_TREATMENT
    caution:
      - treatment_guidelines_must_not_be_used_as_diagnostic_authority

  granulomatous_ild_reasoning_map_v1:
    primary:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    secondary:
      - future_granulomatous_infection_sources
      - future_GLILD_sources
      - future_occupational_granulomatous_sources
```

---

## 9. Safety Boundary

```yaml
safety_boundary:
  platform_must_not:
    - diagnose_sarcoidosis_from_imaging_alone
    - ignore_granulomatous_infection
    - ignore_occupational_mimics
    - ignore_HP_clues
    - ignore_GLILD_or_immune_deficiency_context
    - ignore_malignancy_or_sarcoid_like_reaction
    - use_treatment_guideline_as_diagnostic_authority

  platform_must:
    - preserve_uncertainty
    - show_mimics
    - expose_missing_data
    - show_red_flags
    - link_to_evidence_registry
    - trigger_MDD_when_context_is_uncertain
```

---

## 10. Final Crosslink Rule

Every granulomatous ILD page should end with:

```text
Do not force the label.

Ask:
1. Is the pattern truly sarcoidosis-like?
2. Are nodules perilymphatic, centrilobular, or random?
3. Is lymphadenopathy symmetric, necrotic, asymmetric, or progressive?
4. Has infection been considered?
5. Is there HP, occupational, immune deficiency, vasculitic, or malignancy context?
6. Is tissue needed, available, or misleading without context?
7. What do we still not know?
```
---

## 11. Implemented Granulomatous Gray-Zone Modules

```yaml
implemented_granulomatous_gray_zone_modules:
  sarcoidosis_vs_granulomatous_infection:
    path: docs/reasoning/sarcoidosis_vs_granulomatous_infection_gray_zone_v1.md
    role: infection_safety_gray_zone
    status: implemented
    linked_pattern:
      - sarcoidosis_pattern_gold_standard_v1
    core_safety_question:
      - Has granulomatous infection been considered before increasing sarcoidosis confidence?

  sarcoidosis_vs_hypersensitivity_pneumonitis:
    path: docs/reasoning/sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1.md
    role: granulomatous_airway_exposure_gray_zone
    status: implemented
    linked_patterns:
      - sarcoidosis_pattern_gold_standard_v1
      - fibrotic_hp_pattern_gold_standard_v1
    core_safety_question:
      - Are the nodules perilymphatic or centrilobular, and is there air trapping or exposure evidence?

pending_granulomatous_gray_zone_modules:
  - sarcoidosis_vs_GLILD
  - sarcoidosis_vs_berylliosis_or_pneumoconiosis
  - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction
  - fibrotic_sarcoidosis_vs_chronic_HP
  - sarcoidosis_vs_GPA_or_granulomatous_vasculitis
```

---

## 12. Granulomatous Module Next-Step Priority

```yaml
granulomatous_next_step_priority:
  completed:
    - granulomatous_ild_reasoning_map_v1
    - sarcoidosis_pattern_gold_standard_v1
    - sarcoidosis_pattern_taxonomy_v1
    - sarcoidosis_vs_granulomatous_infection_gray_zone_v1
    - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1

  next_recommended:
    module: sarcoidosis_vs_GLILD
    reason:
      - GLILD is a high-value sarcoidosis mimic in immune deficiency context.
      - It protects the platform from calling immune-deficiency granulomatous disease simple sarcoidosis.
      - It expands the granulomatous module beyond infection and HP into immune-system context.

  later:
    - sarcoidosis_vs_berylliosis_or_pneumoconiosis
    - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction
    - fibrotic_sarcoidosis_vs_chronic_HP
```
---

## 13. GLILD Gray-Zone Module Sync

```yaml
implemented_granulomatous_gray_zone_modules_update:
  sarcoidosis_vs_GLILD:
    path: docs/reasoning/sarcoidosis_vs_glild_gray_zone_v1.md
    role: immune_deficiency_granulomatous_gray_zone
    status: implemented
    linked_pattern:
      - sarcoidosis_pattern_gold_standard_v1
    linked_reasoning_map:
      - granulomatous_ild_reasoning_map_v1
    core_safety_question:
      - Is there CVID, primary antibody deficiency, recurrent infection, hypogammaglobulinemia, splenomegaly, cytopenia, or lymphoproliferative context before calling this sarcoidosis?

updated_completed_granulomatous_modules:
  - granulomatous_ild_reasoning_map_v1
  - sarcoidosis_pattern_gold_standard_v1
  - sarcoidosis_pattern_taxonomy_v1
  - sarcoidosis_vs_granulomatous_infection_gray_zone_v1
  - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1
  - sarcoidosis_vs_glild_gray_zone_v1

remaining_high_priority_granulomatous_gray_zones:
  - sarcoidosis_vs_berylliosis_or_pneumoconiosis
  - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction
  - fibrotic_sarcoidosis_vs_chronic_HP
  - sarcoidosis_vs_GPA_or_granulomatous_vasculitis
```

---

## 14. Updated Granulomatous Routing Logic

```yaml
updated_granulomatous_routing_logic:
  if_user_starts_with_sarcoidosis_like_pattern_and_recurrent_infections:
    route_to:
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - immune_deficiency_and_GLILD_review

  if_user_starts_with_sarcoidosis_like_pattern_and_hypogammaglobulinemia:
    route_to:
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - CVID_or_primary_antibody_deficiency_review

  if_user_starts_with_sarcoidosis_like_pattern_and_splenomegaly_or_cytopenias:
    route_to:
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - GLILD_lymphoproliferative_or_lymphoma_review

  if_user_starts_with_granulomas_and_immune_deficiency_context:
    route_to:
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - granulomas_do_not_equal_simple_sarcoidosis
```

---

## 15. Updated Granulomatous Safety Boundary

```yaml
updated_granulomatous_safety_boundary:
  platform_must_not:
    - diagnose_sarcoidosis_without_considering_GLILD_when_immune_deficiency_context_exists
    - ignore_recurrent_sinopulmonary_infections
    - ignore_hypogammaglobulinemia
    - ignore_CVID_or_primary_antibody_deficiency_context
    - ignore_splenomegaly_cytopenias_or_lymphoproliferative_features
    - treat_granulomas_as_sarcoidosis_without_immune_microbiology_and_pathology_context

  platform_must:
    - route_sarcoidosis_like_imaging_with_immune_deficiency_clues_to_GLILD_review
    - keep_infection_and_lymphoma_malignancy_visible_in_CVID_GLILD_context
    - preserve_uncertainty_when_immunoglobulin_status_is_unknown
    - trigger_MDD_when_sarcoidosis_GLILD_infection_or_lymphoma_signals_overlap
```
---

## 16. GLILD Pattern Module Sync

```yaml
implemented_granulomatous_pattern_modules_update:
  GLILD_pattern:
    path: docs/patterns/glild_pattern_gold_standard_v1.md
    role: immune_deficiency_granulomatous_pattern_datasheet
    status: implemented
    linked_reasoning_maps:
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    linked_evidence:
      - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT
      - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
      - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024
    core_safety_question:
      - Is there CVID, primary antibody deficiency, recurrent infection, hypogammaglobulinemia, splenomegaly, cytopenia, or lymphoproliferative context?

updated_completed_granulomatous_modules:
  - granulomatous_ild_reasoning_map_v1
  - sarcoidosis_pattern_gold_standard_v1
  - sarcoidosis_pattern_taxonomy_v1
  - sarcoidosis_vs_granulomatous_infection_gray_zone_v1
  - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1
  - sarcoidosis_vs_glild_gray_zone_v1
  - glild_pattern_gold_standard_v1
```

---

## 17. Updated GLILD Routing Logic

```yaml
updated_GLILD_routing_logic:
  if_user_starts_with_known_CVID_and_lung_abnormality:
    route_to:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - GLILD_infection_and_lymphoma_review

  if_user_starts_with_recurrent_infections_and_sarcoidosis_like_imaging:
    route_to:
      - sarcoidosis_vs_glild_gray_zone_v1
      - glild_pattern_gold_standard_v1
    required_prompt:
      - immunoglobulin_and_primary_antibody_deficiency_review

  if_user_starts_with_hypogammaglobulinemia_and_nodules_GGO_or_consolidation:
    route_to:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
    required_prompt:
      - CVID_GLILD_infection_lymphoma_context_review

  if_user_starts_with_granulomas_and_immune_deficiency_context:
    route_to:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    required_prompt:
      - granulomas_do_not_equal_sarcoidosis_without_immune_context_review
```

---

## 18. Updated GLILD Safety Boundary

```yaml
updated_GLILD_safety_boundary:
  platform_must_not:
    - diagnose_GLILD_from_imaging_alone
    - diagnose_sarcoidosis_without_reviewing_CVID_or_antibody_deficiency_context
    - ignore_recurrent_sinopulmonary_infections
    - ignore_hypogammaglobulinemia
    - ignore_splenomegaly_cytopenias_or_lymphoproliferative_features
    - ignore_infection_or_lymphoma_malignancy_mimics
    - hide_limited_GLILD_evidence_base

  platform_must:
    - route_CVID_or_antibody_deficiency_context_to_GLILD_pattern
    - keep_sarcoidosis_vs_GLILD_gray_zone_visible
    - keep_infection_and_lymphoma_review_visible
    - preserve_uncertainty_when_immunoglobulin_status_is_unknown
    - trigger_MDD_when_GLILD_sarcoidosis_infection_or_lymphoma_signals_overlap
```