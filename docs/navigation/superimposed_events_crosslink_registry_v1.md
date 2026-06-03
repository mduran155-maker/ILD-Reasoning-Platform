# Superimposed Events Crosslink Registry — v1

## Document Metadata

```yaml
id: navigation_superimposed_events_crosslink_registry_v1
title: Superimposed Events Crosslink Registry
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: navigation_and_crosslink_contract
diagnostic_authority: none
module_version: v0.3
last_updated: draft
```

---

## 0. Purpose

This registry defines how the Superimposed Events Core links across the ILD Reasoning Platform.

It connects:

- baseline ILD pattern pages,
- fibrotic ILD reasoning maps,
- granulomatous reasoning maps,
- acute change reasoning,
- infection reasoning,
- edema / vascular / hemorrhage mimics,
- malignancy and focal lesion review,
- drug toxicity / treatment-related injury,
- temporal comparison methodology,
- and MDD escalation prompts.

The module must not behave like a standalone “acute exacerbation” article.

It must remain a superimposed-event reasoning network.

---

## 1. Core Superimposed Events Pages

```yaml
core_superimposed_events_pages:
  superimposed_events_core_blueprint:
    path: docs/reasoning/superimposed_events_core_blueprint_v1.md
    role: central_superimposed_events_blueprint
    status: implemented

  superimposed_infection_on_ILD_background:
    path: docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    role: infection_safety_reasoning_map
    status: implemented

  acute_exacerbation_vs_infection_vs_edema:
    path: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    role: acute_bilateral_GGO_three_way_reasoning_map
    status: implemented
```

---

## 2. Implemented v0.3 Modules

```yaml
implemented_superimposed_event_modules:
  v0_3_0:
    module: superimposed_events_core_blueprint
    path: docs/reasoning/superimposed_events_core_blueprint_v1.md
    role: module_blueprint
    core_question:
      - What new process may have appeared on top of the ILD background?

  v0_3_1:
    module: superimposed_infection_on_ILD_background
    path: docs/reasoning/superimposed_infection_on_ILD_background_v1.md
    role: infection_on_ILD_reasoning_map
    core_question:
      - What evidence is missing before calling this infection rather than OP, aspiration, malignancy, AE, or another superimposed process?

  v0_3_2:
    module: acute_exacerbation_vs_infection_vs_edema
    path: docs/reasoning/acute_exacerbation_vs_infection_vs_edema_v1.md
    role: AE_infection_edema_triage_map
    core_question:
      - What evidence is missing before calling this acute exacerbation, infection, or edema?
```

---

## 3. Planned v0.3 Modules

```yaml
planned_superimposed_event_modules:
  organizing_pneumonia_on_ILD_background:
    path: docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    status: planned
    role: OP_inflammatory_superimposed_pattern

  malignancy_on_fibrotic_ILD_background:
    path: docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
    status: planned
    role: focal_lesion_and_cancer_on_fibrosis_reasoning

  drug_toxicity_or_treatment_related_lung_injury:
    path: docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
    status: planned
    role: medication_and_treatment_timeline_reasoning

  vascular_edema_hemorrhage_mimic_panel:
    path: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
    status: planned
    role: edema_PE_DAH_vascular_mimic_panel

  temporal_comparison_methodology:
    path: docs/reasoning/temporal_comparison_methodology_v1.md
    status: planned
    role: prior_CT_change_interpretation_methodology
```

---

## 4. Entry Trigger Routing

```yaml
entry_trigger_routing:
  new_bilateral_GGO_on_fibrotic_ILD_background:
    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
      - superimposed_events_core_blueprint_v1
    required_prompt:
      - New bilateral GGO is not specific for acute exacerbation, infection, or edema.

  new_focal_consolidation_on_ILD_background:
    route_to:
      - superimposed_infection_on_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
    required_prompt:
      - Persistent, asymmetric, or mass-like consolidation requires OP, infection, aspiration, and malignancy review.

  new_tree_in_bud_or_airway_centered_opacity:
    route_to:
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Tree-in-bud should trigger airway-centered infection, aspiration, TB/NTM, or bronchiolitis review.

  new_cavitation_on_ILD_background:
    route_to:
      - superimposed_infection_on_ILD_background_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - malignancy_on_fibrotic_ILD_background_v1
    required_prompt:
      - Cavitation is a high-risk red flag and should not be called simple ILD change.

  rapid_diffuse_worsening:
    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_events_core_blueprint_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    required_prompt:
      - Rapid worsening should keep infection, edema, PE, hemorrhage, drug toxicity, and acute exacerbation visible.

  new_or_growing_nodule_or_mass:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_events_core_blueprint_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Do not let background fibrosis hide a focal lesion.

  new_smooth_septal_GGO_or_effusions:
    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    required_prompt:
      - Edema and volume overload must be reviewed before increasing acute exacerbation confidence.

  new_opacity_after_new_medication_or_cancer_therapy:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Medication and treatment timeline are high-yield missing data.
```

