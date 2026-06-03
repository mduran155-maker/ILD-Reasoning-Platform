# Temporal Comparison Methodology — Reasoning Map v1

## Document Metadata

```yaml
id: reasoning_temporal_comparison_methodology_v1
title: Temporal Comparison Methodology — Reasoning Map
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: temporal_reasoning_methodology
diagnostic_authority: none
module_version: v0.3
linked_reasoning_maps:
  - superimposed_events_core_blueprint_v1
  - superimposed_infection_on_ILD_background_v1
  - acute_exacerbation_vs_infection_vs_edema_v1
  - organizing_pneumonia_on_ILD_background_v1
  - malignancy_on_fibrotic_ILD_background_v1
  - drug_toxicity_treatment_related_lung_injury_v1
  - vascular_edema_hemorrhage_mimic_panel_v1
  - fibrotic_ild_triage_map_v1
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - residents
  - fellows
  - MDD teams
clinical_scope: educational_reasoning_support
last_updated: draft
```

---

## 0. Purpose

This methodology helps users compare current and prior CT / HRCT examinations in patients with known or suspected ILD.

It does not diagnose progression, regression, stabilization, acute exacerbation, infection, edema, drug toxicity, hemorrhage, malignancy, OP, or treatment response.

It helps users ask:

- What is truly new compared with prior CT?
- What has increased, decreased, migrated, resolved, persisted, or changed morphology?
- Is the apparent change technical rather than biological?
- Is the change fibrotic progression or reversible inflammatory opacity?
- Is the change a superimposed event?
- Is the time interval appropriate for the claimed interpretation?
- What clinical, treatment, exposure, and laboratory context is missing?
- What do we still not know?

---

## 1. Core Safety Principle

```yaml
core_safety_principle:
  main_statement: >
    A single CT snapshot should not be treated as proof of progression, regression, treatment response, or superimposed disease.

  platform_rule:
    - do_not_call_progression_without_prior_CT_or_longitudinal_context
    - do_not_call_regression_without_distinguishing_reversible_opacity_from_fibrosis
    - do_not_call_stability_without_technical_comparability_review
    - do_not_call_new_GGO_progression_without_superimposed_event_review
    - do_not_call_new_nodule_scar_without_growth_and_prior_CT_review
    - preserve_temporal_uncertainty_when_prior_imaging_is_unavailable
```

### Teaching Point

The first question is not:

```text
What disease is this?
```

The better temporal question is:

```text
What changed, over what interval, and is that change real?
```

---

## 2. Temporal Comparison Workflow

```yaml
temporal_comparison_workflow:
  step_1_identify_baseline_pattern:
    questions:
      - What was the baseline ILD pattern?
      - UIP_like, NSIP_like, fibrotic_HP_like, sarcoidosis_like, GLILD_like, OP_like, unclassifiable, or mixed?
      - Was fibrosis already present?
      - Was there prior GGO, consolidation, nodularity, air trapping, or lymphadenopathy?

  step_2_confirm_technical_comparability:
    questions:
      - Are slice thickness, reconstruction kernel, inspiratory effort, motion, contrast status, and positioning comparable?
      - Was expiratory imaging available before and now?
      - Was prone imaging used in one study but not the other?
      - Could poor inspiration create pseudo-GGO or pseudo-volume loss?

  step_3_separate_structural_fibrosis_from_reversible_opacity:
    questions:
      - Did reticulation, traction bronchiectasis, honeycombing, architectural distortion, or volume loss increase?
      - Did GGO or consolidation change without structural fibrosis progression?
      - Is the change inflammatory, infectious, edematous, hemorrhagic, or fibrotic?

  step_4_define_change_type:
    change_categories:
      - new
      - increased
      - decreased
      - resolved
      - migrated
      - persistent
      - stable
      - morphologically_changed
      - technically_uncertain

  step_5_match_change_to_time_interval:
    questions:
      - Did the change occur over hours, days, weeks, months, or years?
      - Is the speed compatible with chronic fibrosis progression?
      - Is the speed more compatible with superimposed event?

  step_6_route_to_reasoning_modules:
    routes:
      - progression_vs_superimposed_event
      - infection_review
      - AE_infection_edema_review
      - OP_review
      - malignancy_review
      - drug_toxicity_review
      - vascular_edema_hemorrhage_review
      - MDD_review
```

---

## 3. Change Categories

