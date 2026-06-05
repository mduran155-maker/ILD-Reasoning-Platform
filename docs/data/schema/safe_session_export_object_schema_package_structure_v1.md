# ILD Reasoning Platform — Safe Session Export Object Schema / Package Structure v1

Version: v0.13.1  
Status: safe_session_export_object_schema_package_structure  
Scope: Detailed schema for governance-safe session export and MDD preparation package structure  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the detailed object schema and package structure for v0.13 — Safe Session Export / MDD Preparation Package Contract.

It follows:

- `docs/navigation/safe_session_export_mdd_preparation_entry_gate_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_12.md`
- `docs/navigation/case_assembly_reasoning_session_structural_seal_v1.md`
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

Its purpose is to define how a governed reasoning session object may be exported as a safe, non-authoritative package for clinician review and MDD preparation.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.13 rule remains:

> “A safe session export may prepare discussion, but it must not become diagnosis, treatment, order, procedure decision, follow-up schedule, triage report, patient-facing output, public-ready output, or clinical validation.”

For v0.13.1:

> “A safe export object is valid only if every section preserves source status, missing evidence, confidence limiters, mimic visibility, overlap, review prompts, audit references, authority envelope, and no-decision constraints.”

---

## 2. Global Export Object Contract

Every export object and export section must preserve:

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

No export object, package section, exported note, appendix, table, heading, badge, or audit reference may override the authority envelope.

---

## 3. Root Safe Session Export Object

### 3.1 Purpose

The `safe_session_export` is the root export object.

It packages selected governed session state for clinician review and MDD preparation.

It is not a clinical report.

### 3.2 Required Schema

```yaml
safe_session_export:
  export_id: string
  export_schema_version: safe_session_export_object_schema_package_structure_v1
  export_type:
    - governance_safe_session_summary
    - MDD_preparation_package
    - case_snapshot_summary
    - audit_reference_package
  export_status:
    - draft
    - governance_safe
    - superseded
    - invalidated
  session_id: string
  snapshot_id: string
  snapshot_eligibility_status: eligible | ineligible | blocked
  created_at: implementation_defined
  created_by: clinician | system | unknown
  source_session_schema_version: string
  source_snapshot_schema_version: string

  export_header: export_header
  non_authority_statement: non_authority_statement
  snapshot_export_reference: snapshot_export_reference
  case_context_export_section: case_context_export_section
  temporal_context_export_section: temporal_context_export_section
  source_status_export_section: source_status_export_section
  missing_evidence_export_section: missing_evidence_export_section
  confidence_limiter_export_section: confidence_limiter_export_section
  mimic_visibility_export_section: mimic_visibility_export_section
  overlap_export_section: overlap_export_section
  review_prompt_export_section: review_prompt_export_section
  audit_reference_export_section: audit_reference_export_section
  authority_envelope_export_section: authority_envelope_export_section
  no_decision_statement_export_section: no_decision_statement_export_section
  blocked_output_notice: blocked_output_notice

  optional_appendices:
    clinician_note_export_section: optional
    local_workflow_note_export_section: optional
    source_reference_appendix: optional
    audit_reference_appendix: optional

  export_authority_effect: none
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

### 3.3 Blocked Root Export Fields

The root export object must not contain:

```yaml
blocked_root_export_fields:
  final_diagnosis: blocked
  confirmed_diagnosis: blocked
  clinical_impression: blocked
  excluded_disease: blocked
  excluded_mimic: blocked
  treatment_plan: blocked
  medication_recommendation: blocked
  test_order: blocked
  procedure_recommendation: blocked
  follow_up_schedule: blocked
  triage_decision: blocked
  patient_facing_summary: blocked
  public_ready_output: blocked
  clinical_validation_status: blocked
  platform_MDD_consensus: blocked
