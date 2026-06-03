# Sarcoidosis vs GPA / Granulomatous Vasculitis — Gray Zone Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_sarcoidosis_vs_GPA_or_granulomatous_vasculitis_v1
title: Sarcoidosis vs GPA / Granulomatous Vasculitis — Gray Zone Reasoning Map
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
  - rheumatologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users compare sarcoidosis-like thoracic disease with granulomatosis with polyangiitis (GPA) or other granulomatous vasculitis contexts without forcing premature diagnostic certainty.

It does not diagnose sarcoidosis, GPA, ANCA-associated vasculitis, infection, malignancy, lymphoma, rheumatoid nodules, septic emboli, or other cavitary lung diseases.

It helps users ask:

- Is the pattern truly sarcoidosis-like?
- Are there cavitating nodules, destructive airway disease, or vasculitic red flags?
- Are sinonasal, renal, skin, neurologic, or systemic vasculitis clues present?
- Is ANCA testing available or relevant?
- Is there hemoptysis, diffuse alveolar hemorrhage, or rapidly progressive renal disease context?
- Are infection, malignancy, septic emboli, and rheumatoid nodules still visible?
- Is tissue, microbiology, rheumatology, or MDD review needed?
- What do we still not know?

---

## 1. Core Distinction

```yaml
core_distinction:
  sarcoidosis_pathway:
    reasoning_center: compatible_nodal_perilymphatic_granulomatous_pattern_with_mimics_reviewed
    classic_clues:
      - symmetric_bilateral_hilar_lymphadenopathy
      - mediastinal_lymphadenopathy
      - perilymphatic_nodules
      - fissural_nodules
      - peribronchovascular_nodules
      - upper_or_mid_lung_predominance
      - compatible_eye_skin_or_lymph_node_context
    danger_statement: sarcoidosis_should_not_be_called_when_cavitary_destructive_airway_renal_or_vasculitic_clues_are_present_without_GPA_review

  GPA_or_granulomatous_vasculitis_pathway:
    reasoning_center: necrotizing_granulomatous_vasculitis_context_with_airway_lung_and_systemic_clues
    classic_clues:
      - cavitating_pulmonary_nodules
      - multiple_pulmonary_nodules_or_masses
      - tracheobronchial_or_subglottic_stenosis
      - destructive_sinonasal_disease
      - hemoptysis_or_alveolar_hemorrhage_context
      - renal_findings_or_glomerulonephritis_context
      - skin_or_neurologic_vasculitis_clues
      - ANCA_context_when_available
    danger_statement: GPA_or_vasculitis_can_be_missed_if_cavitation_airway_destruction_or_renal_clues_are_hidden_under_a_sarcoidosis_label
```

### Teaching Point

Sarcoidosis asks:

```text
Is this a compatible nodal-perilymphatic granulomatous disease pattern after mimics are considered?
```

GPA / granulomatous vasculitis asks:

```text
Is there necrotizing granulomatous vasculitis behavior involving lung, airway, sinonasal tract, kidney, or systemic vasculitis context?
```

The key error is to treat cavitary nodules or destructive airway disease as atypical sarcoidosis without vasculitis review.

---

## 2. Features Supporting Sarcoidosis Pathway

```yaml
features_supporting_sarcoidosis_pathway:
  imaging_distribution:
    - symmetric_bilateral_hilar_lymphadenopathy
    - mediastinal_lymphadenopathy
    - perilymphatic_nodules
    - fissural_nodules
    - subpleural_nodules
    - peribronchovascular_nodules
    - upper_or_mid_lung_predominance

  clinical_context:
    - compatible_eye_or_skin_or_lymph_node_features
    - chronic_or_subacute_noninfectious_course
    - no_destructive_sinonasal_context
    - no_renal_or_glomerulonephritis_context
    - no_hemoptysis_or_alveolar_hemorrhage_context
    - no_strong_GPA_or_vasculitis_signal_after_review

  pathology_context_when_available:
    - nonnecrotizing_granulomatous_inflammation
    - compatible_clinical_radiologic_context
    - infection_occupational_malignancy_and_vasculitis_mimics_reviewed

  reasoning_weight:
    symmetric_bilateral_hilar_lymphadenopathy: high_when_context_compatible
    perilymphatic_nodules: high
    compatible_extrapulmonary_sarcoid_context: moderate_to_high
    absence_of_vasculitic_context_after_review: supportive_but_not_absolute
```

---

## 3. Features Supporting GPA / Granulomatous Vasculitis Pathway

