# Superimposed Events Core Lock Checklist — v1

## Document Metadata

```yaml
id: data_schema_superimposed_events_core_lock_checklist_v1
title: Superimposed Events Core Lock Checklist
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: validation_checklist
diagnostic_authority: none
module_version: v0.3
last_updated: draft
```

---

## 0. Purpose

This checklist defines the structural lock criteria for the Superimposed Events Core v0.3.

It verifies that the module is:

- baseline-aware,
- temporal-comparison-aware,
- superimposed-event-aware,
- mimic-aware,
- red-flag-aware,
- uncertainty-preserving,
- cross-linked,
- and safe from diagnostic overreach.

This lock does not mean public clinical readiness.

It means the v0.3 Superimposed Events Core blueprint is internally coherent and ready for future evidence review, expert review, and implementation planning.

---

## 1. Required Superimposed Events Core Files

```yaml
required_superimposed_events_core_files:
  central_blueprint:
    - docs/reasoning/superimposed_events_core_blueprint_v1.md

  reasoning_maps:
    - docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    - docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    - docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    - docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
    - docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
    - docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
    - docs/reasoning/temporal_comparison_methodology_v1.md

  navigation:
    - docs/navigation/superimposed_events_crosslink_registry_v1.md

  supporting_core:
    - docs/reasoning/fibrotic_ild_triage_map_v1.md
    - docs/evidence/guideline_registry_v1.md
    - docs/editorial/editorial_policy_v1.md
    - docs/editorial/source_review_protocol_v1.md
```

---

## 2. Core Coverage Requirements

```yaml
superimposed_events_core_coverage:
  required_event_families:
    - infection_on_ILD_background
    - acute_exacerbation_vs_infection_vs_edema
    - organizing_pneumonia_like_opacity
    - malignancy_or_focal_lesion_on_fibrotic_background
    - drug_toxicity_or_treatment_related_lung_injury
    - edema_PE_infarct_DAH_and_vascular_mimics
    - temporal_comparison_methodology

  required_baseline_contexts:
    - UIP_or_IPF_like_background
    - NSIP_or_CTD_ILD_like_background
    - fibrotic_HP_background
    - sarcoidosis_or_granulomatous_background
    - GLILD_or_immune_deficiency_background
    - oncology_or_post_treatment_context
    - unclassifiable_or_mixed_ILD_background
```

---

## 3. Safety Boundary Checks

```yaml
superimposed_events_safety_boundary_checks:
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
    - recommend_treatment
    - replace_urgent_clinical_judgment_or_MDD

  platform_must:
    - preserve_superimposed_event_differential
    - request_prior_CT_when_temporal_reasoning_is_required
    - separate_structural_fibrosis_from_reversible_airspace_opacity
    - expose_missing_data
    - show_mimics
    - identify_red_flags
    - route_high_risk_contexts_to_urgent_or_specialist_review
    - end_major_reasoning_pages_with_what_do_we_still_not_know
```

---

## 4. Required Red Flag Coverage

