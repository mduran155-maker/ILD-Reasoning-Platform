# Superimposed Events Core Seal — v1

## Document Metadata

```yaml
id: data_schema_superimposed_events_core_seal_v1
title: Superimposed Events Core Seal
version: v1
language: English
status: blueprint_seal
project: ILD Reasoning Platform
content_type: module_seal
diagnostic_authority: none
module_version: v0.3
last_updated: draft
```

---

## 0. Purpose

This document seals the Superimposed Events Core v0.3 blueprint.

The seal confirms that the module has reached structural coherence across:

- baseline ILD pattern awareness,
- temporal comparison methodology,
- infection reasoning,
- acute exacerbation / infection / edema triage,
- organizing pneumonia mimic reasoning,
- malignancy on fibrotic ILD background,
- drug toxicity / treatment-related lung injury,
- vascular / edema / hemorrhage mimics,
- crosslink routing,
- missing data logic,
- red-flag visibility,
- and MDD / urgent review prompts.

This seal does not mean public clinical readiness.

It means the v0.3 Superimposed Events Core blueprint is structurally locked for future evidence review, expert review, and implementation planning.

---

## 1. Seal Scope

```yaml
seal_scope:
  module: Superimposed Events Core
  version: v0.3
  seal_type: structural_blueprint_lock
  public_ready: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  expert_review_required: true
  full_source_review_required: true
```

---

## 2. Locked Core Modules

```yaml
locked_superimposed_events_core:
  central_blueprint:
    path: docs/reasoning/superimposed_events_core_blueprint_v1.md
    role: central_superimposed_events_blueprint
    status: locked_blueprint

  infection_on_ILD_background:
    path: docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    role: infection_safety_reasoning_map
    status: locked_blueprint

  acute_exacerbation_vs_infection_vs_edema:
    path: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    role: acute_bilateral_GGO_triage_map
    status: locked_blueprint

  organizing_pneumonia_on_ILD_background:
    path: docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    role: OP_like_inflammatory_opacity_mimic_map
    status: locked_blueprint

  malignancy_on_fibrotic_ILD_background:
    path: docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
    role: focal_lesion_and_cancer_on_fibrosis_map
    status: locked_blueprint

  drug_toxicity_treatment_related_lung_injury:
    path: docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
    role: medication_treatment_timeline_pneumonitis_map
    status: locked_blueprint

  vascular_edema_hemorrhage_mimic_panel:
    path: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
    role: edema_PE_infarct_DAH_vascular_mimic_panel
    status: locked_blueprint

  temporal_comparison_methodology:
    path: docs/reasoning/temporal_comparison_methodology_v1.md
    role: prior_CT_change_interpretation_methodology
    status: locked_blueprint
```

---

## 3. Locked Navigation Core

```yaml
locked_navigation_core:
  superimposed_events_crosslink_registry:
    path: docs/navigation/superimposed_events_crosslink_registry_v1.md
    role: module_crosslink_and_routing_contract
    status: locked_blueprint

  routing_principle:
    - superimposed_events_pages_must_not_behave_as_isolated_articles
    - baseline_ILD_label_must_not_swallow_new_findings
    - prior_CT_and_temporal_context_must_remain_visible
    - high_risk_new_findings_must_route_to_mimic_review
    - urgent_or_MDD_review_must_remain_visible_when_context_conflicts
```

---

## 4. Core Coverage

```yaml
core_coverage:
  infection:
    status: covered
    module: superimposed_infection_on_ILD_background_v1

  acute_exacerbation_infection_edema:
    status: covered
    module: acute_exacerbation_vs_infection_vs_edema_v1

  organizing_pneumonia:
    status: covered
    module: organizing_pneumonia_on_ILD_background_v1

  malignancy_or_focal_lesion:
    status: covered
    module: malignancy_on_fibrotic_ILD_background_v1

  drug_toxicity_or_treatment_related_lung_injury:
    status: covered
    module: drug_toxicity_treatment_related_lung_injury_v1

  vascular_edema_hemorrhage_mimics:
    status: covered
    module: vascular_edema_hemorrhage_mimic_panel_v1

  temporal_comparison:
    status: covered
    module: temporal_comparison_methodology_v1
```

---

## 5. Safety Invariants

```yaml
safety_invariants:
  platform_must_not:
    - call_new_GGO_simple_progression_without_prior_CT_review
    - diagnose_acute_exacerbation_from_GGO_alone
    - diagnose_infection_from_consolidation_alone
    - diagnose_OP_from_morphology_alone
    - diagnose_malignancy_from_CT_or_PET_alone
    - diagnose_drug_toxicity_from_timing_alone
    - diagnose_edema_from_smooth_septal_thickening_without_clinical_context
    - diagnose_DAH_from_GGO_alone
    - ignore_PE_when_decline_is_disproportionate_to_CT_change
    - ignore_technical_CT_differences_when_apparent_change_is_subtle
    - treat_improvement_of_GGO_as_fibrosis_reversal
    - treat_persistent_focal_opacity_as_benign_without_review
    - recommend_treatment
    - replace_urgent_clinical_judgment_or_MDD

  platform_must:
    - preserve_superimposed_event_differential
    - request_prior_CT_when_temporal_reasoning_is_required
    - separate_structural_fibrosis_from_reversible_airspace_opacity
    - expose_missing_data
    - show_mimics
    - identify_red_flags
    - classify_temporal_change_explicitly
    - route_high_risk_contexts_to_urgent_or_specialist_review
    - end_major_reasoning_pages_with_what_do_we_still_not_know
```

