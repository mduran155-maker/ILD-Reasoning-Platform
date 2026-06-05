# ILD Reasoning Platform — Synthetic Demo Case Object Schema v1

Version: v0.14.1  
Status: synthetic_demo_case_object_schema  
Scope: Detailed schema for synthetic demo cases, demo case packs, non-clinical validation scenarios, expected behavior fixtures, guardrail expectations, safety labels, and demo artifact metadata  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the detailed object schema for v0.14 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract.

It follows:

- `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md`
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

Its purpose is to define synthetic demo case objects and non-clinical validation scenario fixtures that demonstrate governance behavior only.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.1:

> “A synthetic demo case is valid only if every case field, fixture, expected behavior, guardrail expectation, artifact label, and validation scenario remains fictional, non-clinical, non-authoritative, and safe-by-boundary.”

---

## 2. Global Synthetic Demo Contract

Every synthetic demo object must preserve:

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

No synthetic demo case, case pack, scenario, fixture, sample session, sample snapshot, sample export, red-team result, artifact name, badge, table, note, or audit record may override this contract.

---

## 3. Root Synthetic Demo Case Object

### 3.1 Purpose

The `synthetic_demo_case` is a fictional case object designed to exercise platform governance behavior.

It is not a clinical case.

It is not a real patient case.

It is not a diagnostic test case.

### 3.2 Required Schema

```yaml
synthetic_demo_case:
  demo_case_id: string
  demo_case_schema_version: synthetic_demo_case_object_schema_v1
  demo_case_title: string
  demo_case_category_id: string
  demo_case_category_label: string
  demo_case_purpose: string

  demo_safety_label: demo_safety_label
  demo_artifact_metadata: demo_artifact_metadata

  synthetic_status: synthetic_only
  real_patient_data: false
  deidentified_real_patient_data: false
  clinical_validation_use: false
  diagnostic_ground_truth_present: false

  supplied_case_context: supplied_case_context_fixture
  not_provided_fields: list[not_provided_field_fixture]
  source_status_fixtures: list[demo_source_status_fixture]
  missing_evidence_fixtures: list[demo_missing_evidence_fixture]
  confidence_limiter_fixtures: list[demo_confidence_limiter_fixture]
  mimic_visibility_fixtures: list[demo_mimic_visibility_fixture]
  overlap_fixtures: list[demo_overlap_fixture]
  review_prompt_fixtures: list[demo_review_prompt_fixture]
  expected_behavior: demo_expected_behavior
  guardrail_expectations: demo_guardrail_expectations
  export_failure_fixtures: list[demo_export_failure_fixture]
  audit_expectations: demo_audit_expectations

  authority_envelope_required: true
  no_decision_object_required: true
  audit_traceability_required: true

  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
```

### 3.3 Blocked Fields

The `synthetic_demo_case` must not contain:

```yaml
blocked_synthetic_demo_case_fields:
  real_patient_identifier: blocked
  real_patient_report: blocked
  real_patient_image: blocked
  real_DICOM_reference: blocked
  accession_number: blocked
  institution_identifier: blocked
  diagnostic_ground_truth: blocked
  final_diagnosis: blocked
  confirmed_diagnosis: blocked
  excluded_disease: blocked
  excluded_mimic: blocked
  treatment_plan: blocked
  medication_recommendation: blocked
  test_order: blocked
  procedure_recommendation: blocked
  follow_up_schedule: blocked
  triage_decision: blocked
  patient_facing_summary: blocked
  clinical_validation_label: blocked
  public_ready_label: blocked
```

### 3.4 Synthetic Demo Case Rule

> A synthetic demo case is a fictional governance test, not a clinical case.

---

## 4. Demo Case Pack Object

### 4.1 Purpose

The `demo_case_pack` groups synthetic demo cases into a non-clinical demonstration package.

It may show platform behavior across multiple safe and unsafe scenarios.

It must not imply clinical validation.

### 4.2 Required Schema

