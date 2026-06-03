# ILD Reasoning Platform

## Purpose

The ILD Reasoning Platform is a structured educational platform for interstitial lung disease reasoning.

It is designed to help clinicians, radiologists, pulmonologists, rheumatologists, residents, and fellows reason through:

- HRCT patterns
- fibrotic ILD gray zones
- missing diagnostic information
- temporal change
- superimposed events
- guideline-linked uncertainty
- multidisciplinary discussion triggers

## Core Principle

Diagnosing ILD is not about finding the right answer.  
It is about asking the right next question — and knowing when you don’t have enough information yet.

## Safety Boundary

This platform does **not**:

- diagnose individual patients
- classify individual cases
- recommend treatment
- replace clinical judgment
- replace multidisciplinary discussion
- replace full guideline review

This platform does:

- support structured clinical reasoning
- expose diagnostic uncertainty
- show competing explanations
- identify missing high-yield information
- connect patterns to gray-zone maps
- link reasoning to guideline-backed evidence

## MVP Scope

The first MVP focuses on fibrotic ILD reasoning.

Initial pattern atlas:

- UIP Pattern
- NSIP Pattern
- Fibrotic Hypersensitivity Pneumonitis Pattern

Initial reasoning maps:

- UIP vs NSIP
- UIP vs Fibrotic HP
- NSIP vs Fibrotic HP
- Fibrotic ILD Triage Map

Initial platform infrastructure:

- Project Blueprint
- Crosslink Registry
- Guideline Registry
- MVP Entry Flow

## Project Structure

```text
docs/
  project_blueprint_v1.md

  patterns/
    uip_pattern_gold_standard_v1.md
    nsip_pattern_gold_standard_v1.md
    fibrotic_hp_pattern_gold_standard_v1.md

  reasoning/
    uip_vs_nsip_gray_zone_v1.md
    uip_vs_fibrotic_hp_gray_zone_v1.md
    nsip_vs_fibrotic_hp_gray_zone_v1.md
    fibrotic_ild_triage_map_v1.md

  navigation/
    mvp_crosslink_registry_v1.md
    mvp_entry_flow_v1.md

  evidence/
    guideline_registry_v1.md
```

## MVP User Flow

The first usable version should allow the user to:

1. Start from a fibrotic ILD pattern.
2. Review UIP, NSIP, and Fibrotic HP reasoning.
3. Explore gray zones.
4. Ask “Why not?”
5. Identify missing high-yield information.
6. Review red flags and superimposed event warnings.
7. Link to guideline-backed evidence.
8. Preserve uncertainty when data are incomplete.

## Editorial Rule

Every content page should end with:

```text
What do we still not know?
```

Expanded form:

```text
Do not force the label.

Ask:
1. What pattern is most supported?
2. What pattern is still competing?
3. What finding weakens the leading label?
4. What clinical, exposure, laboratory, or temporal data are missing?
5. Is there a red flag or superimposed event?
6. Is multidisciplinary discussion needed?
7. What do we still not know?
```

## Current Status

Status: blueprint phase  
Code status: not started  
Diagnostic authority: none  
Clinical use: educational reasoning support only  