```yaml
required_red_flags:
  infection_red_flags:
    - fever_or_sepsis_context
    - immunosuppression
    - tree_in_bud
    - cavitation
    - necrotic_nodes
    - opportunistic_infection_risk
    - TB_NTM_or_fungal_context

  acute_exacerbation_red_flags:
    - new_bilateral_GGO_or_consolidation_on_fibrotic_background
    - acute_or_subacute_respiratory_worsening
    - increased_oxygen_requirement
    - no_sufficient_alternative_explanation_after_review

  edema_red_flags:
    - smooth_interlobular_septal_thickening
    - dependent_or_perihilar_GGO
    - pleural_effusions
    - cardiac_failure_context
    - renal_failure_or_volume_overload_context
    - rapid_improvement_after_volume_management_when_known

  OP_red_flags:
    - peripheral_or_peribronchovascular_consolidation
    - perilobular_opacity
    - migratory_or_waxing_waning_opacity
    - reverse_halo_or_atoll_like_pattern
    - persistent_focal_OP_like_opacity

  malignancy_red_flags:
    - new_or_growing_nodule
    - persistent_focal_consolidation
    - mass_like_opacity
    - new_soft_tissue_component_within_fibrosis
    - progressive_or_asymmetric_lymphadenopathy
    - known_or_prior_malignancy
    - suspicious_PET_CT_context

  drug_treatment_red_flags:
    - new_drug_or_recent_dose_change
    - immune_checkpoint_inhibitor_context
    - chemotherapy_or_targeted_therapy_context
    - radiation_field_or_recall_context
    - DMARD_biologic_or_immunosuppressive_context
    - rapid_respiratory_decline_after_exposure

  vascular_hemorrhage_red_flags:
    - acute_dyspnea_disproportionate_to_CT_change
    - pleuritic_chest_pain
    - PE_risk_context
    - peripheral_wedge_shaped_opacity
    - pulmonary_hypertension_or_right_heart_strain_context
    - hemoptysis
    - falling_hemoglobin_or_unexplained_anemia
    - anticoagulation_or_coagulopathy
    - renal_or_urinalysis_abnormality
    - vasculitis_or_autoimmune_context

  temporal_red_flags:
    - prior_CT_unavailable
    - CT_technical_comparability_uncertain
    - rapid_change_too_fast_for_chronic_fibrosis
    - apparent_progression_based_on_GGO_alone
    - persistent_focal_opacity
    - morphologic_change_such_as_cavitation_solid_component_or_mass_like_contour
```

---

## 5. Missing Piece Engine Coverage

```yaml
required_missing_piece_items:
  universal:
    - prior_CT
    - baseline_ILD_pattern
    - clinical_time_course
    - oxygen_requirement_trend
    - CT_technical_comparability
    - MDD_review

  temporal_specific:
    - exact_time_interval
    - change_category
    - structural_vs_airspace_change
    - new_increased_decreased_resolved_migrated_persistent_stable_or_technically_uncertain_status

  infection_specific:
    - fever_or_systemic_infectious_context
    - WBC_CRP_or_inflammatory_marker_context
    - microbiology_or_viral_testing
    - immune_status
    - aspiration_risk_when_relevant

  acute_exacerbation_specific:
    - acute_or_subacute_worsening_context
    - infection_review
    - edema_review
    - PE_review
    - drug_toxicity_review
    - hemorrhage_review

  edema_vascular_hemorrhage_specific:
    - cardiac_status
    - renal_function_and_fluid_balance
    - BNP_echo_or_right_heart_context_when_available
    - PE_risk_and_vascular_context
    - hemoptysis_and_hemoglobin_trend
    - anticoagulation_and_coagulation_status
    - urinalysis_and_autoimmune_context

  OP_specific:
    - migration_or_persistence_context
    - CTD_or_autoimmune_activity_context
    - medication_or_treatment_timeline
    - infection_review
    - malignancy_review_if_focal_or_persistent

  malignancy_specific:
    - growth_rate
    - lesion_characterization
    - cancer_history_and_risk
    - PET_CT_context
    - tissue_sampling_target
    - oncology_review

  drug_treatment_specific:
    - exact_medication_treatment_radiation_and_dose_timeline
    - oncology_treatment_context
    - radiation_field_and_timing
    - tumor_response_context
    - immune_status
    - infection_review
```

---

## 6. Crosslink Integrity

```yaml
crosslink_integrity:
  required:
    - superimposed_events_core_blueprint_links_to_all_v0_3_submodules
    - superimposed_events_crosslink_registry_lists_all_implemented_modules
    - infection_module_links_to_AE_OP_drug_malignancy_and_core_blueprint
    - AE_infection_edema_module_links_to_infection_drug_vascular_and_core_blueprint
    - OP_module_links_to_infection_malignancy_drug_and_temporal_context
    - malignancy_module_links_to_OP_infection_drug_temporal_and_fibrotic_triage
    - drug_toxicity_module_links_to_infection_OP_malignancy_AE_vascular_contexts
    - vascular_edema_hemorrhage_module_links_to_AE_infection_drug_OP_malignancy
    - temporal_methodology_links_to_all_superimposed_event_modules
    - remaining_high_priority_modules_marked_none_for_v0_3_core

  required_existing_links:
    - superimposed_events_core_blueprint_v1
    - superimposed_infection_on_ILD_background_v1
    - acute_exacerbation_vs_infection_vs_edema_v1
    - organizing_pneumonia_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1
```