```

### 3.4 Root Export Rule

> The safe session export packages governed reasoning state; it does not package clinical authority.

---

## 4. MDD Preparation Package Object

### 4.1 Purpose

The `MDD_preparation_package` is a governed export format that prepares a case for multidisciplinary discussion.

It organizes what should be reviewed.

It does not replace the review.

### 4.2 Required Schema

```yaml
MDD_preparation_package:
  package_id: string
  export_id: string
  session_id: string
  snapshot_id: string
  package_status: draft | governance_safe | superseded | invalidated
  intended_use: clinician_review_and_MDD_preparation_only
  patient_facing_use: not_allowed
  public_ready: false

  package_sections:
    - export_header
    - non_authority_statement
    - case_context_export_section
    - temporal_context_export_section
    - source_status_export_section
    - missing_evidence_export_section
    - confidence_limiter_export_section
    - mimic_visibility_export_section
    - overlap_export_section
    - review_prompt_export_section
    - audit_reference_export_section
    - authority_envelope_export_section
    - no_decision_statement_export_section
    - blocked_output_notice

  MDD_replacement: not_allowed
  platform_consensus_created: false
  final_diagnosis_created: false
  treatment_plan_created: false
  authority_effect: none
```

### 4.3 Blocked MDD Package Fields

Blocked:

- MDD conclusion,
- platform consensus,
- final diagnosis,
- disease exclusion,
- treatment plan,
- test order,
- procedure recommendation,
- follow-up interval,
- triage disposition,
- patient-facing advice.

### 4.4 MDD Package Rule

> An MDD preparation package organizes review inputs; it does not create review outputs.

---

## 5. Export Header Schema

### 5.1 Purpose

The export header identifies the package and declares non-authority before any clinical reasoning content is shown.

### 5.2 Required Schema

```yaml
export_header:
  export_id: string
  export_type:
    - governance_safe_session_summary
    - MDD_preparation_package
    - case_snapshot_summary
    - audit_reference_package
  session_id: string
  snapshot_id: string
  snapshot_index: integer
  created_at: implementation_defined
  created_by: clinician | system | unknown
  export_status: draft | governance_safe | superseded | invalidated
  intended_use: clinician_review_and_MDD_preparation_only
  patient_facing_use: not_allowed
  public_ready: false
  diagnostic_authority: none
  treatment_authority: none
  clinically_reviewed_platform_wide: false
```

### 5.3 Blocked Header Labels

Blocked:

- final diagnostic report,
- clinical impression,
- diagnosis report,
- treatment plan,
- test order package,
- procedure plan,
- follow-up plan,
- triage report,
- patient report,
- public-ready report,
- clinically validated report,
- MDD consensus.

### 5.4 Header Rule

> Export header must declare non-authority before any reasoning content appears.

---

## 6. Non-Authority Statement Schema

### 6.1 Purpose

The non-authority statement prevents the export from being mistaken for a diagnostic report or clinical action document.

### 6.2 Required Schema

```yaml
non_authority_statement:
  statement_id: string
  required: true
  position: before_reasoning_content
  text: >
    This package summarizes governed reasoning state for clinician review
    and MDD preparation. It does not diagnose, exclude disease, recommend
    treatment, order tests, recommend procedures, schedule follow-up, triage,
    replace MDD, validate clinical correctness, create patient-facing advice,
    or create public readiness.
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
```

### 6.3 Required Covered Blocks

The statement must explicitly block:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment recommendation,
- test ordering,
- procedure recommendation,
- follow-up scheduling,
- triage,
- MDD replacement,
- specialist replacement,
- clinical validation,
- patient-facing advice,
- public readiness.

### 6.4 Non-Authority Statement Rule

> A safe export must state what it is not before presenting what it contains.

---

## 7. Snapshot Export Reference Schema

### 7.1 Purpose

The snapshot export reference proves that the export comes from an eligible v0.12 snapshot.

### 7.2 Required Schema

```yaml
snapshot_export_reference:
  reference_id: string
  session_id: string
  snapshot_id: string
  snapshot_index: integer
  snapshot_status: current | historical | superseded | corrected | archived
  snapshot_export_eligibility: eligible | ineligible | blocked
  snapshot_is_final_report: false
  snapshot_is_patient_facing: false
  snapshot_is_public_ready: false
  snapshot_is_clinically_validated: false
  authority_envelope_ref_present: true
  no_decision_object_ref_present: true
  stale_bindings_present_as_current: false
  orphan_bindings_present: false
  audit_event_refs_present: true
  export_authority_effect: none
