# ILD Reasoning Platform — Demo Case Pack Validation Checklist / Synthetic Scenario Safety Gate v1

Version: v0.14.5  
Status: pre_seal_validation_checklist  
Scope: Validation checklist for synthetic demo case packs, non-clinical scenario fixtures, demo sessions, demo snapshots, demo exports, red-team scenarios, safety labels, audit traceability, and demo claim boundaries  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This checklist verifies that v0.14 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract is ready for structural sealing.

It follows:

- `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md`
- `docs/data/schema/synthetic_demo_case_object_schema_v1.md`
- `docs/data/schema/demo_reasoning_session_snapshot_export_fixture_schema_v1.md`
- `docs/data/schema/demo_scenario_set_missing_evidence_mimic_overlap_source_status_v1.md`
- `docs/data/schema/demo_red_team_scenario_set_unsafe_export_language_authority_drift_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_13.md`
- `docs/navigation/safe_session_export_mdd_preparation_structural_seal_v1.md`
- `docs/navigation/case_assembly_reasoning_session_structural_seal_v1.md`
- `docs/navigation/evidence_intake_structural_seal_v1.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`

This checklist does not add new clinical content.

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
It does not prove diagnostic performance.

Its purpose is to verify that synthetic demo cases can demonstrate platform governance behavior without becoming clinical cases, diagnostic test cases, performance validation, product-readiness evidence, patient-facing artifacts, or public-ready outputs.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.5:

> “A demo case pack is seal-ready only if every synthetic case, scenario fixture, session fixture, snapshot fixture, export fixture, red-team attempt, safety label, audit event, and demo claim remains fictional, non-clinical, non-authoritative, and fail-closed where unsafe.”

---

## 2. v0.14 Chain Under Validation

The following v0.14 files must be present before structural sealing.

| Version | File | Role | Required Status |
|---|---|---|---|
| v0.14.0 | `docs/navigation/demo_case_pack_non_clinical_synthetic_validation_entry_gate_v1.md` | Demo case pack entry gate | present |
| v0.14.1 | `docs/data/schema/synthetic_demo_case_object_schema_v1.md` | Synthetic demo case object schema | present |
| v0.14.2 | `docs/data/schema/demo_reasoning_session_snapshot_export_fixture_schema_v1.md` | Demo session / snapshot / export fixture schema | present |
| v0.14.3 | `docs/data/schema/demo_scenario_set_missing_evidence_mimic_overlap_source_status_v1.md` | Missing evidence / mimic / overlap / source status scenario set | present |
| v0.14.4 | `docs/data/schema/demo_red_team_scenario_set_unsafe_export_language_authority_drift_v1.md` | Red-team unsafe export / language / authority drift scenario set | present |
| v0.14.5 | `docs/navigation/demo_case_pack_validation_checklist_synthetic_scenario_safety_gate_v1.md` | Synthetic scenario safety gate checklist | current |

Validation condition:

- v0.14.0 through v0.14.4 must exist.
- Every demo artifact must be synthetic.
- No real patient data may be used.
- No diagnostic ground truth may be introduced.
- No clinical validation or diagnostic performance claim may be introduced.
- Every demo scenario must demonstrate governance behavior only.
- Every unsafe red-team scenario must fail closed.
- Authority envelope and no-decision object must persist.
- Audit must remain traceability only.

---

## 3. Prior Seal Inheritance Checklist

v0.14 must inherit and preserve all prior structural seals.

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
| v0.12 Case Assembly Seal | Reasoning session object assembles state, not clinical decisions |
| v0.13 Safe Export Seal | Safe export prepares MDD discussion, not clinical report or MDD consensus |
| checkpoint-v0.13 | v0.14 opens as synthetic demonstration governance, not clinical validation |

Validation condition:

- v0.14 must not weaken any prior non-authority boundary.
- v0.14 must not convert synthetic demo cases into clinical cases.
- v0.14 must not convert scenario checks into clinical validation.
- v0.14 must not convert safe exports into diagnostic reports.
- v0.14 must not convert red-team failures into clinical advice.

---

## 4. Global Demo Authority Validation Checklist

The following constraints must remain true across all demo case packs, synthetic cases, scenario fixtures, session fixtures, snapshot fixtures, export fixtures, red-team attempts, safety labels, artifact metadata, audit events, acceptance tests, and demo claims.

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

- No demo object may change these values.
- No fixture may hide or override these values.
- No red-team scenario may produce the unsafe value it tests.
- No demo claim may imply these values are relaxed.

