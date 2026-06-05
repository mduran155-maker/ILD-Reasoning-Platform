# ILD Reasoning Platform — Safe Export Validation State Machine / Unsafe Export Failure Rules v1

Version: v0.13.3  
Status: safe_export_validation_state_machine_unsafe_failure_rules  
Scope: Export validation states, unsafe export detection, fail-closed behavior, repair, invalidation, supersession, and audit-linked safety governance  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the safe export validation state machine and unsafe export failure rules for v0.13 — Safe Session Export / MDD Preparation Package Contract.

It follows:

- `docs/navigation/safe_session_export_mdd_preparation_entry_gate_v1.md`
- `docs/data/schema/safe_session_export_object_schema_package_structure_v1.md`
- `docs/data/schema/mdd_preparation_package_section_semantics_safe_formatting_rules_v1.md`
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

Its purpose is to define how every safe session export and MDD preparation package must be validated before use.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.13 rule remains:

> “A safe session export may prepare discussion, but it must not become diagnosis, treatment, order, procedure decision, follow-up schedule, triage report, patient-facing output, public-ready output, or clinical validation.”

For v0.13.3:

> “An export is safe only after snapshot eligibility, section presence, formatting, language, authority envelope, no-decision, binding integrity, and audit checks pass; otherwise it must fail closed.”

---

## 2. Global Export Validation Contract

Every export validation state, transition, failure, repair, invalidation, supersession, and audit event must preserve:

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

No validation success may mean clinical correctness.

No validation failure may create clinical guidance.

No repair may create authority.

No override may bypass blocked outputs.

---

## 3. Export Validation Principle

Export validation may confirm:

- required export sections are present,
- snapshot is eligible,
- authority envelope is present,
- no-decision statement is present,
- blocked output notice is present,
- source limitations are preserved,
- missing evidence is preserved,
- confidence limiters are preserved,
- mimic visibility is preserved where relevant,
- overlap is preserved where relevant,
- review prompts are preserved where relevant,
- audit references are preserved,
- stale bindings are blocked,
- orphan bindings are blocked,
- unsafe headings are absent,
- unsafe badges are absent,
- unsafe table columns are absent,
- unsafe action formatting is absent,
- patient-facing formatting is absent,
- public-ready formatting is absent,
- clinical validation language is absent.

Export validation must not confirm:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment,
- test ordering,
- procedure decision,
- follow-up scheduling,
- triage,
- MDD consensus,
- specialist conclusion,
- clinical correctness,
- patient-facing readiness,
- public readiness.

Validation rule:

> Export validation confirms governance safety, not clinical truth.

---

## 4. Export Validation State Registry

Allowed export validation states:

| State ID | State Name | Meaning |
|---|---|---|
| V13_EXPORT_STATE_001 | export_draft | Export object exists but is not validated |
| V13_EXPORT_STATE_002 | validation_pending | Validation requested |
| V13_EXPORT_STATE_003 | snapshot_eligibility_checked | Source snapshot eligibility checked |
| V13_EXPORT_STATE_004 | required_sections_checked | Required sections checked |
| V13_EXPORT_STATE_005 | authority_envelope_checked | Authority envelope checked |
| V13_EXPORT_STATE_006 | no_decision_statement_checked | No-decision statement checked |
| V13_EXPORT_STATE_007 | blocked_output_notice_checked | Blocked output notice checked |
| V13_EXPORT_STATE_008 | binding_integrity_checked | Stale/orphan binding checks completed |
| V13_EXPORT_STATE_009 | source_status_checked | Source status preservation checked |
| V13_EXPORT_STATE_010 | missing_evidence_checked | Missing evidence preservation checked |
| V13_EXPORT_STATE_011 | confidence_limiter_checked | Limiter preservation checked |
| V13_EXPORT_STATE_012 | mimic_overlap_review_checked | Mimic/overlap/review prompts checked |
| V13_EXPORT_STATE_013 | formatting_checked | Heading/badge/table/list/layout checks completed |
| V13_EXPORT_STATE_014 | language_checked | Unsafe language check completed |
| V13_EXPORT_STATE_015 | non_patient_facing_checked | Patient-facing boundary checked |
| V13_EXPORT_STATE_016 | audit_reference_checked | Audit reference preservation checked |
| V13_EXPORT_STATE_017 | export_governance_safe | Export passed governance safety |
| V13_EXPORT_STATE_018 | unsafe_export_detected | Unsafe export condition detected |
| V13_EXPORT_STATE_019 | export_blocked | Export use blocked |
| V13_EXPORT_STATE_020 | repair_required | Repair required before export |
| V13_EXPORT_STATE_021 | repair_pending | Repair process started |
| V13_EXPORT_STATE_022 | repaired_export_revalidation_pending | Repaired export requires revalidation |
| V13_EXPORT_STATE_023 | export_superseded | Export superseded by newer safe export |
| V13_EXPORT_STATE_024 | export_invalidated | Export invalidated and unusable |
| V13_EXPORT_STATE_025 | export_audit_recorded | Export validation/failure event audited |

