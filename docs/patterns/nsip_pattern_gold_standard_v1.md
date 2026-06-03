# NSIP Pattern Atlas — Gold Standard Datasheet v1

## Document Metadata

```yaml
id: pattern_nsip_gold_standard_v1
title: NSIP Pattern Atlas — Gold Standard Datasheet
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

---

## 1. Identity

```yaml
pattern_id: nsip
full_name: Nonspecific Interstitial Pneumonia Pattern
short_name: NSIP
category: Fibrotic / Inflammatory Interstitial Lung Disease Pattern
primary_domain: HRCT Pattern Recognition
clinical_role: Pattern-level reasoning, not disease-level diagnosis
important_distinction: NSIP is a radiologic/pathologic pattern and may be idiopathic or secondary.
related_disease_contexts:
  - Idiopathic NSIP
  - Systemic sclerosis-associated ILD
  - Myositis-associated ILD
  - Sjogren-associated ILD
  - Mixed connective tissue disease-associated ILD
  - Drug-related ILD
  - Hypersensitivity Pneumonitis mimic
  - Organizing Pneumonia overlap
  - Unclassifiable ILD
```
## 2. Pattern Summary
one_sentence_summary: >
  NSIP is an interstitial pneumonia pattern typically characterized by
  relatively homogeneous ground-glass opacity, fine reticulation, traction
  bronchiectasis in fibrotic cases, and often lower-lung predominance with
  possible subpleural sparing.

danger_statement: >
  NSIP pattern should trigger a search for autoimmune, drug-related, exposure-related,
  or overlap disease before calling it idiopathic.
Key Teaching Point

NSIP is often more homogeneous than UIP.

A classic NSIP pattern should raise the question:

Is this idiopathic NSIP, or is this a manifestation of CTD-ILD or another secondary process?

## 3. HRCT Imaging Anatomy

3.1 Distribution
distribution:
  lower_lobe_predominance: supportive
  basal_gradient: supportive
  bilateral_symmetry: supportive
  subpleural_sparing: strongly_supportive_when_present
  peripheral_distribution: common
  diffuse_distribution: possible
  upper_lobe_predominance: argues_against_classic_nsip
  marked_lobular_air_trapping: suggests_hp_or_airway_component
3.2 Core Imaging Features
core_features:
  ground_glass_opacity:
    role: common_core_feature
    importance: high
    comment: May reflect inflammatory or fine fibrotic abnormality depending on context.

  fine_reticulation:
    role: interstitial_fibrotic_feature
    importance: high

  traction_bronchiectasis_or_bronchiolectasis:
    role: fibrotic_nsip_marker
    importance: high_in_fibrotic_nsip

  volume_loss:
    role: chronic_fibrotic_remodeling_marker
    importance: moderate_to_high

  subpleural_sparing:
    role: classic_supportive_feature
    importance: high_when_present
    caution: absence_does_not_exclude_nsip
3.3 Findings That Require Caution
caution_features:
  honeycombing:
    concern:
      - UIP
      - advanced_fibrotic_NSIP
      - CTD_related_overlap
    warning: Honeycombing should trigger UIP/NSIP gray-zone review.

  marked_air_trapping_or_three_density_pattern:
    concern:
      - fibrotic_hypersensitivity_pneumonitis
      - small_airways_disease

  profuse_centrilobular_nodules:
    concern:
      - hypersensitivity_pneumonitis
      - infection
      - respiratory_bronchiolitis

  dominant_consolidation:
    concern:
      - organizing_pneumonia
      - infection
      - drug_toxicity
      - malignancy

  upper_lobe_dominant_fibrosis:
    concern:
      - sarcoidosis
      - chronic_hp
      - pleuroparenchymal_fibroelastosis
      - pneumoconiosis
## 4. NSIP Subtypes
nsip_subtypes:
  cellular_nsip:
    dominant_features:
      - ground_glass_opacity
      - minimal_reticulation
      - little_or_no_traction_bronchiectasis
      - no_honeycombing
    reasoning_note: Potentially more inflammatory and more treatment-responsive in the correct context.

  fibrotic_nsip:
    dominant_features:
      - reticulation
      - traction_bronchiectasis
      - volume_loss
      - persistent_ground_glass_component
      - usually_little_or_no_honeycombing
    reasoning_note: Requires progression assessment and CTD-ILD evaluation.

  mixed_nsip_op_pattern:
    dominant_features:
      - ground_glass_opacity
      - reticulation
      - consolidation_or_perilobular_op_features
    reasoning_note: Consider CTD-ILD, myositis spectrum, drug toxicity, or organizing pneumonia overlap.
## 5. Confidence Levels
confidence_levels:
  typical_nsip_pattern:
    supportive_features:
      - bilateral_symmetric_lower_lung_ground_glass
      - fine_reticulation
      - traction_bronchiectasis_if_fibrotic
      - subpleural_sparing_when_present
      - relative_homogeneity
      - absent_or_minimal_honeycombing
    interpretation: Strong NSIP pattern; evaluate for CTD-ILD and secondary causes.

  probable_nsip_pattern:
    supportive_features:
      - lower_lung_predominant_ground_glass_and_reticulation
      - some_symmetry
      - no_dominant_alternative_features
      - no_classic_uip_honeycombing
    interpretation: Probable NSIP; clinical context, serology, and temporal behavior are important.

  indeterminate_nsip_or_uip_gray_zone:
    supportive_features:
      - fibrotic_features_present
      - traction_bronchiectasis_present
      - honeycombing_absent_or_uncertain
      - distribution_not_classic
    interpretation: Gray zone; compare against UIP and fibrotic HP.

  alternative_diagnosis_suggested:
    supportive_features:
      - marked_air_trapping
      - profuse_nodules
      - upper_lobe_dominance
      - dominant_consolidation
      - cysts_not_explained_by_fibrosis
      - rapid_new_changes
    interpretation: Pause NSIP pathway and evaluate for HP, OP, sarcoidosis, infection, edema, drug toxicity, or malignancy.
## 6. Differential Field
core_question_1: Is this truly an NSIP pattern?
core_question_2: If NSIP is present, is it idiopathic or secondary?
core_question_3: Is this cellular, fibrotic, mixed, or overlap NSIP?
Main Disease Contexts
differential_contexts:
  idiopathic_nsip:
    supports:
      - compatible_nsip_pattern
      - no_ctd_features
      - no_relevant_exposure
      - no_drug_cause
      - mdd_supports_idiopathic_context
    weakens:
      - autoimmune_features
      - positive_ctd_serology
      - relevant_drug_history
      - marked_air_trapping
      - strong_exposure_history

  systemic_sclerosis_ild:
    supports:
      - raynaud
      - skin_thickening
      - esophageal_dysmotility
      - anti_scl_70
      - anticentromere_context
      - nsip_pattern_common_context
    weakens:
      - absent_scleroderma_features
      - alternative_exposure_or_pattern

  myositis_associated_ild:
    supports:
      - mechanic_hands
      - proximal_muscle_weakness
      - elevated_ck
      - antisynthetase_antibodies
      - mixed_nsip_op_pattern
      - rapidly_progressive_context_possible
    weakens:
      - no_myositis_features
      - negative_myositis_panel_does_not_fully_exclude

  sjogren_or_mctd_related_ild:
    supports:
      - sicca_symptoms
      - arthritis
      - raynaud
      - anti_ssa_or_ssb
      - anti_rnp
      - nsip_or_lip_overlap_possible
    weakens:
      - no_systemic_features
      - no_serologic_support

  fibrotic_hp_mimic:
    supports:
      - exposure_history
      - air_trapping
      - mosaic_attenuation
      - centrilobular_nodules
      - three_density_pattern
      - bal_lymphocytosis
    weakens:
      - no_exposure
      - no_airway_centered_features
      - symmetric_homogeneous_nsip_pattern

  drug_related_nsip_or_op:
    supports:
      - temporal_relationship_to_medication
      - mixed_ground_glass_or_op_features
      - improvement_after_drug_withdrawal_possible
    weakens:
      - no_relevant_drug_exposure
      - long_stable_pre_existing_fibrosis
## 7. Gray Zone Links
gray_zone_links:
  - nsip_vs_uip
  - fibrotic_nsip_vs_probable_uip
  - nsip_vs_fibrotic_hp
  - nsip_vs_organizing_pneumonia
  - cellular_nsip_vs_infection_or_edema
  - fibrotic_nsip_vs_ctd_ild
Key Gray Zone Questions
Is the fibrosis homogeneous or heterogeneous?
Is there true subpleural sparing?
Is honeycombing present, absent, or uncertain?
Are airway-centered findings present?
Is this CTD-related disease?
Is there an OP component?
Has the disease improved, stabilized, or progressed over time?
## 8. Why Not Engine
Why should this not automatically be called idiopathic NSIP?
arguments_against_automatic_idiopathic_nsip_label:
  - autoimmune_features
  - positive_ctd_serology
  - myositis_features
  - systemic_sclerosis_features
  - relevant_drug_exposure
  - occupational_or_environmental_exposure
  - marked_air_trapping
  - profuse_nodules
  - dominant_consolidation
  - rapid_unexpected_change
Why might this not be NSIP?
arguments_against_nsip_pattern:
  - definite_honeycombing_with_patchy_heterogeneous_fibrosis
  - strong_upper_lobe_predominance
  - perilymphatic_nodules
  - three_density_pattern
  - extensive_lobar_consolidation
  - random_nodules
  - diffuse_thin_walled_cysts
Common False Assumptions
false_assumptions:
  - Ground-glass opacity always means cellular NSIP.
  - Symmetric lower-lobe disease automatically means NSIP.
  - NSIP means idiopathic NSIP.
  - Improvement in GGO means fibrosis has reversed.
  - Absence of honeycombing excludes clinically significant fibrosis.
  - Negative autoimmune serology fully excludes CTD-ILD.
## 9. Missing Piece Candidates
missing_piece_engine:
  default_question: What do we still not know?

  high_yield_missing_data:
    autoimmune_screen:
      reason: NSIP is strongly associated with CTD-ILD contexts.
      examples:
        - ANA
        - RF
        - anti_CCP
        - ENA_panel
        - anti_Scl_70
        - anticentromere
        - anti_RNP
        - anti_SSA
        - myositis_panel

    clinical_ctd_review:
      reason: Serology alone is not enough; symptoms and examination matter.
      examples:
        - raynaud
        - sicca
        - inflammatory_arthritis
        - mechanic_hands
        - skin_thickening
        - proximal_muscle_weakness

    prior_ct:
      reason: Temporal behavior separates stable fibrosis, active inflammation, treatment response, and progression.

    medication_history:
      reason: Drug-related ILD may mimic NSIP or NSIP/OP overlap.

    exposure_history:
      reason: Fibrotic HP may mimic fibrotic NSIP.

    expiratory_hrct:
      reason: Air trapping may redirect away from NSIP toward HP or airway-centered disease.

    pft_trend:
      reason: FVC and DLCO trend help distinguish stable disease from progression.

    mdd_review:
      reason: Needed when radiologic, clinical, and serologic signals do not align.
## 10. Temporal Behavior
temporal_behavior:
  improvement_or_partial_regression:
    supportive_changes:
      - reduced_ground_glass_opacity
      - reduced_consolidation_if_op_overlap
      - improved_symptoms_or_pft_when_available
    interpretation:
      - inflammatory_component_or_op_overlap_may_have_improved
    caution:
      - established_reticulation_and_traction_bronchiectasis_may_not_fully_reverse

  stabilization:
    supportive_changes:
      - stable_reticulation
      - stable_traction_bronchiectasis
      - stable_extent_of_fibrosis
      - stable_fvc_or_dlco_when_available
    interpretation:
      - stable_fibrotic_nsip_or_controlled_ctd_ild_possible

  progression:
    supportive_changes:
      - increasing_reticulation
      - increasing_traction_bronchiectasis
      - increasing_fibrosis_extent
      - new_volume_loss
      - declining_fvc_or_dlco_when_available
    interpretation:
      - progressive_fibrotic_phenotype_possible

  unexpectedly_fast_worsening:
    consider:
      - infection
      - acute_exacerbation
      - organizing_pneumonia_flare
      - drug_toxicity
      - pulmonary_edema
      - pulmonary_embolism
      - rapidly_progressive_ctd_ild
## 11. Pattern Interaction Atlas
pattern_interactions:
  nsip_plus_op:
    consider:
      - myositis_associated_ild
      - antisynthetase_syndrome
      - drug_toxicity
      - organizing_pneumonia_overlap
    questions:
      - Is there consolidation or perilobular opacity?
      - Are myositis symptoms present?
      - Is the course rapidly progressive?

  nsip_plus_air_trapping:
    consider:
      - fibrotic_hp
      - small_airways_disease
      - mixed_ctd_airway_disease
    questions:
      - Is expiratory CT available?
      - Is there exposure history?
      - Is three-density pattern present?

  nsip_plus_cysts:
    consider:
      - LIP_overlap
      - Sjogren_related_ILD
      - amyloidosis
      - lymphoproliferative_disease
    questions:
      - Are cysts diffuse and thin-walled?
      - Are nodules present?
      - Are sicca symptoms present?

  nsip_plus_honeycombing:
    consider:
      - UIP_overlap
      - advanced_fibrotic_nsip
      - CTD_related_fibrotic_overlap
    questions:
      - Is honeycombing definite or overcalled?
      - Is fibrosis homogeneous or patchy?
      - Is subpleural sparing present?

  nsip_plus_nodules:
    consider:
      - hp
      - sarcoidosis
      - infection
      - pneumoconiosis
      - malignancy
    questions:
      - Are nodules centrilobular, perilymphatic, or random?
      - Are they new?
      - Is there lymphadenopathy?
## 12. Superimposed Event Atlas
superimposed_events:
  new_ground_glass_on_nsip_background:
    consider:
      - inflammatory_flare
      - infection
      - drug_toxicity
      - edema
      - hemorrhage
      - acute_exacerbation
    warning: New GGO should not automatically be interpreted as NSIP progression.

  new_consolidation:
    consider:
      - organizing_pneumonia_overlap
      - infection
      - drug_toxicity
      - aspiration
      - malignancy
    warning: Persistent or asymmetric consolidation requires careful follow-up.

  new_nodule_or_mass:
    consider:
      - malignancy
      - infection
      - rheumatoid_nodule
      - sarcoid_like_reaction
      - lymphoproliferative_disease
    warning: Do not let background ILD hide a new focal lesion.

  rapid_diffuse_worsening:
    consider:
      - rapidly_progressive_ctd_ild
      - infection
      - acute_exacerbation
      - pulmonary_edema
      - pulmonary_embolism
      - treatment_related_lung_injury
## 13. Diagnostic Escalation
diagnostic_escalation:
  mdd_needed_if:
    - fibrotic_nsip_vs_probable_uip_uncertainty
    - possible_ctd_ild
    - possible_myositis_associated_ild
    - discordant_serology_and_imaging
    - rapid_progression
    - major_pattern_interaction
    - suspected_superimposed_event

  rheumatology_review_high_value_if:
    - positive_autoantibodies
    - raynaud
    - sicca
    - inflammatory_arthritis
    - mechanic_hands
    - skin_thickening
    - proximal_muscle_weakness

  bal_may_help_if:
    - hp_suspected
    - infection_suspected
    - alveolar_process_suspected
    - immunosuppressed_patient

  biopsy_discussion_if:
    - diagnosis_remains_uncertain_after_clinical_hrct_lab_review
    - result_would_change_management
    - patient_risk_is_acceptable
    - mdd_supports_need

  follow_up_ct_reasonable_if:
    - early_or_mild_disease
    - uncertainty_between_inflammation_and_fibrosis
    - suspected_treatment_response
    - uncertain_progression
## 14. Treatment Response Reasoning
treatment_response_reasoning:
  response_possible_components:
    ground_glass_opacity:
      possible_meaning: inflammatory_or_reversible_component
      caution: not_all_ground_glass_is_reversible_inflammation

    consolidation_or_op_overlap:
      possible_meaning: organizing_pneumonia_component
      caution: persistent_consolidation_needs_reassessment

    reticulation:
      possible_meaning: fibrotic_component
      caution: may_stabilize_without_disappearing

    traction_bronchiectasis:
      possible_meaning: established_fibrotic_remodeling
      caution: true_reversal_is_less_expected

  response_categories:
    improved:
      imaging_logic:
        - reduced_ground_glass
        - reduced_consolidation
        - stable_or_reduced_extent
      caution: determine_whether_fibrosis_or_superimposed_inflammation_changed

    stable:
      imaging_logic:
        - no_meaningful_increase_in_fibrosis
        - stable_traction_bronchiectasis
        - stable_pft_when_available

    progressed:
      imaging_logic:
        - increased_fibrosis_extent
        - increased_traction_bronchiectasis
        - new_volume_loss
        - declining_pft_when_available
## 15. Pitfall Library
pitfalls:
  - title: Calling all ground-glass opacity cellular NSIP.
    correction: Ground-glass opacity may reflect inflammation, fine fibrosis, edema, infection, drug toxicity, or OP overlap.

  - title: Calling NSIP idiopathic too early.
    correction: CTD-ILD, drug-related ILD, and exposure-related disease must be considered.

  - title: Missing myositis-associated ILD.
    correction: Ask about mechanic hands, muscle weakness, CK, and myositis antibodies.

  - title: Ignoring subpleural sparing.
    correction: Subpleural sparing, when present, is a powerful NSIP clue.

  - title: Overcalling UIP when honeycombing is absent.
    correction: Fibrotic NSIP and probable UIP may overlap and require MDD.

  - title: Assuming improvement means fibrosis reversed.
    correction: Improvement may reflect resolution of inflammation, OP, infection, or edema rather than reversal of established fibrosis.
## 16. Evidence and Guideline Registry
evidence_and_guideline_registry:
  primary_guidelines_to_link:
    - ATS_ERS_IIP_classification_statement
    - ATS_ERS_JRS_ALAT_IPF_PPF_guideline
    - ACR_CHEST_SARD_ILD_screening_monitoring_guideline
    - ATS_SSc_ILD_treatment_guideline

  evidence_notes:
    - NSIP is recognized as a clinicopathologic ILD pattern/entity in international IIP classification.
    - NSIP pattern often requires evaluation for CTD-ILD and other secondary causes.
    - Fibrotic NSIP can behave as a progressive fibrotic ILD and may require longitudinal assessment.
    - Treatment response interpretation must distinguish reversible inflammatory/OP components from established fibrosis.

  consensus_strength:
    nsip_as_pattern_entity: high
    nsip_ctd_ild_association: high
    fibrotic_nsip_vs_probable_uip_gray_zone: high_complexity
    treatment_response_imaging_interpretation: context_dependent
## 17. Narrative Questions

Every NSIP page should end with these questions:

narrative_questions:
  - Is this truly an NSIP pattern?
  - Is this cellular, fibrotic, mixed, or overlap NSIP?
  - Is this idiopathic or secondary?
  - Are there CTD features that have not been recognized yet?
  - Is there a drug or exposure explanation?
  - What does the prior CT show?
  - Is the disease improving, stable, or progressing?
  - Is the ground-glass component reversible inflammation, fine fibrosis, infection, edema, or OP overlap?
  - Are there findings that do not belong to classic NSIP?
  - What is the single most important missing piece of information?
## 18. MVP Screen Behavior
mvp_screen_behavior:
  main_panel:
    - pattern_summary
    - nsip_subtypes
    - hrct_imaging_anatomy
    - confidence_levels
    - differential_field

  right_sidebar:
    - why_not_engine
    - missing_piece_candidates
    - gray_zone_links
    - treatment_response_reasoning
    - pitfall_library
    - guideline_registry

  bottom_panel:
    - temporal_comparison_prompt
    - rheumatology_review_prompt
    - mdd_prompt
    - what_do_we_still_not_know_prompt
## 19. MVP Test Case
case_test_nsip_001:
  input:
    age: 48
    sex: female
    hrct:
      - bilateral_lower_lung_ground_glass
      - fine_reticulation
      - traction_bronchiectasis
      - possible_subpleural_sparing
      - no_definite_honeycombing
      - no_marked_air_trapping
    history:
      raynaud: unknown
      sicca: unknown
      myositis_symptoms: unknown
      medication_history: unknown
      prior_ct: unavailable
    laboratory:
      autoimmune_screen: unavailable

  system_output:
    pattern_confidence: probable_nsip_pattern
    disease_statement: NSIP pattern is possible, but idiopathic NSIP is not established.
    why_not_idiopathic_nsip:
      - ctd_features_unknown
      - autoimmune_screen_unavailable
      - medication_history_unknown
      - prior_ct_unavailable
    missing_pieces:
      - autoimmune_screen
      - clinical_ctd_review
      - medication_history
      - prior_ct
    final_prompt:
      - What evidence is needed before calling this idiopathic NSIP?  