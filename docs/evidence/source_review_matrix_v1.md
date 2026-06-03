# Source Review Matrix — v1

## Document Metadata

```yaml
id: evidence_source_review_matrix_v1
title: Source Review Matrix
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: evidence_governance_matrix
diagnostic_authority: none
module_version: v0.4
last_updated: draft
```

---

## 0. Purpose

This matrix tracks whether a source can safely support platform claims.

It separates:

- source identity,
- source type,
- source scope,
- citation status,
- full-text review status,
- claim-to-source mapping,
- diagnostic authority,
- treatment authority,
- public-ready support,
- and module usage.

This matrix is not a bibliography.

It is an evidence governance layer.

---

## 1. Source Review Status Vocabulary

```yaml
source_review_status_vocabulary:
  source_identity_status:
    unverified: source identity not yet confirmed
    bibliographic_verified: title/year/journal or organization verified
    official_page_verified: source verified through official organization or publisher page
    duplicate_or_deprecated: source replaced by newer or better source

  full_text_review_status:
    not_started: no full-text review performed
    abstract_only: only abstract or citation metadata reviewed
    full_text_available_not_reviewed: full text appears accessible but has not been reviewed
    full_text_review_pending: full text review required before public-ready use
    full_text_reviewed: full text reviewed by project team
    expert_reviewed: reviewed by appropriate clinical/domain expert

  claim_mapping_status:
    not_mapped: no claim-to-source mapping yet
    partial_mapping: some module claims linked to source scope
    claim_mapped: source claims mapped to platform statements
    expert_validated_mapping: claim mapping reviewed by expert

  public_ready_support:
    none: cannot support public-ready content
    limited_educational_context: may support educational context after review
    candidate_support: can support draft module with caution labels
    public_ready_support_after_review: may support public page only after full-text and expert review
```

---

## 2. Core Evidence Safety Rule

```yaml
core_evidence_safety_rule:
  platform_must_not:
    - treat_source_presence_as_source_review
    - treat_abstract_review_as_full_text_review
    - use_treatment_guidelines_as_imaging_only_diagnostic_authority
    - use_imaging_reviews_as_final_diagnostic_authority
    - use_case_reports_as_high_certainty_general_rules
    - remove_uncertainty_when_source_scope_is_limited
    - claim_public_ready_status_without_full_text_and_expert_review

  platform_must:
    - label_each_source_by_type_and_scope
    - map_each_source_to_specific_platform_claims
    - keep_candidate_sources_visibly_pending
    - distinguish_guideline_consensus_review_position_paper_case_series
    - preserve_diagnostic_and_treatment_boundaries
    - require_expert_review_for_public_ready_clinical_pages
```

---

## 3. Source Review Matrix — Core Guidelines and Statements

