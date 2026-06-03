# Superimposed Events Core Blueprint — v1

## Document Metadata

```yaml
id: reasoning_superimposed_events_core_blueprint_v1
title: Superimposed Events Core Blueprint
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: reasoning_core_blueprint
diagnostic_authority: none
module_version: v0.3
last_updated: draft
```

---

## 0. Purpose

This blueprint defines the Superimposed Events Core of the ILD Reasoning Platform.

The purpose is to help users reason through new or changing findings on a background of known or suspected interstitial lung disease.

It does not diagnose infection, malignancy, acute exacerbation, organizing pneumonia, edema, pulmonary embolism, drug toxicity, aspiration, hemorrhage, or ILD progression.

It helps users ask:

- Is this true ILD progression?
- Is this a new superimposed process?
- Is the change inflammatory, infectious, vascular, malignant, drug-related, or treatment-related?
- Is the abnormality focal, multifocal, diffuse, symmetric, dependent, airway-centered, or vascular?
- What did the prior CT show?
- What clinical/laboratory/treatment data are missing?
- Is urgent review needed?
- What do we still not know?

---

## 1. Core Principle

```yaml
core_principle:
  main_statement: >
    New findings on fibrotic or inflammatory ILD should not automatically be interpreted as baseline ILD progression.

  platform_rule:
    - do_not_call_every_new_ground_glass_progression
    - do_not_call_every_new_consolidation_organizing_pneumonia
    - do_not_call_every_new_nodule_malignancy
    - do_not_call_every_rapid_decline_acute_exacerbation
    - preserve_superimposed_event_differential_until_context_is_reviewed
```

### Teaching Point

The key question is not:

```text
Has the ILD worsened?
```

The better first question is:

```text
What new process may have appeared on top of the ILD background?
```

---

## 2. Core Superimposed Event Families

```yaml
superimposed_event_families:
  infection:
    role: common_and_high_risk_mimic_of_progression
    examples:
      - bacterial_pneumonia
      - viral_pneumonia
      - fungal_infection
      - TB_or_NTM_context
      - opportunistic_infection
      - aspiration_related_infection

  acute_exacerbation_or_acute_lung_injury:
    role: acute_deterioration_with_new_diffuse_alveolar_abnormality_on_ILD_background
    examples:
      - acute_exacerbation_of_IPF
      - acute_exacerbation_of_non_IPF_fibrotic_ILD
      - diffuse_alveolar_damage_pattern_context
      - acute_inflammatory_lung_injury

  organizing_pneumonia_or_inflammatory_flare:
    role: potentially_reversible_or_treatment_related_inflammatory_superimposed_pattern
    examples:
      - OP_like_consolidation
      - perilobular_opacity
      - migratory_consolidation
      - CTD_ILD_flare_context
      - drug_or_radiation_related_OP

  pulmonary_edema_or_cardiogenic_mimic:
    role: non_ILD_process_that_can_create_new_GGO_or_septal_thickening
    examples:
      - hydrostatic_edema
      - volume_overload
      - cardiac_failure_context
      - renal_failure_context

  pulmonary_embolism_or_vascular_event:
    role: vascular_process_that_can_cause_acute_decline_or_peripheral_opacity
    examples:
      - pulmonary_embolism
      - pulmonary_infarct
      - pulmonary_hypertension_decompensation
      - vascular_complication_in_fibrotic_lung

  malignancy_or_new_focal_lesion:
    role: focal_or_progressive_lesion_hidden_by_background_fibrosis
    examples:
      - lung_cancer_on_fibrotic_background
      - lymphoma_or_metastatic_disease
      - sarcoid_like_reaction_in_oncology_context
      - new_nodule_or_mass

  drug_or_treatment_related_lung_injury:
    role: medication_or_cancer_treatment_related_new_lung_abnormality
    examples:
      - immune_checkpoint_inhibitor_pneumonitis
      - chemotherapy_related_lung_injury
      - amiodarone_toxicity
      - nitrofurantoin_toxicity
      - methotrexate_or_DMARD_context
      - radiation_pneumonitis

  aspiration_or_airway_event:
    role: dependent_or_airway_centered_process_mimicking_ILD_worsening
    examples:
      - aspiration_pneumonitis
      - aspiration_pneumonia
      - airway_impaction
      - tree_in_bud_or_bronchiolitis_context

  hemorrhage:
    role: acute_GGO_or_consolidation_from_bleeding_context
    examples:
      - diffuse_alveolar_hemorrhage
      - vasculitis_related_hemorrhage
      - anticoagulation_context
      - hemoptysis_context
```