```

### 7.3 Blocked Snapshot Reference States

Blocked:

- snapshot marked final report,
- snapshot marked patient-facing,
- snapshot marked public-ready,
- snapshot marked clinically validated,
- missing authority envelope,
- missing no-decision object,
- stale current bindings,
- orphan bindings,
- missing audit references.

### 7.4 Snapshot Reference Rule

> Only a governance-valid snapshot may be referenced by a safe export.

---

## 8. Case Context Export Section Schema

### 8.1 Purpose

The case context section summarizes supplied case context without generating a clinical conclusion.

### 8.2 Required Schema

```yaml
case_context_export_section:
  section_id: string
  section_title: Case Context Summary
  section_required: true
  section_state: visible
  case_id: string
  deidentification_status: deidentified | local_only | not_provided
  provided_demographics:
    age: supplied_value_or_not_provided
    sex: supplied_value_or_not_provided
  provided_imaging_context: list
  clinician_supplied_evidence_items: list
  report_supplied_facts: list
  uploaded_record_supplied_facts: list
  not_provided_fields: list
  provenance_notes: list
  linked_intake_field_bindings: list
  linked_audit_events: list
  authority_effect: none
```

### 8.3 Allowed Content

Allowed:

- provided facts,
- not-provided fields,
- clinician-supplied labels,
- report-supplied labels,
- uploaded-record labels,
- imaging context as provided,
- provenance notes,
- deidentification state.

### 8.4 Blocked Content

Blocked:

- diagnostic label,
- clinical impression,
- disease conclusion,
- treatment recommendation,
- test recommendation,
- patient-facing explanation.

### 8.5 Case Context Rule

> Case context export summarizes supplied state; it does not conclude disease.

---

## 9. Temporal Context Export Section Schema

### 9.1 Purpose

The temporal context section summarizes comparison availability and change state without diagnosing progression.

### 9.2 Required Schema

```yaml
temporal_context_export_section:
  section_id: string
  section_title: Temporal Context
  section_required: optional_but_recommended
  prior_imaging_available: true | false | unclear | not_provided
  comparison_interval: supplied_value_or_not_provided
  same_protocol_available: true | false | unclear | not_provided
  change_direction: new | increased | decreased | stable | mixed | unclear | not_assessable | not_provided
  temporal_limiters: list
  linked_confidence_limiters: list
  linked_missing_evidence: list
  linked_audit_events: list
  authority_effect: none
```

### 9.3 Blocked Content

Blocked:

- PPF diagnosis,
- acute exacerbation diagnosis,
- progression diagnosis,
- stability as benignity,
- follow-up interval.

### 9.4 Temporal Export Rule

> Temporal export shows change and limitation, not progression diagnosis.

---

## 10. Source Status Export Section Schema

### 10.1 Purpose

The source status section preserves source role, claim mapping status, and limitations.

### 10.2 Required Schema

```yaml
source_status_export_section:
  section_id: string
  section_title: Source Status and Limitations
  section_required: true
  source_status_items: list[source_status_export_item]
  source_limitations_preserved: true
  platform_wide_review_false: true
  authority_effect: none
```

```yaml
source_status_export_item:
  source_status_item_id: string
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
  linked_claims_or_sections: list
  authority_effect: none
```

### 10.3 Blocked Source Export Meanings

Blocked:

- clinically validated,
- diagnosis confirmed,
- treatment supported,
- test order supported,
- procedure supported,
- patient ready,
- public ready.

### 10.4 Source Status Rule

> Source status export preserves source limitations; it does not create clinical authority.

---

## 11. Missing Evidence Export Section Schema

### 11.1 Purpose

The missing evidence section preserves evidence gaps and prevents missing data from becoming exclusion.

### 11.2 Required Schema

```yaml
missing_evidence_export_section:
  section_id: string
  section_title: Missing Evidence
  section_required: true
  missing_evidence_items: list[missing_evidence_export_item]
  missing_evidence_preserved: true
  missing_as_exclusion_blocked: true
  authority_effect: none
