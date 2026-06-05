# ILD Reasoning Platform — Demo Reasoning Session / Snapshot / Export Fixture Schema v1

Version: v0.14.2  
Status: demo_reasoning_session_snapshot_export_fixture_schema  
Scope: Demo reasoning sessions, intake bindings, workspace state, structured output fixtures, snapshots, revision history, safe exports, MDD preparation packages, unsafe export failures, audit events, and fixture consistency rules  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the demo reasoning session, snapshot, and export fixture schema for v0.14 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract.

It follows:

- `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md`
- `docs/data/schema/synthetic_demo_case_object_schema_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_13.md`
- `docs/navigation/safe_session_export_mdd_preparation_structural_seal_v1.md`
- `docs/navigation/case_assembly_reasoning_session_structural_seal_v1.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

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

Its purpose is to define how a synthetic demo case becomes a governed demo reasoning session, demo snapshot, demo revision history, demo safe export, demo MDD preparation package, unsafe export failure fixture, and audit-linked scenario artifact.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.2:

> “A demo session fixture is valid only if synthetic case state can travel through intake, workspace, structured output, snapshot, revision, export, failure, and audit fixtures without becoming clinical authority.”

---

## 2. Global Demo Fixture Contract

Every demo fixture must preserve:

| Constraint | Required State |
|---|---|
| synthetic_only | true |
| real_patient_data | false |
| deidentified_real_patient_data | false |
| clinical_validation_use | false |
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| product_ready | false |
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

No demo fixture, sample session, sample snapshot, sample export, red-team fixture, validation result, audit event, or artifact metadata may override this contract.

---

## 3. Demo Fixture Chain

The v0.14.2 fixture chain is:

```text
synthetic_demo_case
→ demo_reasoning_session_object
→ demo_intake_binding_fixture
→ demo_workspace_state_fixture
→ demo_structured_output_fixture
→ demo_case_snapshot_fixture
→ demo_revision_history_fixture
→ demo_safe_export_fixture
→ demo_MDD_preparation_package_fixture
→ demo_unsafe_export_failure_fixture where relevant
→ demo_audit_event_fixture
```

The fixture chain may demonstrate:

- synthetic intake propagation,
- missing evidence preservation,
- source status limitation preservation,
- confidence limiter visibility,
- high-risk mimic visibility,
- overlap preservation,
- review prompt visibility,
- authority envelope persistence,
- no-decision object persistence,
- snapshot creation,
- safe export,
- unsafe export fail-closed behavior,
- audit traceability.

The fixture chain must not demonstrate:

- final diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment plan,
- test order,
- procedure recommendation,
- follow-up schedule,
- triage decision,
- patient-facing output,
- public-ready output,
- clinical validation,
- MDD consensus.

Fixture chain rule:

> Demo fixtures may show the platform moving reasoning state safely; they must not show the platform making clinical decisions.

---

## 4. Demo Reasoning Session Object Fixture

### 4.1 Purpose

The `demo_reasoning_session_object` is the synthetic fixture equivalent of the v0.12 reasoning session object.

It assembles demo case state without becoming a diagnosis object.

### 4.2 Required Schema

```yaml
demo_reasoning_session_object:
  demo_session_id: string
  demo_session_schema_version: demo_reasoning_session_snapshot_export_fixture_schema_v1
  linked_demo_case_id: string
  linked_demo_case_pack_id: string_or_null
  synthetic_only: true
  real_patient_data: false
  clinical_validation_use: false

  session_status:
    - demo_draft
    - demo_active
    - demo_snapshot_created
    - demo_export_attempted
    - demo_completed
    - demo_invalidated

  demo_intake_binding_fixtures: list[demo_intake_binding_fixture]
  demo_workspace_state_fixtures: list[demo_workspace_state_fixture]
  demo_structured_output_fixtures: list[demo_structured_output_fixture]
  demo_source_status_fixtures: list[demo_source_status_fixture_ref]
  demo_missing_evidence_fixtures: list[demo_missing_evidence_fixture_ref]
  demo_confidence_limiter_fixtures: list[demo_confidence_limiter_fixture_ref]
  demo_mimic_visibility_fixtures: list[demo_mimic_visibility_fixture_ref]
  demo_overlap_fixtures: list[demo_overlap_fixture_ref]
  demo_review_prompt_fixtures: list[demo_review_prompt_fixture_ref]

  demo_case_snapshot_fixtures: list[demo_case_snapshot_fixture]
  demo_revision_history_fixture: demo_revision_history_fixture
  demo_safe_export_fixtures: list[demo_safe_export_fixture]
  demo_unsafe_export_failure_fixtures: list[demo_unsafe_export_failure_fixture]
  demo_audit_event_fixtures: list[demo_audit_event_fixture]

  demo_authority_envelope_fixture: demo_authority_envelope_fixture
  demo_no_decision_object_fixture: demo_no_decision_object_fixture
  demo_safety_label: demo_safety_label

  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinical_validation_claim: false
