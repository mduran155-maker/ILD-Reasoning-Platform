# Pattern Schema — v1

## Document Metadata

```yaml
id: data_schema_pattern_schema_v1
title: Pattern Schema
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

This schema defines the standard structure for all Pattern Atlas pages in the ILD Reasoning Platform.

It is designed to make pattern datasheets:

- consistent,
- cross-linkable,
- searchable,
- convertible to JSON,
- usable in future UI components,
- compatible with reasoning maps,
- and safe from diagnostic overreach.

This schema does not define diagnostic authority.

It defines educational reasoning structure.

---

## 1. Required Top-Level Fields

```yaml
required_top_level_fields:
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
    - pattern_datasheet
    - gray_zone_reasoning_map
    - triage_reasoning_engine
    - guideline_registry
    - navigation_contract
    - ui_wireframe

  diagnostic_authority:
    - none
```

---

## 3. Identity Schema

```yaml
identity:
  pattern_id: string
  full_name: string
  short_name: string
  category: string
  primary_domain: string
  clinical_role: string
  important_distinction: string
  related_disease_contexts: list[string]
```

### Example

```yaml
identity:
  pattern_id: uip
  full_name: Usual Interstitial Pneumonia Pattern
  short_name: UIP
  category: Fibrotic Interstitial Lung Disease Pattern
  primary_domain: HRCT Pattern Recognition
  clinical_role: Pattern-level reasoning, not disease-level diagnosis
  important_distinction: UIP is a radiologic/pathologic pattern; IPF is a clinical disease diagnosis.
```

---

## 4. Pattern Summary Schema

```yaml
pattern_summary:
  one_sentence_summary: string
  danger_statement: string
  key_teaching_point: string
```

### Required Safety Rule

Every pattern summary must include a warning against converting a pattern directly into a disease diagnosis.

Examples:

```yaml
UIP: UIP pattern does not automatically mean IPF.
NSIP: NSIP pattern should trigger secondary-cause review before calling it idiopathic.
Fibrotic_HP: Fibrotic HP cannot be diagnosed by imaging alone.
```

---

## 5. Imaging Anatomy Schema

```yaml
imaging_anatomy:
  distribution:
    required: true
    fields:
      - zonal_distribution
      - axial_distribution
      - symmetry
      - heterogeneity
      - special_distribution_clues

  core_features:
    required: true
    fields:
      - feature_name
      - role
      - importance
      - comment
      - caution

  caution_features:
    required: true
    fields:
      - feature_name
      - concern
      - warning
```

### Importance Scale

```yaml
importance_scale:
  - low
  - moderate
  - moderate_to_high
  - high
  - very_high
  - context_dependent
```

---

## 6. Confidence Levels Schema

```yaml
confidence_levels:
  required: true
  structure:
    level_name:
      supportive_features: list[string]
      interpretation: string
      caution: optional[string]
```

### Recommended Levels

```yaml
recommended_confidence_levels:
  - typical_pattern
  - probable_pattern
  - indeterminate_or_gray_zone
  - alternative_diagnosis_suggested
```

Pattern-specific names are allowed:

```yaml
UIP:
  - definite_uip_pattern
  - probable_uip_pattern
  - indeterminate_for_uip
  - alternative_diagnosis_suggested

NSIP:
  - typical_nsip_pattern
  - probable_nsip_pattern
  - indeterminate_nsip_or_uip_gray_zone
  - alternative_diagnosis_suggested

Fibrotic_HP:
  - typical_fibrotic_hp_pattern
  - compatible_fibrotic_hp_pattern
  - indeterminate_for_fibrotic_hp
  - alternative_diagnosis_suggested
```

---

## 7. Differential Field Schema

```yaml
differential_field:
  core_questions: list[string]
  differential_contexts:
    disease_or_context_id:
      supports: list[string]
      weakens: list[string]
      missing_data: optional[list[string]]
      reasoning_note: optional[string]
