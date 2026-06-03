# Guideline Registry — v1

## Document Metadata

```yaml
id: evidence_guideline_registry_v1
title: Guideline Registry
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: evidence_registry
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This registry defines the guideline and evidence backbone of the ILD Reasoning Platform.

It does not replace full guideline review.

It exists to:

- identify which guidelines support each platform module,
- prevent unsupported claims,
- separate guideline-backed statements from educational reasoning,
- flag low-certainty or context-dependent areas,
- and make evidence traceable across pattern pages, reasoning maps, and future UI components.

---

## 1. Evidence Safety Rule

```yaml
evidence_safety_rule:
  platform_must_not:
    - present_guideline_summary_as_full_guideline
    - imply_individual_patient_diagnosis
    - imply_treatment_recommendation_without_clinician_context
    - hide_uncertainty_or_low_certainty_evidence
    - merge_different_guidelines_without_labeling_scope

  platform_must:
    - cite_primary_guidelines_when_possible
    - separate_diagnosis_guidelines_from_treatment_guidelines
    - show_scope_limits
    - show_confidence_or_consensus_strength
    - mark_when_full_text_review_is_required
```

---

## 2. Core Guideline Sources

```yaml
core_guideline_sources:

  ATS_ERS_JRS_ALAT_2022_IPF_PPF:
    title: Idiopathic Pulmonary Fibrosis (an Update) and Progressive Pulmonary Fibrosis in Adults
    organization:
      - American Thoracic Society
      - European Respiratory Society
      - Japanese Respiratory Society
      - Asociación Latinoamericana de Tórax
    year: 2022
    scope:
      - IPF update
      - Progressive pulmonary fibrosis in adults
      - HRCT pattern categories
      - PPF framework
    platform_use:
      - UIP pattern registry
      - fibrotic ILD triage map
      - temporal progression reasoning
      - IPF vs non-IPF caution
    evidence_role: primary_guideline
    full_text_review_required: true

  ATS_JRS_ALAT_2020_HP_DIAGNOSIS:
    title: Diagnosis of Hypersensitivity Pneumonitis in Adults
    organization:
      - American Thoracic Society
      - Japanese Respiratory Society
      - Asociación Latinoamericana de Tórax
    year: 2020
    scope:
      - nonfibrotic HP diagnosis
      - fibrotic HP diagnosis
      - exposure assessment
      - HRCT pattern assessment
      - BAL lymphocytosis
      - pathology and MDD integration
    platform_use:
      - fibrotic HP pattern registry
      - UIP vs fibrotic HP gray zone
      - NSIP vs fibrotic HP gray zone
      - exposure reasoning layer
    evidence_role: primary_guideline
    full_text_review_required: true

  ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING:
    title: Screening and Monitoring of Interstitial Lung Disease in People with Systemic Autoimmune Rheumatic Diseases
    organization:
      - American College of Rheumatology
      - American College of Chest Physicians
    year: 2023
    publication_year: 2024
    scope:
      - systemic autoimmune rheumatic disease-associated ILD
      - screening
      - monitoring
      - HRCT and PFT surveillance context
    platform_use:
      - NSIP pattern registry
      - CTD-ILD reasoning
      - Missing Piece Engine
      - treatment response and monitoring prompts
    evidence_role: primary_guideline
    full_text_review_required: true

  ACR_CHEST_2023_SARD_ILD_TREATMENT:
    title: Treatment of Interstitial Lung Disease in Adults with Systemic Autoimmune Rheumatic Diseases
    organization:
      - American College of Rheumatology
      - American College of Chest Physicians
    year: 2023
    publication_year: 2024
    scope:
      - treatment of SARD-ILD
      - systemic sclerosis
      - idiopathic inflammatory myopathy
      - rheumatoid arthritis
      - mixed connective tissue disease
      - Sjogren disease
    platform_use:
      - treatment response reasoning
      - CTD-ILD context pages
      - Decision Core future modules
    evidence_role: primary_guideline
    full_text_review_required: true

  ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION:
    title: Diagnosis and Detection of Sarcoidosis
    organization:
      - American Thoracic Society
    year: 2020
    scope:
      - sarcoidosis diagnosis
      - compatible clinical presentation
      - nonnecrotizing granulomatous inflammation
      - exclusion of alternative granulomatous disease
      - extrapulmonary screening considerations
    platform_use:
      - granulomatous ILD future module
      - sarcoidosis pattern registry
      - sarcoidosis vs HP vs infection gray zones
    evidence_role: primary_guideline
    full_text_review_required: true

  ERS_2021_SARCOIDOSIS_TREATMENT:
    title: ERS Clinical Practice Guidelines on Treatment of Sarcoidosis
    organization:
      - European Respiratory Society
    year: 2021
    scope:
      - sarcoidosis treatment principles
      - organ involvement
      - quality of life and organ function considerations
    platform_use:
      - sarcoidosis disease page
      - treatment principle disclaimer layer
      - future patient communication module
    evidence_role: primary_guideline
    full_text_review_required: true