```

### 4.3 Blocked Session Fixture Fields

Blocked:

- final_diagnosis,
- confirmed_diagnosis,
- clinical_impression,
- excluded_disease,
- excluded_mimic,
- treatment_plan,
- medication_recommendation,
- test_order,
- procedure_recommendation,
- follow_up_schedule,
- triage_decision,
- patient_facing_summary,
- public_ready_output,
- clinical_validation_status,
- MDD_consensus.

### 4.4 Demo Session Rule

> A demo reasoning session object assembles synthetic reasoning state, not clinical authority.

---

## 5. Demo Intake Binding Fixture

### 5.1 Purpose

The `demo_intake_binding_fixture` links synthetic demo case fields into the demo reasoning session.

### 5.2 Required Schema

```yaml
demo_intake_binding_fixture:
  fixture_id: string
  demo_session_id: string
  linked_demo_case_id: string
  linked_synthetic_field_id: string
  intake_domain:
    - demographics_context
    - imaging_context
    - temporal_context
    - exposure_history
    - CTD_SARD_context
    - microbiology_context
    - occupational_context
    - therapy_context
    - oncology_context
    - pathology_context
    - clinical_context

  field_state:
    - synthetic_provided
    - synthetic_not_provided
    - synthetic_source_limited
    - synthetic_conflicting
    - synthetic_incomplete

  value_source: synthetic_fixture
  inference_allowed: false
  inferred_fact_blocked: true
  expected_missing_evidence_visibility: true_or_not_relevant
  expected_downstream_bindings: list
  linked_audit_events: list

  authority_effect: none
  diagnosis_created: false
  exclusion_created: false
  treatment_created: false
  test_order_created: false
  procedure_decision_created: false
  follow_up_created: false
  triage_created: false
```

### 5.3 Blocked Intake Fixture Effects

Blocked:

- synthetic field becomes diagnosis,
- not-provided field becomes negative evidence,
- supplied context becomes disease confirmation,
- incomplete field becomes safety clearance,
- intake binding creates treatment/test/procedure/follow-up/triage.

### 5.4 Intake Fixture Rule

> Demo intake binding carries synthetic field state and provenance, not clinical truth.

---

## 6. Demo Workspace State Fixture

### 6.1 Purpose

The `demo_workspace_state_fixture` shows how synthetic state would appear in the clinician workspace.

It demonstrates visibility, not decision controls.

### 6.2 Required Schema

```yaml
demo_workspace_state_fixture:
  fixture_id: string
  demo_session_id: string
  linked_demo_case_id: string
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

  linked_intake_bindings: list
  linked_structured_output_fixtures: list
  linked_snapshot_fixtures: list
  linked_audit_events: list

  decision_control_created: false
  authority_effect: none
