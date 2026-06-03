# Evidence Layer Lock Checklist — v1

## Document Metadata

```yaml
id: data_schema_evidence_layer_lock_checklist_v1
title: Evidence Layer Lock Checklist
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: validation_checklist
diagnostic_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This checklist defines the structural lock criteria for the Evidence Layer v0.4.

It verifies that the platform now separates:

- source presence,
- source identity,
- source scope,
- full-text review status,
- claim-to-source mapping,
- public-ready language safety,
- candidate source gaps,
- diagnostic boundaries,
- treatment boundaries,
- and expert review requirements.

This lock does not mean public clinical readiness.

It means the evidence governance architecture is internally coherent and ready for future full-text review, expert review, and public-candidate preparation.

---

## 1. Required Evidence Governance Files

```yaml
required_evidence_governance_files:
  source_matrix:
    - docs/evidence/source_review_matrix_v1.md

  source_records:
    - docs/evidence/source_review_records_core_guidelines_v1.md

  claim_mapping:
    - docs/evidence/claim_to_source_mapping_template_pack_v1.md
    - docs/evidence/temporal_comparison_claim_map_v1.md

  public_language_safety:
    - docs/evidence/temporal_comparison_public_allowed_phrases_v1.md

  gap_registry:
    - docs/evidence/candidate_source_gap_list_v1.md

  evidence_registry:
    - docs/evidence/evidence_governance_registry_v1.md

  supporting_policy:
    - docs/editorial/editorial_policy_v1.md
    - docs/editorial/source_review_protocol_v1.md
```

---

## 2. Evidence Layer Coverage Requirements

```yaml
evidence_layer_coverage_requirements:
  source_identity_tracking:
    required:
      - source_id
      - source_title
      - source_type
      - organization_or_journal
      - publication_year
      - source_identity_status

  source_review_tracking:
    required:
      - full_text_review_status
      - claim_mapping_status
      - expert_review_status
      - public_ready_support_status

  boundary_tracking:
    required:
      - can_support_claims
      - cannot_support_claims
      - diagnostic_boundary
      - treatment_boundary
      - public_ready_boundary

  module_usage_tracking:
    required:
      - used_by_modules
      - affected_claims
      - next_actions
```

---

## 3. Required Source Status Vocabulary

```yaml
required_source_status_vocabulary:
  source_identity_status:
    - unverified
    - bibliographic_verified
    - official_page_verified
    - duplicate_or_deprecated

  full_text_review_status:
    - not_started
    - abstract_only
    - full_text_available_not_reviewed
    - full_text_review_pending
    - full_text_reviewed
    - expert_reviewed

  claim_mapping_status:
    - not_mapped
    - partial_mapping
    - draft_mapping
    - claim_mapped
    - expert_validated_mapping

  public_ready_support:
    - none
    - draft_only
    - limited_educational_context
    - candidate_support
    - after_full_text_review
    - after_expert_review
    - public_ready_support_after_review
```

---

## 4. Evidence Safety Boundary Checks

```yaml
evidence_safety_boundary_checks:
  platform_must_not:
    - treat_source_presence_as_evidence_review
    - treat_bibliographic_verification_as_full_text_review
    - treat_claim_mapping_as_expert_validation
    - use_treatment_guidelines_as_imaging_only_diagnostic_authority
    - use_imaging_reviews_as_final_diagnostic_authority
    - allow_candidate_sources_to_support_public_ready_claims
    - cite_guidelines_as_general_page_authority_without_claim_scope
    - remove_uncertainty_language_before_full_text_and_expert_review
    - recommend_treatment
    - declare_any_page_public_ready_during_v0_4_lock

  platform_must:
    - label_each_source_by_type_and_scope
    - keep_review_status_visible
    - map_claims_to_specific_sources
    - define_what_each_source_cannot_support
    - preserve_diagnostic_authority_none
    - preserve_treatment_authority_none
    - require_full_text_review
    - require_expert_review
    - keep_candidate_source_gaps_visible
```

---

## 5. Required Claim Mapping Structure

```yaml
required_claim_mapping_structure:
  each_claim_mapping_must_include:
    - claim_id
    - claim_text
    - module_path
    - page_section
    - source_id
    - source_type
    - source_review_record_path
    - source_identity_status
    - full_text_review_status
    - claim_mapping_status
    - source_scope
    - claim_strength
    - public_ready_allowed
    - source_can_support
    - source_cannot_support
    - diagnostic_boundary
    - treatment_boundary
    - review_requirements

  public_ready_allowed_default:
    value: false
    reason:
      - full_text_review_pending_by_default
      - expert_review_required
      - overclaim_prevention
