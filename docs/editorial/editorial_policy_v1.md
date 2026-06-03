# Editorial Policy — v1

## Document Metadata

```yaml
id: editorial_policy_v1
title: Editorial Policy
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: editorial_policy
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This document defines the editorial policy for the ILD Reasoning Platform.

The platform is designed to support structured educational reasoning in interstitial lung disease.

It must remain:

- clinically cautious,
- guideline-aware,
- uncertainty-preserving,
- evidence-traceable,
- free from diagnostic overreach,
- and safe for global educational use.

This document applies to:

- Pattern Atlas pages
- Disease Atlas pages
- Gray Zone Reasoning Maps
- Triage Maps
- Missing Piece Engine modules
- Guideline summaries
- UI text
- future case simulations

---

## 1. Core Editorial Principle

The platform must teach reasoning, not deliver conclusions.

```text
Do not tell the user what the patient has.
Show the user how to think through what remains possible.
```

Every page should reinforce:

```text
Diagnosing ILD is not about finding the right answer.
It is about asking the right next question — and knowing when you don’t have enough information yet.
```

---

## 2. Diagnostic Authority Boundary

```yaml
diagnostic_authority_boundary:
  platform_must_not:
    - diagnose_individual_patients
    - classify_individual_cases_as_final_diagnoses
    - recommend_treatment
    - replace_clinician_judgment
    - replace_multidisciplinary_discussion
    - replace_full_guideline_review
    - provide individual risk prediction
    - provide disease probability for a specific patient

  platform_may:
    - describe patterns
    - describe disease contexts
    - show differential reasoning
    - identify missing data
    - show pitfalls
    - link guideline scope
    - preserve uncertainty
    - recommend multidisciplinary review when appropriate
```

---

## 3. Preferred Language

Use reasoning-support language.

```yaml
preferred_language:
  - supports
  - weakens
  - raises concern for
  - suggests
  - remains possible
  - should prompt review
  - requires clinical context
  - requires multidisciplinary discussion
  - missing information
  - gray zone
  - context-dependent
  - cannot conclude
```

Examples:

```text
This finding supports a UIP-like pattern.
Fibrotic HP remains possible.
Exposure history is missing.
MDD may be needed.
```

---

## 4. Forbidden Language

Avoid diagnostic closure language.

```yaml
forbidden_language:
  - confirms
  - proves
  - rules out
  - rules in
  - final diagnosis
  - confirmed diagnosis
  - diagnose now
  - treatment recommendation
  - patient has
  - disease probability for this patient
  - certainty score for individual patient
```

Bad:

```text
This patient has IPF.
This confirms fibrotic HP.
Start treatment.
```

Better:

```text
The pattern is UIP-like, but IPF is not established by imaging alone.
Fibrotic HP remains possible if exposure or airway-centered clues are present.
Treatment decisions require clinical judgment and guideline review.
```

---

## 5. Pattern vs Disease Rule

Patterns must never be treated as final diseases.

```yaml
pattern_vs_disease_rule:
  UIP:
    allowed: UIP pattern supports an IPF pathway in the correct clinical context.
    forbidden: UIP means IPF.

  NSIP:
    allowed: NSIP pattern should prompt secondary-cause review, especially CTD-ILD.
    forbidden: NSIP means idiopathic NSIP.

  Fibrotic_HP:
    allowed: Fibrotic HP reasoning requires exposure, HRCT, BAL/pathology when relevant, and MDD integration.
    forbidden: Air trapping alone diagnoses HP.
```

---

## 6. Evidence Hierarchy

```yaml
evidence_hierarchy:
  level_1:
    label: Official guideline or society statement
    examples:
      - ATS
      - ERS
      - JRS
      - ALAT
      - ACR
      - CHEST

  level_2:
    label: Peer-reviewed review or consensus article
    examples:
      - major review articles
      - expert consensus statements
      - society white papers

  level_3:
    label: Primary research study
    examples:
      - cohort studies
      - diagnostic accuracy studies
      - imaging-pathology correlation studies

  level_4:
    label: Educational reasoning structure
    examples:
      - platform-created reasoning maps
      - crosslink logic
      - Missing Piece Engine prompts
