# Vascular / Edema / Hemorrhage Mimic Panel — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_vascular_edema_hemorrhage_mimic_panel_v1
title: Vascular / Edema / Hemorrhage Mimic Panel — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: superimposed_event_reasoning_map
diagnostic_authority: none
module_version: v0.3
linked_reasoning_maps:
  - superimposed_events_core_blueprint_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - superimposed_infection_on_ILD_background_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - organizing_pneumonia_on_ILD_background_v1
  - malignancy_on_fibrotic_ILD_background_v1
linked_future_modules:
  - temporal_comparison_methodology_v1
  - pulmonary_hypertension_in_fibrotic_ILD_context_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - emergency / acute care clinicians
  - intensivists
  - cardiologists
  - rheumatologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This reasoning map helps users evaluate vascular, edema, and hemorrhage mimics on a background of known or suspected interstitial lung disease.

It does not diagnose pulmonary edema, heart failure, renal failure, volume overload, pulmonary embolism, pulmonary infarction, pulmonary hypertension decompensation, diffuse alveolar hemorrhage, vasculitis, infection, acute exacerbation, drug toxicity, malignancy, or ILD progression.

It helps users ask:

- Is new GGO or consolidation actually edema?
- Is acute decline caused by pulmonary embolism, infarct, or vascular decompensation?
- Is diffuse GGO/consolidation hemorrhage rather than infection or acute exacerbation?
- Is smooth septal thickening meaningful or nonspecific?
- Are pleural effusions, dependent GGO, cardiomegaly, renal failure, or volume context present?
- Is there hemoptysis, anemia, anticoagulation, vasculitis, renal abnormality, or DAH context?
- Is there PE risk, infarct-like opacity, pulmonary hypertension, or right-heart strain context?
- What did the prior CT show?
- What clinical, laboratory, cardiac, renal, coagulation, vascular, and temporal data are missing?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    Acute GGO, consolidation, septal thickening, or clinical decline on ILD background should not automatically be labeled
    acute exacerbation, infection, drug toxicity, or progression before edema, vascular event, and hemorrhage are reviewed.

  platform_rule:
    - do_not_call_every_new_bilateral_GGO_acute_exacerbation
    - do_not_call_every_new_GGO_infection
    - do_not_call_smooth_septal_thickening_edema_without_clinical_context
    - do_not_ignore_PE_or_infarct_when_acute_decline_or_peripheral_opacity_is_present
    - do_not_ignore_DAH_when_GGO_occurs_with_hemoptysis_anemia_renal_or_vasculitis_context
    - preserve_edema_PE_hemorrhage_infection_AE_drug_toxicity_OP_and_malignancy_differential
```

### Teaching Point

The first question is not:

```text
Is this acute exacerbation or infection?
```

The better first question is:

```text
Could this acute opacity or decline be vascular, hydrostatic, or hemorrhagic rather than primary ILD activity?
```

---

## 2. Mimic Families

```yaml
vascular_edema_hemorrhage_families:
  pulmonary_edema_or_volume_overload:
    possible_features:
      - ground_glass_opacity
      - smooth_interlobular_septal_thickening
      - peribronchovascular_thickening
      - dependent_or_perihilar_distribution
      - pleural_effusions
      - cardiomegaly_or_vascular_congestion_context
    key_mimics:
      - acute_exacerbation
      - infection
      - drug_toxicity
      - hemorrhage
      - OP
      - fibrotic_progression

  pulmonary_embolism_or_pulmonary_infarct:
    possible_features:
      - acute_dyspnea_or_chest_pain_context
      - peripheral_wedge_shaped_opacity
      - pleural_based_opacity
      - infarct_like_consolidation
      - small_pleural_effusion_possible
      - right_heart_strain_context_when_available
    key_mimics:
      - pneumonia
      - organizing_pneumonia
      - malignancy
      - vasculitis
      - hemorrhage
      - atelectasis

  pulmonary_hypertension_or_right_heart_decompensation:
    possible_contexts:
      - advanced_fibrotic_ILD
      - sarcoidosis_or_fibrotic_sarcoidosis
      - chronic_HP
      - CTD_ILD
      - chronic_hypoxemia
    possible_features:
      - acute_or_subacute_dyspnea_disproportionate_to_CT_change
      - enlarged_pulmonary_artery_context
      - right_heart_strain_context
      - edema_or_effusion_context
      - vascular_decompensation_possible
    key_mimics:
      - acute_exacerbation
      - PE
      - infection
      - edema
      - simple_progression

  diffuse_alveolar_hemorrhage:
    possible_features:
      - diffuse_or_patchy_GGO
      - consolidation
      - crazy_paving_possible
      - rapid_change_possible
      - hemoptysis_may_be_present_or_absent
      - anemia_or_falling_hemoglobin_context
    key_mimics:
      - infection
      - acute_exacerbation
      - edema
      - drug_toxicity
      - OP
      - aspiration

  vasculitis_or_pulmonary_renal_context:
    possible_contexts:
      - ANCA_associated_vasculitis
      - anti_GBM_context
      - connective_tissue_disease
      - renal_abnormality
      - hematuria_or_proteinuria
    possible_features:
      - GGO_or_consolidation_from_DAH
      - cavitating_nodules_when_GPA_context
      - systemic_vasculitis_clues
    key_mimics:
      - infection
      - malignancy
      - sarcoidosis_or_granulomatous_disease
      - drug_toxicity
      - acute_exacerbation

  anticoagulation_or_coagulopathy_related_bleeding:
    possible_contexts:
      - anticoagulation
      - thrombocytopenia
      - coagulopathy
      - hematologic_malignancy_or_treatment_context
    possible_features:
      - diffuse_or_patchy_GGO
      - consolidation
      - anemia_context
      - bleeding_risk_context
    key_mimics:
      - infection
      - edema
      - acute_exacerbation
      - drug_toxicity
