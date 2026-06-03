# Reasoning Map Schema — v1

## Document Metadata

```yaml
id: data_schema_reasoning_map_schema_v1
title: Reasoning Map Schema
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: data_schema
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This schema defines the standard structure for all reasoning maps in the ILD Reasoning Platform.

It applies to:

- gray-zone comparison maps,
- triage reasoning engines,
- differential reasoning maps,
- temporal reasoning maps,
- superimposed event reasoning maps,
- and future Missing Piece Engine modules.

This schema does not create diagnostic authority.

It defines educational reasoning structure.

---

## 1. Required Top-Level Fields

```yaml
required_top_level_fields:
  - metadata
  - purpose
  - linked_patterns
  - core_distinction
  - features_supporting_each_pathway
  - comparison_matrix
  - gray_zone_scenarios
  - why_not_engine
  - missing_piece_engine
  - temporal_reasoning
  - diagnostic_escalation_logic
  - pitfall_library
  - mvp_test_case
  - final_page_prompt
```

---

## 2. Metadata Schema

```yaml
metadata:
  id: string
  title: string
  version: string
  language: string
  status: enum
  project: string
  content_type: enum
  linked_patterns: list[string]
  linked_reasoning_maps: optional[list[string]]
  primary_audience: list[string]
  clinical_scope: string
  diagnostic_authority: enum
  last_updated: string
```

### Allowed Values

```yaml
allowed_values:
  status:
    - blueprint_draft
    - evidence_review_pending
    - clinically_reviewed
    - public_ready
    - archived

  content_type:
    - gray_zone_reasoning_map
    - triage_reasoning_engine
    - temporal_reasoning_map
    - superimposed_event_reasoning_map
    - missing_piece_engine
    - data_schema

  diagnostic_authority:
    - none
```

---

## 3. Purpose Schema

```yaml
purpose:
  summary: string
  does_not_do: list[string]
  helps_user_ask: list[string]
```

### Required Safety Language

Every reasoning map must explicitly state that it does not diagnose individual patients.

Required concepts:

```yaml
required_safety_concepts:
  - does_not_diagnose
  - does_not_recommend_treatment
  - does_not_replace_MDD
  - preserves_uncertainty
  - identifies_missing_information
```

---

## 4. Linked Pattern Schema

```yaml
linked_patterns:
  - pattern_id: string
    path: optional[string]
    role: enum
```

### Roles

```yaml
pattern_roles:
  - primary_comparison_target
  - secondary_comparison_target
  - mimic
  - competing_context
  - future_expansion
```

Example:

```yaml
linked_patterns:
  - pattern_id: pattern_uip_gold_standard_v1
    role: primary_comparison_target

  - pattern_id: pattern_nsip_gold_standard_v1
    role: secondary_comparison_target
```

---

## 5. Core Distinction Schema

```yaml
core_distinction:
  pathway_id:
    reasoning_center: string
    classic_clues: list[string]
    strongest_features: optional[list[string]]
    danger_statement: string
```

### Purpose

This section defines the conceptual difference between competing pathways.

It should answer:

```text
What is the central reasoning logic behind each pathway?
```

Example:

```yaml
core_distinction:
  uip:
    reasoning_center: basal_subpleural_patchy_fibrosis
    strongest_feature: honeycombing
    danger_statement: UIP pattern does not equal IPF.

  fibrotic_hp:
    reasoning_center: fibrotic_ILD_with_airway_centered_or_exposure_related_clues
    strongest_features:
      - air_trapping
      - three_density_pattern
      - exposure_history
    danger_statement: Fibrotic HP can mimic UIP/IPF.
```

---

## 6. Features Supporting Each Pathway Schema

```yaml
features_supporting_each_pathway:
  pathway_id:
    distribution: optional[list[string]]
    morphology: optional[list[string]]
    clinical_context: optional[list[string]]
    exposure_context: optional[list[string]]
    temporal_behavior: optional[list[string]]
    supportive_tests: optional[list[string]]
    reasoning_weight: optional[map]
```

### Safety Rule

Supporting features must not be treated as diagnostic confirmation.

Allowed wording:

```text
supports
suggests
raises concern for
increases reasoning weight
```

Disallowed wording:

```text
confirms
proves
rules in
rules out
```

---

## 7. Comparison Matrix Schema

```yaml
comparison_matrix:
  columns:
    - feature
    - pathway_a
    - pathway_b
    - reasoning_note
  rows:
    - feature: string
      pathway_a: string
      pathway_b: string
      reasoning_note: string
```

### Required Rule

Every gray-zone map must include a direct comparison matrix.

It should highlight:

- overlapping features,
- distinguishing features,
- misleading features,
- and context-dependent features.

---

## 8. Gray Zone Scenario Schema

```yaml
gray_zone_scenarios:
  scenario_id:
    title: string
    problem: list[string]
    pathway_a_leaning_features: list[string]
    pathway_b_leaning_features: list[string]
    missing_pieces: list[string]
    pitfall: optional[string]
```

### Required Minimum

Each gray-zone map should include at least three scenarios.

Examples:

```yaml
required_scenario_types:
  - classic_overlap
  - misleading_feature
  - missing_data_conflict
```

---

## 9. Why Not Engine Schema

```yaml
why_not_engine:
  why_not_primary_pathway: list[string]
  why_not_secondary_pathway: list[string]
  why_not_common_final_label: optional[list[string]]
  why_not_stop_at_pattern_label: optional[list[string]]