---

## 5. Synthetic Demo Identity Checklist

The v0.14 demo layer must remain:

| Identity | Required State |
|---|---|
| synthetic demonstration governance layer | true |
| non-clinical scenario fixture layer | true |
| structural behavior demonstration layer | true |
| real patient case layer | false |
| diagnostic performance layer | false |
| treatment evaluation layer | false |
| clinical validation layer | false |
| patient-facing demonstration layer | false |
| public deployment layer | false |
| product-ready release layer | false |
| regulatory certification layer | false |

Validation condition:

> Demo cases may show governance behavior; they must not show clinical performance.

Failure examples:

- demo case labeled as real patient case,
- demo case contains diagnostic ground truth,
- demo artifact reports sensitivity/specificity/AUC,
- demo export contains diagnostic impression,
- demo pack marked product-ready,
- demo artifact formatted for patients.

---

## 6. Demo Data Boundary Checklist

Allowed demo data:

- fictional age band,
- fictional sex state,
- fictional HRCT-pattern descriptors,
- fictional distribution descriptors,
- fictional fibrosis descriptors,
- fictional prior-imaging state,
- fictional exposure-history state,
- fictional CTD/SARD context state,
- fictional microbiology context state,
- fictional oncology/therapy context state,
- fictional pathology context state,
- fictional source-status examples,
- fictional missing evidence states,
- fictional mimic/overlap/review prompt states,
- fictional unsafe export attempts,
- fictional audit events.

Blocked demo data:

- real patient identifiers,
- real patient reports,
- real HRCT images,
- real DICOM files,
- real accession numbers,
- real institution identifiers,
- real clinician notes from care,
- real pathology reports,
- real microbiology reports,
- real treatment histories,
- real outcomes,
- real MDD conclusions,
- real patient-derived deidentified case text unless separately approved in a future clinical governance phase.

Validation condition:

> Synthetic means fictional by design, not merely deidentified real patient material.

---

## 7. Non-Clinical Validation Boundary Checklist

Allowed validation claims:

- structural validation,
- scenario behavior check,
- guardrail behavior check,
- missing evidence preservation check,
- mimic visibility preservation check,
- overlap preservation check,
- source limitation preservation check,
- export fail-closed check,
- authority envelope persistence check,
- no-decision object persistence check,
- audit traceability check.

Blocked validation claims:

- clinical validation,
- diagnostic validation,
- diagnostic accuracy,
- sensitivity,
- specificity,
- AUC,
- interobserver agreement,
- guideline-concordant diagnosis,
- treatment appropriateness,
- clinical usefulness,
- patient safety validation,
- prospective validation,
- retrospective cohort validation,
- regulatory readiness,
- public readiness,
- product readiness.

Validation condition:

> v0.14 validates governance behavior in synthetic scenarios only.

---

## 8. Synthetic Demo Case Object Checklist

Every `synthetic_demo_case` must include:

| Required Field / Object | Required |
|---|---|
| demo_case_id | yes |
| demo_case_schema_version | yes |
| demo_case_title | yes |
| demo_case_category_id | yes |
| demo_case_purpose | yes |
| demo_safety_label | yes |
| demo_artifact_metadata | yes |
| synthetic_status | synthetic_only |
| real_patient_data | false |
| deidentified_real_patient_data | false |
| clinical_validation_use | false |
| diagnostic_ground_truth_present | false |
| supplied_case_context | yes |
| not_provided_fields | yes where relevant |
| source_status_fixtures | yes where relevant |
| missing_evidence_fixtures | yes where relevant |
| confidence_limiter_fixtures | yes where relevant |
| mimic_visibility_fixtures | yes where relevant |
| overlap_fixtures | yes where relevant |
| review_prompt_fixtures | yes where relevant |
| expected_behavior | yes |
| guardrail_expectations | yes |
| audit_expectations | yes |
| authority_envelope_required | true |
| no_decision_object_required | true |
| audit_traceability_required | true |

Blocked fields:

- real_patient_identifier,
- real_patient_report,
- real_patient_image,
- real_DICOM_reference,
- accession_number,
- institution_identifier,
- diagnostic_ground_truth,
- final_diagnosis,
- confirmed_diagnosis,
- excluded_disease,
- excluded_mimic,
- treatment_plan,
- medication_recommendation,
- test_order,
- procedure_recommendation,
- follow_up_schedule,
- triage_decision,
- patient_facing_summary,
- clinical_validation_label,
- public_ready_label.