---

## 5. Baseline ILD Crosslinks

```yaml
baseline_ILD_crosslinks:
  UIP_or_IPF_like_background:
    related_pages:
      - uip_pattern_gold_standard_v1
      - fibrotic_ild_triage_map_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
    core_prompt:
      - Do not call new GGO simple UIP progression without superimposed event review.

  NSIP_or_CTD_ILD_like_background:
    related_pages:
      - nsip_pattern_gold_standard_v1
      - fibrotic_ild_triage_map_v1
      - organizing_pneumonia_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    core_prompt:
      - New inflammatory opacity may represent flare, OP, infection, edema, drug toxicity, or progression.

  fibrotic_HP_background:
    related_pages:
      - fibrotic_hp_pattern_gold_standard_v1
      - fibrotic_ild_triage_map_v1
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    core_prompt:
      - Exposure recurrence, infection, edema, AE, OP, or drug toxicity may mimic worsening.

  sarcoidosis_or_granulomatous_background:
    related_pages:
      - sarcoidosis_pattern_gold_standard_v1
      - granulomatous_ild_reasoning_map_v1
      - fibrotic_sarcoidosis_vs_chronic_hp_gray_zone_v1
      - superimposed_infection_on_ILD_background_v1
    core_prompt:
      - New cavitation, mass, GGO, or consolidation requires infection, malignancy, vasculitis, complication, and treatment-context review.

  GLILD_or_immune_deficiency_background:
    related_pages:
      - glild_pattern_gold_standard_v1
      - sarcoidosis_vs_glild_gray_zone_v1
      - superimposed_infection_on_ILD_background_v1
    core_prompt:
      - Infection and lymphoma/malignancy remain high-value mimics in immune deficiency context.
```

---

## 6. Red Flag Routing

```yaml
red_flag_routing:
  fever_or_sepsis_context:
    route_to:
      - superimposed_infection_on_ILD_background_v1
    prompt:
      - Infection remains high priority, but AE, edema, OP, PE, and drug toxicity may still coexist.

  immunosuppression:
    route_to:
      - superimposed_infection_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    prompt:
      - Opportunistic infection and drug/treatment-related lung injury must remain visible.

  smooth_septal_thickening_plus_effusions:
    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    prompt:
      - Edema / volume overload review is required.

  hemoptysis_or_anemia_with_GGO:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
    prompt:
      - Diffuse alveolar hemorrhage and vasculitis review may be urgent.

  PE_risk_or_infarct_like_opacity:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
    prompt:
      - Vascular event may explain acute decline or peripheral opacity.

  persistent_focal_opacity:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    prompt:
      - Persistent focal opacity should not be assumed to be infection or scar.

  new_cavitation:
    route_to:
      - superimposed_infection_on_ILD_background_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - malignancy_on_fibrotic_ILD_background_v1
    prompt:
      - Cavitation requires infection, vasculitis, malignancy, septic emboli, and rheumatoid nodule review.
```

---

## 7. Missing Piece Priority

```yaml
superimposed_events_missing_piece_priority:
  essential:
    - prior_CT
    - clinical_time_course
    - oxygen_requirement_trend
    - baseline_ILD_pattern
    - distribution_of_new_abnormality
    - CT_technical_comparability

  high_yield:
    - infection_review
    - microbiology_when_relevant
    - medication_and_treatment_timeline
    - cardiac_and_volume_status
    - renal_function
    - immune_status
    - cancer_history
    - aspiration_risk
    - hemoptysis_or_anemia_context
    - PE_or_vascular_context

  context_dependent:
    - BAL_or_sampling_context
    - follow_up_CT
    - echocardiography_or_BNP_context
    - oncology_review
    - infectious_disease_review
    - rheumatology_nephrology_ENT_review
    - MDD_review
```