```

### 6.3 Blocked Workspace Fixture Components

Blocked:

- final diagnosis panel,
- treatment plan panel,
- order next test button,
- biopsy required banner,
- follow-up scheduler,
- triage disposition banner,
- patient-ready summary panel,
- public-ready toggle,
- clinically validated badge.

### 6.4 Workspace Fixture Rule

> Demo workspace fixtures show reasoning visibility, not clinical decision state.

---

## 7. Demo Structured Output Fixture

### 7.1 Purpose

The `demo_structured_output_fixture` represents synthetic structured reasoning output from v0.9 layers.

### 7.2 Required Schema

```yaml
demo_structured_output_fixture:
  fixture_id: string
  demo_session_id: string
  linked_demo_case_id: string
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

  safe_display_text: string
  linked_intake_bindings: list
  linked_source_status_fixtures: list
  linked_missing_evidence_fixtures: list
  linked_confidence_limiter_fixtures: list
  linked_mimic_visibility_fixtures: list
  linked_overlap_fixtures: list
  linked_review_prompt_fixtures: list
  linked_audit_events: list

  authority_effect: none
  diagnosis_created: false
  exclusion_created: false
  treatment_created: false
  test_order_created: false
  procedure_decision_created: false
  follow_up_created: false
  triage_created: false
```

### 7.3 Blocked Structured Output Fixture Layers

Blocked:

- final_diagnosis_layer,
- confirmed_diagnosis_layer,
- disease_exclusion_layer,
- mimic_exclusion_layer,
- treatment_plan_layer,
- test_order_layer,
- procedure_decision_layer,
- follow_up_layer,
- triage_layer,
- patient_advice_layer,
- clinical_validation_layer.

### 7.4 Structured Output Fixture Rule

> Demo structured output may display reasoning layers, not clinical decision layers.

---

## 8. Demo Case Snapshot Fixture

### 8.1 Purpose

The `demo_case_snapshot_fixture` freezes synthetic reasoning state.

It is not a final report.

### 8.2 Required Schema

```yaml
demo_case_snapshot_fixture:
  fixture_id: string
  snapshot_id: string
  demo_session_id: string
  linked_demo_case_id: string
  snapshot_schema_version: demo_reasoning_session_snapshot_export_fixture_schema_v1
  snapshot_index: integer
  snapshot_status:
    - demo_current
    - demo_historical
    - demo_superseded
    - demo_corrected
    - demo_invalidated

  created_reason:
    - demo_session_created
    - synthetic_intake_bound
    - missing_evidence_updated
    - source_status_updated
    - confidence_limiter_updated
    - mimic_visibility_updated
    - overlap_updated
    - review_prompt_updated
    - guardrail_triggered
    - unsafe_export_attempted
    - safe_export_created
    - demo_completed

  intake_binding_refs: list
  workspace_state_refs: list
  structured_output_refs: list
  source_status_refs: list
  missing_evidence_refs: list
  confidence_limiter_refs: list
  mimic_visibility_refs: list
  overlap_refs: list
  review_prompt_refs: list
  authority_envelope_ref: demo_authority_envelope_fixture_ref
  no_decision_object_ref: demo_no_decision_object_fixture_ref
  audit_event_refs: list

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
  clinical_validation_created: false
```

### 8.3 Blocked Snapshot Fixture Content

Blocked:

- final report,
- diagnostic impression,
- final diagnosis,
- excluded disease,
- excluded mimic,
- treatment plan,
- recommended tests,
- procedure recommendation,
- follow-up schedule,
- triage disposition,
- patient-facing summary,
- clinical validation.

### 8.4 Snapshot Fixture Rule

> Demo snapshot freezes synthetic reasoning state, not clinical truth.

---

## 9. Demo Revision History Fixture

### 9.1 Purpose

The `demo_revision_history_fixture` records synthetic state movement.

It does not validate correctness.

### 9.2 Required Schema

```yaml
demo_revision_history_fixture:
  fixture_id: string
  demo_session_id: string
  linked_demo_case_id: string
  revision_count: integer
  revisions: list[demo_revision_fixture]
  authority_effect: none
  clinical_validation_created: false
```

```yaml
demo_revision_fixture:
  revision_id: string
  demo_session_id: string
  revision_index: integer
  revision_type:
    - demo_session_created
    - synthetic_intake_added
    - synthetic_intake_updated
    - source_status_updated
    - missing_evidence_updated
    - confidence_limiter_updated
    - mimic_visibility_updated
    - overlap_updated
    - review_prompt_updated
    - workspace_state_refreshed
    - structured_output_refreshed
    - guardrail_triggered
    - unsafe_export_blocked
    - repair_required
    - safe_export_created
    - demo_completed

  previous_snapshot_id: string_or_null
  new_snapshot_id: string_or_null
  changed_fixture_refs: list
  audit_event_refs: list

  revision_is_clinical_validation: false
  revision_is_diagnostic_update: false
  revision_is_treatment_update: false
  authority_effect: none