```

---

## 3. Core Distinction

```yaml
core_distinction:
  edema_pathway:
    reasoning_center: new_GGO_or_septal_thickening_with_cardiac_renal_volume_or_hydrostatic_context
    supportive_clues:
      - smooth_interlobular_septal_thickening
      - dependent_or_perihilar_GGO
      - pleural_effusions
      - cardiomegaly_or_heart_failure_context
      - renal_failure_context
      - volume_overload_context
      - improvement_after_diuresis_or_volume_management_when_known
    danger_statement: edema_can_mimic_AE_infection_or_drug_toxicity_and_requires_cardiac_renal_volume_context

  PE_or_infarct_pathway:
    reasoning_center: acute_vascular_event_causing_dyspnea_chest_pain_hypoxemia_or_peripheral_opacity_on_ILD_background
    supportive_clues:
      - acute_dyspnea_or_pleuritic_chest_pain
      - PE_risk_context
      - peripheral_wedge_shaped_or_pleural_based_opacity
      - unexplained_hypoxemia_disproportionate_to_parenchymal_change
      - right_heart_strain_context_when_available
      - CTPA_or_vascular_imaging_context_when_available
    danger_statement: PE_or_infarct_can_be_missed_if_all_acute_decline_is_attributed_to_ILD_or_infection

  hemorrhage_pathway:
    reasoning_center: diffuse_or_patchy_alveolar_opacity_with_bleeding_vasculitis_anticoagulation_anemia_or_pulmonary_renal_context
    supportive_clues:
      - hemoptysis
      - falling_hemoglobin_or_anemia_context
      - diffuse_or_patchy_GGO
      - crazy_paving_possible
      - anticoagulation_or_coagulopathy_context
      - renal_or_urinalysis_abnormality
      - vasculitis_or_autoimmune_context
      - BAL_or_clinical_hemorrhage_context_when_available
    danger_statement: hemorrhage_can_mimic_AE_infection_edema_or_drug_toxicity_and_may_require_urgent_review

  acute_exacerbation_or_infection_mimic_pathway:
    reasoning_center: new_alveolar_opacity_on_fibrotic_ILD_background_where_AE_or_infection_remain_possible_but_not_exclusive
    supportive_clues:
      - new_bilateral_GGO_or_consolidation
      - acute_or_subacute_respiratory_worsening
      - fever_or_microbiology_when_infection_possible
      - fibrotic_background_when_AE_possible
    danger_statement: AE_or_infection_should_not_be_called_before_edema_PE_and_hemorrhage_review_when_clues_exist
