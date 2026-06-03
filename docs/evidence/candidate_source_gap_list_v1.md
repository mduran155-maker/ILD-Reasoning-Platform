# Candidate Source Gap List — v1

## Document Metadata

```yaml
id: evidence_candidate_source_gap_list_v1
title: Candidate Source Gap List
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: evidence_gap_registry
diagnostic_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This document lists weak, unverified, candidate, or incomplete evidence sources that block public-ready status.

It does not validate sources.

It identifies evidence gaps that must be resolved before claim mapping can become public-candidate.

The goal is to prevent candidate sources from silently becoming authority.

---

## 1. Core Rule

```yaml
core_rule:
  statement: >
    A candidate source may guide internal research direction, but it cannot support public-ready claims.

  platform_must_not:
    - use_candidate_sources_as_public_authority
    - hide_unverified_source_status
    - treat_pending_sources_as reviewed evidence
    - let_internal_blueprint_modules become citation authority
    - use reviews or guidelines outside their scope

  platform_must:
    - list all candidate source gaps
    - define what each source is needed for
    - define replacement or verification action
    - block public-ready status until resolved
```

---

## 2. Current Highest-priority Evidence Gaps

```yaml
highest_priority_evidence_gaps:
  HRCT_TECHNICAL_COMPARABILITY_REVIEW_SOURCE:
    status: missing_or_candidate
    needed_for:
      - temporal_comparison_methodology_v1
      - temporal_comparison_claim_map_v1
      - temporal_comparison_public_allowed_phrases_v1
    needed_claims:
      - CT technique can affect apparent interval change.
      - Slice thickness, reconstruction kernel, inspiration, motion, contrast status, and positioning can influence comparison.
      - Subtle progression or regression should be interpreted cautiously when protocols differ.
    current_blocker:
      - technical_comparability_claims_are_draft_only
      - public_ready_language_blocked
    required_action:
      - identify_reliable_HRCT_technical_comparison_source
      - verify_bibliography
      - full_text_review
      - claim_mapping
      - expert_review

  AE_IPF_REVISED_DEFINITION_AND_REVIEW_SOURCE:
    status: candidate_unverified
    needed_for:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_events_core_blueprint_v1
      - temporal_comparison_methodology_v1
      - temporal_comparison_claim_map_v1
    needed_claims:
      - acute_exacerbation reasoning requires acute clinical worsening and new bilateral alveolar abnormality on ILD background.
      - infection, edema, PE, hemorrhage, drug toxicity, and other mimics must remain visible.
    current_blocker:
      - AE_related_public_claims_blocked
      - AE_source_must_be_primary_or_high_quality_review
    required_action:
      - identify_primary_AE_IPF_definition_source
      - identify_non_IPF_AE_fibrotic_ILD_review_source_if_needed
      - verify_full_text
      - map_AE_claims
      - expert_review

  VASCULAR_EDEMA_HEMORRHAGE_SOURCE_GROUP:
    status: candidate_group
    needed_for:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - temporal_comparison_methodology_v1
    needed_claims:
      - smooth septal thickening, GGO, effusions, and volume context may support edema reasoning.
      - DAH can mimic infection, AE, drug toxicity, or edema.
      - PE / infarct can mimic pneumonia, OP, malignancy, or ILD worsening.
    current_blocker:
      - vascular_DAH_PE_public_claims_blocked
    required_action:
      - identify_best_pulmonary_edema_CT_review
      - identify_best_DAH_clinical_imaging_review
      - identify_best_PE_infarct_CT_review
      - full_text_review
      - claim_mapping
      - expert_review

  OCCUPATIONAL_LUNG_DISEASE_REVIEW_SOURCE:
    status: candidate_unverified
    needed_for:
      - sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1
      - fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    needed_claims:
      - occupational exposure can mimic sarcoidosis-like or fibrotic granulomatous disease.
      - dust, silica, beryllium, pneumoconiosis, and PMF contexts must remain visible.
    current_blocker:
      - occupational_public_claims_blocked_except_where_ATS_beryllium_statement_is_mapped
    required_action:
      - identify_high_quality_occupational_lung_disease_review
      - verify_source
      - full_text_review
      - claim_mapping
      - occupational_or_thoracic_radiology_expert_review

  SARCOID_LIKE_REACTION_MALIGNANCY_REVIEW_SOURCE:
    status: candidate_unverified
    needed_for:
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    needed_claims:
      - sarcoid-like reaction can mimic malignancy or sarcoidosis in oncology context.
      - FDG uptake is not specific.
      - malignancy, inflammation, infection, and treatment-related reactions may overlap.
    current_blocker:
      - sarcoid_like_reaction_public_claims_blocked
    required_action:
      - identify_verified_review_or_consensus_source
      - separate_PET_CT_irAE_sources_from_general_sarcoid_like_reaction_sources
      - full_text_review
      - oncology_or_nuclear_medicine_expert_review
