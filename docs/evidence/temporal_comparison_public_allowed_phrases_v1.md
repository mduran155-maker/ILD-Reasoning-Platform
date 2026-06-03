# Temporal Comparison Public Allowed Phrases — v1

## Document Metadata

```yaml
id: evidence_temporal_comparison_public_allowed_phrases_v1
title: Temporal Comparison Public Allowed Phrases
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: public_language_safety_draft
diagnostic_authority: none
module_version: v0.4
linked_claim_map:
  - docs/evidence/temporal_comparison_claim_map_v1.md
linked_page_candidate:
  - docs/reasoning/temporal_comparison_methodology_v1.md
last_updated: draft
```

---

## 0. Purpose

This document defines draft public-facing language boundaries for the Temporal Comparison Methodology page.

It separates:

- allowed cautious phrases,
- conditional phrases,
- blocked phrases,
- required uncertainty language,
- and claim-to-source dependency notes.

This document does not make the Temporal Comparison Methodology page public-ready.

It prepares the page for future full-text review, expert review, and public-candidate evaluation.

---

## 1. Current Public Status

```yaml
current_public_status:
  page: temporal_comparison_methodology_v1
  public_ready: false
  public_candidate: false
  allowed_for_public_release_now: false

  reason:
    - full_text_review_pending
    - expert_review_not_started
    - public_phrase_set_is_draft_only
    - claim_map_is_draft_only
    - some_supporting_sources_are_candidate_or_not_fully_reviewed
```

---

## 2. Core Public Language Principle

```yaml
core_public_language_principle:
  statement: >
    Public-facing language must teach temporal reasoning without diagnosing, classifying, or recommending treatment.

  platform_must:
    - use_reasoning_language
    - preserve_uncertainty
    - identify_missing_data
    - separate_observation_from_interpretation
    - separate_structural_fibrosis_from_reversible_opacity
    - avoid_patient_specific_diagnostic_claims
    - avoid_treatment_or_followup_recommendations

  platform_must_not:
    - say_this_patient_has_progression
    - say_this_is_acute_exacerbation
    - say_this_is_infection
    - say_this_is_cancer
    - say_this_is_drug_toxicity
    - recommend_CT_interval
    - recommend_BAL_biopsy_treatment_or_medication_change
    - replace_clinician_or_MDD_judgment
```

---

## 3. Allowed Phrase Set — Prior CT / Longitudinal Context

```yaml
allowed_phrases_prior_CT:
  safe_phrases:
    - "Prior imaging is often essential for interpreting whether an abnormality is new, stable, improving, or progressive."
    - "A single CT examination can describe current findings, but it cannot reliably establish temporal behavior by itself."
    - "When prior CT is unavailable, temporal certainty should remain limited."
    - "Comparison with earlier imaging can help separate chronic baseline ILD from a new superimposed process."

  conditional_phrases:
    - "If comparable prior CT is available, the first step is to identify what has changed."
    - "If no prior imaging exists, the page should frame the finding as current-pattern reasoning rather than progression or regression."

  blocked_phrases:
    - "This CT proves progression."
    - "This CT proves stability."
    - "This CT proves regression."
    - "No prior CT is needed to determine disease behavior."
```

---

## 4. Allowed Phrase Set — Structural Fibrosis vs Reversible Opacity

```yaml
allowed_phrases_structural_vs_reversible:
  safe_phrases:
    - "Temporal comparison should distinguish structural fibrotic change from potentially reversible airspace opacity."
    - "Increasing reticulation, traction bronchiectasis, honeycombing, architectural distortion, or volume loss may support structural fibrotic worsening when interpreted in context."
    - "New ground-glass opacity or consolidation may reflect a superimposed process rather than fibrosis progression."
    - "Improvement in ground-glass opacity or consolidation should not automatically be interpreted as reversal of established fibrosis."

  conditional_phrases:
    - "If new ground-glass opacity appears without clear structural fibrotic worsening, infection, edema, organizing pneumonia, drug toxicity, hemorrhage, acute exacerbation, and other superimposed processes may need consideration."
    - "If structural fibrotic features increase on comparable imaging, progression becomes a stronger reasoning pathway, but superimposed opacity should still be assessed separately."

  blocked_phrases:
    - "Ground-glass opacity equals fibrosis progression."
    - "Improved ground-glass opacity means fibrosis reversed."
    - "New consolidation is simply ILD progression."
    - "Traction bronchiectasis always proves progression without comparison context."
```