---

## 8. Safety Boundary

```yaml
superimposed_events_safety_boundary:
  platform_must_not:
    - call_new_GGO_simple_progression_without_prior_CT_review
    - diagnose_acute_exacerbation_from_GGO_alone
    - diagnose_infection_from_consolidation_alone
    - diagnose_edema_from_smooth_septal_thickening_without_clinical_context
    - diagnose_malignancy_from_new_nodule_alone
    - diagnose_drug_toxicity_without_medication_or_treatment_timeline
    - ignore_PE_hemorrhage_OP_aspiration_or_malignancy_mimics
    - recommend_treatment
    - replace_urgent_clinical_judgment_or_MDD

  platform_must:
    - preserve_superimposed_event_differential
    - request_prior_CT_when_available
    - request_clinical_time_course
    - request_treatment_and_medication_timeline
    - show_red_flags
    - separate_progression_from_superimposed_events
    - trigger_urgent_review_when_high_risk_context_exists
    - trigger_MDD_when pathways_overlap_or_context_conflicts
```

---

## 9. v0.3 Current Status

```yaml
v0_3_current_status:
  module: Superimposed Events Core
  status: active_development
  completed:
    - superimposed_events_core_blueprint_v1
    - superimposed_infection_on_ILD_background_v1
    - acute_exacerbation_vs_infection_vs_edema_v1
    - superimposed_events_crosslink_registry_v1

  next_recommended:
    module: organizing_pneumonia_on_ILD_background_v1
    reason:
      - OP is a major mimic of infection, acute exacerbation, malignancy, drug toxicity, and CTD-ILD flare.
      - It helps separate potentially reversible inflammatory opacity from irreversible fibrosis progression.
      - It links naturally to treatment response and temporal comparison modules.

  later:
    - malignancy_on_fibrotic_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1
```

---

## 10. Final Crosslink Rule

Every Superimposed Events page should end with:

```text
Do not force the label.

Ask:
1. What is the baseline ILD pattern?
2. What is new compared with prior CT?
3. Is the new finding focal, multifocal, diffuse, dependent, airway-centered, vascular, cavitary, or mass-like?
4. What is the clinical time course?
5. Is infection, acute exacerbation, edema, PE, hemorrhage, OP, drug toxicity, aspiration, or malignancy still possible?
6. What clinical, microbiologic, cardiac, renal, medication, oncology, immune, or temporal data are missing?
7. Is urgent review or MDD needed?
8. What do we still not know?
```
---

## 11. Organizing Pneumonia Module Sync

```yaml
implemented_superimposed_event_modules_update:
  organizing_pneumonia_on_ILD_background:
    path: docs/reasoning/organizing_pneumonia_on_ILD_background_v1.md
    role: reversible_inflammatory_opacity_and_mimic_reasoning_map
    status: implemented
    linked_reasoning_maps:
      - superimposed_events_core_blueprint_v1
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - fibrotic_ild_triage_map_v1
    core_safety_question:
      - Is this truly OP-like inflammation, or could infection, malignancy, drug toxicity, aspiration, radiation injury, edema, PE, hemorrhage, acute exacerbation, or baseline ILD progression explain the opacity?

updated_completed_superimposed_event_modules:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - organizing_pneumonia_on_ILD_background_v1

remaining_high_priority_superimposed_event_modules:
  - malignancy_on_fibrotic_ILD_background_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - vascular_edema_hemorrhage_mimic_panel_v1
  - temporal_comparison_methodology_v1
```

---

## 12. Updated OP Routing Logic

