# ILD Reasoning Platform — Demo Illustration / Visual Artifact Safety Contract v1

Version: v0.14.6  
Status: demo_illustration_visual_artifact_safety_contract  
Scope: Visual safety rules for demo illustrations, reasoning-flow diagrams, state maps, red-team graphics, safe-vs-unsafe comparison cards, UI mock visuals, and synthetic explanatory artifacts  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the safety contract for visual artifacts used in v0.14 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract.

It follows:

- `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md`
- `docs/data/schema/synthetic_demo_case_object_schema_v1.md`
- `docs/data/schema/demo_reasoning_session_snapshot_export_fixture_schema_v1.md`
- `docs/data/schema/demo_scenario_set_missing_evidence_mimic_overlap_source_status_v1.md`
- `docs/data/schema/demo_red_team_scenario_set_unsafe_export_language_authority_drift_v1.md`
- `docs/navigation/demo_case_pack_validation_checklist_synthetic_scenario_safety_gate_v1.md`

This document does not add new clinical content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not clinically validate the platform.  
It does not create disease-teaching atlas authority.

Its purpose is to define how visual artifacts may support platform understanding without becoming diagnostic images, disease atlases, treatment pathways, patient education materials, or authority-bearing outputs.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.6:

> “A visual artifact is valid only if it explains reasoning state, safety boundaries, or fail-closed behavior without acting as diagnostic proof, disease confirmation, probability display, treatment pathway, patient-facing explanation, or public-ready clinical illustration.”

---

## 2. Why This Contract Exists

The platform should not rely on text only.

A purely text-based or button-only interface may become cognitively dry, repetitive, and hard to navigate.

At the same time, the platform should not become visually overconfident.

A purely visual interface may:

- over-simplify clinical ambiguity,
- imply diagnostic certainty,
- suggest probability where none exists,
- turn icons/colors into hidden authority,
- make diagrams look like proof,
- make synthetic examples look like clinical truth,
- make demo artifacts look patient-ready.

Therefore, the visual layer must be:

> visually guided, text-governed.

Visual role:

- improve navigation,
- improve cognitive flow,
- improve state visibility,
- improve structure comprehension,
- improve guardrail comprehension.

Visuals must not become:

- diagnosis surfaces,
- probability surfaces,
- triage surfaces,
- treatment recommendation surfaces,
- patient explanation surfaces,
- clinical proof surfaces.

---

## 3. Global Visual Authority Constraints

All visual artifacts must preserve:

| Constraint | Required State |
|---|---|
| synthetic_only | true |
| real_patient_data | false |
| clinical_validation_use | false |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| patient_facing_use | not_allowed |
| clinically_reviewed.platform_wide | false |
| probability_display | not_allowed |
| diagnostic_confirmation_display | not_allowed |
| disease_atlas_authority | not_allowed |
| treatment_pathway_authority | not_allowed |
| triage_authority | not_allowed |

No illustration, icon, chart, diagram, badge, flow, map, mockup, comparison panel, or export preview may override these constraints.

---

## 4. Core Visual Philosophy

The interface should be:

> visually guided but text-governed.

This means:

- visuals help the user understand structure,
- visuals help the user understand state,
- visuals help the user understand blocked outputs,
- visuals help the user understand review visibility,
- visuals help the user understand synthetic demo behavior,

but:

- text carries the actual limitation,
- text carries the authority boundary,
- text carries the missingness,
- text carries the non-diagnostic rule,
- text carries the no-decision rule,
- text carries the review-only rule.

Visual rule:

> Visuals support interpretation of governance state; text preserves epistemic discipline.

---

## 5. Allowed Visual Artifact Classes

The following visual classes are allowed.