```

### Evidence Rule

Platform-created reasoning structures must be labeled as educational reasoning unless directly supported by specific guideline language.

---

## 7. Guideline Use Policy

```yaml
guideline_use_policy:
  required:
    - cite_guideline_scope
    - separate_diagnosis_guidelines_from_treatment_guidelines
    - mark_full_source_review_required_when_needed
    - avoid extending guideline beyond its scope
    - record which platform modules each guideline supports

  forbidden:
    - using_treatment_guideline_as_diagnostic_authority
    - using_diagnostic_guideline_as_treatment_authority
    - merging_different_guidelines_without_scope_label
    - claiming guideline compliance without full source review
```

---

## 8. Gray Zone Policy

Gray zones must be explicit, not hidden.

```yaml
gray_zone_policy:
  every_gray_zone_page_must_show:
    - what supports pathway A
    - what supports pathway B
    - where the two overlap
    - which features are misleading
    - what information is missing
    - when uncertainty should be preserved
    - when MDD may be needed
```

Required phrase:

```text
Do not force the label.
```

---

## 9. Missing Data Policy

The platform must treat missing data as a first-class reasoning object.

```yaml
missing_data_policy:
  required_missing_data_categories:
    - prior_CT
    - expiratory_HRCT
    - exposure_history
    - autoimmune_screen
    - clinical_CTD_review
    - medication_history
    - occupational_history
    - PFT_trend
    - BAL_when_relevant
    - MDD_review

  rule:
    - Missing data should be visible before any diagnostic label is strengthened.
```

---

## 10. Temporal Reasoning Policy

ILD should not be represented as static when longitudinal data matter.

```yaml
temporal_policy:
  required_temporal_states:
    - progression
    - stabilization
    - partial_improvement_or_regression
    - unexpectedly_fast_worsening

  safety_rule:
    - A single HRCT snapshot must not be treated as proof of progression.

  technical_caution:
    - slice_thickness
    - inspiratory_effort
    - scanner_protocol
    - reconstruction_kernel
    - comparison_interval
```

---

## 11. Superimposed Event Policy

New findings on fibrotic ILD must not automatically be labeled as baseline disease progression.

```yaml
superimposed_event_policy:
  red_flags:
    - new_ground_glass
    - new_consolidation
    - new_nodule_or_mass
    - rapid_diffuse_worsening

  must_consider:
    - infection
    - acute_exacerbation
    - pulmonary_edema
    - pulmonary_embolism
    - drug_toxicity
    - aspiration
    - malignancy
    - exposure_rechallenge_when_relevant
```

---

## 12. Patient Communication Boundary

The MVP is clinician-facing.

Patient-facing content should not be added casually.

```yaml
patient_communication_policy:
  current_scope:
    - clinician_facing
    - trainee_facing
    - educational_reasoning_support

  future_scope_requires:
    - plain_language_review
    - psychological_safety_review
    - prognosis_language_review
    - transplant_discussion_sensitivity_review
    - explicit_patient_disclaimer
```

---

## 13. Editorial Review States

```yaml
editorial_review_states:
  blueprint_draft:
    meaning: Structure exists but source review and clinical review are incomplete.

  evidence_review_pending:
    meaning: Content requires source verification.

  clinically_reviewed:
    meaning: Reviewed by qualified domain expert.

  public_ready:
    meaning: Source-reviewed, clinically reviewed, safety-reviewed, and UI-reviewed.

  archived:
    meaning: Superseded or no longer maintained.
```

---

## 14. Public Release Rule

No page should be marked public-ready unless:

```yaml
public_release_requirements:
  - safety_boundary_present
  - no_forbidden_diagnostic_language
  - evidence_sources_verified
  - guideline_scope_declared
  - gray_zones_visible
  - missing_data_visible
  - MDD_trigger_present_when_relevant
  - clinical_review_completed
```

---

## 15. Content Page Ending Rule

Every major content page must end with:

```text
What do we still not know?
```

Expanded form:

```text
Do not force the label.

Ask:
1. What supports the leading pathway?
2. What weakens it?
3. What competing explanation remains possible?
4. What clinical, laboratory, exposure, or temporal data are missing?
5. Is there a red flag or superimposed event?
6. Is MDD needed?
7. What do we still not know?
```

---

## 16. Final Editorial Rule

A valid ILD Reasoning Platform page must make the user better at reasoning without making the platform appear to diagnose.

```text
Reasoning clarity is the product.
Diagnostic authority remains with clinicians and multidisciplinary review.
```