```

```yaml
missing_evidence_export_item:
  missing_item_id: string
  missing_item_label: string
  missing_state:
    - missing
    - partially_supplied
    - supplied_by_clinician
    - source_limited
    - conflicting
    - no_longer_missing_but_still_limited
  affected_prompts: list
  linked_confidence_limiters: list
  linked_mimics: list
  linked_overlap: list
  linked_review_prompts: list
  linked_audit_events: list
  exclusion_effect: none
  authority_effect: none
```

### 11.3 Blocked Missing Evidence Meanings

Blocked:

- disease excluded,
- mimic excluded,
- benign,
- safe,
- no review needed,
- no urgent review needed.

### 11.4 Missing Evidence Export Rule

> Missing evidence export must keep absence of data from becoming absence of disease.

---

## 12. Confidence Limiter Export Section Schema

### 12.1 Purpose

The confidence limiter section preserves interpretation limits without creating probability or diagnostic confidence.

### 12.2 Required Schema

```yaml
confidence_limiter_export_section:
  section_id: string
  section_title: Confidence Limiters
  section_required: true
  confidence_limiter_items: list[confidence_limiter_export_item]
  diagnostic_confidence_created: false
  probability_created: false
  authority_effect: none
```

```yaml
confidence_limiter_export_item:
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
  linked_cause: string
  affected_prompts: list
  linked_missing_evidence: list
  linked_source_status: list
  linked_audit_events: list
  diagnostic_confidence_score: blocked
  disease_probability: blocked
  authority_effect: none
```

### 12.3 Blocked Limiter Meanings

Blocked:

- diagnostic confidence score,
- disease probability,
- final diagnostic rank,
- exclusion score,
- safety clearance,
- treatment threshold.

### 12.4 Confidence Limiter Export Rule

> Confidence limiter export explains interpretation limits, not diagnosis probability.

---

## 13. Mimic Visibility Export Section Schema

### 13.1 Purpose

The mimic visibility section preserves high-risk mimic visibility without diagnosing or excluding mimics.

### 13.2 Required Schema

```yaml
mimic_visibility_export_section:
  section_id: string
  section_title: High-Risk Mimic Visibility
  section_required: yes_where_relevant
  mimic_visibility_items: list[mimic_visibility_export_item]
  mimic_diagnosis_created: false
  mimic_exclusion_created: false
  authority_effect: none
```

```yaml
mimic_visibility_export_item:
  mimic_prompt_id: string
  mimic_family:
    - infection
    - TB
    - NTM
    - fungal_disease
    - aspiration
    - occupational_ILD
    - beryllium_sarcoid_mimic
    - drug_induced_or_therapy_related_ILD
    - radiation_pneumonitis_or_RILI
    - checkpoint_inhibitor_pneumonitis
    - ICI_sarcoid_like_reaction
    - pulmonary_lymphangitic_carcinomatosis
    - malignancy_or_lymphoma_or_recurrence
    - sarcoid_like_reaction
    - acute_dangerous_overlay
  mimic_state:
    - mimic_prompt_visible
    - mimic_prompt_not_triggered
    - mimic_source_limited
    - mimic_missing_evidence_limited
    - mimic_overlap_visible
    - mimic_review_visible
  linked_missing_evidence: list
  linked_confidence_limiters: list
  linked_overlap: list
  linked_source_status: list
  linked_audit_events: list
  diagnosis_status: not_diagnosed
  exclusion_status: not_excluded
  treatment_status: not_recommended
  authority_effect: none
```

### 13.3 Blocked Mimic Export Meanings

Blocked:

- mimic confirmed,
- mimic excluded,
- mimic treatment needed,
- mimic test needed,
- mimic procedure needed.

### 13.4 Mimic Export Rule

> Mimic visibility export preserves review visibility without diagnosing or excluding mimics.

---

## 14. Overlap Export Section Schema

### 14.1 Purpose

The overlap section preserves unresolved coexistence and boundary states.

### 14.2 Required Schema

```yaml
overlap_export_section:
  section_id: string
  section_title: Overlap and Unresolved Boundaries
  section_required: yes_where_relevant
  overlap_items: list[overlap_export_item]
  winner_selected: false
  final_label_selected: false
  authority_effect: none