```

---

## 4. Direct Comparison Matrix

| Feature | More Edema-like | More PE/Infarct-like | More Hemorrhage-like | More AE/Infection-like |
|---|---|---|---|---|
| GGO distribution | Dependent/perihilar possible | May be focal/peripheral if infarct | Diffuse or patchy | Diffuse, focal, airway-centered depending cause |
| Septal thickening | Smooth septal thickening supports edema context | Not defining | Crazy paving possible | Can occur nonspecifically |
| Pleural effusion | Supports edema/volume context | Small effusion possible with infarct | Not defining | Can occur with infection |
| Peripheral wedge opacity | Not classic | Supports infarct context | Possible mimic | Pneumonia/OP/malignancy can mimic |
| Hemoptysis | Not typical driver | Possible | High-value hemorrhage clue | Infection can also cause |
| Anemia / falling Hb | Not typical driver | Possible if hemorrhagic infarct | High-value DAH clue | Not defining |
| Cardiac/renal context | High-value | PE risk may coexist | Renal vasculitis context matters | Comorbidity may confuse |
| Urinalysis abnormality | Not edema-specific | Not PE-specific | Pulmonary-renal vasculitis clue | Can suggest broader systemic disease |
| Fever/microbiology | Not central | Not central | May coexist | Supports infection |
| Prior CT | Shows newness and background | Shows new infarct-like opacity | Shows rapid change/resolution | Essential for AE/progression |

---

## 5. Entry Scenarios

### 5.1 Smooth Septal Thickening + GGO on Fibrotic ILD Background

```yaml
scenario_smooth_septal_GGO_on_fibrotic_ILD:
  problem:
    - background_fibrotic_ILD
    - new_GGO
    - smooth_interlobular_septal_thickening
    - edema_AE_infection_drug_toxicity_hemorrhage_possible

  edema_leaning_features:
    - smooth_septal_thickening
    - pleural_effusions
    - dependent_or_perihilar_GGO
    - heart_failure_context
    - renal_failure_or_volume_overload
    - response_to_diuresis_when_known

  AE_or_infection_leaning_features:
    - acute_respiratory_worsening
    - fever_or_microbiology_context
    - diffuse_bilateral_GGO_without_sufficient_volume_explanation
    - immunosuppression_or_infectious_risk

  hemorrhage_or_drug_mimic_features:
    - hemoptysis_or_anemia
    - anticoagulation_or_vasculitis_context
    - medication_or_treatment_timeline

  missing_pieces:
    - prior_CT
    - cardiac_status
    - renal_function_and_fluid_balance
    - BNP_or_echo_context_if_available
    - infection_review
    - medication_timeline
    - hemoptysis_anemia_context
    - MDD_or_urgent_review

  pitfall:
    - Smooth_septal_GGO_should_not_be_labeled_AE_without_edema_and_volume_review
```

### 5.2 Peripheral Wedge-shaped Opacity on ILD Background

```yaml
scenario_peripheral_wedge_opacity:
  problem:
    - background_ILD
    - new_peripheral_or_pleural_based_wedge_like_opacity
    - PE_infarct_infection_OP_malignancy_possible

  PE_or_infarct_leaning_features:
    - acute_pleuritic_chest_pain
    - acute_dyspnea_or_hypoxemia
    - PE_risk_context
    - pleural_based_wedge_shape
    - small_pleural_effusion_context
    - vascular_imaging_support_when_available

  infection_or_OP_leaning_features:
    - fever_or_microbiology
    - OP_like_peripheral_consolidation
    - migratory_or_waxing_waning_behavior
    - aspiration_or_airway_context

  malignancy_or_other_mimic_features:
    - persistent_or_growing_focal_opacity
    - cancer_history
    - suspicious_nodes
    - cavitation_or_mass_like_morphology

  missing_pieces:
    - PE_risk_assessment
    - chest_pain_and_acuity_context
    - vascular_imaging_or_CTPA_context_if_available
    - infection_review
    - prior_CT_or_follow_up_CT
    - cancer_history
    - MDD_review

  pitfall:
    - Peripheral_wedge_like_opacity_should_not_be_assumed_pneumonia_or_OP_without_PE_infarct_review
