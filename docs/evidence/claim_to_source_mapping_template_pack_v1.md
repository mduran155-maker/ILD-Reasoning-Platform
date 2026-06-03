# Claim-to-Source Mapping Template Pack — v1

## Document Metadata

```yaml
id: evidence_claim_to_source_mapping_template_pack_v1
title: Claim-to-Source Mapping Template Pack
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: evidence_mapping_schema
diagnostic_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This document defines how platform claims must be mapped to evidence sources.

It prevents the platform from treating a source as general authority.

A source may support only:

- a specific claim,
- inside a specific scope,
- with a specific boundary,
- after an explicit review status is recorded.

This document does not complete claim mapping.

It defines the mapping structure.

---

## 1. Core Rule

```yaml
core_rule:
  statement: >
    A source does not support a page. 
    A source supports a specific claim within a defined scope and boundary.

  platform_must_not:
    - cite_a_source_as_general_page_authority
    - use_source_presence_as_evidence_review
    - use_abstract_only_review_as_full_text_review
    - use_treatment_guidelines_as_imaging_only_diagnostic_authority
    - use_imaging_reviews_as_final_diagnostic_authority
    - let_candidate_sources_support_public_ready_claims

  platform_must:
    - assign_claim_id_to_each_major_claim
    - map_claim_to_specific_source_id
    - define_source_scope
    - define_what_the_source_does_not_support
    - record_full_text_review_status
    - record_public_ready_permission
    - preserve_uncertainty_when_mapping_is_incomplete
```

---

## 2. Claim ID Vocabulary

```yaml
claim_id_vocabulary:
  prefix_rules:
    UIP: UIP_pattern_or_IPF_related_claim
    NSIP: NSIP_pattern_related_claim
    FHP: fibrotic_HP_claim
    SAR: sarcoidosis_claim
    GLILD: GLILD_claim
    GRAN: granulomatous_reasoning_claim
    SUPER: superimposed_events_claim
    TEMP: temporal_comparison_claim
    AE: acute_exacerbation_claim
    INF: infection_claim
    OP: organizing_pneumonia_claim
    MAL: malignancy_claim
    DRUG: drug_toxicity_treatment_related_claim
    VASC: vascular_edema_hemorrhage_claim
    SAFETY: editorial_or_safety_boundary_claim

  claim_id_format:
    pattern: PREFIX_MODULE_SHORTNAME_NUMBER
    examples:
      - UIP_PATTERN_001
      - FHP_EXPOSURE_001
      - SAR_MIMIC_001
      - SUPER_BASELINE_BIAS_001
      - TEMP_STRUCTURAL_VS_AIRSPACE_001
      - DRUG_TIMELINE_001
```

---

## 3. Claim Strength Vocabulary

```yaml
claim_strength_vocabulary:
  high_for_scope:
    meaning: Source strongly supports this claim inside its intended scope after review.

  moderate_for_scope:
    meaning: Source supports the claim as contextual reasoning, but not as standalone authority.

  low_or_candidate:
    meaning: Source may support draft awareness only; cannot support public-ready content.

  not_supported:
    meaning: Source should not be used for this claim.

  expert_review_required:
    meaning: Claim may be plausible but requires clinical expert validation before public use.
```

---

## 4. Source Scope Vocabulary

```yaml
source_scope_vocabulary:
  diagnostic_framework:
    description: Source supports a diagnostic reasoning framework but not automated diagnosis.

  imaging_pattern_awareness:
    description: Source supports recognition of imaging patterns and mimics.

  mimic_awareness:
    description: Source supports visibility of differential diagnoses or pitfalls.

  temporal_reasoning:
    description: Source supports progression, stability, regression, or longitudinal comparison reasoning.

  management_context:
    description: Source is primarily management-focused and must not become diagnostic authority.

  treatment_context:
    description: Source contains treatment guidance; current platform must not convert this into recommendations.

  evidence_limitation:
    description: Source supports caution, uncertainty, limitations, or lack of definitive evidence.

  expert_consensus:
    description: Source reflects expert agreement or consensus, but still requires scope control.

  candidate_context:
    description: Source is not yet verified or reviewed; draft awareness only.