```

### 9.3 Blocked Revision Fixture Interpretations

Blocked:

- diagnosis improved,
- diagnosis confirmed,
- disease excluded,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD completed,
- clinical validation achieved.

### 9.4 Revision Fixture Rule

> Demo revision history records synthetic state movement, not clinical correctness.

---

## 10. Demo Safe Export Fixture

### 10.1 Purpose

The `demo_safe_export_fixture` demonstrates governance-safe export behavior from v0.13.

It is not a diagnostic report.

### 10.2 Required Schema

```yaml
demo_safe_export_fixture:
  fixture_id: string
  export_id: string
  demo_session_id: string
  linked_demo_case_id: string
  linked_snapshot_id: string
  export_type:
    - demo_governance_safe_session_summary
    - demo_MDD_preparation_package
    - demo_case_snapshot_summary
    - demo_audit_reference_package

  export_status:
    - demo_draft
    - demo_governance_safe
    - demo_blocked
    - demo_superseded
    - demo_invalidated

  demo_safety_label: demo_safety_label
  non_authority_statement_present: true
  authority_envelope_present: true
  no_decision_statement_present: true
  blocked_output_notice_present: true

  source_status_preserved: true
  missing_evidence_preserved: true
  confidence_limiters_preserved: true
  mimic_visibility_preserved_where_relevant: true_or_not_relevant
  overlap_preserved_where_relevant: true_or_not_relevant
  review_prompts_preserved_where_relevant: true_or_not_relevant
  audit_references_present: true

  unsafe_heading_present: false
  unsafe_language_present: false
  unsafe_badge_present: false
  unsafe_table_column_present: false
  patient_facing_language_present: false
  public_ready_label_present: false
  clinical_validation_language_present: false

  export_authority_effect: none
  diagnosis_created: false
  exclusion_created: false
  treatment_created: false
  test_order_created: false
  procedure_decision_created: false
  follow_up_created: false
  triage_created: false
  patient_facing_created: false
  public_ready_created: false
  clinical_validation_created: false
```

### 10.3 Blocked Demo Export Content

Blocked:

- diagnostic report,
- impression,
- conclusion,
- final diagnosis,
- disease exclusion,
- treatment recommendation,
- test-order recommendation,
- procedure recommendation,
- follow-up recommendation,
- triage report,
- patient-facing summary,
- MDD consensus,
- clinical validation.

### 10.4 Demo Safe Export Rule

> Demo safe export may show safe export mechanics, not clinical reporting.

---

## 11. Demo MDD Preparation Package Fixture

### 11.1 Purpose

The `demo_MDD_preparation_package_fixture` demonstrates MDD preparation format without replacing MDD.

### 11.2 Required Schema

```yaml
demo_MDD_preparation_package_fixture:
  fixture_id: string
  package_id: string
  export_id: string
  demo_session_id: string
  linked_demo_case_id: string
  linked_snapshot_id: string
  intended_use: synthetic_clinician_review_and_MDD_preparation_demo_only

  package_sections:
    - export_header
    - non_authority_statement
    - authority_envelope
    - no_decision_statement
    - blocked_output_notice
    - snapshot_export_reference
    - case_context_summary
    - source_status_and_limitations
    - missing_evidence
    - confidence_limiters
    - high_risk_mimic_visibility_where_relevant
    - overlap_and_unresolved_boundaries_where_relevant
    - review_prompts_where_relevant
    - audit_references

  MDD_replacement: not_allowed
  platform_consensus_created: false
  final_diagnosis_created: false
  treatment_plan_created: false
  patient_facing_use: not_allowed
  public_ready: false
  clinical_validation_claim: false
  authority_effect: none