```yaml
features_supporting_GPA_or_granulomatous_vasculitis_pathway:
  pulmonary_imaging_features:
    - multiple_pulmonary_nodules
    - cavitating_nodules
    - pulmonary_masses_or_mass_like_nodules
    - peripheral_or_random_nodule_distribution_possible
    - consolidation_or_infarct_like_opacity_possible
    - diffuse_ground_glass_if_alveolar_hemorrhage_context
    - airway_wall_thickening_or_stenosis_possible

  airway_and_ENT_context:
    - chronic_sinusitis_or_refractory_sinonasal_disease
    - nasal_crusting_or_epistaxis
    - septal_perforation_or_saddle_nose_context
    - otitis_or_mastoid_context
    - subglottic_stenosis
    - tracheobronchial_stenosis_or_airway_inflammation

  systemic_vasculitis_context:
    - hematuria
    - proteinuria
    - rapidly_progressive_renal_dysfunction
    - glomerulonephritis_context
    - purpura_or_skin_vasculitis
    - mononeuritis_multiplex_or_neuropathy
    - constitutional_symptoms

  laboratory_context_when_available:
    - PR3_ANCA_or_cANCA_context
    - MPO_ANCA_context_less_specific_for_GPA_but_AAV_relevant
    - inflammatory_markers_context
    - urinalysis_abnormality

  pathology_context_when_available:
    - necrotizing_granulomatous_inflammation
    - vasculitis
    - pauci_immune_glomerulonephritis_context
    - exclusion_of_infection_and_malignancy_when_relevant

  reasoning_weight:
    cavitating_pulmonary_nodules: high
    destructive_sinonasal_disease: high
    renal_or_glomerulonephritis_context: very_high
    subglottic_or_tracheobronchial_stenosis: high
    PR3_ANCA_context: high_when_clinically_compatible
```

---

## 4. Direct Comparison Matrix

| Feature | More Sarcoidosis-like | More GPA / Vasculitis-like | Reasoning Note |
|---|---|---|---|
| Lymphadenopathy | Symmetric hilar/mediastinal common | May occur but not usually the dominant classic clue | Nodes alone do not decide |
| Nodules | Perilymphatic/fissural/peribronchovascular | Multiple nodules, often cavitating possible | Cavitation is a major red flag |
| Cavitation | Atypical / complication context | Strong concern | Infection and malignancy also remain visible |
| Airway disease | Airway sarcoidosis possible | Subglottic/tracheobronchial stenosis or destructive airway disease | Airway pattern and systemic context matter |
| ENT disease | Not usually destructive | Sinonasal destruction, epistaxis, crusting | High-value GPA clue |
| Renal disease | Not classic defining feature | Hematuria/proteinuria/GN high-value | Urinalysis is high yield |
| ANCA | Not defining | Supports AAV context when compatible | ANCA is not standalone diagnosis |
| Pathology | Nonnecrotizing granulomas in context | Necrotizing granulomatous inflammation/vasculitis | Tissue requires infection/malignancy context |
| Hemoptysis/DAH | Not classic simple sarcoidosis | Important vasculitis clue | Also infection/malignancy/PE differential |

---

## 5. Gray Zone Scenarios

### 5.1 Sarcoidosis-like Nodules with Cavitation

```yaml
scenario_sarcoidosis_like_nodules_with_cavitation:
  problem:
    - pulmonary_nodules_present
    - cavitation_present
    - sarcoidosis_GPA_infection_malignancy_all_possible

  sarcoidosis_leaning_features:
    - typical_perilymphatic_background_nodules
    - symmetric_hilar_or_mediastinal_nodes
    - known_sarcoidosis_context
    - chronic_fibrocystic_sarcoid_complication_possible

  GPA_or_vasculitis_leaning_features:
    - multiple_cavitating_nodules
    - sinonasal_symptoms
    - hemoptysis_or_alveolar_hemorrhage_context
    - renal_findings
    - ANCA_context_when_available
    - systemic_vasculitic_features

  infection_or_malignancy_review_triggers:
    - fever_or_immunosuppression
    - septic_emboli_context
    - known_malignancy
    - rapid_growth
    - necrotic_nodes

  missing_pieces:
    - microbiology
    - ANCA_context
    - urinalysis_and_renal_function
    - ENT_review
    - prior_CT
    - tissue_or_sampling_context_if_needed
    - MDD_review

  pitfall:
    - Cavitation_should_not_be_hidden_inside_an_atypical_sarcoidosis_label
```

### 5.2 Airway Sarcoidosis vs GPA Airway Disease