Blocked export validation states:

| Blocked State | Why Blocked |
|---|---|
| clinically_validated | validation is not clinical review |
| diagnosis_validated | diagnosis authority leak |
| treatment_validated | treatment authority leak |
| order_ready | test-order authority leak |
| procedure_ready | procedure authority leak |
| follow_up_ready | follow-up authority leak |
| triage_ready | triage authority leak |
| patient_ready | patient-facing leak |
| public_ready | deployment leak |
| MDD_consensus_created | MDD replacement leak |

---

## 5. Export Validation Event Registry

Allowed validation events:

| Event ID | Event | Meaning |
|---|---|---|
| V13_EXPORT_EVENT_001 | export_created | Export draft created |
| V13_EXPORT_EVENT_002 | validation_requested | Validation requested |
| V13_EXPORT_EVENT_003 | snapshot_eligibility_passed | Snapshot eligible |
| V13_EXPORT_EVENT_004 | snapshot_eligibility_failed | Snapshot ineligible |
| V13_EXPORT_EVENT_005 | required_sections_passed | Required sections present |
| V13_EXPORT_EVENT_006 | required_sections_failed | Required section missing |
| V13_EXPORT_EVENT_007 | authority_envelope_passed | Authority envelope present and valid |
| V13_EXPORT_EVENT_008 | authority_envelope_failed | Authority envelope missing/invalid |
| V13_EXPORT_EVENT_009 | no_decision_statement_passed | No-decision statement present and valid |
| V13_EXPORT_EVENT_010 | no_decision_statement_failed | No-decision statement missing/invalid |
| V13_EXPORT_EVENT_011 | blocked_output_notice_passed | Blocked output notice present |
| V13_EXPORT_EVENT_012 | blocked_output_notice_failed | Blocked output notice missing/invalid |
| V13_EXPORT_EVENT_013 | binding_integrity_passed | Stale/orphan checks passed |
| V13_EXPORT_EVENT_014 | binding_integrity_failed | Stale/orphan issue detected |
| V13_EXPORT_EVENT_015 | source_status_passed | Source limitations preserved |
| V13_EXPORT_EVENT_016 | source_status_failed | Source limitations lost |
| V13_EXPORT_EVENT_017 | missing_evidence_passed | Missing evidence preserved |
| V13_EXPORT_EVENT_018 | missing_evidence_failed | Missing evidence lost or reframed unsafely |
| V13_EXPORT_EVENT_019 | confidence_limiter_passed | Limiters preserved |
| V13_EXPORT_EVENT_020 | confidence_limiter_failed | Limiters lost or converted to probability |
| V13_EXPORT_EVENT_021 | mimic_overlap_review_passed | Mimic/overlap/review visibility preserved |
| V13_EXPORT_EVENT_022 | mimic_overlap_review_failed | Mimic/overlap/review state unsafe |
| V13_EXPORT_EVENT_023 | formatting_passed | Safe formatting passed |
| V13_EXPORT_EVENT_024 | formatting_failed | Unsafe formatting detected |
| V13_EXPORT_EVENT_025 | language_passed | Safe language passed |
| V13_EXPORT_EVENT_026 | language_failed | Unsafe language detected |
| V13_EXPORT_EVENT_027 | non_patient_facing_passed | Non-patient-facing boundary preserved |
| V13_EXPORT_EVENT_028 | non_patient_facing_failed | Patient-facing leak detected |
| V13_EXPORT_EVENT_029 | audit_reference_passed | Audit references preserved |
| V13_EXPORT_EVENT_030 | audit_reference_failed | Audit references missing/unsafe |
| V13_EXPORT_EVENT_031 | export_marked_governance_safe | Export marked governance-safe |
| V13_EXPORT_EVENT_032 | unsafe_export_blocked | Unsafe export blocked |
| V13_EXPORT_EVENT_033 | repair_requested | Repair requested |
| V13_EXPORT_EVENT_034 | repair_completed | Repair completed |
| V13_EXPORT_EVENT_035 | revalidation_requested | Revalidation requested |
| V13_EXPORT_EVENT_036 | export_superseded | Export superseded |
| V13_EXPORT_EVENT_037 | export_invalidated | Export invalidated |
| V13_EXPORT_EVENT_038 | export_audit_recorded | Export audit recorded |

