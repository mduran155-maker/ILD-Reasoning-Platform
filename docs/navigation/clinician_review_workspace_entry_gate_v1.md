# ILD Reasoning Platform — Clinician Review Workspace / Interactive Reasoning UI Contract Entry Gate v1

Version: v0.10.0  
Status: clinician_review_workspace_entry_gate  
Scope: Interactive clinician-facing reasoning workspace contract entry gate  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document opens v0.10 — Clinician Review Workspace / Interactive Reasoning UI Contract.

v0.10 defines how clinicians may safely interact with the structured reasoning layers sealed in v0.9.

This document does not add new disease content.

This document does not diagnose.  
This document does not treat.  
This document does not decide tests.  
This document does not decide procedures.  
This document does not schedule follow-up.  
This document does not exclude mimics.  
This document does not replace MDD.  
This document does not create public readiness.  
This document does not make the platform clinically reviewed.  
This document does not create a patient-facing product.

Its purpose is to define the entry gate for an interactive review workspace that displays reasoning safely without converting interaction into clinical authority.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.9 sealed principle remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

The v0.10 entry principle is:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

---

## 2. Relationship to Prior Seals

v0.10 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Upgrade,
- v0.6.R1/R2/R3 source debt and source-status correction,
- v0.7 Non-UIP Fibrotic ILD Differential Reasoning Structural Seal,
- v0.8 High-Risk Mimic Source-Limited Prompt Visibility Structural Seal,
- v0.9 Reasoning Output Contract / Structured Response Schema Structural Seal,
- checkpoint-v0.9 and 100-file milestone roadmap discipline.

v0.10 must not weaken any prior seal.

v0.10 is a clinician review workspace governance phase.

It is not:

- a diagnostic phase,
- a treatment phase,
- a public-readiness phase,
- a patient-facing phase,
- an automated clinical decision-support deployment phase.

---

## 3. v0.10 Entry Gate Scope

v0.10 may define:

- clinician review workspace layout,
- interactive reasoning layer cards,
- source-status badges,
- missing-evidence panel,
- high-risk mimic visibility panel,
- temporal comparison panel,
- overlap panel,
- uncertainty panel,
- urgent review banner,
- MDD / specialist review panel,
- blocked output guardrails,
- authority envelope footer,
- audit trail for visible prompts,
- interaction constraints,
- safe expand/collapse behavior,
- safe filtering behavior,
- safe export / copy behavior,
- clinician-facing UI wording constraints.

v0.10 may not define:

- new disease diagnosis,
- treatment pathway,
- test ordering workflow,
- procedure recommendation workflow,
- follow-up schedule workflow,
- patient-facing report,
- public-ready interface,
- platform-wide clinical review status,
- autonomous triage,
- autonomous MDD replacement.

---

## 4. Global Authority Constraints

The following constraints remain mandatory across v0.10.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed.platform_wide | false |
| patient_facing_use | not_allowed |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_test_order | not_allowed |
| automated_procedure_decision | not_allowed |
| automated_follow_up_schedule | not_allowed |
| automated_triage | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_rheumatologist | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_occupational_medicine_review | not_allowed |
| replacement_of_oncology_review | not_allowed |
| replacement_of_radiation_oncology_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No workspace interaction may override these constraints.

---

## 5. Workspace Philosophy

The workspace must help the clinician inspect reasoning.

It must not push the clinician toward a final disease label.

The workspace should make the following easier to see:

- what was provided,
- what changed,
- which pattern prompts are visible,
- which differentials remain unresolved,
- which high-risk mimics remain visible,
- which evidence is missing,
- which overlaps remain unresolved,
- what limits interpretation,
- which source anchors support prompt visibility,
- where source limitations exist,
- whether urgent review prompts are visible,
- whether MDD or specialist review prompts are visible,
- what outputs are blocked,
- what authority limits remain active.

The workspace must not make the following easier to do:

- diagnose,
- exclude mimics,
- recommend treatment,
- order tests,
- decide procedures,
- schedule follow-up,
- bypass MDD,
- bypass urgent clinical review,
- generate a patient-facing report,
- imply public readiness.

Workspace rule:

> The workspace is a reasoning visibility surface, not a decision surface.

---

## 6. Clinician Workspace Component Registry

The following workspace components are opened for contract design.

| Component ID | Component Name | Purpose | Authority Risk |
|---|---|---|---|
| V10_COMPONENT_001 | reasoning_flow_layout | Display four-phase Case Reasoning Flow | disease-first layout risk |
| V10_COMPONENT_002 | layer_cards | Display 13 structured output layers | layer-as-diagnosis risk |
| V10_COMPONENT_003 | source_status_badges | Show source role, mapping, and limitations | source-as-validation risk |
| V10_COMPONENT_004 | missing_evidence_panel | Show missing pieces | missing-evidence-as-exclusion risk |
| V10_COMPONENT_005 | mimic_visibility_panel | Show high-risk mimics | mimic-as-diagnosis risk |
| V10_COMPONENT_006 | temporal_comparison_panel | Show change before disease naming | progression-overclaim risk |
| V10_COMPONENT_007 | overlap_panel | Show coexistence and unresolved boundaries | single-label closure risk |
| V10_COMPONENT_008 | uncertainty_panel | Show confidence limiters | diagnostic-confidence risk |
| V10_COMPONENT_009 | urgent_review_banner | Show urgent review prompt where relevant | triage-authority risk |
| V10_COMPONENT_010 | MDD_review_panel | Show MDD / specialist review prompts | MDD-replacement risk |
| V10_COMPONENT_011 | blocked_output_guardrails | Prevent unsafe actions/phrases | hidden-advice risk |
| V10_COMPONENT_012 | authority_envelope_footer | Keep authority limits always visible | authority-hidden risk |
| V10_COMPONENT_013 | audit_trail | Record visible prompts and reasons | audit-as-validation risk |

---

## 7. Required Workspace Layout

The workspace must preserve the v0.9 four-phase reasoning flow.

| Workspace Section | Required Components |
|---|---|
| Grounding | case context card; temporal comparison panel |
| Reasoning Core | pattern family cards; differential prompt cards; overlap panel |
| Safety Net | high-risk mimic panel; missing evidence panel; uncertainty panel |
| Escalation and Governance | urgent review banner; MDD review panel; source status badges; authority footer; blocked output guardrails; audit trail |

Layout rule:

> The workspace must not begin with a final diagnosis field.

Blocked first-screen elements:

- “Final diagnosis”
- “Most likely diagnosis”
- “Treatment recommendation”
- “Order next test”
- “Biopsy recommendation”
- “Follow-up interval”
- “Patient-ready summary”

---

## 8. Interaction Types

### 8.1 Allowed Interactions

The workspace may allow the clinician to:

- expand a reasoning layer,
- collapse a reasoning layer,
- inspect source status,
- inspect claim mapping status,
- inspect source limitations,
- view missing evidence,
- view high-risk mimic prompts,
- view overlap states,
- view confidence limiters,
- view urgent review prompt status,
- view MDD / specialist review prompts,
- copy a non-authoritative structured summary,
- export a governance-safe draft,
- mark an item as “reviewed by clinician” without converting it into platform authority,
- add clinician notes as separate clinician-authored notes,
- mark evidence as provided if user supplies it,
- rerun reasoning visibility after new evidence is provided.

### 8.2 Blocked Interactions

The workspace must not allow the platform to:

- select final diagnosis,
- confirm diagnosis,
- exclude disease or mimic,
- recommend treatment,
- recommend stopping or starting medication,
- recommend steroid therapy,
- recommend antifungal or antimicrobial therapy,
- order HRCT,
- order PET/CT,
- order serology,
- order microbiology,
- order biopsy,
- order bronchoscopy,
- order BAL,
- schedule follow-up interval,
- generate patient-facing advice,
- declare MDD unnecessary,
- declare urgent review unnecessary,
- mark public_ready as true,
- mark clinically_reviewed.platform_wide as true.

