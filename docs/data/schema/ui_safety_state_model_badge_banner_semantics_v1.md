# ILD Reasoning Platform — UI Safety State Model / Badge and Banner Semantics v1

Version: v0.10.3  
Status: ui_safety_state_model_badge_banner_semantics  
Scope: Safety state, badge, banner, label, and visual semantics for clinician review workspace  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the UI safety state model, badge semantics, banner semantics, label rules, and visual meaning constraints for v0.10 — Clinician Review Workspace / Interactive Reasoning UI Contract.

It follows:

- `docs/navigation/clinician_review_workspace_entry_gate_v1.md`
- `docs/data/schema/clinician_workspace_component_schema_v1.md`
- `docs/data/schema/workspace_interaction_rules_allowed_blocked_map_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`
- `docs/data/schema/structured_output_layer_schema_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_9.md`

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
This document does not create patient-facing use.

Its purpose is to ensure that UI states, badges, banners, labels, icons, colors, urgency markers, and visual emphasis increase reasoning visibility without implying clinical authority.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.3:

> “UI semantics must make uncertainty, source limits, missing evidence, mimics, and authority boundaries visible without visually implying diagnosis, exclusion, treatment, or safety clearance.”

---

## 2. Global UI Safety Contract

Every UI safety state, badge, banner, label, icon, and visual emphasis must preserve:

| Field | Required State |
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
| replacement_of_specialist_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No UI visual state may imply:

- diagnosis confirmed,
- disease excluded,
- treatment recommended,
- test order supported,
- procedure recommended,
- follow-up interval set,
- triage decision made,
- public-ready status,
- patient-facing readiness,
- platform-wide clinical review.

---

## 3. UI Semantic Principle

The UI may emphasize:

- prompt visibility,
- missing evidence,
- source limitation,
- high-risk mimic visibility,
- urgent review prompt visibility,
- MDD / specialist review visibility,
- uncertainty,
- blocked output guardrails,
- authority boundaries.

The UI may not emphasize:

- final diagnosis,
- most likely disease,
- disease confirmation,
- mimic exclusion,
- treatment action,
- next test,
- biopsy or BAL decision,
- follow-up timing,
- patient advice,
- public deployment status.

Semantic rule:

> UI emphasis must point toward safer reasoning, not toward clinical closure.

---

## 4. Safety State Registry

The following UI safety states are allowed.

| Safety State ID | State Name | Meaning | Authority Effect |
|---|---|---|---|
| V10_STATE_001 | prompt_visible | Reasoning prompt is visible | none |
| V10_STATE_002 | source_status_visible | Source role and limitation visible | none |
| V10_STATE_003 | source_limited | Source exists but use is constrained | none |
| V10_STATE_004 | missing_evidence_visible | Evidence gap visible | none |
| V10_STATE_005 | mimic_visible | High-risk mimic prompt visible | none |
| V10_STATE_006 | overlap_visible | Coexistence or unresolved boundary visible | none |
| V10_STATE_007 | uncertainty_visible | Unresolved question or confidence limiter visible | none |
| V10_STATE_008 | urgent_review_prompt_visible | Urgent review prompt visible | none |
| V10_STATE_009 | MDD_review_prompt_visible | MDD or specialist review prompt visible | none |
| V10_STATE_010 | blocked_output_guard_active | Unsafe output category blocked | none |
| V10_STATE_011 | authority_envelope_visible | Authority boundary visible | none |
| V10_STATE_012 | clinician_note_present | Clinician-authored note present | none |
| V10_STATE_013 | clinician_supplied_evidence_present | Evidence supplied by clinician | none |
| V10_STATE_014 | audit_recorded | Interaction event recorded | none |
| V10_STATE_015 | narrow_reviewed_scope_visible | Limited reviewed scope visible | none |

The following UI safety states are blocked.

