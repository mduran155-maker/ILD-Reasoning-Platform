# ILD Reasoning Platform — Session Binding Propagation / Object Integrity Rules v1

Version: v0.12.3  
Status: session_binding_propagation_object_integrity_rules  
Scope: Binding propagation, object integrity, stale/orphan prevention, rehydration safety, audit chain consistency, and authority-envelope preservation  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines session binding propagation and object integrity rules for v0.12 — Case Assembly / Reasoning Session Object Contract.

It follows:

- `docs/navigation/case_assembly_reasoning_session_entry_gate_v1.md`
- `docs/data/schema/reasoning_session_object_schema_v1.md`
- `docs/data/schema/case_snapshot_revision_history_contract_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_11.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
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

Its purpose is to ensure that session bindings remain synchronized, non-orphaned, non-stale, audit-linked, snapshot-safe, rehydration-safe, and authority-neutral.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.3:

> “A reasoning session is valid only if every binding can be traced, refreshed, audited, rehydrated, and exported without losing authority boundaries or creating decision state.”

---

## 2. Global Object Integrity Contract

Every binding propagation and object integrity rule must preserve:

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

No propagation event, binding refresh, snapshot rehydration, integrity repair, export, audit chain update, or session revision may override the authority envelope.

---

## 3. Object Integrity Principle

The reasoning session object is a graph of governed bindings.

The graph may contain:

- intake field bindings,
- workspace state bindings,
- structured output bindings,
- source status bindings,
- missing evidence bindings,
- confidence limiter bindings,
- mimic visibility bindings,
- overlap bindings,
- review prompt bindings,
- authority envelope binding,
- audit event chain,
- no-decision object.

The graph must not contain:

- final diagnosis binding,
- disease exclusion binding,
- mimic exclusion binding,
- treatment plan binding,
- test order binding,
- procedure decision binding,
- follow-up schedule binding,
- triage decision binding,
- patient-facing binding,
- public-ready binding,
- platform-wide clinical validation binding.

Object integrity rule:

> A session graph may connect reasoning state; it must not connect clinical authority.

---

## 4. Binding Graph Registry

The following binding families are governed by v0.12.3.

| Binding Family ID | Binding Family | Required Integrity |
|---|---|---|
| V12_BINDING_001 | intake_field_binding | must link to session, snapshot, prompt/audit where relevant |
| V12_BINDING_002 | workspace_state_binding | must link to session, component, snapshot, audit |
| V12_BINDING_003 | structured_output_binding | must link to v0.9 layer, session, snapshot, audit |
| V12_BINDING_004 | source_status_binding | must link to claim/source and dependent fields/layers |
| V12_BINDING_005 | missing_evidence_binding | must link to missing field, affected prompts, limiter, audit |
| V12_BINDING_006 | confidence_limiter_binding | must link to missing/source/conflict cause and prompts |
| V12_BINDING_007 | mimic_visibility_binding | must link to relevant intake fields, missing evidence, overlap |
| V12_BINDING_008 | overlap_binding | must link to involved prompts and unresolved boundary |
| V12_BINDING_009 | review_prompt_binding | must link to urgent/MDD/specialist prompt and evidence cause |
| V12_BINDING_010 | authority_envelope_binding | must exist in every session, snapshot, export |
| V12_BINDING_011 | audit_event_chain | must link every mutation and guardrail event |
| V12_BINDING_012 | no_decision_object | must exist in every session and snapshot |

---

## 5. Canonical Binding Object

Every binding must follow a common integrity structure.

```yaml
canonical_binding:
  binding_id: string
  binding_family: string
  session_id: string
  current_snapshot_id: string
  created_at: implementation_defined
  updated_at: implementation_defined
  binding_state:
    - active
    - inactive
    - superseded
    - corrected
    - source_limited
    - stale_blocked
    - orphan_blocked

  upstream_refs: list
  downstream_refs: list
  snapshot_refs: list
  audit_event_refs: list

  stale_status:
    is_stale: false
    stale_reason: null

  orphan_status:
    is_orphan: false
    orphan_reason: null

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

Canonical binding rule:

> Every binding must know where it came from, where it propagates, which snapshot contains it, and which audit event records it.

---

## 6. Binding Directionality Rules

### 6.1 Allowed Directionality

Allowed propagation direction:

```yaml
allowed_directionality:
  intake_field_binding:
    may_feed:
      - missing_evidence_binding
      - confidence_limiter_binding
      - mimic_visibility_binding
      - overlap_binding
      - structured_output_binding
      - workspace_state_binding
      - review_prompt_binding
      - audit_event_chain

  source_status_binding:
    may_feed:
      - intake_field_binding
      - structured_output_binding
      - workspace_state_binding
      - confidence_limiter_binding
      - audit_event_chain

  missing_evidence_binding:
    may_feed:
      - confidence_limiter_binding
      - mimic_visibility_binding
      - overlap_binding
      - structured_output_binding
      - workspace_state_binding
      - review_prompt_binding
      - audit_event_chain

  confidence_limiter_binding:
    may_feed:
      - uncertainty_layer
      - workspace_state_binding
      - structured_output_binding
      - audit_event_chain

  mimic_visibility_binding:
    may_feed:
      - high_risk_mimic_layer
      - overlap_binding
      - workspace_state_binding
      - review_prompt_binding
      - audit_event_chain

  overlap_binding:
    may_feed:
      - overlap_layer
      - uncertainty_layer
      - workspace_state_binding
      - review_prompt_binding
      - audit_event_chain

  review_prompt_binding:
    may_feed:
      - urgent_review_prompt_layer
      - MDD_review_prompt_layer
      - workspace_state_binding
      - audit_event_chain
```

### 6.2 Blocked Directionality

Blocked propagation direction:

| From | To | Why Blocked |
|---|---|---|
| intake_field_binding | final_diagnosis | diagnosis leak |
| missing_evidence_binding | disease_exclusion | missing-as-exclusion leak |
| mimic_visibility_binding | mimic_diagnosis | mimic diagnosis leak |
| mimic_visibility_binding | mimic_exclusion | unsafe closure |
| confidence_limiter_binding | disease_probability | probability leak |
| source_status_binding | clinical_validation | source-to-validation leak |
| review_prompt_binding | MDD_replacement | review replacement |
| urgent_review_binding | triage_decision | triage leak |
| workspace_state_binding | treatment_panel | decision-control leak |
| audit_event_chain | clinical_correctness | audit-to-validation leak |

Directionality rule:

> Bindings may propagate visibility and limitation; they may not propagate authority.

---

## 7. Orphan Binding Prevention

An orphan binding is a binding that has lost required upstream or downstream references.

### 7.1 Orphan Conditions

A binding is invalid if:

- it has no session_id,
- it has no snapshot reference,
- it has no audit reference after mutation,
- it references a missing upstream field,
- it references a missing workspace component,
- it references a deleted source status without supersession,
- it references a missing authority envelope,
- it references no-decision object incorrectly or not at all,
- it exists outside the session graph.

### 7.2 Required Orphan Guard

```yaml
orphan_guard:
  session_ref_required: true
  snapshot_ref_required: true
  audit_ref_required_after_mutation: true
  authority_envelope_ref_required: true
  no_decision_object_ref_required: true
  orphan_binding_allowed: false
```

### 7.3 Orphan Repair

Allowed repair actions:

- relink binding to current session,
- relink binding to current snapshot,
- attach missing audit event,
- mark old binding superseded,
- create corrected binding,
- create correction audit event,
- preserve authority_effect: none.

Blocked repair actions:

- silently delete orphan binding,
- silently attach to diagnosis object,
- use orphan repair to create clinical validation,
- remove authority envelope,
- remove no-decision object.

Orphan prevention rule:

> Orphan bindings must fail closed and require traceable repair.

---

## 8. Stale Binding Prevention

A stale binding is a binding that no longer matches the current snapshot or upstream evidence state.

### 8.1 Stale Conditions

A binding becomes stale when:

- upstream intake field changes,
- source status changes,
- missing evidence state changes,
- confidence limiter changes,
- prompt visibility changes,
- workspace component refreshes,
- snapshot supersedes prior state,
- correction is recorded,
- rollback is performed.

### 8.2 Stale Binding States

Allowed stale handling states:

- stale_detected,
- stale_blocked,
- stale_superseded,
- stale_corrected,
- refresh_required,
- refresh_completed,
- audit_recorded.

Blocked stale handling states:

- stale_accepted_as_current,
- stale_used_for_export,
- stale_used_for_diagnosis,
- stale_used_for_exclusion,
- stale_used_for_treatment,
- stale_used_for_validation.

### 8.3 Required Stale Guard

```yaml
stale_binding_guard:
  stale_detection_required: true
  stale_bindings_export_blocked: true
  stale_bindings_rehydration_blocked: true
  stale_bindings_authority_effect: none
  stale_resolution_audit_required: true
```