```

### 5.3 Acute Diffuse GGO with Hemoptysis or Anemia

```yaml
scenario_diffuse_GGO_hemoptysis_anemia:
  problem:
    - background_ILD
    - acute_or_subacute_diffuse_GGO_or_consolidation
    - hemoptysis_or_anemia_context_possible

  hemorrhage_leaning_features:
    - hemoptysis
    - falling_hemoglobin
    - diffuse_or_patchy_GGO
    - crazy_paving_possible
    - anticoagulation_or_coagulopathy
    - vasculitis_or_autoimmune_context
    - renal_or_urinalysis_abnormality

  AE_or_infection_leaning_features:
    - acute_respiratory_deterioration
    - fever_or_microbiology_context
    - fibrotic_ILD_background
    - no_bleeding_or_renal_context_after_review

  drug_or_treatment_mimic_features:
    - medication_or_cancer_therapy_timeline
    - drug_related_hemorrhagic_or_DAD_like_context
    - immunosuppression

  missing_pieces:
    - hemoglobin_trend
    - hemoptysis_history
    - anticoagulation_or_coagulation_status
    - urinalysis_and_renal_function
    - ANCA_or_autoimmune_context_if_relevant
    - infection_review
    - medication_timeline
    - urgent_review

  pitfall:
    - Acute_diffuse_GGO_with_anemia_or_hemoptysis_should_trigger_DAH_review_not_only_AE_or_infection
```

### 5.4 Acute Decline Disproportionate to CT Change

```yaml
scenario_acute_decline_disproportionate_to_CT:
  problem:
    - known_or_suspected_ILD
    - acute_clinical_decline
    - CT_parenchymal_change_mild_or_disproportionate

  vascular_leaning_features:
    - PE_risk_context
    - pulmonary_hypertension_context
    - right_heart_strain_context
    - chest_pain_or_syncope
    - hypoxemia_disproportionate_to_imaging

  infection_AE_edema_mimics:
    - fever_or_sepsis
    - volume_overload_or_effusions
    - new_bilateral_GGO
    - medication_toxicity_context

  missing_pieces:
    - PE_risk_assessment
    - CTPA_or_vascular_imaging_context_if_available
    - pulmonary_hypertension_or_echo_context
    - oxygen_requirement_trend
    - cardiac_status
    - infection_review
    - prior_CT
    - urgent_review

  pitfall:
    - Disproportionate_decline_should_not_be_explained_by_stable_ILD_without_PE_PH_cardiac_and_infection_review
```

### 5.5 Pulmonary-Renal / Vasculitic Hemorrhage Context

```yaml
scenario_pulmonary_renal_vasculitic_context:
  problem:
    - ILD_or_granulomatous_background_possible
    - new_GGO_or_consolidation
    - renal_or_vasculitis_context_possible

  DAH_or_vasculitis_leaning_features:
    - hemoptysis_or_anemia
    - hematuria
    - proteinuria
    - rising_creatinine
    - ANCA_or_autoimmune_context
    - cavitating_nodules_if_GPA_context
    - systemic_vasculitis_clues

  infection_or_drug_mimic_features:
    - fever_or_microbiology
    - immunosuppression
    - medication_or_treatment_context
    - diffuse_GGO_or_DAD_like_pattern

  missing_pieces:
    - urinalysis
    - creatinine_and_renal_trend
    - hemoglobin_trend
    - ANCA_autoimmune_testing_context_if_relevant
    - infection_review
    - medication_timeline
    - rheumatology_nephrology_or_MDD_review

  pitfall:
    - Pulmonary_renal_clues_should_not_be_missed_when_diffuse_GGO_is_seen_on_ILD_background
```

---

## 6. Why Not Engine

### Why not edema?

```yaml
why_not_edema:
  - no_cardiac_renal_or_volume_overload_context
  - no_pleural_effusions_or_expected_dependent_pattern_when_relevant
  - focal_airway_centered_or_cavitary_pattern
  - microbiology_or_infectious_context_stronger
  - hemoptysis_anemia_or_vasculitis_context_stronger
  - PE_or_infarct_context_stronger
  - findings_persist_despite_volume_management_when_known
```

### Why not PE / infarct?

```yaml
why_not_PE_or_infarct:
  - no_PE_risk_or_vascular_context_after_review
  - opacity_not_peripheral_or_infarct_like_when_relevant
  - symptoms_and_imaging_better_explained_by_infection_edema_AE_or_OP
  - vascular_imaging_not_supportive_when_available
  - persistent_growth_suggests_malignancy_or_OP_mimic

