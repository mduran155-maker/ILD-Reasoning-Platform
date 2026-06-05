# ILD Reasoning Platform — Case Assembly / Reasoning Session Object Contract Entry Gate v1

Version: v0.12.0  
Status: case_assembly_reasoning_session_entry_gate  
Scope: Case assembly and governed reasoning session object contract entry gate  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document opens v0.12 — Case Assembly / Reasoning Session Object Contract.

v0.12 defines how evidence intake fields, clinician-supplied case context, structured output layers, workspace state, source status, missing evidence, confidence limiters, review prompts, authority envelope, and audit events may be assembled into one governed reasoning session object.

This document does not add new disease content.

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

Its purpose is to define the entry gate for case assembly governance.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.9 sealed principle remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

The v0.10 sealed principle remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

The v0.11 sealed principle remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

The v0.12 entry principle is:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

---

## 2. Relationship to Prior Seals

v0.12 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Upgrade,
- v0.6.R1/R2/R3 source debt and source-status correction,
- v0.7 Non-UIP Fibrotic ILD Differential Reasoning Structural Seal,
- v0.8 High-Risk Mimic Source-Limited Prompt Visibility Structural Seal,
- v0.9 Reasoning Output Contract / Structured Response Schema Structural Seal,
- v0.10 Clinician Review Workspace / Interactive Reasoning UI Contract Structural Seal,
- v0.11 Evidence Intake / Clinician-Supplied Case Context Contract Structural Seal,
- checkpoint-v0.11 roadmap discipline.

v0.12 must not weaken any prior seal.

v0.12 is a case assembly governance phase.

It is not:

- a diagnostic phase,
- a treatment phase,
- a test-ordering phase,
- a procedure-decision phase,
- a follow-up scheduling phase,
- a triage phase,
- a public-readiness phase,
- a patient-facing phase,
- an automated clinical decision-support deployment phase.

---

## 3. v0.12 Entry Gate Scope

v0.12 may define:

- governed reasoning session object,
- case snapshot object,
- session revision history,
- intake field bindings,
- workspace state bindings,
- structured output layer bindings,
- source status bindings,
- missing evidence bindings,
- confidence limiter bindings,
- mimic visibility bindings,
- overlap bindings,
- urgent review prompt bindings,
- MDD review prompt bindings,
- authority envelope binding,
- audit event chain,
- case assembly validation,
- safe session export boundary,
- no-decision object constraints.

v0.12 may not define:

- final diagnosis object,
- disease exclusion object,
- treatment plan object,
- test order object,
- procedure recommendation object,
- follow-up schedule object,
- triage decision object,
- patient-facing report object,
- public-ready object,
- platform-wide clinical review object,
- autonomous MDD conclusion object.

---

## 4. Global Authority Constraints

The following constraints remain mandatory across v0.12.

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

No session object, case snapshot, revision, binding, export, or audit event may override these constraints.

---

## 5. Case Assembly Philosophy

The platform now has three major governed layers:

| Layer | Purpose |
|---|---|
| v0.9 structured output | Defines what reasoning layers can be displayed |
| v0.10 clinician workspace | Defines how clinicians can safely interact with reasoning |
| v0.11 evidence intake | Defines how case context can safely enter the platform |

v0.12 assembles these layers into a governed session object.

The session object may hold:

- what was provided,
- what was missing,
- what was inferred-blocked,
- what prompts are visible,
- what mimics remain visible,
- what overlaps remain unresolved,
- what confidence limiters are active,
- what source status applies,
- what review prompts are visible,
- what authority envelope applies,
- what audit events occurred.

The session object must not hold:

- final diagnosis,
- excluded disease,
- excluded mimic,
- treatment plan,
- test order,
- procedure decision,
- follow-up interval,
- triage disposition,
- patient-facing advice,
- public-ready output,
- platform-wide clinical validation.

Case assembly rule:

> A reasoning session organizes state; it does not decide clinical truth.

---

## 6. Core Session Object Registry

The following objects are opened for v0.12 schema design.

