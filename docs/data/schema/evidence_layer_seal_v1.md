# Evidence Layer Seal — v1

## Document Metadata

```yaml
id: data_schema_evidence_layer_seal_v1
title: Evidence Layer Seal
version: v1
language: English
status: blueprint_seal
project: ILD Reasoning Platform
content_type: module_seal
diagnostic_authority: none
treatment_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This document seals the Evidence Layer v0.4 blueprint.

The seal confirms that the platform now has a structurally coherent evidence governance architecture across:

- source review matrix,
- source review records,
- claim-to-source mapping templates,
- first page-level claim map,
- public language safety draft,
- candidate source gap tracking,
- evidence governance registry,
- source scope boundaries,
- diagnostic boundaries,
- treatment boundaries,
- and public-ready blockers.

This seal does not mean public clinical readiness.

It means the v0.4 Evidence Layer blueprint is structurally locked for future full-text review, expert review, claim expansion, and public-candidate preparation.

---

## 1. Seal Scope

```yaml
seal_scope:
  module: Evidence Layer
  version: v0.4
  seal_type: structural_blueprint_lock
  public_ready: false
  public_candidate_allowed: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  expert_review_required: true
  full_source_review_required: true
```

---

## 2. Locked Evidence Governance Files

```yaml
locked_evidence_governance_files:
  source_review_matrix:
    path: docs/evidence/source_review_matrix_v1.md
    role: global_source_status_scope_and_boundary_matrix
    status: locked_blueprint

  core_guideline_source_review_records:
    path: docs/evidence/source_review_records_core_guidelines_v1.md
    role: structured_review_records_for_core_sources
    status: locked_blueprint

  claim_to_source_mapping_template_pack:
    path: docs/evidence/claim_to_source_mapping_template_pack_v1.md
    role: claim_mapping_schema_and_public_ready_gate_template
    status: locked_blueprint

  temporal_comparison_claim_map:
    path: docs/evidence/temporal_comparison_claim_map_v1.md
    role: first_page_level_claim_to_source_mapping_candidate
    status: locked_blueprint

  temporal_comparison_public_allowed_phrases:
    path: docs/evidence/temporal_comparison_public_allowed_phrases_v1.md
    role: public_language_safety_draft_for_first_candidate_page
    status: locked_blueprint

  candidate_source_gap_list:
    path: docs/evidence/candidate_source_gap_list_v1.md
    role: weak_unverified_candidate_source_gap_registry
    status: locked_blueprint

  evidence_governance_registry:
    path: docs/evidence/evidence_governance_registry_v1.md
    role: evidence_layer_crosslink_and_workflow_registry
    status: locked_blueprint

  evidence_layer_lock_checklist:
    path: docs/data/schema/evidence_layer_lock_checklist_v1.md
    role: structural_lock_validation_checklist
    status: locked_blueprint
```

---

## 3. Locked Evidence Principles

```yaml
locked_evidence_principles:
  core_rule:
    - A source does not support a page.
    - A source supports a specific claim inside a specific scope and boundary.
    - Source presence is not source review.
    - Citation is not authority.
    - Claim mapping is not expert validation.
    - Public language must teach reasoning, not diagnose.

  platform_must_not:
    - treat_source_presence_as_evidence_review
    - treat_bibliographic_verification_as_full_text_review
    - treat_claim_mapping_as_expert_validation
    - use_treatment_guidelines_as_imaging_only_diagnostic_authority
    - use_imaging_reviews_as_final_diagnostic_authority
    - let_candidate_sources_support_public_ready_claims
    - cite_guidelines_as_general_page_authority_without_claim_scope
    - remove_uncertainty_language_before_full_text_and_expert_review
    - recommend_treatment
    - declare_any_page_public_ready_during_v0_4_lock

  platform_must:
    - label_each_source_by_type_and_scope
    - keep_review_status_visible
    - map_claims_to_specific_sources
    - define_what_each_source_can_and_cannot_support
    - preserve_diagnostic_authority_none
    - preserve_treatment_authority_none
    - require_full_text_review
    - require_expert_review
    - keep_candidate_source_gaps_visible
