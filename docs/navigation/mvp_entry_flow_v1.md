# MVP Entry Flow — v1

## Document Metadata

```yaml
id: navigation_mvp_entry_flow_v1
title: MVP Entry Flow
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: user_entry_flow
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This document defines the first user-facing entry flow for the ILD Reasoning Platform MVP.

The platform should not begin by asking:

```text
What is the diagnosis?
```

It should begin by asking:

```text
What are you trying to understand?
```

The goal is to guide users toward structured reasoning, not premature labeling.

---

## 1. Homepage Core Message

```yaml
homepage_message:
  primary_statement: >
    The ILD Reasoning Platform helps clinicians reason through interstitial lung disease patterns,
    gray zones, missing data, and guideline-linked uncertainty.

  safety_statement: >
    This platform does not diagnose patients or recommend treatment.
    It supports educational reasoning and guideline navigation.

  core_principle: >
    Diagnosing ILD is not about finding the right answer.
    It is about asking the right next question — and knowing when you don’t have enough information yet.
```

---

## 2. Three Main Entry Doors

```yaml
entry_doors:
  start_with_pattern:
    label: Start with a Pattern
    user_question: What do you see on HRCT?
    examples:
      - UIP-like fibrosis
      - NSIP-like pattern
      - Fibrosis with air trapping
      - Fibrosis with nodules
      - Fibrosis with emphysema
      - New ground-glass opacity on fibrotic background
    primary_route:
      - fibrotic_ild_triage_map_v1

  start_with_clinical_problem:
    label: Start with a Clinical Problem
    user_question: What is the clinical dilemma?
    examples:
      - Is this IPF or fibrotic HP?
      - Is this NSIP or fibrotic HP?
      - Is biopsy needed?
      - Is this progression or superimposed disease?
      - Why is the patient worsening quickly?
      - What information is missing?
    primary_route:
      - fibrotic_ild_triage_map_v1
      - relevant_gray_zone_map

  start_with_disease_context:
    label: Start with a Disease Context
    user_question: Which disease or diagnostic context are you reviewing?
    examples:
      - IPF
      - CTD-ILD
      - Fibrotic HP
      - Sarcoidosis
      - Occupational ILD
      - Drug-related ILD
    primary_route:
      - disease_or_pattern_datasheet_when_available
      - guideline_registry_v1
```

---

## 3. MVP Entry Button Layout

```yaml
mvp_entry_buttons:
  primary_buttons:
    - label: Fibrotic ILD Triage
      route: docs/reasoning/fibrotic_ild_triage_map_v1.md
      description: Start here when the HRCT shows fibrosis but the pattern is uncertain.

    - label: UIP Pattern
      route: docs/patterns/uip_pattern_gold_standard_v1.md
      description: Review UIP anatomy, mimics, missing data, and why UIP does not automatically mean IPF.

    - label: NSIP Pattern
      route: docs/patterns/nsip_pattern_gold_standard_v1.md
      description: Review NSIP anatomy, CTD context, treatment-response reasoning, and gray zones.

    - label: Fibrotic HP Pattern
      route: docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
      description: Review airway-centered clues, exposure reasoning, air trapping, and HP mimics.

  secondary_buttons:
    - label: UIP vs NSIP
      route: docs/reasoning/uip_vs_nsip_gray_zone_v1.md

    - label: UIP vs Fibrotic HP
      route: docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md

    - label: NSIP vs Fibrotic HP
      route: docs/reasoning/nsip_vs_fibrotic_hp_gray_zone_v1.md

    - label: Guideline Registry
      route: docs/evidence/guideline_registry_v1.md
```

---

## 4. First User Flow: Pattern-first

```yaml
flow_pattern_first:
  user_input:
    - I see fibrotic ILD on HRCT.

  platform_response:
    - route_to_fibrotic_ild_triage_map
    - ask_distribution
    - ask_dominant_features
    - ask_air_trapping
    - ask_ground_glass
    - ask_honeycombing
    - ask_prior_ct
    - ask_exposure_history
    - ask_autoimmune_context

  output:
    - possible_pattern_support
    - competing_gray_zones
    - missing_piece_candidates
    - red_flags
    - guideline_links
    - final_uncertainty_prompt
