# Source Review Records — Core Guidelines v1

## Document Metadata

```yaml
id: evidence_source_review_records_core_guidelines_v1
title: Source Review Records — Core Guidelines
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: evidence_review_records
diagnostic_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This document opens structured source review records for the first core evidence sources of the ILD Reasoning Platform.

It does not complete full-text review.

It creates a controlled evidence workspace for:

- source identity verification,
- source type classification,
- platform claim boundary,
- diagnostic authority boundary,
- treatment authority boundary,
- public-ready restriction,
- and future claim-to-source mapping.

These records must be completed before any public-ready clinical page can be declared.

---

## 1. Review Status Legend

```yaml
review_status_legend:
  source_identity_status:
    official_page_verified: source identity confirmed through official organization or publisher page
    bibliographic_verified: title, authorship, journal, year, or DOI-level identity verified
    unverified: source not yet verified

  full_text_review_status:
    not_started: full text not reviewed
    full_text_review_pending: full text review required before public-ready use
    full_text_reviewed: full text reviewed by project team
    expert_reviewed: reviewed by relevant clinical expert

  claim_mapping_status:
    not_mapped: no claims mapped
    partial_mapping: high-level scope mapped, but exact claim mapping incomplete
    claim_mapped: platform claims mapped to source scope
    expert_validated_mapping: claim mapping reviewed by expert

  public_ready_support:
    none: source cannot support public-ready content yet
    draft_only: can support internal blueprint with caution
    after_full_text_review: may support public candidate after full-text review
    after_expert_review: may support public candidate only after expert review
```

---

## 2. Core Source Record — ATS/ERS/JRS/ALAT 2022 IPF / PPF

```yaml
source_review_record:
  source_id: ATS_ERS_JRS_ALAT_2022_IPF_PPF
  title: Idiopathic Pulmonary Fibrosis (an Update) and Progressive Pulmonary Fibrosis in Adults
  source_type: clinical_practice_guideline
  organizations:
    - American Thoracic Society
    - European Respiratory Society
    - Japanese Respiratory Society
    - Asociación Latinoamericana del Tórax
  year: 2022

  verification_status:
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    expert_review_status: not_started
    public_ready_support: after_full_text_review

  platform_scope:
    can_support:
      - IPF_and_PPF_framework_context
      - progressive_pulmonary_fibrosis_reasoning_context
      - radiologic_progression_context
      - structural_fibrotic_progression_language
      - UIP_related_context_after_claim_mapping

    cannot_support:
      - automated_IPF_diagnosis
      - imaging_only_patient_classification
      - treatment_recommendation_by_platform
      - public_ready_page_without_full_text_review
      - replacing_MDD_or_clinician_judgment

  used_by_modules:
    - docs/patterns/uip_pattern_gold_standard_v1.md
    - docs/reasoning/fibrotic_ild_triage_map_v1.md
    - docs/reasoning/superimposed_events_core_blueprint_v1.md
    - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    - docs/reasoning/temporal_comparison_methodology_v1.md

  claim_boundary:
    allowed_draft_claims:
      - Radiologic progression reasoning should emphasize structural fibrotic change rather than ground-glass opacity alone.
      - Progressive fibrotic disease reasoning requires longitudinal context.
      - New ground-glass opacity on fibrotic background requires superimposed event review before progression labeling.

    prohibited_until_reviewed:
      - exact_guideline_wording
      - exact_recommendation_strength
      - exact_treatment_guidance
      - public_ready_UIP_claims
      - public_ready_PPF_claims

  diagnostic_boundary:
    - guideline_supports_reasoning_framework_not_automated_diagnosis
    - imaging_findings_must_remain_contextual
    - MDD_or_clinical_judgment_not_replaced

  treatment_boundary:
    - treatment_recommendations_are_not_active_platform_content
    - treatment_claims_require_separate_review_and_expert_validation

  next_actions:
    - full_text_review
    - extract_progression_relevant_sections
    - map_UIP_pattern_claims
    - map_temporal_comparison_claims
    - define_public_ready_allowed_phrases