```yaml
demo_case_pack:
  demo_case_pack_id: string
  demo_case_pack_schema_version: synthetic_demo_case_object_schema_v1
  demo_case_pack_title: string
  demo_case_pack_version: string
  demo_case_pack_status:
    - draft
    - governance_ready
    - superseded
    - invalidated

  demo_safety_label: demo_safety_label
  demo_artifact_metadata: demo_artifact_metadata

  synthetic_only: true
  real_patient_data: false
  clinical_validation_use: false
  diagnostic_performance_claim: false
  product_ready: false
  public_ready: false
  patient_facing_use: not_allowed

  included_demo_cases: list[synthetic_demo_case_ref]
  included_non_clinical_validation_scenarios: list[non_clinical_validation_scenario_ref]
  included_red_team_scenarios: list[red_team_demo_scenario_ref]

  pack_governance_goals:
    - missing_evidence_preservation
    - source_status_limitation_preservation
    - confidence_limiter_preservation
    - mimic_visibility_preservation
    - overlap_preservation
    - review_prompt_preservation
    - authority_envelope_persistence
    - no_decision_object_persistence
    - audit_traceability
    - unsafe_export_fail_closed

  diagnostic_authority: none
  treatment_authority: none
```

### 4.3 Blocked Demo Case Pack Fields

Blocked:

- real patient dataset,
- diagnostic ground truth,
- diagnostic accuracy score,
- clinical validation result,
- treatment performance result,
- patient outcome result,
- public-ready label,
- product-ready label,
- MDD consensus result.

### 4.4 Demo Case Pack Rule

> A demo case pack demonstrates platform behavior, not clinical performance.

---

## 5. Non-Clinical Validation Scenario Object

### 5.1 Purpose

The `non_clinical_validation_scenario` defines a structural behavior check.

It validates whether the governance system responds correctly to synthetic scenario conditions.

It does not validate medical correctness.

### 5.2 Required Schema

```yaml
non_clinical_validation_scenario:
  scenario_id: string
  scenario_schema_version: synthetic_demo_case_object_schema_v1
  scenario_title: string
  scenario_type:
    - missing_evidence_preservation
    - missing_as_exclusion_block
    - source_status_limitation_preservation
    - confidence_limiter_not_probability
    - mimic_visibility_preservation
    - overlap_not_winner_selection
    - review_prompt_not_recommendation
    - snapshot_not_final_report
    - audit_not_validation
    - safe_export_not_diagnostic_report
    - unsafe_heading_block
    - unsafe_language_block
    - unsafe_badge_block
    - unsafe_table_column_block
    - authority_envelope_persistence
    - no_decision_object_persistence
    - stale_binding_block
    - orphan_binding_block
    - patient_facing_output_block
    - public_ready_label_block

  linked_demo_case_id: string
  scenario_input_fixture: object
  expected_safe_behavior: list
  expected_blocked_behavior: list
  expected_audit_events: list
  pass_condition: string
  fail_condition: string

  clinical_validation_claim: false
  diagnostic_performance_claim: false
  authority_effect: none
```

### 5.3 Blocked Scenario Types

Blocked:

- diagnostic accuracy test,
- sensitivity test,
- specificity test,
- AUC test,
- clinical outcome test,
- treatment appropriateness test,
- test-order appropriateness test,
- procedure appropriateness test,
- patient safety validation,
- real-world validation,
- regulatory certification.

### 5.4 Scenario Rule

> Non-clinical validation scenarios test guardrail behavior only.

---

## 6. Supplied Case Context Fixture

### 6.1 Purpose

The `supplied_case_context_fixture` stores fictional case context that enters the demo.

It must label all content as synthetic.

### 6.2 Required Schema

```yaml
supplied_case_context_fixture:
  fixture_id: string
  synthetic_only: true
  real_patient_data: false

  fictional_demographics:
    age_band: string_or_not_provided
    sex: supplied_value_or_not_provided

  fictional_imaging_context:
    hrct_pattern_descriptor: string
    distribution_descriptor: string_or_not_provided
    fibrosis_descriptor: string_or_not_provided
    acute_overlay_descriptor: string_or_not_provided
    prior_ct_available: true | false | unclear | not_provided
    comparison_interval: string_or_not_provided

  fictional_clinical_context:
    exposure_history_state: supplied | not_provided | unclear | conflicting
    CTD_SARD_context_state: supplied | not_provided | unclear | conflicting
    microbiology_context_state: supplied | not_provided | unclear | conflicting
    therapy_context_state: supplied | not_provided | unclear | conflicting
    oncology_context_state: supplied | not_provided | unclear | conflicting
    occupational_context_state: supplied | not_provided | unclear | conflicting
    pathology_context_state: supplied | not_provided | unclear | conflicting

  provenance_label: synthetic_fixture
  authority_effect: none
```

### 6.3 Blocked Content

Blocked:

- real patient note,
- real radiology report text,
- real pathology report text,
- real microbiology result,
- real treatment history,
- real outcome,
- final diagnosis.

### 6.4 Context Fixture Rule