```yaml
change_categories:
  new_finding:
    definition: abnormality not visible on prior comparable CT
    examples:
      - new_GGO
      - new_consolidation
      - new_nodule
      - new_mass
      - new_cavitation
      - new_lymphadenopathy
    caution:
      - new_visibility_may_reflect_technical_difference_or_previous_obscuration

  increased_finding:
    definition: pre-existing abnormality is larger, more extensive, denser, coarser, or more structurally advanced
    examples:
      - increased_reticulation
      - increased_traction_bronchiectasis
      - increased_honeycombing
      - increased_GGO
      - increased_consolidation
      - larger_nodule
    caution:
      - increased_GGO_is_not_equivalent_to_fibrotic_progression

  decreased_finding:
    definition: abnormality is less extensive, less dense, or less conspicuous
    examples:
      - decreased_GGO
      - decreased_consolidation
      - decreased_nodules
      - reduced_septal_thickening
    caution:
      - decrease_in_reversible_opacity_does_not_prove_fibrosis_reversal

  resolved_finding:
    definition: previously visible abnormality is no longer visible
    examples:
      - resolved_consolidation
      - resolved_GGO
      - resolved_nodule
    caution:
      - resolution_supports_reversible_process_but_does_not_define_cause

  migrated_finding:
    definition: opacity resolves or improves in one region and appears elsewhere
    examples:
      - migratory_OP_like_opacity
      - waxing_waning_consolidation
    caution:
      - migration_supports_inflammatory_behavior_but_does_not_exclude_infection_drug_toxicity_or_aspiration

  persistent_finding:
    definition: abnormality remains despite expected interval for resolution
    examples:
      - persistent_focal_consolidation
      - persistent_nodule
      - persistent_GGO
    caution:
      - persistence_may_trigger_malignancy_chronic_infection_OP_or_drug_toxicity_review

  stable_finding:
    definition: no meaningful change on comparable imaging
    examples:
      - stable_reticulation
      - stable_honeycombing
      - stable_lymphadenopathy
      - stable_nodule
    caution:
      - stability_duration_and_lesion_type_matter

  morphologic_change:
    definition: lesion changes character, not only size
    examples:
      - GGO_becomes_part_solid
      - nodule_develops_cavitation
      - scar_develops_soft_tissue_component
      - consolidation_becomes_mass_like
    caution:
      - morphologic_change_can_be_more_important_than_size_change
```

---

## 4. Technical Comparability Checklist

```yaml
technical_comparability_checklist:
  acquisition_factors:
    - slice_thickness
    - reconstruction_kernel
    - inspiratory_effort
    - expiratory_phase_or_air_trapping_protocol
    - prone_vs_supine_positioning
    - motion_artifact
    - contrast_vs_noncontrast
    - scanner_or_protocol_difference
    - field_of_view_difference

  interpretation_risks:
    poor_inspiration:
      may_mimic:
        - increased_GGO
        - dependent_opacity
        - apparent_volume_loss

    thicker_slices:
      may_mimic:
        - increased_reticulation
        - obscured_small_nodules
        - reduced_fine_detail

    different_kernel:
      may_mimic:
        - increased_or_decreased_reticular_conspicuity
        - altered_honeycombing_visibility

    contrast_difference:
      may_affect:
        - vascular_visibility
        - lymph_node_assessment
        - mass_or_soft_tissue_conspicuity

    no_expiratory_comparison:
      may_limit:
        - air_trapping_progression
        - mosaic_attenuation_interpretation
        - small_airway_disease_assessment
```

---

## 5. Fibrotic Progression vs Reversible Opacity

```yaml
fibrotic_progression_features:
  structural_progression_clues:
    - increased_reticulation
    - increased_coarseness_of_reticulation
    - increased_extent_or_severity_of_traction_bronchiectasis
    - new_or_increased_honeycombing
    - increased_architectural_distortion
    - increased_lobar_or_regional_volume_loss
    - new_GGO_with_traction_bronchiectasis_context

  interpretation:
    - structural_fibrotic_features_carry_more_weight_than_GGO_alone
    - GGO_requires_assessment_for_reversibility_and_superimposed_events
    - progression_claim_requires_temporal_and_technical_context

reversible_or_potentially_reversible_opacity_features:
  reversible_opacity_clues:
    - new_GGO_without_new_traction_bronchiectasis
    - new_consolidation
    - waxing_waning_opacity
    - migratory_consolidation
    - smooth_septal_thickening
    - dependent_GGO
    - rapid_improvement

  possible_causes:
    - infection
    - edema
    - organizing_pneumonia
    - drug_toxicity
    - hemorrhage
    - aspiration
    - acute_exacerbation
    - inflammatory_flare

  interpretation:
    - reversible_opacity_should_not_be_called_fibrotic_progression_without_structural_change
    - improvement_of_opacity_does_not_prove_fibrosis_reversal
```

