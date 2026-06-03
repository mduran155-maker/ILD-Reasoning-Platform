# MVP Crosslink Registry — v1

## Document Metadata

```yaml
id: navigation_mvp_crosslink_registry_v1
title: MVP Crosslink Registry
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: navigation_and_crosslink_contract
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This registry defines how MVP pages should link to each other.

The platform must not behave like isolated articles.

Every page should act as a reasoning node connected to:

- related patterns,
- gray-zone maps,
- missing-piece prompts,
- pitfall warnings,
- temporal reasoning,
- superimposed events,
- and guideline evidence.

---

## 1. Core MVP Pages

```yaml
core_mvp_pages:
  project_blueprint:
    path: docs/project_blueprint_v1.md
    role: platform_mission_and_architecture

  uip_pattern:
    path: docs/patterns/uip_pattern_gold_standard_v1.md
    role: pattern_datasheet

  nsip_pattern:
    path: docs/patterns/nsip_pattern_gold_standard_v1.md
    role: pattern_datasheet

  fibrotic_hp_pattern:
    path: docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
    role: pattern_datasheet

  uip_vs_nsip:
    path: docs/reasoning/uip_vs_nsip_gray_zone_v1.md
    role: gray_zone_reasoning_map

  uip_vs_fibrotic_hp:
    path: docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md
    role: gray_zone_reasoning_map

  nsip_vs_fibrotic_hp:
    path: docs/reasoning/nsip_vs_fibrotic_hp_gray_zone_v1.md
    role: gray_zone_reasoning_map

  fibrotic_ild_triage:
    path: docs/reasoning/fibrotic_ild_triage_map_v1.md
    role: central_reasoning_engine
```

---

## 2. Pattern Page Sidebar Contract

Every pattern datasheet should include a right-sidebar concept.

```yaml
pattern_sidebar_contract:
  required_sidebar_sections:
    - why_not_engine
    - missing_piece_candidates
    - gray_zone_links
    - pitfall_library
    - temporal_prompt
    - superimposed_event_alerts
    - guideline_registry

  final_question:
    - What do we still not know?
```

---

## 3. UIP Page Crosslinks

```yaml
uip_pattern_crosslinks:
  primary_gray_zones:
    - uip_vs_nsip_gray_zone_v1
    - uip_vs_fibrotic_hp_gray_zone_v1

  triage_engine:
    - fibrotic_ild_triage_map_v1

  sidebar_alerts:
    why_not:
      - Why not IPF?
      - Why not CTD-UIP?
      - Why not fibrotic HP?
      - Why not asbestosis?

    missing_pieces:
      - prior_CT
      - exposure_history
      - autoimmune_screen
      - expiratory_HRCT
      - MDD_review

    red_flags:
      - new_ground_glass
      - new_nodule_or_mass
      - new_consolidation
      - unexpectedly_fast_worsening
```

---

## 4. NSIP Page Crosslinks

```yaml
nsip_pattern_crosslinks:
  primary_gray_zones:
    - uip_vs_nsip_gray_zone_v1
    - nsip_vs_fibrotic_hp_gray_zone_v1

  triage_engine:
    - fibrotic_ild_triage_map_v1

  sidebar_alerts:
    why_not:
      - Why not idiopathic NSIP?
      - Why not CTD-ILD?
      - Why not fibrotic HP?
      - Why not drug-related ILD?

    missing_pieces:
      - autoimmune_screen
      - clinical_CTD_review
      - medication_history
      - prior_CT
      - expiratory_HRCT
      - MDD_review

    red_flags:
      - rapid_worsening
      - dominant_consolidation
      - new_nodule_or_mass
      - marked_air_trapping
```

---

## 5. Fibrotic HP Page Crosslinks

```yaml
fibrotic_hp_pattern_crosslinks:
  primary_gray_zones:
    - uip_vs_fibrotic_hp_gray_zone_v1
    - nsip_vs_fibrotic_hp_gray_zone_v1

  triage_engine:
    - fibrotic_ild_triage_map_v1

  sidebar_alerts:
    why_not:
      - Why not IPF?
      - Why not NSIP?
      - Why not CTD-ILD?
      - Why not occupational ILD?

    missing_pieces:
      - detailed_exposure_history
      - expiratory_HRCT
      - prior_CT
      - BAL_lymphocytosis
      - autoimmune_screen
      - MDD_review

    red_flags:
      - new_consolidation
      - new_nodule_or_mass
      - rapid_diffuse_worsening
      - ongoing_or_recurrent_exposure
```

---

## 6. Central Triage Entry Logic

```yaml
mvp_entry_logic:
  if_user_starts_with_fibrosis:
    route_to:
      - fibrotic_ild_triage_map_v1

  if_user_starts_with_uip:
    route_to:
      - uip_pattern_gold_standard_v1
      - uip_vs_nsip_gray_zone_v1
      - uip_vs_fibrotic_hp_gray_zone_v1

  if_user_starts_with_nsip:
    route_to:
      - nsip_pattern_gold_standard_v1
      - uip_vs_nsip_gray_zone_v1
      - nsip_vs_fibrotic_hp_gray_zone_v1

  if_user_starts_with_air_trapping_and_fibrosis:
    route_to:
      - fibrotic_hp_pattern_gold_standard_v1
      - uip_vs_fibrotic_hp_gray_zone_v1
      - nsip_vs_fibrotic_hp_gray_zone_v1

  if_user_starts_with_uncertain_fibrotic_ild:
    route_to:
      - fibrotic_ild_triage_map_v1
```

---

## 7. Required Final Prompt on All MVP Pages

Every MVP page must end with:

```text
What do we still not know?
```

Expanded form:

```text
Do not force the label.

Ask:
1. What is the dominant pattern?
2. What findings support it?
3. What findings weaken it?
4. What mimics remain possible?
5. What does the prior CT show?
6. What clinical/laboratory/exposure data are missing?
7. Is MDD needed?
8. What do we still not know?
```

---

## 8. Safety Boundary

```yaml
safety_boundary:
  platform_must_not:
    - diagnose_individual_patients
    - recommend_treatment
    - replace_clinician_judgment
    - present_pattern_as_final_disease
    - imply_guideline_compliance_without_source_review

  platform_must:
    - preserve_uncertainty
    - show_reasoning
    - expose_missing_data
    - link_gray_zones
    - show_pitfalls
    - encourage_MDD_when_needed
```