```yaml
updated_OP_routing_logic:
  if_user_starts_with_new_peripheral_or_peribronchovascular_consolidation:
    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
    required_prompt:
      - OP_like_consolidation_requires_infection_malignancy_drug_aspiration_and_temporal_review

  if_user_starts_with_migratory_or_waxing_waning_consolidation:
    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - superimposed_events_core_blueprint_v1
    required_prompt:
      - Migratory_opacity_supports_OP_like_behavior_but_does_not_exclude_infection_drug_toxicity_or_aspiration

  if_user_starts_with_reverse_halo_or_atoll_like_pattern:
    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    required_prompt:
      - Reverse_halo_is_not_specific_for_OP_and_requires_infection_infarct_vasculitis_malignancy_review

  if_user_starts_with_persistent_focal_OP_like_consolidation:
    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Persistent_focal_OP_like_opacity_should_not_hide_malignancy_or_chronic_infection

  if_user_starts_with_OP_like_opacity_after_drug_or_cancer_therapy:
    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - malignancy_on_fibrotic_ILD_background_v1
    required_prompt:
      - Treatment_timeline_is_high_yield_and_progression_toxicity_infection_OP_must_remain_visible
```

---

## 13. Updated OP Safety Boundary

```yaml
updated_OP_safety_boundary:
  platform_must_not:
    - diagnose_OP_from_morphology_alone
    - call_every_peripheral_consolidation_OP
    - call_every_migratory_opacity_benign_inflammatory_OP
    - ignore_infection_in_OP_like_opacity
    - ignore_malignancy_in_persistent_focal_OP_like_consolidation
    - ignore_drug_toxicity_or_cancer_treatment_timeline
    - ignore_aspiration_radiation_PE_hemorrhage_or_edema_mimics
    - treat_improvement_as_proof_of_OP
    - call_OP_like_opacity_simple_ILD_progression_without_prior_CT_review

  platform_must:
    - route_OP_like_opacity_to_infection_malignancy_drug_aspiration_and_temporal_review
    - request_prior_CT_or_follow_up_context_when_persistence_or_migration_matters
    - keep_treatment_timeline_visible
    - keep_sampling_or_follow_up_discussion_visible_when_focal_persistent_or_mass_like
    - preserve_uncertainty_when_microbiology_oncology_or_medication_context_is_missing
    - trigger_MDD_when_OP_infection_malignancy_drug_toxicity_or_AE_signals_overlap
```
---

## 14. Malignancy on Fibrotic ILD Module Sync

```yaml
implemented_superimposed_event_modules_update:
  malignancy_on_fibrotic_ILD_background:
    path: docs/reasoning/malignancy_on_fibrotic_ILD_background_v1.md
    role: focal_lesion_and_cancer_on_fibrotic_background_reasoning_map
    status: implemented
    linked_reasoning_maps:
      - superimposed_events_core_blueprint_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - fibrotic_ild_triage_map_v1
    core_safety_question:
      - Is this truly malignancy, or could infection, OP, infarct, drug toxicity, sarcoid-like reaction, scar, or fibrotic distortion explain the focal abnormality?

updated_completed_superimposed_event_modules:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - organizing_pneumonia_on_ILD_background_v1
  - malignancy_on_fibrotic_ILD_background_v1

remaining_high_priority_superimposed_event_modules:
  - drug_toxicity_treatment_related_lung_injury_v1
  - vascular_edema_hemorrhage_mimic_panel_v1
  - temporal_comparison_methodology_v1
```

---

## 15. Updated Malignancy on Fibrotic ILD Routing Logic

```yaml
updated_malignancy_on_fibrotic_ILD_routing_logic:
  if_user_starts_with_new_or_growing_nodule_on_fibrotic_background:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_events_core_blueprint_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - New_or_growing_nodule_should_not_be_hidden_inside_fibrosis_or_scar_label

  if_user_starts_with_persistent_focal_consolidation:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Persistent_focal_consolidation_requires_malignancy_OP_infection_and_temporal_review

  if_user_starts_with_mass_like_fibrotic_distortion:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - fibrotic_ild_triage_map_v1
    required_prompt:
      - Mass_like_fibrotic_distortion_requires_growth_soft_tissue_component_and_prior_CT_review

  if_user_starts_with_new_or_progressive_lymphadenopathy_on_ILD_background:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_events_core_blueprint_v1
      - sarcoidosis_vs_malignancy_or_sarcoid_like_reaction_gray_zone_v1
    required_prompt:
      - Progressive_or_asymmetric_nodes_require_malignancy_lymphoma_infection_and_sarcoid_like_reaction_review

  if_user_starts_with_known_cancer_and_new_fibrotic_lung_opacity:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Cancer_context_requires_progression_treatment_reaction_infection_OP_and_sarcoid_like_reaction_review

  if_user_starts_with_FDG_avid_focus_in_fibrotic_lung:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - FDG_uptake_is_not_specific_and_requires_timeline_distribution_and_inflammatory_context
```

