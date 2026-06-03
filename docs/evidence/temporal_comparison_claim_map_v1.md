# Temporal Comparison Claim Map — v1

## Document Metadata

```yaml
id: evidence_temporal_comparison_claim_map_v1
title: Temporal Comparison Claim Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: claim_to_source_mapping
diagnostic_authority: none
module_version: v0.4
mapped_page:
  - docs/reasoning/temporal_comparison_methodology_v1.md
last_updated: draft
```

---

## 0. Purpose

This claim map connects major claims in the Temporal Comparison Methodology page to evidence sources, review status, scope, and safety boundaries.

This document does not make the page public-ready.

It creates the first controlled claim-to-source mapping candidate for future full-text review and expert validation.

---

## 1. Mapping Status

```yaml
mapping_status:
  mapped_page: temporal_comparison_methodology_v1
  mapping_stage: draft_claim_mapping
  source_review_status: full_text_review_pending
  expert_review_status: not_started
  public_ready_allowed: false

  current_allowed_use:
    - internal_blueprint
    - evidence_governance_development
    - future_expert_review_preparation

  current_disallowed_use:
    - public_ready_page
    - clinical_decision_tool
    - diagnostic_authority
    - treatment_guidance
```

---

## 2. Claim Map — Prior CT Requirement

```yaml
claim_mapping_TEMP_PRIOR_CT_001:
  claim_id: TEMP_PRIOR_CT_001
  claim_text: >
    Temporal reasoning requires prior CT or longitudinal imaging context before progression, stability, regression, or new disease behavior can be confidently interpreted.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Core Safety Principle

  source_support:
    primary_source_id: ATS_ERS_JRS_ALAT_2022_IPF_PPF
    source_type: clinical_practice_guideline
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - diagnostic_framework
      - temporal_reasoning
      - fibrotic_progression_context
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  source_can_support:
    - longitudinal_context_for_progression_reasoning
    - radiologic_progression_framework_after_review

  source_cannot_support:
    - automated_progression_diagnosis
    - public_ready_claim_without_full_text_review
    - treatment_recommendation
    - replacement_of_MDD_or_clinical_judgment

  diagnostic_boundary:
    - prior_CT_requirement_supports_reasoning_not_final_classification

  treatment_boundary:
    - no_treatment_guidance_allowed

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
```

---

## 3. Claim Map — Structural Fibrosis vs Reversible Opacity

```yaml
claim_mapping_TEMP_STRUCTURAL_VS_AIRSPACE_001:
  claim_id: TEMP_STRUCTURAL_VS_AIRSPACE_001
  claim_text: >
    Temporal comparison should separate structural fibrotic progression from potentially reversible airspace opacity.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Fibrotic Progression vs Reversible Opacity

  source_support:
    primary_source_id: ATS_ERS_JRS_ALAT_2022_IPF_PPF
    source_type: clinical_practice_guideline
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - diagnostic_framework
      - temporal_reasoning
      - radiologic_progression_context
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  source_can_support:
    - structural_fibrotic_progression_context
    - radiologic_progression_reasoning_context

  source_cannot_support:
    - declaring_progression_from_GGO_alone
    - automated_progression_label
    - treatment_action
    - public_ready_claim_without_review

  diagnostic_boundary:
    - supports_framework_for_separating_fibrotic_change_from_reversible_opacity

  treatment_boundary:
    - treatment_claims_not_active

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
```

---

## 4. Claim Map — New GGO Requires Superimposed Event Review

