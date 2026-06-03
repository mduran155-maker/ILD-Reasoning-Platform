# Source Review Protocol — v1

## Document Metadata

```yaml
id: editorial_source_review_protocol_v1
title: Source Review Protocol
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: editorial_protocol
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This protocol defines how sources should be reviewed before they are used in the ILD Reasoning Platform.

The goal is to prevent:

- unsupported claims,
- guideline overreach,
- outdated information,
- false certainty,
- treatment advice leakage,
- citation drift,
- and mixing educational reasoning with guideline authority.

---

## 1. Source Priority

```yaml
source_priority:
  level_1:
    label: official_guideline_or_society_statement
    preferred_for:
      - diagnostic_frameworks
      - terminology
      - HRCT categories
      - screening_or_monitoring_guidance
      - treatment_scope_boundaries
    examples:
      - ATS
      - ERS
      - JRS
      - ALAT
      - ACR
      - CHEST

  level_2:
    label: peer_reviewed_consensus_or_review
    preferred_for:
      - background_explanation
      - clinical_context
      - imaging_overview
      - disease_subtypes
      - gray_zone_discussion

  level_3:
    label: primary_research
    preferred_for:
      - specific data
      - cohort observations
      - diagnostic performance
      - outcome associations

  level_4:
    label: platform_educational_reasoning
    preferred_for:
      - navigation logic
      - Missing Piece Engine prompts
      - gray-zone maps
      - UI reasoning flow
```

---

## 2. Required Source Extraction Fields

Every source used in the platform should be extracted into this structure:

```yaml
source_review_record:
  source_id: string
  title: string
  authors_or_organization: string
  year: string
  publication_type: enum
  guideline_or_article_scope: list[string]
  relevant_platform_modules: list[string]
  key_supported_claims: list[string]
  limitations: list[string]
  evidence_certainty_or_strength: optional[string]
  full_text_review_status: enum
  citation_status: enum
```

Allowed values:

```yaml
publication_type:
  - official_guideline
  - official_statement
  - consensus_statement
  - peer_reviewed_review
  - systematic_review
  - primary_research
  - educational_resource

full_text_review_status:
  - not_started
  - abstract_only
  - full_text_review_pending
  - full_text_reviewed
  - expert_reviewed

citation_status:
  - candidate
  - accepted_for_blueprint
  - needs_verification
  - retired
```

---

## 3. Scope Separation Rule

A source can only support claims within its actual scope.

```yaml
scope_separation_rule:
  diagnosis_guideline:
    may_support:
      - diagnostic framework
      - diagnostic criteria
      - suggested evaluation components
      - uncertainty statements
    must_not_support:
      - treatment recommendation unless explicitly included

  treatment_guideline:
    may_support:
      - treatment decision context
      - treatment response monitoring
      - organ-specific treatment considerations
    must_not_support:
      - diagnosis claim
      - pattern classification claim

  imaging_review:
    may_support:
      - imaging features
      - mimics
      - pattern descriptions
    must_not_support:
      - final clinical diagnosis without context

  platform_reasoning_map:
    may_support:
      - educational navigation
      - question prompts
      - gray-zone structure
    must_not_support:
      - guideline authority
      - individual patient diagnosis
```

---

## 4. Claim Classification

Every claim in a public page should be classified.

```yaml
claim_classification:
  guideline_backed:
    definition: directly supported by official guideline or society statement

  evidence_supported:
    definition: supported by peer-reviewed literature but not necessarily guideline-level

  consensus_supported:
    definition: broadly accepted expert framing

  educational_reasoning:
    definition: platform-created reasoning structure built from accepted concepts

  context_dependent:
    definition: valid only under specific clinical/imaging conditions

  gray_zone:
    definition: explicitly uncertain or overlapping area
```

---

## 5. Claim Wording Rules

```yaml
allowed_claim_formats:
  guideline_backed:
    - "The guideline describes..."
    - "The guideline framework includes..."
    - "This source supports considering..."

  evidence_supported:
    - "Studies/reviews describe..."
    - "Reported associations include..."
    - "This has been described in..."

  educational_reasoning:
    - "This platform organizes the reasoning as..."
    - "A useful question is..."
    - "This should prompt review of..."

  gray_zone:
    - "This remains a gray zone."
    - "The available information is insufficient."
    - "Multiple pathways remain possible."
```

Forbidden formats:

```yaml
forbidden_claim_formats:
  - "This confirms..."
  - "This proves..."
  - "The patient has..."
  - "This rules out..."
  - "Treatment should be started..."
  - "The diagnosis is..."
```

---

## 6. Guideline Review Workflow

```yaml
guideline_review_workflow:
  step_1_identify_guideline:
    action: Find official publication or official society implementation page.

  step_2_record_scope:
    action: Identify whether the guideline is diagnostic, treatment, screening, monitoring, or mixed.

  step_3_extract_relevant_claims:
    action: Extract only claims relevant to the platform module.

  step_4_mark_limitations:
    action: Note uncertainty, conditional recommendations, evidence limitations, or population limits.

  step_5_assign_platform_modules:
    action: Link the guideline only to relevant pages.

  step_6_prevent_overreach:
    action: Ensure the guideline is not used outside its scope.

  step_7_require_clinical_review:
    action: Mark public release as blocked until medical expert review is complete.
```

---

## 7. Sarcoidosis Example Rule

Sarcoidosis content must be especially careful.

```yaml
sarcoidosis_source_rule:
  diagnosis_source:
    preferred_source: ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    supported_framework:
      - compatible_clinical_presentation
      - nonnecrotizing_granulomatous_inflammation
      - exclusion_of_alternative_granulomatous_disease
    safety_note:
      - sarcoidosis_diagnosis_is_not_fully_secure
      - infection_and_other_granulomatous_mimics_must_be_excluded

  treatment_source:
    preferred_source: ERS_2021_SARCOIDOSIS_TREATMENT
    supported_framework:
      - organ_involvement
      - risk_of_morbidity_or_mortality
      - quality_of_life_impact
      - treatment_toxicity_consideration
    safety_note:
      - treatment_guideline_must_not_be_used_as_diagnostic_authority
```

---

## 8. Citation Drift Prevention

```yaml
citation_drift_prevention:
  required:
    - claim_has_source_id
    - source_scope_matches_claim
    - source_year_recorded
    - full_text_review_status_recorded
    - page_last_reviewed_date_recorded

  forbidden:
    - citing_guideline_for_unrelated_claim
    - copying_source_language_without_review
    - using_abstract_only_as_full_guideline_summary
    - hiding_low_certainty_evidence
```

---

## 9. Public Release Gate

A content page cannot be marked `public_ready` unless:

```yaml
public_release_gate:
  required:
    - all_major_claims_have_source_ids
    - guideline_scope_is_declared
    - forbidden_language_absent
    - gray_zones_visible
    - missing_data_visible
    - MDD_prompt_present_when_relevant
    - source_review_completed
    - clinical_review_completed
```

---

## 10. Final Source Review Rule

Every source-backed page must answer:

```text
1. What source supports this claim?
2. What is the scope of that source?
3. Is the claim diagnostic, treatment-related, monitoring-related, or educational?
4. Is the evidence strong, conditional, context-dependent, or gray-zone?
5. Is full-text review complete?
6. What do we still not know?
```