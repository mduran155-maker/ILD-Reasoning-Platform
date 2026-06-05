# ILD Reasoning Platform — Reasoning Session Object Schema v1

Version: v0.12.1  
Status: reasoning_session_object_schema  
Scope: Detailed schema for governed reasoning session object, case snapshots, bindings, audit chain, and no-decision constraints  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the detailed schema for v0.12 — Case Assembly / Reasoning Session Object Contract.

It follows:

- `docs/navigation/case_assembly_reasoning_session_entry_gate_v1.md`
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

Its purpose is to define how a governed reasoning session object assembles:

- evidence intake fields,
- case snapshots,
- session revisions,
- workspace state,
- structured output layers,
- source status,
- missing evidence,
- confidence limiters,
- mimic visibility,
- overlap,
- urgent and MDD review prompts,
- authority envelope,
- audit event chain,
- no-decision constraints.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.1:

> “A reasoning session object is valid only if every bound state remains provenance-aware, visibility-oriented, audit-linked, and authority-neutral.”

---

## 2. Global Session Object Contract

Every session object must preserve:

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

No object, binding, snapshot, revision, export, or audit event may override the authority envelope.

---

## 3. Root Reasoning Session Object

### 3.1 Purpose

The `reasoning_session_object` is the root governed object for a single case reasoning session.

It assembles state from:

- v0.11 evidence intake,
- v0.10 clinician workspace,
- v0.9 structured output contract,
- source governance,
- audit trail,
- authority envelope.

It is not a clinical conclusion object.

### 3.2 Required Schema

```yaml
reasoning_session_object:
  session_id: string
  session_schema_version: reasoning_session_object_schema_v1
  session_status: active | closed | archived | superseded
  created_at: implementation_defined
  updated_at: implementation_defined
  created_by: clinician | system | unknown
  case_snapshot_current: case_snapshot_ref
  case_snapshot_history: list[case_snapshot_ref]
  session_revision_history: session_revision_history
  intake_field_bindings: list[intake_field_binding]
  workspace_state_bindings: list[workspace_state_binding]
  structured_output_bindings: list[structured_output_binding]
  source_status_bindings: list[source_status_binding]
  missing_evidence_bindings: list[missing_evidence_binding]
  confidence_limiter_bindings: list[confidence_limiter_binding]
  mimic_visibility_bindings: list[mimic_visibility_binding]
  overlap_bindings: list[overlap_binding]
  review_prompt_bindings: list[review_prompt_binding]
  authority_envelope_binding: authority_envelope_binding
  audit_event_chain: audit_event_chain
  no_decision_object: no_decision_object
```

### 3.3 Required Authority Fields

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

### 3.4 Blocked Root Fields

The root session object must not contain:

```yaml
blocked_root_fields:
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

### 3.5 Root Object Rule

> The root session object assembles governed reasoning state; it does not assemble clinical truth.

---

## 4. Case Snapshot Object

### 4.1 Purpose

The `case_snapshot` freezes the current governed reasoning state at a point in time.

It is useful for audit, revision history, safe export, and session continuity.

It is not a final report.

### 4.2 Required Schema

```yaml
case_snapshot:
  snapshot_id: string
  session_id: string
  snapshot_index: integer
  created_at: implementation_defined
  created_reason:
    - session_created
    - evidence_updated
    - workspace_refreshed
    - guardrail_triggered
    - clinician_note_added
    - safe_export_created
    - session_closed
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
  audit_event_refs: list[audit_event_ref]
  no_decision_object_ref: no_decision_object_ref
```

### 4.3 Required Snapshot Flags

```yaml
snapshot_is_final_report: false
snapshot_is_patient_facing: false
snapshot_is_public_ready: false
snapshot_is_clinically_validated: false
snapshot_authority_effect: none
```

### 4.4 Blocked Snapshot Fields

Blocked:

- final diagnosis,
- confirmed diagnosis,
- ruled-out disease,
- treatment plan,
- test recommendation,
- procedure recommendation,
- follow-up schedule,
- triage disposition,
- patient-facing advice,
- public-ready status.

### 4.5 Snapshot Rule

> A case snapshot freezes reasoning state, not clinical conclusion.

---

## 5. Session Revision History

### 5.1 Purpose

`session_revision_history` records state changes over the session timeline.

Revision history does not validate correctness.

### 5.2 Required Schema

```yaml
session_revision_history:
  revision_count: integer
  revisions: list[session_revision]
