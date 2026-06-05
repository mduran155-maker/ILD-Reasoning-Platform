# ILD Reasoning Platform — Case Snapshot / Revision History Contract v1

Version: v0.12.2  
Status: case_snapshot_revision_history_contract  
Scope: Case snapshot creation, revision history, snapshot immutability, correction, supersession, diffing, audit linkage, and safe export boundary  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the case snapshot and revision history contract for v0.12 — Case Assembly / Reasoning Session Object Contract.

It follows:

- `docs/navigation/case_assembly_reasoning_session_entry_gate_v1.md`
- `docs/data/schema/reasoning_session_object_schema_v1.md`
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

Its purpose is to define how case snapshots and session revisions are created, frozen, linked, corrected, superseded, audited, compared, and exported safely.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.2:

> “A snapshot freezes reasoning state, not clinical truth; a revision records state movement, not clinical correctness.”

---

## 2. Global Snapshot and Revision Contract

Every snapshot and revision must preserve:

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

No snapshot, revision, diff, correction, supersession, export, or audit event may override the authority envelope.

---

## 3. Snapshot Identity

A `case_snapshot` is a frozen representation of the governed reasoning session state at a specific point in time.

A snapshot may freeze:

- intake field states,
- provided facts,
- not-provided fields,
- clinician-supplied evidence labels,
- inferred fact blocks,
- workspace component states,
- structured output layer states,
- source status bindings,
- missing evidence bindings,
- confidence limiter bindings,
- mimic visibility bindings,
- overlap bindings,
- review prompt bindings,
- authority envelope binding,
- audit event references,
- no-decision object.

A snapshot must not freeze:

- final diagnosis,
- confirmed diagnosis,
- excluded disease,
- excluded mimic,
- treatment plan,
- test order,
- procedure recommendation,
- follow-up schedule,
- triage disposition,
- patient-facing advice,
- public-ready output,
- platform-wide clinical validation.

Snapshot identity rule:

> A snapshot is a frozen reasoning-state object, not a clinical conclusion object.

---

## 4. Snapshot Creation Triggers

A snapshot may be created only for governed state reasons.

Allowed snapshot creation triggers:

| Trigger ID | Trigger | Meaning |
|---|---|---|
| V12_SNAPSHOT_TRIGGER_001 | session_created | Initial governed session state created |
| V12_SNAPSHOT_TRIGGER_002 | intake_field_bound | Intake field bound into session |
| V12_SNAPSHOT_TRIGGER_003 | evidence_updated | Supplied evidence changed field state |
| V12_SNAPSHOT_TRIGGER_004 | missing_evidence_updated | Missing evidence badge/state changed |
| V12_SNAPSHOT_TRIGGER_005 | confidence_limiter_updated | Interpretation limiter changed |
| V12_SNAPSHOT_TRIGGER_006 | prompt_visibility_updated | Reasoning prompt visibility changed |
| V12_SNAPSHOT_TRIGGER_007 | workspace_refreshed | Workspace state refreshed |
| V12_SNAPSHOT_TRIGGER_008 | source_status_updated | Source binding or limitation changed |
| V12_SNAPSHOT_TRIGGER_009 | mimic_visibility_updated | Mimic visibility state changed |
| V12_SNAPSHOT_TRIGGER_010 | overlap_updated | Overlap state changed |
| V12_SNAPSHOT_TRIGGER_011 | review_prompt_updated | Urgent or MDD prompt state changed |
| V12_SNAPSHOT_TRIGGER_012 | guardrail_triggered | Unsafe output/transition blocked |
| V12_SNAPSHOT_TRIGGER_013 | clinician_note_added | Clinician-authored note linked |
| V12_SNAPSHOT_TRIGGER_014 | correction_recorded | Prior evidence value corrected |
| V12_SNAPSHOT_TRIGGER_015 | supersession_recorded | Prior snapshot superseded |
| V12_SNAPSHOT_TRIGGER_016 | safe_export_created | Governance-safe export created |
| V12_SNAPSHOT_TRIGGER_017 | session_closed | Session closed |

Blocked snapshot creation triggers:

| Blocked Trigger | Why Blocked |
|---|---|
| final_diagnosis_created | diagnostic authority leak |
| disease_excluded | exclusion authority leak |
| treatment_plan_created | treatment authority leak |
| test_order_created | test-order authority leak |
| procedure_decision_created | procedure authority leak |
| follow_up_schedule_created | follow-up authority leak |
| triage_decision_created | triage authority leak |
| public_ready_enabled | deployment leak |
| patient_facing_summary_created | patient-facing use leak |
| clinical_validation_confirmed | unsupported clinical review claim |