---

## 5. Allowed Phrase Set — Technical Comparability

```yaml
allowed_phrases_technical_comparability:
  safe_phrases:
    - "CT technique can affect apparent change."
    - "Slice thickness, reconstruction kernel, inspiratory effort, motion, contrast status, and patient positioning can influence comparison."
    - "When technique differs between studies, subtle interval change should be interpreted cautiously."
    - "Poor inspiration can make dependent opacity or ground-glass abnormality appear more conspicuous."

  conditional_phrases:
    - "If the current and prior CT studies are not technically comparable, the platform should flag temporal uncertainty."
    - "If expiratory imaging is absent, air trapping comparison may be limited."

  blocked_phrases:
    - "Technical differences do not matter."
    - "Subtle progression can be declared even when the CT protocols are not comparable."
    - "Poor inspiration has no effect on ILD comparison."
```

---

## 6. Allowed Phrase Set — New GGO / Consolidation

```yaml
allowed_phrases_new_GGO_consolidation:
  safe_phrases:
    - "New ground-glass opacity on an ILD background is not specific."
    - "New consolidation on an ILD background requires temporal and clinical context."
    - "New airspace opacity may reflect infection, edema, organizing pneumonia, drug or treatment-related injury, hemorrhage, aspiration, acute exacerbation, or another superimposed process."
    - "The baseline ILD label should not automatically explain every new opacity."

  conditional_phrases:
    - "If new bilateral ground-glass opacity appears during acute clinical worsening, acute exacerbation may be part of the differential, but infection, edema, hemorrhage, drug toxicity, and other mimics should remain visible."
    - "If a focal opacity persists or grows, malignancy, chronic infection, organizing pneumonia, infarct, and other focal processes may require reassessment."

  blocked_phrases:
    - "New GGO means acute exacerbation."
    - "New GGO means infection."
    - "New consolidation means pneumonia."
    - "New consolidation means organizing pneumonia."
    - "The known ILD diagnosis explains the new opacity."
```

---

## 7. Allowed Phrase Set — Nodules / Mass / Persistent Focal Opacity

```yaml
allowed_phrases_focal_opacity:
  safe_phrases:
    - "A new or growing focal abnormality should not be hidden inside the baseline fibrosis label."
    - "Persistent focal opacity requires careful temporal and morphologic review."
    - "A focal lesion on fibrotic background may represent malignancy, infection, organizing pneumonia, infarct, scar-like distortion, or treatment-related change depending on context."
    - "FDG uptake is not specific and should be interpreted with timeline, distribution, and inflammatory context."

  conditional_phrases:
    - "If a focal opacity persists or grows on comparable imaging, malignancy and chronic infection should remain visible reasoning pathways."
    - "If a nodule resolves, a reversible inflammatory or infectious process becomes more plausible, but context still matters."

  blocked_phrases:
    - "A new nodule in fibrosis is just scar."
    - "A persistent focal consolidation is just organizing pneumonia."
    - "FDG uptake proves malignancy."
    - "PET negativity excludes malignancy."
    - "A benign sample from one site explains all other lesions."
```

---

## 8. Allowed Phrase Set — Improvement / Regression

```yaml
allowed_phrases_improvement:
  safe_phrases:
    - "Improvement in airspace opacity may reflect resolution of a reversible component."
    - "Reduction in ground-glass opacity or consolidation does not automatically mean established fibrosis has reversed."
    - "Improvement should be interpreted by separating reversible opacity from structural fibrotic abnormality."
    - "Treatment response language requires careful evidence and context."

  conditional_phrases:
    - "If ground-glass opacity decreases but traction bronchiectasis or honeycombing persists, the improvement may involve a reversible superimposed component rather than fibrosis reversal."
    - "If both symptoms and reversible opacity improve, the platform may describe improvement of the reversible component, not cure or reversal of the baseline ILD."

  blocked_phrases:
    - "Fibrosis reversed."
    - "The ILD is cured."
    - "Improvement in GGO proves treatment worked."
    - "Regression is certain from one follow-up CT."
```

---

## 9. Allowed Phrase Set — MDD / Specialist Review

