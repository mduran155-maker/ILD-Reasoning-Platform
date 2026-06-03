# Sarcoidosis vs GLILD — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_sarcoidosis_vs_glild_v1
title: Sarcoidosis vs GLILD — Gray Zone Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: gray_zone_reasoning_map
diagnostic_authority: none
linked_patterns:
  - sarcoidosis_pattern_gold_standard_v1
linked_reasoning_maps:
  - granulomatous_ild_reasoning_map_v1
linked_navigation:
  - granulomatous_crosslink_registry_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - immunologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare sarcoidosis-like thoracic disease and granulomatous-lymphocytic interstitial lung disease (GLILD) without forcing premature diagnostic certainty.

It does not diagnose sarcoidosis, GLILD, CVID, lymphoma, infection, malignancy, or other immune-deficiency-related lung disease.

It helps users ask:

- Is the patient immunocompetent or is there immune deficiency context?
- Is CVID or primary antibody deficiency known or suspected?
- Are recurrent infections, hypogammaglobulinemia, splenomegaly, cytopenias, or lymphoproliferative features present?
- Are imaging findings sarcoidosis-like, GLILD-like, infection-like, or lymphoma-like?
- Is tissue needed, available, or potentially misleading without immune context?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  sarcoidosis_pathway:
    reasoning_center: granulomatous_disease_in_compatible_clinical_radiologic_context_usually_without_primary_immunodeficiency_context
    classic_clues:
      - bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - upper_or_mid_lung_predominance
      - compatible_extrapulmonary_features
    danger_statement: sarcoidosis_should_not_be_called_simple_when_immune_deficiency_context_is_present

  glild_pathway:
    reasoning_center: granulomatous_lymphocytic_interstitial_lung_disease_in_CVID_or_primary_antibody_deficiency_context
    classic_context_clues:
      - known_CVID
      - hypogammaglobulinemia
      - recurrent_sinopulmonary_infections
      - autoimmune_cytopenias
      - lymphoproliferative_features
      - splenomegaly
      - immune_dysregulation_context
    imaging_clues:
      - pulmonary_nodules
      - ground_glass_opacity
      - consolidation
      - lymphadenopathy
      - splenomegaly_context
      - interstitial_abnormality
    danger_statement: GLILD_can_mimic_sarcoidosis_but_requires_immune_deficiency_reasoning
```

### Teaching Point

Sarcoidosis asks:

```text
Is this compatible granulomatous disease after relevant mimics are considered?
```

GLILD asks:

```text
Is this granulomatous/lymphocytic lung disease occurring in CVID or immune dysregulation context?
```

The key error is to see granulomas, nodules, or lymphadenopathy and ignore immune deficiency context.

---

## 2. Features Supporting Sarcoidosis Pathway

```yaml
features_supporting_sarcoidosis_pathway:
  imaging_distribution:
    - symmetric_bilateral_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - perilymphatic_nodules
    - fissural_nodules
    - peribronchovascular_nodules
    - upper_or_mid_lung_predominance

  clinical_context:
    - no_known_CVID_or_primary_antibody_deficiency
    - compatible_eye_skin_or_lymph_node_features
    - compatible_multisystem_sarcoid_context
    - no_strong_recurrent_infection_or_hypogammaglobulinemia_context

  pathology_context_when_available:
    - nonnecrotizing_granulomatous_inflammation
    - compatible_clinical_radiologic_context
    - alternative_causes_reviewed

  reasoning_weight:
    symmetric_bilateral_hilar_lymphadenopathy: high_when_context_compatible
    perilymphatic_nodules: high
    compatible_extrapulmonary_sarcoid_context: moderate_to_high
    absence_of_primary_immunodeficiency_context: supportive_but_not_absolute
```

---

## 3. Features Supporting GLILD Pathway

```yaml
features_supporting_glild_pathway:
  immune_context:
    - known_CVID
    - suspected_primary_antibody_deficiency
    - hypogammaglobulinemia
    - recurrent_sinopulmonary_infections
    - autoimmune_cytopenias
    - lymphoproliferative_manifestations
    - splenomegaly
    - immune_dysregulation_context

  imaging_features:
    - pulmonary_nodules
    - ground_glass_opacity
    - consolidation
    - interstitial_abnormality
    - lymphadenopathy
    - possible_airway_or_infectious_overlap
    - possible_splenomegaly_or_extrathoracic_lymphoid_context

  pathology_context_when_available:
    - granulomatous_inflammation
    - lymphocytic_interstitial_pneumonia_pattern
    - follicular_bronchiolitis
    - lymphoid_hyperplasia
    - exclusion_of_infection_and_malignancy_when_relevant

  reasoning_weight:
    known_CVID: very_high_contextual_weight
    recurrent_infections_plus_hypogammaglobulinemia: very_high_contextual_weight
    splenomegaly_or_lymphoproliferation: high
    granulomatous_plus_lymphocytic_pathology: high_when_available
