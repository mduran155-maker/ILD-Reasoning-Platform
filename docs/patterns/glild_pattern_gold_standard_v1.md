# GLILD Pattern Atlas — Gold Standard Datasheet v1

## Document Metadata

```yaml
id: pattern_glild_gold_standard_v1
title: GLILD Pattern Atlas — Gold Standard Datasheet
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: pattern_datasheet
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - immunologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
diagnostic_authority: none
last_updated: draft
linked_reasoning_maps:
  - sarcoidosis_vs_glild_gray_zone_v1
  - granulomatous_ild_reasoning_map_v1
```

---

## 0. Platform Safety Statement

This platform does not diagnose patients, classify individual cases, or recommend treatment.

It supports structured clinical reasoning in GLILD and immune-deficiency-related granulomatous ILD by helping users understand:

- why GLILD is being considered,
- which mimics remain possible,
- which findings weaken a GLILD pathway,
- what immune, infectious, malignant, or pathology context is missing,
- when immunology, microbiology, pathology, hematology/oncology, or MDD review may be required.

> **Core principle:**  
> Diagnosing ILD is not about finding the right answer.  
> It is about asking the right next question — and knowing when you don’t have enough information yet.

---

## 1. Identity

```yaml
pattern_id: glild
full_name: Granulomatous-Lymphocytic Interstitial Lung Disease
short_name: GLILD
category: Immune-Deficiency-Associated Granulomatous / Lymphocytic Interstitial Lung Disease Pattern
primary_domain: HRCT Pattern Recognition + Immunodeficiency Context Reasoning
clinical_role: Pattern-level reasoning, not disease-level diagnosis
important_distinction: GLILD is considered in CVID or primary antibody deficiency context; it should not be diagnosed by imaging alone.
```

### Related Disease Contexts

```yaml
related_disease_contexts:
  - Common Variable Immunodeficiency
  - Primary antibody deficiency
  - Immune dysregulation-associated ILD
  - Granulomatous lymphocytic ILD
  - Sarcoidosis mimic
  - Opportunistic infection mimic
  - Lymphoma / lymphoproliferative disease mimic
  - Organizing pneumonia overlap
  - LIP / follicular bronchiolitis context
```

---

## 2. Pattern Summary

```yaml
one_sentence_summary: >
  GLILD is an immune-deficiency-associated granulomatous and lymphocytic interstitial lung disease pattern,
  classically considered in the context of CVID or primary antibody deficiency, with imaging that may include
  nodules, ground-glass opacity, consolidation, interstitial abnormalities, lymphadenopathy, and systemic
  immune dysregulation clues such as recurrent infections, hypogammaglobulinemia, splenomegaly, cytopenias,
  or lymphoproliferative features.

danger_statement: >
  GLILD can mimic sarcoidosis, infection, lymphoma, OP, LIP, and other ILD patterns; immune deficiency,
  infection, and lymphoproliferative context must remain visible before increasing diagnostic confidence.
```

### Key Teaching Point

GLILD reasoning does not start with imaging alone.

It starts with the question:

```text
Is this granulomatous/lymphocytic lung disease occurring in CVID or immune dysregulation context?
```

---

## 3. Diagnostic Context Framework

```yaml
diagnostic_context_framework:
  core_context:
    - known_CVID
    - suspected_primary_antibody_deficiency
    - hypogammaglobulinemia
    - recurrent_sinopulmonary_infections
    - immune_dysregulation
    - lymphoproliferative_features

  supportive_multidomain_evidence:
    - HRCT_abnormality
    - PFT_abnormality_or_trend
    - infection_review
    - immunology_review
    - pathology_when_needed_or_available
    - lymphoma_or_malignancy_review_when_relevant
    - MDD_review

  platform_rule:
    - do_not_diagnose_GLILD_from_imaging_alone
    - do_not_call_sarcoidosis_without_reviewing_CVID_or_antibody_deficiency_context
    - do_not_ignore_infection_or_lymphoma_mimics
    - preserve_uncertainty_when_immunoglobulin_status_is_unknown
```