---

## 16. Updated Malignancy on Fibrotic ILD Safety Boundary

```yaml
updated_malignancy_on_fibrotic_ILD_safety_boundary:
  platform_must_not:
    - call_new_or_growing_nodule_scar_without_prior_CT_review
    - hide_focal_malignancy_inside_baseline_fibrosis
    - assume_persistent_focal_consolidation_is_infection_or_OP_indefinitely
    - diagnose_malignancy_from_CT_or_PET_alone
    - rely_on_FDG_uptake_without_timeline_distribution_and_inflammatory_context
    - ignore_infection_OP_infarct_drug_toxicity_sarcoid_like_reaction_or_fibrotic_scar_mimics
    - let_benign_sampling_from_one_site_explain_a_separate_unsampled_growing_lesion
    - ignore_sampling_risk_in_fibrotic_lung

  platform_must:
    - route_new_or_growing_focal_abnormality_to_malignancy_on_fibrotic_ILD_review
    - request_prior_CT_or_follow_up_context_when_newness_growth_or_persistence_matters
    - keep_infection_OP_and_inflammatory_mimics_visible
    - keep_oncology_history_and_treatment_timeline_visible
    - keep_tissue_sampling_target_and_risk_context_visible
    - preserve_uncertainty_when_prior_CT_PET_CT_or_growth_rate_are_unavailable
    - trigger_oncology_or_MDD_review_when_malignancy_mimic_or_sampling_signals_overlap
```
---

## 17. Drug Toxicity / Treatment-related Lung Injury Module Sync

```yaml
implemented_superimposed_event_modules_update:
  drug_toxicity_treatment_related_lung_injury:
    path: docs/reasoning/drug_toxicity_treatment_related_lung_injury_v1.md
    role: medication_treatment_timeline_and_pneumonitis_mimic_reasoning_map
    status: implemented
    linked_reasoning_maps:
      - superimposed_events_core_blueprint_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - malignancy_on_fibrotic_ILD_background_v1
    core_safety_question:
      - Is this truly drug toxicity or treatment-related lung injury, or could infection, malignancy progression, OP, edema, hemorrhage, PE, CTD flare, aspiration, acute exacerbation, or baseline ILD progression explain the change?

updated_completed_superimposed_event_modules:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - organizing_pneumonia_on_ILD_background_v1
  - malignancy_on_fibrotic_ILD_background_v1
  - drug_toxicity_treatment_related_lung_injury_v1

remaining_high_priority_superimposed_event_modules:
  - vascular_edema_hemorrhage_mimic_panel_v1
  - temporal_comparison_methodology_v1
```

---

## 18. Updated Drug / Treatment-related Lung Injury Routing Logic

```yaml
updated_drug_toxicity_treatment_related_lung_injury_routing_logic:
  if_user_starts_with_new_opacity_after_new_medication_or_dose_change:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    required_prompt:
      - Medication_timeline_supports_suspicion_but_does_not_prove_drug_toxicity

  if_user_starts_with_new_lung_opacity_during_immune_checkpoint_inhibitor_therapy:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - ICI_context_requires_pneumonitis_progression_infection_sarcoid_like_reaction_and_radiation_recall_review

  if_user_starts_with_OP_like_pattern_after_drug_or_cancer_therapy:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
    required_prompt:
      - OP_like_pattern_after_treatment_requires_toxicity_progression_infection_and_secondary_OP_review

  if_user_starts_with_DAD_or_ARDS_like_pattern_after_treatment:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    required_prompt:
      - DAD_like_treatment_injury_and_acute_exacerbation_can_overlap_and_require_timeline_exclusion_context

  if_user_starts_with_radiation_field_opacity_or_radiation_recall_context:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
    required_prompt:
      - Radiation_field_timing_recall_trigger_recurrence_infection_and_OP_review_required

  if_user_starts_with_CTD_ILD_and_new_opacity_after_DMARD_or_biologic:
    route_to:
      - drug_toxicity_treatment_related_lung_injury_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - CTD_flare_DMARD_toxicity_secondary_OP_and_infection_must_remain_visible
```

---

## 19. Updated Drug / Treatment-related Lung Injury Safety Boundary