```yaml
source_review_matrix:
  ATS_ERS_JRS_ALAT_2022_IPF_PPF:
    title: Idiopathic Pulmonary Fibrosis (an Update) and Progressive Pulmonary Fibrosis in Adults
    source_type: clinical_practice_guideline
    organizations:
      - American Thoracic Society
      - European Respiratory Society
      - Japanese Respiratory Society
      - Asociación Latinoamericana del Tórax
    year: 2022
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - uip_pattern_gold_standard_v1
      - fibrotic_ild_triage_map_v1
      - superimposed_events_core_blueprint_v1
      - temporal_comparison_methodology_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    can_support_claims:
      - IPF_PPF_framework_context
      - radiologic_progression_context
      - fibrotic_progression_reasoning
    cannot_support_claims:
      - imaging_only_patient_diagnosis
      - treatment_recommendation_by_platform
      - public_ready_claim_without_review
    diagnostic_boundary:
      - guideline_supports_framework_not_automated_diagnosis
    treatment_boundary:
      - treatment_content_not_activated_in_current_platform
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - claim_to_section_mapping
      - UIP_parity_update_mapping

  ATS_JRS_ALAT_2020_HP_DIAGNOSIS:
    title: Diagnosis of Hypersensitivity Pneumonitis in Adults
    source_type: clinical_practice_guideline
    organizations:
      - American Thoracic Society
      - Japanese Respiratory Society
      - Asociación Latinoamericana del Tórax
    year: 2020
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - fibrotic_hp_pattern_gold_standard_v1
      - fibrotic_ild_triage_map_v1
      - sarcoidosis_vs_hypersensitivity_pneumonitis_gray_zone_v1
      - fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1
      - temporal_comparison_methodology_v1
    can_support_claims:
      - HP_diagnostic_framework_context
      - fibrotic_HP_HRCT_reasoning_context
      - exposure_HRCT_BAL_pathology_MDD_integration_context
    cannot_support_claims:
      - HP_diagnosis_from_imaging_alone
      - exposure_history_as_standalone_diagnosis
      - treatment_recommendation_by_platform
    diagnostic_boundary:
      - guideline_supports_multidomain_HP_reasoning
      - does_not_replace_MDD
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - HP_pattern_claim_mapping
      - exposure_reasoning_claim_mapping

  ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION:
    title: Diagnosis and Detection of Sarcoidosis
    source_type: clinical_practice_guideline
    organization:
      - American Thoracic Society
    year: 2020
    source_identity_status: official_page_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_pattern_gold_standard_v1
      - sarcoidosis_pattern_taxonomy_v1
      - granulomatous_ild_reasoning_map_v1
      - sarcoidosis_vs_granulomatous_infection_gray_zone_v1
      - sarcoidosis_vs_glild_gray_zone_v1
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
    can_support_claims:
      - sarcoidosis_diagnostic_framework
      - compatible_clinical_context_plus_granulomatous_inflammation_plus_mimic_exclusion
      - alternative_causes_must_remain_visible
    cannot_support_claims:
      - sarcoidosis_from_imaging_alone
      - sarcoidosis_from_granulomas_alone
      - sarcoidosis_without_infection_malignancy_occupational_GLILD_or_vasculitis_review_when_relevant
    diagnostic_boundary:
      - supports_framework_not_automated_case_classification
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - sarcoidosis_pattern_claim_mapping
      - granulomatous_gray_zone_claim_mapping

  BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT:
    title: BTS Clinical Statement on Pulmonary Sarcoidosis
    source_type: clinical_statement
    organization:
      - British Thoracic Society
    year: 2021
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_pattern_gold_standard_v1
      - sarcoidosis_pattern_taxonomy_v1
      - sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
    can_support_claims:
      - pulmonary_sarcoidosis_clinical_context
      - mimic_awareness_context
      - occupational_history_importance_context
    cannot_support_claims:
      - sarcoidosis_final_diagnosis_from_imaging
      - public_ready_claim_without_full_text_review
    diagnostic_boundary:
      - clinical_statement_context_not_automated_diagnosis
    public_ready_support: public_ready_support_after_review
    next_action:
      - official_source_confirmation
      - full_text_review
      - occupational_mimic_claim_mapping
```

---

## 4. Source Review Matrix — Fibrotic / Pattern / Nodule Sources

```yaml
fibrotic_pattern_and_nodule_sources:
  Fleischner_2017_Pulmonary_Nodule_Guidelines_Context:
    title: Guidelines for Management of Incidental Pulmonary Nodules Detected on CT Images
    source_type: guideline_context
    organization:
      - Fleischner Society
    year: 2017
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: not_mapped
    used_by_modules:
      - malignancy_on_fibrotic_ILD_background_v1
      - temporal_comparison_methodology_v1
    can_support_claims:
      - pulmonary_nodule_followup_context
      - nodule_risk_framework_context
    cannot_support_claims:
      - automatic_nodule_management_in_fibrotic_ILD
      - platform_treatment_or_followup_recommendation
      - malignancy_diagnosis_from_nodule_alone
    diagnostic_boundary:
      - nodule_guideline_context_only
      - ILD_background_requires_extra_caution
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - determine_how_to_label_as_context_not_decision_rule

  Fleischner_ILA_Position_Paper_2020:
    title: Interstitial Lung Abnormalities Detected Incidentally on CT
    source_type: position_paper
    organization:
      - Fleischner Society
    year: 2020
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: not_mapped
    used_by_modules:
      - fibrotic_ild_triage_map_v1
      - temporal_comparison_methodology_v1
    can_support_claims:
      - incidental_interstitial_abnormality_context
      - early_fibrotic_abnormality_reasoning_context
    cannot_support_claims:
      - ILD_diagnosis_from_ILA_alone
      - public_ready_claim_without_review
    public_ready_support: public_ready_support_after_review
    next_action:
      - source_identity_verification
      - full_text_review
      - claim_mapping
```

