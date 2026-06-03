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