Stale prevention rule:

> Stale bindings must refresh, supersede, or fail closed; they must not remain silently active.

---

## 9. Binding Synchronization Rules

### 9.1 Required Synchronization

The following binding families must remain synchronized.

| Binding | Must Sync With |
|---|---|
| intake_field_binding | missing evidence, confidence limiters, prompts, audit |
| missing_evidence_binding | intake fields, confidence limiters, workspace, output layers |
| confidence_limiter_binding | missing evidence, uncertainty panel, output layers |
| mimic_visibility_binding | intake fields, missing evidence, overlap, workspace |
| overlap_binding | involved prompts, mimics, missing evidence, uncertainty |
| source_status_binding | intake fields, output layers, workspace badges |
| review_prompt_binding | urgent/MDD panels, output layers, audit |
| authority_envelope_binding | session, snapshot, export, workspace footer |
| no_decision_object | session, snapshot, export, rehydration |
| audit_event_chain | every state mutation and guardrail event |

### 9.2 Blocked Desynchronization

Blocked:

- missing evidence exists in snapshot but not workspace,
- source status exists in output but not session,
- confidence limiter exists in workspace but not snapshot,
- mimic visible in output but missing from session object,
- overlap visible in workspace but absent from snapshot,
- urgent banner visible without review prompt binding,
- MDD prompt visible without review binding,
- authority envelope in session but absent from export,
- no-decision object in session but absent from snapshot,
- audit event absent after mutation.

Synchronization rule:

> A session is invalid when reasoning state is visible in one layer but unbound in another without audit.

---

## 10. Authority Envelope Consistency Rules

The authority envelope must be present and identical across:

- reasoning_session_object,
- case_snapshot,
- workspace_state_binding,
- structured_output_binding,
- safe exports,
- audit event chain,
- rehydrated workspace.

Required invariant:

```yaml
authority_envelope_invariant:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed.platform_wide: false
  patient_facing_use: not_allowed
  mutable: false
  removable: false
```

Blocked authority envelope drift:

- missing from snapshot,
- missing from export,
- different value in workspace,
- public_ready changed to true,
- patient_facing_use enabled,
- clinically_reviewed.platform_wide changed to true,
- diagnostic authority enabled,
- treatment authority enabled.

Authority consistency rule:

> Authority envelope drift invalidates the session state.

---

## 11. No-Decision Object Consistency Rules

The no-decision object must be present and identical across:

- reasoning_session_object,
- case_snapshot,
- snapshot export,
- workspace rehydration,
- audit chain reference.

Required invariant:

```yaml
no_decision_invariant:
  final_diagnosis: blocked
  disease_exclusion: blocked
  mimic_exclusion: blocked
  treatment_plan: blocked
  test_order: blocked
  procedure_decision: blocked
  follow_up_schedule: blocked
  triage_decision: blocked
  public_ready_output: blocked
  patient_facing_output: blocked
  platform_wide_clinical_review: blocked
  hidden_decision_fields_allowed: false
```

Blocked no-decision drift:

- no-decision object missing,
- no-decision object editable,
- blocked field removed,
- hidden decision field added,
- final diagnosis object created beside no-decision object,
- export omits no-decision statement.

No-decision consistency rule:

> A session without a no-decision object is invalid.

---

## 12. Audit Chain Integrity Rules

Every state change must produce an audit event.

### 12.1 Required Audit Coverage

Audit event required for:

- binding created,
- binding updated,
- binding superseded,
- binding corrected,
- binding marked stale,
- binding repaired,
- orphan detected,
- orphan repaired,
- snapshot created,
- snapshot superseded,
- snapshot rehydrated,
- workspace refreshed,
- safe export created,
- guardrail triggered,
- authority envelope checked,
- no-decision object checked.

### 12.2 Audit Chain Invariants

```yaml
audit_chain_invariant:
  every_mutation_has_event: true
  every_guardrail_has_event: true
  every_snapshot_has_event: true
  every_export_has_event: true
  audit_authority_effect: none
  audit_clinical_validation: false
```

### 12.3 Blocked Audit Drift

Blocked:

- mutation without audit,
- guardrail without audit,
- export without audit,
- audit event claims correctness,
- audit event claims diagnosis,
- audit event claims treatment authorization,
- audit event claims MDD completion,
- audit event claims public readiness.

Audit integrity rule:

> Audit chain proves traceability, not clinical truth.

---

## 13. Snapshot Rehydration Integrity