```yaml
scenario_airway_sarcoidosis_vs_GPA_airway_disease:
  problem:
    - airway_narrowing_or_wall_thickening_present
    - sarcoidosis_and_GPA_both_possible

  airway_sarcoidosis_leaning_features:
    - coexisting_typical_sarcoid_nodes
    - perilymphatic_nodules
    - known_sarcoidosis_context
    - non_destructive_airway_involvement
    - compatible_endobronchial_sarcoid_context

  GPA_airway_leaning_features:
    - subglottic_stenosis
    - tracheobronchial_stenosis
    - destructive_sinonasal_disease
    - recurrent_epistaxis_or_nasal_crusting
    - renal_or_ANCA_context
    - systemic_vasculitic_clues

  missing_pieces:
    - ENT_history_and_exam_context
    - bronchoscopy_context_if_relevant
    - ANCA_testing_context
    - urinalysis
    - prior_airway_imaging
    - MDD_review

  pitfall:
    - Do_not_call_airway_stenosis_sarcoidosis_without_checking_GPA_context
```

### 5.3 Granulomas on Tissue with Renal / ENT Clues

```yaml
scenario_granulomas_with_renal_ENT_clues:
  problem:
    - granulomatous_inflammation_reported
    - renal_or_sinonasal_clues_present_or_unknown

  sarcoidosis_leaning_features:
    - nonnecrotizing_granulomas
    - typical_sarcoid_imaging
    - no_vasculitis_or_necrosis_reported
    - no_renal_or_ENT_red_flags_after_review

  GPA_or_vasculitis_leaning_features:
    - necrotizing_granulomatous_inflammation
    - vasculitis_on_pathology
    - hematuria_or_proteinuria
    - renal_dysfunction
    - destructive_sinonasal_disease
    - ANCA_context

  missing_pieces:
    - pathology_detail
    - renal_function
    - urinalysis
    - ENT_context
    - ANCA_testing_context
    - infection_review
    - MDD_review

  pitfall:
    - Granulomas_do_not_define_sarcoidosis_when_vasculitis_or_renal_clues_are_unreviewed
```

### 5.4 Diffuse Ground-glass / Hemoptysis Context

```yaml
scenario_diffuse_GGO_or_hemoptysis_context:
  problem:
    - diffuse_ground_glass_or_acute_opacity_present
    - hemoptysis_or_anemia_or_acute_decline_possible
    - sarcoidosis_flare_infection_DAH_or_GPA_possible

  sarcoidosis_leaning_features:
    - known_sarcoidosis_context
    - no_hemoptysis_or_anemia
    - no_renal_or_ANCA_context
    - compatible_nonacute_sarcoid_parenchymal_pattern

  GPA_or_vasculitis_leaning_features:
    - hemoptysis
    - falling_hemoglobin
    - diffuse_alveolar_hemorrhage_context
    - renal_findings
    - ANCA_context
    - systemic_vasculitic_clues

  infection_or_other_review_triggers:
    - fever
    - immunosuppression
    - pulmonary_edema_context
    - drug_toxicity_context
    - pulmonary_embolism_context

  missing_pieces:
    - clinical_acuity
    - hemoglobin_trend
    - urinalysis_and_renal_function
    - ANCA_context
    - infection_review
    - prior_CT
    - urgent_clinical_review_if_severe

  pitfall:
    - Acute_diffuse_GGO_with_hemoptysis_should_not_be_called_sarcoidosis_progression_without_DAH_and_infection_review
```

---

## 6. Why Not Engine

### Why not sarcoidosis?

```yaml
why_not_sarcoidosis:
  - cavitating_pulmonary_nodules
  - destructive_sinonasal_disease
  - subglottic_or_tracheobronchial_stenosis
  - hemoptysis_or_diffuse_alveolar_hemorrhage_context
  - hematuria_or_proteinuria
  - renal_dysfunction_or_glomerulonephritis_context
  - ANCA_positive_or_AAV_context_when_compatible
  - necrotizing_granulomatous_inflammation
  - vasculitis_on_pathology
  - infection_or_malignancy_not_excluded
```

### Why not GPA / granulomatous vasculitis?

```yaml
why_not_GPA_or_granulomatous_vasculitis:
  - no_ENT_or_airway_destructive_context_after_review
  - no_renal_or_urinalysis_abnormality_when_relevant
  - ANCA_not_supportive_in_compatible_testing_context
  - classic_symmetric_sarcoid_nodes_and_perilymphatic_nodules_dominate
  - nonnecrotizing_granulomas_without_vasculitis_in_compatible_sarcoid_context
  - infection_or_malignancy_explains_cavitary_or_nodular_findings_better
```

### Why not stop at “granulomatous disease”?