```yaml
updated_drug_toxicity_treatment_related_lung_injury_safety_boundary:
  platform_must_not:
    - diagnose_drug_toxicity_from_timing_alone
    - call_every_new_GGO_after_medication_drug_toxicity
    - call_every_ICI_lung_opacity_immune_checkpoint_inhibitor_pneumonitis
    - ignore_infection_in_treated_or_immunosuppressed_patients
    - ignore_malignancy_progression_during_cancer_therapy
    - ignore_radiation_field_radiation_recall_or_recurrence_context
    - ignore_CTD_flare_secondary_OP_or_baseline_ILD_progression
    - call_diffuse_GGO_acute_exacerbation_without_medication_treatment_timeline_review
    - treat_improvement_as_proof_of_drug_toxicity

  platform_must:
    - request_exact_medication_treatment_radiation_and_dose_timeline
    - keep_infection_visible_when_immunosuppression_or_cancer_therapy_exists
    - keep_progression_visible_when_oncology_context_exists
    - keep_AE_edema_hemorrhage_PE_OP_and_aspiration_mimics_visible
    - preserve_uncertainty_when_prior_CT_treatment_dates_or_microbiology_are_unavailable
    - trigger_oncology_rheumatology_infectious_disease_or_MDD_review_when_signals_overlap
```
---

## 20. Vascular / Edema / Hemorrhage Mimic Panel Sync

```yaml
implemented_superimposed_event_modules_update:
  vascular_edema_hemorrhage_mimic_panel:
    path: docs/reasoning/vascular_edema_hemorrhage_mimic_panel_v1.md
    role: vascular_edema_DAH_PE_infarct_mimic_reasoning_panel
    status: implemented
    linked_reasoning_maps:
      - superimposed_events_core_blueprint_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
    core_safety_question:
      - Is this truly AE, infection, OP, drug toxicity, or progression, or could edema, PE/infarct, pulmonary hypertension decompensation, hemorrhage, or pulmonary-renal vasculitis explain the acute change?

updated_completed_superimposed_event_modules:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - organizing_pneumonia_on_ILD_background_v1
  - malignancy_on_fibrotic_ILD_background_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - vascular_edema_hemorrhage_mimic_panel_v1

remaining_high_priority_superimposed_event_modules:
  - temporal_comparison_methodology_v1
```

---

## 21. Updated Vascular / Edema / Hemorrhage Routing Logic

```yaml
updated_vascular_edema_hemorrhage_routing_logic:
  if_user_starts_with_smooth_septal_GGO_or_pleural_effusions:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    required_prompt:
      - Smooth_septal_GGO_or_effusions_require_cardiac_renal_volume_and_edema_review_before_AE_or_infection_labeling

  if_user_starts_with_peripheral_wedge_or_pleural_based_opacity:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
    required_prompt:
      - Peripheral_wedge_like_opacity_requires_PE_infarct_OP_infection_and_malignancy_review

  if_user_starts_with_acute_diffuse_GGO_and_hemoptysis_or_anemia:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - drug_toxicity_treatment_related_lung_injury_v1
    required_prompt:
      - Acute_diffuse_GGO_with_hemoptysis_or_anemia_requires_DAH_anticoagulation_vasculitis_and_drug_review

  if_user_starts_with_acute_decline_disproportionate_to_CT_change:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    required_prompt:
      - Disproportionate_decline_requires_PE_pulmonary_hypertension_cardiac_edema_infection_and_AE_review

  if_user_starts_with_pulmonary_renal_or_vasculitic_context:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
    required_prompt:
      - Pulmonary_renal_context_requires_DAH_AAV_GPA_renal_urinalysis_and_rheumatology_review

  if_user_starts_with_rapid_GGO_improvement_after_diuresis_or_volume_change:
    route_to:
      - vascular_edema_hemorrhage_mimic_panel_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
    required_prompt:
      - Rapid_improvement_supports_edema_context_but_does_not_alone_prove_edema_without_clinical_review
```

---

## 22. Updated Vascular / Edema / Hemorrhage Safety Boundary