| Blocked State ID | Blocked State | Why Blocked |
|---|---|---|
| V10_BLOCKED_STATE_001 | diagnosis_confirmed | diagnostic authority leak |
| V10_BLOCKED_STATE_002 | disease_excluded | exclusion authority leak |
| V10_BLOCKED_STATE_003 | mimic_confirmed | mimic overdiagnosis |
| V10_BLOCKED_STATE_004 | mimic_excluded | unsafe mimic closure |
| V10_BLOCKED_STATE_005 | treatment_recommended | treatment authority leak |
| V10_BLOCKED_STATE_006 | test_order_recommended | test-order authority leak |
| V10_BLOCKED_STATE_007 | procedure_recommended | procedure authority leak |
| V10_BLOCKED_STATE_008 | follow_up_interval_set | management authority leak |
| V10_BLOCKED_STATE_009 | triage_decision_made | triage authority leak |
| V10_BLOCKED_STATE_010 | MDD_replaced | review replacement |
| V10_BLOCKED_STATE_011 | urgent_review_replaced | urgent review replacement |
| V10_BLOCKED_STATE_012 | public_ready_enabled | public readiness leak |
| V10_BLOCKED_STATE_013 | patient_facing_enabled | patient-facing use leak |
| V10_BLOCKED_STATE_014 | platform_wide_clinically_reviewed_true | unsupported clinical review claim |
| V10_BLOCKED_STATE_015 | diagnostic_confidence_displayed | diagnostic confidence leak |

---

## 5. Visual Token Model

The UI may use semantic tokens rather than diagnosis-like labels.

Allowed visual tokens:

| Token | Meaning |
|---|---|
| reasoning_prompt_token | Reasoning prompt is visible |
| source_role_token | Source role shown |
| source_limited_token | Source limitation shown |
| missing_evidence_token | Missing evidence shown |
| mimic_visibility_token | Mimic prompt shown |
| overlap_token | Overlap or coexistence shown |
| uncertainty_token | Confidence limiter or unresolved question shown |
| urgent_review_prompt_token | Urgent review prompt shown |
| MDD_review_prompt_token | MDD/specialist review prompt shown |
| blocked_output_token | Unsafe output blocked |
| authority_boundary_token | Authority envelope visible |
| clinician_note_token | Clinician-authored note present |
| clinician_supplied_evidence_token | Evidence supplied by clinician |
| audit_token | Audit event recorded |

Blocked visual tokens:

| Blocked Token | Why Blocked |
|---|---|
| diagnosis_confirmed_token | implies diagnosis |
| disease_excluded_token | implies exclusion |
| treatment_needed_token | implies treatment |
| order_next_test_token | implies test order |
| biopsy_required_token | implies procedure |
| follow_up_due_token | implies schedule |
| safe_to_ignore_token | unsafe reassurance |
| patient_ready_token | patient-facing leak |
| clinically_validated_token | unsupported validation |
| public_ready_token | deployment leak |
| high_confidence_diagnosis_token | diagnostic confidence leak |

Token rule:

> Visual tokens must identify reasoning state, not clinical decision state.

---

## 6. Color and Emphasis Semantics

The UI may use color or emphasis only to represent visibility, limitation, review need, or guardrail status.

Allowed color/emphasis meanings:

| Semantic Category | Allowed Meaning |
|---|---|
| neutral_information | provided facts, source metadata, layer title |
| reasoning_visibility | prompt is visible |
| limitation_visibility | missing evidence or source limitation |
| safety_visibility | urgent review prompt or high-risk mimic prompt |
| governance_visibility | authority envelope or blocked output guard |
| review_visibility | MDD/specialist review prompt |
| audit_visibility | audit event exists |

Blocked color/emphasis meanings:

| Blocked Meaning | Why Blocked |
|---|---|
| green means disease excluded | exclusion authority leak |
| green means safe / benign | unsafe reassurance |
| red means treatment required | treatment authority leak |
| red means diagnosis confirmed | diagnostic authority leak |
| yellow means probable diagnosis | diagnostic confidence leak |
| color gradient means disease probability | diagnostic probability leak |
| muted color hides missing evidence | missing evidence burial |
| low-saturation means mimic irrelevant | mimic erasure |
| checkmark means confirmed diagnosis | diagnostic confirmation leak |
| crossed-out label means ruled out | exclusion authority leak |

Color rule:

> Color may indicate attention or visibility, but it must not encode diagnosis, exclusion, treatment, probability, or safety clearance.

---

## 7. Icon Semantics

Allowed icon meanings:

| Icon Meaning | Allowed Use |
|---|---|
| information | source or context detail |
| limitation | missing evidence or source limitation |
| visibility | prompt remains visible |
| review | MDD/specialist review prompt |
| urgent prompt | urgent review prompt visibility |
| blocked | blocked output category |
| audit | event recorded |
| authority boundary | non-authority envelope |

Blocked icon meanings:

| Icon Meaning | Why Blocked |
|---|---|
| checkmark as diagnosis confirmed | diagnostic authority leak |
| checkmark as disease excluded | exclusion authority leak |
| prescription icon as treatment suggested | treatment authority leak |
| test tube as order recommended | test-order authority leak |
| scalpel as biopsy recommended | procedure authority leak |
| calendar as follow-up scheduled | management authority leak |
| shield as patient-safe | patient-facing safety claim |
| certificate as clinically validated | unsupported validation |
| launch icon as public-ready | deployment claim |

Icon rule:

> Icons may guide attention, not authorize clinical action.

---

## 8. Badge Semantics Registry

The following badge families are allowed.

| Badge Family | Purpose |
|---|---|
| source_status_badge | show source role and mapping status |
| source_limitation_badge | show limited, treatment-heavy, diagnostic-performance, or case-only source scope |
| missing_evidence_badge | show missing or incomplete evidence |
| mimic_visibility_badge | show high-risk mimic prompt visibility |
| overlap_badge | show unresolved coexistence or boundary |
| uncertainty_badge | show confidence limiter or unresolved question |
| urgent_review_badge | show urgent review prompt visibility |
| MDD_review_badge | show MDD/specialist review prompt visibility |
| authority_badge | show non-authority boundary |
| blocked_output_badge | show blocked output type |
| audit_badge | show audit event status |
| clinician_note_badge | show clinician-authored note boundary |
| narrow_reviewed_scope_badge | show limited reviewed metadata only |

Blocked badge families:

| Blocked Badge Family | Why Blocked |
|---|---|
| diagnosis_badge | diagnostic authority leak |
| confirmed_badge | confirmation leak |
| excluded_badge | exclusion leak |
| treatment_badge | treatment authority leak |
| order_badge | test-order authority leak |
| biopsy_badge | procedure authority leak |
| followup_badge | follow-up authority leak |
| patient_ready_badge | patient-facing leak |
| public_ready_badge | deployment leak |
| clinically_validated_badge | unsupported validation leak |
| probability_badge | diagnostic confidence leak |

---

## 9. Source Status Badge Semantics

### 9.1 Allowed Source Badges

| Badge | Meaning |
|---|---|
| primary_high_authority | Source role class only |
| primary_limited_scope | Source role class with limitation |
| auxiliary_review | Auxiliary review/context source |
| diagnostic_performance_study | Diagnostic-performance source; interpretation not automated |
| case_example_cautionary | Case example only; not generalized rule |
| internal_governance | Governance constraint; not clinical source |
| claim_mapped | Claim mapped to source |
| partially_mapped | Claim partially mapped |
| source_limited | Source use constrained |
| treatment_heavy_limited | Treatment content not imported |
| diagnostic_performance_limited | Feature visibility only |
| cautionary_case_only | Test case inspiration only |
| platform_wide_review_false | Platform-wide clinical review false |
| narrow_reviewed_scope | Limited scope metadata only |

### 9.2 Blocked Source Badges

| Badge | Why Blocked |
|---|---|
| clinically_validated | source mapping is not validation |
| diagnosis_supported | source mapping is not diagnosis |
| treatment_supported | source mapping is not treatment |
| test_order_supported | source mapping is not order |
| public_ready | source mapping is not deployment |
| patient_ready | source mapping is not patient-facing safety |

### 9.3 Required Source Badge Tooltip

Every source badge group must be able to display:

> Source status supports reasoning visibility only. It does not create diagnostic authority, treatment authority, public readiness, or platform-wide clinical review.

### 9.4 Source Badge Rule

> Source badges must increase transparency without implying validation, diagnosis, or management authority.

---

## 10. Missing Evidence Badge Semantics

### 10.1 Allowed Missing Evidence Badges