```

```yaml
overlap_export_item:
  overlap_id: string
  overlap_family:
    - UIP_vs_HP
    - UIP_vs_CTD_ILD
    - HP_vs_CTD_ILD
    - CTD_ILD_vs_NSIP
    - NSIP_vs_OP
    - OP_vs_infection
    - OP_vs_aspiration
    - sarcoidosis_vs_infection
    - sarcoidosis_vs_beryllium
    - sarcoidosis_vs_malignancy
    - drug_induced_ILD_vs_NSIP_OP
    - radiation_pneumonitis_vs_infection_recurrence
    - CIP_vs_infection_progression
    - PLC_vs_ILD_infection_edema
    - acute_overlay_vs_chronic_fibrosis
  overlap_state:
    - overlap_visible
    - overlap_unresolved
    - overlap_source_limited
    - overlap_missing_evidence_limited
    - overlap_conflict_visible
    - overlap_deferred_to_review
  involved_prompts: list
  linked_mimics: list
  linked_missing_evidence: list
  linked_confidence_limiters: list
  linked_review_prompts: list
  linked_audit_events: list
  closure_status: not_established
  authority_effect: none
```

### 14.3 Blocked Overlap Export Meanings

Blocked:

- winner selected,
- secondary process excluded,
- mimic suppressed,
- final label selected.

### 14.4 Overlap Export Rule

> Overlap export preserves unresolved coexistence, not forced closure.

---

## 15. Review Prompt Export Section Schema

### 15.1 Purpose

The review prompt section preserves urgent, MDD, and specialist review visibility without replacing review.

### 15.2 Required Schema

```yaml
review_prompt_export_section:
  section_id: string
  section_title: Review Prompts
  section_required: yes_where_relevant
  review_prompt_items: list[review_prompt_export_item]
  review_replacement_created: false
  triage_created: false
  authority_effect: none
```

```yaml
review_prompt_export_item:
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
  linked_missing_evidence: list
  linked_confidence_limiters: list
  linked_source_status: list
  linked_audit_events: list
  authority_effect: none
```

### 15.3 Blocked Review Export Meanings

Blocked:

- triage decision made,
- emergency disposition selected,
- outpatient safe declared,
- MDD replaced,
- MDD unnecessary,
- specialist review replaced,
- consensus created by platform.

### 15.4 Review Prompt Export Rule

> Review prompt export prepares discussion, not decision replacement.

---

## 16. Audit Reference Export Section Schema

### 16.1 Purpose

The audit reference section preserves traceability without validating clinical correctness.

### 16.2 Required Schema

```yaml
audit_reference_export_section:
  section_id: string
  section_title: Audit References
  section_required: true
  audit_reference_items: list[audit_reference_export_item]
  audit_clinical_validation: false
  authority_effect: none
```

```yaml
audit_reference_export_item:
  audit_event_id: string
  event_type:
    - session_created
    - case_snapshot_created
    - intake_field_bound
    - evidence_update_recorded
    - workspace_refresh_recorded
    - source_status_bound
    - missing_evidence_bound
    - confidence_limiter_bound
    - mimic_visibility_bound
    - overlap_bound
    - review_prompt_bound
    - guardrail_triggered
    - correction_recorded
    - supersession_recorded
    - safe_export_created
  event_summary: string
  linked_export_sections: list
  linked_snapshot_id: string
  authority_effect: none
  diagnosis_validated: false
  treatment_authorized: false
  test_ordered: false
  procedure_recommended: false
  follow_up_scheduled: false
  triage_completed: false
  MDD_completed_by_platform: false
  public_ready_enabled: false
```

### 16.3 Blocked Audit Export Meanings

Blocked:

- diagnosis validated,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD completed by platform,
- clinical validation confirmed,
- public readiness enabled.

### 16.4 Audit Export Rule

> Audit references show traceability, not correctness.

---

## 17. Authority Envelope Export Section Schema

### 17.1 Purpose

The authority envelope section preserves the platform’s non-authority boundary inside every export.

### 17.2 Required Schema

```yaml
authority_envelope_export_section:
  section_id: string
  section_title: Authority Envelope
  section_required: true
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

### 17.3 Blocked Authority Export States

Blocked:

- authority envelope omitted,
- authority envelope hidden,
- authority envelope editable,
- diagnostic authority enabled,
- treatment authority enabled,
- public ready true,
- patient-facing enabled,
- clinically reviewed platform wide true.