```

### 11.3 Blocked MDD Fixture Content

Blocked:

- MDD conclusion,
- consensus statement,
- final diagnosis,
- treatment plan,
- test order,
- procedure recommendation,
- follow-up interval,
- triage disposition,
- patient-facing advice.

### 11.4 MDD Fixture Rule

> Demo MDD preparation package organizes review inputs, not review outputs.

---

## 12. Demo Unsafe Export Failure Fixture

### 12.1 Purpose

The `demo_unsafe_export_failure_fixture` demonstrates fail-closed behavior when unsafe export conditions are attempted.

### 12.2 Required Schema

```yaml
demo_unsafe_export_failure_fixture:
  fixture_id: string
  failure_id: string
  demo_session_id: string
  linked_demo_case_id: string
  linked_snapshot_id: string_or_null
  unsafe_export_attempt_type:
    - unsafe_heading
    - unsafe_language
    - unsafe_badge
    - unsafe_table_column
    - missing_authority_envelope
    - missing_no_decision_statement
    - missing_blocked_output_notice
    - stale_binding
    - orphan_binding
    - source_limitation_loss
    - missing_evidence_loss
    - confidence_limiter_loss
    - mimic_visibility_loss
    - overlap_loss
    - review_prompt_loss
    - audit_reference_loss
    - patient_facing_language
    - public_ready_label
    - clinical_validation_language
    - MDD_consensus_claim

  unsafe_input_example: string
  unsafe_state_detected: true
  export_blocked: true
  failure_reason_visible: true
  repair_required: true
  revalidation_required: true
  audit_recorded: true
  authority_effect: none

  diagnosis_created: false
  exclusion_created: false
  treatment_created: false
  test_order_created: false
  procedure_decision_created: false
  follow_up_created: false
  triage_created: false
  patient_facing_created: false
  public_ready_created: false
  clinical_validation_created: false
```

### 12.3 Blocked Failure Fixture Meanings

Blocked:

- unsafe failure becomes clinical advice,
- unsafe failure becomes diagnosis,
- unsafe failure becomes treatment warning,
- unsafe failure becomes triage warning,
- unsafe failure becomes patient-facing warning.

### 12.4 Unsafe Export Failure Fixture Rule

> Demo unsafe export failure proves blocking, not clinical advice.

---

## 13. Demo Audit Event Fixture

### 13.1 Purpose

The `demo_audit_event_fixture` demonstrates traceability for synthetic scenario behavior.

It does not validate correctness.

### 13.2 Required Schema

```yaml
demo_audit_event_fixture:
  fixture_id: string
  audit_event_id: string
  demo_session_id: string
  linked_demo_case_id: string
  linked_snapshot_id: string_or_null
  linked_export_id: string_or_null
  event_type:
    - demo_case_created
    - demo_session_created
    - synthetic_intake_bound
    - workspace_state_bound
    - structured_output_bound
    - source_status_bound
    - missing_evidence_bound
    - confidence_limiter_bound
    - mimic_visibility_bound
    - overlap_bound
    - review_prompt_bound
    - authority_envelope_checked
    - no_decision_object_checked
    - snapshot_created
    - revision_recorded
    - safe_export_attempted
    - safe_export_created
    - unsafe_export_detected
    - unsafe_export_blocked
    - repair_required
    - revalidation_required
    - demo_completed

  event_summary: string
  linked_fixture_refs: list
  authority_effect: none
  diagnosis_created: false
  exclusion_created: false
  treatment_created: false
  test_order_created: false
  procedure_decision_created: false
  follow_up_created: false
  triage_created: false
  patient_facing_created: false
  public_ready_created: false
  clinical_validation_created: false
```

### 13.3 Blocked Audit Fixture Meanings

Blocked:

- audit validates diagnosis,
- audit proves correctness,
- audit authorizes treatment,
- audit orders test,
- audit recommends procedure,
- audit schedules follow-up,
- audit completes triage,
- audit completes MDD,
- audit creates product readiness.

### 13.4 Audit Fixture Rule

> Demo audit records synthetic traceability, not clinical correctness.

---

## 14. Demo Authority Envelope Fixture

### 14.1 Purpose

The `demo_authority_envelope_fixture` preserves non-authority across all demo artifacts.

### 14.2 Required Schema

```yaml
demo_authority_envelope_fixture:
  fixture_id: string
  demo_session_id: string
  linked_demo_case_id: string
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  product_ready: false
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
  mutable: false
  removable: false
  required_in_session: true
  required_in_snapshot: true
  required_in_export: true