```yaml
why_not_stop_at_granulomatous_disease:
  - granulomatous_disease_has_broad_differential
  - necrosis_vasculitis_and_systemic_context_change_reasoning
  - renal_ENT_airway_and_ANCA_context_are_high_yield
  - infection_and_malignancy_must_remain_visible
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    cavitation_review:
      reason: Cavitation is atypical for simple sarcoidosis and should trigger GPA, infection, malignancy, and septic emboli review.

    ENT_and_airway_context:
      reason: Sinonasal destruction, epistaxis, crusting, subglottic stenosis, and tracheobronchial disease support GPA-like reasoning.

    renal_function_and_urinalysis:
      reason: Hematuria, proteinuria, or glomerulonephritis context strongly redirects toward AAV/GPA review.

    ANCA_testing_context:
      reason: PR3/MPO ANCA may support AAV reasoning when clinically compatible but is not standalone diagnostic authority.

    pathology_detail:
      reason: Necrosis, vasculitis, granuloma type, and sampling site matter.

    microbiology:
      reason: Infection can mimic cavitary nodular vasculitic disease and must remain visible.

    malignancy_review:
      reason: Cavitary or mass-like nodules may reflect malignancy in the right context.

    prior_CT:
      reason: Growth, cavitation, migration, stability, or treatment response may redirect reasoning.

    rheumatology_or_MDD_review:
      reason: Sarcoidosis-vs-GPA reasoning requires pulmonary, radiology, rheumatology, pathology, microbiology, and renal/ENT context integration.
```

---

## 8. Temporal Reasoning

```yaml
temporal_reasoning:
  behavior_supporting_sarcoidosis_like_course:
    clues:
      - stable_or_regressing_symmetric_nodes
      - stable_or_regressing_perilymphatic_nodules
      - chronic_non_destructive_course
      - no_new_cavitation_or_renal_ENT_clues
    caution:
      - known_sarcoidosis_does_not_exclude_new_GPA_infection_or_malignancy

  behavior_supporting_GPA_or_vasculitis:
    clues:
      - new_or_migratory_nodules
      - new_cavitation
      - recurrent_or_progressive_airway_stenosis
      - evolving_sinonasal_or_renal_clues
      - acute_GGO_with_hemoptysis_or_DAH_context
      - systemic_vasculitic_flare_pattern

  rapid_worsening:
    consider:
      - diffuse_alveolar_hemorrhage
      - infection
      - pulmonary_embolism
      - rapidly_progressive_glomerulonephritis_context
      - malignancy
      - drug_toxicity
      - acute_sarcoid_inflammatory_activity_context_dependent
```

---

## 9. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if:
    - sarcoidosis_like_pattern_with_cavitating_nodules
    - airway_stenosis_or_destructive_airway_disease_present
    - sinonasal_or_renal_clues_present
    - hemoptysis_or_diffuse_alveolar_hemorrhage_context
    - ANCA_context_conflicts_with_imaging_pattern
    - tissue_result_and_systemic_context_conflict
    - infection_or_malignancy_not_excluded

  rheumatology_review_high_value_if:
    - cavitating_nodules_with_systemic_clues
    - ENT_or_airway_destruction
    - renal_or_urinalysis_abnormality
    - ANCA_positive_or_AAV_suspected
    - purpura_neuropathy_or_systemic_vasculitis_clues

  nephrology_review_high_value_if:
    - hematuria
    - proteinuria
    - rising_creatinine
    - suspected_glomerulonephritis
    - pulmonary_renal_syndrome_context

  ENT_or_airway_review_high_value_if:
    - destructive_sinonasal_symptoms
    - epistaxis_or_nasal_crusting
    - subglottic_stenosis
    - tracheobronchial_stenosis

  microbiology_review_high_value_if:
    - cavitation
    - fever_or_infectious_context
    - immunosuppression
    - septic_emboli_context
    - necrotizing_granulomas

  tissue_or_sampling_discussion_if:
    - diagnosis_uncertain_after_clinical_imaging_systemic_review
    - infection_or_malignancy_must_be_excluded
    - result_would_change_management
    - accessible_site_exists
    - patient_risk_is_acceptable
    - MDD_supports_need