Blocked validation events:

- diagnosis_confirmed,
- diagnosis_validated,
- treatment_authorized,
- test_order_created,
- procedure_recommended,
- follow_up_scheduled,
- triage_completed,
- MDD_consensus_created,
- patient_report_created,
- public_ready_enabled,
- clinical_correctness_certified.

---

## 6. Export Validation State Machine

### 6.1 Allowed Success Path

```yaml
safe_export_validation_state_machine:
  export_draft:
    event: validation_requested
    next_state: validation_pending

  validation_pending:
    event: snapshot_eligibility_passed
    next_state: snapshot_eligibility_checked

  snapshot_eligibility_checked:
    event: required_sections_passed
    next_state: required_sections_checked

  required_sections_checked:
    event: authority_envelope_passed
    next_state: authority_envelope_checked

  authority_envelope_checked:
    event: no_decision_statement_passed
    next_state: no_decision_statement_checked

  no_decision_statement_checked:
    event: blocked_output_notice_passed
    next_state: blocked_output_notice_checked

  blocked_output_notice_checked:
    event: binding_integrity_passed
    next_state: binding_integrity_checked

  binding_integrity_checked:
    event: source_status_passed
    next_state: source_status_checked

  source_status_checked:
    event: missing_evidence_passed
    next_state: missing_evidence_checked

  missing_evidence_checked:
    event: confidence_limiter_passed
    next_state: confidence_limiter_checked

  confidence_limiter_checked:
    event: mimic_overlap_review_passed
    next_state: mimic_overlap_review_checked

  mimic_overlap_review_checked:
    event: formatting_passed
    next_state: formatting_checked

  formatting_checked:
    event: language_passed
    next_state: language_checked

  language_checked:
    event: non_patient_facing_passed
    next_state: non_patient_facing_checked

  non_patient_facing_checked:
    event: audit_reference_passed
    next_state: audit_reference_checked

  audit_reference_checked:
    event: export_marked_governance_safe
    next_state: export_governance_safe
```

### 6.2 Failure Path

```yaml
unsafe_export_failure_path:
  any_validation_state:
    event:
      - snapshot_eligibility_failed
      - required_sections_failed
      - authority_envelope_failed
      - no_decision_statement_failed
      - blocked_output_notice_failed
      - binding_integrity_failed
      - source_status_failed
      - missing_evidence_failed
      - confidence_limiter_failed
      - mimic_overlap_review_failed
      - formatting_failed
      - language_failed
      - non_patient_facing_failed
      - audit_reference_failed
    next_state: unsafe_export_detected

  unsafe_export_detected:
    event: unsafe_export_blocked
    next_state: export_blocked

  export_blocked:
    event: repair_requested
    next_state: repair_required

  repair_required:
    event: repair_completed
    next_state: repaired_export_revalidation_pending

  repaired_export_revalidation_pending:
    event: revalidation_requested
    next_state: validation_pending
```

### 6.3 State Machine Rule

> A safe export must pass every validation state; any failure blocks export and requires repair plus revalidation.

---

## 7. Snapshot Eligibility Check

### 7.1 Required Checks

A snapshot is export-eligible only if:

| Check | Required Result |
|---|---|
| snapshot exists | true |
| snapshot belongs to session | true |
| snapshot_is_final_report | false |
| snapshot_is_patient_facing | false |
| snapshot_is_public_ready | false |
| snapshot_is_clinically_validated | false |
| authority_envelope_ref present | true |
| no_decision_object_ref present | true |
| stale bindings present as current | false |
| orphan bindings present | false |
| audit_event_refs present | true |
| source_status limitations preserved | true |
| missing evidence preserved | true |
| confidence limiters preserved | true |
| mimic visibility preserved where relevant | true |
| overlap preserved where relevant | true |
| review prompts preserved where relevant | true |

### 7.2 Failure Reasons

Snapshot eligibility fails if:

- snapshot missing,
- snapshot not linked to session,
- snapshot marked final report,
- snapshot marked patient-facing,
- snapshot marked public-ready,
- snapshot marked clinically validated,
- authority envelope missing,
- no-decision object missing,
- stale current binding present,
- orphan binding present,
- audit references missing,
- source status limitation lost,
- missing evidence lost,
- confidence limiter lost,
- mimic visibility lost where relevant,
- overlap lost where relevant,
- review prompt lost where relevant.