| Object ID | Object Name | Purpose | Authority Risk |
|---|---|---|---|
| V12_OBJECT_001 | reasoning_session_object | Root governed session object | session-as-diagnosis risk |
| V12_OBJECT_002 | case_snapshot | Frozen case state at a point in time | snapshot-as-final-report risk |
| V12_OBJECT_003 | session_revision_history | Revision chain across evidence updates | revision-as-validation risk |
| V12_OBJECT_004 | intake_field_bindings | Links v0.11 fields to session state | supplied-evidence-as-authority risk |
| V12_OBJECT_005 | workspace_state_bindings | Links v0.10 components to session state | workspace-as-decision risk |
| V12_OBJECT_006 | structured_output_bindings | Links v0.9 layers to session state | output-as-diagnosis risk |
| V12_OBJECT_007 | source_status_bindings | Carries source role and limitation | source-as-validation risk |
| V12_OBJECT_008 | missing_evidence_bindings | Carries missing evidence across revisions | missing-as-exclusion risk |
| V12_OBJECT_009 | confidence_limiter_bindings | Carries interpretation limiters | limiter-as-probability risk |
| V12_OBJECT_010 | mimic_visibility_bindings | Carries high-risk mimic prompts | mimic-as-diagnosis risk |
| V12_OBJECT_011 | overlap_bindings | Carries unresolved coexistence states | forced-winner risk |
| V12_OBJECT_012 | review_prompt_bindings | Carries urgent and MDD review prompts | review-replacement risk |
| V12_OBJECT_013 | authority_envelope_binding | Persistent authority boundary | authority-hidden risk |
| V12_OBJECT_014 | audit_event_chain | Records state changes and guardrails | audit-as-validation risk |
| V12_OBJECT_015 | no_decision_object | Explicit block against decision objects | hidden-decision risk |

---

## 7. Reasoning Session Object — Entry Definition

The `reasoning_session_object` is the root object that assembles the current governed state of a case.

It may contain:

```yaml
reasoning_session_object:
  session_id: string
  session_version: string
  case_snapshot_current: object_ref
  revision_history: list
  intake_field_bindings: list
  workspace_state_bindings: list
  structured_output_bindings: list
  source_status_bindings: list
  missing_evidence_bindings: list
  confidence_limiter_bindings: list
  mimic_visibility_bindings: list
  overlap_bindings: list
  review_prompt_bindings: list
  authority_envelope_binding: object_ref
  audit_event_chain: list
  no_decision_object: object_ref
```

It must not contain:

```yaml
blocked_session_fields:
  final_diagnosis: blocked
  confirmed_diagnosis: blocked
  excluded_disease: blocked
  excluded_mimic: blocked
  treatment_plan: blocked
  test_order: blocked
  procedure_recommendation: blocked
  follow_up_schedule: blocked
  triage_decision: blocked
  patient_facing_summary: blocked
  public_ready_output: blocked
  clinical_validation_status: blocked
```

Session object rule:

> A reasoning session object is a governed assembly of reasoning state, not a clinical conclusion object.

---

## 8. Case Snapshot — Entry Definition

A `case_snapshot` freezes the current state of the session at a point in time.

It may capture:

- provided facts,
- missing fields,
- clinician-supplied evidence,
- inferred fact blocks,
- active prompts,
- active mimics,
- active overlaps,
- active confidence limiters,
- active source limitations,
- active urgent/MDD review prompts,
- authority envelope,
- audit reference.

It must not freeze:

- final diagnosis,
- excluded disease,
- excluded mimic,
- treatment plan,
- test order,
- procedure recommendation,
- follow-up schedule,
- triage decision,
- patient-facing report.

Snapshot rule:

> A snapshot freezes reasoning state; it does not freeze clinical truth.

---

## 9. Revision History — Entry Definition

`session_revision_history` records how the case state changes over time.

Allowed revision triggers:

- new intake field supplied,
- missing evidence updated,
- confidence limiter updated,
- source status updated,
- prompt visibility updated,
- workspace component refreshed,
- clinician note added,
- safe export created,
- guardrail triggered,
- correction or rollback recorded.

Blocked revision interpretations:

- revision proves diagnosis,
- revision proves exclusion,
- revision validates clinical correctness,
- revision replaces MDD,
- revision creates public readiness.

