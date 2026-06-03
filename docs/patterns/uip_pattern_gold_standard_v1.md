# UIP Pattern Atlas — Gold Standard Datasheet v1

## Document Metadata

```yaml
id: pattern_uip_gold_standard_v1
title: UIP Pattern Atlas — Gold Standard Datasheet
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: pattern_datasheet
primary_audience:
  - thoracic radiologists
  - pulmonologists
  - rheumatologists
  - residents
  - fellows
clinical_scope: educational_reasoning_support
diagnostic_authority: none
last_updated: draft
```

## 0. Platform Safety Statement

This platform does not diagnose patients, classify individual cases, or recommend treatment.

It is designed to support structured clinical reasoning in interstitial lung disease by helping users understand:

why a pattern is being considered,
which differential diagnoses remain on the table,
which findings weaken a working diagnosis,
what information is still missing,
when uncertainty should be preserved,
and when multidisciplinary discussion may be needed.

Core principle:
Diagnosing ILD is not about finding the right answer. It is about asking the right next question — and knowing when you don’t have enough information yet.

## 1. Identity
pattern_id: uip
full_name: Usual Interstitial Pneumonia Pattern
short_name: UIP
category: Fibrotic Interstitial Lung Disease Pattern
primary_domain: HRCT Pattern Recognition
clinical_role: Pattern-level reasoning, not disease-level diagnosis
important_distinction: UIP is a radiologic/pathologic pattern; IPF is a clinical disease diagnosis.
Related Disease Contexts
related_disease_contexts:
  - Idiopathic Pulmonary Fibrosis
  - Rheumatoid Arthritis-associated ILD
  - Other CTD-ILD
  - Fibrotic Hypersensitivity Pneumonitis
  - Asbestosis
  - Drug-related fibrotic ILD
  - Unclassifiable fibrotic ILD
## 2. Pattern Summary
one_sentence_summary: >
  UIP is a fibrotic interstitial lung disease pattern typically characterized
  by basal and subpleural-predominant reticulation, traction bronchiectasis or
  bronchiolectasis, architectural distortion, and, in classic cases, honeycombing.

danger_statement: >
  UIP pattern does not automatically mean IPF.
Key Teaching Point

UIP is a pattern.
IPF is a diagnosis.

A UIP pattern may support IPF in the correct clinical context, but secondary causes such as CTD-ILD, fibrotic HP, asbestosis, and drug-related ILD must be considered before labeling a case as idiopathic.

## 3. HRCT Imaging Anatomy
# 3.1 Distribution
distribution:
  lower_lobe_predominance: supportive
  basal_gradient: supportive
  subpleural_predominance: strongly_supportive
  peripheral_distribution: supportive
  upper_lobe_predominance: argues_against_classic_uip
  peribronchovascular_dominance: argues_against_classic_uip
  central_dominance: argues_against_classic_uip
# 3.2 Core Fibrotic Features
core_features:
  reticulation:
    role: core_fibrotic_feature
    importance: high

  traction_bronchiectasis_or_bronchiolectasis:
    role: fibrosis_marker
    importance: high

  architectural_distortion:
    role: chronic_fibrotic_remodeling_marker
    importance: high

  honeycombing:
    role: classic_uip_feature
    importance: very_high
    caution: may_be_confused_with_paraseptal_emphysema_or_subpleural_cysts
# 3.3 Findings That Require Caution
caution_features:
  extensive_ground_glass_opacity:
    concern:
      - NSIP
      - OP
      - infection
      - edema
      - drug_toxicity
      - acute_exacerbation

  dominant_consolidation:
    concern:
      - organizing_pneumonia
      - infection
      - malignancy
      - drug_toxicity

  profuse_nodules:
    concern:
      - hypersensitivity_pneumonitis
      - sarcoidosis
      - pneumoconiosis
      - infection
      - malignancy

  marked_air_trapping:
    concern:
      - fibrotic_hypersensitivity_pneumonitis
      - small_airways_disease

  cysts_not_explained_by_honeycombing:
    concern:
      - LIP
      - LAM
      - PLCH
      - Birt-Hogg-Dube
      - amyloidosis