```

---

## 3. Guideline Scope Separation

```yaml
scope_separation:
  diagnosis_guidelines:
    - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF

  treatment_guidelines:
    - ACR_CHEST_2023_SARD_ILD_TREATMENT
    - ERS_2021_SARCOIDOSIS_TREATMENT

  screening_monitoring_guidelines:
    - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING

  progression_frameworks:
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF

  platform_rule:
    - Do not use treatment guidelines as diagnostic authority.
    - Do not use diagnostic guidelines as treatment recommendation authority.
    - Do not use pattern recognition as disease diagnosis.
```

---

## 4. Pattern-to-Guideline Mapping

```yaml
pattern_to_guideline_mapping:
  UIP:
    primary:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
    secondary:
      - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    reasoning_note:
      - UIP pattern supports IPF only in the correct clinical context after known causes are excluded.

  NSIP:
    primary:
      - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
      - ACR_CHEST_2023_SARD_ILD_TREATMENT
    secondary:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    reasoning_note:
      - NSIP pattern should trigger CTD-ILD, drug-related ILD, HP mimic, and overlap review.

  Fibrotic_HP:
    primary:
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    secondary:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
      - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
    reasoning_note:
      - Fibrotic HP diagnosis requires integration of exposure, HRCT, BAL/pathology when appropriate, and MDD.

  Sarcoidosis:
    primary:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - ERS_2021_SARCOIDOSIS_TREATMENT
    secondary:
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    reasoning_note:
      - Granulomatous ILD reasoning must exclude infection, HP, berylliosis, GLILD, malignancy, and other mimics.
```

---

## 5. Reasoning Map-to-Guideline Mapping

```yaml
reasoning_map_to_guideline_mapping:
  uip_vs_nsip_gray_zone_v1:
    primary_sources:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
      - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
    support_type:
      - HRCT_pattern_categories
      - CTD_ILD_context
      - progression_framework

  uip_vs_fibrotic_hp_gray_zone_v1:
    primary_sources:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    support_type:
      - UIP_pattern_reasoning
      - HP_exposure_HRCT_BAL_MDD_reasoning

  nsip_vs_fibrotic_hp_gray_zone_v1:
    primary_sources:
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
      - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
    support_type:
      - HP_airway_centered_reasoning
      - CTD_NSIP_context

  fibrotic_ild_triage_map_v1:
    primary_sources:
      - ATS_ERS_JRS_ALAT_2022_IPF_PPF
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
      - ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
    support_type:
      - fibrotic_pattern_triage
      - missing_piece_engine
      - temporal_reasoning
      - MDD_escalation