---

## 4. HRCT Imaging Anatomy

```yaml
imaging_anatomy:
  pulmonary_findings:
    supportive:
      - pulmonary_nodules
      - ground_glass_opacity
      - consolidation
      - interstitial_abnormality
      - reticulation_possible
      - airway_or_bronchiolitis_features_possible
    caution:
      - findings_are_not_specific_without_CVID_or_immune_context
      - infection_and_lymphoma_may_overlap

  lymphatic_and_systemic_context:
    supportive:
      - mediastinal_or_hilar_lymphadenopathy
      - splenomegaly_when_available
      - extrathoracic_lymphadenopathy_when_available
    caution:
      - progressive_asymmetric_nodes_or_dominant_mass_should_trigger_lymphoma_malignancy_review

  pattern_overlap:
    possible_overlaps:
      - sarcoidosis_like_pattern
      - organizing_pneumonia_like_pattern
      - LIP_or_follicular_bronchiolitis_context
      - infection_like_pattern
      - lymphoma_like_pattern
```

---

## 5. Confidence Levels

```yaml
confidence_levels:
  GLILD_context_strong:
    supportive_features:
      - known_CVID_or_primary_antibody_deficiency
      - recurrent_sinopulmonary_infections
      - hypogammaglobulinemia
      - nodules_GGO_consolidation_or_interstitial_abnormality
      - lymphadenopathy_or_splenomegaly
      - infection_and_malignancy_review_active
      - MDD_context_available_or_planned
    interpretation: Strong GLILD reasoning context, but not imaging-only diagnosis.

  GLILD_context_possible:
    supportive_features:
      - sarcoidosis_like_or_granulomatous_pattern
      - recurrent_infection_history_possible
      - immune_status_unknown
      - nodules_GGO_or_consolidation_present
    interpretation: GLILD remains possible; immunoglobulin and immune status are high-yield missing data.

  sarcoidosis_vs_GLILD_gray_zone:
    supportive_features:
      - lymphadenopathy
      - pulmonary_nodules
      - granulomatous_pattern_possible
      - CVID_status_unknown_or_uncertain
    interpretation: Compare against sarcoidosis, infection, lymphoma, and immune deficiency context.

  alternative_diagnosis_suggested:
    supportive_features:
      - active_infection_context
      - dominant_lymphoma_or_malignancy_signal
      - no_CVID_or_antibody_deficiency_after_review
      - classic_sarcoidosis_context_stronger
    interpretation: Pause GLILD pathway and evaluate stronger alternative explanation.
```

---

## 6. Differential Field

```yaml
core_question_1: Is there CVID or primary antibody deficiency context?
core_question_2: Are lung findings granulomatous, lymphocytic, infectious, malignant, or mixed?
core_question_3: What immune, microbiologic, pathology, or temporal data are missing?
```

```yaml
differential_contexts:
  GLILD:
    supports:
      - known_CVID
      - hypogammaglobulinemia
      - recurrent_sinopulmonary_infections
      - splenomegaly
      - cytopenias
      - lymphoproliferative_features
      - nodules_GGO_consolidation_or_interstitial_abnormality
      - granulomatous_plus_lymphocytic_pathology_when_available
    weakens:
      - no_CVID_or_antibody_deficiency_after_review
      - normal_immunoglobulin_context_when_relevant
      - infection_explains_findings
      - lymphoma_or_malignancy_explains_findings
      - classic_sarcoidosis_context_stronger

  sarcoidosis:
    supports:
      - symmetric_bilateral_hilar_lymphadenopathy
      - perilymphatic_nodules
      - compatible_extrapulmonary_sarcoid_context
      - no_primary_immunodeficiency_context
    weakens:
      - known_CVID
      - recurrent_infections
      - hypogammaglobulinemia
      - splenomegaly_cytopenias_or_lymphoproliferation

  infection:
    supports:
      - recurrent_or_active_infection
      - immunodeficiency_context
      - new_GGO_or_consolidation
      - fever_or_systemic_infectious_context
      - microbiology_support_when_available
    weakens:
      - chronic_stable_pattern_without_infectious_support_after_review

  lymphoma_or_malignancy:
    supports:
      - progressive_asymmetric_lymphadenopathy
      - dominant_mass_or_node
      - B_symptoms
      - splenomegaly_with_cytopenias
      - discordant_clinical_course
    weakens:
      - stable_nonprogressive_context_without_malignancy_support_after_review
```