---

## 5. Source Review Matrix — GLILD / Immune Deficiency Sources

```yaml
GLILD_sources:
  BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT:
    title: BLF/UKPIN Consensus Statement on the Definition, Diagnosis and Management of Granulomatous-Lymphocytic Interstitial Lung Disease in Common Variable Immunodeficiency Disorders
    source_type: consensus_statement
    organizations:
      - British Lung Foundation
      - United Kingdom Primary Immunodeficiency Network
    year: 2017
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    can_support_claims:
      - GLILD_definition_context
      - CVID_GLILD_reasoning_context
      - immune_deficiency_context_importance
    cannot_support_claims:
      - GLILD_from_imaging_alone
      - GLILD_public_ready_claim_without_expert_review
    diagnostic_boundary:
      - consensus_statement_not_imaging_only_authority
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - immunology_expert_review_required

  CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023:
    title: Diagnostic testing for interstitial lung disease in common variable immunodeficiency
    source_type: systematic_review
    year: 2023
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
    can_support_claims:
      - diagnostic_testing_evidence_limitations
      - cautious_language_for_CVID_ILD
    cannot_support_claims:
      - definitive_GLILD_diagnostic_algorithm
      - imaging_only_GLILD_classification
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - evidence_limitation_claim_mapping

  GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024:
    title: Approach to diagnosing and managing granulomatous-lymphocytic interstitial lung disease
    source_type: peer_reviewed_review
    year: 2024
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
    can_support_claims:
      - practical_GLILD_reasoning_context
      - MDD_and_multidomain_review_context
    cannot_support_claims:
      - high_certainty_guideline_claim
      - imaging_only_diagnostic_authority
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - expert_review
```

---

## 6. Source Review Matrix — Occupational / Beryllium / Pneumoconiosis Sources

```yaml
occupational_sources:
  ATS_2014_BERYLLIUM_SENSITIVITY_AND_CHRONIC_BERYLLIUM_DISEASE_STATEMENT:
    title: Beryllium Sensitivity and Chronic Beryllium Disease
    source_type: official_statement
    organization:
      - American Thoracic Society
    year: 2014
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
    can_support_claims:
      - beryllium_exposure_context
      - BeLPT_context
      - chronic_beryllium_disease_sarcoidosis_mimic_context
    cannot_support_claims:
      - CBD_diagnosis_from_CT_alone
      - BeLPT_as_standalone_platform_diagnosis
    diagnostic_boundary:
      - exposure_and_testing_context_required
    public_ready_support: public_ready_support_after_review
    next_action:
      - official_source_confirmation
      - full_text_review
      - BeLPT_claim_mapping

  OCCUPATIONAL_LUNG_DISEASE_REVIEW_SOURCE_CANDIDATE:
    title: Occupational lung disease review source
    source_type: candidate_review
    year: source_review_pending
    source_identity_status: unverified
    full_text_review_status: not_started
    claim_mapping_status: not_mapped
    used_by_modules:
      - sarcoidosis_vs_berylliosis_or_pneumoconiosis_gray_zone_v1
      - fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1
    can_support_claims:
      - none_until_verified
    cannot_support_claims:
      - public_ready_claim
      - high_certainty_occupational_diagnosis
    public_ready_support: none
    next_action:
      - identify_best_source
      - verify_bibliography
      - full_text_review
```

---

## 7. Source Review Matrix — Oncology / Sarcoid-like Reaction Sources