| Badge | Meaning |
|---|---|
| prior_CT_missing | Prior imaging unavailable or not documented |
| exposure_history_missing | Exposure context missing |
| occupational_history_missing | Occupational context missing |
| beryllium_context_missing | Beryllium context missing |
| medication_history_missing | Medication context missing |
| therapy_history_missing | Therapy context missing |
| radiation_context_missing | Radiation context missing |
| ICI_context_missing | Checkpoint inhibitor context missing |
| autoimmune_context_missing | CTD/SARD context missing |
| microbiology_missing | Microbiology context missing |
| AFB_culture_NAAT_missing | TB microbiology context missing |
| fungal_testing_missing | Fungal testing context missing |
| expiratory_HRCT_missing | Expiratory imaging context missing |
| BAL_context_missing | BAL context missing |
| pathology_context_missing | Pathology context missing |
| malignancy_status_missing | Malignancy status missing |
| PET_CT_context_missing | PET/CT context missing |
| aspiration_risk_missing | Aspiration risk context missing |
| urgent_clinical_status_missing | Urgent clinical data missing |
| MDD_status_missing | MDD context missing |

### 10.2 Blocked Missing Evidence Badges

| Badge | Why Blocked |
|---|---|
| HP_excluded_due_to_missing_exposure | missing evidence cannot exclude |
| infection_excluded_due_to_missing_microbiology | missing evidence cannot exclude |
| CTD_excluded_due_to_missing_serology | missing evidence cannot exclude |
| occupational_ILD_excluded_due_to_missing_history | missing evidence cannot exclude |
| malignancy_excluded_due_to_missing_context | missing evidence cannot exclude |
| stable_due_to_missing_prior_CT | missing prior CT cannot prove stability |

### 10.3 Required Missing Evidence Tooltip

> Missing evidence limits interpretation. Missing evidence is not exclusion.

### 10.4 Missing Evidence Badge Rule

> Missing evidence badges must keep missing pieces visible without turning absence into negative evidence.

---

## 11. Mimic Visibility Badge Semantics

### 11.1 Allowed Mimic Badges

| Badge | Meaning |
|---|---|
| infection_mimic_visible | Infection mimic prompt visible |
| TB_mimic_visible | TB mimic prompt visible |
| NTM_mimic_visible | NTM mimic prompt visible |
| fungal_mimic_visible | Fungal mimic prompt visible |
| aspiration_mimic_visible | Aspiration mimic prompt visible |
| occupational_mimic_visible | Occupational mimic prompt visible |
| beryllium_mimic_visible | Beryllium/sarcoid mimic prompt visible |
| drug_induced_mimic_visible | Drug-induced / therapy-related prompt visible |
| radiation_pneumonitis_mimic_visible | Radiation mimic prompt visible |
| checkpoint_inhibitor_pneumonitis_mimic_visible | ICI pneumonitis prompt visible |
| ICI_sarcoid_like_reaction_mimic_visible | ICI-SLR prompt visible |
| PLC_malignancy_mimic_visible | PLC/malignancy mimic prompt visible |
| lymphoma_recurrence_mimic_visible | Lymphoma/recurrence mimic prompt visible |
| sarcoid_like_reaction_mimic_visible | Sarcoid-like reaction prompt visible |
| acute_danger_overlay_visible | Acute dangerous overlay prompt visible |

### 11.2 Blocked Mimic Badges

| Badge | Why Blocked |
|---|---|
| TB_confirmed | diagnosis leak |
| TB_excluded | exclusion leak |
| fungal_excluded | exclusion leak |
| aspiration_confirmed | diagnosis leak |
| berylliosis_confirmed | diagnosis leak |
| radiation_pneumonitis_confirmed | diagnosis leak |
| CIP_confirmed | diagnosis leak |
| PLC_confirmed | diagnosis leak |
| malignancy_excluded | exclusion leak |
| SLR_confirmed | diagnosis leak |

### 11.3 Required Mimic Tooltip

> Mimic visibility means the mimic remains reasoning-visible. It is not diagnosed or excluded by this platform.

### 11.4 Mimic Badge Rule

> Mimic badges must prevent mimic erasure without creating mimic diagnosis.

---

## 12. Overlap Badge Semantics

### 12.1 Allowed Overlap Badges