Snapshot trigger rule:

> A snapshot may be triggered by reasoning-state movement, not by clinical decision creation.

---

## 5. Snapshot Schema

Every snapshot must use the following schema.

```yaml
case_snapshot:
  snapshot_id: string
  session_id: string
  snapshot_schema_version: case_snapshot_revision_history_contract_v1
  snapshot_index: integer
  created_at: implementation_defined
  created_by: system | clinician | unknown
  created_reason: allowed_snapshot_creation_trigger
  previous_snapshot_id: string_or_null
  supersedes_snapshot_id: string_or_null
  superseded_by_snapshot_id: string_or_null
  snapshot_status:
    - current
    - historical
    - superseded
    - corrected
    - archived

  intake_state_refs: list[intake_field_binding_ref]
  workspace_state_refs: list[workspace_state_binding_ref]
  structured_output_refs: list[structured_output_binding_ref]
  source_status_refs: list[source_status_binding_ref]
  missing_evidence_refs: list[missing_evidence_binding_ref]
  confidence_limiter_refs: list[confidence_limiter_binding_ref]
  mimic_visibility_refs: list[mimic_visibility_binding_ref]
  overlap_refs: list[overlap_binding_ref]
  review_prompt_refs: list[review_prompt_binding_ref]
  authority_envelope_ref: authority_envelope_binding_ref
  no_decision_object_ref: no_decision_object_ref
  audit_event_refs: list[audit_event_ref]

  snapshot_is_final_report: false
  snapshot_is_patient_facing: false
  snapshot_is_public_ready: false
  snapshot_is_clinically_validated: false
  snapshot_authority_effect: none

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

Snapshot schema rule:

> Every snapshot must carry authority-negative fields explicitly.

---

## 6. Snapshot Immutability

Once created, a snapshot must be immutable.

Allowed operations on an existing snapshot:

- read,
- reference,
- export governance-safe summary,
- mark as historical,
- mark as superseded by a later snapshot,
- link correction metadata,
- link audit event.

Blocked operations on an existing snapshot:

- mutate prior values silently,
- delete audit references silently,
- overwrite source status silently,
- remove missing evidence silently,
- remove confidence limiters silently,
- convert snapshot into diagnostic report,
- convert snapshot into treatment plan,
- convert snapshot into patient-facing output,
- edit authority envelope.

Immutability rule:

> A snapshot can be superseded or corrected by a later snapshot; it cannot be silently rewritten.

---

## 7. Snapshot Correction Contract

Corrections must preserve history.

A correction may occur when:

- clinician corrects a supplied value,
- report-derived field is corrected,
- uploaded record extraction is corrected,
- source status linkage is corrected,
- missing evidence state is corrected,
- confidence limiter linkage is corrected,
- prompt visibility state is corrected,
- workspace component state is corrected.

Correction must create:

```yaml
correction_record:
  correction_id: string
  session_id: string
  prior_snapshot_id: string
  corrected_snapshot_id: string
  corrected_binding_ids: list
  correction_reason: string
  corrected_by: clinician | system | unknown
  audit_event_ref: audit_event_ref
  authority_effect: none
```

Correction must not create:

- diagnosis,
- exclusion,
- treatment,
- test order,
- procedure decision,
- follow-up schedule,
- triage,
- public readiness,
- patient-facing use,
- platform-wide clinical validation.

Correction rule:

> Correction repairs state provenance; it does not validate clinical correctness.

---

## 8. Snapshot Supersession Contract

A snapshot may be superseded by a later snapshot.

Allowed supersession reasons:

- new evidence supplied,
- prior evidence corrected,
- missing evidence resolved or updated,
- confidence limiter updated,
- prompt visibility refreshed,
- workspace state refreshed,
- source status corrected,
- guardrail event recorded,
- session closed.

Supersession must preserve:

- prior snapshot reference,
- new snapshot reference,
- reason for supersession,
- audit event,
- authority envelope,
- no-decision object.

Supersession must not imply:

- prior snapshot was clinically wrong,
- new snapshot is clinically correct,
- diagnosis is established,
- treatment is authorized,
- MDD is replaced,
- clinical validation is complete.

Supersession rule:

> Supersession changes current state, not clinical truth.

---

## 9. Revision History Schema

Every session must maintain a revision history.

```yaml
session_revision_history:
  revision_history_id: string
  session_id: string
  revision_count: integer
  revisions: list[session_revision]
  authority_effect: none