```

### Why not hemorrhage / DAH?

```yaml
why_not_hemorrhage_or_DAH:
  - no_hemoptysis_anemia_or_falling_hemoglobin_context_after_review
  - no_anticoagulation_coagulopathy_or_vasculitis_context
  - no_renal_or_urinalysis_abnormality_when_relevant
  - infection_edema_AE_or_drug_toxicity_context_stronger
  - BAL_or_clinical_context_not_supportive_when_available
```

### Why not acute exacerbation?

```yaml
why_not_acute_exacerbation:
  - edema_or_volume_overload_context_sufficient
  - PE_or_infarct_context_present
  - hemoptysis_anemia_or_DAH_context_present
  - infection_or_drug_toxicity_not_reviewed
  - prior_CT_not_reviewed
  - CT_change_not_new_or_not_bilateral_alveolar_abnormality
```

### Why not infection?

```yaml
why_not_infection:
  - cardiac_volume_context_stronger
  - PE_or_infarct_context_stronger
  - hemoptysis_anemia_or_renal_vasculitis_context_stronger
  - no_infectious_symptoms_or_microbiology_after_review
  - rapid_improvement_with_volume_management_when known
```

---

## 7. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether opacity is new, resolving, progressive, chronic, or technical.

    clinical_time_course:
      reason: Hours, days, weeks, or months helps separate edema, PE, DAH, infection, AE, OP, or progression.

    cardiac_status:
      reason: Heart failure, valvular disease, pulmonary venous hypertension, and volume overload can explain GGO/septal thickening.

    renal_function_and_fluid_balance:
      reason: Renal failure or volume overload may support edema and also reveal pulmonary-renal context when abnormal.

    BNP_echo_or_right_heart_context:
      reason: Cardiac and right-heart data may clarify edema, pulmonary hypertension, or PE-related decompensation.

    PE_risk_and_vascular_context:
      reason: Acute dyspnea, pleuritic chest pain, immobility, cancer, thrombosis risk, and pulmonary hypertension matter.

    oxygen_requirement_trend:
      reason: Rapid oxygen escalation increases urgency and broadens acute mimic review.

    hemoptysis_and_hemoglobin_trend:
      reason: Hemoptysis may be absent, but falling hemoglobin can support hemorrhage context.

    anticoagulation_and_coagulation_status:
      reason: Bleeding risk can redirect diffuse GGO/consolidation toward hemorrhage.

    urinalysis_and_autoimmune_context:
      reason: Hematuria, proteinuria, renal dysfunction, ANCA/autoimmune context may support pulmonary-renal vasculitis.

    infection_review:
      reason: Infection can mimic edema, PE/infarct, hemorrhage, and AE.

    medication_and_treatment_timeline:
      reason: Drug toxicity can mimic DAH, edema, AE, OP, or infection.

    MDD_or_urgent_review:
      reason: Vascular, edema, and hemorrhage mimics often require acute multidisciplinary integration.
```

---

## 8. Red Flag Panel

```yaml
red_flags:
  edema_red_flags:
    - smooth_interlobular_septal_thickening
    - dependent_or_perihilar_GGO
    - pleural_effusions
    - cardiac_failure_context
    - renal_failure_or_volume_overload
    - rapid_improvement_after_diuresis_when_known

  PE_or_vascular_red_flags:
    - acute_dyspnea_disproportionate_to_CT_change
    - pleuritic_chest_pain
    - PE_risk_context
    - peripheral_wedge_shaped_opacity
    - pulmonary_hypertension_or_right_heart_strain_context
    - cancer_or_immobility_thrombosis_context

  hemorrhage_red_flags:
    - hemoptysis
    - falling_hemoglobin_or_unexplained_anemia
    - diffuse_or_patchy_GGO
    - crazy_paving_possible
    - anticoagulation_or_coagulopathy
    - renal_or_urinalysis_abnormality
    - vasculitis_or_autoimmune_context

  overlap_red_flags:
    - severe_immunosuppression
    - medication_or_cancer_therapy_timeline
    - fever_or_sepsis_context
    - cavitation
    - persistent_focal_opacity
    - rapidly_increasing_oxygen_requirement
```

---

## 9. Temporal Reasoning

