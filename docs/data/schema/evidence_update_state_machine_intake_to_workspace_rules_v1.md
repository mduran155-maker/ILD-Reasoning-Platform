# ILD Reasoning Platform — Evidence Update State Machine / Intake-to-Workspace Propagation Rules v1

Version: v0.11.3  
Status: evidence_update_state_machine_intake_to_workspace_rules  
Scope: Evidence update state machine and safe propagation from intake fields to clinician workspace  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the evidence update state machine for v0.11 — Evidence Intake / Clinician-Supplied Case Context Contract.

It follows:

- `docs/navigation/evidence_intake_case_context_entry_gate_v1.md`
- `docs/data/schema/evidence_intake_field_schema_provided_vs_inferred_boundary_v1.md`
- `docs/data/schema/structured_intake_domain_schema_case_context_fields_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_10.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

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

Its purpose is to define how evidence intake fields safely transition between states and propagate updates to the clinician review workspace.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.11 rule remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

For v0.11.3:

> “Evidence update may refresh visibility, missingness, confidence limiters, prompts, overlap, mimics, source status, review prompts, and audit trail, but it must not refresh the platform into clinical authority.”

---

## 2. Global State Machine Contract

Every state transition must preserve:

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
| replacement_of_specialist_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

No state transition may create:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment recommendation,
- test order,
- procedure decision,
- follow-up interval,
- triage decision,
- public readiness,
- patient-facing output,
- platform-wide clinical review.

---

## 3. State Machine Principle

Evidence update is allowed to change:

- field state,
- missing evidence visibility,
- confidence limiter status,
- affected prompt visibility,
- overlap visibility,
- mimic visibility,
- urgent review prompt visibility,
- MDD review prompt visibility,
- source status linkage,
- workspace component refresh status,
- audit trail.

Evidence update is not allowed to change:

- diagnostic authority,
- treatment authority,
- test-order authority,
- procedure authority,
- follow-up authority,
- triage authority,
- public readiness,
- patient-facing status,
- platform-wide clinical review.

State machine rule:

> Evidence state may move; authority state may not.

---

## 4. Core Evidence States

Allowed evidence states:

| State ID | State Name | Meaning |
|---|---|---|
| V11_STATE_001 | not_provided | Field is missing or undocumented |
| V11_STATE_002 | missing_evidence_visible | Missing field remains visible as interpretation limiter |
| V11_STATE_003 | provided_fact | Field was explicitly supplied before reasoning |
| V11_STATE_004 | clinician_supplied_evidence | Field was supplied by clinician during workspace interaction |
| V11_STATE_005 | report_supplied_fact | Field was supplied by report text |
| V11_STATE_006 | uploaded_record_supplied_fact | Field was supplied by uploaded record |
| V11_STATE_007 | source_context_supplied_fact | Field was supplied by source-governance context |
| V11_STATE_008 | source_limited | Field or claim has source limitation |
| V11_STATE_009 | confidence_limiter_active | Field limits interpretation |
| V11_STATE_010 | confidence_limiter_updated | Limiter was updated after evidence change |
| V11_STATE_011 | confidence_limiter_resolved_by_supplied_evidence | Limiter reduced because evidence was supplied |
| V11_STATE_012 | prompt_visibility_updated | A reasoning prompt changed visibility state |
| V11_STATE_013 | workspace_component_refresh_pending | Workspace component must refresh |
| V11_STATE_014 | workspace_component_refreshed | Workspace component updated |
| V11_STATE_015 | evidence_update_audited | State change recorded |
| V11_STATE_016 | authority_effect_none | No authority created |

Blocked evidence states:

| Blocked State | Why Blocked |
|---|---|
| diagnosis_created | diagnostic authority leak |
| exclusion_created | exclusion authority leak |
| mimic_excluded | unsafe mimic closure |
| treatment_created | treatment authority leak |
| test_order_created | test-order authority leak |
| procedure_decision_created | procedure authority leak |
| follow_up_created | follow-up authority leak |
| triage_created | triage authority leak |
| public_ready_created | deployment leak |
| patient_facing_created | patient-facing use leak |
| platform_wide_clinical_review_created | unsupported clinical review claim |
| MDD_replaced | review replacement |
| urgent_review_replaced | urgent review replacement |

---

## 5. Evidence Update Event Types

Allowed update events:

| Event ID | Event Type | Meaning |
|---|---|---|
| V11_EVENT_001 | evidence_field_initialized | Field created in intake schema |
| V11_EVENT_002 | evidence_marked_not_provided | Field explicitly missing |
| V11_EVENT_003 | missing_evidence_badge_created | Missing evidence made visible |
| V11_EVENT_004 | clinician_supplies_evidence | Clinician supplies field value |
| V11_EVENT_005 | report_supplies_evidence | Report supplies field value |
| V11_EVENT_006 | uploaded_record_supplies_evidence | Uploaded record supplies field value |
| V11_EVENT_007 | source_context_links_evidence | Source status linked |
| V11_EVENT_008 | confidence_limiter_created | Limiter created |
| V11_EVENT_009 | confidence_limiter_updated | Limiter updated |
| V11_EVENT_010 | confidence_limiter_resolved | Limiter reduced or resolved by supplied evidence |
| V11_EVENT_011 | affected_prompt_visibility_updated | Prompt visibility updated |
| V11_EVENT_012 | workspace_component_refresh_requested | Workspace refresh requested |
| V11_EVENT_013 | workspace_component_refreshed | Workspace refresh completed |
| V11_EVENT_014 | guardrail_blocks_unsafe_transition | Unsafe transition blocked |
| V11_EVENT_015 | evidence_update_audit_recorded | Audit record created |

Blocked update events:

| Blocked Event | Why Blocked |
|---|---|
| diagnosis_confirmed_from_evidence | diagnosis leak |
| disease_excluded_from_missing_evidence | exclusion leak |
| treatment_recommended_from_evidence | treatment leak |
| test_order_generated_from_evidence | test-order leak |
| procedure_recommended_from_evidence | procedure leak |
| follow_up_scheduled_from_evidence | follow-up leak |
| triage_decision_from_evidence | triage leak |
| MDD_conclusion_generated | MDD replacement |
| patient_summary_generated_from_intake | patient-facing leak |
| public_ready_enabled_from_intake | deployment leak |

---

## 6. Primary State Transition Matrix

### 6.1 Allowed Transitions

| From State | Event | To State | Required Guard |
|---|---|---|---|
| field_initialized | evidence_marked_not_provided | not_provided | inference blocked |
| not_provided | missing_evidence_badge_created | missing_evidence_visible | exclusion effect none |
| not_provided | clinician_supplies_evidence | clinician_supplied_evidence | audit required |
| not_provided | report_supplies_evidence | report_supplied_fact | source provenance required |
| not_provided | uploaded_record_supplies_evidence | uploaded_record_supplied_fact | source provenance required |
| provided_fact | source_context_links_evidence | source_limited or source_linked | source status visible |
| clinician_supplied_evidence | confidence_limiter_updated | confidence_limiter_updated | diagnostic confidence blocked |
| clinician_supplied_evidence | affected_prompt_visibility_updated | prompt_visibility_updated | authority effect none |
| prompt_visibility_updated | workspace_component_refresh_requested | workspace_component_refresh_pending | no clinical closure |
| workspace_component_refresh_pending | workspace_component_refreshed | workspace_component_refreshed | authority envelope preserved |
| any_allowed_state | evidence_update_audit_recorded | evidence_update_audited | audit not validation |

### 6.2 Blocked Transitions

| From State | Blocked To State | Why Blocked |
|---|---|---|
| clinician_supplied_evidence | diagnosis_created | supplied evidence is not diagnosis |
| clinician_supplied_evidence | exclusion_created | supplied evidence is not exclusion |
| clinician_supplied_evidence | treatment_created | supplied evidence is not treatment |
| clinician_supplied_evidence | test_order_created | supplied evidence is not order |
| clinician_supplied_evidence | procedure_decision_created | supplied evidence is not procedure decision |
| clinician_supplied_evidence | follow_up_created | supplied evidence is not follow-up |
| clinician_supplied_evidence | triage_created | supplied evidence is not triage |
| not_provided | disease_excluded | missing evidence is not exclusion |
| missing_evidence_visible | mimic_excluded | missing evidence cannot erase mimic |
| source_limited | clinically_validated | source limitation is not validation |
| confidence_limiter_active | diagnostic_confidence_created | limiter is not confidence score |
| prompt_visibility_updated | final_diagnosis_selected | prompt visibility is not diagnosis |
| workspace_component_refreshed | decision_surface_enabled | workspace remains reasoning visibility surface |
| evidence_update_audited | clinical_correctness_validated | audit is not validation |

State transition rule:

> Every blocked transition must fail closed and record a guardrail audit event.

---

## 7. Evidence Update Pipeline

Every evidence update must pass through the following pipeline.

```yaml
evidence_update_pipeline:
  step_1_receive_update:
    input: field_id + value + value_source
    required: provenance

  step_2_classify_field_state:
    allowed_states:
      - provided_fact
      - not_provided
      - clinician_supplied_evidence
      - report_supplied_fact
      - uploaded_record_supplied_fact
      - source_context_supplied_fact
      - source_limited

  step_3_check_inference_boundary:
    inferred_fact_blocked: true
    missing_unsupplied_facts_remain_missing: true

  step_4_update_missing_evidence:
    missing_badge_created_or_removed_or_updated: true
    exclusion_effect: none

  step_5_update_confidence_limiters:
    diagnostic_confidence_created: false
    probability_created: false

  step_6_update_prompt_visibility:
    affected_prompts_updated: true
    diagnosis_created: false

  step_7_refresh_workspace_components:
    component_refresh_requested: true
    authority_envelope_preserved: true

  step_8_record_audit:
    audit_required: true
    authority_effect: none