```yaml
allowed_phrases_MDD_review:
  safe_phrases:
    - "When imaging, clinical course, laboratory data, and treatment timeline conflict, multidisciplinary review may be important."
    - "Temporal reasoning may require integration of radiology, pulmonary, clinical, laboratory, treatment, exposure, and pathology context."
    - "The platform is designed to expose uncertainty and missing information, not replace clinician judgment."

  conditional_phrases:
    - "If acute deterioration, hypoxemia, hemoptysis, suspected infection, suspected PE, or new focal lesion is present, urgent clinical review may be needed."
    - "If tissue sampling is being considered, the target lesion and clinical question should be explicit."

  blocked_phrases:
    - "MDD is unnecessary."
    - "The platform replaces clinical judgment."
    - "The platform decides whether biopsy is needed."
    - "The platform decides treatment."
```

---

## 10. Required Uncertainty Phrases

```yaml
required_uncertainty_phrases:
  when_prior_CT_missing:
    - "Prior CT is unavailable, so temporal behavior cannot be established with confidence."
    - "This should be framed as current-pattern reasoning rather than confirmed progression or regression."

  when_technical_comparability_limited:
    - "Comparison is limited by technical differences."
    - "Subtle interval change should be interpreted cautiously."

  when_new_GGO_or_consolidation_present:
    - "This finding is not specific."
    - "A superimposed process should remain in the differential."

  when_focal_opacity_persistent:
    - "Persistence requires reassessment."
    - "Malignancy, chronic infection, organizing pneumonia, infarct, scar-like distortion, and treatment-related change should remain visible as appropriate."

  when_claim_mapping_incomplete:
    - "This language remains draft-only until full-text source review and expert review are completed."
```

---

## 11. Forbidden Public Language

```yaml
forbidden_public_language:
  diagnostic_overreach:
    - "This is IPF progression."
    - "This is acute exacerbation."
    - "This is infection."
    - "This is drug toxicity."
    - "This is malignancy."
    - "This is organizing pneumonia."
    - "This is pulmonary edema."
    - "This is diffuse alveolar hemorrhage."

  treatment_or_management:
    - "Start steroids."
    - "Stop the medication."
    - "Give antibiotics."
    - "Order biopsy."
    - "Repeat CT in X months."
    - "No follow-up is needed."
    - "This requires treatment."

  false_certainty:
    - "Definitive."
    - "Proven."
    - "Excluded."
    - "Guaranteed."
    - "No uncertainty."
    - "Rules out."
    - "Confirms."

  authority_overclaim:
    - "The platform diagnoses."
    - "The platform decides."
    - "The platform replaces MDD."
    - "The platform gives treatment advice."
```

---

## 12. Public Draft Example Paragraph

```yaml
public_draft_example_paragraph:
  status: draft_only_not_public_ready
  text: >
    Temporal comparison is central in ILD reasoning. A current CT can describe the pattern that is present today,
    but prior imaging is often needed to determine whether a finding is new, stable, progressive, resolving, or migratory.
    New ground-glass opacity or consolidation on a fibrotic background is not specific and should not automatically be
    labeled progression. The first step is to separate structural fibrotic change from potentially reversible airspace
    opacity, while keeping infection, edema, organizing pneumonia, drug or treatment-related injury, hemorrhage,
    acute exacerbation, aspiration, and malignancy visible when relevant.

  reason_allowed_as_draft:
    - reasoning_focused
    - non_diagnostic
    - uncertainty_preserving
    - no_treatment_recommendation
    - claim_map_exists_but_pending_review

  public_ready_allowed: false
```

---

## 13. Page-level Language Gate

```yaml
temporal_comparison_public_language_gate:
  page: docs/reasoning/temporal_comparison_methodology_v1.md
  phrase_set_status: draft
  public_ready_allowed: false

  gate_blockers:
    - full_text_review_pending
    - expert_review_not_started
    - claim_map_draft_only
    - public_allowed_phrases_not_expert_validated
    - candidate_sources_remain_for_technical_comparability_and_AE_context

  allowed_next_status:
    - public_language_draft_prepared
    - not_public_ready
```

---

## 14. Final Public Language Rule

```text
Public language must teach how to think, not tell the user what the patient has.

The safest public phrase is one that preserves the next question.
```