```yaml
temporal_reasoning:
  minutes_to_hours:
    consider:
      - pulmonary_embolism
      - acute_edema
      - hemorrhage
      - aspiration
      - severe_acute_cardiac_event
    caution:
      - CT_parenchymal_change_may_lag_or_be_disproportionate

  hours_to_days:
    consider:
      - edema
      - infection
      - PE_or_infarct
      - DAH
      - drug_reaction
      - acute_exacerbation

  days_to_weeks:
    consider:
      - infection
      - acute_exacerbation
      - drug_toxicity
      - OP
      - evolving_infarct
      - hemorrhage_resolution_or_recurrence

  rapid_improvement:
    possible_explanations:
      - edema_response_to_diuresis
      - hemorrhage_resolution_if_bleeding_stops
      - infection_response
      - technical_or_inspiratory_difference
    caution:
      - rapid_improvement_does_not_prove_one_pathway_without_context

  persistence_or_growth:
    consider:
      - malignancy
      - OP
      - chronic_infection
      - unresolved_infarct
      - fibrosis_or_scar
    caution:
      - persistent_focal_abnormality_requires_reassessment
```

---

## 10. Diagnostic Escalation Logic

```yaml
diagnostic_escalation_logic:
  urgent_review_high_value_if:
    - rapidly_increasing_oxygen_requirement
    - suspected_PE_or_right_heart_strain
    - hemoptysis_or_falling_hemoglobin
    - severe_diffuse_GGO_or_consolidation
    - renal_abnormality_with_pulmonary_opacity
    - hemodynamic_instability
    - AE_infection_edema_PE_DAH_overlap_in_unstable_patient

  cardiology_or_volume_review_high_value_if:
    - smooth_septal_thickening_with_effusions
    - heart_failure_or_volume_context
    - renal_failure_or_fluid_overload
    - edema_vs_AE_or_infection_uncertain

  vascular_or_PE_review_high_value_if:
    - acute_dyspnea_disproportionate_to_CT
    - pleuritic_chest_pain
    - peripheral_wedge_opacity
    - PE_risk_context
    - pulmonary_hypertension_decompensation_context

  rheumatology_nephrology_review_high_value_if:
    - DAH_possible
    - hematuria_or_proteinuria
    - rising_creatinine
    - ANCA_or_autoimmune_context
    - pulmonary_renal_syndrome_context

  infectious_disease_review_high_value_if:
    - fever_or_sepsis
    - immunosuppression
    - cavitation_or_tree_in_bud
    - infection_vs_DAH_edema_AE_uncertain

  MDD_strongly_recommended_if:
    - AE_vs_infection_vs_edema_vs_DAH_uncertain
    - PE_or_infarct_vs_OP_infection_malignancy_uncertain
    - clinical_decline_disproportionate_to_parenchymal_CT_change
    - treatment_decision_depends_on_distinguishing_mimics
    - prior_CT_and_clinical_data_conflict
```

---

## 11. Pitfall Library

```yaml
pitfalls:
  - title: Calling smooth septal GGO acute exacerbation.
    correction: Edema and volume overload require cardiac, renal, fluid, effusion, and response-context review.

  - title: Calling peripheral wedge opacity pneumonia.
    correction: Pulmonary embolism and infarct must remain visible when opacity is pleural-based or wedge-like.

  - title: Ignoring DAH when hemoptysis is absent.
    correction: Hemoptysis may be absent; anemia, renal findings, anticoagulation, or vasculitis context matter.

  - title: Explaining disproportionate dyspnea by stable ILD.
    correction: PE, pulmonary hypertension decompensation, cardiac disease, infection, and anemia should remain visible.

  - title: Treating GGO as specific.
    correction: GGO can reflect edema, hemorrhage, infection, AE, drug toxicity, OP, or technical factors.

  - title: Ignoring renal and urinalysis data.
    correction: Pulmonary-renal vasculitis can present with lung opacity and renal abnormalities.

  - title: Treating rapid improvement as proof of edema.
    correction: Improvement can also occur with infection, hemorrhage resolution, OP, or technical differences.

  - title: Letting baseline ILD swallow acute vascular disease.
    correction: Known ILD does not exclude PE, infarct, edema, pulmonary hypertension decompensation, or hemorrhage.
```

---