Snapshot eligibility rule:

> Only a governance-valid snapshot may start export validation.

---

## 8. Required Section Presence Check

Every safe export must contain:

- export header,
- non-authority statement,
- snapshot export reference,
- authority envelope export section,
- no-decision statement export section,
- blocked output notice,
- case context export section,
- source status export section,
- missing evidence export section,
- confidence limiter export section,
- audit reference export section.

Where relevant, every safe export must contain:

- temporal context export section,
- mimic visibility export section,
- overlap export section,
- review prompt export section.

Optional safe sections:

- clinician note export section,
- local workflow note export section,
- source reference appendix,
- audit reference appendix.

Blocked missing section cases:

- no authority envelope,
- no no-decision statement,
- no blocked output notice,
- no source status section,
- no missing evidence section,
- no confidence limiter section,
- no audit reference section,
- high-risk mimic relevant but mimic section absent,
- overlap relevant but overlap section absent,
- review prompt relevant but review section absent.

Section presence rule:

> A safe export must preserve limitation, missingness, traceability, and authority boundaries as visible sections.

---

## 9. Authority Envelope Validation Check

### 9.1 Required State

```yaml
authority_envelope_validation:
  diagnostic_authority: none
  treatment_authority: none
  public_ready: false
  clinically_reviewed.platform_wide: false
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

### 9.2 Failure Conditions

Authority envelope validation fails if:

- authority envelope missing,
- authority envelope hidden,
- authority envelope appears after all reasoning content only,
- diagnostic_authority is not none,
- treatment_authority is not none,
- public_ready is not false,
- patient_facing_use is not not_allowed,
- clinically_reviewed.platform_wide is not false,
- authority envelope is editable,
- authority envelope is removable,
- export omits authority envelope.

Authority envelope rule:

> Export without a visible and correct authority envelope is invalid.

---

## 10. No-Decision Statement Validation Check

### 10.1 Required State

```yaml
no_decision_validation:
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

### 10.2 Failure Conditions

No-decision validation fails if:

- no-decision statement missing,
- blocked category omitted,
- blocked category softened,
- hidden decision field detected,
- final diagnosis object appears elsewhere,
- treatment plan object appears elsewhere,
- test order object appears elsewhere,
- procedure decision object appears elsewhere,
- follow-up schedule object appears elsewhere,
- triage object appears elsewhere,
- patient-facing output appears elsewhere,
- public-ready output appears elsewhere.

No-decision rule:

> Export must explicitly remember what it cannot become.

---

## 11. Blocked Output Notice Validation Check

Required blocked categories:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment recommendation,
- test ordering,
- procedure decision,
- follow-up scheduling,
- triage / disposition,
- public readiness,
- clinical validation,
- patient-facing report,
- MDD replacement,
- urgent review replacement.

Failure conditions:

- blocked output notice missing,
- diagnosis block omitted,
- treatment block omitted,
- test-order block omitted,
- procedure block omitted,
- follow-up block omitted,
- triage block omitted,
- patient-facing block omitted,
- public-ready block omitted,
- clinical validation block omitted,
- blocked output notice hidden in unreadable footer only.

Blocked output notice rule:

> Blocked categories must be visible, not hidden.

---

## 12. Binding Integrity Validation Check

### 12.1 Required Checks

Binding validation must confirm:

- no stale binding is exported as current,
- no orphan binding is exported,
- every exported section links to source snapshot,
- every mutation has audit reference,
- authority envelope binding is present,
- no-decision object binding is present,
- source status bindings remain linked,
- missing evidence bindings remain linked,
- confidence limiter bindings remain linked,
- mimic visibility bindings remain linked where relevant,
- overlap bindings remain linked where relevant,
- review prompt bindings remain linked where relevant.

### 12.2 Failure Conditions

Binding integrity fails if:

- stale binding included as current,
- orphan binding detected,
- section lacks snapshot reference,
- section lacks audit reference after mutation,
- authority envelope binding missing,
- no-decision binding missing,
- source status detached,
- missing evidence detached,
- confidence limiter detached,
- mimic visibility detached where relevant,
- overlap detached where relevant,
- review prompt detached where relevant.

Binding integrity rule:

> Export must not carry stale, orphaned, or detached reasoning state.

---

## 13. Source Status Validation Check

Required:

- source IDs preserved,
- source role classes preserved,
- claim mapping status preserved,
- source limitations preserved,
- treatment-heavy warnings preserved where relevant,
- diagnostic-performance warnings preserved where relevant,
- case-example-only warnings preserved where relevant,
- platform-wide review false preserved.

Failure conditions:

- source limitation omitted,
- source role upgraded without audit,
- claim mapping status omitted,
- treatment-heavy warning removed,
- diagnostic-performance warning removed,
- case-example warning removed,
- source status described as clinically validated,
- source status described as confirming diagnosis,
- source status described as authorizing treatment.

Source status rule:

> Source status may support transparency but cannot become authority.

---

## 14. Missing Evidence Validation Check

Required:

- missing evidence section present,
- missing evidence states preserved,
- missing evidence linked to affected prompts,
- missing evidence linked to confidence limiters where relevant,
- missing evidence linked to mimics where relevant,
- missing evidence linked to overlap where relevant,
- missing evidence linked to review prompts where relevant,
- missing evidence not reframed as negative evidence.

Failure conditions:

- missing evidence omitted,
- missing evidence removed without supplied evidence,
- missing evidence described as exclusion,
- missing evidence suppresses mimic visibility,
- missing evidence described as benignity,
- missing evidence described as safety,
- missing evidence converted into “not present” without explicit supplied evidence.

Missing evidence rule:

> Missing evidence must remain visible as limitation, not exclusion.

---

## 15. Confidence Limiter Validation Check

Required:

- confidence limiter section present,
- limiter types preserved,
- limiter states preserved,
- linked cause present,
- affected prompts preserved,
- linked missing evidence preserved,
- linked source status preserved,
- diagnostic confidence not generated,
- probability not generated.

Failure conditions:

- limiter omitted,
- limiter detached from cause,
- limiter converted into probability,
- limiter converted into ranking,
- limiter converted into diagnostic confidence,
- limiter converted into safety clearance,
- limiter converted into treatment threshold.

Confidence limiter rule:

> Limiters explain interpretation limits, not diagnostic certainty.

---

## 16. Mimic / Overlap / Review Prompt Validation Check

### 16.1 Mimic Checks

Required:

- high-risk mimic visibility preserved where relevant,
- mimic state preserved,
- linked missing evidence preserved,
- linked confidence limiters preserved,
- linked overlap preserved,
- mimic diagnosis not created,
- mimic exclusion not created.

Failure:

- mimic omitted where relevant,
- mimic suppressed by missing evidence,
- mimic confirmed,
- mimic excluded,
- mimic linked to treatment/test/procedure recommendation.

### 16.2 Overlap Checks

Required:

- overlap preserved where relevant,
- overlap state preserved,
- involved prompts preserved,
- linked mimics preserved,
- closure status not established,
- winner not selected.

Failure:

- overlap omitted where relevant,
- overlap converted to winner selection,
- secondary process excluded,
- mimic suppressed,
- final label selected.

### 16.3 Review Prompt Checks

Required:

- urgent/MDD/specialist prompts preserved where relevant,
- prompt type preserved,
- linked evidence and limiters preserved,
- triage not created,
- MDD replacement not created,
- consensus not created.

Failure:

- urgent banner becomes disposition,
- MDD prompt becomes consensus,
- specialist prompt becomes specialist replacement,
- review prompt says no review needed without human conclusion.

Mimic/overlap/review rule:

> Safety visibility must remain visible without becoming closure or action.

---

## 17. Formatting Validation Check

### 17.1 Unsafe Heading Detection

Blocked headings:

- Impression,
- Conclusion,
- Diagnosis,
- Final Diagnosis,
- Clinical Impression,
- Assessment,
- Plan,
- Recommendations,
- Next Steps,
- Management,
- Workup,
- Biopsy Recommendation,
- Follow-Up,
- Triage,
- Disposition,
- Patient Summary,
- Validated Findings,
- Consensus,
- MDD Conclusion,
- Final Report.

Failure:

- any blocked heading appears,
- heading synonym implies diagnosis/action/closure,
- highest hierarchy emphasizes disease label before safety boundary.

### 17.2 Unsafe Badge Detection

Blocked badges:

- Confirmed,
- Diagnosed,
- Ruled out,
- Excluded,
- Negative,
- Benign,
- Safe,
- Treatment required,
- Test required,
- Biopsy required,
- Follow-up due,
- Triage needed,
- Validated,
- Clinically reviewed,
- Patient-ready,
- Public-ready,
- Consensus reached.

Failure:

- blocked badge appears,
- green badge implies diagnosis/exclusion/treatment safety,
- red badge implies triage decision,
- badge implies clinical validation.

### 17.3 Unsafe Table Column Detection

Blocked columns:

- Diagnosis,
- Final Diagnosis,
- Probability,
- Confidence %,
- Risk Score,
- Rule Out,
- Excluded,
- Treatment,
- Recommended Treatment,
- Test to Order,
- Biopsy,
- Follow-Up,
- Triage,
- Disposition,
- Action Required,
- Clinical Validation.

Failure:

- blocked table column appears,
- table ranks diseases,
- table assigns disease probabilities,
- table creates action list.

Formatting rule:

> Formatting must look like review preparation, not diagnosis, management, triage, or validation.

---

## 18. Language Validation Check

### 18.1 Blocked Verbs

Blocked verbs:

- diagnoses,
- confirms,
- proves,
- establishes,
- rules out,
- excludes,
- recommends,
- orders,
- requires,
- treats,
- schedules,
- triages,
- clears,
- validates,
- certifies,
- decides,
- determines.

### 18.2 Blocked Phrases

Blocked phrases:

- final diagnosis,
- diagnostic impression,
- confirmed diagnosis,
- ruled out,
- excluded,
- treatment plan,
- recommended test,
- biopsy required,
- follow-up due,
- triage decision,
- safe for outpatient care,
- clinically validated,
- patient-ready,
- public-ready,
- MDD consensus.

### 18.3 Required Safe Language

Allowed safe language includes:

- review-visible,
- not provided,
- source-limited,
- missing evidence,
- interpretation limiter,
- discussion prompt,
- MDD preparation,
- authority effect: none,
- not a diagnostic report,
- not patient-facing,
- not public-ready,
- does not replace MDD.

Language rule:

> Export language must describe review state, not clinical conclusion.

---

## 19. Non-Patient-Facing Validation Check

Required:

```yaml
patient_facing_use: not_allowed
patient_ready: false
public_ready: false
```

Failure conditions:

- patient-friendly explanation appears,
- patient next-step list appears,
- patient treatment explanation appears,
- patient risk/reassurance language appears,
- patient discharge-style formatting appears,
- patient portal-ready layout appears,
- “send to patient” action appears,
- export marked patient-ready,
- export marked public-ready.

Non-patient-facing rule:

> Export must remain clinician/MDD-preparation only.

---

## 20. Audit Reference Validation Check

Required:

- audit reference section present,
- safe export created event recorded,
- validation pass/fail recorded,
- repair/invalidation/supersession recorded where relevant,
- audit authority effect none,
- audit clinical validation false.

Failure conditions:

- export created without audit,
- validation failure without audit,
- repair without audit,
- invalidation without audit,
- supersession without audit,
- audit claims correctness,
- audit claims diagnosis,
- audit claims treatment authorization,
- audit claims MDD completion,
- audit claims public readiness.

Audit validation rule:

> Audit records export governance, not clinical correctness.

---

## 21. Safe Export Validation Object

Every export must include or reference:

```yaml
safe_export_validation_object:
  validation_id: string
  export_id: string
  session_id: string
  snapshot_id: string
  validation_state: export_governance_safe | export_blocked | repair_required | export_invalidated
  snapshot_eligible: true_or_false
  required_sections_present: true_or_false
  authority_envelope_present: true_or_false
  no_decision_statement_present: true_or_false
  blocked_output_notice_present: true_or_false
  binding_integrity_passed: true_or_false
  source_limitations_preserved: true_or_false
  missing_evidence_preserved: true_or_false
  confidence_limiters_preserved: true_or_false
  mimic_visibility_preserved_where_relevant: true_or_false
  overlap_preserved_where_relevant: true_or_false
  review_prompts_preserved_where_relevant: true_or_false
  formatting_safe: true_or_false
  language_safe: true_or_false
  patient_facing_format_blocked: true_or_false
  public_ready_label_blocked: true_or_false
  clinical_validation_language_blocked: true_or_false
  audit_references_preserved: true_or_false
  export_valid: true_or_false
  authority_effect: none
  clinical_correctness_validated: false
```

Validation object rule:

> Validation object must expose safety checks without implying clinical correctness.

---

## 22. Unsafe Export Failure Object

Unsafe export attempts must create:

```yaml
unsafe_export_failure:
  failure_id: string
  export_id: string
  session_id: string
  snapshot_id: string
  failure_state: unsafe_export_detected | export_blocked | repair_required
  failure_reason:
    - snapshot_ineligible
    - required_section_missing
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
    - review_prompt_lost
    - audit_reference_missing
    - unsafe_heading_detected
    - unsafe_badge_detected
    - unsafe_table_column_detected
    - unsafe_language_detected
    - action_formatting_detected
    - patient_facing_language_detected
    - public_ready_label_detected
    - clinical_validation_language_detected
  export_allowed: false
  repair_required: true
  audit_event_required: true
  authority_effect: none
  diagnosis_created: false
  treatment_created: false
  triage_created: false
  clinical_validation_created: false
```

Failure object rule:

> Unsafe export failure must explain why export failed without giving clinical advice.

---

## 23. Fail-Closed Behavior

When unsafe export is detected, the system must:

1. block export,
2. preserve prior safe state,
3. record failure reason,
4. show failure reason to clinician,
5. require repair,
6. record audit event,
7. preserve authority envelope,
8. preserve no-decision statement,
9. prevent patient-facing/public-ready output,
10. prevent warning-only bypass.

Blocked fail-open behavior:

- export with warning,
- export with hidden failure,
- export after clinician override,
- export as draft while unsafe content remains,
- export with missing authority envelope,
- export with patient-facing wording,
- export with diagnostic report heading,
- export with action recommendations.

Fail-closed rule:

> Unsafe export must stop the package from leaving the governed state.

---

## 24. Export Repair Rules

Allowed repair actions:

- restore missing authority envelope,
- restore no-decision statement,
- restore blocked output notice,
- remove unsafe heading,
- replace unsafe title with safe title,
- remove unsafe badge,
- replace unsafe badge with evidence-state badge,
- remove unsafe table column,
- replace unsafe action language,
- restore source limitations,
- restore missing evidence,
- restore confidence limiters,
- restore mimic visibility,
- restore overlap,
- restore review prompts,
- restore audit references,
- remove patient-facing language,
- remove public-ready language,
- create repair audit event,
- revalidate repaired export.

Blocked repair actions:

- silently deleting failure record,
- silently mutating export without audit,
- keeping unsafe heading with disclaimer only,
- allowing clinician override of authority envelope,
- allowing public-ready toggle,
- converting repair into clinical validation,
- creating diagnosis during repair,
- hiding missing evidence during repair,
- suppressing mimic visibility during repair.

Repair rule:

> Export repair restores governance safety, not clinical correctness.

---

## 25. Export Invalidation Rules

An export must be invalidated if:

- source snapshot is superseded,
- export contains stale binding,
- export contains orphan binding,
- authority envelope drift is detected,
- no-decision statement is missing,
- blocked output notice is missing,
- unsafe diagnosis/action/patient-facing language is discovered,
- source limitation loss is discovered,
- missing evidence loss is discovered,
- confidence limiter loss is discovered,
- mimic/overlap/review prompt loss is discovered,
- audit reference integrity failure is discovered.

Invalidated export behavior:

```yaml
invalidated_export_behavior:
  export_status: invalidated
  current_use: blocked
  sharing_allowed: false
  repair_or_regeneration_required: true
  audit_event_required: true
  authority_effect: none
```

Invalidation rule:

> Unsafe or stale exports must be invalidated rather than trusted historically.

---

## 26. Export Supersession Rules

An export may be superseded when:

- a newer eligible snapshot is exported,
- repaired export passes validation,
- prior export is outdated,
- case session revision changes export-relevant state,
- source status changes,
- missing evidence changes,
- confidence limiter changes,
- mimic/overlap/review prompt state changes.

Superseded export behavior:

```yaml
superseded_export_behavior:
  export_status: superseded
  current_use: blocked
  retained_for_audit: true
  superseded_by_export_id: string
  audit_event_required: true
  authority_effect: none
```

Supersession must not imply:

- prior export was clinically wrong,
- new export is clinically correct,
- diagnosis established,
- treatment authorized,
- MDD completed,
- clinical validation achieved.

Supersession rule:

> Export supersession changes current governance state, not clinical truth.

---

## 27. Export Validation Audit Rules

Every validation pass, validation failure, repair, invalidation, or supersession must create audit event.

Required audit events:

- validation_requested,
- validation_passed,
- validation_failed,
- unsafe_export_blocked,
- repair_requested,
- repair_completed,
- revalidation_requested,
- export_marked_governance_safe,
- export_invalidated,
- export_superseded.

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
clinical_correctness_validated: false
```

Audit rule:

> Export validation audit records safety process, not clinical accuracy.

---

## 28. Export Validation Acceptance Tests

### TEST_001 — Safe Export Passes

Input:

```yaml
export:
  authority_envelope_present: true
  no_decision_statement_present: true
  blocked_output_notice_present: true
  stale_bindings_present: false
  orphan_bindings_present: false
  unsafe_headings_present: false
  unsafe_language_present: false
  patient_facing_language_present: false
