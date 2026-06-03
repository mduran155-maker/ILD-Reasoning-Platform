# Evidence Governance Registry — v1

## Document Metadata

```yaml
id: evidence_governance_registry_v1
title: Evidence Governance Registry
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: evidence_crosslink_registry
diagnostic_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This registry connects the v0.4 evidence governance layer.

It tracks:

- source review matrix,
- source review records,
- claim-to-source mapping templates,
- first page-level claim maps,
- public-ready blockers,
- and evidence safety rules.

This registry does not make any page public-ready.

It defines the evidence workflow required before public-ready status can be considered.

---

## 1. Implemented Evidence Governance Files

```yaml
implemented_evidence_governance_files:
  source_review_matrix:
    path: docs/evidence/source_review_matrix_v1.md
    role: global_source_status_and_scope_matrix
    status: implemented

  core_guideline_source_review_records:
    path: docs/evidence/source_review_records_core_guidelines_v1.md
    role: structured_review_records_for_core_guidelines
    status: implemented

  claim_to_source_mapping_template_pack:
    path: docs/evidence/claim_to_source_mapping_template_pack_v1.md
    role: claim_mapping_schema_and_public_ready_gate_template
    status: implemented

  temporal_comparison_claim_map:
    path: docs/evidence/temporal_comparison_claim_map_v1.md
    role: first_page_level_claim_to_source_mapping_candidate
    status: implemented
```

---

## 2. v0.4 Evidence Layer Current Status

```yaml
v0_4_evidence_layer_current_status:
  module: Evidence Layer Lock / Source Review Governance
  status: active_development
  public_ready: false
  diagnostic_authority: none
  treatment_authority: none
  expert_review_required: true
  full_text_review_required: true

  completed:
    - source_review_matrix_v1
    - source_review_records_core_guidelines_v1
    - claim_to_source_mapping_template_pack_v1
    - temporal_comparison_claim_map_v1

  active_claim_map_candidate:
    page: docs/reasoning/temporal_comparison_methodology_v1.md
    claim_map: docs/evidence/temporal_comparison_claim_map_v1.md
    gate_status: blocked
    reason:
      - full_text_review_pending
      - expert_review_not_started
      - candidate_sources_present
      - public_allowed_phrases_not_defined
```

---

## 3. Evidence Workflow

```yaml
evidence_workflow:
  step_1_source_identity:
    required:
      - source_id
      - source_title
      - source_type
      - year
      - organization_or_journal
      - source_identity_status

  step_2_source_review_record:
    required:
      - platform_scope
      - can_support_claims
      - cannot_support_claims
      - diagnostic_boundary
      - treatment_boundary
      - used_by_modules
      - next_actions

  step_3_claim_mapping:
    required:
      - claim_id
      - exact_claim_text
      - module_path
      - page_section
      - source_id
      - source_scope
      - claim_strength
      - boundary_statement
      - review_requirements

  step_4_public_candidate_gate:
    required:
      - full_text_reviewed_or_expert_reviewed
      - claim_mapped_or_expert_validated_mapping
      - public_ready_allowed_true
      - uncertainty_language_preserved
      - source_scope_matches_claim_text
      - no_treatment_recommendation_leak
      - no_diagnostic_authority_leak

  step_5_public_ready_candidate:
    allowed_only_if:
      - all_major_claims_are_mapped
      - all_sources_are_reviewed
      - expert_review_completed
      - public_allowed_phrases_defined
      - forbidden_claims_checked
      - page_level_public_gate_passed
```

---

## 4. Source Type Boundary Registry

```yaml
source_type_boundary_registry:
  clinical_practice_guideline:
    allowed_role:
      - diagnostic_framework_context
      - terminology_support_after_review
      - progression_or_pattern_context_when_scope_matches
    disallowed_role:
      - automated_patient_diagnosis
      - imaging_only_authority
      - treatment_recommendation_by_platform

  clinical_statement:
    allowed_role:
      - clinical_context
      - practice_context_after_review
      - mimic_awareness
    disallowed_role:
      - final_diagnostic_authority
      - public_ready_claim_without_full_text_review

  consensus_statement:
    allowed_role:
      - consensus_definition_context
      - multidisciplinary_reasoning_context
      - evidence_limitation_context
    disallowed_role:
      - imaging_only_diagnosis
      - expert_review_replacement

  position_paper:
    allowed_role:
      - pattern_awareness
      - terminology_context
      - multidisciplinary_context
    disallowed_role:
      - automatic_management_action
      - treatment_instruction_by_platform

  imaging_review:
    allowed_role:
      - pattern_awareness
      - mimic_visibility
      - differential_reasoning_support
    disallowed_role:
      - final_diagnostic_label
      - exclusion_of_mimics_without_context

  candidate_source:
    allowed_role:
      - internal_awareness_only
      - future_source_identification
    disallowed_role:
      - public_ready_claim_support
      - high_certainty_authority