## 4. Confidence Levels
confidence_levels:
  definite_uip_pattern:
    supportive_features:
      - basal_and_subpleural_predominance
      - reticulation
      - honeycombing
      - traction_bronchiectasis_may_be_present
      - no_dominant_alternative_features
    interpretation: Strong UIP pattern.

  probable_uip_pattern:
    supportive_features:
      - basal_and_subpleural_predominance
      - reticulation
      - traction_bronchiectasis_or_bronchiolectasis
      - no_honeycombing
      - no_dominant_alternative_features
    interpretation: Probable UIP pattern; clinical context and MDD may be decisive.

  indeterminate_for_uip:
    supportive_features:
      - fibrotic_abnormality_present
      - insufficient_for_definite_or_probable_uip
      - no_clear_alternative_pattern
    interpretation: Gray zone; temporal comparison and multidisciplinary review are high value.

  alternative_diagnosis_suggested:
    supportive_features:
      - upper_or_mid_lung_predominance
      - peribronchovascular_predominance
      - extensive_ground_glass
      - profuse_nodules
      - marked_mosaic_attenuation_or_air_trapping
      - dominant_consolidation
      - cysts_not_explained_by_honeycombing
    interpretation: Pause the IPF pathway and search for alternative explanations.
## 5. Differential Field
core_question_1: Is this truly a UIP pattern?
core_question_2: If UIP is present, what is the cause?
core_question_3: What evidence is missing before calling this idiopathic?
Main Disease Contexts
differential_contexts:
  ipf:
    supports:
      - older_age
      - classic_basal_subpleural_uip
      - no_known_exposure
      - no_ctd_features
    weakens:
      - young_age
      - autoimmune_features
      - exposure_history
      - marked_air_trapping
      - profuse_nodules

  ctd_uip:
    supports:
      - inflammatory_arthritis
      - raynaud
      - sicca_symptoms
      - mechanic_hands
      - myositis_features
      - positive_autoantibodies
    weakens:
      - absent_systemic_features
      - negative_screening_does_not_fully_exclude

  fibrotic_hp:
    supports:
      - bird_exposure
      - mold_exposure
      - farming_exposure
      - air_trapping
      - mosaic_attenuation
      - centrilobular_nodules
      - three_density_pattern
      - bal_lymphocytosis
    weakens:
      - no_exposure_identified
      - no_airway_centered_features

  asbestosis:
    supports:
      - occupational_exposure
      - pleural_plaques
      - diaphragmatic_pleural_calcification
      - basal_subpleural_fibrosis
    weakens:
      - no_exposure_history
      - no_pleural_findings
## 6. Gray Zone Links
gray_zone_links:
  - uip_vs_fibrotic_hp
  - uip_vs_fibrotic_nsip
  - ipf_vs_ctd_uip
  - uip_vs_asbestosis
  - uip_vs_cpfe
  - uip_with_superimposed_infection_or_exacerbation
Key Gray Zone Questions
Is there airway-centered disease?
Is expiratory HRCT available?
Is there a relevant exposure history?
Are there autoimmune clinical or serologic clues?
Are the fibrotic changes temporally progressive, stable, or partially reversible?
Are there findings that do not belong to classic UIP?
## 7. Why Not Engine
Why should this not automatically be called IPF?
arguments_against_automatic_ipf_label:
  - young_age
  - autoimmune_features
  - positive_ctd_serology
  - relevant_exposure_history
  - marked_air_trapping
  - profuse_nodules
  - upper_lobe_predominance
  - pleural_plaques
  - dominant_consolidation
  - unexpectedly_rapid_change
  - new_mass_or_nodule
