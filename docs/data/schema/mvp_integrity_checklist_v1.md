# MVP Integrity Checklist — v1

## Document Metadata

```yaml
id: data_schema_mvp_integrity_checklist_v1
title: MVP Integrity Checklist
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: validation_checklist
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This checklist defines the minimum integrity requirements for the ILD Reasoning Platform MVP blueprint.

It is designed to verify that the platform remains:

- structured,
- cross-linkable,
- evidence-aware,
- uncertainty-preserving,
- safe from diagnostic overreach,
- and ready for future conversion into JSON, TypeScript objects, database rows, and UI components.

---

## 1. Required MVP Files

```yaml
required_mvp_files:
  root:
    - README.md

  blueprint:
    - docs/project_blueprint_v1.md

  patterns:
    - docs/patterns/uip_pattern_gold_standard_v1.md
    - docs/patterns/nsip_pattern_gold_standard_v1.md
    - docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md

  reasoning_maps:
    - docs/reasoning/uip_vs_nsip_gray_zone_v1.md
    - docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md
    - docs/reasoning/nsip_vs_fibrotic_hp_gray_zone_v1.md
    - docs/reasoning/fibrotic_ild_triage_map_v1.md

  navigation:
    - docs/navigation/mvp_crosslink_registry_v1.md
    - docs/navigation/mvp_entry_flow_v1.md
    - docs/navigation/mvp_home_wireframe_v1.md

  evidence:
    - docs/evidence/guideline_registry_v1.md

  schemas:
    - docs/data/schema/pattern_schema_v1.md
    - docs/data/schema/reasoning_map_schema_v1.md
```

---

## 2. Safety Boundary Checks

```yaml
safety_boundary_checks:
  required_on_all_core_pages:
    - platform_does_not_diagnose_patients
    - platform_does_not_recommend_treatment
    - platform_does_not_replace_clinician_judgment
    - platform_does_not_replace_MDD
    - platform_preserves_uncertainty

  forbidden_language:
    - final_diagnosis
    - confirmed_diagnosis
    - diagnose_now
    - treatment_recommendation
    - probability_for_individual_patient
    - rules_out
    - proves
    - confirms

  preferred_language:
    - supports
    - weakens
    - raises_concern_for
    - remains_possible
    - requires_review
    - missing_information
    - gray_zone
    - MDD_may_be_needed
```

---

## 3. Required Page Ending

Every MVP page should end with one of the following prompts:

```yaml
required_final_prompts:
  primary:
    - What do we still not know?

  expanded:
    - Do not force the label.
    - What pattern is most supported?
    - What pattern is still competing?
    - What finding weakens the leading label?
    - What clinical, exposure, laboratory, or temporal data are missing?
    - Is there a red flag or superimposed event?
    - Is MDD needed?
    - What do we still not know?
```

---

## 4. Pattern Datasheet Integrity Checks

```yaml
pattern_datasheet_integrity:
  required_sections:
    - metadata
    - platform_safety_statement
    - identity
    - pattern_summary
    - imaging_anatomy
    - confidence_levels
    - differential_field
    - gray_zone_links
    - why_not_engine
    - missing_piece_candidates
    - temporal_behavior
    - pattern_interactions
    - superimposed_events
    - diagnostic_escalation
    - pitfall_library
    - evidence_and_guideline_registry
    - narrative_questions
    - mvp_screen_behavior
    - mvp_test_case

  required_safety_logic:
    - pattern_must_not_equal_disease
    - disease_context_must_require_clinical_context
    - missing_data_must_be_visible
    - gray_zone_links_must_exist
    - mvp_test_case_must_not_output_final_diagnosis
```

---

## 5. Reasoning Map Integrity Checks

```yaml
reasoning_map_integrity:
  required_sections:
    - metadata
    - purpose
    - core_distinction
    - features_supporting_each_pathway
    - direct_comparison_matrix
    - gray_zone_scenarios
    - why_not_engine
    - missing_piece_engine
    - temporal_reasoning
    - diagnostic_escalation_logic
    - pitfall_library
    - mvp_test_case
    - final_page_prompt

  required_reasoning_logic:
    - competing_pathways_must_be_visible
    - overlap_must_be_explicit
    - false_certainty_must_be_blocked
    - missing_pieces_must_be_named
    - MDD_triggers_must_be_declared
```

---

## 6. Evidence Integrity Checks

```yaml
evidence_integrity:
  required:
    - guideline_registry_exists
    - diagnosis_guidelines_separated_from_treatment_guidelines
    - guideline_scope_declared
    - full_source_review_required_when_needed
    - evidence_confidence_labels_defined

  forbidden:
    - using_treatment_guideline_as_diagnostic_authority
    - using_pattern_recognition_as_final_diagnosis
    - claiming_guideline_compliance_without_source_review
```

---

## 7. Crosslink Integrity Checks

```yaml
crosslink_integrity:
  required:
    - every_pattern_links_to_gray_zone_map
    - every_gray_zone_links_to_pattern_pages
    - fibrotic_ild_triage_links_to_all_three_patterns
    - homepage_links_to_triage_and_patterns
    - guideline_registry_links_to_pattern_and_reasoning_modules

  mvp_required_triangle:
    - UIP_to_NSIP
    - UIP_to_Fibrotic_HP
    - NSIP_to_Fibrotic_HP
```

---

## 8. Missing Piece Engine Checks

```yaml
missing_piece_engine_integrity:
  required_missing_items_across_mvp:
    - prior_CT
    - expiratory_HRCT
    - detailed_exposure_history
    - autoimmune_screen
    - clinical_CTD_review
    - medication_history
    - occupational_history
    - PFT_trend
    - BAL_lymphocytosis_when_relevant
    - MDD_review

  rule:
    - The platform should help users identify the next highest-yield missing information, not force a diagnosis.
```

---

## 9. Temporal Reasoning Checks

```yaml
temporal_reasoning_integrity:
  required_states:
    - progression
    - stabilization
    - partial_improvement_or_regression
    - unexpectedly_fast_worsening

  safety_rule:
    - A single HRCT snapshot must not be treated as proof of progression.

  required_superimposed_event_awareness:
    - infection
    - acute_exacerbation
    - pulmonary_edema
    - pulmonary_embolism
    - drug_toxicity
    - aspiration
    - malignancy
    - exposure_rechallenge_when_relevant
```

---

## 10. MVP Lock Criteria

The MVP blueprint can be considered structurally locked when:

```yaml
mvp_lock_criteria:
  atlas_core_complete:
    - UIP
    - NSIP
    - Fibrotic_HP

  reasoning_core_complete:
    - UIP_vs_NSIP
    - UIP_vs_Fibrotic_HP
    - NSIP_vs_Fibrotic_HP
    - Fibrotic_ILD_Triage

  navigation_core_complete:
    - Crosslink_Registry
    - Entry_Flow
    - Home_Wireframe

  evidence_core_complete:
    - Guideline_Registry

  data_schema_core_complete:
    - Pattern_Schema
    - Reasoning_Map_Schema
    - MVP_Integrity_Checklist

  safety_core_preserved:
    - no_diagnosis_claim
    - no_treatment_recommendation
    - uncertainty_preserved
    - missing_data_visible
    - MDD_prompt_available
```

---

## 11. Final Integrity Rule

A valid MVP page must answer:

```text
1. What is being reviewed?
2. What supports it?
3. What weakens it?
4. What mimics it?
5. What data are missing?
6. What temporal behavior matters?
7. What red flags or superimposed events could distort interpretation?
8. What guideline or evidence scope applies?
9. When is MDD needed?
10. What do we still not know?
```