```yaml
oncology_sarcoid_like_reaction_sources:
  ICI_RELATED_SARCOID_LIKE_REACTION_PET_CT_REVIEW:
    title: Immune checkpoint inhibitor-related adverse effects and FDG PET/CT findings
    source_type: imaging_review
    year: 2021
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    can_support_claims:
      - ICI_sarcoid_like_reaction_awareness
      - FDG_PET_CT_pitfall_context
      - inflammatory_mimic_context
    cannot_support_claims:
      - sarcoid_like_reaction_diagnosis_from_PET_alone
      - malignancy_exclusion
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - PET_context_claim_mapping

  FDG_PET_CT_IMMUNOTHERAPY_IRAE_REVIEW_2024:
    title: FDG PET/CT patterns of immune-related adverse events in immune checkpoint inhibitor therapy
    source_type: peer_reviewed_review
    year: 2024
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    can_support_claims:
      - immunotherapy_irAE_imaging_context
      - PET_CT_inflammatory_mimic_context
    cannot_support_claims:
      - PET_only_classification
      - treatment_decision_by_platform
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - claim_mapping

  SARCOID_LIKE_REACTION_MALIGNANCY_REVIEW_CANDIDATE:
    title: Sarcoid-like reaction in malignancy context
    source_type: candidate_review
    year: source_review_pending
    source_identity_status: unverified
    full_text_review_status: not_started
    claim_mapping_status: not_mapped
    used_by_modules:
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
    can_support_claims:
      - none_until_verified
    cannot_support_claims:
      - public_ready_claim
      - generalized_diagnostic_rule
    public_ready_support: none
    next_action:
      - replace_with_verified_review_or_case_series
      - full_text_review
```

---

## 8. Source Review Matrix — GPA / AAV / Vasculitis Sources

```yaml
GPA_AAV_sources:
  ACR_VF_2021_ANCA_ASSOCIATED_VASCULITIS_GUIDELINE:
    title: 2021 American College of Rheumatology / Vasculitis Foundation Guideline for the Management of ANCA-Associated Vasculitis
    source_type: management_guideline
    organizations:
      - American College of Rheumatology
      - Vasculitis Foundation
    year: 2021
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    can_support_claims:
      - AAV_management_context
      - GPA_AAV_red_flag_context
      - specialist_review_context
    cannot_support_claims:
      - GPA_diagnosis_from_CT_alone
      - ANCA_as_standalone_diagnostic_authority
      - platform_treatment_recommendation
    diagnostic_boundary:
      - management_guideline_not_imaging_only_diagnostic_authority
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - management_vs_diagnostic_boundary_mapping

  EULAR_2022_ANCA_ASSOCIATED_VASCULITIS_RECOMMENDATIONS:
    title: EULAR recommendations for the management of ANCA-associated vasculitis
    source_type: recommendation_statement
    organization:
      - EULAR
    year: 2022
    publication_year: 2024
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    can_support_claims:
      - AAV_context
      - ANCA_testing_context
      - rheumatology_nephrology_review_context
    cannot_support_claims:
      - CT_only_GPA_diagnosis
      - treatment_recommendation_by_platform
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - claim_mapping

  GPA_THORACIC_MANIFESTATIONS_RADIOGRAPHICS_REVIEW:
    title: Common and Uncommon Manifestations of Wegener Granulomatosis at Chest CT
    source_type: imaging_review
    year: 2012
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    can_support_claims:
      - GPA_thoracic_pattern_awareness
      - cavitating_nodules_airway_GGO_consolidation_context
    cannot_support_claims:
      - GPA_final_diagnosis
      - treatment_recommendation
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - imaging_pattern_claim_mapping
```

---

## 9. Source Review Matrix — Superimposed Events / Drug / Acute Sources