```

---

## 5. Current Evidence Blockers

```yaml
current_evidence_blockers:
  full_text_review:
    status: blocking
    description: Core sources are not yet marked full_text_reviewed.

  expert_review:
    status: blocking
    description: No page or claim map has expert validation.

  candidate_sources:
    status: blocking
    description: Some claim maps still depend on candidate sources, especially AE, HRCT technical comparability, vascular/DAH/PE, and occupational/oncology contexts.

  public_allowed_phrases:
    status: blocking
    description: No public-ready allowed phrase set has been defined.

  test_case_coverage:
    status: secondary_blocker
    description: Current test cases are blueprint-level and not broad enough for public education release.

  UIP_parity:
    status: secondary_blocker
    description: UIP page remains less mature than Fibrotic HP, Sarcoidosis, and Superimposed Events pages.
```

---

## 6. First Public Candidate Strategy

```yaml
first_public_candidate_strategy:
  preferred_candidate:
    page: docs/reasoning/temporal_comparison_methodology_v1.md
    reason:
      - cross_cutting_reasoning_page
      - lower_risk_than_disease_specific_diagnosis_page
      - strong_safety_orientation
      - highlights_prior_CT_and_uncertainty
      - useful_to_radiology_pulmonary_and_MDD_education

  current_gate_status:
    public_candidate: false
    gate_status: blocked

  must_complete_before_candidate:
    - full_text_review_ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - verify_HRCT_technical_comparability_source
    - verify_Fleischner_2017_nodule_context_source_if_used
    - expert_review_temporal_comparison_claim_map
    - define_public_allowed_phrases
    - remove_or_replace_candidate_sources_for_public_claims
```

---

## 7. Evidence Safety Invariants

```yaml
evidence_safety_invariants:
  platform_must_not:
    - treat_source_presence_as_evidence_review
    - treat_source_review_record_as_public_ready_permission
    - treat_claim_mapping_as_expert_validation
    - cite_guidelines_as_general_page_authority
    - use_management_guidelines_as_imaging_only_diagnostic_authority
    - use_imaging_reviews_as final_diagnosis_authority
    - allow_candidate_sources_to_support_public_ready_claims
    - remove_uncertainty_language_before_review
    - recommend_treatment

  platform_must:
    - keep_review_status_visible
    - keep_public_ready_false_until_gate_passes
    - define_claim_scope_and_boundary
    - preserve_diagnostic_authority_none
    - preserve_treatment_authority_none
    - require_full_text_review
    - require_expert_review
    - separate_internal_blueprint_from_public_candidate
```

---

## 8. Next Recommended Evidence Steps

```yaml
next_recommended_evidence_steps:
  step_v0_4_4:
    title: Evidence Governance Registry
    path: docs/evidence/evidence_governance_registry_v1.md
    status: current_step

  step_v0_4_5:
    title: Public Allowed Phrase Draft for Temporal Comparison
    path: docs/evidence/temporal_comparison_public_allowed_phrases_v1.md
    reason:
      - define safe public-facing wording
      - prevent overclaim
      - prepare expert review

  step_v0_4_6:
    title: Candidate Source Gap List
    path: docs/evidence/candidate_source_gap_list_v1.md
    reason:
      - identify weak or unverified sources
      - replace candidate sources before public candidate pages

  step_v0_4_7:
    title: Evidence Layer Lock Checklist
    path: docs/data/schema/evidence_layer_lock_checklist_v1.md
    reason:
      - verify source matrix, review records, claim maps, boundaries, and blockers before evidence seal
```

---

## 9. Final Evidence Governance Rule

```text
A source is not authority by existing.

A source becomes useful only when its scope, claim, boundary, review status, and public permission are explicit.
```