---

## 3. Entry Triggers

```yaml
entry_triggers:
  new_ground_glass_on_ILD_background:
    route_to:
      - infection_review
      - acute_exacerbation_review
      - edema_review
      - drug_toxicity_review
      - hemorrhage_review
      - OP_or_inflammatory_flare_review

  new_consolidation:
    route_to:
      - infection_review
      - organizing_pneumonia_review
      - aspiration_review
      - malignancy_review_if_persistent_or_focal
      - drug_or_radiation_related_OP_review

  new_nodule_or_mass:
    route_to:
      - malignancy_review
      - infection_review
      - inflammatory_nodule_review
      - sarcoid_like_reaction_review_if_oncology_context
      - vasculitis_review_if_cavitary_or_multiple

  rapid_diffuse_worsening:
    route_to:
      - acute_exacerbation_review
      - infection_review
      - edema_review
      - pulmonary_embolism_review
      - drug_toxicity_review
      - hemorrhage_review

  new_cavitation:
    route_to:
      - infection_review
      - GPA_or_vasculitis_review
      - malignancy_review
      - rheumatoid_nodule_context_review
      - septic_emboli_review

  discordant_clinical_decline:
    route_to:
      - PE_review
      - cardiac_or_pulmonary_hypertension_review
      - occult_infection_review
      - drug_toxicity_review
      - acute_exacerbation_review
```

---

## 4. Pattern Interaction Matrix

| New finding on ILD background | Do not assume | Must consider |
|---|---|---|
| New diffuse GGO | Progression | Infection, acute exacerbation, edema, hemorrhage, drug toxicity |
| New consolidation | OP only | Infection, aspiration, OP, malignancy, drug/radiation injury |
| New nodule/mass | Scar or fibrosis | Lung cancer, infection, inflammatory nodule, metastasis |
| New cavitation | Atypical ILD | Infection, GPA, malignancy, aspergilloma, septic emboli |
| Rapid worsening | Acute exacerbation only | Infection, PE, edema, hemorrhage, drug toxicity |
| Increased reticulation | Fibrotic progression | Technical difference, inspiratory effort, true progression, treatment effect |
| Decreased GGO | Fibrosis reversed | Resolving inflammation, edema, infection, OP, exposure removal |
| Persistent focal opacity | Slow ILD change | Malignancy, chronic infection, OP, atelectasis |

---

## 5. Temporal Reasoning Model

```yaml
temporal_reasoning_model:
  progression:
    definition_for_platform: worsening_of_fibrotic_or_structural_disease_over_time
    requires:
      - prior_CT_or_longitudinal_imaging
      - technical_comparability_review
      - clinical_context
    imaging_clues:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_honeycombing
      - increasing_architectural_distortion
      - increasing_volume_loss

  stabilization:
    definition_for_platform: no_meaningful_worsening_in_fibrotic_burden_or_clinical_trajectory
    requires:
      - comparable_prior_imaging_or_PFT_context
    caution:
      - stable_disease_can_remain_diagnostically_uncertain

  regression_or_partial_improvement:
    definition_for_platform: reduction_of_reversible_component_without_assuming_fibrosis_reversal
    possible_explanations:
      - resolving_infection
      - resolving_edema
      - resolving_OP
      - reduced_inflammatory_component
      - exposure_control
      - treatment_response
    caution:
      - improvement_of_GGO_or_consolidation_does_not_prove_fibrosis_reversed

  unexpectedly_fast_worsening:
    definition_for_platform: decline_too_fast_for_simple_chronic_fibrosis_progression
    must_consider:
      - infection
      - acute_exacerbation
      - pulmonary_embolism
      - edema
      - hemorrhage
      - drug_toxicity
      - malignancy
      - aspiration
```