```

```yaml
session_revision:
  revision_id: string
  session_id: string
  revision_index: integer
  revision_reason:
    - intake_field_added
    - intake_field_updated
    - missing_evidence_updated
    - confidence_limiter_updated
    - prompt_visibility_updated
    - workspace_component_refreshed
    - source_status_updated
    - clinician_note_added
    - guardrail_triggered
    - correction_recorded
    - safe_export_created
    - session_closed
  previous_snapshot_id: string_or_null
  new_snapshot_id: string
  changed_bindings: list
  audit_event_refs: list
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

### 5.3 Blocked Revision Interpretations

Revision history must not mean:

- diagnosis improved,
- diagnosis confirmed,
- disease excluded,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- MDD completed,
- clinical validation achieved.

### 5.4 Revision Rule

> A revision records state movement, not clinical correctness.

---

## 6. Intake Field Binding

### 6.1 Purpose

`intake_field_binding` links v0.11 intake fields into the session object.

It carries provenance, missingness, field state, affected prompts, confidence limiters, source links, and authority-neutral status.

### 6.2 Required Schema

```yaml
intake_field_binding:
  binding_id: string
  session_id: string
  field_id: string
  field_name: string
  intake_domain_id: string
  intake_domain_name: string
  field_state:
    - provided_fact
    - not_provided
    - clinician_supplied_evidence
    - report_supplied_fact
    - uploaded_record_supplied_fact
    - source_context_supplied_fact
    - inferred_fact_blocked
    - missing_evidence_visible
    - source_linked
    - evidence_update_audited
  value: any_or_null
  value_source:
    - clinician_supplied
    - user_supplied
    - report_supplied
    - uploaded_record_supplied
    - source_context_supplied
    - not_provided
    - blocked_inference
  provided_by: clinician | user | report | uploaded_record | source_context | platform | unknown
  inference_allowed: false_unless_explicit_non_clinical_metadata
  inferred_fact_blocked: true_or_false
  missing_evidence_visible: true_or_false
  affected_prompt_refs: list
  source_status_refs: list
  confidence_limiter_refs: list
  audit_event_refs: list
  authority_effect: none
```

### 6.3 Blocked Binding Effects

An intake binding must not create:

- diagnosis,
- exclusion,
- treatment,
- order,
- procedure decision,
- follow-up,
- triage,
- public-ready output,
- patient-facing output,
- platform-wide clinical review.

### 6.4 Binding Rule

> Intake binding carries field state and provenance, not clinical authority.

---

## 7. Workspace State Binding

### 7.1 Purpose

`workspace_state_binding` links v0.10 clinician workspace components into the session.

It preserves UI visibility state without creating decision controls.

### 7.2 Required Schema

```yaml
workspace_state_binding:
  binding_id: string
  session_id: string
  component_id: string
  component_name:
    - reasoning_flow_layout
    - layer_cards
    - source_status_badges
    - missing_evidence_panel
    - mimic_visibility_panel
    - temporal_comparison_panel
    - overlap_panel
    - uncertainty_panel
    - urgent_review_banner
    - MDD_review_panel
    - blocked_output_guardrails
    - authority_envelope_footer
    - audit_trail
  component_state:
    - visible
    - collapsed
    - expanded
    - locked_visible
    - source_limited
    - prompt_visible
    - missing_evidence_visible
    - urgent_prompt_visible
    - review_prompt_visible
    - authority_block_active
    - audit_recorded
  linked_intake_fields: list
  linked_output_layers: list
  linked_audit_events: list
  authority_effect: none
```

### 7.3 Blocked Workspace States

Blocked:

- final diagnosis panel,
- treatment plan panel,
- order next test button,
- biopsy required banner,
- follow-up scheduler,
- triage disposition banner,
- patient-ready summary,
- public-ready toggle,
- clinically validated badge.

### 7.4 Workspace Binding Rule

> Workspace binding preserves display state, not decision state.

---

## 8. Structured Output Binding

### 8.1 Purpose

`structured_output_binding` links v0.9 structured output layers into the session.

### 8.2 Required Schema