```

---

## 5. Mapping Template

```yaml
claim_to_source_mapping_template:
  claim_id: REQUIRED
  claim_text: REQUIRED
  module_path: REQUIRED
  page_section: REQUIRED

  source_support:
    source_id: REQUIRED
    source_type: REQUIRED
    source_review_record_path: REQUIRED
    source_identity_status: REQUIRED
    full_text_review_status: REQUIRED
    claim_mapping_status: REQUIRED

  mapping_scope:
    source_scope:
      - diagnostic_framework
      - imaging_pattern_awareness
      - mimic_awareness
      - temporal_reasoning
      - management_context
      - treatment_context
      - evidence_limitation
      - expert_consensus
      - candidate_context
    claim_strength: REQUIRED
    public_ready_allowed: false

  boundary:
    source_can_support:
      - REQUIRED
    source_cannot_support:
      - REQUIRED
    diagnostic_boundary:
      - REQUIRED
    treatment_boundary:
      - REQUIRED

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes: pending

  output_status:
    mapping_status: draft
    allowed_in_blueprint: true
    allowed_in_public_page: false
```

---

## 6. Example Mapping — Temporal Comparison Claim

```yaml
example_mapping_TEMP_STRUCTURAL_VS_AIRSPACE_001:
  claim_id: TEMP_STRUCTURAL_VS_AIRSPACE_001
  claim_text: >
    Temporal comparison should separate structural fibrotic progression from potentially reversible airspace opacity.
  module_path: docs/reasoning/temporal_comparison_methodology_v1.md
  page_section: Fibrotic Progression vs Reversible Opacity

  source_support:
    source_id: ATS_ERS_JRS_ALAT_2022_IPF_PPF
    source_type: clinical_practice_guideline
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping

  mapping_scope:
    source_scope:
      - diagnostic_framework
      - temporal_reasoning
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  boundary:
    source_can_support:
      - radiologic_progression_context
      - structural_fibrotic_progression_reasoning_context
    source_cannot_support:
      - automated_progression_diagnosis
      - public_ready_claim_without_full_text_review
      - treatment_recommendation
    diagnostic_boundary:
      - supports_reasoning_framework_not_patient_classification
    treatment_boundary:
      - treatment_guidance_not_active_platform_content

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes: pending

  output_status:
    mapping_status: draft
    allowed_in_blueprint: true
    allowed_in_public_page: false
```

---

## 7. Example Mapping — HP Exposure Claim

```yaml
example_mapping_FHP_EXPOSURE_001:
  claim_id: FHP_EXPOSURE_001
  claim_text: >
    Fibrotic HP reasoning requires exposure context, HRCT pattern review, and multidisciplinary integration rather than exposure history alone.
  module_path: docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
  page_section: Exposure Reasoning Layer

  source_support:
    source_id: ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    source_type: clinical_practice_guideline
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping

  mapping_scope:
    source_scope:
      - diagnostic_framework
      - mimic_awareness
      - evidence_limitation
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  boundary:
    source_can_support:
      - HP_multidomain_reasoning_context
      - exposure_HRCT_BAL_pathology_MDD_integration_context
    source_cannot_support:
      - HP_diagnosis_from_exposure_alone
      - HP_diagnosis_from_imaging_alone
      - treatment_recommendation
    diagnostic_boundary:
      - exposure_history_is_context_not_standalone_authority
    treatment_boundary:
      - antigen_avoidance_or_treatment_guidance_not_active_platform_content

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes: pending

  output_status:
    mapping_status: draft
    allowed_in_blueprint: true
    allowed_in_public_page: false
```

---

## 8. Example Mapping — Sarcoidosis Mimic Claim

```yaml
example_mapping_SAR_MIMIC_001:
  claim_id: SAR_MIMIC_001
  claim_text: >
    Sarcoidosis-like reasoning should keep infection, malignancy, occupational disease, immune deficiency, HP, and vasculitis visible when relevant.
  module_path: docs/reasoning/granulomatous_ild_reasoning_map_v1.md
  page_section: Mimic Review

  source_support:
    source_id: ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    source_type: clinical_practice_guideline
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping

  mapping_scope:
    source_scope:
      - diagnostic_framework
      - mimic_awareness
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  boundary:
    source_can_support:
      - alternative_cause_exclusion_context
      - sarcoidosis_diagnostic_framework_context
    source_cannot_support:
      - sarcoidosis_from_imaging_alone
      - sarcoidosis_from_granulomas_alone
      - automated_patient_classification
    diagnostic_boundary:
      - framework_support_only_not_final_platform_diagnosis
    treatment_boundary:
      - treatment_of_sarcoidosis_not_active_platform_content

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes: pending

  output_status:
    mapping_status: draft
    allowed_in_blueprint: true
    allowed_in_public_page: false