```

---

## 4. Direct Comparison Matrix

| Feature | More Sarcoidosis-like | More GLILD-like | Reasoning Note |
|---|---|---|---|
| Immune context | Usually immunocompetent context | CVID / antibody deficiency context | Immune context is central |
| Infections | Not defining | Recurrent sinopulmonary infections common context | Infection history should be actively reviewed |
| Immunoglobulins | Not defining | Hypogammaglobulinemia supports CVID context | Missing Ig levels are high-yield |
| Lymphadenopathy | Common | Can occur | Nodes alone do not separate them |
| Nodules | Perilymphatic pattern supports sarcoid | Nodules may occur in GLILD | Distribution and immune context matter |
| GGO/consolidation | Possible but less defining | Commonly described imaging components | Infection and OP-like mimics remain visible |
| Splenomegaly | Possible but not core | Supports immune dysregulation/lymphoproliferation context | Important missing piece |
| Pathology | Nonnecrotizing granulomas in context | Granulomatous + lymphocytic patterns | Tissue needs immune/microbiology context |
| Malignancy/lymphoma risk | Context-dependent | Lymphoproliferative/malignancy review important | Do not ignore lymphoma-like signals |

---

## 5. Gray Zone Scenarios

### 5.1 Sarcoid-like Imaging in a Patient with Known CVID

```yaml
scenario_sarcoid_like_imaging_known_CVID:
  problem:
    - bilateral_hilar_or_mediastinal_lymphadenopathy
    - pulmonary_nodules_or_GGO
    - known_CVID

  sarcoidosis_leaning_features:
    - classic_perilymphatic_nodules
    - symmetric_hilar_nodes
    - compatible_sarcoid_extrapulmonary_context

  glild_leaning_features:
    - known_CVID
    - recurrent_infections
    - hypogammaglobulinemia
    - splenomegaly
    - lymphoproliferative_features
    - granulomatous_plus_lymphocytic_pathology_when_available

  missing_pieces:
    - immunoglobulin_profile
    - infection_review
    - splenomegaly_assessment
    - lymphoproliferative_or_lymphoma_review
    - tissue_context_if_needed
    - MDD_review

  pitfall:
    - Do_not_call_sarcoidosis_without_GLILD_review_when_CVID_context_exists
```

### 5.2 Granulomas on Pathology with Recurrent Infections

```yaml
scenario_granulomas_with_recurrent_infections:
  problem:
    - granulomatous_inflammation_reported
    - recurrent_sinopulmonary_infections_present_or_suspected

  sarcoidosis_leaning_features:
    - compatible_sarcoid_imaging
    - no_hypogammaglobulinemia
    - no_CVID_context
    - infection_and_malignancy_review_complete

  glild_leaning_features:
    - recurrent_infections
    - low_immunoglobulins
    - CVID_or_antibody_deficiency_context
    - lymphocytic_interstitial_or_follicular_bronchiolitis_features
    - splenomegaly_or_cytopenias

  missing_pieces:
    - immunoglobulin_levels
    - vaccine_response_or_immunology_context_if_relevant
    - microbiology
    - pathology_detail
    - immune_dysregulation_review
    - MDD_review

  pitfall:
    - Granulomas_do_not_define_sarcoidosis_without_immune_and_infection_context
```

### 5.3 Sarcoidosis-like Lymphadenopathy with Splenomegaly

```yaml
scenario_sarcoid_like_nodes_with_splenomegaly:
  problem:
    - thoracic_lymphadenopathy_present
    - splenomegaly_present_or_suspected

  sarcoidosis_leaning_features:
    - classic_perilymphatic_nodules
    - compatible_sarcoid_multisystem_context
    - no_primary_immunodeficiency_clues

  glild_or_immune_dysregulation_leaning_features:
    - CVID_context
    - hypogammaglobulinemia
    - recurrent_infections
    - cytopenias
    - lymphoproliferative_features

  lymphoma_or_malignancy_review_triggers:
    - progressive_asymmetric_nodes
    - B_symptoms
    - discordant_clinical_course
    - focal_mass_or_dominant_node

  missing_pieces:
    - immune_status
    - immunoglobulin_levels
    - cytopenia_history
    - cancer_or_lymphoma_review
    - prior_CT
    - MDD_review

  pitfall:
    - Splenomegaly_should_trigger_GLILD_immune_dysregulation_and_lymphoma_context_review