```

Expected:

- export_governance_safe,
- audit recorded,
- diagnostic_authority none,
- treatment_authority none,
- public_ready false,
- patient_facing_use not_allowed.

---

### TEST_002 — Missing Authority Envelope

Input:

```yaml
export:
  authority_envelope_present: false
```

Expected:

- unsafe_export_detected,
- export_blocked,
- repair_required,
- audit recorded,
- no export allowed.

---

### TEST_003 — Unsafe Heading

Input:

```yaml
export_section_title: Impression
```

Expected:

- formatting_failed,
- unsafe_export_detected,
- export_blocked,
- failure_reason: unsafe_heading_detected,
- repair required.

---

### TEST_004 — Probability Column

Input:

```yaml
table_column: Probability
```

Expected:

- formatting_failed,
- export_blocked,
- failure_reason: unsafe_table_column_detected,
- confidence limiter not converted to probability.

---

### TEST_005 — Missing Evidence Reframed as Exclusion

Input:

```yaml
export_text: HP ruled out due to no exposure history
```

Expected:

- language_failed,
- export_blocked,
- failure_reason: unsafe_language_detected,
- missing_as_exclusion blocked.

---

### TEST_006 — Patient-Facing Summary

Input:

```yaml
export_type: patient_summary
```

Expected:

- non_patient_facing_failed,
- export_blocked,
- patient_facing_use not_allowed,
- public_ready false.

---

## 29. Export Validation Red-Team Scenarios

The following failures must be blocked.

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
| Export contains stale binding | stale export blocked |
| Export contains orphan binding | orphan export blocked |
| Export repair silently deletes audit | repair blocked |
| Export supersession claims new snapshot is correct | supersession-as-validation blocked |

---

## 30. v0.13.3 Acceptance Criteria

v0.13.3 is accepted only if:

- export validation state registry is defined,
- validation event registry is defined,
- success path is defined,
- failure path is defined,
- snapshot eligibility check is defined,
- required section presence check is defined,
- authority envelope validation check is defined,
- no-decision statement validation check is defined,
- blocked output notice validation check is defined,
- binding integrity validation check is defined,
- source status validation check is defined,
- missing evidence validation check is defined,
- confidence limiter validation check is defined,
- mimic/overlap/review prompt validation check is defined,
- formatting validation check is defined,
- language validation check is defined,
- non-patient-facing validation check is defined,
- audit reference validation check is defined,
- safe export validation object is defined,
- unsafe export failure object is defined,
- fail-closed behavior is defined,
- export repair rules are defined,
- export invalidation rules are defined,
- export supersession rules are defined,
- export validation audit rules are defined,
- acceptance tests are defined,
- red-team scenarios are blocked,
- unsafe export cannot leave governed state,
- warning-only bypass is blocked,
- clinician override cannot bypass authority envelope,
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

## 31. Next Step

The next recommended step is:

- v0.13.4 — Safe Export Validation Checklist / Export Safety Gate

v0.13.4 should verify:

- v0.13.0 entry gate exists,
- v0.13.1 export object schema exists,
- v0.13.2 safe formatting rules exist,
- v0.13.3 validation state machine exists,
- safe export required sections exist,
- unsafe headings are blocked,
- unsafe badges are blocked,
- unsafe table columns are blocked,
- unsafe language is blocked,
- missing authority envelope blocks export,
- missing no-decision statement blocks export,
- stale/orphan bindings block export,
- patient-facing formatting blocks export,
- public-ready labels block export,
- clinical validation language blocks export,
- export repair requires audit and revalidation,
- export invalidation/supersession remain non-authoritative.

v0.13.4 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 32. Governance Statement

This document defines safe export validation state machine and unsafe export failure rules.

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

Safe export validation remains a governance safety check, not clinical validation.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.13 rule remains:

> “A safe session export may prepare discussion, but it must not become diagnosis, treatment, order, procedure decision, follow-up schedule, triage report, patient-facing output, public-ready output, or clinical validation.”

For v0.13.3:

> “An export is safe only after snapshot eligibility, section presence, formatting, language, authority envelope, no-decision, binding integrity, and audit checks pass; otherwise it must fail closed.”