| Badge | Meaning |
|---|---|
| UIP_HP_overlap_visible | UIP/HP boundary unresolved |
| UIP_CTD_overlap_visible | UIP/CTD boundary unresolved |
| NSIP_OP_overlap_visible | NSIP/OP overlap visible |
| OP_infection_overlap_visible | OP/infection overlap visible |
| OP_aspiration_overlap_visible | OP/aspiration overlap visible |
| sarcoid_infection_overlap_visible | Sarcoid/infection overlap visible |
| sarcoid_beryllium_overlap_visible | Sarcoid/beryllium overlap visible |
| sarcoid_malignancy_overlap_visible | Sarcoid/malignancy overlap visible |
| therapy_infection_overlap_visible | Therapy toxicity/infection overlap visible |
| radiation_recurrence_overlap_visible | Radiation/recurrence overlap visible |
| CIP_progression_overlap_visible | CIP/progression overlap visible |
| PLC_ILD_edema_overlap_visible | PLC/ILD/edema overlap visible |
| acute_chronic_overlap_visible | Acute overlay over chronic background visible |

### 12.2 Blocked Overlap Badges

| Badge | Why Blocked |
|---|---|
| overlap_resolved_by_platform | closure authority leak |
| winner_selected | forced diagnosis |
| secondary_process_excluded | unsafe closure |
| mimic_suppressed | mimic erasure |

### 12.3 Required Overlap Tooltip

> Overlap is displayed as coexistence or unresolved boundary, not as a winner selection.

### 12.4 Overlap Badge Rule

> Overlap badges must preserve coexistence and prevent forced single-label closure.

---

## 13. Uncertainty Badge Semantics

### 13.1 Allowed Uncertainty Badges

| Badge | Meaning |
|---|---|
| confidence_limiter_visible | Interpretation limiter visible |
| unresolved_question_visible | Unresolved question visible |
| source_uncertainty_visible | Source limitation visible |
| closure_not_established | Diagnostic closure not established |
| diagnostic_confidence_blocked | Diagnostic confidence not allowed |
| probability_blocked | Numeric probability not allowed |

### 13.2 Blocked Uncertainty Badges

| Badge | Why Blocked |
|---|---|
| high_confidence_IPF | diagnostic confidence leak |
| low_confidence_HP | diagnostic confidence leak |
| disease_probability | probability leak |
| final_rank | diagnostic ranking leak |
| uncertainty_cleared | false closure |

### 13.3 Required Uncertainty Tooltip

> The platform shows what limits interpretation, not what diagnosis it owns.

### 13.4 Uncertainty Badge Rule

> Uncertainty badges must replace diagnostic confidence, not disguise it.

---

## 14. Urgent Review Banner Semantics

### 14.1 Allowed Urgent Banner

Allowed banner type:

```yaml
urgent_review_banner:
  status: urgent_review_prompt_visible
  authority_effect: none
  triage_authority: none
  diagnostic_authority: none
  treatment_authority: none
```

Allowed banner text:

- “Urgent review prompt visible.”
- “Acute danger context may require urgent clinical assessment.”
- “The platform does not triage, diagnose, or treat.”
- “Clinical instability data are incomplete; urgent review prompt remains visible.”

### 14.2 Allowed Urgent Banner Triggers

- acute hypoxemia,
- rapid dyspnea progression,
- fever or systemic illness,
- hemoptysis or anemia,
- vascular concern,
- severe infection possible,
- immunosuppression with new findings,
- known malignancy with new findings,
- post-radiation new opacity,
- ICI exposure with new pulmonary findings,
- severe or worsening respiratory status.

### 14.3 Blocked Urgent Banner Text

- “Emergency confirmed.”
- “No urgent review needed.”
- “Safe for outpatient management.”
- “Treat immediately with...”
- “Acute exacerbation confirmed.”
- “Triage decision made.”

### 14.4 Dismissibility Rule

| Banner State | Dismissibility |
|---|---|
| active high-risk urgent prompt | not permanently dismissible |
| incomplete acute danger data | not permanently dismissible |
| informational urgent context | collapsible but visible in safety net |
| inactive urgent prompt | may be collapsed |

### 14.5 Urgent Banner Rule

> Urgent review banner is safety visibility, not triage authority.

---

## 15. MDD / Specialist Review Banner Semantics

### 15.1 Allowed Review Banner