---

## 6. Time Interval Logic

```yaml
time_interval_logic:
  hours_to_days:
    more_compatible_with:
      - edema
      - pulmonary_embolism
      - hemorrhage
      - aspiration
      - severe_infection
      - acute_drug_reaction
      - acute_exacerbation_context
    less_compatible_with:
      - ordinary_chronic_fibrotic_progression

  days_to_weeks:
    more_compatible_with:
      - infection
      - acute_exacerbation
      - OP
      - drug_toxicity
      - edema
      - hemorrhage
      - aspiration
      - infarct_evolution

  weeks_to_months:
    more_compatible_with:
      - OP
      - unresolved_infection
      - malignancy
      - drug_toxicity
      - subacute_progression
      - treatment_response
      - recurrent_exposure_or_HP_activity

  months_to_years:
    more_compatible_with:
      - fibrotic_progression
      - chronic_treatment_effect
      - malignancy_growth
      - chronic_infection
      - occupational_or_exposure_related_evolution
      - stable_or_slowly_progressive_ILD
```

---

## 7. Routing by Temporal Pattern

```yaml
temporal_pattern_routing:
  new_bilateral_GGO:
    route_to:
      - acute_exacerbation_vs_infection_vs_edema_v1
      - superimposed_infection_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
    prompt:
      - New bilateral GGO is not specific for progression or acute exacerbation.

  new_focal_consolidation:
    route_to:
      - superimposed_infection_on_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - malignancy_on_fibrotic_ILD_background_v1
    prompt:
      - Focal consolidation requires infection, OP, aspiration, infarct, malignancy, and temporal review.

  migratory_opacity:
    route_to:
      - organizing_pneumonia_on_ILD_background_v1
      - drug_toxicity_treatment_related_lung_injury_v1
      - superimposed_infection_on_ILD_background_v1
    prompt:
      - Migration supports inflammatory behavior but does not prove OP.

  persistent_focal_opacity:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - organizing_pneumonia_on_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    prompt:
      - Persistence should trigger malignancy and chronic infection review.

  new_or_growing_nodule:
    route_to:
      - malignancy_on_fibrotic_ILD_background_v1
      - superimposed_infection_on_ILD_background_v1
    prompt:
      - New or growing nodule should not be hidden inside fibrosis.

  new_cavitation:
    route_to:
      - superimposed_infection_on_ILD_background_v1
      - vascular_edema_hemorrhage_mimic_panel_v1
      - sarcoidosis_vs_GPA_or_granulomatous_vasculitis_gray_zone_v1
      - malignancy_on_fibrotic_ILD_background_v1
    prompt:
      - Cavitation requires infection, vasculitis, malignancy, septic emboli, and complication review.

  increased_structural_fibrosis:
    route_to:
      - fibrotic_ild_triage_map_v1
      - superimposed_events_core_blueprint_v1
    prompt:
      - Structural fibrosis progression should be separated from reversible superimposed opacity.

  decreased_GGO_or_consolidation:
    route_to:
      - treatment_response_future_module
      - superimposed_events_core_blueprint_v1
    prompt:
      - Improvement of airspace opacity does not prove fibrosis reversal.
```

---

## 8. Pattern-Specific Temporal Questions