```yaml
structured_output_binding:
  binding_id: string
  session_id: string
  output_layer_id: string
  output_layer_name:
    - case_context_summary
    - temporal_change_summary
    - pattern_family_prompts
    - differential_prompt_layer
    - overlap_layer
    - high_risk_mimic_layer
    - missing_evidence_layer
    - uncertainty_layer
    - urgent_review_prompt_layer
    - MDD_review_prompt_layer
    - source_status_layer
    - authority_envelope
    - blocked_outputs
  layer_state:
    - visible
    - not_triggered
    - source_limited
    - missing_evidence_limited
    - uncertainty_limited
    - review_visible
    - blocked_output_active
  linked_intake_fields: list
  linked_workspace_components: list
  linked_source_status_refs: list
  linked_audit_events: list
  authority_effect: none
```

### 8.3 Blocked Output Bindings

Blocked:

- final_diagnosis_layer,
- confirmed_diagnosis_layer,
- disease_exclusion_layer,
- treatment_plan_layer,
- test_order_layer,
- procedure_decision_layer,
- follow_up_layer,
- triage_layer,
- patient_advice_layer.

### 8.4 Structured Output Binding Rule

> Structured output bindings remain reasoning layers, not clinical decision layers.

---

## 9. Source Status Binding

### 9.1 Purpose

`source_status_binding` carries source role, claim mapping, source limitations, and source-scope metadata into the session.

### 9.2 Required Schema

```yaml
source_status_binding:
  binding_id: string
  session_id: string
  source_id: string
  source_role_class:
    - primary_high_authority
    - primary_limited_scope
    - auxiliary_review
    - diagnostic_performance_study
    - case_example_cautionary
    - internal_governance
  claim_mapping_status:
    - claim_mapped
    - partially_mapped
    - source_limited
    - not_mapped
    - internal_governance_only
  source_limitations: list
  treatment_heavy_warning: string_or_null
  diagnostic_performance_warning: string_or_null
  case_example_only_warning: string_or_null
  narrow_reviewed_scope_metadata: list
  platform_wide_review_false: true
  linked_intake_fields: list
  linked_output_layers: list
  linked_workspace_components: list
  authority_effect: none
```

### 9.3 Blocked Source Binding Meanings

Blocked:

- clinically validated,
- diagnosis confirmed,
- treatment supported,
- test order supported,
- procedure supported,
- public ready,
- patient ready.

### 9.4 Source Binding Rule

> Source status explains support and limitation; it does not authorize clinical conclusion.

---

## 10. Missing Evidence Binding

### 10.1 Purpose

`missing_evidence_binding` preserves missingness across session state and revisions.

### 10.2 Required Schema

```yaml
missing_evidence_binding:
  binding_id: string
  session_id: string
  missing_item_id: string
  missing_item_label: string
  missing_state:
    - missing
    - partially_supplied
    - supplied_by_clinician
    - source_limited
    - conflicting
    - no_longer_missing_but_still_limited
  linked_intake_fields: list
  affected_prompts: list
  linked_workspace_components: list
  confidence_limiter_refs: list
  mimic_visibility_refs: list
  overlap_refs: list
  review_prompt_refs: list
  audit_event_refs: list
  exclusion_effect: none
  authority_effect: none
```

### 10.3 Blocked Missing Evidence States

Blocked:

- disease_excluded,
- mimic_excluded,
- benign,
- safe,
- no_review_needed,
- no_urgent_review_needed.

### 10.4 Missing Evidence Binding Rule

> Missing evidence may persist, update, or resolve; it may not exclude.

---

## 11. Confidence Limiter Binding

### 11.1 Purpose

`confidence_limiter_binding` carries interpretation limiters across the session.

It replaces diagnostic confidence.

### 11.2 Required Schema

```yaml
confidence_limiter_binding:
  binding_id: string
  session_id: string
  limiter_id: string
  limiter_type:
    - missing
    - incomplete
    - source_limited
    - unresolved
    - conflicting
    - temporal_limited
    - review_not_documented
  limiter_state:
    - active
    - updated
    - reduced
    - resolved_by_supplied_evidence
    - replaced_by_new_limiter
    - source_limited
    - conflicting_evidence_present
  linked_intake_fields: list
  affected_prompts: list
  linked_missing_evidence: list
  linked_source_status: list
  audit_event_refs: list
  diagnostic_confidence_created: false
  probability_created: false
  authority_effect: none
```

### 11.3 Blocked Limiter States

Blocked:

- diagnostic_confidence_score,
- disease_probability,
- final_rank,
- exclusion_score,
- safety_clearance,
- treatment_threshold.

### 11.4 Confidence Limiter Rule