```

Pipeline rule:

> Every update must pass through provenance, inference boundary, missing evidence, confidence limiter, prompt visibility, workspace refresh, and audit gates.

---

## 8. Missing Evidence Badge Update Rules

### 8.1 Badge Creation

A missing evidence badge is created when:

- field_state = not_provided,
- field is relevant to active or possible prompt,
- missingness limits interpretation,
- missingness prevents closure,
- missingness preserves mimic or overlap visibility.

Allowed badge creation examples:

| Missing Field | Badge |
|---|---|
| prior imaging not supplied | prior_CT_missing |
| exposure not supplied | exposure_history_missing |
| microbiology not supplied | microbiology_missing |
| beryllium context not supplied | beryllium_context_missing |
| CTD/SARD context not supplied | autoimmune_context_missing |
| MDD status not supplied | MDD_status_missing |

### 8.2 Badge Update

A missing evidence badge may update when:

- clinician supplies partial evidence,
- clinician supplies complete evidence,
- report supplies context,
- uploaded record supplies context,
- source limitation is discovered,
- conflicting evidence is supplied.

Allowed badge update states:

- missing,
- partially_supplied,
- supplied_by_clinician,
- source_limited,
- conflicting,
- no_longer_missing_but_still_limited.

### 8.3 Badge Removal

A missing evidence badge may be removed from active missing list only if:

- evidence is explicitly supplied,
- provenance is recorded,
- affected prompts are updated,
- confidence limiters are updated,
- audit event is recorded.

Even after badge removal, the field must not create diagnosis or exclusion.

### 8.4 Blocked Badge Behavior

A missing evidence badge must not:

- become disease excluded,
- become mimic excluded,
- become safe/benign,
- suppress prompt visibility without evidence,
- disappear without audit,
- remove source limitation,
- remove uncertainty automatically.

Missing evidence badge rule:

> A missing badge can move to supplied or limited; it cannot move to excluded.

---

## 9. Confidence Limiter Update Rules

### 9.1 Limiter Creation

A confidence limiter is created when a field is:

- missing,
- incomplete,
- source-limited,
- conflicting,
- not temporally comparable,
- not integrated with MDD or specialist review,
- lacking microbiology/pathology/clinical context where relevant.

### 9.2 Limiter Update

A confidence limiter may update to:

- active,
- reduced,
- resolved_by_supplied_evidence,
- replaced_by_new_limiter,
- source_limited,
- conflicting_evidence_present.

### 9.3 Limiter Resolution

A confidence limiter may be resolved only if:

- relevant evidence is explicitly supplied,
- provenance is recorded,
- source status is updated where relevant,
- affected prompts are updated,
- audit event is recorded.

### 9.4 Blocked Limiter Behavior

A confidence limiter must not become:

- diagnostic confidence score,
- disease probability,
- final diagnosis rank,
- exclusion score,
- safety clearance,
- treatment threshold.

Confidence limiter rule:

> Confidence limiters explain what changed in interpretation limits; they do not calculate diagnostic certainty.

---

## 10. Prompt Visibility Propagation Rules

Evidence updates may propagate to prompt visibility.

Allowed prompt visibility states:

| Prompt State | Meaning |
|---|---|
| prompt_visible | Prompt remains visible |
| prompt_not_triggered | Prompt not triggered by supplied evidence |
| prompt_source_limited | Prompt visible but source-limited |
| prompt_missing_evidence_limited | Prompt visible but limited by missing evidence |
| prompt_updated | Prompt visibility changed after evidence update |
| prompt_conflict_visible | Conflicting evidence preserved |
| prompt_deferred_to_review | Prompt requires MDD/specialist review visibility |

Blocked prompt visibility states:

| Blocked State | Why Blocked |
|---|---|
| diagnosis_confirmed | prompt is not diagnosis |
| disease_excluded | prompt is not exclusion |
| mimic_excluded | unsafe closure |
| treatment_triggered | treatment authority leak |
| test_order_triggered | test-order leak |
| procedure_triggered | procedure leak |
| follow_up_triggered | follow-up leak |
| triage_triggered | triage leak |

Prompt propagation rule:

> Prompt visibility may change; clinical truth status may not.

---

## 11. Workspace Component Refresh Rules

Evidence updates may refresh v0.10 workspace components.

Allowed component refresh targets:

| Intake Update | Workspace Components That May Refresh |
|---|---|
| prior imaging supplied | temporal_comparison_panel; uncertainty_panel; audit_trail |
| exposure supplied | missing_evidence_panel; fibrotic_HP_prompt; overlap_panel; uncertainty_panel |
| occupational history supplied | mimic_visibility_panel; missing_evidence_panel; source_status_badges |
| beryllium context supplied | mimic_visibility_panel; overlap_panel; MDD_review_panel |
| CTD/SARD context supplied | differential_prompt_cards; overlap_panel; MDD_review_panel |
| medication history supplied | mimic_visibility_panel; uncertainty_panel; source_status_badges |
| radiation context supplied | mimic_visibility_panel; overlap_panel; urgent_review_banner where relevant |
| ICI context supplied | mimic_visibility_panel; overlap_panel; MDD_review_panel |
| oncology context supplied | mimic_visibility_panel; overlap_panel; source_status_badges |
| microbiology supplied | mimic_visibility_panel; missing_evidence_panel; uncertainty_panel |
| pathology supplied | layer_cards; mimic_visibility_panel; overlap_panel; MDD_review_panel |
| aspiration risk supplied | mimic_visibility_panel; overlap_panel |
| urgent clinical status supplied | urgent_review_banner; mimic_visibility_panel; uncertainty_panel |
| MDD status supplied | MDD_review_panel; audit_trail |

Blocked component refresh outputs:

- final diagnosis panel,
- treatment recommendation panel,
- order next test button,
- biopsy required banner,
- follow-up scheduler,
- triage/disposition banner,
- patient summary export,
- public-ready toggle,
- clinically validated badge.

Component refresh rule:

> Workspace refresh may rearrange visibility, but it cannot add decision controls.

---

## 12. Domain-Specific Propagation Rules

### 12.1 Exposure Update

Allowed propagation:

```yaml
exposure_history_context:
  from: not_provided
  to: clinician_supplied_evidence
  updates:
    - exposure_history_missing badge updated
    - fibrotic_HP_prompt visibility updated
    - UIP_HP_overlap visibility updated
    - confidence_limiter updated
    - audit recorded
  authority_effect: none