```yaml
superimposed_events_sources:
  Fleischner_2021_DRUG_RELATED_PNEUMONITIS_POSITION_PAPER:
    title: Chest CT Diagnosis and Clinical Management of Drug-related Pneumonitis in Patients Receiving Molecular Targeting Agents and Immune Checkpoint Inhibitors
    source_type: position_paper
    organization:
      - Fleischner Society
    year: 2021
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - drug_toxicity_treatment_related_lung_injury_v1
      - organizing_pneumonia_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    can_support_claims:
      - drug_related_pneumonitis_CT_pattern_context
      - OP_NSIP_HP_DAD_like_pattern_awareness
      - ICI_and_molecular_targeting_agent_pneumonitis_context
    cannot_support_claims:
      - drug_toxicity_from_timing_alone
      - treatment_recommendation_by_platform
      - infection_exclusion
    diagnostic_boundary:
      - position_paper_context_not_automated_diagnosis
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - CT_pattern_claim_mapping
      - treatment_boundary_review

  AE_IPF_REVISED_DEFINITION_AND_REVIEW_SOURCE_CANDIDATE:
    title: Acute exacerbation of idiopathic pulmonary fibrosis revised definition / review source
    source_type: candidate_review
    year: source_review_pending
    source_identity_status: unverified
    full_text_review_status: not_started
    claim_mapping_status: not_mapped
    used_by_modules:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_events_core_blueprint_v1
      - temporal_comparison_methodology_v1
    can_support_claims:
      - none_until_verified
    cannot_support_claims:
      - public_ready_claim
      - AE_definition_claim_until_verified
    public_ready_support: none
    next_action:
      - identify_primary_AE_IPF_definition_source
      - verify_bibliography
      - full_text_review

  ORGANIZING_PNEUMONIA_ERS_REVIEW_2021:
    title: Cryptogenic organizing pneumonia / organizing pneumonia current understanding review
    source_type: peer_reviewed_review
    year: 2021
    source_identity_status: bibliographic_verified
    full_text_review_status: full_text_review_pending
    claim_mapping_status: partial_mapping
    used_by_modules:
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_events_core_blueprint_v1
    can_support_claims:
      - OP_pattern_context
      - secondary_OP_context
      - OP_mimic_awareness
    cannot_support_claims:
      - OP_diagnosis_from_morphology_alone
      - treatment_recommendation_by_platform
    public_ready_support: public_ready_support_after_review
    next_action:
      - full_text_review
      - OP_claim_mapping

  VASCULAR_EDEMA_HEMORRHAGE_SOURCE_CANDIDATES:
    title: Pulmonary edema / PE-infarct / DAH imaging and clinical review sources
    source_type: candidate_source_group
    year: source_review_pending
    source_identity_status: unverified
    full_text_review_status: not_started
    claim_mapping_status: not_mapped
    used_by_modules:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    can_support_claims:
      - none_until_verified
    cannot_support_claims:
      - public_ready_claim
      - high_certainty_mimic_claims_until_verified
    public_ready_support: none
    next_action:
      - identify_best_pulmonary_edema_CT_review
      - identify_best_DAH_review
      - identify_best_PE_infarct_CT_review
      - full_text_review
```

---

## 10. Claim-to-Source Mapping Template

```yaml
claim_to_source_mapping_template:
  claim_id: example_claim_id
  claim_text: exact_or_near_exact_platform_statement
  module_path: docs/path/to/module.md
  source_id: SOURCE_ID
  source_type: guideline_or_review_or_consensus_or_position_paper
  source_scope:
    - diagnostic_framework
    - imaging_pattern_awareness
    - mimic_awareness
    - management_context
    - evidence_limitation
  source_strength:
    - high_for_scope
    - moderate_for_scope
    - low_or_candidate
  boundary_statement:
    - what_this_source_does_not_support
  full_text_review_status: not_started_or_pending_or_reviewed
  public_ready_allowed: false
```

---

## 11. v0.4 Evidence Layer Lock Criteria Draft

```yaml
v0_4_evidence_layer_lock_criteria:
  required_before_public_ready_candidate:
    - every_source_has_source_identity_status
    - every_source_has_full_text_review_status
    - every_source_has_source_type
    - every_source_has_claim_scope
    - every_source_has_diagnostic_boundary
    - every_source_has_public_ready_support_status
    - candidate_sources_are_marked_unverified_or_pending
    - no_module_uses_candidate_source_as_high_certainty_authority
    - every_public_candidate_page_has_claim_to_source_mapping
    - expert_review_required_remains_visible

  current_status:
    evidence_layer: active_development
    public_ready: false
    first_public_page_candidate_allowed: false
    next_required_step:
      - source_review_records_for_core_guidelines
```

---

## 12. Final Evidence Rule

```text
A source does not support a page.

A source supports a specific claim, inside a specific scope, with a specific boundary.

If the scope is unclear, the claim must remain draft-only.
```