### 17.4 Authority Export Rule

> Export without authority envelope is invalid.

---

## 18. No-Decision Statement Export Section Schema

### 18.1 Purpose

The no-decision statement section explicitly prevents the export from hiding decision outputs.

### 18.2 Required Schema

```yaml
no_decision_statement_export_section:
  section_id: string
  section_title: No-Decision Statement
  section_required: true
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

### 18.3 Required Assertion

```yaml
no_decision_export_assertion:
  export_contains_decision_object: false
  export_contains_authority_override: false
  export_contains_patient_facing_output: false
  export_contains_public_ready_output: false
```

### 18.4 No-Decision Export Rule

> Export must explicitly remember what it is not allowed to become.

---

## 19. Blocked Output Notice Schema

### 19.1 Purpose

The blocked output notice makes unsafe output categories visible inside the export.

### 19.2 Required Schema

```yaml
blocked_output_notice:
  section_id: string
  section_title: Blocked Outputs
  section_required: true
  blocked_categories:
    diagnosis: blocked
    disease_exclusion: blocked
    mimic_exclusion: blocked
    treatment_recommendation: blocked
    test_ordering: blocked
    procedure_decision: blocked
    follow_up_scheduling: blocked
    triage_or_disposition: blocked
    public_readiness: blocked
    clinical_validation: blocked
    patient_facing_report: blocked
    MDD_replacement: blocked
    urgent_review_replacement: blocked
  bypass_allowed: false
  authority_effect: none
```

### 19.3 Blocked Output Notice Rule

> A safe export must make blocked categories visible, not hidden.

---

## 20. Clinician Note Export Section

### 20.1 Purpose

Clinician notes may be exported only if clearly labeled as clinician-authored content.

This section is optional.

### 20.2 Required Schema

```yaml
clinician_note_export_section:
  section_id: string
  section_title: Clinician Notes
  section_required: false
  notes: list[clinician_note_export_item]
  platform_conclusion_created: false
  authority_effect: none
```

```yaml
clinician_note_export_item:
  note_id: string
  note_type:
    - clinician_authored_note
    - clinician_supplied_evidence_note
    - MDD_preparation_note
    - local_workflow_note
  authored_by: clinician | unknown
  note_text: string
  linked_session_id: string
  linked_snapshot_id: string
  linked_audit_events: list
  platform_authored: false
  platform_conclusion_created: false
  authority_effect: none
```

### 20.3 Blocked Clinician Note Interpretations

Blocked:

- clinician note becomes platform diagnosis,
- clinician note becomes platform treatment,
- clinician note becomes source-reviewed claim,
- clinician note becomes clinical validation,
- clinician note becomes patient-facing advice.

### 20.4 Clinician Note Export Rule

> Clinician notes may be included as human-authored notes, not platform conclusions.

---

## 21. Source Reference Appendix Schema

### 21.1 Purpose

A source reference appendix may list source references used for source-status visibility.

This section is optional.

### 21.2 Required Schema

```yaml
source_reference_appendix:
  appendix_id: string
  appendix_title: Source References
  appendix_required: false
  source_refs: list[source_reference_item]
  source_limitations_preserved: true
  authority_effect: none
```

```yaml
source_reference_item:
  source_id: string
  source_title_or_label: string
  source_role_class: string
  source_status_ref_id: string
  linked_export_sections: list
  source_limitations: list
  clinical_validation_created: false
  authority_effect: none
```

### 21.3 Blocked Appendix Meanings

Blocked:

- source list means guideline completeness,
- source list means clinical validation,
- source list means diagnosis supported,
- source list means treatment supported,
- source list means public readiness.

### 21.4 Source Appendix Rule

> Source references support transparency, not clinical authority.

---

## 22. Audit Reference Appendix Schema

### 22.1 Purpose

An audit reference appendix may list audit events in greater detail.

This section is optional.

### 22.2 Required Schema

```yaml
audit_reference_appendix:
  appendix_id: string
  appendix_title: Audit Reference Detail
  appendix_required: false
  audit_refs: list[audit_reference_export_item]
  audit_clinical_validation: false
  authority_effect: none