```

---

## 6. Evidence Confidence Labels

```yaml
evidence_confidence_labels:
  guideline_backed:
    definition: Supported directly by a major guideline or official society statement.
    UI_label: Guideline-backed

  consensus_backed:
    definition: Supported by broad expert consensus but not always based on high-certainty evidence.
    UI_label: Consensus-supported

  context_dependent:
    definition: Valid only in specific clinical, imaging, or temporal context.
    UI_label: Context-dependent

  gray_zone:
    definition: Known area of overlap or diagnostic uncertainty.
    UI_label: Gray zone

  educational_reasoning:
    definition: Platform-derived reasoning structure that organizes existing knowledge but is not itself a guideline.
    UI_label: Educational reasoning

  needs_full_source_review:
    definition: Requires direct review of full guideline/article before final publication.
    UI_label: Full source review required
```

---

## 7. Source Review Workflow

```yaml
source_review_workflow:
  step_1_identify_primary_source:
    action: Find official society source or peer-reviewed full text.

  step_2_extract_scope:
    action: Record what the source actually addresses.

  step_3_extract_recommendation_type:
    action: Diagnosis, treatment, screening, monitoring, progression, or terminology.

  step_4_assign_platform_modules:
    action: Link source only to relevant platform modules.

  step_5_mark_uncertainty:
    action: Add confidence label and context limitations.

  step_6_require_human_review:
    action: Medical content must be reviewed before public release.

  step_7_prevent_scope_creep:
    action: Do not allow one guideline to authorize unrelated claims.
```

---

## 8. MVP Evidence Tasks

```yaml
mvp_evidence_tasks:
  immediate:
    - verify_full_reference_details_for_ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - verify_full_reference_details_for_ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    - verify_full_reference_details_for_ACR_CHEST_2023_SARD_ILD_SCREENING_MONITORING
    - verify_full_reference_details_for_ACR_CHEST_2023_SARD_ILD_TREATMENT

  next:
    - add_ATS_2020_sarcoidosis_diagnosis_detection
    - add_ERS_2021_sarcoidosis_treatment
    - add_Fleischner_IPF_white_paper_if_available_and_relevant
    - add_CHEST_HP_diagnosis_evaluation_guideline_if_needed
    - add_BTS_sarcoidosis_statement_if_relevant

  later:
    - create_guideline_summary_cards
    - create_guideline_conflict_matrix
    - create_evidence_badges_for_each_page
```

---

## 9. Final Registry Rule

Every evidence-linked platform page must end with:

```text
This page supports reasoning, not diagnosis.

Before applying to a patient, ask:
1. Which guideline actually applies?
2. What is the scope of that guideline?
3. What evidence is missing?
4. Is this a gray zone?
5. Is MDD or specialist review needed?
6. What do we still not know?
```
---

## 10. Granulomatous ILD / Sarcoidosis Module Update

```yaml
granulomatous_ild_module_sources:
  ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION:
    title: Diagnosis and Detection of Sarcoidosis
    organization:
      - American Thoracic Society
    year: 2020
    publication:
      journal: American Journal of Respiratory and Critical Care Medicine
      volume: 201
      issue: 8
      pages: e26-e51
    scope:
      - sarcoidosis diagnosis
      - compatible clinical presentation
      - nonnecrotizing granulomatous inflammation
      - exclusion of alternative granulomatous disease
      - detection of selected extrapulmonary disease
    platform_use:
      - sarcoidosis_pattern_gold_standard_v1
      - granulomatous_ild_reasoning_map_v1
      - granulomatous_crosslink_registry_v1
      - source_review_protocol_v1
    evidence_role: primary_diagnostic_guideline
    full_text_review_required: true
    diagnostic_boundary:
      - supports_sarcoidosis_reasoning_framework
      - does_not_allow_imaging_only_diagnosis
      - requires_alternative_granulomatous_causes_to_remain_visible

  BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT:
    title: BTS Clinical Statement on Pulmonary Sarcoidosis
    organization:
      - British Thoracic Society
    year: 2021
    publication:
      journal: Thorax
      volume: 76
      issue: 1
      pages: 4-20
    scope:
      - pulmonary sarcoidosis diagnosis
      - evaluation
      - management context
      - clinical practice points
    platform_use:
      - sarcoidosis_pattern_gold_standard_v1
      - granulomatous_ild_reasoning_map_v1
      - granulomatous_crosslink_registry_v1
    evidence_role: clinical_statement
    full_text_review_required: true
    diagnostic_boundary:
      - supports_pulmonary_sarcoidosis_context
      - does_not_replace_ATS_diagnostic_framework
      - does_not_remove_need_for_mimic_review

  ERS_2021_SARCOIDOSIS_TREATMENT:
    title: ERS Clinical Practice Guidelines on Treatment of Sarcoidosis
    organization:
      - European Respiratory Society
    year: 2021
    publication:
      journal: European Respiratory Journal
      volume: 58
      article: 2004079
    scope:
      - treatment of sarcoidosis
      - organ involvement
      - morbidity and mortality risk
      - quality of life impact
      - treatment toxicity consideration
    platform_use:
      - future_sarcoidosis_treatment_response_reasoning
      - patient_communication_future_module
      - guideline_scope_warning
    evidence_role: treatment_guideline
    full_text_review_required: true
    diagnostic_boundary:
      - must_not_be_used_as_diagnostic_authority
      - supports_treatment_context_only