Interaction rule:

> Clinician interaction may annotate reasoning; it may not turn the platform into a decision-maker.

---

## 9. Component Rules

### 9.1 reasoning_flow_layout

Required:

- show four phases,
- preserve order,
- keep safety and governance visible,
- avoid disease-first layout.

Blocked:

- diagnosis-first layout,
- final impression field,
- hidden authority envelope,
- collapsed safety layer by default in high-risk cases.

---

### 9.2 layer_cards

Required:

- show layer name,
- show layer purpose,
- show active prompts,
- show missing evidence where relevant,
- show source status attachment,
- show authority limits.

Blocked:

- card title as diagnosis,
- color coding that implies diagnosis certainty,
- “confirmed” status,
- “excluded” status,
- disease probability meter.

---

### 9.3 source_status_badges

Required badge types:

- primary_high_authority,
- primary_limited_scope,
- auxiliary_review,
- diagnostic_performance_study,
- case_example_cautionary,
- internal_governance,
- claim_mapped,
- partially_mapped,
- source_limited,
- treatment_heavy_limited,
- diagnostic_performance_limited,
- cautionary_case_only,
- narrow_reviewed_scope,
- platform_wide_review_false.

Blocked badge types:

- diagnosis_confirmed,
- clinically_validated,
- public_ready,
- treatment_recommended,
- test_order_supported,
- biopsy_required,
- disease_excluded.

Badge rule:

> Source badge means source status, not clinical authority.

---

### 9.4 missing_evidence_panel

Required:

- list missing evidence,
- link missing evidence to affected prompts,
- state that missing evidence is not exclusion,
- allow clinician-supplied updates as provided facts.

Blocked:

- hide missing evidence after clinician opens diagnosis-oriented layer,
- treat missing evidence as exclusion,
- auto-fill missing evidence,
- infer missing occupational, exposure, medication, malignancy, microbiology, or prior imaging data.

Panel rule:

> Missing pieces remain visible until explicitly supplied.

---

### 9.5 mimic_visibility_panel

Required:

- show high-risk mimics,
- show why each mimic remains visible,
- show missing evidence for each mimic,
- show source limitation for each mimic,
- show not diagnosed / not excluded status.

Blocked:

- “mimic confirmed,”
- “mimic excluded,”
- “treat mimic,”
- “order test for mimic,”
- hide mimics behind chronic ILD label.

Panel rule:

> Mimic visibility prevents unsafe closure; it is not mimic diagnosis.

---

### 9.6 temporal_comparison_panel

Required:

- show prior comparison status,
- show change direction if supported,
- show temporal limiters,
- show acute vs chronic uncertainty,
- show narrow reviewed scope where applicable.

Blocked:

- PPF diagnosis,
- acute exacerbation diagnosis,
- progression confirmed without sufficient temporal context,
- invented prior comparison.

Panel rule:

> Temporal comparison shows change; it does not own diagnosis.

---

### 9.7 overlap_panel

Required:

- show coexisting processes,
- show unresolved boundaries,
- show competing families,
- show acute overlay separately from chronic background.

Blocked:

- forced single winner,
- hidden overlap,
- hidden acute overlay,
- hidden mimic.

Panel rule:

> Overlap is displayed as coexistence, not forced closure.

---

### 9.8 uncertainty_panel

Required:

- show unresolved questions,
- show confidence limiters,
- show source uncertainty,
- show closure_status: not_established.

Blocked:

- diagnostic confidence score,
- disease probability,
- ranked diagnosis,
- “high confidence IPF,”
- “low confidence HP.”

Panel rule:

> The workspace shows what limits interpretation, not what diagnosis it owns.