```

```yaml
session_revision:
  revision_id: string
  session_id: string
  revision_index: integer
  revision_type:
    - session_created
    - intake_field_added
    - intake_field_updated
    - evidence_updated
    - missing_evidence_updated
    - confidence_limiter_updated
    - prompt_visibility_updated
    - workspace_component_refreshed
    - source_status_updated
    - mimic_visibility_updated
    - overlap_updated
    - review_prompt_updated
    - clinician_note_added
    - guardrail_triggered
    - correction_recorded
    - supersession_recorded
    - safe_export_created
    - session_closed

  previous_snapshot_id: string_or_null
  new_snapshot_id: string
  changed_binding_ids: list
  added_binding_ids: list
  removed_or_deactivated_binding_ids: list
  preserved_binding_ids: list
  audit_event_refs: list

  revision_is_clinical_validation: false
  revision_is_diagnostic_update: false
  revision_is_treatment_update: false
  revision_authority_effect: none

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

Revision schema rule:

> Revision history records governed state changes and must explicitly deny clinical authority creation.

---

## 10. Revision Types and Allowed Effects

| Revision Type | Allowed Effect | Blocked Effect |
|---|---|---|
| session_created | create initial state | create diagnosis |
| intake_field_added | bind provided/missing field | infer clinical truth |
| intake_field_updated | update field state | diagnose/exclude |
| evidence_updated | update visibility | create authority |
| missing_evidence_updated | update missingness | exclude disease |
| confidence_limiter_updated | update limiter | create probability |
| prompt_visibility_updated | update prompt state | confirm diagnosis |
| workspace_component_refreshed | refresh UI state | add decision controls |
| source_status_updated | update source limitation | claim validation |
| mimic_visibility_updated | update mimic prompt | diagnose/exclude mimic |
| overlap_updated | update coexistence | choose winner |
| review_prompt_updated | update review visibility | replace review |
| clinician_note_added | link human note | platform conclusion |
| guardrail_triggered | block unsafe action | provide bypass |
| correction_recorded | preserve correction | validate correctness |
| supersession_recorded | update current state | validate new snapshot |
| safe_export_created | export governance-safe state | export clinical report |
| session_closed | close state | create final diagnosis |

Revision effect rule:

> Revisions update state and traceability, not clinical decisions.

---

## 11. Snapshot Diff Contract

A snapshot diff compares two snapshots.

Allowed diff outputs:

- fields added,
- fields updated,
- fields marked not provided,
- missing evidence added,
- missing evidence updated,
- missing evidence resolved or limited,
- confidence limiters added,
- confidence limiters updated,
- confidence limiters resolved,
- prompt visibility changes,
- mimic visibility changes,
- overlap changes,
- source status changes,
- workspace component changes,
- review prompt changes,
- audit events added,
- authority envelope preserved.

Blocked diff outputs:

- diagnosis improved,
- disease ruled out,
- treatment now indicated,
- test now needed,
- procedure now required,
- follow-up due,
- triage changed,
- clinical accuracy improved,
- MDD replaced,
- public readiness achieved.

Diff schema:

```yaml
snapshot_diff:
  diff_id: string
  session_id: string
  from_snapshot_id: string
  to_snapshot_id: string
  changed_bindings: list
  added_bindings: list
  deactivated_bindings: list
  unchanged_bindings: list
  authority_envelope_changed: false
  no_decision_object_changed: false
  diagnosis_created: false
  treatment_created: false
  exclusion_created: false
  clinical_validation_created: false
```

Diff rule:

> Snapshot diff shows state change, not clinical improvement.

---

## 12. Snapshot Export Boundary

A snapshot may be exported only as governance-safe content.

Allowed snapshot export types:

- governance_safe_snapshot_summary,
- case_state_snapshot_summary,
- missing_evidence_snapshot_summary,
- source_status_snapshot_summary,
- confidence_limiter_snapshot_summary,
- mimic_visibility_snapshot_summary,
- overlap_snapshot_summary,
- review_prompt_snapshot_summary,
- audit_reference_snapshot_summary,
- authority_envelope_snapshot_export.