Revision rule:

> A revision records state movement, not clinical correctness.

---

## 10. Intake Field Binding — Entry Definition

`intake_field_bindings` link v0.11 intake fields into the session object.

Allowed binding states:

- provided_fact_bound,
- not_provided_bound,
- clinician_supplied_evidence_bound,
- report_supplied_fact_bound,
- uploaded_record_supplied_fact_bound,
- source_context_supplied_fact_bound,
- inferred_fact_blocked_bound,
- missing_evidence_visible_bound,
- authority_effect_none_bound.

Blocked binding states:

- diagnosis_created_from_binding,
- exclusion_created_from_binding,
- treatment_created_from_binding,
- order_created_from_binding,
- procedure_created_from_binding,
- follow_up_created_from_binding,
- triage_created_from_binding.

Binding rule:

> Intake binding carries provenance and state, not authority.

---

## 11. Workspace State Binding — Entry Definition

`workspace_state_bindings` link v0.10 workspace components into the session object.

Allowed bindings:

- reasoning_flow_layout_state,
- layer_card_state,
- source_status_badge_state,
- missing_evidence_panel_state,
- mimic_visibility_panel_state,
- temporal_comparison_panel_state,
- overlap_panel_state,
- uncertainty_panel_state,
- urgent_review_banner_state,
- MDD_review_panel_state,
- blocked_output_guardrail_state,
- authority_envelope_footer_state,
- audit_trail_state.

Blocked bindings:

- final_diagnosis_panel_state,
- treatment_plan_panel_state,
- order_next_test_state,
- biopsy_required_state,
- follow_up_scheduler_state,
- triage_disposition_state,
- patient_summary_state,
- public_ready_toggle_state.

Workspace binding rule:

> Workspace state binding preserves visibility state, not decision state.

---

## 12. Structured Output Binding — Entry Definition

`structured_output_bindings` link v0.9 output layers into the session object.

Allowed bindings:

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

Blocked bindings:

- final_diagnosis_layer,
- treatment_plan_layer,
- test_order_layer,
- procedure_decision_layer,
- follow_up_layer,
- patient_advice_layer.

Structured output binding rule:

> Output layers remain reasoning layers, not clinical decision layers.

---

## 13. Source Status Binding — Entry Definition

`source_status_bindings` preserve source role, claim mapping, and limitations inside the session object.

Allowed fields:

- source_id,
- source_role_class,
- claim_mapping_status,
- source_limitations,
- treatment_heavy_warning,
- diagnostic_performance_warning,
- case_example_only_warning,
- narrow_reviewed_scope_metadata,
- platform_wide_review_false.

Blocked meanings:

- clinically_validated,
- diagnosis_confirmed,
- treatment_supported,
- test_order_supported,
- procedure_supported,
- public_ready,
- patient_ready.

Source binding rule:

> Source status explains reasoning support and limitation; it does not authorize a clinical conclusion.

---

## 14. Missing Evidence Binding — Entry Definition

`missing_evidence_bindings` preserve missingness across session revisions.

Allowed states:

- missing,
- partially_supplied,
- supplied_by_clinician,
- source_limited,
- conflicting,
- no_longer_missing_but_still_limited.

Blocked states:

- disease_excluded,
- mimic_excluded,
- benign,
- safe,
- no_review_needed,
- no_urgent_review_needed.

Missing evidence binding rule:

> Missing evidence may persist, update, or resolve; it may not exclude.

---

## 15. Confidence Limiter Binding — Entry Definition

`confidence_limiter_bindings` preserve interpretation limiters across revisions.

Allowed states:

- active,
- updated,
- reduced,
- resolved_by_supplied_evidence,
- replaced_by_new_limiter,
- source_limited,
- conflicting_evidence_present.

Blocked states:

- diagnostic_confidence_score,
- disease_probability,
- final_rank,
- exclusion_score,
- safety_clearance,
- treatment_threshold.

Confidence limiter binding rule:

> Confidence limiters explain interpretation limits, not diagnostic certainty.

---

## 16. Mimic Visibility Binding — Entry Definition