> Confidence limiters explain interpretation limits, not diagnostic certainty.

---

## 12. Mimic Visibility Binding

### 12.1 Purpose

`mimic_visibility_binding` preserves high-risk mimic prompt visibility inside the session.

### 12.2 Required Schema

```yaml
mimic_visibility_binding:
  binding_id: string
  session_id: string
  mimic_prompt_id: string
  mimic_family:
    - infection_mimic
    - TB_mimic
    - NTM_mimic
    - fungal_mimic
    - aspiration_mimic
    - occupational_ILD_mimic
    - beryllium_sarcoid_mimic
    - drug_induced_ILD_mimic
    - radiation_pneumonitis_mimic
    - checkpoint_inhibitor_pneumonitis_mimic
    - ICI_sarcoid_like_reaction_mimic
    - PLC_malignancy_mimic
    - lymphoma_recurrence_mimic
    - sarcoid_like_reaction_mimic
    - acute_danger_overlay
  mimic_state:
    - mimic_prompt_visible
    - mimic_prompt_not_triggered
    - mimic_source_limited
    - mimic_missing_evidence_limited
    - mimic_overlap_visible
    - mimic_review_visible
  linked_intake_fields: list
  linked_missing_evidence: list
  linked_confidence_limiters: list
  linked_overlap_refs: list
  linked_source_status: list
  audit_event_refs: list
  diagnosis_status: not_diagnosed
  exclusion_status: not_excluded
  treatment_status: not_recommended
  authority_effect: none
```

### 12.3 Blocked Mimic States

Blocked:

- mimic_confirmed,
- mimic_excluded,
- mimic_treatment_triggered,
- mimic_test_order_triggered,
- mimic_procedure_triggered.

### 12.4 Mimic Binding Rule

> Mimic visibility prevents unsafe closure without creating mimic diagnosis.

---

## 13. Overlap Binding

### 13.1 Purpose

`overlap_binding` preserves unresolved coexistence and boundary states.

### 13.2 Required Schema

```yaml
overlap_binding:
  binding_id: string
  session_id: string
  overlap_id: string
  overlap_family:
    - UIP_vs_HP_overlap
    - UIP_vs_CTD_ILD_overlap
    - HP_vs_CTD_ILD_overlap
    - CTD_ILD_vs_NSIP_overlap
    - NSIP_vs_OP_overlap
    - OP_vs_infection_overlap
    - OP_vs_aspiration_overlap
    - sarcoidosis_vs_infection_overlap
    - sarcoidosis_vs_beryllium_overlap
    - sarcoidosis_vs_malignancy_overlap
    - drug_induced_ILD_vs_NSIP_OP_overlap
    - radiation_pneumonitis_vs_infection_recurrence_overlap
    - CIP_vs_infection_progression_overlap
    - PLC_vs_ILD_infection_edema_overlap
    - acute_overlay_vs_chronic_fibrosis_overlap
  overlap_state:
    - overlap_visible
    - overlap_unresolved
    - overlap_source_limited
    - overlap_missing_evidence_limited
    - overlap_conflict_visible
    - overlap_deferred_to_review
  involved_prompts: list
  linked_intake_fields: list
  linked_mimic_visibility: list
  linked_missing_evidence: list
  linked_confidence_limiters: list
  audit_event_refs: list
  closure_status: not_established
  authority_effect: none
```

### 13.3 Blocked Overlap States

Blocked:

- winner_selected,
- secondary_process_excluded,
- mimic_suppressed,
- final_label_selected.

### 13.4 Overlap Binding Rule

> Overlap remains coexistence, not forced closure.

---

## 14. Review Prompt Binding

### 14.1 Purpose

`review_prompt_binding` preserves urgent review and MDD/specialist review visibility.

### 14.2 Required Schema

```yaml
review_prompt_binding:
  binding_id: string
  session_id: string
  review_prompt_id: string
  review_prompt_type:
    - urgent_review_prompt
    - MDD_review_prompt
    - specialist_review_prompt
  review_prompt_state:
    - urgent_review_prompt_visible
    - urgent_review_prompt_not_triggered
    - urgent_review_prompt_source_limited
    - MDD_review_prompt_visible
    - MDD_review_prompt_not_triggered
    - specialist_review_prompt_visible
  specialist_domains:
    - pulmonology
    - thoracic_radiology
    - pathology
    - microbiology
    - rheumatology
    - occupational_medicine
    - oncology
    - radiation_oncology
    - urgent_clinical_assessment
    - multidisciplinary_discussion
  linked_intake_fields: list
  linked_workspace_components: list
  linked_output_layers: list
  audit_event_refs: list
  authority_effect: none
```