Required export content:

- non-authority statement,
- snapshot ID,
- session ID,
- snapshot status,
- source status limitations where relevant,
- missing evidence state where relevant,
- confidence limiters where relevant,
- mimic visibility where relevant,
- overlap where relevant,
- review prompts where relevant,
- authority envelope,
- no-decision statement,
- audit references.

Blocked snapshot export types:

- final diagnostic report,
- clinical impression report,
- treatment plan,
- test order recommendation,
- procedure recommendation,
- follow-up schedule,
- triage report,
- patient-facing report,
- public-ready report,
- clinically validated report.

Snapshot export rule:

> A snapshot export may summarize reasoning state; it may not summarize clinical authority.

---

## 13. Final Snapshot and Session Close

A session may have a closing snapshot.

A closing snapshot may indicate:

- session closed,
- current reasoning state frozen,
- audit chain completed for this session,
- authority envelope preserved,
- no-decision object preserved.

A closing snapshot must not indicate:

- final diagnosis,
- final clinical impression,
- final treatment plan,
- final test plan,
- final procedure decision,
- final follow-up schedule,
- final triage disposition,
- clinical validation completed,
- public readiness,
- patient-facing readiness.

Closing snapshot rule:

> Final snapshot means final state of the platform session, not final clinical diagnosis.

---

## 14. Snapshot Authority Envelope Requirement

Every snapshot must include or reference the authority envelope.

Required state:

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed:
    platform_wide: false
  patient_facing_use: not_allowed
  automated_diagnosis: not_allowed
  automated_exclusion: not_allowed
  automated_treatment_selection: not_allowed
  automated_test_order: not_allowed
  automated_procedure_decision: not_allowed
  automated_follow_up_schedule: not_allowed
  automated_triage: not_allowed
```

Blocked authority envelope states:

- missing_from_snapshot,
- hidden_from_export,
- editable,
- public_ready_true,
- patient_facing_enabled,
- clinically_reviewed_platform_wide_true,
- diagnostic_authority_enabled,
- treatment_authority_enabled.

Authority envelope rule:

> Snapshot without authority envelope is invalid.

---

## 15. No-Decision Object Requirement

Every snapshot must include or reference the `no_decision_object`.

Required state:

```yaml
no_decision_object:
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
  MDD_replacement: blocked
  urgent_review_replacement: blocked
  hidden_decision_fields_allowed: false