```

### Safety Rule

Differential contexts must not be presented as ranked diagnoses unless a future validated scoring framework exists.

Allowed language:

```text
supports
weakens
raises concern for
requires review
remains possible
```

Disallowed language:

```text
diagnoses
confirms
rules out
final diagnosis
```

---

## 8. Gray Zone Links Schema

```yaml
gray_zone_links:
  - gray_zone_id: string
    title: optional[string]
    core_question: optional[string]
    high_yield_features: optional[list[string]]
```

### Required Rule

Every pattern must link to at least one gray-zone reasoning map.

Examples:

```yaml
UIP:
  - uip_vs_nsip
  - uip_vs_fibrotic_hp

NSIP:
  - uip_vs_nsip
  - nsip_vs_fibrotic_hp

Fibrotic_HP:
  - uip_vs_fibrotic_hp
  - nsip_vs_fibrotic_hp
```

---

## 9. Why Not Engine Schema

```yaml
why_not_engine:
  primary_question: string
  arguments_against_primary_label: list[string]
  arguments_against_common_mimic_labels: optional[map]
  false_assumptions: list[string]
```

### Purpose

The Why Not Engine prevents premature closure.

It should ask:

- Why not the leading label?
- Why not the common mimic?
- Why not the familiar diagnosis?
- What assumption could be wrong?

---

## 10. Missing Piece Candidates Schema

```yaml
missing_piece_candidates:
  default_question: What do we still not know?
  high_yield_missing_data:
    missing_item_id:
      reason: string
      examples: optional[list[string]]
      caution: optional[string]
      when_high_value: optional[list[string]]
```

### Required Missing Piece Categories

```yaml
required_missing_piece_categories:
  - prior_ct
  - exposure_history
  - autoimmune_screen
  - medication_history
  - occupational_history
  - expiratory_hrct
  - pft_trend
  - mdd_review
```

Pattern-specific optional categories:

```yaml
optional_missing_piece_categories:
  - bal_lymphocytosis
  - biopsy_discussion
  - rheumatology_review
  - exposure_specialist_review
  - pathology_review
```

---

## 11. Temporal Behavior Schema

```yaml
temporal_behavior:
  progression:
    supportive_changes: list[string]
    interpretation: optional[list[string]]
    caution: optional[list[string]]

  stabilization:
    supportive_changes: list[string]
    interpretation: optional[list[string]]
    caution: optional[list[string]]

  regression_or_partial_improvement:
    supportive_changes: list[string]
    interpretation: optional[list[string]]
    caution: list[string]

  unexpectedly_fast_worsening:
    consider: list[string]
```

### Temporal Safety Rule

The platform must not call change “progression” unless prior imaging or longitudinal clinical data are part of the reasoning context.

---

## 12. Pattern Interaction Schema

```yaml
pattern_interactions:
  interaction_id:
    consider: list[string]
    questions: list[string]
    warning: optional[string]
```

### Required Interaction Types for Fibrotic ILD MVP

```yaml
required_interactions:
  - fibrosis_plus_ground_glass
  - fibrosis_plus_air_trapping
  - fibrosis_plus_nodules
  - fibrosis_plus_consolidation
  - fibrosis_plus_cysts
  - fibrosis_plus_emphysema
```

---

## 13. Superimposed Events Schema

```yaml
superimposed_events:
  event_id:
    consider: list[string]
    warning: string
    missing_data: optional[list[string]]
```

### MVP Required Events

```yaml
required_superimposed_events:
  - new_ground_glass_on_fibrotic_background
  - new_consolidation
  - new_nodule_or_mass
  - rapid_diffuse_worsening
```

### Safety Rule

New findings on fibrotic ILD must not automatically be interpreted as baseline ILD progression.

---

## 14. Diagnostic Escalation Schema

```yaml
diagnostic_escalation:
  mdd_needed_if: list[string]
  specialist_review_high_value_if: optional[map]
  bal_may_help_if: optional[list[string]]
  biopsy_discussion_if: optional[list[string]]
  follow_up_ct_reasonable_if: optional[list[string]]