A snapshot may rehydrate the workspace only if all required bindings are present and current.

### 13.1 Required Rehydration Inputs

Required:

- current snapshot ID,
- authority envelope binding,
- no-decision object,
- workspace state bindings,
- intake field bindings,
- missing evidence bindings,
- confidence limiter bindings,
- source status bindings,
- mimic visibility bindings,
- overlap bindings,
- review prompt bindings,
- audit event references.

### 13.2 Allowed Rehydrated Outputs

Allowed:

- reasoning flow layout,
- layer cards,
- source status badges,
- missing evidence panel,
- mimic visibility panel,
- temporal comparison panel,
- overlap panel,
- uncertainty panel,
- urgent review banner,
- MDD review panel,
- blocked output guardrails,
- authority envelope footer,
- audit trail.

### 13.3 Blocked Rehydrated Outputs

Blocked:

- final diagnosis panel,
- treatment plan panel,
- test order panel,
- biopsy required banner,
- follow-up scheduler,
- triage disposition banner,
- patient-facing panel,
- public-ready toggle,
- clinically validated badge.

Rehydration integrity rule:

> Rehydration restores reasoning visibility, not decision controls.

---

## 14. Snapshot Export Integrity

A snapshot export is valid only if it includes:

- snapshot ID,
- session ID,
- non-authority statement,
- authority envelope,
- no-decision statement,
- source status limitations,
- missing evidence state,
- confidence limiters,
- mimic visibility where relevant,
- overlap where relevant,
- review prompts where relevant,
- audit references,
- blocked output notice.

Blocked export defects:

- missing authority envelope,
- missing no-decision statement,
- stale binding included as current,
- source limitation removed,
- missing evidence omitted,
- confidence limiter omitted,
- mimic visibility omitted in high-risk context,
- output framed as diagnosis,
- output framed as treatment plan,
- output framed as clinical validation,
- patient-facing format.

Snapshot export integrity rule:

> Export integrity requires authority, limitation, missingness, audit, and no-decision preservation.

---

## 15. Source Status Binding Integrity

A source status binding must stay attached to every dependent field, output layer, and workspace badge.

Required source status propagation:

```yaml
source_status_integrity:
  source_id_required: true
  source_role_class_required: true
  claim_mapping_status_required: true
  source_limitations_required: true
  authority_effect: none
```

Blocked source integrity failures:

- source status omitted from dependent claim,
- source limitation lost during snapshot,
- source role upgraded without audit,
- source mapping treated as validation,
- treatment-heavy warning removed,
- diagnostic-performance warning removed,
- case-example-only warning removed.

Source integrity rule:

> Source status may support visibility; it must preserve limitation.

---

## 16. Missing Evidence Binding Integrity

A missing evidence binding must remain synchronized with:

- intake field state,
- missing evidence panel,
- confidence limiter,
- affected prompts,
- snapshot,
- audit chain.

Blocked integrity failures:

- missing evidence hidden from workspace,
- missing evidence absent from snapshot,
- missing evidence removed without supplied evidence,
- missing evidence treated as exclusion,
- missing evidence suppresses mimic visibility,
- missing evidence missing from export.

Missing evidence integrity rule:

> Missing evidence must remain visible wherever it limits interpretation.

---

## 17. Confidence Limiter Binding Integrity

A confidence limiter binding must remain synchronized with:

- missing or incomplete field,
- source limitation,
- conflicting evidence,
- uncertainty panel,
- structured output uncertainty layer,
- snapshot,
- audit chain.

Blocked integrity failures:

- limiter detached from cause,
- limiter displayed as probability,
- limiter omitted from snapshot,
- limiter omitted from export,
- limiter removed without evidence or audit,
- limiter becomes disease rank.

Confidence limiter integrity rule:

> A limiter must always have a traceable cause and must never become probability.

---

## 18. Mimic Visibility Binding Integrity

A mimic visibility binding must remain synchronized with:

- relevant intake fields,
- missing evidence,
- confidence limiters,
- overlap bindings,
- high-risk mimic layer,
- mimic visibility panel,
- snapshot,
- audit chain.

Blocked integrity failures:

- mimic visible in output but absent from session,
- mimic omitted from high-risk workspace,
- mimic suppressed by missing evidence,
- mimic confirmed,
- mimic excluded,
- mimic used to recommend treatment/test/procedure.

Mimic integrity rule:

> High-risk mimic visibility must not be orphaned, suppressed, diagnosed, or excluded.

