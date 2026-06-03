# MVP Home Wireframe — v1

## Document Metadata

```yaml
id: navigation_mvp_home_wireframe_v1
title: MVP Home Wireframe
version: v1
language: English
status: blueprint_draft
project: ILD Reasoning Platform
content_type: ui_wireframe
diagnostic_authority: none
last_updated: draft
```

---

## 0. Purpose

This document defines the first homepage wireframe for the ILD Reasoning Platform MVP.

The homepage must communicate three things immediately:

1. This is a reasoning platform, not a diagnostic calculator.
2. The user can start from a pattern, a clinical problem, or a disease context.
3. Every pathway preserves uncertainty and asks what information is still missing.

---

## 1. Homepage Header

```yaml
header:
  product_name: ILD Reasoning Platform
  subtitle: Pattern Atlas + Gray Zone Maps + Missing Piece Engine
  primary_navigation:
    - Patterns
    - Reasoning Maps
    - Triage Engine
    - Guidelines
    - About
```

---

## 2. Hero Section

```yaml
hero_section:
  headline: Reason through ILD patterns without forcing premature certainty.

  subheadline: >
    A structured educational platform for fibrotic ILD pattern recognition,
    gray-zone reasoning, missing data identification, temporal comparison,
    and guideline-linked uncertainty.

  safety_line: >
    This platform supports reasoning, not diagnosis. It does not classify individual patients
    or recommend treatment.

  core_principle: >
    Diagnosing ILD is not about finding the right answer.
    It is about asking the right next question — and knowing when you don’t have enough information yet.
```

### Hero CTA Buttons

```yaml
hero_cta_buttons:
  primary:
    label: Start Fibrotic ILD Triage
    route: docs/reasoning/fibrotic_ild_triage_map_v1.md

  secondary:
    label: Explore Pattern Atlas
    route: docs/patterns/

  tertiary:
    label: Review Guideline Registry
    route: docs/evidence/guideline_registry_v1.md
```

---

## 3. Three Entry Doors

```yaml
entry_doors:
  start_with_pattern:
    title: Start with a Pattern
    prompt: What do you see on HRCT?
    examples:
      - UIP-like fibrosis
      - NSIP-like pattern
      - Fibrosis with air trapping
      - Fibrosis with nodules
      - Fibrosis with new ground-glass opacity
    route: fibrotic_ild_triage_map_v1

  start_with_problem:
    title: Start with a Clinical Problem
    prompt: What is the dilemma?
    examples:
      - Is this IPF or fibrotic HP?
      - Is this NSIP or fibrotic HP?
      - Is this progression or a superimposed event?
      - What information is missing?
      - Is MDD needed?
    route: relevant_reasoning_map

  start_with_context:
    title: Start with a Disease Context
    prompt: Which disease context are you reviewing?
    examples:
      - IPF
      - CTD-ILD
      - Fibrotic HP
      - Sarcoidosis
      - Drug-related ILD
      - Occupational ILD
    route: disease_or_pattern_page_when_available
```

---

## 4. Quick Access Cards

```yaml
quick_access_cards:
  fibrotic_ild_triage:
    title: Fibrotic ILD Triage
    description: Start here when fibrosis is present but the dominant pattern is uncertain.
    route: docs/reasoning/fibrotic_ild_triage_map_v1.md
    badge: Reasoning Engine

  uip_pattern:
    title: UIP Pattern
    description: Review UIP anatomy, mimics, missing data, and why UIP does not automatically mean IPF.
    route: docs/patterns/uip_pattern_gold_standard_v1.md
    badge: Pattern Atlas

  nsip_pattern:
    title: NSIP Pattern
    description: Review NSIP anatomy, CTD context, treatment-response reasoning, and gray zones.
    route: docs/patterns/nsip_pattern_gold_standard_v1.md
    badge: Pattern Atlas

  fibrotic_hp_pattern:
    title: Fibrotic HP Pattern
    description: Review airway-centered clues, exposure reasoning, air trapping, and HP mimics.
    route: docs/patterns/fibrotic_hp_pattern_gold_standard_v1.md
    badge: Pattern Atlas
```

---

## 5. Gray Zone Section