```

Blocked propagation:

- HP diagnosis,
- HP exclusion,
- antigen causation,
- treatment or avoidance recommendation.

---

### 12.2 Prior Imaging Update

Allowed propagation:

```yaml
prior_imaging_context:
  from: not_provided
  to: clinician_supplied_evidence
  updates:
    - temporal_comparison_panel refreshed
    - prior_CT_missing badge updated
    - temporal confidence limiter updated
    - acute_vs_chronic_context updated where relevant
    - audit recorded
  authority_effect: none
```

Blocked propagation:

- PPF diagnosis,
- acute exacerbation diagnosis,
- stability proves benignity,
- progression diagnosis.

---

### 12.3 Microbiology Update

Allowed propagation:

```yaml
microbiology_context:
  from: not_provided
  to: clinician_supplied_evidence
  updates:
    - microbiology_missing badge updated
    - infection_mimic_prompt visibility updated
    - TB/NTM/fungal mimic visibility updated
    - OP_vs_infection overlap updated
    - confidence_limiter updated
    - audit recorded
  authority_effect: none
```

Blocked propagation:

- infection diagnosis,
- infection exclusion,
- TB excluded,
- antimicrobial recommendation,
- antifungal recommendation.

---

### 12.4 Pathology Update

Allowed propagation:

```yaml
pathology_context:
  from: not_provided
  to: clinician_supplied_evidence
  updates:
    - pathology_context_missing badge updated
    - granulomatous_prompt visibility updated where relevant
    - sarcoid_like_prompt visibility updated where relevant
    - infection/beryllium/malignancy mimic visibility preserved
    - MDD_review_panel refreshed
    - audit recorded
  authority_effect: none