```yaml
pattern_specific_temporal_questions:
  UIP_or_IPF_like_background:
    ask:
      - Is there increased honeycombing, traction bronchiectasis, reticulation, or volume loss?
      - Is new GGO accompanied by traction bronchiectasis or separate reversible opacity?
      - Could new GGO represent AE, infection, edema, hemorrhage, or drug toxicity?

  NSIP_or_CTD_ILD_background:
    ask:
      - Is GGO inflammatory, fibrotic, treatment-responsive, infectious, edematous, or drug-related?
      - Is there CTD activity or medication change?
      - Has fibrotic NSIP progressed structurally?

  fibrotic_HP_background:
    ask:
      - Is air trapping or three-density pattern changing?
      - Is exposure recurrence possible?
      - Is new GGO inflammatory HP activity, infection, edema, AE, or drug toxicity?

  sarcoidosis_or_granulomatous_background:
    ask:
      - Are nodules stable, new, cavitary, random, or perilymphatic?
      - Is lymphadenopathy symmetric, asymmetric, progressive, or necrotic?
      - Could new change represent infection, malignancy, HP, GLILD, occupational mimic, or vasculitis?

  GLILD_or_immune_deficiency_background:
    ask:
      - Is waxing-waning opacity infection, GLILD activity, lymphoma, or treatment-related?
      - Are immunoglobulins, infection context, and lymphoproliferative features known?

  post_treatment_or_oncology_context:
    ask:
      - Is change progression, pseudoprogression, pneumonitis, sarcoid-like reaction, infection, OP, or radiation injury?
      - Are other tumor sites responding, stable, or progressing?
```

---

## 9. Temporal Pitfall Library

```yaml
temporal_pitfalls:
  - title: Calling progression from a single CT.
    correction: Progression requires longitudinal comparison and technical comparability.

  - title: Calling increased GGO fibrotic progression.
    correction: GGO may reflect infection, edema, OP, drug toxicity, hemorrhage, AE, or inflammation.

  - title: Calling improvement fibrosis reversal.
    correction: Improvement usually reflects reversible opacity unless structural fibrosis also regresses, which requires caution.

  - title: Ignoring technical differences.
    correction: Inspiration, slice thickness, motion, contrast, reconstruction, and positioning can create apparent change.

  - title: Treating persistence as benign.
    correction: Persistent focal opacity requires malignancy, chronic infection, OP, and atelectasis review.

  - title: Treating migration as diagnostic of OP.
    correction: Migration supports OP-like behavior but can also occur in aspiration, drug reaction, eosinophilic disease, or infection.

  - title: Ignoring morphology change.
    correction: Development of cavitation, solid component, mass-like contour, or soft tissue within scar may be more important than size alone.

  - title: Letting baseline ILD swallow new disease.
    correction: Known ILD does not explain every new opacity, nodule, mass, or acute decline.
```

---

## 10. Missing Piece Engine

```yaml
missing_piece_engine:
  default_question: What do we still not know?

  highest_yield_missing_data:
    prior_CT:
      reason: Temporal comparison cannot mature without previous imaging.

    exact_time_interval:
      reason: Hours, days, weeks, months, or years changes the likely explanation.

    technical_comparability:
      reason: Apparent change may be protocol-related rather than biological.

    baseline_pattern:
      reason: UIP, NSIP, HP, sarcoidosis, GLILD, OP, and unclassifiable ILD have different temporal expectations.

    structural_vs_airspace_change:
      reason: Fibrotic progression and reversible opacity must be separated.

    clinical_time_course:
      reason: Symptoms and oxygen trajectory help distinguish acute event from chronic progression.

    treatment_and_medication_timeline:
      reason: Therapy changes can explain improvement, worsening, or new pneumonitis.

    infection_and_microbiology_context:
      reason: Infection can appear, resolve, persist, or mimic progression.

    cardiac_renal_vascular_context:
      reason: Edema, PE, PH, and DAH can alter CT rapidly.

    oncology_context:
      reason: New focal lesion, lymphadenopathy, or persistent consolidation requires malignancy review.

    exposure_context:
      reason: HP or occupational disease may worsen or improve with exposure changes.

    MDD_review:
      reason: Temporal reasoning often requires integration of radiology, pulmonary, clinical course, labs, treatment timeline, and pathology.
```

---

## 11. Reporting Language Templates