---

## 6. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Determines whether the finding is new, stable, resolving, progressive, or technical.

    time_course:
      reason: Hours-days-weeks-months pattern changes the differential.

    symptom_change:
      reason: Fever, dyspnea, cough, hemoptysis, chest pain, aspiration, or systemic decline redirect reasoning.

    oxygen_requirement:
      reason: Acute oxygen change supports urgent superimposed process review.

    infection_data:
      reason: Fever, WBC, CRP, cultures, viral testing, immunosuppression, and exposure context may change reasoning.

    medication_and_treatment_timeline:
      reason: Drug toxicity, ICI pneumonitis, chemotherapy injury, radiation injury, and immunosuppression complications require timeline.

    cardiac_and_volume_context:
      reason: Edema can mimic inflammatory or infectious GGO.

    PE_or_vascular_context:
      reason: Acute dyspnea, chest pain, risk factors, pulmonary hypertension, or infarct-like opacity require vascular review.

    cancer_history:
      reason: New nodules, masses, lymphadenopathy, or persistent consolidation require malignancy review.

    immune_status:
      reason: Opportunistic infection, GLILD, treatment complications, and unusual pathogens require immune context.

    technical_CT_comparability:
      reason: Slice thickness, inspiration, motion, kernel, contrast, and positioning can create false change.

    MDD_review:
      reason: Superimposed events often require radiology, pulmonology, infectious disease, oncology, cardiology, rheumatology, and pathology integration.
```

---

## 7. Red Flag Panel

```yaml
red_flags:
  new_diffuse_GGO:
    concern:
      - infection
      - acute_exacerbation
      - edema
      - hemorrhage
      - drug_toxicity
    prompt:
      - New diffuse GGO is not automatically ILD progression.

  new_focal_nodule_or_mass:
    concern:
      - malignancy
      - infection
      - inflammatory_nodule
      - metastasis
    prompt:
      - Do not let background fibrosis hide a focal lesion.

  new_persistent_consolidation:
    concern:
      - infection
      - organizing_pneumonia
      - malignancy
      - aspiration
      - drug_or_radiation_injury
    prompt:
      - Persistence, asymmetry, or growth requires reassessment.

  new_cavitation:
    concern:
      - infection
      - GPA_or_vasculitis
      - malignancy
      - septic_emboli
      - rheumatoid_nodule_context
    prompt:
      - Cavitation is a high-risk red flag.

  rapid_clinical_decline:
    concern:
      - acute_exacerbation
      - infection
      - PE
      - edema
      - hemorrhage
      - drug_toxicity
    prompt:
      - Do not rely on the baseline ILD label alone.

  hemoptysis_or_anemia_with_GGO:
    concern:
      - diffuse_alveolar_hemorrhage
      - vasculitis
      - infection
      - anticoagulation_related_bleeding
    prompt:
      - Hemorrhage context requires urgent clinical review.

  new_or_asymmetric_lymphadenopathy:
    concern:
      - malignancy
      - lymphoma
      - infection
      - sarcoid_like_reaction
    prompt:
      - Nodes must be interpreted with oncology, infection, and temporal context.
```

---

## 8. Core Submodules Planned

```yaml
core_submodules_planned:
  infection_on_ILD_background:
    path: docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    status: planned

  acute_exacerbation_vs_infection_vs_edema:
    path: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    status: planned

  organizing_pneumonia_on_ILD_background:
    path: docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    status: planned

  malignancy_on_fibrotic_ILD_background:
    path: docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
    status: planned

  drug_toxicity_or_treatment_related_lung_injury:
    path: docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
    status: planned

  pulmonary_edema_PE_hemorrhage_mimic_panel:
    path: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
    status: planned

  temporal_comparison_methodology:
    path: docs/reasoning/temporal_comparison_methodology_v1.md
    status: planned
