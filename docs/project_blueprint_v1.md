# ILD Reasoning Platform — Project Blueprint v1

## Mission

The ILD Reasoning Platform is designed to support structured clinical reasoning in interstitial lung disease.

It does not diagnose patients, classify individual cases, or recommend treatment.

It helps clinicians, radiologists, pulmonologists, rheumatologists, residents, and fellows understand:

- how ILD patterns are recognized,
- which differential diagnoses remain possible,
- which findings weaken a working diagnosis,
- what information is missing,
- when uncertainty should be preserved,
- and when multidisciplinary discussion may be needed.

## Core Principle

Diagnosing ILD is not about finding the right answer.  
It is about asking the right next question — and knowing when you don’t have enough information yet.

## Platform Architecture

### 1. Atlas Core

Core reference layer.

Includes:

- Pattern Atlas
- Disease Atlas
- Rare Disease Vault
- Guideline Library

### 2. Reasoning Core

Clinical reasoning layer.

Includes:

- Diagnostic Reasoning Maps
- Pattern Interaction Atlas
- Temporal Comparison Atlas
- Evolution Atlas
- Superimposed Event Atlas

### 3. Decision Core

Escalation and follow-up layer.

Includes:

- Missing Piece Engine
- Biopsy Decision Engine
- Treatment Response Atlas
- Serology and Biomarker Matrix
- Active Surveillance Logic

### 4. Safety Core

Uncertainty and error-prevention layer.

Includes:

- Gray Zone Atlas
- Why Not Engine
- Pitfall Library
- Red Flag Panel
- Uncertainty Atlas
- Cognitive Bias Atlas

### 5. MDD Core

Multidisciplinary education layer.

Includes:

- Case-based MDD simulations
- Radiology perspective
- Pulmonology perspective
- Rheumatology perspective
- Pathology perspective
- Final reasoning summary

## MVP User Flow

The first usable version should allow the user to:

1. Select a pattern.
2. Review the pattern anatomy.
3. See relevant pattern interactions.
4. Explore gray zones.
5. Ask “Why not?”
6. Identify missing high-yield information.
7. Link to guideline-backed evidence.

## First Pattern Datasheet

The first pattern datasheet is:

```text
docs/patterns/uip_pattern_gold_standard_v1.md
```
UIP is the first operating-system test for the platform because it connects:

pattern recognition,
disease context,
gray zones,
temporal reasoning,
superimposed events,
missing information,
biopsy/MDD escalation,
and guideline-based interpretation.
Editorial Rule

Every content page should end with:

What do we still not know?
Safety Rule

The platform must never present itself as a diagnostic authority.

It must remain an educational, reasoning-support, and guideline-navigation platform.