```

---

## 3. Secondary Evidence Gaps

```yaml
secondary_evidence_gaps:
  LUNG_CANCER_IN_FIBROTIC_ILD_REVIEW_SOURCE:
    status: pending_review
    needed_for:
      - malignancy_on_fibrotic_ILD_background_v1
      - temporal_comparison_methodology_v1
    needed_claims:
      - fibrotic ILD background can obscure focal malignancy.
      - new or growing focal lesions should not be hidden inside fibrosis.
    required_action:
      - identify_high_quality_review_or_cohort
      - full_text_review
      - claim_mapping

  OP_VS_INFECTION_VS_MALIGNANCY_SOURCE_GROUP:
    status: pending_review
    needed_for:
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    needed_claims:
      - OP-like morphology is not diagnostic alone.
      - persistent focal OP-like opacity requires malignancy and infection review.
    required_action:
      - verify_OP_review_sources
      - identify_OP_malignancy_mimic_source_if_available
      - full_text_review

  INFECTION_ON_ILD_BACKGROUND_SOURCE_GROUP:
    status: pending_review
    needed_for:
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    needed_claims:
      - infection can mimic progression, AE, OP, drug toxicity, and edema.
      - immunosuppressed ILD patients may have atypical infectious presentations.
    required_action:
      - identify_high_quality_review
      - separate_general_pneumonia_sources_from_immunosuppressed_ILD_sources
      - full_text_review

  DRUG_INDUCED_ILD_GENERAL_REVIEW_SOURCE:
    status: pending_review
    needed_for:
      - drug_toxicity_treatment_related_lung_injury_v1
      - organizing_pneumonia_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    needed_claims:
      - drug-induced lung injury may present with OP-like, NSIP-like, HP-like, DAD-like, eosinophilic, hemorrhagic, or mixed patterns.
    required_action:
      - verify_general_drug_induced_ILD_review
      - distinguish_from_Fleischner_2021_DRP_position_paper
      - full_text_review

  PULMONARY_HYPERTENSION_IN_ILD_SOURCE:
    status: future_gap
    needed_for:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - future_pulmonary_hypertension_in_fibrotic_ILD_context_v1
    needed_claims:
      - pulmonary hypertension or right-heart decompensation can contribute to acute decline disproportionate to CT parenchymal change.
    required_action:
      - future_source_identification
      - not_required_for_current_v0_4_lock_if_claims_remain_draft
