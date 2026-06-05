# ILD Reasoning Platform — Case Assembly Validation Checklist / Session Integrity Gate v1

Version: v0.12.4  
Status: pre_seal_validation_checklist  
Scope: Validation checklist for case assembly, reasoning session object, snapshots, revisions, bindings, rehydration, exports, audit chain, and object integrity  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This checklist verifies that v0.12 — Case Assembly / Reasoning Session Object Contract is ready for structural sealing.

It follows:

- `docs/navigation/case_assembly_reasoning_session_entry_gate_v1.md`
- `docs/data/schema/reasoning_session_object_schema_v1.md`
- `docs/data/schema/case_snapshot_revision_history_contract_v1.md`
- `docs/data/schema/session_binding_propagation_object_integrity_rules_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_11.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

This checklist does not add new disease content.

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

Its purpose is to verify that the platform can assemble a governed reasoning session object without assembling diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, triage, public readiness, patient-facing output, or platform-wide clinical review.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.4:

> “Case assembly is seal-ready only if every session object, snapshot, revision, binding, rehydration, export, and audit event remains traceable, synchronized, non-stale, non-orphaned, and authority-neutral.”

---

## 2. v0.12 Chain Under Validation

The following v0.12 files must be present before structural sealing.

| Version | File | Role | Required Status |
|---|---|---|---|
| v0.12.0 | `docs/navigation/case_assembly_reasoning_session_entry_gate_v1.md` | Case assembly entry gate | present |
| v0.12.1 | `docs/data/schema/reasoning_session_object_schema_v1.md` | Reasoning session object schema | present |
| v0.12.2 | `docs/data/schema/case_snapshot_revision_history_contract_v1.md` | Case snapshot / revision history contract | present |
| v0.12.3 | `docs/data/schema/session_binding_propagation_object_integrity_rules_v1.md` | Session binding propagation / object integrity rules | present |
| v0.12.4 | `docs/navigation/case_assembly_validation_checklist_session_integrity_gate_v1.md` | Session integrity validation checklist | current |

Validation condition:

- v0.12.0 through v0.12.3 must exist.
- The reasoning session object must contain no decision fields.
- Snapshots must be reasoning-state snapshots, not final reports.
- Revision history must record state movement, not clinical validation.
- Bindings must be synchronized, non-orphaned, non-stale, and audit-linked.
- Authority envelope and no-decision object must be present everywhere required.

---

## 3. Prior Seal Inheritance Checklist

v0.12 must inherit and preserve all prior structural seals.

| Prior Layer | Required Inheritance |
|---|---|
| v0.3 Superimposed Events Core | Multiple processes may coexist; single-label closure remains blocked |
| v0.4 Evidence Layer / Source Review Governance | Source-sensitive claims require anchor, role, review status, and limitation visibility |
| v0.5 Test Case Coverage Expansion | Missing evidence, mimics, MDD, urgent review, and non-authority remain visible |
| v0.6 UIP Parity Seal | UIP-facing reasoning remains non-diagnostic and source-governed |
| v0.6.R1/R2/R3 | Source-review debt and claim mapping discipline remain visible |
| v0.7 Non-UIP Differential Seal | Differential prompts remain visible without diagnoses |
| v0.8 High-Risk Mimic Seal | High-risk mimics remain visible without becoming diagnoses |
| v0.9 Structured Output Contract Seal | Structured output displays reasoning safely without clinical authority |
| v0.10 Clinician Workspace Seal | Interactive workspace remains reasoning visibility surface, not decision surface |
| v0.11 Evidence Intake Seal | Supplied evidence may update reasoning visibility but not create authority |
| checkpoint-v0.11 | v0.12 opens as case assembly governance, not clinical deployment |

Validation condition:

- v0.12 must not weaken any previous non-authority boundary.
- v0.12 must not convert case assembly into diagnostic assembly.
- v0.12 must not convert session snapshots into clinical reports.
- v0.12 must not convert revision history or audit chain into clinical validation.

---

## 4. Global Authority Validation Checklist

The following constraints must remain true across all v0.12 session objects, snapshots, revisions, bindings, diffs, rehydration, exports, audits, and repair operations.

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

Validation condition:

- No session object may change these values.
- No snapshot may omit or override these values.
- No revision may reinterpret these values.
- No binding repair may bypass these values.
- No export may hide these values.

---

## 5. Case Assembly Identity Checklist

The case assembly layer must remain:

| Identity | Required State |
|---|---|
| case assembly governance layer | true |
| reasoning session state layer | true |
| clinical decision layer | false |
| diagnostic layer | false |
| treatment layer | false |
| ordering layer | false |
| procedure decision layer | false |
| follow-up scheduling layer | false |
| triage layer | false |
| patient-facing layer | false |
| public deployment layer | false |

Validation condition:

> Case assembly may organize governed reasoning state, but it must not create clinical conclusions.

Failure examples:

- session object contains `final_diagnosis`,
- snapshot is called a diagnostic report,
- revision history claims clinical validation,
- rehydration creates treatment panel,
- export omits authority envelope.

---

## 6. Reasoning Session Object Checklist

The root `reasoning_session_object` must include:

| Required Object / Field | Required |
|---|---|
| session_id | yes |
| session_schema_version | yes |
| session_status | yes |
| case_snapshot_current | yes |
| case_snapshot_history | yes |
| session_revision_history | yes |
| intake_field_bindings | yes |
| workspace_state_bindings | yes |
| structured_output_bindings | yes |
| source_status_bindings | yes |
| missing_evidence_bindings | yes |
| confidence_limiter_bindings | yes |
| mimic_visibility_bindings | yes |
| overlap_bindings | yes |
| review_prompt_bindings | yes |
| authority_envelope_binding | yes |
| audit_event_chain | yes |
| no_decision_object | yes |

Required authority fields:

| Field | Required Value |
|---|---|
| authority_effect | none |
| diagnosis_created | false |
| exclusion_created | false |
| treatment_created | false |
| test_order_created | false |
| procedure_decision_created | false |
| follow_up_created | false |
| triage_created | false |
| public_ready_created | false |
| patient_facing_created | false |
| platform_wide_clinical_review_created | false |

Blocked root fields:

- final_diagnosis,
- confirmed_diagnosis,
- excluded_disease,
- excluded_mimic,
- treatment_plan,
- test_order,
- procedure_recommendation,
- follow_up_schedule,
- triage_decision,
- patient_facing_summary,
- public_ready_output,
- clinical_validation_status.

Validation condition:

> The root session object assembles governed reasoning state only.

---

## 7. Case Snapshot Checklist

Every `case_snapshot` must include:

| Required Snapshot Element | Required |
|---|---|
| snapshot_id | yes |
| session_id | yes |
| snapshot_index | yes |
| created_reason | allowed snapshot trigger only |
| intake_state_refs | yes |
| workspace_state_refs | yes |
| structured_output_refs | yes |
| source_status_refs | yes |
| missing_evidence_refs | yes |
| confidence_limiter_refs | yes |
| mimic_visibility_refs | yes |
| overlap_refs | yes |
| review_prompt_refs | yes |
| authority_envelope_ref | yes |
| no_decision_object_ref | yes |
| audit_event_refs | yes |

Required snapshot flags:

| Flag | Required Value |
|---|---|
| snapshot_is_final_report | false |
| snapshot_is_patient_facing | false |
| snapshot_is_public_ready | false |
| snapshot_is_clinically_validated | false |
| snapshot_authority_effect | none |

Blocked snapshot content:

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

Validation condition:

> A snapshot freezes reasoning state, not clinical conclusion.

---

## 8. Snapshot Trigger Checklist

Allowed snapshot triggers:

- session_created,
- intake_field_bound,
- evidence_updated,
- missing_evidence_updated,
- confidence_limiter_updated,
- prompt_visibility_updated,
- workspace_refreshed,
- source_status_updated,
- mimic_visibility_updated,
- overlap_updated,
- review_prompt_updated,
- guardrail_triggered,
- clinician_note_added,
- correction_recorded,
- supersession_recorded,
- safe_export_created,
- session_closed.

Blocked snapshot triggers:

- final_diagnosis_created,
- disease_excluded,
- treatment_plan_created,
- test_order_created,
- procedure_decision_created,
- follow_up_schedule_created,
- triage_decision_created,
- public_ready_enabled,
- patient_facing_summary_created,
- clinical_validation_confirmed.

Validation condition:

> Snapshot creation may follow reasoning-state movement, not clinical decision creation.

---

## 9. Snapshot Immutability / Correction / Supersession Checklist

Required:

- snapshots are immutable after creation,
- corrections create correction records,
- corrections create later corrected snapshots,
- supersessions preserve prior snapshot references,
- prior snapshots are not silently rewritten,
- audit trail is preserved,
- authority envelope is preserved,
- no-decision object is preserved.

Blocked:

- silent snapshot mutation,
- silent audit deletion,
- source status overwrite without audit,
- missing evidence removal without audit,
- confidence limiter removal without audit,
- snapshot converted into diagnostic report,
- correction interpreted as clinical validation,
- supersession interpreted as clinical correctness.

Validation condition:

> A snapshot can be corrected or superseded, but not silently rewritten.

---

## 10. Revision History Checklist

Every revision must include:

| Revision Field | Required |
|---|---|
| revision_id | yes |
| session_id | yes |
| revision_index | yes |
| revision_type | allowed revision type |
| previous_snapshot_id | yes or null |
| new_snapshot_id | yes |
| changed_binding_ids | yes |
| added_binding_ids | yes |
| removed_or_deactivated_binding_ids | yes |
| preserved_binding_ids | yes |
| audit_event_refs | yes |
| revision_authority_effect | none |

Required revision flags:

| Flag | Required Value |
|---|---|
| revision_is_clinical_validation | false |
| revision_is_diagnostic_update | false |
| revision_is_treatment_update | false |
| diagnosis_created | false |
| exclusion_created | false |
| treatment_created | false |
| test_order_created | false |
| procedure_decision_created | false |
| follow_up_created | false |
| triage_created | false |
| public_ready_created | false |
| patient_facing_created | false |
| platform_wide_clinical_review_created | false |

Validation condition:

> Revision history records state movement, not clinical correctness.

---

## 11. Snapshot Diff Checklist

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

Required diff flags:

| Diff Field | Required Value |
|---|---|
| authority_envelope_changed | false |
| no_decision_object_changed | false |
| diagnosis_created | false |
| treatment_created | false |
| exclusion_created | false |
| clinical_validation_created | false |

Validation condition:

> Snapshot diff shows state change, not clinical improvement.

---

## 12. Binding Graph Checklist

The session binding graph must contain governed binding families only.

Required binding families:

| Binding Family | Required Integrity |
|---|---|
| intake_field_binding | session/snapshot/prompt/audit refs |
| workspace_state_binding | session/component/snapshot/audit refs |
| structured_output_binding | v0.9 layer/session/snapshot/audit refs |
| source_status_binding | claim/source/dependent refs |
| missing_evidence_binding | missing field/prompt/limiter/audit refs |
| confidence_limiter_binding | cause/prompt/audit refs |
| mimic_visibility_binding | intake/missing/overlap refs |
| overlap_binding | involved prompts/unresolved boundary refs |
| review_prompt_binding | urgent/MDD/specialist prompt refs |
| authority_envelope_binding | required everywhere |
| audit_event_chain | every mutation and guardrail |
| no_decision_object | required everywhere |

Blocked binding families:

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

Validation condition:

> The session graph may connect reasoning state, not clinical authority.

---

## 13. Canonical Binding Object Checklist

Every binding must include:

| Canonical Binding Field | Required |
|---|---|
| binding_id | yes |
| binding_family | yes |
| session_id | yes |
| current_snapshot_id | yes |
| binding_state | yes |
| upstream_refs | yes |
| downstream_refs | yes |
| snapshot_refs | yes |
| audit_event_refs | yes |
| stale_status | yes |
| orphan_status | yes |
| authority_effect | none |

Required blocked-authority flags:

| Flag | Required Value |
|---|---|
| diagnosis_created | false |
| exclusion_created | false |
| treatment_created | false |
| test_order_created | false |
| procedure_decision_created | false |
| follow_up_created | false |
| triage_created | false |
| public_ready_created | false |
| patient_facing_created | false |
| platform_wide_clinical_review_created | false |

Validation condition:

> Every binding must know where it came from, where it propagates, which snapshot contains it, and which audit event records it.

---

## 14. Orphan Binding Checklist

A binding is invalid if:

- it has no session_id,
- it has no snapshot reference,
- it has no audit reference after mutation,
- it references a missing upstream field,
- it references a missing workspace component,
- it references deleted source status without supersession,
- it references missing authority envelope,
- it references missing no-decision object,
- it exists outside the session graph.

Required orphan behavior:

- orphan binding blocked,
- export blocked,
- rehydration blocked,
- repair audit required,
- authority_effect remains none.

Blocked orphan repair behavior:

- silent deletion,
- silent attachment to diagnosis object,
- repair creating clinical validation,
- authority envelope removal,
- no-decision object removal.

Validation condition:

> Orphan bindings must fail closed and require traceable repair.

---

## 15. Stale Binding Checklist

A stale binding must be detected when:

- upstream intake field changes,
- source status changes,
- missing evidence state changes,
- confidence limiter changes,
- prompt visibility changes,
- workspace component refreshes,
- snapshot supersedes prior state,
- correction is recorded,
- rollback is performed.

Allowed stale handling:

- stale_detected,
- stale_blocked,
- stale_superseded,
- stale_corrected,
- refresh_required,
- refresh_completed,
- audit_recorded.

Blocked stale handling:

- stale accepted as current,
- stale used for export,
- stale used for rehydration,
- stale used for diagnosis,
- stale used for exclusion,
- stale used for treatment,
- stale used for validation.

Validation condition:

> Stale bindings must refresh, supersede, or fail closed.

---

## 16. Binding Synchronization Checklist

The following must remain synchronized:

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

Blocked desynchronization:

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

Validation condition:

> A session is invalid when reasoning state is visible in one layer but unbound in another without audit.

---

## 17. Authority Envelope Consistency Checklist

Authority envelope must be present and identical across:

- reasoning_session_object,
- case_snapshot,
- workspace_state_binding,
- structured_output_binding,
- safe export,
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

Blocked drift:

- missing from snapshot,
- missing from export,
- different value in workspace,
- public_ready changed to true,
- patient_facing_use enabled,
- clinically_reviewed.platform_wide changed to true,
- diagnostic authority enabled,
- treatment authority enabled.

Validation condition:

> Authority envelope drift invalidates the session state.

---

## 18. No-Decision Object Checklist

No-decision object must be present and identical across:

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

Blocked drift:

- no-decision object missing,
- no-decision object editable,
- blocked field removed,
- hidden decision field added,
- final diagnosis object created beside no-decision object,
- export omits no-decision statement.

Validation condition:

> A session or snapshot without a no-decision object is invalid.

---

## 19. Audit Chain Integrity Checklist

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

Required audit invariants:

```yaml
audit_chain_invariant:
  every_mutation_has_event: true
  every_guardrail_has_event: true
  every_snapshot_has_event: true
  every_export_has_event: true
  audit_authority_effect: none
  audit_clinical_validation: false