```yaml
updated_vascular_edema_hemorrhage_safety_boundary:
  platform_must_not:
    - call_smooth_septal_GGO_acute_exacerbation_without_edema_volume_review
    - call_peripheral_wedge_opacity_pneumonia_or_OP_without_PE_infarct_review
    - ignore_PE_when_acute_decline_is_disproportionate_to_CT_change
    - ignore_pulmonary_hypertension_or_right_heart_decompensation_in_advanced_ILD
    - ignore_DAH_when_GGO_occurs_with_hemoptysis_anemia_anticoagulation_or_renal_context
    - ignore_urinalysis_creatinine_ANCA_or_autoimmune_context_when_pulmonary_renal_syndrome_is_possible
    - treat_GGO_as_specific_for_AE_infection_edema_or_drug_toxicity
    - treat_rapid_improvement_as_proof_of_a_single_pathway

  platform_must:
    - keep_edema_PE_infarct_pulmonary_hypertension_and_DAH_visible_in_acute_ILD_worsening
    - request_cardiac_renal_volume_context_when_GGO_septal_thickening_or_effusions_are_present
    - request_PE_risk_and_vascular_context_when_decline_is_disproportionate_or_opacity_is_wedge_like
    - request_hemoptysis_hemoglobin_anticoagulation_urinalysis_and_renal_context_when_DAH_is_possible
    - preserve_uncertainty_when_prior_CT_cardiac_renal_vascular_or_hemorrhage_data_are_missing
    - trigger_urgent_review_when_edema_PE_DAH_AE_infection_or_drug_toxicity_overlap_in_unstable_patient
```
---

## 23. Temporal Comparison Methodology Module Sync

```yaml
implemented_superimposed_event_modules_update:
  temporal_comparison_methodology:
    path: docs/reasoning/temporal_comparison_methodology_v1.md
    role: prior_CT_change_interpretation_and_temporal_reasoning_methodology
    status: implemented
    linked_reasoning_maps:
      - superimposed_events_core_blueprint_v1
      - superimposed_infection_on_ILD_background_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - fibrotic_ild_triage_map_v1
    core_safety_question:
      - What truly changed compared with prior CT, over what interval, and is that change structural fibrosis, reversible opacity, technical difference, or superimposed disease?

updated_completed_superimposed_event_modules:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - organizing_pneumonia_on_ILD_background_v1
  - malignancy_on_fibrotic_ILD_background_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - vascular_edema_hemorrhage_mimic_panel_v1
  - temporal_comparison_methodology_v1

remaining_high_priority_superimposed_event_modules:
  - none_for_v0_3_core
```

---

## 24. Updated Temporal Comparison Routing Logic

```yaml
updated_temporal_comparison_routing_logic:
  if_user_starts_with_prior_CT_comparison_question:
    route_to:
      - temporal_comparison_methodology_v1
      - superimposed_events_core_blueprint_v1
    required_prompt:
      - Determine what is new, increased, decreased, resolved, migrated, persistent, stable, or technically uncertain.

  if_user_starts_with_possible_progression:
    route_to:
      - temporal_comparison_methodology_v1
      - fibrotic_ild_triage_map_v1
      - superimposed_events_core_blueprint_v1
    required_prompt:
      - Separate structural fibrotic progression from reversible superimposed opacity before calling progression.

  if_user_starts_with_new_GGO_or_consolidation_compared_with_prior_CT:
    route_to:
      - temporal_comparison_methodology_v1
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    required_prompt:
      - New GGO or consolidation is not automatically progression and requires superimposed event review.

  if_user_starts_with_decreased_GGO_or_consolidation:
    route_to:
      - temporal_comparison_methodology_v1
      - superimposed_events_core_blueprint_v1
    required_prompt:
      - Improvement of reversible opacity should not be equated with reversal of established fibrosis.

  if_user_starts_with_persistent_focal_opacity:
    route_to:
      - temporal_comparison_methodology_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Persistent focal opacity requires malignancy, chronic infection, OP, atelectasis, infarct, and treatment-context review.

  if_user_starts_with_migratory_or_waxing_waning_opacity:
    route_to:
      - temporal_comparison_methodology_v1
      - organizing_pneumonia_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - Migration supports inflammatory behavior but does not prove OP or exclude infection, drug toxicity, or aspiration.

  if_user_starts_with_new_or_growing_nodule:
    route_to:
      - temporal_comparison_methodology_v1
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    required_prompt:
      - New or growing nodule should not be hidden inside fibrosis, scar, or baseline ILD label.

  if_user_starts_with_technical_difference_between_CT_studies:
    route_to:
      - temporal_comparison_methodology_v1
    required_prompt:
      - Technique, inspiration, slice thickness, reconstruction, contrast, motion, and positioning must be reviewed before declaring biological change.
```