---

## 7. Gray Zone Links

```yaml
gray_zone_links:
  - sarcoidosis_vs_glild_gray_zone_v1
  - granulomatous_ild_reasoning_map_v1
  - sarcoidosis_vs_granulomatous_infection_gray_zone_v1
  - future_GLILD_vs_infection
  - future_GLILD_vs_lymphoma
  - future_GLILD_vs_OP_LIP_follicular_bronchiolitis
```

---

## 8. Why Not Engine

```yaml
why_not_GLILD:
  - no_CVID_or_antibody_deficiency_context_after_review
  - normal_immunoglobulin_context_when_relevant
  - no_recurrent_infection_history
  - no_splenomegaly_cytopenias_or_lymphoproliferative_context
  - classic_sarcoidosis_context_stronger
  - infection_explains_findings
  - lymphoma_or_malignancy_explains_findings

why_not_sarcoidosis:
  - known_CVID
  - hypogammaglobulinemia
  - recurrent_sinopulmonary_infections
  - splenomegaly
  - cytopenias
  - lymphoproliferative_features
  - infection_or_lymphoma_review_incomplete

why_not_infection_or_lymphoma:
  - microbiology_or_malignancy_review_not_supportive_when_appropriately_performed
  - stable_pattern_with_stronger_GLILD_context
  - MDD_supports_noninfectious_nonmalignant_immune_dysregulation_context
```

---

## 9. Missing Piece Candidates

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  high_yield_missing_data:
    immunoglobulin_levels:
      reason: GLILD reasoning requires CVID or antibody deficiency context.

    CVID_or_antibody_deficiency_review:
      reason: GLILD should not be considered mature without immune deficiency assessment.

    recurrent_infection_history:
      reason: Recurrent sinopulmonary infections redirect toward CVID/immune dysregulation context.

    splenomegaly_and_cytopenia_review:
      reason: Supports lymphoproliferative or immune dysregulation context and may trigger lymphoma review.

    infection_review:
      reason: Infection can mimic or coexist with GLILD.

    lymphoma_or_malignancy_review:
      reason: CVID and lymphoproliferative context require malignancy visibility.

    pathology_detail:
      reason: Granulomatous and lymphocytic patterns require immune, microbiologic, and malignancy context.

    prior_CT:
      reason: Temporal behavior can show waxing/waning disease, recurrent infection, progression, or malignancy-like behavior.

    MDD_review:
      reason: GLILD reasoning requires integrated radiology, pulmonology, immunology, pathology, microbiology, and sometimes hematology/oncology.
```

---

## 10. Temporal Behavior

```yaml
temporal_behavior:
  waxing_waning_inflammatory_behavior:
    supportive_changes:
      - changing_ground_glass
      - changing_consolidation
      - fluctuating_nodules
      - recurrent_infection_like_events
    caution:
      - fluctuation_can_reflect_infection_or_treatment_effect_not_GLILD_alone

  progression:
    supportive_changes:
      - increasing_interstitial_abnormality
      - increasing_nodules_or_consolidation
      - worsening_PFT_when_available
      - increasing_lymphadenopathy_or_splenomegaly
    consider:
      - GLILD_progression
      - infection
      - lymphoma_or_malignancy
      - treatment_related_effect

  stabilization:
    supportive_changes:
      - stable_interstitial_abnormality
      - stable_nodes
      - stable_PFT_when_available
    caution:
      - stability_does_not_remove_need_for_immune_context_review

  unexpectedly_fast_worsening:
    consider:
      - infection
      - opportunistic_infection
      - lymphoma_or_malignancy
      - GLILD_activity
      - drug_toxicity
      - pulmonary_embolism