```

---

## 3. Core Source Record — ATS/JRS/ALAT 2020 HP Diagnosis

```yaml
source_review_record:
  source_id: ATS_JRS_ALAT_2020_HP_DIAGNOSIS
  title: Diagnosis of Hypersensitivity Pneumonitis in Adults
  source_type: clinical_practice_guideline
  organizations:
    - American Thoracic Society
    - Japanese Respiratory Society
    - Asociación Latinoamericana del Tórax
  year: 2020

  verification_status:
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    expert_review_status: not_started
    public_ready_support: after_full_text_review

  platform_scope:
    can_support:
      - HP_diagnostic_framework_context
      - fibrotic_HP_HRCT_reasoning_context
      - exposure_history_reasoning_context
      - BAL_pathology_MDD_integration_context
      - HP_vs_sarcoidosis_or_HP_vs_UIP_gray_zone_context

    cannot_support:
      - HP_diagnosis_from_imaging_alone
      - HP_diagnosis_from_exposure_history_alone
      - treatment_recommendation_by_platform
      - automatic_confidence_score_without_review
      - public_ready_HP_page_without_full_text_review

  used_by_modules:
    - docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
    - docs/reasoning/fibrotic_ild_triage_map_v1.md
    - docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1.md
    - docs/reasoning/fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1.md
    - docs/reasoning/temporal_comparison_methodology_v1.md

  claim_boundary:
    allowed_draft_claims:
      - HP reasoning requires integration of exposure, HRCT pattern, BAL/pathology when relevant, and MDD context.
      - Air trapping, mosaic attenuation, centrilobular nodules, and three-density pattern are high-yield HP reasoning features when interpreted in context.
      - Exposure history is important but should not be treated as standalone diagnosis.

    prohibited_until_reviewed:
      - exact_guideline_algorithm_language
      - exact_confidence_category_definitions
      - exact_recommendation_strengths
      - public_ready_HP_diagnostic_rules
      - treatment_or_management_claims

  diagnostic_boundary:
    - guideline_supports_multidomain_reasoning
    - imaging_only_HP_classification_not_allowed
    - exposure_history_not_standalone_authority
    - MDD_context_must_remain_visible

  treatment_boundary:
    - treatment_response_or_antigen_avoidance_guidance_not_active_until_separate_review

  next_actions:
    - full_text_review
    - map_fibrotic_HP_pattern_claims
    - map_exposure_reasoning_claims
    - map_gray_zone_HP_vs_UIP_and_HP_vs_sarcoidosis_claims
    - define_public_ready_allowed_phrases
```

---

## 4. Core Source Record — ATS 2020 Sarcoidosis Diagnosis / Detection

```yaml
source_review_record:
  source_id: ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
  title: Diagnosis and Detection of Sarcoidosis
  source_type: clinical_practice_guideline
  organization:
    - American Thoracic Society
  year: 2020

  verification_status:
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    expert_review_status: not_started
    public_ready_support: after_full_text_review

  platform_scope:
    can_support:
      - sarcoidosis_diagnostic_framework_context
      - compatible_clinical_context_reasoning
      - granulomatous_inflammation_context
      - alternative_cause_exclusion_context
      - sarcoidosis_mimic_visibility_principle

    cannot_support:
      - sarcoidosis_from_imaging_alone
      - sarcoidosis_from_granulomas_alone
      - sarcoidosis_without_mimic_review
      - automated_patient_classification
      - public_ready_sarcoidosis_page_without_full_text_review

  used_by_modules:
    - docs/patterns/sarcoidosis_pattern_gold_standard_v1.md
    - docs/patterns/sarcoidosis_pattern_taxonomy_v1.md
    - docs/reasoning/granulomatous_ild_reasoning_map_v1.md
    - docs/reasoning/sarcoidosis_vs_granulomatous_infection_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_glild_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1.md
    - docs/reasoning/sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1.md

  claim_boundary:
    allowed_draft_claims:
      - Sarcoidosis reasoning requires compatible clinical context and review of alternative granulomatous causes.
      - Imaging can support sarcoidosis-like reasoning but cannot establish sarcoidosis alone.
      - Infection, malignancy, occupational disease, GLILD, HP, and vasculitis must remain visible when relevant.

    prohibited_until_reviewed:
      - exact_guideline_wording
      - exact_recommendation_strengths
      - public_ready_sarcoidosis_diagnostic_claims
      - extrapulmonary_screening_claims
      - treatment_claims

  diagnostic_boundary:
    - source_supports_diagnostic_framework_not_final_platform_diagnosis
    - alternative_causes_must_remain_visible
    - tissue_context_must_not_override_clinical_mimic_context

  treatment_boundary:
    - treatment_of_sarcoidosis_not_active_platform_content
    - management_claims_require_separate_source_review

  next_actions:
    - full_text_review
    - map_sarcoidosis_pattern_claims
    - map_granulomatous_gray_zone_claims
    - map_mimic_exclusion_language
    - define_public_ready_allowed_phrases