---

## 6. Temporal Reasoning Seal

```yaml
temporal_reasoning_seal:
  required_change_categories:
    - new
    - increased
    - decreased
    - resolved
    - migrated
    - persistent
    - stable
    - morphologically_changed
    - technically_uncertain

  required_distinctions:
    - structural_fibrotic_progression_vs_reversible_airspace_opacity
    - biological_change_vs_technical_difference
    - chronic_progression_vs_acute_superimposed_event
    - improvement_of_opacity_vs_reversal_of_fibrosis
    - persistent_focal_opacity_vs_benign_scar

  required_technical_checks:
    - slice_thickness
    - reconstruction_kernel
    - inspiratory_effort
    - expiratory_phase_or_air_trapping_protocol
    - prone_vs_supine_positioning
    - motion_artifact
    - contrast_vs_noncontrast
    - scanner_or_protocol_difference
    - field_of_view_difference
```

---

## 7. Missing Piece Engine Coverage

```yaml
missing_piece_engine_coverage:
  universal:
    - prior_CT
    - baseline_ILD_pattern
    - clinical_time_course
    - oxygen_requirement_trend
    - CT_technical_comparability
    - MDD_review

  infection:
    - fever_or_systemic_infectious_context
    - WBC_CRP_or_inflammatory_marker_context
    - microbiology_or_viral_testing
    - immune_status
    - aspiration_risk_when_relevant

  acute_exacerbation:
    - infection_review
    - edema_review
    - PE_review
    - drug_toxicity_review
    - hemorrhage_review

  edema_vascular_hemorrhage:
    - cardiac_status
    - renal_function_and_fluid_balance
    - BNP_echo_or_right_heart_context_when_available
    - PE_risk_and_vascular_context
    - hemoptysis_and_hemoglobin_trend
    - anticoagulation_and_coagulation_status
    - urinalysis_and_autoimmune_context

  organizing_pneumonia:
    - migration_or_persistence_context
    - CTD_or_autoimmune_activity_context
    - medication_or_treatment_timeline
    - infection_review
    - malignancy_review_if_focal_or_persistent

  malignancy:
    - growth_rate
    - lesion_characterization
    - cancer_history_and_risk
    - PET_CT_context
    - tissue_sampling_target
    - oncology_review

  drug_treatment:
    - exact_medication_treatment_radiation_and_dose_timeline
    - oncology_treatment_context
    - radiation_field_and_timing
    - tumor_response_context
    - immune_status
    - infection_review
```

---

## 8. Red Flag Coverage

```yaml
red_flag_coverage:
  infection:
    status: covered
    examples:
      - fever_or_sepsis_context
      - immunosuppression
      - tree_in_bud
      - cavitation
      - opportunistic_infection_risk

  acute_exacerbation:
    status: covered
    examples:
      - new_bilateral_GGO_or_consolidation_on_fibrotic_background
      - acute_or_subacute_respiratory_worsening
      - increased_oxygen_requirement

  edema:
    status: covered
    examples:
      - smooth_interlobular_septal_thickening
      - dependent_or_perihilar_GGO
      - pleural_effusions
      - cardiac_failure_or_volume_context

  OP:
    status: covered
    examples:
      - peripheral_or_peribronchovascular_consolidation
      - perilobular_opacity
      - migratory_or_waxing_waning_opacity
      - persistent_focal_OP_like_opacity

  malignancy:
    status: covered
    examples:
      - new_or_growing_nodule
      - persistent_focal_consolidation
      - mass_like_opacity
      - progressive_or_asymmetric_lymphadenopathy

  drug_treatment:
    status: covered
    examples:
      - new_drug_or_recent_dose_change
      - immune_checkpoint_inhibitor_context
      - chemotherapy_or_targeted_therapy_context
      - radiation_field_or_recall_context

  vascular_hemorrhage:
    status: covered
    examples:
      - acute_dyspnea_disproportionate_to_CT_change
      - PE_risk_context
      - peripheral_wedge_shaped_opacity
      - hemoptysis
      - falling_hemoglobin
      - renal_or_urinalysis_abnormality

  temporal:
    status: covered
    examples:
      - prior_CT_unavailable
      - CT_technical_comparability_uncertain
      - rapid_change_too_fast_for_chronic_fibrosis
      - persistent_focal_opacity
      - morphologic_change
```

---

## 9. Lock Statement

```yaml
superimposed_events_core_v0_3_lock_statement:
  status: structurally_locked_blueprint
  public_ready: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  source_review_required: true
  expert_review_required: true
  next_phase_allowed:
    - evidence_review_matrix
    - test_case_expansion
    - UIP_parity_upgrade
    - implementation_planning
```

---

## 10. Final Seal Rule

A valid Superimposed Events pathway must ask:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. Is the prior CT technically comparable?
4. Is the change structural fibrosis or reversible airspace opacity?
5. Did the change occur over hours, days, weeks, months, or years?
6. Is infection, acute exacerbation, edema, PE, hemorrhage, OP, drug toxicity, aspiration, malignancy, or exposure recurrence still possible?
7. What clinical, microbiologic, cardiac, renal, medication, oncology, immune, exposure, vascular, or temporal data are missing?
8. Is urgent review, follow-up, sampling, specialist review, or MDD needed?
9. What do we still not know?
```