```

---

## 11. Granulomatous Module-to-Guideline Mapping

```yaml
granulomatous_module_to_guideline_mapping:
  sarcoidosis_pattern_gold_standard_v1:
    primary_sources:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    secondary_sources:
      - ERS_2021_SARCOIDOSIS_TREATMENT
    scope_note:
      - ATS_2020_supports_diagnostic_framework
      - BTS_2021_supports_pulmonary_sarcoidosis_context
      - ERS_2021_is_treatment_scope_only

  granulomatous_ild_reasoning_map_v1:
    primary_sources:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - ATS_JRS_ALAT_2020_HP_DIAGNOSIS
    secondary_sources:
      - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    future_sources_needed:
      - GLILD_consensus_or_review_source
      - berylliosis_occupational_granulomatous_disease_source
      - granulomatous_infection_review_source
      - GPA_vasculitis_source
    scope_note:
      - sarcoidosis_reasoning_requires_mimic_review
      - HP_reasoning_requires_exposure_HRCT_BAL_MDD_context
      - infection_malignancy_GLILD_occupational_mimics_need_dedicated_sources_before_public_release

  granulomatous_crosslink_registry_v1:
    primary_sources:
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
      - BTS_2021_PULMONARY_SARCOIDOSIS_CLINICAL_STATEMENT
    scope_note:
      - navigation_contract_only
      - does_not_create_diagnostic_authority
```

---

## 12. Granulomatous Evidence Safety Rule

```yaml
granulomatous_evidence_safety_rule:
  platform_must_not:
    - diagnose_sarcoidosis_from_imaging_alone
    - use_ERS_treatment_guideline_as_diagnostic_authority
    - ignore_granulomatous_infection
    - ignore_occupational_mimics
    - ignore_GLILD_or_immune_deficiency_context
    - ignore_malignancy_or_sarcoid_like_reaction
    - hide_need_for_full_source_review

  platform_must:
    - show_ATS_diagnostic_framework
    - keep_mimics_visible
    - label_BTS_as_clinical_statement_context
    - label_ERS_as_treatment_scope_only
    - preserve_uncertainty
    - trigger_MDD_when_pattern_and_context_conflict