Allowed banner type:

```yaml
MDD_review_banner:
  status: review_prompt_visible
  authority_effect: none
  MDD_replacement: not_allowed
```

Allowed text:

- “MDD / specialist review prompt visible.”
- “Integrated review remains relevant.”
- “The platform does not replace MDD or specialist judgment.”

### 15.2 Blocked Review Banner Text

- “MDD unnecessary.”
- “MDD completed by platform.”
- “Specialist review replaced.”
- “Final diagnosis ready.”
- “Consensus achieved.”

### 15.3 MDD Banner Rule

> Review banners may show why review is relevant; they may not replace review.

---

## 16. Blocked Output Banner Semantics

### 16.1 Allowed Blocked Output Banner

Allowed banner type:

```yaml
blocked_output_banner:
  status: blocked_output_guard_active
  blocked_category: diagnosis | exclusion | treatment | test_order | procedure | follow_up | triage | public_ready | patient_facing | clinical_review
  safe_reframe_required: true
```

Allowed text:

- “This output type is blocked.”
- “The platform can show reasoning prompts and limitations instead.”
- “Authority remains none.”
- “Safe reframe available.”

### 16.2 Blocked Blocked-Output Banner Text

- “Proceed anyway.”
- “Override guardrail.”
- “Generate without caveats.”
- “Hide authority envelope.”
- “Use as clinical report.”

### 16.3 Blocked Output Banner Rule

> A blocked-output banner must redirect to safe reasoning visibility, not provide a bypass.

---

## 17. Authority Envelope Footer Semantics

### 17.1 Required Footer

The authority footer must be locked visible.

```yaml
authority_envelope_footer:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
```

### 17.2 Allowed Footer Labels

- “Authority Envelope”
- “Platform Authority Boundary”
- “Diagnostic authority: none”
- “Treatment authority: none”
- “Public ready: false”
- “Platform-wide clinically reviewed: false”
- “Patient-facing use: not allowed”

### 17.3 Blocked Footer States

- hidden permanently,
- editable,
- dismissible permanently,
- public_ready toggled true,
- clinically_reviewed.platform_wide toggled true,
- patient_facing_use enabled,
- diagnostic_authority changed,
- treatment_authority changed.

### 17.4 Authority Footer Rule

> Authority limits must remain visible even when reasoning layers are collapsed.

---

## 18. Narrow Reviewed Scope Badge Semantics

### 18.1 Allowed Narrow Review Badge

Allowed:

```yaml
narrow_reviewed_scope_badge:
  reviewed_scope:
    - temporal_comparison_methodology
    - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
  platform_wide_clinically_reviewed: false
  authority_effect: none
```

Allowed text:

- “Narrow reviewed scope.”
- “Method/source-scope limited.”
- “Does not create platform-wide clinical review.”
- “Does not create diagnostic or treatment authority.”

### 18.2 Blocked Narrow Review Badge Text

- “Clinically validated platform.”
- “Clinically reviewed output.”
- “Diagnosis clinically confirmed.”
- “Public-ready.”
- “Deployment-ready.”

### 18.3 Narrow Review Rule

> Narrow reviewed scope is metadata, not clinical authority.

---

## 19. Audit Badge Semantics

### 19.1 Allowed Audit Badges

| Badge | Meaning |
|---|---|
| event_recorded | Interaction recorded |
| guardrail_triggered | Blocked output guardrail activated |
| source_viewed | Source badge inspected |
| evidence_supplied | Clinician supplied evidence |
| note_added | Clinician note added |
| safe_export_created | Governance-safe export created |

### 19.2 Blocked Audit Badges

| Badge | Why Blocked |
|---|---|
| diagnosis_validated | audit is not validation |
| treatment_authorized | audit is not treatment authority |
| clinically_validated | audit is not clinical validation |
| MDD_completed | audit is not MDD |
| public_ready | audit is not deployment |

### 19.3 Audit Badge Tooltip

> Audit trail records what was shown and blocked. It does not validate clinical correctness.

### 19.4 Audit Badge Rule

> Audit badges prove visibility events, not clinical truth.

---

## 20. Clinician Note Badge Semantics

### 20.1 Allowed Clinician Note Badges