```

### Safety Rule

Biopsy discussion must always include:

```yaml
biopsy_required_conditions:
  - diagnosis_remains_uncertain
  - result_would_change_management
  - patient_risk_is_acceptable
  - MDD_supports_need
```

---

## 15. Pitfall Library Schema

```yaml
pitfall_library:
  - title: string
    correction: string
    linked_module: optional[string]
    severity: optional[enum]
```

### Severity Labels

```yaml
pitfall_severity:
  - educational
  - important
  - high_risk
```

---

## 16. Evidence and Guideline Registry Schema

```yaml
evidence_and_guideline_registry:
  primary_guidelines_to_link: list[string]
  secondary_guidelines_to_link: optional[list[string]]
  evidence_notes: list[string]
  consensus_strength:
    topic_id: enum
```

### Consensus Strength Labels

```yaml
consensus_strength_labels:
  - high
  - moderate
  - low
  - context_dependent
  - high_complexity
  - full_source_review_required
```

---

## 17. Narrative Questions Schema

```yaml
narrative_questions:
  required: true
  questions: list[string]
```

### Required Final Question

Every pattern page must include:

```text
What is the single most important missing piece of information?
```

or:

```text
What do we still not know?
```

---

## 18. MVP Screen Behavior Schema

```yaml
mvp_screen_behavior:
  main_panel: list[string]
  right_sidebar: list[string]
  bottom_panel: list[string]
```

### Required Sidebar Sections

```yaml
required_sidebar_sections:
  - why_not_engine
  - missing_piece_candidates
  - gray_zone_links
  - pitfall_library
  - superimposed_event_alerts
  - guideline_registry
```

---

## 19. MVP Test Case Schema

```yaml
mvp_test_case:
  case_id: string
  input:
    age: optional[number]
    sex: optional[string]
    hrct: list[string]
    history: map
    laboratory: optional[map]
    pft: optional[map]
  system_output:
    pattern_confidence: string
    disease_statement: string
    why_not: optional[map]
    missing_pieces: list[string]
    final_prompt: list[string]
```

### Test Case Safety Rule

The test case output must not produce a final diagnosis.

Allowed:

```text
pattern_confidence
reasoning_state
possible_context
missing_pieces
cannot_conclude
```

Disallowed:

```text
final_diagnosis
confirmed_diagnosis
treatment_recommendation
```

---

## 20. Conversion Target

This schema is designed so each pattern page can later be converted into:

```yaml
future_conversion_targets:
  - JSON
  - TypeScript object
  - database row
  - React component props
  - searchable knowledge graph node
```

---

## 21. Minimal TypeScript Shape Preview

```ts
type PatternDatasheet = {
  metadata: PatternMetadata;
  identity: PatternIdentity;
  patternSummary: PatternSummary;
  imagingAnatomy: ImagingAnatomy;
  confidenceLevels: Record<string, ConfidenceLevel>;
  differentialField: DifferentialField;
  grayZoneLinks: GrayZoneLink[];
  whyNotEngine: WhyNotEngine;
  missingPieceCandidates: MissingPieceEngine;
  temporalBehavior: TemporalBehavior;
  patternInteractions: Record<string, PatternInteraction>;
  superimposedEvents: Record<string, SuperimposedEvent>;
  diagnosticEscalation: DiagnosticEscalation;
  pitfallLibrary: Pitfall[];
  evidenceAndGuidelineRegistry: EvidenceRegistry;
  narrativeQuestions: string[];
  mvpScreenBehavior: MvpScreenBehavior;
  mvpTestCase: MvpTestCase;
};
```

---

## 22. Final Schema Rule

A valid Pattern Datasheet must answer:

```text
1. What pattern is being described?
2. What supports it?
3. What weakens it?
4. What mimics it?
5. What gray zones does it connect to?
6. What information is missing?
7. What temporal behavior matters?
8. What superimposed events can distort interpretation?
9. What pitfalls should be avoided?
10. What guideline evidence is linked?
11. What do we still not know?
```