```yaml
claim_mapping_TEMP_NEW_GGO_001:
  claim_id: TEMP_NEW_GGO_001
  claim_text: >
    New ground-glass opacity on an ILD background should not automatically be labeled fibrotic progression without superimposed event review.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Routing by Temporal Pattern

  source_support:
    primary_source_id: ATS_ERS_JRS_ALAT_2022_IPF_PPF
    secondary_source_ids:
      - AE_IPF_REVISED_DEFINITION_AND_REVIEW_SOURCE_CANDIDATE
      - superimposed_events_core_blueprint_v1
    source_type: clinical_practice_guideline_plus_internal_blueprint_context
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: mixed_verified_and_candidate
    full_text_review_status: full_text_review_pending
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - temporal_reasoning
      - mimic_awareness
      - diagnostic_framework
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  source_can_support:
    - new_alveolar_abnormality_requires_context
    - progression_reasoning_requires_longitudinal_structural_context

  source_cannot_support:
    - acute_exacerbation_diagnosis_from_GGO
    - infection_exclusion
    - edema_exclusion
    - drug_toxicity_exclusion
    - public_ready_claim_until_AE_source_verified

  diagnostic_boundary:
    - new_GGO_is_a_reasoning_trigger_not_a_final_diagnosis

  treatment_boundary:
    - no_treatment_recommendation_allowed

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes:
      - AE source candidate must be replaced or verified before public use.
```

---

## 5. Claim Map — Technical Comparability

```yaml
claim_mapping_TEMP_TECHNICAL_COMPARABILITY_001:
  claim_id: TEMP_TECHNICAL_COMPARABILITY_001
  claim_text: >
    CT technical comparability should be reviewed before declaring subtle progression, regression, stability, or new abnormality.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Technical Comparability Checklist

  source_support:
    primary_source_id: HRCT_TECHNICAL_COMPARABILITY_REVIEW_SOURCE_CANDIDATE
    secondary_source_id: Fleischner_ILA_Position_Paper_2020
    source_type: candidate_review_plus_position_paper_context
    source_review_record_path: docs/evidence/source_review_matrix_v1.md
    source_identity_status: candidate_or_bibliographic_verified
    full_text_review_status: not_started
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - temporal_reasoning
      - imaging_pattern_awareness
      - evidence_limitation
    claim_strength: low_or_candidate
    public_ready_allowed: false

  source_can_support:
    - draft_awareness_that_technique_can_affect_apparent_change

  source_cannot_support:
    - public_ready_technical_comparability_rules
    - exact_protocol_recommendations
    - diagnostic_or_management_decisions

  diagnostic_boundary:
    - technical_comparability_is_a_caution_layer_not_diagnostic_authority

  treatment_boundary:
    - no_treatment_guidance_allowed

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes:
      - Need stronger HRCT technical comparison source before public-ready use.
```

---

## 6. Claim Map — Improvement Does Not Equal Fibrosis Reversal

```yaml
claim_mapping_TEMP_IMPROVEMENT_001:
  claim_id: TEMP_IMPROVEMENT_001
  claim_text: >
    Improvement of ground-glass opacity or consolidation should not be equated with reversal of established fibrosis without structural evidence.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Change Categories / Reporting Language Templates

  source_support:
    primary_source_id: ATS_ERS_JRS_ALAT_2022_IPF_PPF
    secondary_source_ids:
      - superimposed_events_core_blueprint_v1
      - organizing_pneumonia_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    source_type: clinical_practice_guideline_plus_internal_reasoning_context
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: official_page_verified_plus_internal_blueprint
    full_text_review_status: full_text_review_pending
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - temporal_reasoning
      - fibrotic_progression_context
      - mimic_awareness
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  source_can_support:
    - fibrosis_progression_should_focus_on_structural_features
    - reversible_opacity_should_be_interpreted_separately

  source_cannot_support:
    - declaring_fibrosis_reversal
    - treatment_response_claim
    - public_ready_response_assessment
    - treatment_recommendation

  diagnostic_boundary:
    - improvement_of_opacity_is_not_automated_disease_reversal

  treatment_boundary:
    - treatment_response_module_not_active
    - no_therapy_recommendation_allowed

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
```

---

## 7. Claim Map — Persistent Focal Opacity Requires Reassessment