| Badge | Meaning |
|---|---|
| clinician_authored_note | Human-authored note |
| clinician_supplied_evidence | Evidence supplied by clinician |
| MDD_preparation_note | Note for discussion preparation |
| local_workflow_note | Local clinician workflow note |

### 20.2 Blocked Clinician Note Badges

| Badge | Why Blocked |
|---|---|
| platform_conclusion | merges clinician note with platform reasoning |
| platform_diagnosis | platform authority leak |
| source_reviewed_claim | note is not source-reviewed by platform |
| clinically_validated_note | unsupported validation |
| public_ready_note | deployment leak |

### 20.3 Clinician Note Tooltip

> Clinician notes are separate from platform-generated reasoning and do not create platform authority.

### 20.4 Clinician Note Badge Rule

> Human-authored notes must remain visibly separate from platform reasoning.

---

## 21. Status Label Contract

### 21.1 Allowed Status Labels

| Status Label | Meaning |
|---|---|
| visible | Prompt or component visible |
| review-visible | Review prompt visible |
| source-limited | Source limitation present |
| missing | Evidence missing |
| unresolved | Boundary or uncertainty unresolved |
| not established | Closure not established |
| not diagnosed | Diagnosis not made by platform |
| not excluded | Exclusion not made by platform |
| blocked | Output category blocked |
| authority none | No authority created |
| clinician-authored | Human note |
| governance-safe | Non-authoritative export |

### 21.2 Blocked Status Labels

| Status Label | Why Blocked |
|---|---|
| confirmed | confirmation leak |
| ruled out | exclusion leak |
| diagnosed | diagnosis leak |
| excluded | exclusion leak |
| recommended | action authority leak |
| required | action authority leak |
| safe | unsafe reassurance |
| benign | diagnostic reassurance |
| validated | unsupported validation |
| public-ready | deployment leak |
| patient-ready | patient-facing leak |

Status label rule:

> UI status labels must describe reasoning state, not clinical conclusion.

---

## 22. Tooltip Contract

Every badge or banner must provide clarifying tooltip text.

Required tooltip categories:

| Badge/Banner | Required Tooltip Meaning |
|---|---|
| source badge | source status is not diagnosis |
| missing evidence badge | missing evidence is not exclusion |
| mimic badge | mimic visible is not mimic diagnosis |
| overlap badge | overlap is coexistence, not winner selection |
| uncertainty badge | confidence limiter, not diagnostic confidence |
| urgent banner | safety prompt, not triage |
| MDD banner | review prompt, not review replacement |
| authority footer | authority remains none |
| blocked output banner | safe reframe, no bypass |
| narrow reviewed scope badge | limited metadata, not platform-wide review |
| audit badge | records visibility, not correctness |
| clinician note badge | human note, not platform conclusion |

Tooltip rule:

> Tooltip text must clarify non-authority, not soften it.

---

## 23. Badge and Banner Display Priority

When badge or banner display competes, priority is:

1. urgent_review_banner,
2. blocked_output_banner,
3. authority_envelope_footer,
4. mimic_visibility_badges,
5. missing_evidence_badges,
6. source_limitation_badges,
7. uncertainty_badges,
8. overlap_badges,
9. MDD_review_banner,
10. source_status_badges,
11. narrow_reviewed_scope_badge,
12. audit_badges,
13. clinician_note_badges.

Display priority rule:

> Safety, blocked outputs, authority limits, mimics, missing evidence, source limits, and uncertainty must not be visually buried.

---

## 24. Density and Collapse Rules

The UI may collapse content to reduce clutter, but must preserve safety.

### 24.1 May Be Collapsed

- long source detail,
- audit event detail,
- clinician note detail,
- extended explanation,
- non-critical inactive prompt groups.

### 24.2 Must Remain Visible When Active

- authority envelope footer,
- urgent review banner,
- blocked output banner,
- active high-risk mimic badge,
- critical missing evidence badge,
- source limitation badge,
- uncertainty / confidence limiter summary,
- MDD prompt in cross-domain uncertainty.

### 24.3 Collapse Rule

> Collapse may reduce detail, but it must not hide safety-critical reasoning state.

---

## 25. Safe UI Copy Examples

Allowed copy examples:

- “UIP-like prompt visible; diagnosis not established.”
- “Exposure history missing; missing evidence is not exclusion.”
- “TB mimic visible; infection is not diagnosed or excluded.”
- “Source-limited claim; source status shown.”
- “Confidence limiter: prior CT unavailable.”
- “Urgent review prompt visible; platform does not triage.”
- “MDD review prompt visible; platform does not replace MDD.”
- “Output blocked: treatment recommendation not allowed.”
- “Authority envelope active.”

Blocked copy examples:

- “IPF confirmed.”
- “HP ruled out.”
- “TB excluded.”
- “Start steroids.”
- “Order PET/CT.”
- “Biopsy required.”
- “Follow up in 3 months.”
- “No urgent review needed.”
- “MDD unnecessary.”
- “Clinically validated.”
- “Patient-ready summary.”

---

## 26. Red-Team UI Semantics Scenarios

The following UI semantics failures must be blocked.

| Scenario | Required Block |
|---|---|
| UIP card uses checkmark icon meaning confirmed IPF | block diagnosis icon semantics |
| HP prompt muted after missing exposure history | block missing-evidence-as-exclusion |
| TB mimic badge crossed out after no microbiology entered | block exclusion semantics |
| Urgent banner can be dismissed permanently in acute worsening | block unsafe dismissibility |
| Source badge says clinically validated | block validation inflation |
| Treatment-heavy source badge shows treatment available | block treatment leak |
| PLC mimic badge uses cancer-confirmed language | block diagnosis leak |
| Confidence limiter panel shows IPF 90% | block diagnostic probability |
| Export removes authority envelope | block unsafe export |
| MDD banner says consensus achieved | block MDD replacement |
| Patient-ready badge appears | block patient-facing leak |
| Public-ready badge appears | block deployment leak |

---

## 27. Implementation Notes

The exact visual design may vary by product implementation.

However, every implementation must preserve:

- semantic non-authority,
- badge meaning,
- banner meaning,
- tooltip clarification,
- visual priority,
- no diagnosis color coding,
- no exclusion color coding,
- no treatment/action color coding,
- no diagnostic probability scale,
- no hidden authority envelope,
- no patient-facing readiness marker.

Implementation rule:

> Visual design is flexible; semantic authority boundaries are not.

---

## 28. Acceptance Criteria

v0.10.3 is accepted only if:

- UI safety states are defined,
- blocked UI states are defined,
- visual token semantics are defined,
- color/emphasis semantics are constrained,
- icon semantics are constrained,
- badge families are defined,
- blocked badge families are defined,
- source badge semantics are constrained,
- missing evidence badge semantics are constrained,
- mimic badge semantics are constrained,
- overlap badge semantics are constrained,
- uncertainty badge semantics are constrained,
- urgent review banner semantics are constrained,
- MDD review banner semantics are constrained,
- blocked output banner semantics are constrained,
- authority footer semantics are constrained,
- narrow reviewed scope badge semantics are constrained,
- audit badge semantics are constrained,
- clinician note badge semantics are constrained,
- allowed and blocked status labels are defined,
- tooltip contract is defined,
- display priority is defined,
- collapse rules preserve safety,
- red-team UI semantic failures are blocked,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

---

## 29. Next Step

The next recommended step is:

- v0.10.4 — Clinician Workspace Example Screens / Safe UI Flow Templates

v0.10.4 should define safe example UI flows for:

- UIP-like prompt with missing exposure history,
- fibrotic HP vs UIP overlap,
- granulomatous sarcoid-like pattern with missing microbiology and beryllium context,
- post-radiation new GGO with infection/recurrence/ICI overlap,
- ICI exposure with FDG-avid nodes,
- known malignancy with septal thickening / PLC mimic,
- acute danger over chronic ILD,
- blocked diagnosis request,
- blocked treatment request,
- blocked test/procedure request,
- safe MDD preparation export.

v0.10.4 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 30. Governance Statement

This UI safety state model defines safe badge, banner, label, and visual semantics.

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

The workspace remains a reasoning visibility surface, not a decision surface.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.3:

> “UI semantics must make uncertainty, source limits, missing evidence, mimics, and authority boundaries visible without visually implying diagnosis, exclusion, treatment, or safety clearance.”