### 14.3 Blocked Review States

Blocked:

- triage_decision_made,
- emergency_disposition_selected,
- outpatient_safe_declared,
- MDD_replaced,
- MDD_unnecessary,
- specialist_review_replaced,
- consensus_created_by_platform.

### 14.4 Review Binding Rule

> Review prompts remain visibility prompts, not review replacement.

---

## 15. Authority Envelope Binding

### 15.1 Purpose

`authority_envelope_binding` is mandatory for every session object, snapshot, revision, and export.

### 15.2 Required Schema

```yaml
authority_envelope_binding:
  binding_id: string
  session_id: string
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
  replacement_of_MDD: not_allowed
  replacement_of_clinician: not_allowed
  replacement_of_specialist_review: not_allowed
  replacement_of_urgent_review: not_allowed
  mutable: false
  removable: false
  export_required: true
```

### 15.3 Blocked Authority Envelope States

Blocked:

- hidden,
- editable,
- removed_from_session,
- overridden_by_user,
- overridden_by_export,
- public_ready_true,
- patient_facing_enabled,
- clinically_reviewed_platform_wide_true,
- diagnostic_authority_enabled,
- treatment_authority_enabled.

### 15.4 Authority Binding Rule

> The authority envelope must persist across the entire reasoning session.

---

## 16. Audit Event Chain

### 16.1 Purpose

`audit_event_chain` records session state movement.

It does not certify clinical correctness.

### 16.2 Required Schema

```yaml
audit_event_chain:
  chain_id: string
  session_id: string
  event_count: integer
  events: list[audit_event]
```

```yaml
audit_event:
  audit_event_id: string
  session_id: string
  event_type:
    - session_created
    - case_snapshot_created
    - intake_field_bound
    - workspace_state_bound
    - structured_output_layer_bound
    - source_status_bound
    - missing_evidence_bound
    - confidence_limiter_bound
    - mimic_visibility_bound
    - overlap_bound
    - review_prompt_bound
    - evidence_update_recorded
    - workspace_refresh_recorded
    - guardrail_triggered
    - clinician_note_added
    - safe_export_created
    - case_snapshot_revised
    - session_closed
  event_payload: object
  linked_bindings: list
  previous_snapshot_id: string_or_null
  new_snapshot_id: string_or_null
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

### 16.3 Blocked Audit Interpretations

Blocked:

- diagnosis_validated,
- treatment_authorized,
- test_ordered,
- procedure_recommended,
- follow_up_scheduled,
- triage_completed,
- MDD_completed_by_platform,
- clinical_validation_confirmed,
- public_ready_enabled.

### 16.4 Audit Chain Rule

> Audit chain records session state movement; it does not certify clinical correctness.

---

## 17. No-Decision Object

### 17.1 Purpose

`no_decision_object` is a mandatory explicit object that prevents hidden decision object creation.

### 17.2 Required Schema

```yaml
no_decision_object:
  object_id: string
  session_id: string
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

### 17.3 Required Assertion

```yaml
no_decision_assertion:
  session_contains_decision_object: false
  session_contains_authority_override: false
  session_contains_patient_facing_output: false
  session_contains_public_ready_output: false
```

### 17.4 No-Decision Rule

> The session must explicitly remember what it is not allowed to become.

---

## 18. Session Object Assembly Flow

### 18.1 Allowed Flow

```yaml
session_assembly_flow:
  create_session:
    creates: reasoning_session_object
    authority_effect: none

  bind_intake_fields:
    source: v0.11
    preserves: provided_vs_inferred_boundary

  bind_workspace_state:
    source: v0.10
    preserves: reasoning_visibility_surface

  bind_structured_output_layers:
    source: v0.9
    preserves: non_authoritative_output

  bind_missing_evidence:
    preserves: missing_evidence_not_exclusion

  bind_confidence_limiters:
    preserves: limiter_not_probability

  bind_source_status:
    preserves: source_status_not_validation

  bind_mimics_and_overlap:
    preserves:
      - mimic_not_diagnosis
      - overlap_not_winner_selection

  bind_review_prompts:
    preserves:
      - urgent_review_not_triage
      - MDD_not_replacement

  bind_authority_envelope:
    required: true

  bind_audit_chain:
    audit_not_validation: true

  create_case_snapshot:
    snapshot_not_final_report: true

  bind_no_decision_object:
    required: true
```