```

### 5.4 GLILD-like Imaging but No Known CVID

```yaml
scenario_glild_like_imaging_no_known_CVID:
  problem:
    - nodules_GGO_or_consolidation_with_lymphadenopathy
    - GLILD_like_pattern_possible
    - CVID_not_yet_known

  sarcoidosis_leaning_features:
    - classic_perilymphatic_distribution
    - symmetric_hilar_nodes
    - no_recurrent_infection_history
    - normal_immunoglobulin_context_when_available

  glild_leaning_features:
    - recurrent_infections
    - low_immunoglobulins_if_checked
    - splenomegaly
    - autoimmune_cytopenias
    - lymphoproliferative_context

  missing_pieces:
    - immunoglobulin_levels
    - recurrent_infection_history
    - immunology_review
    - infection_review
    - prior_CT
    - MDD_review

  pitfall:
    - Undiagnosed_CVID_can_make_a_sarcoidosis_label_premature
```

---

## 6. Why Not Engine

### Why not sarcoidosis?

```yaml
why_not_sarcoidosis:
  - known_CVID
  - suspected_primary_antibody_deficiency
  - hypogammaglobulinemia
  - recurrent_sinopulmonary_infections
  - splenomegaly
  - autoimmune_cytopenias
  - lymphoproliferative_features
  - granulomatous_plus_lymphocytic_pathology_context
  - infection_or_lymphoma_review_incomplete
```

### Why not GLILD?

```yaml
why_not_GLILD:
  - no_CVID_or_antibody_deficiency_context_after_review
  - normal_immunoglobulin_context_when_relevant
  - no_recurrent_infection_history
  - classic_sarcoidosis_distribution_with_strong_extrapulmonary_sarcoid_context
  - infection_or_malignancy_explains_findings_better
  - pathology_not_supportive_when_available
```

### Why not stop at “sarcoidosis-like granulomatous disease”?

```yaml
why_not_stop_at_sarcoidosis_like_granulomatous_disease:
  - immune_deficiency_context_changes_the_differential
  - GLILD_is_a_CVID_related_clinicoradiopathologic_context
  - infection_and_lymphoma_may_overlap_or_mimic
  - tissue_findings_require_immune_and_microbiology_context
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    immune_status:
      reason: GLILD reasoning requires CVID or immune deficiency context.

    immunoglobulin_levels:
      reason: Hypogammaglobulinemia supports primary antibody deficiency context.

    recurrent_infection_history:
      reason: Recurrent sinopulmonary infections strongly redirect reasoning toward CVID/GLILD or infection.

    splenomegaly_and_cytopenia_review:
      reason: Splenomegaly, cytopenias, and lymphoproliferative features support immune dysregulation context.

    infection_review:
      reason: Infection can coexist with or mimic immune-deficiency-related lung disease.

    lymphoma_or_malignancy_review:
      reason: Lymphoproliferative disease and malignancy must remain visible in CVID/GLILD context.

    pathology_detail:
      reason: Granulomatous plus lymphocytic patterns require context and may support GLILD when immune context fits.

    prior_CT:
      reason: Temporal evolution may show recurrent infection, waxing/waning inflammatory disease, progression, or lymphoproliferative behavior.

    MDD_review:
      reason: Sarcoidosis-vs-GLILD requires pulmonary, radiology, immunology, pathology, microbiology, and sometimes hematology/oncology integration.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  behavior_supporting_sarcoidosis_like_course:
    clues:
      - stable_or_regressing_symmetric_nodes
      - stable_or_regressing_perilymphatic_nodules
      - compatible_sarcoid_multisystem_course
    caution:
      - stability_does_not_exclude_GLILD_if_CVID_context_exists

  behavior_supporting_GLILD_or_immune_dysregulation:
    clues:
      - recurrent_infectious_exacerbations
      - waxing_waning_nodules_GGO_or_consolidation
      - progressive_interstitial_abnormality_in_CVID_context
      - lymphadenopathy_with_splenomegaly_or_cytopenias
      - recurrent_or_persistent_abnormality_despite_infection_treatment_context

  rapid_worsening:
    consider:
      - infection
      - opportunistic_infection
      - lymphoma_or_malignancy
      - GLILD_activity
      - drug_toxicity
      - pulmonary_embolism
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - sarcoidosis_like_pattern_with_known_or_suspected_CVID
    - granulomas_present_but_recurrent_infections_or_hypogammaglobulinemia_present
    - lymphadenopathy_plus_splenomegaly_or_cytopenias
    - infection_or_lymphoma_context_not_excluded
    - pathology_and_immune_context_conflict
    - treatment_decision_depends_on_diagnostic_confidence

  immunology_review_high_value_if:
    - recurrent_infections
    - hypogammaglobulinemia
    - suspected_CVID
    - autoimmune_cytopenias
    - splenomegaly
    - lymphoproliferative_features

  microbiology_review_high_value_if:
    - recurrent_or_active_infection_possible
    - immunosuppression_or_antibody_deficiency_context
    - new_GGO_or_consolidation
    - fever_or_systemic_infectious_context

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

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling sarcoidosis in a CVID patient without GLILD review.
    correction: CVID or antibody deficiency context should trigger GLILD and infection review.

  - title: Treating granulomas as sarcoidosis.
    correction: Granulomas require clinical, immune, microbiologic, and pathology context.

  - title: Ignoring recurrent infections.
    correction: Recurrent sinopulmonary infection history may reveal immune deficiency context.

  - title: Ignoring hypogammaglobulinemia.
    correction: Low immunoglobulins strongly redirect reasoning toward antibody deficiency and GLILD context.

  - title: Missing lymphoma or lymphoproliferative disease.
    correction: Progressive nodes, splenomegaly, cytopenias, or dominant mass require review.

  - title: Assuming sarcoidosis and GLILD are separated by imaging alone.
    correction: Imaging overlaps; immune context and MDD are essential.

  - title: Treating infection as already excluded.
    correction: CVID/GLILD context increases infection relevance; microbiology review may be high value.