## 12. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - superimposed_events_core_blueprint_v1
    - acute_exacerbation_vs_infection_vs_edema_v1
    - pulmonary_edema_CT_review_sources
    - diffuse_alveolar_hemorrhage_clinical_imaging_review_sources
    - pulmonary_infarction_PE_review_sources

  supportive_sources:
    - interlobular_septal_thickening_CT_review_2024
    - pulmonary_edema_CT_imaging_review_2020
    - DAH_clinical_imaging_review_2013
    - pulmonary_infarction_in_acute_PE_review_2021
    - pulmonary_hypertension_in_ILD_review_sources_pending
    - PE_in_fibrotic_ILD_or_chronic_lung_disease_sources_pending

  evidence_notes:
    - Smooth septal thickening with GGO and pleural effusions can support edema in the right clinical context.
    - DAH can present with GGO and consolidation and requires clinical/laboratory context.
    - Pulmonary infarction may appear as peripheral pleural-based or wedge-like opacity in PE context.
    - Acute exacerbation reasoning should preserve alternative explanations such as infection, edema, PE, hemorrhage, and drug toxicity.
    - Public-ready use requires full source review and expert review.
```

---

## 13. MVP Test Case

```yaml
case_test_vascular_edema_hemorrhage_panel_001:
  input:
    age: 76
    sex: male
    known_background:
      - fibrotic_ILD
      - UIP_like_pattern
    new_hrct:
      - new_bilateral_ground_glass_opacity
      - smooth_interlobular_septal_thickening
      - small_bilateral_pleural_effusions
      - background_honeycombing
      - traction_bronchiectasis
      - no_new_mass_reported
    history:
      dyspnea_worsening: acute_5_days
      oxygen_requirement_change: increased
      fever: unknown
      chest_pain: unknown
      hemoptysis: unknown
      heart_failure_history: unknown
      renal_function: unavailable
      anticoagulation: unknown
      PE_risk_context: unknown
      prior_CT: available_but_not_reviewed
    labs:
      WBC: unavailable
      CRP: unavailable
      BNP: unavailable
      creatinine: unavailable
      hemoglobin_trend: unavailable
      urinalysis: unavailable
    microbiology:
      unavailable

  output:
    reasoning_state: acute_GGO_on_fibrotic_ILD_with_edema_DAH_PE_AE_infection_overlap
    edema_support:
      - smooth_interlobular_septal_thickening
      - small_bilateral_pleural_effusions
      - new_bilateral_GGO
    acute_exacerbation_support:
      - fibrotic_ILD_background
      - acute_worsening
      - new_bilateral_GGO
    infection_support:
      - fever_and_microbiology_unknown
    hemorrhage_or_vascular_support:
      - hemoptysis_anemia_PE_risk_and_renal_context_unknown
    cannot_conclude:
      - pulmonary_edema
      - acute_exacerbation
      - infection_excluded
      - diffuse_alveolar_hemorrhage_excluded
      - pulmonary_embolism_or_infarct_excluded
      - drug_toxicity_excluded
    missing_pieces:
      - prior_CT_review
      - cardiac_status_BNP_or_echo_context
      - renal_function_and_fluid_balance
      - infection_labs_and_microbiology
      - PE_risk_and_chest_pain_context
      - hemoptysis_and_hemoglobin_trend
      - anticoagulation_and_coagulation_status
      - urinalysis_or_autoimmune_context
      - medication_and_treatment_timeline
      - urgent_or_MDD_review
    final_prompt:
      - What vascular, cardiac, renal, hemorrhagic, infectious, and temporal evidence is missing before calling this edema, AE, infection, PE, or DAH?
```

---

## 14. Final Page Prompt

Every Vascular / Edema / Hemorrhage Mimic Panel page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. Is the new finding diffuse GGO, smooth-septal GGO, dependent/perihilar opacity, peripheral wedge opacity, focal consolidation, or hemorrhage-like opacity?
4. Is cardiac failure, renal failure, volume overload, or response to diuresis context present?
5. Is PE risk, chest pain, infarct-like opacity, pulmonary hypertension, or right-heart strain context present?
6. Is hemoptysis, anemia, anticoagulation, coagulopathy, renal abnormality, urinalysis abnormality, or vasculitis context present?
7. Is infection, acute exacerbation, drug toxicity, OP, aspiration, or malignancy still possible?
8. Is urgent review, cardiology, vascular/PE review, nephrology, rheumatology, infectious disease review, or MDD needed?
9. What do we still not know?
```