```

No-decision rule:

> Snapshot without no-decision object is invalid.

---

## 16. Snapshot-to-Workspace Rehydration

A snapshot may be used to rehydrate the clinician workspace.

Allowed rehydrated states:

- reasoning flow layout state,
- layer card state,
- source status badge state,
- missing evidence panel state,
- mimic visibility panel state,
- temporal comparison panel state,
- overlap panel state,
- uncertainty panel state,
- urgent review banner state,
- MDD review panel state,
- blocked output guardrail state,
- authority envelope footer state,
- audit trail state.

Blocked rehydrated states:

- final diagnosis panel,
- treatment plan panel,
- test order panel,
- procedure decision panel,
- follow-up scheduler,
- triage disposition banner,
- patient-facing panel,
- public-ready toggle,
- clinically validated badge.

Rehydration rule:

> Rehydration restores reasoning visibility, not clinical decision state.

---

## 17. Snapshot-to-Structured Output Regeneration

A snapshot may regenerate structured output layers.

Allowed regenerated layers:

- case_context_summary,
- temporal_change_summary,
- pattern_family_prompts,
- differential_prompt_layer,
- overlap_layer,
- high_risk_mimic_layer,
- missing_evidence_layer,
- uncertainty_layer,
- urgent_review_prompt_layer,
- MDD_review_prompt_layer,
- source_status_layer,
- authority_envelope,
- blocked_outputs.

Blocked regenerated layers:

- final_diagnosis_layer,
- treatment_plan_layer,
- test_order_layer,
- procedure_decision_layer,
- follow_up_layer,
- triage_layer,
- patient_advice_layer.

Regeneration rule:

> Snapshot regeneration may rebuild structured reasoning output, not clinical decision output.

---

## 18. Correction and Rollback Safety

Rollback may return the current session to an earlier snapshot only as a reasoning-state rollback.

Allowed rollback effects:

- restore prior intake field state,
- restore prior missing evidence state,
- restore prior confidence limiter state,
- restore prior prompt visibility,
- restore prior workspace component state,
- restore prior source status binding,
- preserve audit trail,
- create rollback revision,
- preserve authority envelope.

Blocked rollback effects:

- declare earlier snapshot clinically correct,
- delete later snapshot silently,
- erase correction history,
- create diagnosis,
- create exclusion,
- create treatment,
- remove authority envelope,
- bypass no-decision object.

Rollback rule:

> Rollback restores governed state while preserving history; it does not restore clinical truth.

---

## 19. Audit Linkage Requirements

Every snapshot must link to audit events.

Required audit linkage:

| Snapshot Event | Required Audit Event |
|---|---|
| snapshot created | case_snapshot_created |
| evidence updated | evidence_update_recorded |
| workspace refreshed | workspace_refresh_recorded |
| guardrail triggered | guardrail_triggered |
| correction recorded | correction_recorded |
| supersession recorded | supersession_recorded |
| safe export created | safe_export_created |
| session closed | session_closed |

Blocked audit linkage meanings:

- audit proves diagnosis,
- audit proves treatment,
- audit proves exclusion,
- audit proves validation,
- audit proves public readiness,
- audit proves patient readiness.

Audit linkage rule:

> Snapshot audit linkage proves traceability, not clinical correctness.

---

## 20. Red-Team Snapshot and Revision Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| Snapshot contains final diagnosis | block diagnostic field |
| Snapshot contains treatment plan | block treatment field |
| Snapshot exported as clinical report | block unsafe export |
| Closing snapshot says final diagnosis established | block diagnostic closure |
| Revision history says diagnosis improved | block validation language |
| Snapshot diff says HP ruled out | block exclusion language |
| Snapshot diff shows disease probability | block probability |
| Correction overwrites old snapshot silently | block silent mutation |
| Supersession implies new snapshot is clinically correct | block supersession-as-validation |
| Audit event validates clinical accuracy | block audit-as-validation |
| Snapshot rehydration creates treatment panel | block decision control |
| Snapshot export hides authority envelope | block unsafe export |
| Snapshot lacks no-decision object | block invalid snapshot |
| Public-ready snapshot created | block deployment claim |
| Patient-facing snapshot created | block patient-facing leak |

---

## 21. v0.12.2 Acceptance Criteria

v0.12.2 is accepted only if:

- snapshot identity is defined,
- snapshot creation triggers are defined,
- blocked snapshot triggers are defined,
- snapshot schema is defined,
- snapshot immutability is required,
- correction contract is defined,
- supersession contract is defined,
- revision history schema is defined,
- revision types and allowed effects are defined,
- snapshot diff contract is defined,
- snapshot export boundary is defined,
- closing snapshot rules are defined,
- authority envelope is required in every snapshot,
- no-decision object is required in every snapshot,
- snapshot-to-workspace rehydration is constrained,
- snapshot-to-structured-output regeneration is constrained,
- correction and rollback safety are defined,
- audit linkage is required,
- red-team snapshot/revision failures are blocked,
- snapshot does not become final report,
- revision history does not become clinical validation,
- diff does not become clinical improvement,
- export does not become diagnostic report,
- no diagnosis field is allowed,
- no treatment field is allowed,
- no test order field is allowed,
- no procedure decision field is allowed,
- no follow-up schedule field is allowed,
- no triage field is allowed,
- no public-ready snapshot is allowed,
- no patient-facing snapshot is allowed,
- no platform-wide clinical review snapshot is allowed.

---

## 22. Next Step

The next recommended step is:

- v0.12.3 — Session Binding Propagation / Object Integrity Rules

v0.12.3 should define:

- how intake bindings connect to snapshot state,
- how workspace bindings connect to snapshot state,
- how structured output bindings connect to snapshot state,
- how source status, missing evidence, confidence limiters, mimic visibility, overlap, and review prompts remain synchronized,
- orphan binding prevention,
- stale binding prevention,
- authority envelope consistency,
- no-decision object consistency,
- audit chain integrity,
- safe snapshot rehydration integrity.

v0.12.3 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 23. Governance Statement

This contract defines case snapshot and revision history governance.

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

A snapshot freezes reasoning state, not clinical truth.

A revision records state movement, not clinical correctness.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.2:

> “A snapshot freezes reasoning state, not clinical truth; a revision records state movement, not clinical correctness.”