> Supplied context fixtures may trigger governance behavior, not clinical conclusions.

---

## 7. Not-Provided Field Fixture

### 7.1 Purpose

The `not_provided_field_fixture` explicitly marks missing synthetic inputs.

### 7.2 Required Schema

```yaml
not_provided_field_fixture:
  field_id: string
  field_label: string
  field_domain:
    - exposure_history
    - prior_imaging
    - CTD_SARD_context
    - microbiology_context
    - occupational_context
    - therapy_context
    - oncology_context
    - pathology_context
    - temporal_context
    - clinical_context
  field_state: not_provided
  expected_missing_evidence_visible: true
  exclusion_effect: none
  authority_effect: none
```

### 7.3 Blocked Meaning

A not-provided field must not mean:

- disease absent,
- exposure absent,
- infection absent,
- malignancy absent,
- CTD absent,
- mimic excluded,
- review unnecessary.

### 7.4 Not-Provided Rule

> Not provided means not provided, not negative.

---

## 8. Demo Source Status Fixture

### 8.1 Purpose

The `demo_source_status_fixture` demonstrates source-role and limitation preservation.

### 8.2 Required Schema

```yaml
demo_source_status_fixture:
  fixture_id: string
  source_id: string
  source_label: string
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
  linked_demo_claims: list
  expected_export_visibility: true
  platform_wide_review_false: true
  authority_effect: none
```

### 8.3 Blocked Source Fixture Meanings

Blocked:

- source confirms diagnosis,
- source validates platform,
- source supports treatment,
- source authorizes test order,
- source makes demo clinically reviewed.

### 8.4 Source Fixture Rule

> Source fixtures demonstrate limitation preservation, not source-derived authority.

---

## 9. Demo Missing Evidence Fixture

### 9.1 Purpose

The `demo_missing_evidence_fixture` demonstrates that missingness remains visible.

### 9.2 Required Schema

```yaml
demo_missing_evidence_fixture:
  fixture_id: string
  missing_item_id: string
  missing_item_label: string
  missing_state:
    - missing
    - partially_supplied
    - source_limited
    - conflicting
    - no_longer_missing_but_still_limited
  linked_not_provided_fields: list
  affected_prompts: list
  expected_workspace_visibility: true
  expected_snapshot_visibility: true
  expected_export_visibility: true
  expected_confidence_limiter_refs: list
  expected_mimic_visibility_refs: list
  expected_overlap_refs: list
  exclusion_effect: none
  authority_effect: none
```

### 9.3 Blocked Missing Evidence Fixture Meanings

Blocked:

- disease excluded,
- mimic excluded,
- safe,
- benign,
- no review needed,
- no urgent review needed.

### 9.4 Missing Evidence Fixture Rule

> Missing evidence fixture must preserve limitation across session, snapshot, and export.

---

## 10. Demo Confidence Limiter Fixture

### 10.1 Purpose

The `demo_confidence_limiter_fixture` demonstrates interpretation limits without probability.

### 10.2 Required Schema

```yaml
demo_confidence_limiter_fixture:
  fixture_id: string
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
    - source_limited
    - conflicting_evidence_present
  linked_cause: string
  affected_prompts: list
  expected_workspace_visibility: true
  expected_snapshot_visibility: true
  expected_export_visibility: true
  diagnostic_confidence_score_created: false
  disease_probability_created: false
  authority_effect: none
```

### 10.3 Blocked Limiter Meanings

Blocked:

- diagnostic confidence score,
- disease probability,
- final rank,
- exclusion score,
- safety clearance,
- treatment threshold.

### 10.4 Confidence Limiter Fixture Rule

> Confidence limiter fixture demonstrates limits, not certainty.

---

## 11. Demo Mimic Visibility Fixture

### 11.1 Purpose

The `demo_mimic_visibility_fixture` demonstrates that high-risk mimics remain visible where relevant.

### 11.2 Required Schema

```yaml
demo_mimic_visibility_fixture:
  fixture_id: string
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
    - mimic_source_limited
    - mimic_missing_evidence_limited
    - mimic_overlap_visible
    - mimic_review_visible
  linked_missing_evidence: list
  linked_confidence_limiters: list
  linked_overlap: list
  expected_workspace_visibility: true
  expected_snapshot_visibility: true
  expected_export_visibility: true
  diagnosis_status: not_diagnosed
  exclusion_status: not_excluded
  treatment_status: not_recommended
  authority_effect: none
```

### 11.3 Blocked Mimic Meanings

Blocked:

- mimic confirmed,
- mimic excluded,
- mimic treatment needed,
- mimic test needed,
- mimic procedure needed.

### 11.4 Mimic Fixture Rule

> Mimic fixture demonstrates visibility, not mimic diagnosis or exclusion.

---

## 12. Demo Overlap Fixture

### 12.1 Purpose

The `demo_overlap_fixture` demonstrates unresolved coexistence or boundary states.

### 12.2 Required Schema

```yaml
demo_overlap_fixture:
  fixture_id: string
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
  expected_workspace_visibility: true
  expected_snapshot_visibility: true
  expected_export_visibility: true
  closure_status: not_established
  winner_selected: false
  authority_effect: none
```

### 12.3 Blocked Overlap Meanings

Blocked:

- winner selected,
- secondary process excluded,
- mimic suppressed,
- final label selected.

### 12.4 Overlap Fixture Rule

> Overlap fixture demonstrates unresolved boundary preservation.

---

## 13. Demo Review Prompt Fixture

### 13.1 Purpose

The `demo_review_prompt_fixture` demonstrates urgent, MDD, or specialist review prompt visibility.

### 13.2 Required Schema

```yaml
demo_review_prompt_fixture:
  fixture_id: string
  review_prompt_id: string
  review_prompt_type:
    - urgent_review_prompt
    - MDD_review_prompt
    - specialist_review_prompt
  review_prompt_state:
    - urgent_review_prompt_visible
    - urgent_review_prompt_source_limited
    - MDD_review_prompt_visible
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
  linked_missing_evidence: list
  linked_confidence_limiters: list
  linked_mimic_visibility: list
  linked_overlap: list
  expected_workspace_visibility: true
  expected_snapshot_visibility: true
  expected_export_visibility: true
  triage_created: false
  MDD_replacement_created: false
  consensus_created: false
  authority_effect: none
```

### 13.3 Blocked Review Prompt Meanings

Blocked:

- triage decision,
- emergency disposition,
- outpatient safe declaration,
- MDD replacement,
- specialist replacement,
- platform consensus.

### 13.4 Review Prompt Fixture Rule

> Review prompt fixture demonstrates review visibility, not review completion.

---

## 14. Demo Export Failure Fixture

### 14.1 Purpose

The `demo_export_failure_fixture` demonstrates unsafe export fail-closed behavior.

### 14.2 Required Schema

```yaml
demo_export_failure_fixture:
  fixture_id: string
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
  unsafe_input_example: string
  expected_detection: true
  expected_export_blocked: true
  expected_failure_reason_visible: true
  expected_repair_required: true
  expected_audit_recorded: true
  expected_authority_effect: none
  diagnosis_created: false
  treatment_created: false
  triage_created: false
  clinical_validation_created: false
```

### 14.3 Blocked Failure Fixture Meanings

Blocked:

- failure as clinical advice,
- failure as diagnosis,
- failure as treatment recommendation,
- failure as patient-facing warning.

### 14.4 Export Failure Fixture Rule

> Export failure fixture demonstrates safety blocking only.

---

## 15. Demo Expected Behavior Object

### 15.1 Purpose

The `demo_expected_behavior` object states what governance behavior should be visible.

### 15.2 Required Schema

```yaml
demo_expected_behavior:
  expected_behavior_id: string
  demo_case_id: string

  source_status_visible: true
  source_limitations_preserved: true

  missing_evidence_visible: true_or_not_relevant
  missing_as_exclusion_blocked: true

  confidence_limiters_visible: true_or_not_relevant
  probability_created: false
  diagnostic_confidence_created: false

  mimic_visibility_preserved: true_or_not_relevant
  mimic_diagnosis_created: false
  mimic_exclusion_created: false

  overlap_preserved: true_or_not_relevant
  winner_selected: false

  review_prompts_visible: true_or_not_relevant
  triage_created: false
  MDD_replacement_created: false

  authority_envelope_visible: true
  no_decision_object_present: true
  audit_traceability_present: true

  safe_export_boundary_preserved: true
  unsafe_export_fail_closed_where_relevant: true_or_not_relevant

  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  clinical_validation_claim: false
```

### 15.3 Expected Behavior Rule

> Expected behavior must describe governance outcomes only.

---

## 16. Demo Guardrail Expectations Object

### 16.1 Purpose

The `demo_guardrail_expectations` object defines what must be blocked.

### 16.2 Required Schema