```

Blocked audit drift:

- mutation without audit,
- guardrail without audit,
- export without audit,
- audit event claims correctness,
- audit event claims diagnosis,
- audit event claims treatment authorization,
- audit event claims MDD completion,
- audit event claims public readiness.

Validation condition:

> Audit chain proves traceability, not clinical truth.

---

## 20. Rehydration Safety Checklist

Snapshot rehydration may restore:

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

Snapshot rehydration must not restore or create:

- final diagnosis panel,
- treatment plan panel,
- test order panel,
- biopsy required banner,
- follow-up scheduler,
- triage disposition banner,
- patient-facing panel,
- public-ready toggle,
- clinically validated badge.

Required rehydration gates:

- no stale bindings,
- no orphan bindings,
- authority envelope present,
- no-decision object present,
- audit refs present,
- decision controls blocked.

Validation condition:

> Rehydration restores reasoning visibility, not clinical decision state.

---

## 21. Snapshot Export Safety Checklist

A snapshot export must include:

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
- patient-facing format,
- public-ready format.

Validation condition:

> Snapshot export is valid only if authority, limitation, missingness, audit, and no-decision constraints remain visible.

---

## 22. Source / Missing Evidence / Limiter Integrity Checklist

### 22.1 Source Status Integrity

Required:

- source_id present,
- source_role_class present,
- claim_mapping_status present,
- source_limitations present,
- authority_effect none.

Blocked:

- source status omitted from dependent claim,
- source limitation lost during snapshot,
- source role upgraded without audit,
- source mapping treated as validation,
- treatment-heavy warning removed,
- diagnostic-performance warning removed,
- case-example-only warning removed.

### 22.2 Missing Evidence Integrity

Required:

- linked to intake field state,
- linked to missing evidence panel,
- linked to confidence limiter,
- linked to affected prompts,
- linked to snapshot,
- linked to audit chain.

Blocked:

- missing evidence hidden from workspace,
- missing evidence absent from snapshot,
- missing evidence removed without supplied evidence,
- missing evidence treated as exclusion,
- missing evidence suppresses mimic visibility,
- missing evidence missing from export.

### 22.3 Confidence Limiter Integrity

Required:

- linked to missing/incomplete/source-limited/conflicting cause,
- linked to uncertainty panel,
- linked to structured output uncertainty layer,
- linked to snapshot,
- linked to audit chain.

Blocked:

- limiter detached from cause,
- limiter displayed as probability,
- limiter omitted from snapshot,
- limiter omitted from export,
- limiter removed without evidence or audit,
- limiter becomes disease rank.

Validation condition:

> Source status, missing evidence, and confidence limiters must preserve limitation rather than create certainty.

---

## 23. Mimic / Overlap / Review Prompt Integrity Checklist

### 23.1 Mimic Visibility Integrity

Required:

- linked to relevant intake fields,
- linked to missing evidence where relevant,
- linked to confidence limiters,
- linked to overlap bindings,
- linked to high-risk mimic layer,
- linked to mimic visibility panel,
- linked to snapshot,
- linked to audit chain.

Blocked:

- mimic visible in output but absent from session,
- mimic omitted from high-risk workspace,
- mimic suppressed by missing evidence,
- mimic confirmed,
- mimic excluded,
- mimic used to recommend treatment/test/procedure.

### 23.2 Overlap Integrity

Required:

- linked to involved prompts,
- linked to relevant mimics,
- linked to missing evidence,
- linked to confidence limiters,
- linked to overlap layer,
- linked to overlap panel,
- linked to snapshot,
- linked to audit chain.

Blocked:

- overlap shown without involved prompts,
- overlap removed without evidence/audit,
- overlap converted to winner selection,
- secondary process excluded,
- mimic suppressed,
- overlap omitted from export.

### 23.3 Review Prompt Integrity

Required:

- linked to urgent or MDD trigger state,
- linked to relevant intake fields,
- linked to missing evidence,
- linked to confidence limiters,
- linked to workspace banner/panel,
- linked to structured output review layer,
- linked to snapshot,
- linked to audit chain.

Blocked:

- urgent banner visible without review binding,
- MDD panel visible without review binding,
- review prompt removed without audit,
- urgent prompt becomes triage,
- MDD prompt becomes MDD replacement,
- specialist review prompt becomes specialist replacement.

Validation condition:

> Mimics, overlaps, and review prompts preserve safety visibility, not clinical closure.

---

## 24. Repair and Recovery Checklist

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

Validation condition:

> Integrity repair restores traceability and safety, not clinical truth.

---

## 25. Object Integrity Acceptance Tests

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

Validation condition:

> All object integrity tests must pass without authority creation.

---

## 26. Red-Team Session Integrity Checklist

The following failures must be blocked.

| Red-Team Scenario | Required Block |
|---|---|
| Session object contains final_diagnosis | decision field blocked |
| Snapshot exported as diagnostic report | unsafe export blocked |
| Closing snapshot says final diagnosis established | diagnostic closure blocked |
| Revision history says diagnosis improved | validation language blocked |
| Snapshot diff says HP ruled out | exclusion language blocked |
| Snapshot diff shows disease probability | probability blocked |
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
| Patient-facing snapshot created | patient-facing leak blocked |

Validation condition:

> Every red-team scenario must fail closed and preserve authority_effect: none.

---

## 27. Safe Language Checklist

Allowed terms:

- reasoning session,
- case snapshot,
- revision history,
- governed state,
- provided fact,
- not provided,
- clinician supplied,
- source linked,
- source limited,
- missing evidence,
- confidence limiter,
- prompt visible,
- mimic visible,
- overlap unresolved,
- review prompt visible,
- authority envelope,
- no-decision object,
- audit recorded.

Blocked terms:

- final diagnosis,
- confirmed diagnosis,
- ruled out,
- disease excluded,
- treatment plan,
- test ordered,
- biopsy required,
- follow-up due,
- triage decision,
- safe for outpatient care,
- clinically validated,
- patient-ready,
- public-ready.

Validation condition:

> Session language must describe governed state, not clinical conclusion.

---

## 28. Minimal Session Mode Validation

A minimal session mode may exist only if it preserves:

- session ID,
- current snapshot ID,
- authority envelope,
- no-decision object,
- intake bindings,
- missing evidence state,
- confidence limiter state,
- source status state,
- audit chain,
- stale/orphan status.

Blocked minimal omissions:

| Omission | Why Invalid |
|---|---|
| no authority envelope | authority boundary hidden |
| no no-decision object | hidden decision risk |
| no current snapshot | state unanchored |
| no audit chain | mutation untraceable |
| no stale/orphan flags | invalid binding risk |
| no missing evidence state | unsafe closure risk |
| no source status | source governance loss |

Validation condition:

> Minimal session mode may reduce detail, but it cannot reduce integrity safeguards.

---

## 29. Full Session Mode Validation

A full session mode must include:

- reasoning_session_object,
- current case_snapshot,
- case_snapshot_history,
- session_revision_history,
- intake_field_bindings,
- workspace_state_bindings,
- structured_output_bindings,
- source_status_bindings,
- missing_evidence_bindings,
- confidence_limiter_bindings,
- mimic_visibility_bindings,
- overlap_bindings,
- review_prompt_bindings,
- authority_envelope_binding,
- audit_event_chain,
- no_decision_object,
- stale/orphan validation status,
- export/rehydration safety status.

Validation condition:

> Full session mode must assemble complete governed reasoning state without adding decision state.

---

## 30. Pre-Seal Readiness Statement

v0.12 is ready for structural sealing only if:

- v0.12.0 entry gate exists,
- v0.12.1 reasoning session object schema exists,
- v0.12.2 case snapshot / revision history contract exists,
- v0.12.3 session binding propagation / object integrity rules exist,
- v0.12.4 validation checklist exists,
- root session object contains no decision fields,
- every snapshot includes authority envelope,
- every snapshot includes no-decision object,
- snapshots are immutable,
- corrections and supersessions preserve history,
- revision history is non-validating,
- snapshot diff is non-clinical,
- every binding has session/snapshot/audit refs,
- orphan bindings fail closed,
- stale bindings cannot export or rehydrate,
- binding synchronization is enforced,
- authority envelope consistency is required,
- no-decision object consistency is required,
- audit chain integrity is required,
- snapshot rehydration is safe,
- snapshot export is governance-safe,
- source status remains non-authoritative,
- missing evidence cannot become exclusion,
- confidence limiters cannot become probability,
- mimics cannot be diagnosed or excluded,
- overlap cannot choose winner,
- review prompts cannot triage or replace review,
- repair cannot create authority,
- red-team integrity failures are blocked,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

This checklist confirms readiness for structural sealing.

It is not itself the seal.

---

## 31. Next Step

If this checklist is accepted, the next recommended step is:

- v0.12.5 — Case Assembly / Reasoning Session Object Contract Structural Seal

The seal should lock v0.12 as structurally complete while preserving:

- case assembly as governance layer,
- reasoning session object,
- case snapshots,
- revision history,
- binding graph integrity,
- orphan/stale prevention,
- authority envelope consistency,
- no-decision object consistency,
- audit chain non-validation,
- snapshot immutability,
- safe correction and supersession,
- safe rehydration,
- governance-safe export,
- no diagnosis,
- no exclusion,
- no treatment,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no public readiness,
- no patient-facing use,
- no platform-wide clinical review.

v0.12.5 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 32. Governance Statement

This validation checklist prepares v0.12 for structural sealing.

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

Case assembly remains a governance layer, not a clinical decision layer.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.4:

> “Case assembly is seal-ready only if every session object, snapshot, revision, binding, rehydration, export, and audit event remains traceable, synchronized, non-stale, non-orphaned, and authority-neutral.”