```

---

## 11. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - BLF_UKPIN_2017_GLILD_CONSENSUS_STATEMENT
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION

  supportive_review_sources:
    - GLILD_DIAGNOSIS_MANAGEMENT_REVIEW_2024
    - CVID_ILD_DIAGNOSTIC_TESTING_SYSTEMATIC_REVIEW_2023
    - SARCOIDOSIS_VS_GLILD_REVIEW_2024

  evidence_notes:
    - GLILD is linked to CVID/primary antibody deficiency and immune dysregulation context.
    - Evidence for GLILD diagnosis and management remains limited compared with major ILD guidelines.
    - Sarcoidosis and GLILD may overlap in imaging and granulomatous pathology, so immune context is decisive.
    - Infection and lymphoma/malignancy review must remain visible in CVID/GLILD reasoning.
```

---

## 12. MVP Test Case

```yaml
case_test_sarcoidosis_vs_glild_001:
  input:
    age: 38
    sex: female
    hrct:
      - mediastinal_lymphadenopathy
      - pulmonary_nodules
      - ground_glass_opacity
      - patchy_consolidation
    history:
      recurrent_sinopulmonary_infections: present
      known_CVID: unknown
      hypogammaglobulinemia: unknown
      splenomegaly: unknown
      cytopenias: unknown
      extrapulmonary_sarcoid_features: unknown
      cancer_history: unknown
      prior_CT: unavailable
    tissue:
      granulomas: unavailable
      lymphocytic_interstitial_features: unavailable
    microbiology:
      unavailable

  output:
    reasoning_state: sarcoidosis_vs_GLILD_gray_zone
    sarcoidosis_support:
      - mediastinal_lymphadenopathy
      - pulmonary_nodules
      - granulomatous_pattern_possible
    glild_support:
      - recurrent_sinopulmonary_infections
      - nodules_GGO_consolidation_pattern
      - immune_status_unknown
    cannot_conclude:
      - sarcoidosis
      - GLILD
      - infection_excluded
      - lymphoma_or_malignancy_excluded
    missing_pieces:
      - immunoglobulin_levels
      - CVID_or_antibody_deficiency_review
      - splenomegaly_and_cytopenia_review
      - infection_review
      - lymphoma_or_malignancy_review
      - pathology_detail_if_available
      - prior_CT
      - MDD_review
    final_prompt:
      - What immune-deficiency evidence is missing before calling this sarcoidosis?
```

---

## 13. Final Page Prompt

Every Sarcoidosis vs GLILD gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Is there known or suspected CVID / primary antibody deficiency?
2. Are there recurrent sinopulmonary infections or hypogammaglobulinemia?
3. Are there splenomegaly, cytopenias, or lymphoproliferative features?
4. Are infection and lymphoma/malignancy still possible?
5. Does pathology show only granulomas, or granulomatous plus lymphocytic disease?
6. What does the prior CT show?
7. What do we still not know?
```