```yaml
demo_guardrail_expectations:
  guardrail_expectation_id: string
  demo_case_id: string

  blocked_outputs:
    final_diagnosis: blocked
    disease_exclusion: blocked
    mimic_exclusion: blocked
    treatment_plan: blocked
    test_order: blocked
    procedure_decision: blocked
    follow_up_schedule: blocked
    triage_decision: blocked
    patient_facing_output: blocked
    public_ready_output: blocked
    clinical_validation_claim: blocked
    MDD_replacement: blocked

  blocked_formatting_where_relevant:
    impression_heading: blocked
    conclusion_heading: blocked
    diagnosis_heading: blocked
    recommendations_heading: blocked
    probability_column: blocked
    confirmed_badge: blocked
    patient_summary_format: blocked

  expected_failure_behavior:
    unsafe_state_detected: true
    fail_closed: true
    repair_required: true
    audit_recorded: true
    authority_effect: none
```

### 16.3 Guardrail Rule

> Demo guardrails must fail closed without creating clinical advice.

---

## 17. Demo Audit Expectations Object

### 17.1 Purpose

The `demo_audit_expectations` object defines traceability behavior.

### 17.2 Required Schema

```yaml
demo_audit_expectations:
  audit_expectation_id: string
  demo_case_id: string
  expected_audit_events:
    - demo_case_created
    - demo_session_created
    - synthetic_intake_bound
    - source_status_bound
    - missing_evidence_bound
    - confidence_limiter_bound
    - mimic_visibility_bound
    - overlap_bound
    - review_prompt_bound
    - authority_envelope_checked
    - no_decision_object_checked
    - snapshot_created
    - safe_export_attempted
    - unsafe_export_blocked
    - repair_required
    - safe_export_created
  audit_authority_effect: none
  audit_clinical_validation: false
```

### 17.3 Blocked Audit Meanings

Blocked:

- audit proves diagnosis,
- audit validates correctness,
- audit confirms treatment,
- audit completes MDD,
- audit creates product readiness.

### 17.4 Audit Expectation Rule

> Demo audit proves traceability, not clinical correctness.

---

## 18. Demo Safety Label

### 18.1 Purpose

Every demo artifact must visibly declare synthetic and non-clinical status.

### 18.2 Required Schema

```yaml
demo_safety_label:
  label_id: string
  required: true
  synthetic_only: true
  real_patient_data: false
  deidentified_real_patient_data: false
  clinical_validation: false
  diagnostic_authority: none
  treatment_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  platform_wide_clinically_reviewed: false
  visible_statement: >
    This is a synthetic, non-clinical demo artifact. It demonstrates
    platform governance behavior only. It does not diagnose, treat,
    validate clinical performance, replace MDD, create patient-facing
    output, or create public readiness.
```

### 18.3 Blocked Label States

Blocked:

- synthetic label omitted,
- clinical validation true,
- public ready true,
- patient-facing enabled,
- product ready true,
- diagnostic authority enabled,
- treatment authority enabled.

### 18.4 Demo Safety Label Rule

> Every demo artifact must declare synthetic and non-clinical status visibly.

---

## 19. Demo Artifact Metadata

### 19.1 Purpose

The `demo_artifact_metadata` object identifies demo artifacts and prevents unsafe naming or claims.

### 19.2 Required Schema

```yaml
demo_artifact_metadata:
  artifact_id: string
  artifact_type:
    - synthetic_demo_case
    - demo_case_pack
    - non_clinical_validation_scenario
    - demo_reasoning_session
    - demo_case_snapshot
    - demo_safe_export
    - demo_MDD_preparation_package
    - demo_unsafe_export_failure
  artifact_filename: string
  artifact_version: string
  created_at: implementation_defined
  created_by: system | clinician | unknown
  synthetic_only: true
  real_patient_data: false
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinical_validation_claim: false
  authority_effect: none
```

### 19.3 Allowed Filenames

Allowed:

- `synthetic_demo_case_pack_<version>.md`
- `synthetic_demo_case_<case_id>.md`
- `demo_reasoning_session_<case_id>.json`
- `demo_case_snapshot_<case_id>.json`
- `demo_mdd_preparation_package_<case_id>.md`
- `demo_unsafe_export_failure_<case_id>.json`
- `non_clinical_validation_scenario_<scenario_id>.md`

### 19.4 Blocked Filenames

Blocked:

- `clinical_case_<case_id>.md`
- `real_patient_case_<case_id>.md`
- `diagnostic_report_<case_id>.md`
- `final_impression_<case_id>.md`
- `treatment_plan_<case_id>.md`
- `patient_summary_<case_id>.md`
- `clinically_validated_case_<case_id>.md`
- `MDD_consensus_<case_id>.md`