```

### Purpose

The Why Not Engine prevents premature closure.

It should challenge:

- the leading pattern,
- the familiar diagnosis,
- the common shortcut,
- and the tendency to stop at a pattern label.

---

## 10. Missing Piece Engine Schema

```yaml
missing_piece_engine:
  default_question: What do we still not know?
  highest_yield_missing_data:
    missing_item_id:
      reason: string
      priority: optional[enum]
      linked_reasoning_section: optional[string]
```

### Priority Labels

```yaml
priority_labels:
  - essential
  - high_yield
  - context_dependent
  - optional
```

### Required Missing Piece Categories

```yaml
required_missing_piece_categories:
  - prior_ct
  - exposure_history
  - autoimmune_screen
  - clinical_context
  - medication_history
  - occupational_history
  - pft_trend
  - mdd_review
```

---

## 11. Temporal Reasoning Schema

```yaml
temporal_reasoning:
  progression:
    clues: list[string]
    caution: optional[list[string]]

  stabilization:
    clues: list[string]
    caution: optional[list[string]]

  partial_improvement:
    clues: list[string]
    caution: optional[list[string]]

  unexpectedly_fast_worsening:
    consider: list[string]
```

### Temporal Safety Rule

A reasoning map must not treat a single HRCT snapshot as proof of progression.

Progression requires:

```yaml
progression_requires:
  - prior_imaging_or_longitudinal_data
  - clinical_context
  - technical_comparability_review
```

---

## 12. Diagnostic Escalation Logic Schema

```yaml
diagnostic_escalation_logic:
  mdd_strongly_recommended_if: list[string]
  specialist_review_high_value_if: optional[map]
  biopsy_discussion_if: optional[list[string]]
  follow_up_ct_reasonable_if: optional[list[string]]
```

### MDD Trigger Rule

Reasoning maps should trigger MDD when:

```yaml
mdd_triggers:
  - competing_patterns_overlap
  - imaging_and_clinical_context_conflict
  - exposure_history_uncertain
  - autoimmune_context_uncertain
  - superimposed_event_suspected
  - biopsy_decision_is_being_considered
  - treatment_response_is_unexpected
```

---

## 13. Pitfall Library Schema

```yaml
pitfall_library:
  - title: string
    correction: string
    severity: optional[enum]
    linked_missing_piece: optional[string]
```

### Severity Labels

```yaml
pitfall_severity:
  - educational
  - important
  - high_risk
```

---

## 14. MVP Test Case Schema

```yaml
mvp_test_case:
  case_id: string
  input:
    age: optional[number]
    sex: optional[string]
    hrct: list[string]
    history: map
    labs: optional[map]
    pft: optional[map]
  output:
    reasoning_state: string_or_list
    pathway_support: map
    cannot_conclude: list[string]
    missing_pieces: list[string]
    final_prompt: list[string]
```

### Test Case Safety Rule

The output must not contain:

```yaml
disallowed_outputs:
  - final_diagnosis
  - confirmed_diagnosis
  - treatment_recommendation
  - probability_of_disease_for_individual_patient
```

Allowed outputs:

```yaml
allowed_outputs:
  - reasoning_state
  - pattern_support
  - competing_pathways
  - cannot_conclude
  - missing_pieces
  - final_prompt
```

---

## 15. Final Page Prompt Schema

```yaml
final_page_prompt:
  title: string
  required_lines:
    - Do not force the label.
    - What do we still not know?
  questions: list[string]
```

### Required Final Questions

Every reasoning map must end with:

```text
Do not force the label.

Ask:
1. What supports the leading pathway?
2. What weakens it?
3. What competing explanation remains possible?
4. What clinical, temporal, laboratory, or exposure data are missing?
5. Is MDD needed?
6. What do we still not know?
```

---

## 16. Conversion Target

This schema is designed so each reasoning map can later be converted into:

```yaml
future_conversion_targets:
  - JSON
  - TypeScript object
  - graph node
  - decision-tree UI component
  - comparison matrix component
  - Missing Piece Engine module
  - case simulation module
```

---

## 17. Minimal TypeScript Shape Preview

```ts
type ReasoningMap = {
  metadata: ReasoningMapMetadata;
  purpose: ReasoningPurpose;
  linkedPatterns: LinkedPattern[];
  coreDistinction: Record<string, CoreDistinction>;
  featuresSupportingEachPathway: Record<string, PathwaySupport>;
  comparisonMatrix: ComparisonMatrixRow[];
  grayZoneScenarios: Record<string, GrayZoneScenario>;
  whyNotEngine: WhyNotEngine;
  missingPieceEngine: MissingPieceEngine;
  temporalReasoning: TemporalReasoning;
  diagnosticEscalationLogic: DiagnosticEscalationLogic;
  pitfallLibrary: Pitfall[];
  mvpTestCase: MvpReasoningTestCase;
  finalPagePrompt: FinalPagePrompt;
};
```

---

## 18. Final Schema Rule

A valid Reasoning Map must answer:

```text
1. What pathways are being compared?
2. What supports each pathway?
3. What weakens each pathway?
4. Where do they overlap?
5. What scenarios create gray-zone uncertainty?
6. What missing data would clarify the case?
7. What temporal behavior matters?
8. What pitfalls should be avoided?
9. When should MDD or specialist review be triggered?
10. What do we still not know?
```