---

## 7. Temporal Reasoning Integrity

```yaml
temporal_reasoning_integrity:
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

  required_time_intervals:
    - minutes_to_hours
    - hours_to_days
    - days_to_weeks
    - weeks_to_months
    - months_to_years

  required_distinctions:
    - structural_fibrotic_progression_vs_reversible_airspace_opacity
    - biological_change_vs_technical_difference
    - chronic_progression_vs_acute_superimposed_event
    - improvement_of_opacity_vs_reversal_of_fibrosis
    - persistent_focal_opacity_vs_benign_scar
```

---

## 8. Required Technical Comparability Checks

```yaml
technical_comparability_checks:
  CT_comparison_must_review:
    - slice_thickness
    - reconstruction_kernel
    - inspiratory_effort
    - expiratory_phase_or_air_trapping_protocol
    - prone_vs_supine_positioning
    - motion_artifact
    - contrast_vs_noncontrast
    - scanner_or_protocol_difference
    - field_of_view_difference

  platform_must_warn_if:
    - apparent_GGO_increase_may_reflect_poor_inspiration
    - apparent_reticulation_change_may_reflect_slice_thickness_or_kernel
    - apparent_volume_loss_may_reflect_inspiratory_difference
    - lymph_node_or_mass_assessment_differs_due_to_contrast_status
    - air_trapping_cannot_be_compared_due_to_missing_expiratory_images
```

---

## 9. Specialist / MDD Review Coverage

```yaml
specialist_and_MDD_review_coverage:
  required_review_prompts:
    - pulmonary_review
    - thoracic_radiology_review
    - infectious_disease_review_when_infection_or_opportunistic_context_possible
    - oncology_review_when_focal_lesion_or_cancer_context_possible
    - cardiology_or_volume_review_when_edema_or_heart_failure_context_possible
    - vascular_or_PE_review_when_PE_or_infarct_context_possible
    - rheumatology_review_when_CTD_flare_vasculitis_or_DAH_context_possible
    - nephrology_review_when_pulmonary_renal_or_renal_failure_context_possible
    - pharmacy_or_medication_review_when_drug_toxicity_possible
    - pathology_or_tissue_sampling_review_when_persistent_focal_or_uncertain_abnormality_exists
    - urgent_review_when_unstable_or_high_risk_context_exists
```

---

## 10. v0.3 Superimposed Events Core Lock Criteria

```yaml
v0_3_superimposed_events_core_lock_criteria:
  central_blueprint:
    - superimposed_events_core_blueprint_v1

  reasoning_core:
    - superimposed_infection_on_ILD_background_v1
    - acute_exacerbation_vs_infection_vs_edema_v1
    - organizing_pneumonia_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1

  navigation_core:
    - superimposed_events_crosslink_registry_v1
    - all_implemented_modules_listed
    - remaining_high_priority_modules_none_for_v0_3_core

  safety_core:
    - no_imaging_only_diagnosis
    - no_treatment_recommendation
    - no_final_patient_classification
    - uncertainty_preserved
    - missing_data_visible
    - mimics_visible
    - red_flags_visible
    - MDD_and_urgent_review_prompts_present

  temporal_core:
    - prior_CT_required_when_temporal_claim_is_made
    - technical_comparability_review_required
    - structural_fibrosis_separated_from_reversible_opacity
    - change_category_explicit
    - time_interval_explicit_or_requested
```

---

## 11. v0.3 Lock Statement

```yaml
v0_3_lock_statement:
  status: structurally_locked_blueprint_candidate
  public_ready: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  treatment_authority: none
  expert_review_required: true
  source_full_text_review_required: true
```

---

## 12. Final Lock Rule

A valid Superimposed Events pathway must answer:

```text
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