### 18.2 Blocked Flow Outputs

Blocked:

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

### 18.3 Assembly Rule

> Session assembly may bind governed state only.

---

## 19. Session Export Boundary

### 19.1 Allowed Session Export Types

Allowed:

- governance_safe_session_summary,
- case_snapshot_summary,
- missing_evidence_state_export,
- source_status_export,
- confidence_limiter_export,
- mimic_visibility_export,
- overlap_visibility_export,
- MDD_preparation_export,
- audit_event_chain_export,
- authority_envelope_export.

### 19.2 Required Export Contents

Every session-level export must include:

- non-authority statement,
- authority envelope,
- missing evidence status where relevant,
- source status limitations where relevant,
- confidence limiters where relevant,
- mimic visibility where relevant,
- overlap where relevant,
- audit reference,
- blocked output notice.

### 19.3 Blocked Session Export Types

Blocked:

- final diagnostic report,
- treatment plan,
- test order recommendation,
- procedure recommendation,
- follow-up schedule,
- triage report,
- patient-facing report,
- public-ready report,
- clinically validated report.

### 19.4 Export Boundary Rule

> A session export may summarize governed reasoning state; it may not summarize clinical authority.

---

## 20. Session Object Red-Team Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| session object contains final_diagnosis | block decision field |
| snapshot exported as diagnostic report | block unsafe export |
| intake binding converts honeycombing to IPF | block pattern-to-diagnosis |
| missing exposure excludes HP | block missing-as-exclusion |
| microbiology missing excludes TB | block missing microbiology exclusion |
| granulomas confirm sarcoidosis | block pathology-alone diagnosis |
| source binding marks clinically validated | block source-to-validation |
| confidence limiter becomes IPF probability | block limiter-to-probability |
| workspace binding adds treatment panel | block decision control |
| urgent review binding assigns disposition | block triage |
| MDD binding creates consensus | block MDD replacement |
| audit chain confirms correctness | block audit-to-validation |
| authority envelope removed | block authority loss |
| patient-facing summary generated | block patient-facing output |
| public-ready toggle added | block deployment claim |

---

## 21. v0.12.1 Acceptance Criteria

v0.12.1 is accepted only if:

- root reasoning session object schema is defined,
- case snapshot schema is defined,
- session revision history schema is defined,
- intake field binding schema is defined,
- workspace state binding schema is defined,
- structured output binding schema is defined,
- source status binding schema is defined,
- missing evidence binding schema is defined,
- confidence limiter binding schema is defined,
- mimic visibility binding schema is defined,
- overlap binding schema is defined,
- review prompt binding schema is defined,
- authority envelope binding schema is defined and mandatory,
- audit event chain schema is defined,
- no-decision object schema is defined and mandatory,
- session object assembly flow is defined,
- session export boundary is defined,
- red-team session object failures are blocked,
- no final diagnosis field is allowed,
- no treatment plan field is allowed,
- no test order field is allowed,
- no procedure decision field is allowed,
- no follow-up schedule field is allowed,
- no triage field is allowed,
- no public-ready output is allowed,
- no patient-facing output is allowed,
- no platform-wide clinical review field is allowed.

---

## 22. Next Step

The next recommended step is:

- v0.12.2 — Case Snapshot / Revision History Contract

v0.12.2 should define:

- snapshot creation rules,
- snapshot revision triggers,
- snapshot immutability,
- correction and supersession rules,
- session revision chain,
- diff between snapshots,
- audit linkage,
- safe session export from snapshot,
- no final-report conversion,
- no diagnosis,
- no treatment,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no patient-facing use,
- no public readiness,
- no platform-wide clinical review.

---

## 23. Governance Statement

This schema defines the governed reasoning session object.

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

The reasoning session object remains a governed case-state assembly, not a clinical decision object.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.12 rule remains:

> “A reasoning session may assemble case state, but it must not assemble a diagnosis, treatment plan, order, procedure decision, follow-up schedule, triage decision, public-ready output, or patient-facing product.”

For v0.12.1:

> “A reasoning session object is valid only if every bound state remains provenance-aware, visibility-oriented, audit-linked, and authority-neutral.”