| Visual Class | Allowed Use |
|---|---|
| reasoning_flow_illustration | show state progression |
| reasoning_map | show relation among prompts, missing evidence, mimic visibility, overlap, review prompts |
| state_card_diagram | show which layers are visible/blocked |
| safe_vs_unsafe_comparison_card | show allowed vs blocked wording or layout |
| red_team_fail_closed_diagram | show unsafe attempt → detection → block → repair → audit |
| export_boundary_diagram | show what safe export includes and excludes |
| workspace_mock_illustration | show synthetic UI layout concepts |
| authority_boundary_diagram | show authority envelope and no-decision object |
| audit_traceability_flow | show traceability chain |
| scenario_summary_card | show synthetic scenario structure |
| interaction_wireframe | show user navigation path |

These visual classes explain platform behavior.

They do not demonstrate clinical truth.

---

## 6. Blocked Visual Artifact Classes

The following visual classes are blocked.

| Blocked Visual Class | Why Blocked |
|---|---|
| diagnostic_image_illustration | may be mistaken for diagnostic proof |
| disease_atlas_panel | shifts platform toward disease-teaching authority |
| probability_heatmap | implies quantitative diagnostic ranking |
| confidence_meter | implies hidden certainty scoring |
| treatment_algorithm_diagram | implies treatment authority |
| triage_decision_tree | implies triage/disposition authority |
| patient_education_visual | implies patient-facing use |
| real_CT_or_HRCT_case_demo | violates synthetic demo boundary |
| diagnosis_ranking_dashboard | implies closure and priority selection |
| biopsy_recommendation_flow | implies procedural authority |
| follow_up_timeline_recommender | implies follow-up scheduling authority |
| guideline_decision_replacement_tree | implies platform replaces expert interpretation |

Blocked visual rule:

> If a visual class can be reasonably mistaken for diagnostic proof, treatment guidance, triage logic, or patient instruction, it must not be used in v0.14 demo artifacts.

---

## 7. Illustration Is Not Clinical Imaging

All demo visuals must preserve the rule:

> illustration ≠ clinical image

This means:

- no real CT slices,
- no pseudo-real HRCT slice renderings,
- no disease-labeled lung atlases,
- no “classic UIP example” image panels,
- no “typical HP” visual examples,
- no “organizing pneumonia pattern” image teaching cards,
- no clinical-image-like montage designed to teach disease identification.

Allowed substitutes:

- abstract geometric lung-region diagrams,
- neutral pattern placeholders,
- symbolic region maps,
- relationship diagrams,
- state flow cards,
- layer maps.

Validation condition:

> Demo visuals may represent conceptual structure, not diagnostic appearance.

---

## 8. Diagram Is Not Proof

All demo diagrams must preserve the rule:

> diagram ≠ proof

Blocked implications:

- “this flow proves UIP,”
- “this branch confirms HP,”
- “this relationship validates diagnosis,”
- “this node path identifies disease.”

Allowed implications:

- “this flow shows reasoning visibility,”
- “this relation shows overlap preserved,”
- “this diagram shows missing evidence remains visible,”
- “this sequence shows unsafe export fail-closed behavior.”

Validation condition:

> A diagram may explain platform behavior, not prove clinical correctness.

---

## 9. Visual State vs Decision State

Visuals may show:

- visible,
- missing,
- unresolved,
- review-visible,
- source-limited,
- blocked,
- fail-closed,
- audit-recorded,
- repair-required,
- discussion-preparation.

Visuals must not show:

- diagnosed,
- ruled out,
- confirmed,
- likely,
- unlikely,
- high probability,
- low probability,
- treat now,
- biopsy required,
- safe for discharge,
- follow-up due,
- public-ready,
- clinically validated.

Visual rule:

> Visuals may display state; they must not display decision.

---

## 10. Color Safety Contract

Color may help orientation, but must not create hidden authority.

Allowed color semantics:

| Color Role | Allowed Meaning |
|---|---|
| neutral blue | informational / visible |
| muted amber | missing / incomplete / limited |
| muted gray | blocked / not allowed / inactive |
| muted red | urgent review visibility or fail-closed event |
| muted purple | overlap / unresolved coexistence |

Blocked color semantics:

| Blocked Use | Why Blocked |
|---|---|
| green = correct diagnosis | hidden confirmation |
| red-green diagnosis traffic light | triage/decision implication |
| heat scale for disease certainty | probability implication |
| brighter color = more likely disease | ranking implication |
| gradient likelihood bars | implicit confidence scoring |

Color rule:

> Color may express state category, not certainty, priority ranking, or treatment urgency.

---

## 11. Icon Safety Contract

Icons may assist navigation only.

Allowed icon roles:

- missing evidence marker,
- source limitation marker,
- blocked output marker,
- review-visible marker,
- audit trace marker,
- overlap marker,
- export-safe marker,
- fail-closed marker.

Blocked icon roles:

- diagnosis confirmed icon,
- disease winner icon,
- treatment recommended icon,
- safe discharge icon,
- next-best-step icon,
- probability medal/icon,
- urgent intervention icon used as action directive.

Icon rule:

> Icons may label state categories, not medical decisions.

---

## 12. Text Must Accompany Strong Visuals

Any strong visual artifact must carry short accompanying governance text.

Required when visual is:

- large flow diagram,
- safe-vs-unsafe comparison,
- red-team fail-closed visual,
- reasoning map,
- export boundary diagram,
- scenario summary card.

Required companion text must clarify at least one of:

- synthetic status,
- non-clinical status,
- non-diagnostic status,
- missing evidence limitation,
- mimic visibility limitation,
- overlap unresolved state,
- review-only nature,
- fail-closed meaning,
- authority effect none.

Example rule:

A visual showing UIP-like prompt + HP overlap must also state:

> “Exposure history not provided. HP-related review visibility remains unresolved and must not be treated as excluded.”

Text-governance rule:

> No high-salience visual should stand alone without a boundary-preserving text anchor.

---

## 13. Allowed Visual Narrative Types

The following narrative types are allowed.

### 13.1 Scenario Flow

Example structure:

```text
Synthetic case context
→ Missing evidence
→ Confidence limiter
→ Mimic visibility
→ Overlap preserved
→ Review prompt
→ Safe export
```

### 13.2 Fail-Closed Flow

Example structure:

```text
Unsafe input
→ Unsafe state detected
→ Export blocked
→ Repair required
→ Revalidation required
→ Audit recorded
```

### 13.3 Safe vs Unsafe Comparison

Example structure:

```text
Unsafe:
Impression
HP ruled out
Biopsy required

Safe:
Pattern family prompt
HP review-visible
Procedure decisions outside platform authority
```

### 13.4 Architecture Overview

Example structure:

```text
Evidence Intake
→ Clinician Workspace
→ Reasoning Session Object
→ Snapshot / Revision / Audit
→ Safe MDD Preparation Export
```

### 13.5 Authority Boundary Diagram

Example structure:

```text
Authority envelope
+ no-decision object
→ blocks diagnosis / treatment / follow-up / triage / public-ready use
```

Allowed narrative rule:

> Visual narratives may explain process and boundaries, not disease certainty.

---

## 14. Blocked Visual Narrative Types

Blocked narrative types include:

- “How to diagnose UIP from CT” infographic,
- “When to biopsy” decision tree,
- “What treatment to start” flowchart,
- “When to discharge / admit” safety pathway,
- “Disease likelihood ladder,”
- “Top 3 diagnoses” ranking panel,
- “Best next test” action pathway,
- “Patient guide to your scan” explainer,
- “Classic imaging appearances” atlas montage,
- “Progressive disease score” dashboard.

Blocked narrative rule:

> A visual narrative becomes invalid when it teaches or implies decision authority instead of reasoning governance.

---

## 15. Safe vs Unsafe Export Visual Rules

Safe-vs-unsafe visuals are allowed and encouraged.

They may show:

- unsafe heading vs safe heading,
- unsafe wording vs safe wording,
- unsafe patient-facing phrasing vs clinician-review-only phrasing,
- unsafe diagnosis badge vs safe evidence-state badge,
- unsafe probability table vs safe evidence-state table.

They must not:

- present unsafe content as acceptable,
- retain unsafe content without visible “blocked” state,
- imply the unsafe content is just stylistically discouraged,
- imply the unsafe content could be permitted in advanced mode.

Required rules:

- unsafe side must be visibly blocked,
- safe side must preserve non-authority wording,
- companion text must explain why unsafe content is blocked.

---

## 16. Red-Team Visual Rules

Red-team visuals are allowed if and only if they show fail-closed behavior.

They may show:

- unsafe input string,
- attacked surface,
- detection node,
- block outcome,
- repair requirement,
- revalidation requirement,
- audit record.

They must not show:

- unsafe content as final output,
- partially accepted unsafe output,
- user-overrides that bypass the block,
- clinician-facing advice generated from the block.

Required red-team visual rule:

> Red-team visuals must celebrate blocking, not demonstrate unsafe capability.

---

## 17. Workspace Mock Visual Rules

Workspace mock visuals may illustrate:

- layer order,
- layout zones,
- panel relationships,
- which cards stay visible,
- where audit trail appears,
- how blocked outputs are surfaced,
- how missing evidence and mimic visibility appear together.

Workspace mock visuals must not illustrate:

- “final diagnosis” panel,
- “recommended treatment” module,
- “recommended biopsy” card,
- “follow-up scheduler” widget,
- “patient summary” panel,
- “public-ready export” toggle,
- “clinically validated” ribbon.

Workspace mock rule:

> Workspace mock visuals show interface structure, not clinical decision UI.

---

## 18. Export Preview Visual Rules

Export preview visuals may show:

- non-authority statement,
- authority envelope,
- no-decision statement,
- blocked output notice,
- source status,
- missing evidence,
- confidence limiters,
- mimic visibility,
- overlap,
- review prompts,
- audit references.

They must not show:

- impression,
- final diagnosis,
- exclusion statement,
- treatment recommendation,
- follow-up recommendation,
- triage recommendation,
- MDD consensus,
- patient explanation.

Preview rule:

> A visual export preview must remain visually non-report-like and non-diagnostic.

---

## 19. Scenario Illustration Rules

Each scenario illustration may show:

- fictional case context,
- missing fields,
- review-visible mimic,
- unresolved overlap,
- active confidence limiter,
- review prompts,
- safe export outcome,
- blocked outputs.

Each scenario illustration must not show:

- disease conclusion,
- winner diagnosis,
- action recommendation,
- management pathway,
- real imaging example,
- pathological proof,
- patient instructions.

Scenario illustration rule:

> Scenario illustrations explain why uncertainty remains visible.

---

## 20. Required Visual Safety Label

Every major demo visual artifact must include or inherit a visual safety label:

```yaml
visual_safety_label:
  synthetic_only: true
  real_patient_data: false
  non_clinical_demo: true
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  clinically_reviewed_platform_wide: false
  visual_role: explanatory_only
```

Required visible statement:

> This is a synthetic explanatory visual. It demonstrates platform governance behavior only. It is not a diagnostic image, treatment pathway, patient-facing artifact, or clinically validated output.

---

## 21. Required Visual Review Questions

Before a visual artifact is accepted, the following questions must all be answered safely:

1. Could this visual be mistaken for a diagnostic image?
2. Could this visual be mistaken for disease confirmation?
3. Could this visual be mistaken for a probability display?
4. Could this visual be mistaken for a treatment recommendation?
5. Could this visual be mistaken for triage advice?
6. Could this visual be mistaken for patient education?
7. Could this visual be mistaken for public-ready product output?
8. Could this visual hide missing evidence or uncertainty?
9. Could this visual hide mimic visibility?
10. Could this visual turn overlap into closure?
11. Could this visual hide authority envelope or no-decision boundaries?
12. Could this visual make audit look like clinical validation?

Acceptance rule:

> If the answer is “yes” to any of these without mitigation, the visual artifact is unsafe.

---

## 22. Allowed Illustration Families for v0.14

The following illustration families are explicitly encouraged for v0.14:

- synthetic reasoning flow cards,
- state transition diagrams,
- overlap relation maps,
- missing evidence visibility diagrams,
- safe export boundary diagrams,
- fail-closed red-team diagrams,
- safe-vs-unsafe comparison cards,
- workspace wireframes,
- audit traceability chains,
- layered reasoning maps.

These are preferred because they make platform behavior visible without simulating diagnostic authority.

---

## 23. Blocked Illustration Families for v0.14

The following illustration families are explicitly blocked for v0.14:

- pseudo-HRCT disease plates,
- real-case radiology teaching boards,
- disease recognition flashcards,
- diagnosis ranking dashboards,
- management algorithms,
- treatment pathway posters,
- prognostic risk meters,
- follow-up interval charts,
- patient explanation pamphlets,
- “classic CT findings of…” panels,
- “top differentials” scoreboards.

These are blocked because they would distort the platform’s reasoning-governance identity.

---

## 24. Minimal Visual Mode

Minimal visual mode may exist if it preserves:

- visual safety label,
- synthetic explanatory status,
- authority envelope visibility,
- no-decision boundary visibility,
- non-diagnostic text anchor,
- no patient-facing implication,
- no public-ready implication.

Minimal mode may reduce ornamentation, but not safety.

---

## 25. Full Visual Mode

Full visual mode may include:

- architecture diagram,
- scenario cards,
- reasoning maps,
- safe-vs-unsafe cards,
- red-team fail-closed diagrams,
- workspace mockups,
- export preview panels,
- authority boundary panels,
- audit traceability panels.

Full mode is acceptable only if every visual still obeys:

- illustration ≠ clinical image,
- diagram ≠ proof,
- color ≠ probability,
- icon ≠ authority,
- flow ≠ treatment pathway,
- visual ≠ patient guidance.

---

## 26. v0.14.6 Acceptance Criteria

v0.14.6 is accepted only if:

- visual role is defined as explanatory only,
- visually guided but text-governed philosophy is defined,
- allowed visual classes are defined,
- blocked visual classes are defined,
- illustration ≠ clinical image rule is defined,
- diagram ≠ proof rule is defined,
- state-vs-decision distinction is defined,
- color safety contract is defined,
- icon safety contract is defined,
- companion text requirement is defined,
- allowed visual narrative types are defined,
- blocked visual narrative types are defined,
- safe-vs-unsafe visual rules are defined,
- red-team visual rules are defined,
- workspace mock visual rules are defined,
- export preview visual rules are defined,
- scenario illustration rules are defined,
- visual safety label is defined,
- visual review questions are defined,
- allowed illustration families are defined,
- blocked illustration families are defined,
- minimal visual mode is bounded,
- full visual mode is bounded,
- no diagnostic image authority is opened,
- no probability surface is opened,
- no treatment or triage visual authority is opened,
- no patient-facing visual layer is opened,
- no public-ready visual claim is opened.

---

## 27. Next Step

If this contract is accepted, the next recommended step is:

- v0.14.7 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract Structural Seal

The seal should lock v0.14 as structurally complete, including:

- synthetic demo case governance,
- demo case schema,
- demo session/snapshot/export fixture schema,
- first scenario set,
- red-team fail-closed set,
- synthetic scenario safety gate,
- visual artifact safety contract,
- safety labels,
- authority envelope persistence,
- no-decision persistence,
- audit traceability,
- non-diagnostic safe export,
- fail-closed unsafe export handling,
- visually guided but text-governed interface principles.

---

## 28. Governance Statement

This document defines the visual safety contract for demo illustrations and other visual artifacts.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not clinically validate the platform.  
It does not create disease-teaching atlas authority.

Visual artifacts remain synthetic explanatory supports only.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.6:

> “A visual artifact is valid only if it explains reasoning state, safety boundaries, or fail-closed behavior without acting as diagnostic proof, disease confirmation, probability display, treatment pathway, patient-facing explanation, or public-ready clinical illustration.”