```

---

## 5. Second User Flow: Gray-zone-first

```yaml
flow_gray_zone_first:
  user_input:
    - I am unsure whether this is UIP, NSIP, or fibrotic HP.

  platform_response:
    - route_to_fibrotic_ild_triage_map
    - show_three_way_comparison
    - link_to_uip_vs_nsip
    - link_to_uip_vs_fibrotic_hp
    - link_to_nsip_vs_fibrotic_hp

  output:
    - what_supports_each_pattern
    - what_weakens_each_pattern
    - what_data_are_missing
    - when_MDD_is_needed
```

---

## 6. Third User Flow: Missing-data-first

```yaml
flow_missing_data_first:
  user_input:
    - I cannot confidently classify this fibrotic ILD.

  platform_response:
    - ask_what_is_missing
    - prioritize_high_yield_missing_data

  highest_yield_missing_data:
    - prior_CT
    - expiratory_HRCT
    - detailed_exposure_history
    - autoimmune_screen
    - clinical_CTD_review
    - medication_history
    - occupational_history
    - PFT_trend
    - BAL_lymphocytosis_if_HP_suspected
    - MDD_review

  output:
    - missing_piece_ranked_list
    - why_each_missing_piece_matters
    - relevant_gray_zone_links
```

---

## 7. Fourth User Flow: Superimposed-event-first

```yaml
flow_superimposed_event_first:
  user_input:
    - This ILD patient has new or rapid worsening.

  trigger_findings:
    - new_ground_glass
    - new_consolidation
    - new_nodule_or_mass
    - rapid_diffuse_worsening
    - unexpected_clinical_decline

  platform_response:
    - do_not_call_simple_progression
    - open_red_flag_panel
    - consider_superimposed_event_differentials

  consider:
    - infection
    - acute_exacerbation
    - pulmonary_edema
    - pulmonary_embolism
    - drug_toxicity
    - aspiration
    - malignancy
    - exposure_rechallenge

  output:
    - superimposed_event_alert
    - missing_data_needed_for_triage
    - MDD_or_urgent_clinical_review_prompt
```

---

## 8. Homepage Safety Panel

```yaml
homepage_safety_panel:
  title: This platform supports reasoning, not diagnosis.

  must_show:
    - Patterns are not final diagnoses.
    - Guideline summaries are not full guideline replacements.
    - Treatment decisions require clinician judgment.
    - Uncertainty should be preserved when data are incomplete.
    - MDD may be needed in gray-zone cases.

  final_line:
    - What do we still not know?
```

---

## 9. MVP Homepage Wireframe

```yaml
homepage_wireframe:
  header:
    - ILD Reasoning Platform
    - Pattern Atlas + Gray Zone Maps + Missing Piece Engine

  hero_section:
    - core_principle
    - safety_statement

  main_entry_section:
    - Start with a Pattern
    - Start with a Clinical Problem
    - Start with a Disease Context

  quick_access_section:
    - Fibrotic ILD Triage
    - UIP Pattern
    - NSIP Pattern
    - Fibrotic HP Pattern

  gray_zone_section:
    - UIP vs NSIP
    - UIP vs Fibrotic HP
    - NSIP vs Fibrotic HP

  evidence_section:
    - Guideline Registry
    - Evidence Confidence Labels

  footer_prompt:
    - What do we still not know?
```

---

## 10. Final Entry Rule

Every user pathway should end with:

```text
Do not force the label.

Ask:
1. What pattern is most supported?
2. What pattern is still competing?
3. What finding weakens the leading label?
4. What clinical, exposure, lab, or temporal data are missing?
5. Is there a red flag or superimposed event?
6. Is MDD needed?
7. What do we still not know?
```