`mimic_visibility_bindings` preserve high-risk mimic visibility.

Allowed states:

- mimic_prompt_visible,
- mimic_prompt_not_triggered,
- mimic_source_limited,
- mimic_missing_evidence_limited,
- mimic_overlap_visible,
- mimic_review_visible.

Blocked states:

- mimic_confirmed,
- mimic_excluded,
- mimic_treatment_triggered,
- mimic_test_order_triggered,
- mimic_procedure_triggered.

Mimic binding rule:

> Mimic visibility prevents unsafe closure without creating mimic diagnosis.

---

## 17. Overlap Binding — Entry Definition

`overlap_bindings` preserve unresolved coexistence and boundary states.

Allowed states:

- overlap_visible,
- overlap_unresolved,
- overlap_source_limited,
- overlap_missing_evidence_limited,
- overlap_conflict_visible,
- overlap_deferred_to_review.

Blocked states:

- winner_selected,
- secondary_process_excluded,
- mimic_suppressed,
- final_label_selected.

Overlap binding rule:

> Overlap remains coexistence, not forced closure.

---

## 18. Review Prompt Binding — Entry Definition

`review_prompt_bindings` preserve urgent and MDD review prompts.

Allowed states:

- urgent_review_prompt_visible,
- urgent_review_prompt_not_triggered,
- urgent_review_prompt_source_limited,
- MDD_review_prompt_visible,
- MDD_review_prompt_not_triggered,
- specialist_review_prompt_visible.

Blocked states:

- triage_decision_made,
- emergency_disposition_selected,
- outpatient_safe_declared,
- MDD_replaced,
- MDD_unnecessary,
- specialist_review_replaced.

Review binding rule:

> Review prompts remain visibility prompts, not review replacement.

---

## 19. Authority Envelope Binding — Entry Definition

`authority_envelope_binding` must be present in every session object.

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

- hidden,
- editable,
- removed_from_session,
- overridden_by_user,
- overridden_by_export,
- public_ready_true,
- patient_facing_enabled,
- clinically_reviewed_platform_wide_true.

Authority binding rule:

> The authority envelope must persist across the entire reasoning session.

---

## 20. Audit Event Chain — Entry Definition

`audit_event_chain` records session events.

Allowed audit events:

- session_created,
- case_snapshot_created,
- intake_field_bound,
- workspace_state_bound,
- structured_output_layer_bound,
- source_status_bound,
- missing_evidence_bound,
- confidence_limiter_bound,
- mimic_visibility_bound,
- overlap_bound,
- review_prompt_bound,
- evidence_update_recorded,
- workspace_refresh_recorded,
- guardrail_triggered,
- clinician_note_added,
- safe_export_created,
- case_snapshot_revised,
- session_closed.

Blocked audit interpretations:

- diagnosis_validated,
- treatment_authorized,
- test_ordered,
- procedure_recommended,
- follow_up_scheduled,
- triage_completed,
- MDD_completed_by_platform,
- clinical_validation_confirmed,
- public_ready_enabled.

Audit chain rule:

> Audit chain records session state movement; it does not certify clinical correctness.

---

## 21. No-Decision Object — Entry Definition

The `no_decision_object` is an explicit governance block inside the session.

It must state:

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
```

No-decision object rule:

> The session must explicitly remember what it is not allowed to become.

---

## 22. Case Assembly State Flow

Allowed state flow:

```yaml
case_assembly_flow:
  step_1_create_session:
    creates: reasoning_session_object
    authority_effect: none

  step_2_bind_intake_fields:
    uses: v0.11 intake fields
    preserves: provided_vs_inferred_boundary

  step_3_bind_workspace_state:
    uses: v0.10 workspace components
    preserves: reasoning_visibility_surface

  step_4_bind_structured_output_layers:
    uses: v0.9 structured output layers
    preserves: non_authoritative_output

  step_5_bind_missing_evidence_and_limiters:
    preserves:
      - missing_evidence_not_exclusion
      - confidence_limiter_not_probability

  step_6_bind_source_status:
    preserves: source_status_not_validation

  step_7_bind_authority_envelope:
    required: true

  step_8_record_audit_event:
    audit_not_validation: true

  step_9_create_case_snapshot:
    snapshot_not_final_report: true