```

---

## 11. Pattern Interactions

```yaml
pattern_interactions:
  GLILD_plus_lymphadenopathy:
    consider:
      - GLILD
      - sarcoidosis
      - lymphoma
      - infection
    questions:
      - Is there CVID or antibody deficiency?
      - Are nodes symmetric, asymmetric, or progressive?
      - Is there splenomegaly or cytopenia?

  GLILD_plus_GGO_or_consolidation:
    consider:
      - GLILD_activity
      - infection
      - organizing_pneumonia_overlap
      - drug_toxicity
      - lymphoma_or_malignancy
    questions:
      - Is this new or chronic?
      - Is microbiology needed?
      - Is there treatment or infection context?

  GLILD_plus_nodules:
    consider:
      - GLILD
      - sarcoidosis
      - infection
      - lymphoma_or_malignancy
    questions:
      - What is the nodule distribution?
      - Are nodules changing?
      - Is immune deficiency known?

  GLILD_plus_splenomegaly_or_cytopenias:
    consider:
      - immune_dysregulation
      - lymphoproliferative_disease
      - lymphoma
      - GLILD_context
    questions:
      - Is hematology/oncology review needed?
      - Are immunoglobulins known?
```

---

## 12. Superimposed Events

```yaml
superimposed_events:
  new_GGO_or_consolidation:
    consider:
      - infection
      - opportunistic_infection
      - GLILD_activity
      - organizing_pneumonia_overlap
      - drug_toxicity
      - lymphoma_or_malignancy
    warning: New opacity in CVID/GLILD context should not automatically be called GLILD progression.

  new_or_progressive_lymphadenopathy:
    consider:
      - lymphoma
      - infection
      - GLILD_activity
      - sarcoidosis_like_process
    warning: Progressive or asymmetric nodes require lymphoma/malignancy review.

  rapid_clinical_decline:
    consider:
      - infection
      - opportunistic_infection
      - pulmonary_embolism
      - drug_toxicity
      - GLILD_activity
      - malignancy
```

---

## 13. Diagnostic Escalation

```yaml
diagnostic_escalation:
  mdd_needed_if:
    - CVID_or_antibody_deficiency_context_with_ILD
    - sarcoidosis_vs_GLILD_uncertainty
    - infection_or_lymphoma_context_not_excluded
    - pathology_and_imaging_context_conflict
    - treatment_decision_depends_on_diagnostic_confidence

  immunology_review_high_value_if:
    - recurrent_infections
    - hypogammaglobulinemia
    - suspected_CVID
    - autoimmune_cytopenias
    - splenomegaly
    - immune_dysregulation_context

  microbiology_review_high_value_if:
    - new_GGO_or_consolidation
    - fever_or_infectious_context
    - immunodeficiency_context
    - recurrent_infection_history

  hematology_oncology_review_high_value_if:
    - progressive_asymmetric_nodes
    - splenomegaly_with_cytopenias
    - dominant_mass_or_node
    - lymphoma_context_possible

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_immune_review
    - infection_or_malignancy_must_be_excluded
    - result_would_change_management
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 14. Pitfall Library

```yaml
pitfalls:
  - title: Diagnosing GLILD from imaging alone.
    correction: GLILD requires immune-deficiency context and integrated clinical-radiologic-pathologic reasoning.

  - title: Calling sarcoidosis in a CVID patient without GLILD review.
    correction: CVID or antibody deficiency should trigger GLILD, infection, and lymphoma review.

  - title: Ignoring recurrent infections.
    correction: Recurrent sinopulmonary infections may reveal immune deficiency context and infectious mimics.

  - title: Ignoring hypogammaglobulinemia.
    correction: Immunoglobulin status is a high-yield missing piece.

  - title: Missing lymphoma.
    correction: Progressive nodes, splenomegaly, cytopenias, or dominant mass require review.

  - title: Treating granulomas as sarcoidosis.
    correction: Granulomas require immune, microbiologic, and pathology context.

  - title: Hiding limited evidence base.
    correction: GLILD evidence is less mature than major IPF/HP/sarcoidosis guidelines and should be labeled cautiously.
```