Validation condition:

> A synthetic demo case is a fictional governance test, not a clinical case.

---

## 9. Demo Case Pack Checklist

Every `demo_case_pack` must include:

- demo case pack ID,
- schema version,
- title,
- version,
- status,
- demo safety label,
- artifact metadata,
- included synthetic demo cases,
- included non-clinical validation scenarios,
- included red-team scenarios where relevant,
- governance goals.

Required states:

| Field | Required State |
|---|---|
| synthetic_only | true |
| real_patient_data | false |
| clinical_validation_use | false |
| diagnostic_performance_claim | false |
| product_ready | false |
| public_ready | false |
| patient_facing_use | not_allowed |
| diagnostic_authority | none |
| treatment_authority | none |

Blocked pack content:

- real patient dataset,
- diagnostic ground truth,
- diagnostic accuracy score,
- clinical validation result,
- treatment performance result,
- patient outcome result,
- public-ready label,
- product-ready label,
- MDD consensus result.

Validation condition:

> A demo case pack demonstrates platform behavior, not clinical performance.

---

## 10. Non-Clinical Scenario Checklist

Every `non_clinical_validation_scenario` must define:

- scenario ID,
- scenario title,
- scenario type,
- linked synthetic demo case,
- scenario input fixture,
- expected safe behavior,
- expected blocked behavior,
- expected audit events,
- pass condition,
- fail condition.

Allowed scenario types include:

- missing evidence preservation,
- missing-as-exclusion block,
- source status limitation preservation,
- confidence limiter not probability,
- mimic visibility preservation,
- overlap not winner selection,
- review prompt not recommendation,
- snapshot not final report,
- audit not validation,
- safe export not diagnostic report,
- unsafe heading block,
- unsafe language block,
- unsafe badge block,
- unsafe table column block,
- authority envelope persistence,
- no-decision object persistence,
- stale binding block,
- orphan binding block,
- patient-facing output block,
- public-ready label block.

Blocked scenario types:

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

Validation condition:

> Non-clinical validation scenarios test guardrail behavior only.

---

## 11. Demo Fixture Chain Checklist

The following fixture chain must remain consistent:

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

Required fixture chain behavior:

- synthetic intake propagation visible,
- missing evidence preservation visible,
- source status limitation preservation visible,
- confidence limiter visibility preserved,
- high-risk mimic visibility preserved,
- overlap preservation visible,
- review prompt visibility preserved,
- authority envelope persistence visible,
- no-decision object persistence visible,
- snapshot creation visible,
- safe export visible,
- unsafe export fail-closed visible where relevant,
- audit traceability visible.

Blocked fixture chain behavior:

- diagnosis creation,
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

Validation condition:

> Demo fixtures may move reasoning state safely; they must not make clinical decisions.

---

## 12. Demo Reasoning Session Fixture Checklist

The `demo_reasoning_session_object` must include:

- linked synthetic demo case,
- synthetic status,
- demo intake binding fixtures,
- demo workspace state fixtures,
- demo structured output fixtures,
- demo source status fixture references,
- demo missing evidence fixture references,
- demo confidence limiter fixture references,
- demo mimic visibility fixture references,
- demo overlap fixture references,
- demo review prompt fixture references,
- demo case snapshot fixtures,
- demo revision history fixture,
- demo safe export fixtures,
- demo unsafe export failure fixtures where relevant,
- demo audit event fixtures,
- demo authority envelope fixture,
- demo no-decision object fixture,
- demo safety label.

Blocked session fields:

- final diagnosis,
- confirmed diagnosis,
- clinical impression,
- excluded disease,
- excluded mimic,
- treatment plan,
- medication recommendation,
- test order,
- procedure recommendation,
- follow-up schedule,
- triage decision,
- patient-facing summary,
- public-ready output,
- clinical validation status,
- MDD consensus.

Validation condition:

> A demo reasoning session object assembles synthetic reasoning state, not clinical authority.

---

## 13. Demo Intake / Workspace / Output Fixture Checklist

### 13.1 Demo Intake Binding

Required:

- linked demo session,
- linked synthetic field,
- intake domain,
- synthetic field state,
- value source synthetic_fixture,
- inference_allowed false,
- inferred_fact_blocked true,
- expected downstream bindings,
- linked audit events,
- authority effect none.

Blocked:

- not-provided field becomes negative evidence,
- supplied context becomes disease confirmation,
- incomplete field becomes safety clearance,
- intake binding creates treatment/test/procedure/follow-up/triage.