```

### 22.3 Blocked Appendix Meanings

Blocked:

- audit list means correctness,
- audit list means diagnosis validated,
- audit list means treatment authorized,
- audit list means MDD completed,
- audit list means public readiness.

### 22.4 Audit Appendix Rule

> Audit references support traceability, not correctness.

---

## 23. Package Ordering Rules

### 23.1 Required Section Order

A safe export should order sections as follows:

1. export header,
2. non-authority statement,
3. snapshot export reference,
4. authority envelope,
5. no-decision statement,
6. blocked output notice,
7. case context summary,
8. temporal context where relevant,
9. source status,
10. missing evidence,
11. confidence limiters,
12. high-risk mimics,
13. overlap and unresolved boundaries,
14. review prompts,
15. audit references,
16. optional clinician notes,
17. optional source appendix,
18. optional audit appendix.

### 23.2 Required Early Safety Placement

The following must appear before reasoning content:

- non-authority statement,
- authority envelope,
- no-decision statement,
- blocked output notice.

### 23.3 Blocked Ordering

Blocked:

- diagnosis-like summary before non-authority statement,
- reasoning content before authority envelope,
- export appendix hiding source limitations,
- no-decision statement only at the end,
- blocked output notice omitted or hidden.

### 23.4 Package Ordering Rule

> Safety and authority boundaries must appear before reasoning content.

---

## 24. Export State Lifecycle

### 24.1 Allowed Export States

Allowed export states:

- draft,
- governance_safe,
- superseded,
- invalidated.

### 24.2 Required State Behavior

```yaml
export_lifecycle:
  draft:
    may_be_edited: true
    may_be_shared: false
    must_preserve_authority: true

  governance_safe:
    may_be_shared_for_clinician_review: true
    patient_facing_use: not_allowed
    public_ready: false

  superseded:
    current_use: blocked
    retained_for_audit: true

  invalidated:
    current_use: blocked
    export_blocked: true
    repair_or_regeneration_required: true
```

### 24.3 Blocked Export States

Blocked:

- final,
- signed,
- clinically_validated,
- patient_ready,
- public_ready,
- treatment_ready,
- order_ready,
- triage_ready.

### 24.4 Export Lifecycle Rule

> Export status may govern package usability, but it must not imply clinical approval.

---

## 25. Export Validation Object

### 25.1 Purpose

Every export must include or reference a validation object confirming export safety.

### 25.2 Required Schema

```yaml
safe_export_validation_object:
  validation_id: string
  export_id: string
  session_id: string
  snapshot_id: string
  snapshot_eligible: true
  authority_envelope_present: true
  no_decision_statement_present: true
  blocked_output_notice_present: true
  non_authority_statement_present: true
  source_limitations_preserved: true
  missing_evidence_preserved: true
  confidence_limiters_preserved: true
  mimic_visibility_preserved_where_relevant: true
  overlap_preserved_where_relevant: true
  review_prompts_preserved_where_relevant: true
  audit_references_preserved: true
  stale_bindings_blocked: true
  orphan_bindings_blocked: true
  decision_fields_absent: true
  patient_facing_format_blocked: true
  public_ready_label_blocked: true
  clinical_validation_language_blocked: true
  export_valid: true_or_false
  authority_effect: none
```

### 25.3 Validation Rule

> Export validation confirms governance safety, not clinical correctness.

---

## 26. Unsafe Export Failure Object

### 26.1 Purpose

Unsafe export attempts must fail closed.

### 26.2 Required Schema

```yaml
unsafe_export_failure:
  failure_id: string
  export_id: string
  session_id: string
  snapshot_id: string
  failure_reason:
    - missing_authority_envelope
    - missing_no_decision_statement
    - missing_blocked_output_notice
    - stale_binding_present
    - orphan_binding_present
    - decision_field_detected
    - source_limitation_lost
    - missing_evidence_lost
    - confidence_limiter_lost
    - mimic_visibility_lost
    - overlap_lost
    - audit_reference_missing
    - patient_facing_language_detected
    - public_ready_label_detected
    - clinical_validation_language_detected
  export_allowed: false
  repair_required: true
  audit_event_required: true
  authority_effect: none