```
---

## 13. GLILD / Immune Deficiency Granulomatous ILD Evidence Update

```yaml
glild_module_sources:
  BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT:
    title: BLF/UKPIN Consensus Statement on the Definition, Diagnosis and Management of Granulomatous-Lymphocytic Interstitial Lung Disease in Common Variable Immunodeficiency Disorders
    organization:
      - British Lung Foundation
      - United Kingdom Primary Immunodeficiency Network
    year: 2017
    publication:
      journal: Journal of Allergy and Clinical Immunology: In Practice
      volume: 5
      issue: 4
      pages: 938-945
    scope:
      - GLILD definition
      - GLILD diagnosis framework
      - GLILD management consensus
      - CVID-associated granulomatous-lymphocytic ILD
    platform_use:
      - sarcoidosis_vs_glild_gray_zone_v1
      - granulomatous_ild_reasoning_map_v1
      - granulomatous_crosslink_registry_v1
      - future_glild_pattern_gold_standard_v1
    evidence_role: consensus_statement
    full_text_review_required: true
    diagnostic_boundary:
      - supports_GLILD_context_in_CVID
      - does_not_create_imaging_only_diagnostic_authority
      - infection_and_lymphoma_review_remain_required

  CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023:
    title: Diagnostic testing for interstitial lung disease in common variable immunodeficiency: a systematic review
    year: 2023
    publication:
      journal: Frontiers in Immunology
    scope:
      - diagnostic tests for CVID-associated ILD
      - HRCT use
      - pulmonary function testing
      - bronchoalveolar lavage
      - biopsy context
      - evidence limitations
    platform_use:
      - sarcoidosis_vs_glild_gray_zone_v1
      - future_glild_pattern_gold_standard_v1
      - source_review_protocol_v1
    evidence_role: systematic_review
    full_text_review_required: true
    diagnostic_boundary:
      - highlights_lack_of_evidence_based_guidelines
      - supports_cautious_language
      - supports_need_for_MDD_and_source_review

  GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024:
    title: Approach to diagnosing and managing granulomatous-lymphocytic interstitial lung disease
    year: 2024
    publication:
      journal: eClinicalMedicine
    scope:
      - GLILD diagnostic approach
      - clinical_radiologic_pathologic_integration
      - multidisciplinary discussion
      - management controversies
      - evidence limitations
    platform_use:
      - sarcoidosis_vs_glild_gray_zone_v1
      - future_glild_pattern_gold_standard_v1
      - MDD_core_future_module
    evidence_role: peer_reviewed_review
    full_text_review_required: true
    diagnostic_boundary:
      - supports_practical_reasoning_framework
      - does_not_replace_consensus_or_expert_review
      - emphasizes_MDD_and_limited_evidence
```

---

## 14. GLILD Module-to-Evidence Mapping

```yaml
glild_module_to_evidence_mapping:
  sarcoidosis_vs_glild_gray_zone_v1:
    primary_sources:
      - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT
      - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    secondary_sources:
      - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
      - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024
    scope_note:
      - Sarcoidosis reasoning uses ATS diagnostic framework.
      - GLILD reasoning uses CVID/immune-deficiency context and BLF/UKPIN consensus.
      - CVID-ILD diagnostic evidence remains limited and must be labeled cautiously.

  granulomatous_ild_reasoning_map_v1:
    added_sources:
      - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT
      - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
      - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024
    scope_note:
      - Immune deficiency context must route to GLILD review.
      - Infection and lymphoma/malignancy must remain visible in GLILD-like cases.

  future_glild_pattern_gold_standard_v1:
    required_sources:
      - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT
      - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
      - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024
    required_caution:
      - evidence_base_less_mature_than_IPF_HP_sarcoidosis_guidelines
      - public_ready_status_requires_expert_review
```

---

## 15. GLILD Evidence Safety Rule

```yaml
glild_evidence_safety_rule:
  platform_must_not:
    - diagnose_GLILD_from_imaging_alone
    - diagnose_sarcoidosis_without_reviewing_CVID_context
    - ignore_recurrent_infections
    - ignore_hypogammaglobulinemia
    - ignore_infection_or_lymphoma_mimics
    - present_GLILD_review_opinion_as_high_certainty_guideline
    - hide_limited_evidence_base

  platform_must:
    - label_BLF_UKPIN_as_consensus_statement
    - label_2023_CVID_ILD_paper_as_systematic_review
    - label_2024_GLILD_paper_as_peer_reviewed_review
    - keep_MDD_and_immunology_review_visible
    - preserve_uncertainty_when_CVID_or_immunoglobulin_status_is_unknown
    - require_full_source_review_before_public_release
```