```

### 14.3 Authority Envelope Fixture Rule

> Every demo artifact must preserve the authority envelope.

---

## 15. Demo No-Decision Object Fixture

### 15.1 Purpose

The `demo_no_decision_object_fixture` explicitly blocks decision objects in demo sessions.

### 15.2 Required Schema

```yaml
demo_no_decision_object_fixture:
  fixture_id: string
  demo_session_id: string
  linked_demo_case_id: string
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
  required_in_session: true
  required_in_snapshot: true
  required_in_export: true
```

### 15.3 No-Decision Fixture Rule

> Demo sessions must explicitly remember what they are not allowed to become.

---

## 16. Fixture Linkage Rules

Every demo fixture must be linked.

Required linkage:

| Fixture | Must Link To |
|---|---|
| demo_reasoning_session_object | synthetic_demo_case |
| demo_intake_binding_fixture | demo_session and synthetic field |
| demo_workspace_state_fixture | demo_session and relevant output/binding |
| demo_structured_output_fixture | demo_session and relevant source/missing/limiter/mimic/overlap/review fixture |
| demo_case_snapshot_fixture | demo_session, bindings, authority envelope, no-decision object, audit |
| demo_revision_history_fixture | demo_session and snapshots |
| demo_safe_export_fixture | demo_session and eligible snapshot |
| demo_MDD_preparation_package_fixture | safe export and eligible snapshot |
| demo_unsafe_export_failure_fixture | unsafe attempt and audit |
| demo_audit_event_fixture | event source fixture and session |
| demo_authority_envelope_fixture | session, snapshot, export |
| demo_no_decision_object_fixture | session, snapshot, export |

Blocked linkage failures:

- fixture exists without demo_session_id,
- fixture exists without linked_demo_case_id,
- snapshot lacks authority envelope,
- snapshot lacks no-decision object,
- export lacks snapshot reference,
- unsafe failure lacks audit event,
- workspace state visible without linked binding,
- output visible without source/missing/limiter linkage where relevant.

Linkage rule:

> Demo fixtures must remain graph-connected and audit-linked.

---

## 17. Fixture Consistency Checks

Every demo session fixture must pass consistency checks.

Required checks:

```yaml
fixture_consistency_checks:
  synthetic_status_consistent: true
  real_patient_data_absent: true
  linked_demo_case_present: true
  demo_session_present: true
  intake_bindings_traceable: true
  workspace_state_traceable: true
  structured_output_traceable: true
  source_status_preserved: true
  missing_evidence_preserved_where_relevant: true
  confidence_limiters_preserved_where_relevant: true
  mimic_visibility_preserved_where_relevant: true
  overlap_preserved_where_relevant: true
  review_prompts_preserved_where_relevant: true
  authority_envelope_present: true
  no_decision_object_present: true
  snapshots_non_final: true
  revision_history_non_validating: true
  exports_non_diagnostic: true
  unsafe_export_fail_closed_where_relevant: true
  audit_traceability_present: true
  patient_facing_blocked: true
  public_ready_blocked: true
  clinical_validation_blocked: true
```

Blocked consistency outcomes:

- diagnosis field appears,
- exclusion field appears,
- treatment field appears,
- test order appears,
- procedure recommendation appears,
- follow-up schedule appears,
- triage decision appears,
- patient-facing output appears,
- public-ready output appears,
- clinical validation claim appears,
- real patient data appears.

Consistency rule:

> Demo consistency proves fixture integrity, not medical correctness.

---

## 18. Demo Fixture Acceptance Tests

### TEST_001 — Synthetic Demo Session Creation

Input:

```yaml
synthetic_demo_case:
  synthetic_only: true
  real_patient_data: false
```

Expected:

- demo_reasoning_session_object created,
- authority envelope present,
- no-decision object present,
- audit recorded,
- no diagnosis created.

---

### TEST_002 — Missing Exposure Preserved

Input:

```yaml
not_provided_field_fixture:
  field_domain: exposure_history
  field_state: not_provided