```yaml
reporting_language_templates:
  when_prior_CT_unavailable:
    preferred_language:
      - No prior CT is available for temporal comparison.
      - Apparent chronicity or progression cannot be established from this examination alone.
      - Correlation with prior imaging is high-yield.

  when_technical_comparison_limited:
    preferred_language:
      - Comparison is limited by differences in technique, inspiration, slice thickness, reconstruction, or positioning.
      - Apparent change should be interpreted cautiously.

  when_structural_fibrosis_progresses:
    preferred_language:
      - There is interval increase in structural fibrotic abnormality, including increased reticulation / traction bronchiectasis / honeycombing / architectural distortion / volume loss.
      - Superimposed reversible opacity should be assessed separately.

  when_new_GGO_present:
    preferred_language:
      - New ground-glass opacity is present on a background of ILD.
      - Differential considerations include infection, edema, hemorrhage, drug/treatment-related injury, organizing pneumonia, acute exacerbation, and inflammatory activity depending on clinical context.

  when_new_focal_opacity_present:
    preferred_language:
      - New focal opacity requires temporal follow-up or contextual review.
      - Infection, OP, infarct, malignancy, aspiration, and treatment-related change remain considerations.

  when_improvement_seen:
    preferred_language:
      - Interval decrease in ground-glass/consolidative opacity suggests improvement of a reversible component.
      - This should not be equated with reversal of established fibrosis without structural evidence.

  when_persistent_focal_opacity_seen:
    preferred_language:
      - Persistent focal opacity should not be assumed benign without review of growth, morphology, infection, OP, and malignancy context.
```

---

## 12. Evidence and Registry Links

```yaml
evidence_and_registry_links:
  primary_context_sources:
    - ATS_ERS_JRS_ALAT_2022_IPF_PPF
    - superimposed_events_core_blueprint_v1
    - fibrotic_ild_triage_map_v1

  supportive_sources:
    - Fleischner_ILA_position_paper_2020
    - PPF_radiologic_progression_review_sources
    - HRCT_technical_comparability_review_sources_pending
    - CT_temporal_comparison_in_ILD_sources_pending
    - superimposed_events_modules_v0_3

  evidence_notes:
    - Radiological progression in fibrotic ILD emphasizes structural fibrotic worsening, not GGO alone.
    - Prior CT and technical comparability are essential for temporal reasoning.
    - Reversible airspace opacity should be separated from structural fibrosis.
    - Public-ready use requires full source review and expert review.
```

---

## 13. MVP Test Case

```yaml
case_test_temporal_comparison_methodology_001:
  input:
    age: 69
    sex: female
    known_background:
      - fibrotic_ILD
      - probable_UIP_pattern
    prior_CT:
      date: 12_months_ago
      findings:
        - basal_reticulation
        - traction_bronchiectasis
        - no_honeycombing
        - no_diffuse_GGO
    current_CT:
      findings:
        - increased_traction_bronchiectasis
        - increased_reticulation
        - new_patchy_ground_glass_opacity
        - no_new_mass_reported
    technical_comparability:
      slice_thickness: comparable
      inspiration: uncertain
      contrast_status: different
    clinical_context:
      dyspnea_worsening: 2_weeks
      fever: unknown
      oxygen_requirement_change: increased
      medication_timeline: unknown
      infection_testing: unavailable
      cardiac_status: unknown

  output:
    reasoning_state: mixed_structural_progression_plus_possible_superimposed_event
    structural_progression_support:
      - increased_traction_bronchiectasis
      - increased_reticulation
    superimposed_event_support:
      - new_patchy_ground_glass_opacity
      - acute_subacute_symptom_worsening
      - oxygen_requirement_increased
    cannot_conclude:
      - pure_fibrotic_progression
      - acute_exacerbation
      - infection_excluded
      - edema_excluded
      - drug_toxicity_excluded
      - hemorrhage_excluded
    missing_pieces:
      - inspiratory_quality_review
      - infection_review
      - medication_and_treatment_timeline
      - cardiac_and_volume_status
      - hemoptysis_or_anemia_context
      - oxygen_trend_detail
      - MDD_review
    final_prompt:
      - What evidence separates true structural progression from a new superimposed process?
```

---

## 14. Final Page Prompt

Every Temporal Comparison Methodology page should end with:

```text
Do not force the label.

Ask:
1. What was the baseline ILD pattern?
2. Is the prior CT technically comparable?
3. What is truly new, increased, decreased, resolved, migrated, persistent, or stable?
4. Is the change structural fibrosis or reversible airspace opacity?
5. Did the change occur over hours, days, weeks, months, or years?
6. Could infection, edema, AE, OP, drug toxicity, hemorrhage, PE, aspiration, malignancy, or exposure recurrence explain the change?
7. What clinical, treatment, laboratory, exposure, cardiac, renal, vascular, oncology, or immune context is missing?
8. Is follow-up, sampling, urgent review, or MDD needed?
9. What do we still not know?
```