```

---

## 10. Pitfall Library

```yaml
pitfalls:
  - title: Calling cavitating nodules atypical sarcoidosis.
    correction: Cavitation should trigger GPA, infection, malignancy, septic emboli, and rheumatoid nodule review.

  - title: Ignoring ENT symptoms.
    correction: Sinonasal destruction, epistaxis, crusting, otologic disease, or subglottic stenosis can be high-value GPA clues.

  - title: Ignoring urinalysis.
    correction: Hematuria, proteinuria, or renal dysfunction may reveal pulmonary-renal vasculitis.

  - title: Treating ANCA as standalone diagnosis.
    correction: ANCA supports AAV reasoning only when integrated with clinical, imaging, renal, and pathology context.

  - title: Treating nonnecrotizing granulomas as sarcoidosis.
    correction: Granulomas require exclusion of infection, occupational mimics, malignancy, and vasculitis when clues exist.

  - title: Missing diffuse alveolar hemorrhage.
    correction: Acute GGO with hemoptysis, anemia, or renal clues requires urgent DAH/vasculitis review.

  - title: Hiding new vasculitic disease under known sarcoidosis.
    correction: Known sarcoidosis does not explain all future nodules, cavitation, airway stenosis, or renal findings.
```

---

## 11. Evidence and Guideline Registry Links

```yaml
evidence_and_guideline_registry_links:
  primary_sources:
    - ATS_2020_SARCOIDOSIS_DIAGNOSIS_DETECTION
    - ACR_VF_2021_ANCA_ASSOCIATED_VASCULITIS_GUIDELINE
    - EULAR_2022_ANCA_ASSOCIATED_VASCULITIS_RECOMMENDATIONS

  supportive_sources:
    - GPA_THORACIC_MANIFESTATIONS_RADIOGRAPHICS_REVIEW
    - DIFFERENTIAL_DIAGNOSIS_OF_PULMONARY_SARCOIDOSIS_2023_REVIEW
    - NON_INFECTIOUS_GRANULOMATOUS_LUNG_DISEASE_REVIEW

  evidence_notes:
    - ATS sarcoidosis diagnostic framework requires mimic review and exclusion of alternative granulomatous causes.
    - ACR/VF and EULAR sources support AAV/GPA clinical management and context but should not be used as imaging-only diagnostic authority.
    - GPA reasoning requires systemic context: airway, ENT, renal, ANCA, pathology, infection, and malignancy review.
    - Cavitation, destructive airway disease, hemoptysis, and renal findings should keep GPA/vasculitis visible.
```

---

## 12. MVP Test Case

```yaml
case_test_sarcoidosis_vs_GPA_001:
  input:
    age: 48
    sex: male
    hrct:
      - bilateral_pulmonary_nodules
      - one_cavitating_nodule
      - mediastinal_lymphadenopathy
      - no_definite_perilymphatic_distribution_reported
    history:
      known_sarcoidosis: unknown
      sinusitis_or_epistaxis: unknown
      hemoptysis: unknown
      renal_symptoms: unknown
      infection_review: unknown
      malignancy_history: unknown
      prior_CT: unavailable
    laboratory:
      ANCA: unavailable
      urinalysis: unavailable
      creatinine: unavailable
    tissue:
      granulomas: unavailable
      vasculitis: unavailable
    microbiology:
      unavailable

  output:
    reasoning_state: sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone
    sarcoidosis_support:
      - mediastinal_lymphadenopathy
      - granulomatous_pattern_possible
    GPA_or_vasculitis_support:
      - cavitating_nodule
      - pulmonary_nodules
      - ENT_renal_ANCA_context_unknown
    cannot_conclude:
      - sarcoidosis
      - GPA
      - infection_excluded
      - malignancy_excluded
      - septic_emboli_or_rheumatoid_nodules_excluded
    missing_pieces:
      - ENT_and_airway_context
      - hemoptysis_or_DAH_review
      - urinalysis_and_renal_function
      - ANCA_testing_context
      - microbiology
      - malignancy_review
      - prior_CT
      - tissue_or_sampling_context_if_needed
      - rheumatology_or_MDD_review
    final_prompt:
      - What vasculitic, infectious, malignant, or renal evidence is missing before calling this sarcoidosis?
```

---

## 13. Final Page Prompt

Every Sarcoidosis vs GPA / Granulomatous Vasculitis gray-zone page should end with:

```text
Do not force the label.

Ask:
1. Are there cavitating nodules, masses, or migratory pulmonary lesions?
2. Is there destructive sinonasal disease, epistaxis, crusting, otologic disease, or subglottic/tracheobronchial stenosis?
3. Is there hemoptysis, diffuse ground-glass opacity, anemia, or alveolar hemorrhage context?
4. Are urinalysis, creatinine, renal symptoms, or glomerulonephritis context known?
5. Is ANCA testing available and clinically compatible?
6. Has infection, malignancy, septic emboli, and rheumatoid nodule context been considered?
7. What does the prior CT show?
8. Is rheumatology, nephrology, ENT, microbiology, tissue sampling, or MDD review needed?
9. What do we still not know?
```