```

---

## 5. Core Source Record — Fleischner 2021 Drug-related Pneumonitis

```yaml
source_review_record:
  source_id: Fleischner_2021_DRUG_RELATED_PNEUMONITIS_POSITION_PAPER
  title: Chest CT Diagnosis and Clinical Management of Drug-related Pneumonitis in Patients Receiving Molecular Targeting Agents and Immune Checkpoint Inhibitors
  source_type: position_paper
  organization:
    - Fleischner Society
  year: 2021

  verification_status:
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    expert_review_status: not_started
    public_ready_support: after_full_text_review

  platform_scope:
    can_support:
      - drug_related_pneumonitis_CT_pattern_context
      - immune_checkpoint_inhibitor_pneumonitis_pattern_awareness
      - molecular_targeting_agent_pneumonitis_context
      - OP_NSIP_HP_DAD_like_pattern_awareness
      - treatment_related_lung_injury_mimic_awareness

    cannot_support:
      - drug_toxicity_from_timing_alone
      - infection_exclusion
      - malignancy_progression_exclusion
      - treatment_recommendation_by_platform
      - public_ready_drug_toxicity_page_without_full_text_review

  used_by_modules:
    - docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
    - docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    - docs/reasoning/superimposed_events_core_blueprint_v1.md

  claim_boundary:
    allowed_draft_claims:
      - Drug-related pneumonitis may show multiple CT pattern families.
      - Treatment-related lung injury requires medication and treatment timeline review.
      - Infection and malignancy progression must remain visible in treated patients.

    prohibited_until_reviewed:
      - exact_position_paper_criteria
      - exact_management_recommendations
      - grading_or_severity_guidance
      - treatment_action_language
      - public_ready_drug_toxicity_claims

  diagnostic_boundary:
    - position_paper_supports_pattern_awareness_and_contextual_reasoning
    - CT_pattern_and_timing_do_not_prove_drug_toxicity
    - infection_and_malignancy_must_remain_visible

  treatment_boundary:
    - management_recommendations_not_activated_in_platform
    - platform_must_not_recommend_drug_discontinuation_steroids_or_therapy_change

  next_actions:
    - full_text_review
    - map_CT_pattern_claims
    - map_immune_checkpoint_inhibitor_claims
    - map_infection_and_progression_mimic_boundaries
    - define_public_ready_allowed_phrases
```

---

## 6. Cross-source Boundary Rules

```yaml
cross_source_boundary_rules:
  diagnostic_guidelines:
    allowed_role:
      - reasoning_framework
      - scope_bound_diagnostic_context
      - missing_data_identification
    disallowed_role:
      - automated_patient_diagnosis
      - imaging_only_authority
      - treatment_recommendation_without_separate_review

  clinical_statements:
    allowed_role:
      - clinical_context
      - practice_point_context_after_review
      - mimic_awareness
    disallowed_role:
      - final_diagnostic_authority
      - public_ready_claim_without_full_text_review

  position_papers:
    allowed_role:
      - pattern_awareness
      - multidisciplinary_context
      - terminology_support_after_review
    disallowed_role:
      - automatic_management_action
      - treatment_instruction_by_platform

  imaging_reviews:
    allowed_role:
      - pattern_awareness
      - mimic_visibility
      - differential_reasoning_support
    disallowed_role:
      - final_diagnostic_label
      - exclusion_of_mimics_without_context
```

---

## 7. v0.4 Core Guideline Review Completion Criteria

```yaml
v0_4_core_guideline_review_completion_criteria:
  each_core_source_must_have:
    - verified_source_identity
    - source_type
    - platform_scope
    - can_support_claims
    - cannot_support_claims
    - used_by_modules
    - diagnostic_boundary
    - treatment_boundary
    - next_actions

  before_public_ready_candidate:
    - full_text_review_status_must_be_full_text_reviewed_or_expert_reviewed
    - claim_mapping_status_must_be_claim_mapped_or_expert_validated_mapping
    - public_ready_allowed_phrases_must_be_defined
    - prohibited_claims_must_remain_visible
    - module_claims_must_link_to_specific_source_records
    - expert_review_required_must_remain_true
```

---

## 8. Current v0.4 Status

```yaml
current_v0_4_status:
  evidence_layer: active_development
  source_review_matrix: implemented
  core_guideline_review_records: implemented
  full_text_review_completed: false
  expert_review_completed: false
  public_ready_page_allowed: false

  next_recommended_step:
    module: claim_to_source_mapping_template_pack_v1
    path: docs/evidence/claim_to_source_mapping_template_pack_v1.md
    purpose:
      - define_claim_ids
      - define_mapping_schema
      - prepare_first_page_claim_mapping
      - prevent_source_presence_from_becoming_false_authority
```

---

## 9. Final Source Review Rule

```text
A source review record does not make a page public-ready.

It only defines what the source may be allowed to support after full-text review and expert validation.
```