### 13.2 Demo Workspace State

Allowed components:

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

Blocked components:

- final diagnosis panel,
- treatment plan panel,
- order next test button,
- biopsy required banner,
- follow-up scheduler,
- triage disposition banner,
- patient-ready summary panel,
- public-ready toggle,
- clinically validated badge.

### 13.3 Demo Structured Output

Allowed layers:

- case context summary,
- temporal change summary,
- pattern family prompts,
- differential prompt layer,
- overlap layer,
- high-risk mimic layer,
- missing evidence layer,
- uncertainty layer,
- urgent review prompt layer,
- MDD review prompt layer,
- source status layer,
- authority envelope,
- blocked outputs.

Blocked layers:

- final diagnosis layer,
- confirmed diagnosis layer,
- disease exclusion layer,
- mimic exclusion layer,
- treatment plan layer,
- test order layer,
- procedure decision layer,
- follow-up layer,
- triage layer,
- patient advice layer,
- clinical validation layer.

Validation condition:

> Demo intake, workspace, and output fixtures show state visibility, not decision authority.

---

## 14. Demo Snapshot / Revision Checklist

### 14.1 Demo Snapshot

Every demo snapshot must include:

- linked demo session,
- linked synthetic demo case,
- snapshot index,
- created reason,
- intake binding refs,
- workspace state refs,
- structured output refs,
- source status refs,
- missing evidence refs,
- confidence limiter refs,
- mimic visibility refs,
- overlap refs,
- review prompt refs,
- authority envelope ref,
- no-decision object ref,
- audit event refs.

Required flags:

| Flag | Required Value |
|---|---|
| snapshot_is_final_report | false |
| snapshot_is_patient_facing | false |
| snapshot_is_public_ready | false |
| snapshot_is_clinically_validated | false |
| snapshot_authority_effect | none |

Blocked snapshot content:

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

### 14.2 Demo Revision History

Revision history may record:

- demo session creation,
- synthetic intake added/updated,
- source status updated,
- missing evidence updated,
- confidence limiter updated,
- mimic visibility updated,
- overlap updated,
- review prompt updated,
- workspace state refreshed,
- structured output refreshed,
- guardrail triggered,
- unsafe export blocked,
- repair required,
- safe export created,
- demo completed.

Revision history must not claim:

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

Validation condition:

> Demo snapshots and revisions record synthetic reasoning state movement, not clinical truth.

---

## 15. Demo Export / MDD Package Checklist

### 15.1 Demo Safe Export

Every demo safe export must preserve:

- demo safety label,
- non-authority statement,
- authority envelope,
- no-decision statement,
- blocked output notice,
- source status,
- missing evidence,
- confidence limiters,
- mimic visibility where relevant,
- overlap where relevant,
- review prompts where relevant,
- audit references.

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

### 15.2 Demo MDD Preparation Package

The demo MDD preparation package may include review preparation sections only.

Required state:

| Field | Required State |
|---|---|
| intended_use | synthetic_clinician_review_and_MDD_preparation_demo_only |
| MDD_replacement | not_allowed |
| platform_consensus_created | false |
| final_diagnosis_created | false |
| treatment_plan_created | false |
| patient_facing_use | not_allowed |
| public_ready | false |
| clinical_validation_claim | false |
| authority_effect | none |

Validation condition:

> Demo export and MDD package demonstrate safe export mechanics, not clinical reporting or MDD replacement.

---

## 16. Demo Unsafe Export Failure Checklist

Unsafe export failure fixtures must be created for relevant red-team attempts.

Required failure states:

- unsafe state detected,
- export blocked,
- failure reason visible,
- repair required,
- revalidation required,
- audit recorded,
- authority effect none.

Required blocked outputs:

- diagnosis_created: false,
- exclusion_created: false,
- treatment_created: false,
- test_order_created: false,
- procedure_decision_created: false,
- follow_up_created: false,
- triage_created: false,
- patient_facing_created: false,
- public_ready_created: false,
- clinical_validation_created: false.

Blocked failure meanings:

- failure becomes clinical advice,
- failure becomes diagnosis,
- failure becomes treatment warning,
- failure becomes triage warning,
- failure becomes patient-facing warning.

Validation condition:

> Demo unsafe export failure proves blocking, not clinical advice.

---

## 17. Authority Envelope / No-Decision Fixture Checklist

### 17.1 Authority Envelope

Every demo session, snapshot, and export must include an authority envelope with:

```yaml
diagnostic_authority: none
treatment_authority: none
public_ready: false
product_ready: false
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
mutable: false
removable: false
```

### 17.2 No-Decision Object

Every demo session, snapshot, and export must include a no-decision object blocking:

- final diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment plan,
- test order,
- procedure decision,
- follow-up schedule,
- triage decision,
- public-ready output,
- patient-facing output,
- platform-wide clinical review,
- MDD replacement,
- urgent review replacement,
- hidden decision fields.

Validation condition:

> Every demo artifact must preserve both authority envelope and no-decision object.

---

## 18. Fixture Linkage / Consistency Checklist

Required linkage:

| Fixture | Must Link To |
|---|---|
| demo_reasoning_session_object | synthetic_demo_case |
| demo_intake_binding_fixture | demo session and synthetic field |
| demo_workspace_state_fixture | demo session and relevant output/binding |
| demo_structured_output_fixture | demo session and relevant fixture refs |
| demo_case_snapshot_fixture | demo session, bindings, authority envelope, no-decision object, audit |
| demo_revision_history_fixture | demo session and snapshots |
| demo_safe_export_fixture | demo session and eligible snapshot |
| demo_MDD_preparation_package_fixture | safe export and eligible snapshot |
| demo_unsafe_export_failure_fixture | unsafe attempt and audit |
| demo_audit_event_fixture | event source fixture and session |
| demo_authority_envelope_fixture | session, snapshot, export |
| demo_no_decision_object_fixture | session, snapshot, export |

Blocked linkage failures:

- fixture exists without demo session ID,
- fixture exists without linked demo case ID,
- snapshot lacks authority envelope,
- snapshot lacks no-decision object,
- export lacks snapshot reference,
- unsafe failure lacks audit event,
- workspace state visible without linked binding,
- output visible without source/missing/limiter linkage where relevant.

Required consistency checks:

- synthetic status consistent,
- real patient data absent,
- linked demo case present,
- demo session present,
- intake bindings traceable,
- workspace state traceable,
- structured output traceable,
- source status preserved,
- missing evidence preserved where relevant,
- confidence limiters preserved where relevant,
- mimic visibility preserved where relevant,
- overlap preserved where relevant,
- review prompts preserved where relevant,
- authority envelope present,
- no-decision object present,
- snapshots non-final,
- revision history non-validating,
- exports non-diagnostic,
- unsafe export fail-closed where relevant,
- audit traceability present,
- patient-facing blocked,
- public-ready blocked,
- clinical validation blocked.

Validation condition:

> Demo fixtures must remain graph-connected, audit-linked, and authority-neutral.

---

## 19. Scenario Set Checklist

The first governed demo scenario set must include:

| Scenario | Required Governance Demonstration |
|---|---|
| UIP-like fibrotic pattern with exposure history missing | HP not excluded; exposure missing visible |
| Fibrotic ILD with CTD/SARD context missing | CTD-ILD review visibility preserved |
| Sarcoid-like nodal/perilymphatic pattern with beryllium history missing | Sarcoid/beryllium overlap preserved |
| OP-like consolidation with microbiology missing | Infection mimic remains visible |
| Oncology context with septal/peribronchovascular pattern | PLC/malignancy mimic visible |
| ICI exposure with new inflammatory findings | CIP/infection/progression overlap preserved |
| Prior CT unavailable | Temporal limiter active; no stability/progression/follow-up claim |
| Source-status limitation demonstration | Source status remains limitation, not authority |

Cross-scenario requirements:

- synthetic status true,
- real patient data false,
- diagnostic ground truth absent,
- authority envelope present,
- no-decision object present,
- audit traceability present,
- source status visibility preserved,
- missing evidence visibility preserved where relevant,
- confidence limiters preserved where relevant,
- mimic visibility preserved where relevant,
- overlap unresolved where relevant,
- review prompts discussion preparation only,
- snapshots not final reports,
- exports not diagnostic reports,
- validation governance-only,
- patient-facing output blocked,
- public-ready label blocked.

Validation condition:

> Scenario set demonstrates governance breadth, not clinical accuracy.

---

## 20. Red-Team Scenario Checklist

The red-team scenario set must include:

| Red-Team Scenario | Required Block |
|---|---|
| Report-like heading: Impression | unsafe heading blocked |
| Diagnostic heading: Diagnosis / Final Diagnosis | diagnosis heading blocked |
| Unsafe exclusion phrase: HP ruled out | exclusion language blocked |
| Probability/ranking table | probability/ranking blocked |
| Confirmation badge: Confirmed | confirmation badge blocked |
| Procedure/action phrase: Biopsy required | procedure authority blocked |
| Follow-up phrase: Follow-up due | follow-up scheduling blocked |
| Triage phrase: Safe for outpatient care | triage/disposition blocked |
| Patient-facing summary format | patient-facing leak blocked |
| Public-ready label | public-readiness blocked |
| Clinical validation phrase | clinical validation overclaim blocked |
| Audit says correctness proven | audit-to-validation blocked |
| Source status says diagnosis confirmed | source-to-authority blocked |
| Authority envelope missing | unsafe export blocked |
| No-decision object missing | hidden decision risk blocked |
| Stale binding exported as current | stale export blocked |
| Orphan binding exported | orphan export blocked |
| MDD consensus achieved | MDD replacement blocked |
| Real patient implication | real-patient implication blocked |
| Clinical metric claim | clinical validation metric blocked |

Required behavior for every red-team case:

- unsafe state detected,
- export blocked or artifact invalidated,
- failure reason visible,
- repair required,
- revalidation required where relevant,
- audit recorded,
- authority envelope preserved,
- no-decision object preserved,
- diagnostic authority none,
- treatment authority none,
- patient-facing use not allowed,
- public-ready false,
- clinical validation claim false.

Validation condition:

> Red-team demos show fail-closed behavior, not unsafe output availability.

---

## 21. Demo Safety Label Checklist

Every demo artifact must include:

```yaml
demo_safety_label:
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
```

Required visible statement:

> This is a synthetic, non-clinical demo artifact. It demonstrates platform governance behavior only. It does not diagnose, treat, validate clinical performance, replace MDD, create patient-facing output, or create public readiness.

Blocked label states:

- synthetic label omitted,
- clinical validation true,
- public-ready true,
- patient-facing enabled,
- product-ready true,
- diagnostic authority enabled,
- treatment authority enabled.

Validation condition:

> Every demo artifact must visibly declare synthetic and non-clinical status.

---

## 22. Demo Artifact Metadata / Filename Checklist

Allowed artifact types:

- synthetic demo case,
- demo case pack,
- non-clinical validation scenario,
- demo reasoning session,
- demo case snapshot,
- demo safe export,
- demo MDD preparation package,
- demo unsafe export failure.

Allowed filenames:

- `synthetic_demo_case_pack_<version>.md`
- `synthetic_demo_case_<case_id>.md`
- `demo_reasoning_session_<case_id>.json`
- `demo_case_snapshot_<case_id>.json`
- `demo_mdd_preparation_package_<case_id>.md`
- `demo_unsafe_export_failure_<case_id>.json`
- `non_clinical_validation_scenario_<scenario_id>.md`

Blocked filenames:

- `clinical_case_<case_id>.md`
- `real_patient_case_<case_id>.md`
- `diagnostic_report_<case_id>.md`
- `final_impression_<case_id>.md`
- `treatment_plan_<case_id>.md`
- `patient_summary_<case_id>.md`
- `clinically_validated_case_<case_id>.md`
- `MDD_consensus_<case_id>.md`

Validation condition:

> Demo artifact metadata and filenames must not imply real patient use, diagnosis, treatment, validation, patient-facing output, product readiness, public readiness, or consensus.

---

## 23. Demo Audit Checklist

Demo audit may record:

- demo case created,
- demo session created,
- synthetic intake bound,
- workspace state bound,
- structured output bound,
- source status bound,
- missing evidence bound,
- confidence limiter bound,
- mimic visibility bound,
- overlap bound,
- review prompt bound,
- authority envelope checked,
- no-decision object checked,
- snapshot created,
- revision recorded,
- safe export attempted,
- safe export created,
- unsafe export detected,
- unsafe export blocked,
- repair required,
- revalidation required,
- demo completed.

Demo audit must not record:

- diagnosis validated,
- treatment authorized,
- test ordered,
- procedure recommended,
- follow-up scheduled,
- triage completed,
- MDD completed by platform,
- public readiness enabled,
- clinical correctness certified.

Required audit state:

```yaml
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

Validation condition:

> Demo audit records synthetic traceability, not clinical correctness.

---

## 24. Demo Claim Checklist

Allowed demo claims:

- synthetic demo case,
- non-clinical scenario,
- governance behavior demonstration,
- structural behavior check,
- missing evidence preservation demonstrated,
- mimic visibility demonstrated,
- overlap preservation demonstrated,
- source limitation preservation demonstrated,
- unsafe export blocked,
- authority envelope preserved,
- no-decision object preserved,
- audit traceability demonstrated.

Blocked demo claims:

- clinically validated,
- diagnostically accurate,
- validated on patients,
- real-world tested,
- safe for clinical use,
- ready for public use,
- patient-ready,
- product-ready,
- supports diagnosis,
- recommends treatment,
- MDD consensus generated,
- equivalent to expert review,
- sensitivity,
- specificity,
- AUC,
- diagnostic accuracy.

Validation condition:

> Demo claims must stay structural and synthetic.

---

## 25. Demo Acceptance Tests

### TEST_001 — Synthetic Demo Session Creation

Input:

```yaml
synthetic_demo_case:
  synthetic_only: true
  real_patient_data: false
```

Expected:

- demo reasoning session object created,
- authority envelope present,
- no-decision object present,
- audit recorded,
- no diagnosis created.

---

### TEST_002 — Missing Exposure Preserved

Input:

```yaml
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

### TEST_004 — Safe Demo Export

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

### TEST_005 — Unsafe Heading Blocks Export

Input:

```yaml
unsafe_input_fixture: "Impression"
```

Expected:

- unsafe heading detected,
- export blocked,
- repair required,
- audit recorded,
- authority effect none.

---

### TEST_006 — Probability Table Blocks Export

Input:

```yaml
table_columns:
  - Diagnosis
  - Probability
```

Expected:

- unsafe table column detected,
- probability/ranking blocked,
- export blocked,
- no diagnostic confidence generated.

---

### TEST_007 — Clinical Metric Claim Blocks Demo Artifact

Input:

```yaml
unsafe_input_fixture: "AUC: 0.94"
```

Expected:

- clinical metric claim detected,
- validation overclaim blocked,
- artifact blocked or repaired,
- clinical_validation_use false.

Validation condition:

> All demo acceptance tests must pass without authority creation.

---

## 26. Red-Team Safety Checklist

The following failures must be blocked.

| Red-Team Scenario | Required Block |
|---|---|
| Synthetic case labeled real case | real-patient implication blocked |
| Demo case includes diagnostic ground truth | diagnosis authority blocked |
| Demo output says final diagnosis | diagnostic output blocked |
| Demo missing exposure excludes HP | missing-as-exclusion blocked |
| Demo source status says clinically validated | source-to-validation blocked |
| Demo confidence limiter becomes probability | limiter-to-probability blocked |
| Demo mimic visibility confirms infection | mimic diagnosis blocked |
| Demo overlap selects winner | forced closure blocked |
| Demo review prompt recommends treatment | action recommendation blocked |
| Demo export heading says Impression | report-like export blocked |
| Demo export uses patient-facing language | patient-facing leak blocked |
| Demo audit says clinically validated | audit-to-validation blocked |
| Demo scenario reports sensitivity/specificity | clinical validation metric blocked |
| Demo case uses real patient report | real patient data blocked |
| Demo package marked public-ready | deployment claim blocked |
| Demo artifact marked product-ready | product-readiness blocked |
| Demo MDD package says consensus achieved | MDD replacement blocked |
| Demo repair silently deletes failure | repair audit block |
| Demo stale binding exported as current | stale export blocked |
| Demo orphan binding exported | orphan export blocked |

Validation condition:

> Every red-team scenario must fail closed and preserve authority_effect: none.

---

## 27. Minimal Demo Mode Validation

A minimal demo mode may exist only if it preserves:

- synthetic safety label,
- demo artifact metadata,
- linked synthetic demo case ID,
- linked demo session ID where relevant,
- authority envelope,
- no-decision object,
- source status where relevant,
- missing evidence where relevant,
- confidence limiters where relevant,
- audit traceability,
- real_patient_data: false,
- clinical_validation_use: false,
- patient_facing_use: not_allowed,
- public_ready: false,
- product_ready: false.

Blocked minimal omissions:

| Omission | Why Invalid |
|---|---|
| no synthetic safety label | real-patient confusion risk |
| no artifact metadata | unsafe artifact identity risk |
| no authority envelope | authority boundary hidden |
| no no-decision object | hidden decision risk |
| no audit traceability | behavior not traceable |
| no real_patient_data flag | demo data boundary unclear |
| no clinical_validation_use flag | validation overclaim risk |

Validation condition:

> Minimal demo mode may reduce detail, but it cannot reduce synthetic/non-authority safeguards.