```

Blocked propagation:

- sarcoidosis diagnosis from granulomas alone,
- IPF diagnosis from UIP pathology alone,
- infection exclusion,
- biopsy recommendation,
- standalone pathology diagnosis.

---

### 12.5 Oncology Update

Allowed propagation:

```yaml
oncology_context:
  from: not_provided
  to: clinician_supplied_evidence
  updates:
    - malignancy_status_missing badge updated
    - PLC_malignancy_mimic visibility updated
    - ICI_SLR_vs_malignancy overlap updated where relevant
    - PET_CT ambiguity limiter updated where relevant
    - MDD_review_panel refreshed
    - audit recorded
  authority_effect: none
```

Blocked propagation:

- recurrence diagnosis,
- PLC diagnosis,
- malignancy exclusion,
- PET/CT interpretation authority,
- oncology management recommendation.

---

### 12.6 Urgent Clinical Status Update

Allowed propagation:

```yaml
urgent_clinical_status_context:
  from: not_provided
  to: clinician_supplied_evidence
  updates:
    - urgent_clinical_status_missing badge updated
    - urgent_review_banner may become visible
    - acute_overlay_prompt visibility updated
    - uncertainty_panel refreshed
    - audit recorded
  authority_effect: none
```

Blocked propagation:

- triage decision,
- outpatient safety,
- emergency disposition,
- treatment recommendation,
- acute exacerbation diagnosis.

---

## 13. Guardrail-Failed Transition Rules

When an unsafe state transition is attempted, the platform must:

1. block transition,
2. preserve previous safe state,
3. show guardrail message,
4. reframe to safe visibility update if possible,
5. preserve authority envelope,
6. record audit event.

Example:

```yaml
attempted_transition:
  from: clinician_supplied_evidence
  to: diagnosis_created