---

## 15. Evidence and Guideline Registry

```yaml
evidence_and_guideline_registry:
  primary_sources_to_link:
    - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT

  secondary_sources_to_link:
    - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
    - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION

  evidence_notes:
    - BLF/UKPIN provides consensus-based GLILD definition/diagnosis/management framework.
    - CVID-ILD diagnostic testing evidence remains limited.
    - 2024 review emphasizes MDD and integrated clinical-radiologic-pathologic reasoning.
    - GLILD content requires cautious language and expert review before public release.
```

---

## 16. Narrative Questions

Every GLILD page should end with these questions:

```yaml
narrative_questions:
  - Is there known or suspected CVID / primary antibody deficiency?
  - Are immunoglobulin levels known?
  - Are there recurrent sinopulmonary infections?
  - Are there splenomegaly, cytopenias, or lymphoproliferative features?
  - Are infection and lymphoma/malignancy still possible?
  - Does pathology show granulomatous plus lymphocytic disease, or only nonspecific granulomas?
  - What does the prior CT show?
  - Is MDD needed?
  - What is the single most important missing piece of information?
```

---

## 17. MVP Screen Behavior

```yaml
mvp_screen_behavior:
  main_panel:
    - pattern_summary
    - diagnostic_context_framework
    - hrct_imaging_anatomy
    - confidence_levels
    - differential_field

  right_sidebar:
    - why_not_GLILD
    - why_not_sarcoidosis
    - missing_piece_candidates
    - sarcoidosis_vs_GLILD_gray_zone_link
    - infection_and_lymphoma_alerts
    - pitfall_library
    - evidence_registry

  bottom_panel:
    - immunology_review_prompt
    - microbiology_review_prompt
    - hematology_oncology_review_prompt
    - mdd_prompt
    - what_do_we_still_not_know_prompt
```

---

## 18. MVP Test Case

```yaml
case_test_GLILD_001:
  input:
    age: 39
    sex: female
    hrct:
      - pulmonary_nodules
      - ground_glass_opacity
      - patchy_consolidation
      - mediastinal_lymphadenopathy
    history:
      recurrent_sinopulmonary_infections: present
      known_CVID: unknown
      hypogammaglobulinemia: unknown
      splenomegaly: unknown
      cytopenias: unknown
      prior_CT: unavailable
    laboratory:
      immunoglobulin_levels: unavailable
    tissue:
      granulomas: unavailable
      lymphocytic_interstitial_features: unavailable
    microbiology:
      unavailable

  system_output:
    pattern_confidence: GLILD_context_possible
    disease_statement: GLILD is possible only if immune-deficiency context is supported; imaging alone is insufficient.
    why_not_GLILD:
      - CVID_or_antibody_deficiency_status_unknown
      - immunoglobulin_levels_unavailable
      - pathology_detail_unavailable
    why_not_sarcoidosis:
      - recurrent_infections_present
      - immune_status_unknown
    missing_pieces:
      - immunoglobulin_levels
      - CVID_or_antibody_deficiency_review
      - splenomegaly_and_cytopenia_review
      - infection_review
      - lymphoma_or_malignancy_review
      - prior_CT
      - MDD_review
    final_prompt:
      - What immune-deficiency evidence is missing before calling this GLILD or sarcoidosis?
```

---

## 19. Final Page Prompt

Every GLILD Pattern page should end with:

```text
Do not force the label.

Ask:
1. Is there known or suspected CVID / primary antibody deficiency?
2. Are immunoglobulin levels known?
3. Are there recurrent infections, splenomegaly, cytopenias, or lymphoproliferative features?
4. Are infection and lymphoma/malignancy still possible?
5. Is this sarcoidosis-like, GLILD-like, infection-like, or lymphoma-like?
6. Does pathology support granulomatous plus lymphocytic disease?
7. What does the prior CT show?
8. What do we still not know?
```