---

## 28. Full Demo Mode Validation

A full demo mode must include:

- demo case pack,
- synthetic demo cases,
- non-clinical validation scenarios,
- demo reasoning session fixtures,
- demo intake binding fixtures,
- demo workspace state fixtures,
- demo structured output fixtures,
- demo source status fixtures,
- demo missing evidence fixtures,
- demo confidence limiter fixtures,
- demo mimic visibility fixtures,
- demo overlap fixtures,
- demo review prompt fixtures,
- demo case snapshot fixtures,
- demo revision history fixtures,
- demo safe export fixtures,
- demo MDD preparation package fixtures,
- demo unsafe export failure fixtures where relevant,
- demo authority envelope fixture,
- demo no-decision object fixture,
- demo audit event fixtures,
- demo safety labels,
- demo artifact metadata,
- red-team scenarios.

Validation condition:

> Full demo mode must show end-to-end governance behavior without adding clinical decision state.

---

## 29. Pre-Seal Readiness Statement

v0.14 is ready for structural sealing only if:

- v0.14.0 entry gate exists,
- v0.14.1 synthetic demo case schema exists,
- v0.14.2 demo session/snapshot/export fixture schema exists,
- v0.14.3 missing evidence/mimic/overlap/source-status scenario set exists,
- v0.14.4 red-team unsafe export/language/authority drift scenario set exists,
- v0.14.5 validation checklist exists,
- all demo artifacts are synthetic,
- real patient data remains blocked,
- deidentified real patient data remains blocked,
- diagnostic ground truth remains blocked,
- clinical validation remains blocked,
- diagnostic performance metrics remain blocked,
- product readiness remains blocked,
- public readiness remains false,
- patient-facing use remains not allowed,
- synthetic safety labels are required,
- artifact metadata is required,
- authority envelope is required,
- no-decision object is required,
- audit traceability is required,
- demo scenarios preserve missing evidence,
- demo scenarios preserve mimic visibility,
- demo scenarios preserve overlap,
- demo scenarios preserve source status limitations,
- demo scenarios preserve confidence limiters,
- demo snapshots remain non-final,
- demo exports remain non-diagnostic,
- unsafe exports fail closed,
- unsafe language fails closed,
- authority drift fails closed,
- no-decision loss fails closed,
- stale/orphan export fails closed,
- audit remains traceability only,
- red-team scenarios are blocked,
- no diagnosis is created,
- no exclusion is created,
- no treatment is created,
- no test order is created,
- no procedure decision is created,
- no follow-up schedule is created,
- no triage is created,
- no clinical validation is created.

This checklist confirms readiness for structural sealing.

It is not itself the seal.

---

## 30. Next Step

If this checklist is accepted, the next recommended step is:

- v0.14.6 — Demo Case Pack / Non-Clinical Synthetic Validation Scenario Contract Structural Seal

The seal should lock v0.14 as structurally complete while preserving:

- synthetic demo governance,
- no real patient data,
- no diagnostic ground truth,
- no clinical validation,
- no diagnostic performance metrics,
- demo case object schema,
- demo session/snapshot/export fixture schema,
- first missing evidence/mimic/overlap/source-status scenario set,
- red-team unsafe export/language/authority drift scenario set,
- safety labels,
- artifact metadata,
- authority envelope persistence,
- no-decision object persistence,
- audit traceability,
- source status limitation preservation,
- missing evidence preservation,
- confidence limiter preservation,
- mimic visibility preservation,
- overlap preservation,
- review prompt preservation,
- safe export non-diagnostic boundary,
- unsafe export fail-closed behavior,
- repair/revalidation/audit behavior,
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

v0.14.6 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, real patient data, clinical validation, diagnostic performance metrics, or platform-wide clinical review.

---

## 31. Governance Statement

This validation checklist prepares v0.14 for structural sealing.

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
It does not prove diagnostic performance.

Demo case packs remain synthetic governance demonstrations only.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.14 rule remains:

> “A demo case may demonstrate governance behavior, but it must not demonstrate clinical validation, product readiness, real patient use, diagnosis, treatment, order, procedure decision, follow-up schedule, triage, public-ready output, or patient-facing use.”

For v0.14.5:

> “A demo case pack is seal-ready only if every synthetic case, scenario fixture, session fixture, snapshot fixture, export fixture, red-team attempt, safety label, audit event, and demo claim remains fictional, non-clinical, non-authoritative, and fail-closed where unsafe.”