```

---

## 6. Required Public Language Safety Structure

```yaml
required_public_language_safety_structure:
  each_public_phrase_file_must_include:
    - current_public_status
    - allowed_safe_phrases
    - conditional_phrases
    - blocked_phrases
    - required_uncertainty_phrases
    - forbidden_public_language
    - page_level_language_gate
    - final_public_language_rule

  public_language_must_not:
    - diagnose
    - classify_patient
    - recommend_treatment
    - recommend_follow_up_interval
    - replace_MDD
    - claim_certainty_without_review

  public_language_must:
    - teach_reasoning
    - preserve_uncertainty
    - identify_missing_data
    - separate_observation_from_interpretation
    - show_when_context_is_missing
```

---

## 7. Required Candidate Source Gap Tracking

```yaml
required_candidate_source_gap_tracking:
  each_gap_must_include:
    - source_gap_id
    - current_status
    - needed_for
    - needed_claims
    - current_blocker
    - required_action
    - public_ready_impact

  highest_priority_gaps_must_remain_visible:
    - HRCT_technical_comparability_source
    - AE_IPF_or_AE_fibrotic_ILD_source
    - vascular_edema_DAH_PE_source_group
    - occupational_lung_disease_review_source
    - sarcoid_like_reaction_malignancy_review_source

  candidate_source_rule:
    - candidate_sources_are_allowed_for_internal_research_direction_only
    - candidate_sources_must_not_support_public_ready_claims
```

---

## 8. First Public Candidate Gate Checks

```yaml
first_public_candidate_gate_checks:
  candidate_page:
    - docs/reasoning/temporal_comparison_methodology_v1.md

  current_gate_status:
    public_ready: false
    public_candidate: false
    gate_status: blocked

  required_before_public_candidate:
    - full_text_review_ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - verified_HRCT_technical_comparability_source
    - verified_AE_source_if_AE_claims_remain
    - verified_Fleischner_2017_nodule_context_if_focal_opacity_claims_remain
    - expert_review_temporal_comparison_claim_map
    - public_allowed_phrases_expert_validated
    - candidate_sources_removed_or_replaced_for_public_claims
    - public_ready_allowed_true_only_for_reviewed_claims
```

---

## 9. Evidence Layer Lock Criteria

```yaml
v0_4_evidence_layer_lock_criteria:
  source_governance:
    - source_review_matrix_v1_exists
    - source_review_records_core_guidelines_v1_exists
    - every_core_source_has_scope_and_boundary
    - every_core_source_public_ready_false_until_review

  claim_governance:
    - claim_to_source_mapping_template_pack_v1_exists
    - temporal_comparison_claim_map_v1_exists
    - claim_ids_defined
    - source_scope_defined_per_claim
    - public_ready_allowed_false_by_default

  language_governance:
    - temporal_comparison_public_allowed_phrases_v1_exists
    - allowed_conditional_blocked_language_defined
    - forbidden_public_language_defined
    - treatment_and_diagnostic_overclaim_blocked

  gap_governance:
    - candidate_source_gap_list_v1_exists
    - high_priority_source_gaps_visible
    - public_ready_blockers_explicit
    - candidate_sources_not_laundered_into_authority

  registry_governance:
    - evidence_governance_registry_v1_exists
    - evidence_workflow_defined
    - current_blockers_visible
    - first_public_candidate_strategy_declared

  safety_core:
    - diagnostic_authority_none
    - treatment_authority_none
    - public_ready_false
    - expert_review_required_true
    - full_text_review_required_true
```

---

## 10. Current v0.4 Lock Result

```yaml
current_v0_4_lock_result:
  evidence_layer_status: structurally_locked_blueprint_candidate
  public_ready: false
  public_candidate_allowed: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  full_text_review_completed: false
  expert_review_completed: false

  lock_meaning:
    - evidence_governance_architecture_is_coherent
    - source_review_workflow_is_defined
    - claim_mapping_workflow_is_defined
    - public_language_safety_is_drafted
    - source_gaps_are_visible
    - public_ready_blockers_are_explicit

  lock_does_not_mean:
    - sources_are_fully_reviewed
    - claims_are_expert_validated
    - pages_are_public_ready
    - clinical_use_is_authorized
    - treatment_or_diagnosis_guidance_is_enabled
```

---

## 11. Next Allowed Steps After v0.4 Lock

```yaml
next_allowed_steps_after_v0_4_lock:
  evidence_deepening:
    - full_text_review_records_for_core_sources
    - claim_mapping_expansion_for_UIP_HP_sarcoidosis_superimposed_events
    - expert_review_workflow_design

  content_quality:
    - test_case_coverage_expansion
    - UIP_parity_upgrade
    - public_candidate_page_preparation

  implementation_planning:
    - markdown_to_JSON_schema_planning
    - Next_js_content_model_planning
    - UI_navigation_prototype_planning

  not_allowed_yet:
    - public_clinical_release
    - clinical_decision_support_claim
    - treatment_recommendation_module
    - patient_specific_diagnosis_tool
```

---

## 12. Final Lock Rule

```text
The Evidence Layer is locked only when uncertainty is visible.

A claim is not safe because it has a citation.

A claim becomes safer when its source, scope, boundary, review status, and public permission are explicit.
```