```

---

## 9. Example Mapping — Drug Timeline Claim

```yaml
example_mapping_DRUG_TIMELINE_001:
  claim_id: DRUG_TIMELINE_001
  claim_text: >
    Drug toxicity or treatment-related lung injury should not be inferred from timing alone; infection, malignancy progression, edema, OP, AE, hemorrhage, and PE must remain visible.
  module_path: docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
  page_section: Core Safety Principle

  source_support:
    source_id: Fleischner_2021_DRUG_RELATED_PNEUMONITIS_POSITION_PAPER
    source_type: position_paper
    source_review_record_path: docs/evidence/source_review_records_core_guidelines_v1.md
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping

  mapping_scope:
    source_scope:
      - imaging_pattern_awareness
      - mimic_awareness
      - treatment_context
    claim_strength: moderate_for_scope
    public_ready_allowed: false

  boundary:
    source_can_support:
      - treatment_related_pneumonitis_pattern_context
      - medication_timeline_context
      - mimic_awareness
    source_cannot_support:
      - drug_toxicity_from_timing_alone
      - treatment_action_by_platform
      - infection_or_progression_exclusion
    diagnostic_boundary:
      - CT_pattern_and_timing_do_not_prove_drug_toxicity
    treatment_boundary:
      - platform_must_not_recommend_drug_discontinuation_steroids_or_therapy_change

  review_requirements:
    requires_full_text_review: true
    requires_expert_review: true
    reviewer_notes: pending

  output_status:
    mapping_status: draft
    allowed_in_blueprint: true
    allowed_in_public_page: false
```

---

## 10. Public-ready Claim Gate

```yaml
public_ready_claim_gate:
  a_claim_may_enter_public_candidate_only_if:
    - source_identity_status_is_official_page_verified_or_bibliographic_verified
    - full_text_review_status_is_full_text_reviewed_or_expert_reviewed
    - claim_mapping_status_is_claim_mapped_or_expert_validated_mapping
    - diagnostic_boundary_is_explicit
    - treatment_boundary_is_explicit
    - public_ready_allowed_is_true
    - source_scope_matches_claim_text
    - claim_does_not_exceed_source_scope
    - uncertainty_language_is_preserved_when_required

  a_claim_must_remain_blueprint_only_if:
    - source_is_unverified
    - source_is_candidate
    - full_text_review_status_is_pending
    - claim_mapping_status_is_partial_or_not_mapped
    - claim_uses_treatment_guideline_as_diagnostic_authority
    - claim_uses_imaging_review_as_final_diagnosis
    - claim_removes_need_for_MDD_or_clinician_judgment
```

---

## 11. Claim Mapping Review Checklist

```yaml
claim_mapping_review_checklist:
  before_mapping:
    - identify_exact_claim_text
    - identify_module_and_section
    - identify_source_id
    - confirm_source_review_record_exists
    - confirm_source_type

  during_mapping:
    - define_source_scope
    - define_claim_strength
    - define_diagnostic_boundary
    - define_treatment_boundary
    - define_what_source_cannot_support
    - set_public_ready_allowed_false_by_default

  after_mapping:
    - verify_claim_does_not_exceed_source_scope
    - verify_candidate_sources_are_not_used_as_authority
    - verify_uncertainty_language_remains
    - verify_MDD_or_expert_review_not_replaced
    - mark_full_text_and_expert_review_requirements
```

---

## 12. First Page Candidate Mapping Targets

```yaml
first_page_candidate_mapping_targets:
  preferred_first_candidate:
    page: docs/reasoning/temporal_comparison_methodology_v1.md
    reason:
      - cross-cutting_platform_value
      - less_disease_specific_than_diagnostic_pattern_pages
      - strong_safety_orientation
      - good_bridge_between_v0_1_v0_2_v0_3
    required_claim_groups:
      - structural_fibrosis_vs_reversible_opacity
      - prior_CT_required_for_temporal_claims
      - technical_comparability
      - new_GGO_requires_superimposed_event_review
      - improvement_of_opacity_not_equal_fibrosis_reversal

  alternate_candidate:
    page: docs/reasoning/superimposed_events_core_blueprint_v1.md
    reason:
      - platform_philosophy_page
      - not_a_diagnostic_page
      - useful_for_public_safety_messaging
    required_claim_groups:
      - baseline_ILD_label_must_not_swallow_new_findings
      - superimposed_event_differential
      - missing_data_awareness
      - urgent_or_MDD_review_visibility
```

---

## 13. Final Mapping Rule

```text
No claim is public-ready because it sounds correct.

A claim becomes public-candidate only when its source, scope, boundary, and review status are visible.
```