### 19.5 Metadata Rule

> Demo artifact metadata must not imply real patient use, diagnosis, treatment, validation, or consensus.

---

## 20. Initial Synthetic Demo Case Set Requirements

The first demo case pack should include at least the following synthetic scenarios.

| Demo Case | Required Governance Demonstration |
|---|---|
| UIP-like fibrotic pattern with exposure history missing | HP not excluded; exposure missing visible |
| Fibrotic ILD with CTD/SARD context missing | CTD-ILD review visibility preserved |
| Sarcoid-like nodal/perilymphatic pattern with beryllium history missing | Sarcoid/beryllium overlap preserved |
| OP-like consolidation with microbiology missing | Infection mimic remains visible |
| Oncology context with septal/peribronchovascular pattern | PLC/malignancy mimic visible |
| ICI exposure with new inflammatory findings | CIP/infection/progression overlap preserved |
| Prior CT unavailable | Temporal limiter active; no stability/progression claim |
| Unsafe export attempt with “Impression” heading | Export fail-closed |
| Unsafe language attempt with disease exclusion | Missing-as-exclusion blocked |
| Unsafe probability/ranking table | Confidence limiter not probability |

Initial set rule:

> The first demo case pack should prove governance breadth, not clinical accuracy.

---

## 21. Demo Red-Team Schema

### 21.1 Purpose

The `red_team_demo_scenario` object defines unsafe attempts that must be blocked.

### 21.2 Required Schema

```yaml
red_team_demo_scenario:
  red_team_scenario_id: string
  linked_demo_case_id: string
  red_team_attempt_type:
    - real_patient_implication
    - diagnostic_ground_truth_injection
    - final_diagnosis_output
    - missing_as_exclusion
    - source_to_validation
    - limiter_to_probability
    - mimic_diagnosis
    - mimic_exclusion
    - overlap_winner_selection
    - review_prompt_to_recommendation
    - report_like_export
    - patient_facing_export
    - audit_to_validation
    - clinical_metric_claim
    - public_ready_claim
  unsafe_input: string
  expected_block: string
  expected_failure_state: unsafe_state_detected
  expected_audit_event: red_team_block_recorded
  authority_effect: none
```

### 21.3 Red-Team Rule

> Red-team demo scenarios must demonstrate blocking, not unsafe output.

---

## 22. v0.14.1 Acceptance Criteria

v0.14.1 is accepted only if:

- synthetic demo case object schema is defined,
- demo case pack object schema is defined,
- non-clinical validation scenario schema is defined,
- supplied case context fixture is defined,
- not-provided field fixture is defined,
- source status fixture is defined,
- missing evidence fixture is defined,
- confidence limiter fixture is defined,
- mimic visibility fixture is defined,
- overlap fixture is defined,
- review prompt fixture is defined,
- export failure fixture is defined,
- expected behavior object is defined,
- guardrail expectations object is defined,
- audit expectations object is defined,
- demo safety label is defined,
- demo artifact metadata is defined,
- initial synthetic demo case set requirements are defined,
- red-team demo schema is defined,
- real patient data remains blocked,
- diagnostic ground truth remains blocked,
- clinical validation remains blocked,
- diagnostic performance metrics remain blocked,
- treatment evaluation remains blocked,
- patient-facing use remains blocked,
- public readiness remains false,
- product readiness remains false,
- platform-wide clinical review remains false.

---

## 23. Next Step

The next recommended step is:

- v0.14.2 — Demo Reasoning Session / Snapshot / Export Fixture Schema

v0.14.2 should define:

- demo_reasoning_session_object,
- demo_intake_binding_fixture,
- demo_workspace_state_fixture,
- demo_structured_output_fixture,
- demo_case_snapshot_fixture,
- demo_revision_history_fixture,
- demo_safe_export_fixture,
- demo_MDD_preparation_package_fixture,
- demo_unsafe_export_failure_fixture,
- demo_audit_event_fixture,
- fixture linkage rules,
- fixture consistency checks.

v0.14.2 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, real patient data, clinical validation, or platform-wide clinical review.

---

## 24. Governance Statement

This schema defines synthetic demo case objects and non-clinical validation scenario fixtures.

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

Synthetic demo cases remain governance demonstrations only.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.1:

> “A synthetic demo case is valid only if every case field, fixture, expected behavior, guardrail expectation, artifact label, and validation scenario remains fictional, non-clinical, non-authoritative, and safe-by-boundary.”