```

Expected:

- missing evidence visible,
- HP-related mimic/overlap remains review-visible where relevant,
- missing-as-exclusion blocked,
- no disease excluded.

---

### TEST_003 — Prior CT Unavailable

Input:

```yaml
prior_ct_available: false
```

Expected:

- temporal limiter active,
- no stability claim,
- no progression diagnosis,
- no follow-up schedule.

---

### TEST_004 — Unsafe Export Heading

Input:

```yaml
unsafe_input_example: "Impression"
```

Expected:

- unsafe state detected,
- export blocked,
- repair required,
- audit recorded,
- authority effect none.

---

### TEST_005 — Demo Safe Export

Input:

```yaml
demo_safe_export_fixture:
  authority_envelope_present: true
  no_decision_statement_present: true
  blocked_output_notice_present: true
```

Expected:

- governance-safe demo export fixture,
- source/missing/limiter/mimic/overlap/review preserved where relevant,
- no diagnostic report created.

---

## 19. Red-Team Fixture Scenarios

The following failures must be blocked.

| Scenario | Required Block |
|---|---|
| Demo session contains final diagnosis | diagnosis field blocked |
| Demo snapshot says final report | snapshot-as-report blocked |
| Demo revision says clinically validated | revision-as-validation blocked |
| Demo export says clinical impression | report-like export blocked |
| Demo export says HP ruled out | missing-as-exclusion blocked |
| Demo table contains probability | limiter-to-probability blocked |
| Demo mimic is marked confirmed | mimic diagnosis blocked |
| Demo overlap selects winner | forced closure blocked |
| Demo review prompt recommends biopsy | procedure recommendation blocked |
| Demo MDD package says consensus achieved | MDD replacement blocked |
| Demo audit says correctness proven | audit-to-validation blocked |
| Demo file uses patient_summary name | patient-facing implication blocked |
| Demo fixture includes real patient report | real patient data blocked |
| Demo result reports sensitivity/specificity | clinical metric blocked |
| Demo artifact marked public-ready | deployment claim blocked |

---

## 20. v0.14.2 Acceptance Criteria

v0.14.2 is accepted only if:

- demo reasoning session object fixture is defined,
- demo intake binding fixture is defined,
- demo workspace state fixture is defined,
- demo structured output fixture is defined,
- demo case snapshot fixture is defined,
- demo revision history fixture is defined,
- demo safe export fixture is defined,
- demo MDD preparation package fixture is defined,
- demo unsafe export failure fixture is defined,
- demo audit event fixture is defined,
- demo authority envelope fixture is defined,
- demo no-decision object fixture is defined,
- fixture linkage rules are defined,
- fixture consistency checks are defined,
- fixture acceptance tests are defined,
- red-team fixture scenarios are blocked,
- synthetic status remains true,
- real patient data remains false,
- snapshots remain non-final,
- revision history remains non-validating,
- safe export remains non-diagnostic,
- unsafe export fails closed,
- audit remains traceability only,
- no diagnosis is created,
- no exclusion is created,
- no treatment is created,
- no test order is created,
- no procedure decision is created,
- no follow-up schedule is created,
- no triage is created,
- no patient-facing use is created,
- no public readiness is created,
- no clinical validation is created.

---

## 21. Next Step

The next recommended step is:

- v0.14.3 — Demo Scenario Set: Missing Evidence / Mimic / Overlap / Source Status

v0.14.3 should define the first governed synthetic scenario set:

- UIP-like fibrotic pattern with exposure history missing,
- fibrotic ILD with CTD/SARD context missing,
- sarcoid-like nodal/perilymphatic pattern with beryllium history missing,
- OP-like consolidation with microbiology missing,
- oncology context with septal/peribronchovascular pattern,
- ICI exposure with new inflammatory findings,
- prior CT unavailable,
- source-status limitation demonstration.

v0.14.3 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, real patient data, clinical validation, or platform-wide clinical review.

---

## 22. Governance Statement

This schema defines demo reasoning session, snapshot, export, failure, and audit fixtures.

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

Demo fixtures remain synthetic governance demonstrations only.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.2:

> “A demo session fixture is valid only if synthetic case state can travel through intake, workspace, structured output, snapshot, revision, export, failure, and audit fixtures without becoming clinical authority.”