---

## 19. Overlap Binding Integrity

An overlap binding must remain synchronized with:

- involved prompts,
- relevant mimics,
- missing evidence,
- confidence limiters,
- overlap layer,
- overlap panel,
- snapshot,
- audit chain.

Blocked integrity failures:

- overlap shown without involved prompts,
- overlap removed without evidence/audit,
- overlap converted to winner selection,
- secondary process excluded,
- mimic suppressed,
- overlap omitted from export.

Overlap integrity rule:

> Overlap must stay connected to involved prompts and must never become winner selection.

---

## 20. Review Prompt Binding Integrity

A review prompt binding must remain synchronized with:

- urgent or MDD trigger state,
- relevant intake fields,
- missing evidence,
- confidence limiters,
- workspace banner/panel,
- structured output review layer,
- snapshot,
- audit chain.

Blocked integrity failures:

- urgent banner visible without review binding,
- MDD panel visible without review binding,
- review prompt removed without audit,
- urgent prompt becomes triage,
- MDD prompt becomes MDD replacement,
- specialist review prompt becomes specialist replacement.

Review prompt integrity rule:

> Review prompt bindings preserve review visibility, not review completion.

---

## 21. Binding Propagation Event Matrix

Allowed propagation events:

| Event | Required Integrity Check |
|---|---|
| intake_field_bound | source/missing/limiter/prompt/audit links checked |
| missing_evidence_bound | affected prompts and limiter links checked |
| confidence_limiter_bound | cause link and probability block checked |
| source_status_bound | limitation preservation checked |
| mimic_visibility_bound | mimic not diagnosis/exclusion checked |
| overlap_bound | winner selection blocked |
| review_prompt_bound | triage/MDD replacement blocked |
| workspace_state_bound | decision controls blocked |
| structured_output_layer_bound | decision layers blocked |
| authority_envelope_bound | invariant checked |
| no_decision_object_bound | blocked fields checked |
| audit_event_bound | validation language blocked |
| snapshot_rehydrated | stale/orphan/authority checks passed |
| snapshot_exported | export boundary checks passed |

Propagation matrix rule:

> Every propagation event must pass both object integrity and authority neutrality checks.

---

## 22. Integrity Validation Pipeline

Every session integrity check must run through:

```yaml
integrity_validation_pipeline:
  step_1_validate_session_id:
    required: true

  step_2_validate_binding_refs:
    orphan_block: true

  step_3_validate_stale_status:
    stale_export_block: true
    stale_rehydration_block: true

  step_4_validate_authority_envelope:
    drift_block: true

  step_5_validate_no_decision_object:
    required: true

  step_6_validate_source_status:
    limitation_preserved: true

  step_7_validate_missing_evidence:
    missing_not_exclusion: true

  step_8_validate_confidence_limiters:
    probability_blocked: true

  step_9_validate_mimics_and_overlap:
    diagnosis_and_winner_selection_blocked: true

  step_10_validate_review_prompts:
    triage_and_review_replacement_blocked: true

  step_11_validate_audit_chain:
    every_mutation_audited: true
    audit_not_validation: true

  step_12_validate_export_or_rehydration:
    decision_controls_blocked: true
    patient_facing_blocked: true
    public_ready_blocked: true
```

Integrity pipeline rule:

> A session object is valid only after passing all integrity gates.

---

## 23. Repair and Recovery Rules

When integrity failure occurs, the platform may repair state only through governed recovery.

Allowed recovery actions:

- mark binding stale,
- block export,
- block rehydration,
- create repair audit event,
- create corrected binding,
- create corrected snapshot,
- supersede invalid snapshot,
- restore authority envelope,
- restore no-decision object,
- relink orphaned binding,
- preserve prior state history.

Blocked recovery actions:

- silently mutate snapshot,
- silently delete audit chain,
- bypass authority envelope,
- bypass no-decision object,
- convert repair into clinical validation,
- create diagnosis during repair,
- hide missing evidence during repair,
- remove mimic visibility during repair.

Repair rule:

> Integrity repair restores traceability and safety, not clinical truth.

---

## 24. Object Integrity Acceptance Tests

### TEST_001 — Orphan Missing Evidence Binding

Input:

```yaml
missing_evidence_binding:
  session_id: missing
```

Expected:

- binding invalid,
- orphan_blocked,
- export blocked,
- rehydration blocked,
- repair audit required,
- authority_effect: none.

---

### TEST_002 — Stale Workspace State

Input:

```yaml
workspace_state_binding:
  source_snapshot_id: older_snapshot
  current_snapshot_id: newer_snapshot
```

Expected:

- stale_detected,
- stale binding cannot rehydrate workspace,
- refresh required,
- audit recorded,
- no decision controls created.

---

### TEST_003 — Missing Authority Envelope in Snapshot

Input:

```yaml
case_snapshot:
  authority_envelope_ref: null
```

Expected:

- snapshot invalid,
- export blocked,
- rehydration blocked,
- repair required,
- no clinical output allowed.

---

### TEST_004 — Source Status Lost During Export

Input:

```yaml
snapshot_export:
  source_status_refs: omitted
```

Expected:

- export invalid,
- source limitation loss blocked,
- corrected export required,
- audit recorded.

---

### TEST_005 — Rehydration Adds Decision Control

Input:

```yaml
rehydrated_workspace:
  component: treatment_plan_panel
```

Expected:

- rehydration blocked,
- decision control rejected,
- guardrail audit recorded,
- authority envelope preserved.

---

## 25. Red-Team Object Integrity Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| Intake binding exists without snapshot ref | orphan binding blocked |
| Workspace state points to old snapshot | stale binding blocked |
| Source status lost during snapshot export | export blocked |
| Missing evidence removed without supplied evidence | missing evidence integrity block |
| Confidence limiter becomes disease probability | limiter-to-probability blocked |
| Mimic visibility disappears after missing evidence update | mimic erasure blocked |
| Overlap binding chooses winner | forced closure blocked |
| Urgent review binding assigns disposition | triage blocked |
| MDD binding says consensus achieved | MDD replacement blocked |
| Audit event claims clinical correctness | audit-to-validation blocked |
| Authority envelope differs across session and export | authority drift blocked |
| No-decision object missing from snapshot | snapshot invalid |
| Rehydration creates final diagnosis panel | decision control blocked |
| Safe export omits blocked output notice | export invalid |
| Public-ready toggle appears after repair | deployment claim blocked |

---

## 26. v0.12.3 Acceptance Criteria

v0.12.3 is accepted only if:

- binding graph registry is defined,
- canonical binding object is defined,
- binding directionality rules are defined,
- blocked directionality is defined,
- orphan binding prevention is defined,
- stale binding prevention is defined,
- binding synchronization rules are defined,
- authority envelope consistency is required,
- no-decision object consistency is required,
- audit chain integrity is required,
- snapshot rehydration integrity is defined,
- snapshot export integrity is defined,
- source status binding integrity is defined,
- missing evidence binding integrity is defined,
- confidence limiter binding integrity is defined,
- mimic visibility binding integrity is defined,
- overlap binding integrity is defined,
- review prompt binding integrity is defined,
- propagation event matrix is defined,
- integrity validation pipeline is defined,
- repair and recovery rules are defined,
- object integrity acceptance tests are defined,
- red-team integrity failures are blocked,
- orphan bindings cannot persist silently,
- stale bindings cannot export or rehydrate as current,
- authority envelope cannot drift,
- no-decision object cannot be omitted,
- audit chain cannot imply validation,
- rehydration cannot add decision controls,
- export cannot omit authority or no-decision constraints,
- no diagnosis is created,
- no treatment is created,
- no test order is created,
- no procedure decision is created,
- no follow-up schedule is created,
- no triage is created,
- no public readiness is created,
- no patient-facing use is created,
- no platform-wide clinical review is created.

---

## 27. Next Step

The next recommended step is:

- v0.12.4 — Case Assembly Validation Checklist / Session Integrity Gate

v0.12.4 should verify:

- v0.12.0 entry gate exists,
- v0.12.1 reasoning session object schema exists,
- v0.12.2 snapshot/revision contract exists,
- v0.12.3 binding propagation integrity rules exist,
- session object contains no decision fields,
- every binding has session/snapshot/audit refs,
- stale/orphan guards exist,
- authority envelope is consistent,
- no-decision object is present,
- audit chain is non-validating,
- snapshot rehydration is safe,
- snapshot export is governance-safe,
- no diagnosis,
- no treatment,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no public readiness,
- no patient-facing use,
- no platform-wide clinical review.

v0.12.4 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 28. Governance Statement

This document defines session binding propagation and object integrity rules.

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

A session graph connects reasoning state, not clinical authority.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.3:

> “A reasoning session is valid only if every binding can be traced, refreshed, audited, rehydrated, and exported without losing authority boundaries or creating decision state.”