```yaml
claim_mapping_TEMP_PERSISTENT_FOCAL_001:
  claim_id: TEMP_PERSISTENT_FOCAL_001
  claim_text: >
    Persistent focal opacity on an ILD background should trigger reassessment for malignancy, chronic infection, organizing pneumonia, infarct, atelectasis, or treatment-related change.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Routing by Temporal Pattern

  source_support:
    primary_source_id: Fleischner_2017_Pulmonary_Nodule_Guidelines_Context
    secondary_source_ids:
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    source_type: nodule_guideline_context_plus_internal_superimposed_event_reasoning
    source_review_record_path: docs/evidence/source_review_matrix_v1.md
    source_identity_status: bibliographic_verified_plus_internal_blueprint
    full_text_review_status: full_text_review_pending
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - mimic_awareness
      - temporal_reasoning
      - imaging_pattern_awareness
    claim_strength: low_to_moderate_for_scope
    public_ready_allowed: false

  source_can_support:
    - focal_lesion_followup_context_after_review
    - malignancy_visibility_context
    - temporal_persistence_as_reasoning_trigger

  source_cannot_support:
    - automatic_nodule_management
    - automatic_malignancy_diagnosis
    - public_ready_followup_recommendation
    - treatment_recommendation

  diagnostic_boundary:
    - persistent_focal_opacity_is_a_red_flag_not_a_final_label

  treatment_boundary:
    - followup_or_sampling_decisions_not_recommended_by_platform

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
```

---

## 8. Claim Map — Baseline ILD Must Not Swallow New Disease

```yaml
claim_mapping_TEMP_BASELINE_CAPTURE_001:
  claim_id: TEMP_BASELINE_CAPTURE_001
  claim_text: >
    A known baseline ILD diagnosis should not be allowed to explain every new opacity, nodule, mass, cavitation, or acute clinical decline without temporal and mimic review.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Temporal Pitfall Library

  source_support:
    primary_source_id: superimposed_events_core_blueprint_v1
    secondary_source_ids:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    source_type: internal_reasoning_principle_plus_guideline_context
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: internal_blueprint_plus_official_page_verified_sources
    full_text_review_status: mixed_internal_and_pending
    claim_mapping_status: draft_mapping

  mapping_scope:
    source_scope:
      - mimic_awareness
      - diagnostic_framework
      - temporal_reasoning
      - evidence_limitation
    claim_strength: moderate_for_blueprint
    public_ready_allowed: false

  source_can_support:
    - baseline_pattern_requires_context
    - mimic_review_principle
    - temporal_reasoning_principle

  source_cannot_support:
    - final_diagnosis
    - automated_classification
    - public_ready_claim_without_full_text_and_expert_review

  diagnostic_boundary:
    - platform_teaches_reasoning_sequence_not_diagnosis

  treatment_boundary:
    - no_treatment_guidance_allowed

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes:
      - This is a platform philosophy claim requiring expert validation before public-facing use.
```

---

## 9. Page-level Public-ready Status

```yaml
temporal_comparison_page_public_ready_status:
  page: docs/reasoning/temporal_comparison_methodology_v1.md
  public_ready: false
  public_candidate: false
  reason:
    - full_text_review_pending
    - claim_mapping_draft_only
    - technical_comparability_source_candidate_needed
    - expert_review_not_started

  strongest_current_claims:
    - TEMP_PRIOR_CT_001
    - TEMP_STRUCTURAL_VS_AIRSPACE_001
    - TEMP_IMPROVEMENT_001

  weakest_current_claims:
    - TEMP_TECHNICAL_COMPARABILITY_001
    - TEMP_PERSISTENT_FOCAL_001

  next_required_actions:
    - full_text_review_ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - identify_and_verify_HRCT_technical_comparability_source
    - full_text_review_Fleischner_2017_nodule_guideline_context
    - expert_review_temporal_reasoning_claims
    - define_public_allowed_phrases
```

---

## 10. Public Candidate Gate Result

```yaml
public_candidate_gate_result:
  evaluated_page: temporal_comparison_methodology_v1
  gate_status: blocked
  blocker_reasons:
    - full_text_review_not_completed
    - expert_review_not_completed
    - candidate_sources_present
    - public_allowed_phrases_not_defined
    - claim_strength_not_finalized

  allowed_next_status:
    - evidence_mapped_blueprint
    - not_public_ready
```

---

## 11. Final Claim Map Rule

```text
Temporal comparison is a strong first public-page candidate, but it is not public-ready yet.

Its value is clear.
Its evidence boundaries are now visible.
That is the point of v0.4.
```