Common False Assumptions
false_assumptions:
  - UIP pattern equals IPF.
  - Honeycombing always means IPF.
  - Air trapping is a minor detail.
  - Prior CT is optional when assessing progression.
  - CTD screening is unnecessary in older patients.
  - New ground-glass opacity in fibrotic ILD always means acute exacerbation.
## 8. Missing Piece Candidates
missing_piece_engine:
  default_question: What do we still not know?

  high_yield_missing_data:
    prior_ct:
      reason: Temporal behavior cannot be assessed without comparison.

    exposure_history:
      reason: Fibrotic HP and occupational ILD cannot be reasonably excluded without it.

    autoimmune_screen:
      reason: CTD-ILD may mimic UIP/IPF and may change clinical interpretation.

    expiratory_hrct:
      reason: Air trapping and mosaic attenuation may redirect toward HP or airway-centered disease.

    bal:
      reason: May help in suspected HP, infection, or alveolar processes.

    mdd_review:
      reason: Required when imaging, clinical context, and laboratory data conflict.

    biopsy_discussion:
      reason: Consider only if uncertainty remains and the result would change management.
## 9. Temporal Behavior
temporal_behavior:
  progression:
    supportive_changes:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_honeycombing
      - increasing_fibrosis_extent
      - progressive_volume_loss

  stabilization:
    supportive_changes:
      - stable_fibrosis_extent
      - stable_traction_bronchiectasis
      - stable_pft_when_available

  regression_or_partial_improvement:
    supportive_changes:
      - reduced_ground_glass
      - reduced_consolidation
      - reduced_inflammatory_component
    caution:
      - established_honeycombing_usually_does_not_truly_regress
      - improvement_may_reflect_resolution_of_superimposed_inflammation_infection_edema_or_op

  unexpectedly_fast_worsening:
    consider:
      - acute_exacerbation
      - infection
      - pulmonary_edema
      - pulmonary_embolism
      - drug_toxicity
      - aspiration
      - malignancy
## 10. Pattern Interaction Atlas
pattern_interactions:
  fibrosis_plus_emphysema:
    consider:
      - CPFE
      - IPF_with_emphysema
      - smoking_related_ILD
      - PLCH_spectrum

  fibrosis_plus_nodules:
    consider:
      - malignancy
      - sarcoidosis
      - pneumoconiosis
      - fibrotic_hp
      - infection
      - rheumatoid_nodules

  fibrosis_plus_cysts:
    consider:
      - honeycombing
      - emphysema_mimic
      - LIP
      - amyloidosis
      - PLCH
      - Birt_Hogg_Dube

  fibrosis_plus_consolidation:
    consider:
      - organizing_pneumonia
      - infection
      - acute_exacerbation
      - adenocarcinoma
      - drug_toxicity

  fibrosis_plus_air_trapping:
    consider:
      - fibrotic_hp
      - small_airways_disease
      - smoking_related_airway_disease
## 11. Superimposed Event Atlas
superimposed_events:
  new_ground_glass_on_fibrotic_background:
    consider:
      - acute_exacerbation
      - infection
      - pulmonary_edema
      - drug_toxicity
      - hemorrhage
      - aspiration

  new_nodule_or_mass:
    consider:
      - lung_cancer
      - infection
      - rheumatoid_nodule
      - sarcoid_like_reaction
      - scar_related_change

  new_consolidation:
    consider:
      - infection
      - organizing_pneumonia
      - adenocarcinoma
      - drug_toxicity
      - aspiration

  rapid_diffuse_worsening:
    consider:
      - acute_exacerbation
      - infection
      - pulmonary_edema
      - pulmonary_embolism
      - treatment_related_lung_injury