```yaml
gray_zone_section:
  title: Gray Zone Reasoning Maps
  description: Compare overlapping patterns without forcing premature labels.

  cards:
    uip_vs_nsip:
      title: UIP vs NSIP
      key_question: Is the fibrosis heterogeneous or homogeneous?
      route: docs/reasoning/uip_vs_nsip_gray_zone_v1.md

    uip_vs_fibrotic_hp:
      title: UIP vs Fibrotic HP
      key_question: Is there airway-centered or exposure-related evidence?
      route: docs/reasoning/uip_vs_fibrotic_hp_gray_zone_v1.md

    nsip_vs_fibrotic_hp:
      title: NSIP vs Fibrotic HP
      key_question: Is this homogeneous CTD-like disease or exposure-related airway-centered fibrosis?
      route: docs/reasoning/nsip_vs_fibrotic_hp_gray_zone_v1.md
```

---

## 6. Missing Piece Panel

```yaml
missing_piece_panel:
  title: Missing Piece Engine
  description: The platform helps identify what information is still missing before a label is forced.

  common_missing_pieces:
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

  primary_question: What do we still not know?
```

---

## 7. Red Flag Panel

```yaml
red_flag_panel:
  title: Red Flags in Fibrotic ILD
  description: Do not call every new finding progression.

  red_flags:
    new_ground_glass:
      label: New ground-glass opacity
      consider:
        - infection
        - acute_exacerbation
        - edema
        - drug_toxicity
        - hemorrhage
        - aspiration

    new_consolidation:
      label: New or persistent consolidation
      consider:
        - organizing_pneumonia
        - infection
        - malignancy
        - drug_toxicity

    new_nodule_or_mass:
      label: New nodule or mass
      consider:
        - malignancy
        - infection
        - inflammatory_nodule

    rapid_worsening:
      label: Rapid diffuse worsening
      consider:
        - infection
        - acute_exacerbation
        - pulmonary_embolism
        - edema
        - treatment_related_lung_injury
```

---

## 8. Evidence Section

```yaml
evidence_section:
  title: Guideline-linked Reasoning
  description: Reasoning modules should be linked to guideline scope, not vague authority.

  primary_registry:
    title: Guideline Registry
    route: docs/evidence/guideline_registry_v1.md

  evidence_badges:
    - Guideline-backed
    - Consensus-supported
    - Context-dependent
    - Gray zone
    - Educational reasoning
    - Full source review required
```

---

## 9. Homepage Layout Sketch

```text
 ------------------------------------------------------------
| ILD Reasoning Platform                                      |
| Pattern Atlas | Reasoning Maps | Triage Engine | Guidelines |
 ------------------------------------------------------------

 HERO:
 Reason through ILD patterns without forcing premature certainty.
 [Start Fibrotic ILD Triage] [Explore Pattern Atlas] [Guidelines]

 SAFETY:
 This platform supports reasoning, not diagnosis.

 THREE ENTRY DOORS:
 [Start with a Pattern] [Start with a Clinical Problem] [Start with a Disease Context]

 QUICK ACCESS:
 [Fibrotic ILD Triage]
 [UIP Pattern]
 [NSIP Pattern]
 [Fibrotic HP Pattern]

 GRAY ZONE MAPS:
 [UIP vs NSIP]
 [UIP vs Fibrotic HP]
 [NSIP vs Fibrotic HP]

 MISSING PIECE ENGINE:
 Prior CT | Expiratory HRCT | Exposure | Autoimmune screen | PFT trend | MDD

 RED FLAGS:
 New GGO | New consolidation | New nodule/mass | Rapid worsening

 EVIDENCE:
 Guideline Registry | Evidence Badges

 FOOTER:
 What do we still not know?
```

---

## 10. UI Safety Rules

```yaml
ui_safety_rules:
  must_show_on_homepage:
    - This platform supports reasoning, not diagnosis.
    - Patterns are not final diagnoses.
    - Guideline summaries do not replace full guideline review.
    - MDD may be needed in gray-zone cases.
    - What do we still not know?

  must_not_show:
    - Diagnose now
    - Calculate diagnosis
    - Recommended treatment
    - Final diagnosis
    - Certainty score for individual patient
```

---

## 11. Final Homepage Prompt

The homepage should end with:

```text
Do not force the label.

Start with what you see.
Ask what else it could be.
Identify what is missing.
Preserve uncertainty when the data are incomplete.

What do we still not know?
```