---

## 25. Updated Temporal Reasoning Safety Boundary

```yaml
updated_temporal_reasoning_safety_boundary:
  platform_must_not:
    - call_progression_from_a_single_CT_snapshot
    - call_regression_without_separating_reversible_opacity_from_structural_fibrosis
    - call_stability_without_technical_comparability_review
    - call_new_GGO_fibrotic_progression_without_superimposed_event_review
    - call_new_or_growing_nodule_scar_without_prior_CT_growth_and_morphology_review
    - treat_migratory_opacity_as_diagnostic_of_OP
    - treat_persistent_focal_opacity_as_benign_without_malignancy_chronic_infection_and_OP_review
    - ignore_CT_technical_factors_when_apparent_change_is_subtle_or_discordant
    - let_baseline_ILD_label_swallow_new_temporal_change

  platform_must:
    - request_prior_CT_when_temporal_reasoning_is_required
    - classify_change_as_new_increased_decreased_resolved_migrated_persistent_stable_morphologically_changed_or_technically_uncertain
    - separate_structural_fibrosis_from_reversible_airspace_opacity
    - match_change_type_to_time_interval
    - review_technical_comparability_before declaring progression_or_regression
    - route_new_airspace_opacity_to_superimposed_event_review
    - route_new_or_growing_focal_abnormality_to_malignancy_and_infection_review
    - preserve_uncertainty_when_prior_CT_or_technical_comparability_is_missing
    - trigger_MDD_when temporal_change_and_clinical_context_conflict
```

---

## 26. v0.3 Superimposed Events Core Completion Status

```yaml
v0_3_superimposed_events_core_completion_status:
  module: Superimposed Events Core
  status: core_architecture_complete_blueprint
  public_ready: false
  clinical_use: educational_reasoning_support_only
  diagnostic_authority: none
  expert_review_required: true
  full_source_review_required: true

  completed_core_modules:
    - superimposed_events_core_blueprint_v1
    - superimposed_infection_on_ILD_background_v1
    - acute_exacerbation_vs_infection_vs_edema_v1
    - organizing_pneumonia_on_ILD_background_v1
    - malignancy_on_fibrotic_ILD_background_v1
    - drug_toxicity_treatment_related_lung_injury_v1
    - vascular_edema_hemorrhage_mimic_panel_v1
    - temporal_comparison_methodology_v1

  core_coverage:
    - infection_on_ILD_background
    - acute_exacerbation_vs_infection_vs_edema
    - organizing_pneumonia_like_opacity
    - malignancy_or_focal_lesion_on_fibrotic_background
    - drug_toxicity_or_treatment_related_lung_injury
    - edema_PE_infarct_DAH_and_vascular_mimics
    - prior_CT_temporal_comparison_methodology

  remaining_high_priority_modules_for_v0_3_core:
    - none

  next_recommended:
    module: superimposed_events_core_lock_checklist_v1
    path: docs/data/schema/superimposed_events_core_lock_checklist_v1.md
    reason:
      - v0.3 now has its central blueprint, major superimposed event families, routing registry, and temporal methodology.
      - A lock checklist should verify file presence, crosslinks, missing-piece coverage, red-flag coverage, and safety boundaries before sealing.
```

---

## 27. Final v0.3 Crosslink Rule

```yaml
final_v0_3_crosslink_rule:
  every_superimposed_events_pathway_must_ask:
    - What is the baseline ILD pattern?
    - What is new compared with prior CT?
    - Is the current and prior CT technically comparable?
    - Is the change structural fibrosis or reversible airspace opacity?
    - Did the change occur over hours, days, weeks, months, or years?
    - Is infection, acute exacerbation, edema, PE, hemorrhage, OP, drug toxicity, aspiration, malignancy, or exposure recurrence still possible?
    - What clinical, microbiologic, cardiac, renal, medication, oncology, immune, exposure, vascular, or temporal data are missing?
    - Is urgent review, follow-up, sampling, specialist review, or MDD needed?
    - What do we still not know?
```