```

---

## 4. Locked Source Governance

```yaml
locked_source_governance:
  required_source_identity_fields:
    - source_id
    - source_title
    - source_type
    - organization_or_journal
    - publication_year
    - source_identity_status

  required_review_fields:
    - full_text_review_status
    - claim_mapping_status
    - expert_review_status
    - public_ready_support_status

  required_boundary_fields:
    - can_support_claims
    - cannot_support_claims
    - diagnostic_boundary
    - treatment_boundary
    - public_ready_boundary

  required_module_usage_fields:
    - used_by_modules
    - affected_claims
    - next_actions
```

---

## 5. Locked Claim Governance

```yaml
locked_claim_governance:
  required_claim_mapping_fields:
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

  public_ready_default:
    public_ready_allowed: false
    reason:
      - full_text_review_pending_by_default
      - expert_review_required
      - overclaim_prevention
      - patient_safety_boundary
```

---

## 6. Locked Public Language Governance

```yaml
locked_public_language_governance:
  first_language_candidate:
    page: docs/reasoning/temporal_comparison_methodology_v1.md
    phrase_file: docs/evidence/temporal_comparison_public_allowed_phrases_v1.md
    status: draft_only_not_public_ready

  public_language_must:
    - teach_reasoning
    - preserve_uncertainty
    - identify_missing_data
    - separate_observation_from_interpretation
    - separate_structural_fibrosis_from_reversible_opacity
    - avoid_patient_specific_diagnostic_claims
    - avoid_treatment_or_followup_recommendations

  public_language_must_not:
    - diagnose
    - classify_patient
    - recommend_treatment
    - recommend_follow_up_interval
    - replace_MDD
    - claim_certainty_without_review
```

---

## 7. Locked Candidate Source Gap Governance

```yaml
locked_candidate_source_gap_governance:
  candidate_source_rule:
    - Candidate sources may guide internal research direction only.
    - Candidate sources cannot support public-ready claims.
    - Candidate source status must remain visible.
    - Public-ready status remains blocked while candidate sources support major claims.

  highest_priority_gaps:
    - HRCT_technical_comparability_source
    - AE_IPF_or_AE_fibrotic_ILD_source
    - vascular_edema_DAH_PE_source_group
    - occupational_lung_disease_review_source
    - sarcoid_like_reaction_malignancy_review_source

  current_gap_resolution_status:
    resolved_for_public_candidate: 0
    full_text_reviewed: 0
    expert_reviewed: 0
```

---

## 8. First Public Candidate Status

```yaml
first_public_candidate_status:
  preferred_candidate_page:
    path: docs/reasoning/temporal_comparison_methodology_v1.md
    reason:
      - cross_cutting_reasoning_page
      - lower_risk_than_disease_specific_diagnosis_page
      - strong_safety_orientation
      - highlights_prior_CT_and_uncertainty

  current_gate_status:
    public_ready: false
    public_candidate: false
    gate_status: blocked

  blockers:
    - full_text_review_pending
    - expert_review_not_started
    - candidate_sources_present
    - public_allowed_phrases_not_expert_validated
    - public_ready_allowed_false_for_all_claims
```

---

## 9. Evidence Layer Lock Statement

```yaml
evidence_layer_v0_4_lock_statement:
  status: structurally_locked_blueprint
  public_ready: false
  public_candidate_allowed: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  source_review_required: true
  full_text_review_required: true
  expert_review_required: true

  lock_means:
    - evidence_governance_architecture_is_coherent
    - source_review_workflow_is_defined
    - claim_mapping_workflow_is_defined
    - public_language_safety_is_drafted
    - candidate_source_gaps_are_visible
    - public_ready_blockers_are_explicit

  lock_does_not_mean:
    - sources_are_fully_reviewed
    - claims_are_expert_validated
    - pages_are_public_ready
    - clinical_use_is_authorized
    - treatment_or_diagnosis_guidance_is_enabled
```

---

## 10. Next Allowed Steps

```yaml
next_allowed_steps_after_v0_4_seal:
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

## 11. Final Seal Rule

```text
The Evidence Layer is sealed only because its uncertainty is explicit.

No page is public-ready.

No claim is clinical authority.

No source is allowed to carry more than its reviewed scope.

That is the lock.
```