---

### 9.9 urgent_review_banner

Required where relevant:

- show urgent prompt visibly,
- appear above MDD and disease-family cards when active,
- state that platform does not triage, diagnose, or treat.

Blocked:

- emergency triage decision,
- treatment recommendation,
- “no urgent review needed” when data are incomplete,
- hiding urgent banner behind collapsed panel.

Banner rule:

> Urgent review prompt is safety visibility, not triage authority.

---

### 9.10 MDD_review_panel

Required:

- show MDD prompt where relevant,
- show specialist domains involved,
- show reason for review prompt,
- preserve “not replacement” statement.

Blocked:

- MDD unnecessary,
- MDD replaced,
- final diagnosis generated from MDD panel,
- single-specialty closure when cross-domain uncertainty persists.

Panel rule:

> The workspace may show why review is relevant; it may not replace review.

---

### 9.11 blocked_output_guardrails

Required:

- intercept diagnosis requests,
- intercept exclusion requests,
- intercept treatment requests,
- intercept test-order requests,
- intercept procedure-decision requests,
- intercept follow-up requests,
- intercept public-ready export requests,
- reframe into safe structured output.

Blocked:

- direct answer to blocked request,
- hidden recommendation,
- “soft” diagnosis,
- action-oriented workaround.

Guardrail rule:

> The guardrail must block both explicit authority leaks and disguised authority leaks.

---

### 9.12 authority_envelope_footer

Required:

Always visible:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
```

Optional narrow scopes may be shown only as limited metadata.

Blocked:

- hiding footer,
- allowing footer to be dismissed permanently,
- changing authority values through UI interaction.

Footer rule:

> Authority limits remain visible even when reasoning layers are collapsed.

---

### 9.13 audit_trail

Required:

- record which prompts were visible,
- record which evidence was missing,
- record which source statuses were shown,
- record which blocked output guardrails were triggered,
- record user-supplied evidence updates as separate events,
- distinguish platform-generated visibility from clinician-authored notes.

Blocked:

- audit trail as clinical validation,
- audit trail as diagnosis,
- audit trail as treatment authorization,
- audit trail as MDD replacement.

Audit rule:

> Audit trail records reasoning visibility; it does not validate clinical correctness.

---

## 10. Clinician Notes Boundary

The workspace may allow clinician notes only if clearly separated from platform reasoning.

Required separation:

| Note Type | Required Label |
|---|---|
| platform-generated reasoning | platform_reasoning_non_authoritative |
| clinician-authored note | clinician_authored_note |
| user-provided evidence update | clinician_supplied_evidence |
| source status | source_governance_metadata |
| authority envelope | platform_authority_boundary |

Clinician note rule:

> Clinician-authored notes are not platform diagnoses, and platform reasoning is not clinician judgment.

Blocked:

- merging clinician notes into platform conclusions,
- treating clinician note as source-reviewed claim,
- using clinician note to create platform-wide clinical review.

---

## 11. Safe Export / Copy Boundary

The workspace may support export or copy only under governance constraints.

Allowed export types:

- governance-safe structured reasoning draft,
- source status summary,
- missing evidence checklist,
- mimic visibility summary,
- MDD discussion preparation draft,
- audit trail of prompts displayed.

Blocked export types:

- final diagnostic report,
- treatment recommendation report,
- patient-facing report,
- test-order recommendation,
- procedure recommendation,
- follow-up schedule,
- public-ready output.

Export rule:

> Exported content must preserve the authority envelope.

---

## 12. UI Wording Contract

Preferred UI labels:

| Preferred UI Label | Meaning |
|---|---|
| Reasoning Prompt | Non-diagnostic prompt |
| Pattern Family Prompt | Pattern visibility only |
| Mimic Visibility | Mimic prompt, not diagnosis |
| Missing Evidence | Missing pieces, not exclusion |
| Confidence Limiter | Interpretation limiter |
| Source Status | Source role and limitation |
| Review Prompt | MDD/specialist review visibility |
| Urgent Review Prompt | Safety visibility |
| Authority Envelope | Non-authority boundary |
| Blocked Output | Unsafe output category |

Blocked UI labels:

| Blocked UI Label | Reason |
|---|---|
| Final Diagnosis | diagnostic authority leak |
| Confirmed Diagnosis | diagnostic authority leak |
| Ruled Out | exclusion authority leak |
| Recommended Treatment | treatment authority leak |
| Order Next Test | test-order authority leak |
| Biopsy Required | procedure authority leak |
| Follow-Up Plan | management authority leak |
| Patient Summary | patient-facing risk |
| Clinically Validated | unsupported validation |
| Public Ready | unsupported deployment |

UI wording rule:

> UI language must keep reasoning visible without creating clinical command language.

---

## 13. Workspace Safety Priority

When UI components compete for space or attention, priority is:

1. urgent_review_banner,
2. high_risk_mimic_layer / mimic_visibility_panel,
3. missing_evidence_panel,
4. source_status_badges and limitations,
5. uncertainty_panel,
6. overlap_panel,
7. temporal_comparison_panel,
8. pattern_family_prompts,
9. differential_prompt_layer,
10. MDD_review_panel,
11. authority_envelope_footer,
12. audit_trail,
13. blocked_output_guardrails.

Priority rule:

> Safety, mimics, missing evidence, source limits, and uncertainty must not be visually buried.

---

## 14. Workspace Modes

v0.10 may later define workspace modes, but v0.10.0 only opens their discussion.

Allowed future modes:

| Mode | Purpose | Authority State |
|---|---|---|
| compact_review_mode | shorter reasoning summary | non_authoritative |
| full_reasoning_mode | all 13 layers visible | non_authoritative |
| MDD_preparation_mode | prepare discussion points | non_authoritative |
| source_audit_mode | inspect sources and claim mapping | non_authoritative |
| missing_evidence_mode | inspect missing pieces | non_authoritative |
| high_risk_mimic_mode | inspect mimics and overlays | non_authoritative |

Blocked future modes:

| Mode | Reason Blocked |
|---|---|
| diagnosis_mode | diagnostic authority leak |
| treatment_mode | treatment authority leak |
| ordering_mode | test/procedure authority leak |
| follow_up_mode | management authority leak |
| patient_mode | patient-facing use not allowed |
| public_mode | public_ready false |
| auto_triage_mode | triage authority leak |

---

## 15. Workspace Acceptance Criteria for v0.10.0

v0.10.0 is accepted only if:

- v0.10 opens as clinician review workspace governance,
- workspace is defined as reasoning visibility surface,
- workspace is not a decision surface,
- core components are listed,
- UI authority constraints are explicit,
- allowed and blocked interactions are defined,
- source-status badges are constrained,
- missing evidence panel is constrained,
- mimic visibility panel is constrained,
- temporal comparison panel is constrained,
- uncertainty panel uses confidence limiters,
- urgent review banner has no triage authority,
- MDD panel does not replace MDD,
- authority envelope footer is always visible,
- audit trail does not become validation,
- safe export/copy remains non-authoritative,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

---

## 16. Next Step

The next recommended step is:

- v0.10.1 — Clinician Workspace Component Schema

v0.10.1 should define detailed schemas for:

- reasoning_flow_layout,
- layer_cards,
- source_status_badges,
- missing_evidence_panel,
- mimic_visibility_panel,
- temporal_comparison_panel,
- overlap_panel,
- uncertainty_panel,
- urgent_review_banner,
- MDD_review_panel,
- blocked_output_guardrails,
- authority_envelope_footer,
- audit_trail.

v0.10.1 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 17. Governance Statement

This entry gate opens clinician review workspace governance.

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

The platform remains an evidence-governed clinical reasoning platform.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 entry rule is:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”