```

---

## 9. Evidence Backbone Initial Sources

```yaml
evidence_backbone_initial_sources:
  IPF_PPF_framework:
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF

  acute_exacerbation_framework:
    - AE_IPF_revised_definition_and_review_sources
    - acute_exacerbation_non_IPF_fibrotic_ILD_sources_pending

  drug_toxicity_framework:
    - drug_induced_ILD_HRCT_pattern_review
    - checkpoint_inhibitor_drug_related_pneumonitis_Fleischner_white_paper

  cancer_fibrosis_framework:
    - lung_cancer_in_fibrotic_ILD_review_sources_pending
    - focal_lesion_on_fibrotic_background_sources_pending

  infection_framework:
    - infection_on_ILD_background_review_sources_pending
    - opportunistic_infection_in_immunosuppressed_ILD_sources_pending

  organizing_pneumonia_framework:
    - organizing_pneumonia_HRCT_and_ILD_overlap_sources_pending

  vascular_edema_hemorrhage_framework:
    - PE_edema_DAH_mimic_sources_pending
```

---

## 10. Evidence Safety Rule

```yaml
evidence_safety_rule:
  platform_must_not:
    - diagnose_acute_exacerbation_from_GGO_alone
    - diagnose_infection_from_consolidation_alone
    - diagnose_malignancy_from_nodule_alone
    - diagnose_drug_toxicity_without_medication_timeline
    - diagnose_PE_without_vascular_context
    - diagnose_edema_without_cardiac_or_volume_context
    - call_progression_without_prior_CT_or_longitudinal_context
    - recommend_treatment

  platform_must:
    - preserve_superimposed_event_differential
    - request_prior_CT_when_available
    - request_clinical_time_course
    - request_treatment_and_medication_timeline
    - show_red_flags
    - separate_progression_from_superimposed_events
    - trigger_urgent_or_MDD_review_when high_risk_context_exists
```

---

## 11. MVP Test Case

```yaml
case_test_superimposed_events_core_001:
  input:
    age: 68
    sex: male
    known_background:
      - fibrotic_ILD
      - UIP_like_pattern
    new_hrct:
      - new_bilateral_ground_glass_opacity
      - background_reticulation
      - traction_bronchiectasis
      - no_new_mass_reported
    history:
      symptom_timing: acute_worsening_over_2_weeks
      fever: unknown
      oxygen_requirement_change: increased
      medication_timeline: unknown
      cardiac_status: unknown
      PE_risk_context: unknown
      infection_testing: unavailable
      prior_CT: available_but_not_reviewed

  output:
    reasoning_state: new_diffuse_GGO_on_fibrotic_ILD_background
    cannot_conclude:
      - acute_exacerbation
      - infection_excluded
      - pulmonary_edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded
      - simple_fibrotic_progression
    missing_pieces:
      - prior_CT_review
      - symptom_time_course
      - infection_review
      - oxygen_requirement_trend
      - medication_and_treatment_timeline
      - cardiac_or_volume_status
      - PE_or_vascular_context
      - hemoptysis_or_anemia_context
      - MDD_or_urgent_clinical_review
    final_prompt:
      - What superimposed process remains possible before calling this acute exacerbation or progression?
```

---

## 12. Final Page Prompt

Every Superimposed Events Core page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with the prior CT?
3. Is the new finding focal, multifocal, diffuse, dependent, airway-centered, or vascular?
4. What is the clinical time course?
5. Is infection, acute exacerbation, edema, PE, hemorrhage, OP, drug toxicity, aspiration, or malignancy still possible?
6. What medication, treatment, immune, cancer, cardiac, or exposure context is missing?
7. Is urgent review or MDD needed?
8. What do we still not know?
```