guardrail_response:
  transition_allowed: false
  previous_state_preserved: true
  safe_reframe: prompt_visibility_updated
  authority_effect: none
  audit_event: guardrail_blocks_unsafe_transition
```

Guardrail rule:

> Unsafe transitions must fail closed, not degrade silently.

---

## 14. Reasoning Visibility Rerun Rules

After evidence update, the platform may rerun reasoning visibility.

Allowed rerun outputs:

- updated visible prompts,
- updated missing evidence badges,
- updated confidence limiters,
- updated source status links,
- updated mimic visibility,
- updated overlap visibility,
- updated urgent review prompt visibility,
- updated MDD prompt visibility,
- updated audit trail.

Blocked rerun outputs:

- final diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment recommendation,
- test order,
- procedure recommendation,
- follow-up schedule,
- triage decision,
- patient-facing report,
- public-ready claim,
- platform-wide clinical review.

Rerun rule:

> Rerun means refresh reasoning visibility, not recompute clinical truth.

---

## 15. Conflict and Partial Evidence Rules

Evidence may be incomplete or conflicting.

Allowed conflict states:

- partial_evidence_supplied,
- conflicting_evidence_present,
- source_limited,
- still_missing_context,
- confidence_limiter_updated,
- overlap_visible,
- MDD_review_prompt_visible.

Blocked conflict resolution:

- choose winner diagnosis,
- suppress conflict,
- hide mimic,
- ignore missing evidence,
- declare evidence sufficient for treatment,
- declare no review needed.

Conflict rule:

> Partial or conflicting evidence must increase visibility of uncertainty, not force closure.

---

## 16. Rollback and Correction Rules

Clinician-supplied evidence may be corrected.

Allowed correction behavior:

- mark previous value as superseded,
- preserve audit record,
- record correction event,
- update missing evidence status,
- update confidence limiter,
- rerun reasoning visibility,
- preserve authority effect none.

Blocked correction behavior:

- delete audit trail silently,
- treat correction as clinical validation,
- create diagnosis from corrected value,
- create exclusion from corrected value,
- hide previous limitation without record.

Correction rule:

> Evidence correction updates provenance and visibility; it does not validate correctness.

---

## 17. Source Status Propagation Rules

If an evidence field is source-linked, the source status must propagate with it.

Required propagation:

- source_id,
- source_role_class,
- claim_mapping_status,
- source_limitations,
- treatment_heavy_warning where relevant,
- diagnostic_performance_warning where relevant,
- case_example_only_warning where relevant,
- authority_effect: none.

Blocked source propagation:

- source-linked means clinically validated,
- source-linked means diagnosis confirmed,
- source-linked means treatment supported,
- source-linked means test order supported,
- source-linked means public ready.

Source propagation rule:

> Source status travels with the field but never becomes authority.

---

## 18. Audit Event Requirements

Every evidence update and workspace propagation must create audit events.

Required audit events:

| Event | Required |
|---|---|
| evidence field updated | yes |
| missing evidence badge created/updated/removed | yes |
| confidence limiter created/updated/resolved | yes |
| affected prompt visibility updated | yes |
| workspace component refresh requested | yes |
| workspace component refreshed | yes |
| unsafe transition blocked | yes |
| clinician evidence corrected | yes |
| source status propagated | yes |

Every audit event must include:

```yaml
authority_effect: none
diagnosis_created: false
exclusion_created: false
treatment_created: false
test_order_created: false
procedure_decision_created: false
follow_up_created: false
triage_created: false
public_ready_created: false
patient_facing_created: false
platform_wide_clinical_review_created: false
```

Audit rule:

> Audit records state movement; it does not certify clinical truth.

---

## 19. Intake-to-Workspace Propagation Acceptance Tests

### TEST_001 — Missing Exposure Supplied

Input:

```yaml
field: exposure_history_context
previous_state: not_provided
new_state: clinician_supplied_evidence
```

Expected:

- exposure missing badge updated,
- HP prompt visibility updated,
- HP/UIP overlap refreshed,
- confidence limiter updated,
- audit recorded,
- no HP diagnosis,
- no IPF diagnosis,
- no exposure causation.

---

### TEST_002 — Microbiology Still Missing

Input:

```yaml
field: microbiology_context
state: not_provided
```

Expected:

- microbiology missing badge visible,
- infection mimic remains visible where relevant,
- confidence limiter active,
- no infection exclusion,
- no antimicrobial recommendation.

---

### TEST_003 — Granulomas Supplied

Input:

```yaml
field: pathology_context
value: nonnecrotizing_granulomas_reported
```

Expected:

- granulomatous prompt visible,
- sarcoid-like prompt visible,
- infection/beryllium/malignancy mimics preserved,
- MDD review prompt visible where relevant,
- no sarcoidosis diagnosis.

---

### TEST_004 — Urgent Status Supplied

Input:

```yaml
field: urgent_clinical_status_context
value: rapid_worsening_or_hypoxemia_supplied
```

Expected:

- urgent review banner visible,
- acute overlay prompt visible,
- no triage,
- no treatment,
- no acute exacerbation diagnosis.

---

### TEST_005 — Source-Linked Claim Updated

Input:

```yaml
field: UIP_category_context
source_status: claim_mapped
```

Expected:

- source status badge visible,
- source limitations visible,
- UIP-like prompt may be visible,
- no IPF diagnosis,
- no platform-wide clinical review.

---

## 20. Red-Team State Machine Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| Exposure supplied and HP is diagnosed | block exposure-to-diagnosis |
| Exposure missing and HP is excluded | block missing-as-exclusion |
| Prior CT supplied and PPF is diagnosed | block temporal-to-diagnosis |
| Microbiology missing and TB is excluded | block missing microbiology exclusion |
| Nonnecrotizing granulomas supplied and sarcoidosis is confirmed | block pathology-alone diagnosis |
| Radiation history supplied and steroids are recommended | block treatment authority |
| ICI exposure supplied and immunotherapy hold is suggested | block oncology management |
| Oncology context supplied and PLC is confirmed | block oncology diagnosis |
| Urgent status supplied and outpatient safety is declared | block triage |
| MDD status supplied and platform finalizes diagnosis | block MDD replacement |
| Source mapped and platform claims clinical validation | block source-to-validation |
| Audit recorded and platform claims correctness | block audit-to-validation |

---

## 21. v0.11.3 Acceptance Criteria

v0.11.3 is accepted only if:

- core evidence states are defined,
- evidence update events are defined,
- allowed state transitions are defined,
- blocked state transitions are defined,
- update pipeline is defined,
- missing evidence badge update rules are defined,
- confidence limiter update rules are defined,
- prompt visibility propagation rules are defined,
- workspace component refresh rules are defined,
- domain-specific propagation rules are defined,
- unsafe transitions fail closed,
- reasoning visibility rerun is constrained,
- partial/conflicting evidence rules are defined,
- rollback/correction rules are defined,
- source status propagation rules are defined,
- audit requirements are defined,
- acceptance tests are defined,
- red-team scenarios are blocked,
- no automatic diagnosis from supplied evidence,
- no exclusion from missing evidence,
- no treatment authority,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no public readiness,
- no patient-facing use,
- no platform-wide clinical review.

---

## 22. Next Step

The next recommended step is:

- v0.11.4 — Evidence Intake Validation Checklist / Intake Safety Gate

v0.11.4 should verify:

- v0.11.0 entry gate exists,
- v0.11.1 field schema exists,
- v0.11.2 domain schema exists,
- v0.11.3 state machine exists,
- provided-vs-inferred boundary is preserved,
- missing evidence cannot become exclusion,
- supplied evidence cannot become diagnosis,
- workspace propagation remains non-authoritative,
- evidence update audit remains non-validating,
- source status remains non-authoritative,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

v0.11.4 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 23. Governance Statement

This evidence update state machine defines safe propagation from intake fields to the clinician workspace.

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

Evidence update remains a visibility update, not a clinical decision update.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.11 rule remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

For v0.11.3:

> “Evidence update may refresh visibility, missingness, confidence limiters, prompts, overlap, mimics, source status, review prompts, and audit trail, but it must not refresh the platform into clinical authority.”