## 12. Diagnostic Escalation
diagnostic_escalation:
  mdd_needed_if:
    - probable_or_indeterminate_uip
    - young_patient
    - discordant_clinical_and_imaging_features
    - possible_ctd
    - possible_hp
    - possible_occupational_ild
    - major_pattern_interaction
    - suspected_superimposed_event

  bal_may_help_if:
    - hp_suspected
    - infection_suspected
    - immunosuppressed_patient
    - alveolar_process_suspected

  biopsy_discussion_if:
    - diagnosis_remains_uncertain_after_clinical_hrct_lab_review
    - result_would_change_management
    - patient_risk_is_acceptable
    - mdd_supports_need

  follow_up_ct_reasonable_if:
    - low_confidence_pattern
    - mild_or_early_disease
    - uncertain_progression
    - need_to_distinguish_transient_inflammation_from_fibrosis
## 13. Pitfall Library
pitfalls:
  - title: UIP pattern equals IPF.
    correction: UIP is a pattern; IPF requires clinical context and exclusion of known causes.

  - title: Overcalling honeycombing.
    correction: Paraseptal emphysema, subpleural cysts, and traction bronchiolectasis can mimic honeycombing.

  - title: Ignoring expiratory CT.
    correction: Air trapping may be crucial for fibrotic HP.

  - title: Calling progression without prior CT.
    correction: Technique, inspiration level, and slice thickness can mimic change.

  - title: Calling new GGO acute exacerbation by default.
    correction: Infection, edema, drug toxicity, hemorrhage, and aspiration must be considered.

  - title: Missing a new nodule within fibrosis.
    correction: Malignancy or infection may be hidden within distorted fibrotic lung.
## 14. Evidence and Guideline Registry
evidence_and_guideline_registry:
  primary_guidelines_to_link:
    - ATS_ERS_JRS_ALAT_IPF_PPF_guideline
    - ATS_ERS_JRS_ALAT_IPF_diagnostic_guidance
    - Fleischner_IPF_white_paper
    - ATS_JRS_ALAT_Hypersensitivity_Pneumonitis_guideline

  evidence_notes:
    - UIP categories are guideline-linked but do not replace clinical diagnosis.
    - HP evaluation requires exposure history, HRCT pattern assessment, and often BAL or pathology depending on confidence.
    - Biopsy decisions are context-dependent and should be made through risk-benefit assessment and MDD.
## 15. Narrative Questions

Every UIP page should end with these questions:

narrative_questions:
  - Is this truly a UIP pattern?
  - If UIP is present, what is the likely cause?
  - Is this idiopathic, autoimmune-related, exposure-related, occupational, or drug-related?
  - What does the prior CT show?
  - Is the fibrosis progressive, stable, or complicated by a superimposed process?
  - Are there findings that do not belong to classic UIP?
  - Has exposure history been adequately assessed?
  - Has CTD screening been considered?
  - Is MDD needed?
  - What is the single most important missing piece of information?
## 16. MVP Screen Behavior
mvp_screen_behavior:
  main_panel:
    - pattern_summary
    - hrct_imaging_anatomy
    - confidence_levels
    - differential_field

  right_sidebar:
    - why_not_engine
    - missing_piece_candidates
    - gray_zone_links
    - pitfall_library
    - superimposed_event_alerts
    - guideline_registry

  bottom_panel:
    - temporal_comparison_prompt
    - mdd_prompt
    - what_do_we_still_not_know_prompt
## 17. MVP Test Case
case_test_uip_001:
  input:
    age: 67
    sex: male
    hrct:
      - basal_subpleural_reticulation
      - traction_bronchiectasis
      - honeycombing
      - no_extensive_ground_glass
      - no_marked_air_trapping
    history:
      exposure: unknown
      ctd_symptoms: unknown
      prior_ct: unavailable

  system_output:
    pattern_confidence: definite_uip_pattern_likely
    disease_statement: IPF is possible, but not confirmed by pattern alone.
    why_not_ipf:
      - exposure_history_unknown
      - ctd_screen_unknown
      - prior_ct_unavailable
    missing_pieces:
      - exposure_history
      - autoimmune_screen
      - prior_ct
    final_prompt:
      - What is the most important missing information before calling this idiopathic?