```

### 26.3 Blocked Failure Handling

Blocked:

- export anyway,
- warning-only bypass,
- clinician override to public-ready,
- hiding failure reason,
- converting failure to clinical validation.

### 26.4 Unsafe Export Rule

> Unsafe export attempts must fail closed and require traceable repair.

---

## 27. Export Red-Team Schema

### 27.1 Purpose

The export schema must explicitly block red-team export failures.

### 27.2 Red-Team Cases

| Red-Team Scenario | Required Block |
|---|---|
| Export title says final diagnostic report | final report conversion blocked |
| Export includes final diagnosis field | diagnosis field blocked |
| Export includes clinical impression | clinical impression blocked |
| Export says HP ruled out due to missing exposure | missing-as-exclusion blocked |
| Export omits microbiology missing while infection mimic visible | missing evidence loss blocked |
| Export omits source limitations | source limitation loss blocked |
| Export turns confidence limiter into probability | limiter-to-probability blocked |
| Export suppresses high-risk mimic visibility | mimic erasure blocked |
| Export selects one diagnosis from overlap | winner selection blocked |
| Export says urgent disposition needed | triage blocked |
| Export says MDD consensus achieved | MDD replacement blocked |
| Export audit section says clinically validated | audit-to-validation blocked |
| Export omits authority envelope | unsafe export blocked |
| Export omits no-decision statement | hidden decision risk blocked |
| Export uses patient-facing language | patient-facing leak blocked |
| Export marked public-ready | deployment claim blocked |

### 27.3 Red-Team Rule

> Every export red-team scenario must fail closed and preserve authority_effect: none.

---

## 28. v0.13.1 Acceptance Criteria

v0.13.1 is accepted only if:

- root safe session export object schema is defined,
- MDD preparation package object schema is defined,
- export header schema is defined,
- non-authority statement schema is defined,
- snapshot export reference schema is defined,
- case context export section schema is defined,
- temporal context export section schema is defined,
- source status export section schema is defined,
- missing evidence export section schema is defined,
- confidence limiter export section schema is defined,
- mimic visibility export section schema is defined,
- overlap export section schema is defined,
- review prompt export section schema is defined,
- audit reference export section schema is defined,
- authority envelope export section schema is defined,
- no-decision statement export section schema is defined,
- blocked output notice schema is defined,
- clinician note export boundary is defined,
- source reference appendix boundary is defined,
- audit reference appendix boundary is defined,
- package ordering rules are defined,
- export lifecycle is defined,
- export validation object is defined,
- unsafe export failure object is defined,
- export red-team schema is defined,
- safe export cannot become diagnostic report,
- MDD preparation package cannot become MDD replacement,
- snapshot export cannot become final clinical impression,
- audit reference cannot become validation,
- source status export cannot become clinical authority,
- no diagnosis is created,
- no exclusion is created,
- no treatment is created,
- no test order is created,
- no procedure decision is created,
- no follow-up schedule is created,
- no triage is created,
- no public readiness is created,
- no patient-facing use is created,
- no platform-wide clinical review is created.

---

## 29. Next Step

The next recommended step is:

- v0.13.2 — MDD Preparation Package Section Semantics / Safe Formatting Rules

v0.13.2 should define:

- safe section titles,
- safe table formats,
- safe badge language,
- safe ordering,
- safe clinician note formatting,
- unsafe report-like formats,
- unsafe impression-like headings,
- unsafe diagnostic conclusion blocks,
- unsafe action recommendation formatting,
- safe MDD discussion prompts,
- safe export disclaimers,
- no patient-facing formatting,
- no final report formatting.

v0.13.2 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 30. Governance Statement

This schema defines the safe session export object and MDD preparation package structure.

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

Safe export remains a governance layer, not a clinical reporting layer.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.13 rule remains:

> “A safe session export may prepare discussion, but it must not become diagnosis, treatment, order, procedure decision, follow-up schedule, triage report, patient-facing output, public-ready output, or clinical validation.”

For v0.13.1:

> “A safe export object is valid only if every section preserves source status, missing evidence, confidence limiters, mimic visibility, overlap, review prompts, audit references, authority envelope, and no-decision constraints.”