```

Blocked state flow outputs:

- diagnosis_created,
- exclusion_created,
- treatment_created,
- test_order_created,
- procedure_decision_created,
- follow_up_created,
- triage_created,
- public_ready_created,
- patient_facing_created,
- platform_wide_clinical_review_created.

Case assembly flow rule:

> The session may assemble governed reasoning state only.

---

## 23. Case Snapshot and Revision Safety

Case snapshots may be created:

- at session start,
- after evidence update,
- after workspace refresh,
- before safe export,
- after guardrail event,
- after clinician note,
- at session close.

Case snapshots must preserve:

- authority envelope,
- provided-vs-inferred boundary,
- missing evidence state,
- source status limitations,
- confidence limiters,
- mimic visibility,
- overlap visibility,
- review prompts,
- audit references.

Case snapshots must not become:

- diagnostic report,
- treatment report,
- test order report,
- procedure recommendation,
- follow-up schedule,
- patient-facing summary.

Snapshot rule:

> Case snapshot is a frozen reasoning state, not a frozen clinical conclusion.

---

## 24. Session Export Boundary

v0.12 may later define session-level exports.

Allowed export concepts:

- governance-safe session summary,
- case snapshot summary,
- missing evidence state export,
- source status export,
- confidence limiter export,
- MDD preparation export,
- audit event chain export,
- authority envelope export.

Blocked export concepts:

- final diagnostic report,
- treatment plan,
- test order recommendation,
- procedure recommendation,
- follow-up schedule,
- triage report,
- patient-facing report,
- public-ready report,
- clinically validated report.

Export boundary rule:

> A session export may summarize governed reasoning state; it may not summarize clinical authority.

---

## 25. Case Assembly Red-Team Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| Session object contains final_diagnosis field | block decision object |
| Case snapshot is exported as diagnostic report | block unsafe export |
| Intake binding converts honeycombing to IPF | block pattern-to-diagnosis |
| Missing exposure field excludes HP | block missing-as-exclusion |
| Microbiology missing excludes TB | block missing microbiology exclusion |
| Pathology binding confirms sarcoidosis from granulomas | block pathology-alone diagnosis |
| Source binding marks clinically validated | block source-to-validation |
| Confidence limiter becomes IPF probability | block limiter-to-probability |
| Workspace binding adds treatment panel | block decision control |
| Urgent review binding assigns disposition | block triage |
| MDD binding creates final consensus | block MDD replacement |
| Audit chain confirms correctness | block audit-to-validation |
| Authority envelope removed from snapshot | block authority boundary loss |
| Patient-facing summary generated | block patient-facing output |
| Public-ready toggle added | block deployment claim |

---

## 26. v0.12.0 Acceptance Criteria

v0.12.0 is accepted only if:

- v0.12 opens as case assembly governance,
- reasoning session object scope is defined,
- case snapshot scope is defined,
- revision history scope is defined,
- intake field bindings are defined,
- workspace state bindings are defined,
- structured output bindings are defined,
- source status bindings are defined,
- missing evidence bindings are defined,
- confidence limiter bindings are defined,
- mimic visibility bindings are defined,
- overlap bindings are defined,
- review prompt bindings are defined,
- authority envelope binding is required,
- audit event chain is defined,
- no-decision object is defined,
- case assembly state flow is defined,
- session export boundary is defined,
- red-team case assembly failures are blocked,
- no diagnosis object is opened,
- no treatment object is opened,
- no test order object is opened,
- no procedure decision object is opened,
- no follow-up schedule object is opened,
- no triage object is opened,
- no public-ready object is opened,
- no patient-facing object is opened,
- no platform-wide clinical review object is opened.

---

## 27. Next Step

The next recommended step is:

- v0.12.1 — Reasoning Session Object Schema

v0.12.1 should define detailed schema for:

- reasoning_session_object,
- case_snapshot,
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
- no_decision_object.

v0.12.1 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 28. Governance Statement

This entry gate opens case assembly and reasoning session object governance.

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

The v0.12 entry rule is:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”