```

---

## 4. Candidate Source Blocker Table

| Source Gap | Affected Modules | Public-ready Impact | Priority |
|---|---|---|---|
| HRCT technical comparability | Temporal Comparison | Blocks first public candidate | Very high |
| AE-IPF / AE-fibrotic ILD source | AE vs infection vs edema | Blocks AE language | Very high |
| Edema / DAH / PE source group | Vascular mimic panel | Blocks vascular mimic public language | Very high |
| Occupational lung disease review | Granulomatous gray zones | Blocks occupational mimic public language | High |
| Sarcoid-like reaction review | Sarcoidosis vs malignancy | Blocks oncology mimic language | High |
| Lung cancer in fibrotic ILD | Malignancy module | Blocks malignancy-on-fibrosis claims | High |
| Infection on ILD background | Infection module | Blocks infection public language | High |
| OP mimic source group | OP module | Blocks OP public language | Moderate-high |
| Drug-induced ILD general review | Drug toxicity module | Blocks broader DRP claims | Moderate-high |

---

## 5. Public Candidate Impact

```yaml
public_candidate_impact:
  temporal_comparison_methodology_v1:
    current_status: blocked
    most_important_blockers:
      - HRCT_TECHNICAL_COMPARABILITY_REVIEW_SOURCE
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF_full_text_review
      - AE_IPF_REVISED_DEFINITION_AND_REVIEW_SOURCE_if_AE_claims_remain_in_public_text
      - Fleischner_2017_nodule_context_if_persistent_focal_opacity_claims_remain

  safest_public_candidate_strategy:
    option_A:
      description: publish_temporal_comparison_as_reasoning_principle_page_only
      requirements:
        - remove_or_soften_AE_specific_claims
        - remove_or_soften_nodule_management_context
        - keep technical comparability as caution language only until source verified
        - expert_review_required

    option_B:
      description: delay_public_candidate_until_all_claim_groups_are_mapped
      requirements:
        - verify_all_high_priority_sources
        - full_text_review
        - expert_review
```

---

## 6. Replacement / Verification Workflow

```yaml
replacement_verification_workflow:
  step_1_identify_candidate_gap:
    - source_gap_id
    - affected_claims
    - affected_modules
    - public_ready_blocker_status

  step_2_find_best_source:
    - prefer_guideline_or_consensus_when_available
    - prefer_peer_reviewed_review_for_pattern_awareness
    - prefer official_society_publication_when_possible
    - avoid low_quality_or_non_peer_reviewed_source_for_public_claims

  step_3_verify_source_identity:
    - title
    - authors_or_organization
    - journal_or_society
    - year
    - DOI_or_publisher_page_when_available

  step_4_review_full_text:
    - relevant_sections
    - exact_supported_claims
    - limitations
    - source_scope

  step_5_map_claims:
    - claim_id
    - claim_text
    - source_scope
    - claim_strength
    - boundaries
    - public_ready_allowed_default_false

  step_6_expert_review:
    - radiology_or_pulmonary_expert
    - additional_specialist_when_needed
    - expert_validated_mapping_if_approved
```

---

## 7. Gap Resolution Status Vocabulary

```yaml
gap_resolution_status_vocabulary:
  unresolved:
    meaning: no verified source selected

  source_identified:
    meaning: likely source identified but not reviewed

  bibliographic_verified:
    meaning: source identity verified but full text not reviewed

  full_text_review_pending:
    meaning: source accessible or located but not reviewed

  full_text_reviewed:
    meaning: source reviewed by project team

  claim_mapped:
    meaning: claims mapped to source scope

  expert_reviewed:
    meaning: specialist reviewed mapping and scope

  resolved_for_public_candidate:
    meaning: source gap no longer blocks public-candidate status for mapped claim
```

---

## 8. Current Gap Status Summary

```yaml
current_gap_status_summary:
  total_highest_priority_gaps: 5
  total_secondary_gaps: 5
  resolved_for_public_candidate: 0
  full_text_reviewed: 0
  expert_reviewed: 0

  public_ready_allowed:
    any_page: false
    temporal_comparison_methodology_v1: false

  evidence_layer_status:
    - structurally_governed
    - not_evidence_locked
    - not_public_ready
```

---

## 9. Final Candidate Source Rule

```text
A candidate source is useful because it shows what we still need.

It is dangerous only if we let it pretend to be reviewed evidence.
```