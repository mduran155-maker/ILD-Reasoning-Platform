# ILD Reasoning Platform — Evidence Intake Validation Checklist / Intake Safety Gate v1

Version: v0.11.4  
Status: pre_seal_validation_checklist  
Scope: Validation checklist for evidence intake and clinician-supplied case context contract  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This checklist verifies that v0.11 — Evidence Intake / Clinician-Supplied Case Context Contract is ready for structural sealing.

It follows:

- `docs/navigation/evidence_intake_case_context_entry_gate_v1.md`
- `docs/data/schema/evidence_intake_field_schema_provided_vs_inferred_boundary_v1.md`
- `docs/data/schema/structured_intake_domain_schema_case_context_fields_v1.md`
- `docs/data/schema/evidence_update_state_machine_intake_to_workspace_rules_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_10.md`
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

Its purpose is to verify that clinician-supplied case context can enter the platform safely without becoming diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, triage, public readiness, patient-facing output, or platform-wide clinical review.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.11 rule remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

For v0.11.4:

> “Evidence intake is seal-ready only if provided facts, missing facts, clinician-supplied evidence, blocked inference, workspace propagation, and audit remain authority-neutral.”

---

## 2. v0.11 Chain Under Validation

The following v0.11 files must be present before structural sealing.

| Version | File | Role | Required Status |
|---|---|---|---|
| v0.11.0 | `docs/navigation/evidence_intake_case_context_entry_gate_v1.md` | Evidence intake entry gate | present |
| v0.11.1 | `docs/data/schema/evidence_intake_field_schema_provided_vs_inferred_boundary_v1.md` | Field schema / provided-vs-inferred boundary | present |
| v0.11.2 | `docs/data/schema/structured_intake_domain_schema_case_context_fields_v1.md` | Structured intake domain schema | present |
| v0.11.3 | `docs/data/schema/evidence_update_state_machine_intake_to_workspace_rules_v1.md` | Evidence update state machine / propagation rules | present |
| v0.11.4 | `docs/navigation/evidence_intake_validation_checklist_v1.md` | Intake safety validation checklist | current |

Validation condition:

- v0.11.0 through v0.11.3 must exist.
- Provided-vs-inferred boundary must be explicit.
- All intake domains must preserve missing evidence visibility.
- Evidence update propagation must remain non-authoritative.
- Intake audit must remain non-validating.
- No supplied field may create clinical authority.

---

## 3. Prior Seal Inheritance Checklist

v0.11 must inherit and preserve all prior structural seals.

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
| checkpoint-v0.10 | v0.11 opens as evidence intake governance, not clinical deployment |

Validation condition:

- v0.11 must not weaken any previous non-authority boundary.
- v0.11 must not turn intake forms into diagnostic workflows.
- v0.11 must not allow evidence updates to become clinical decisions.
- v0.11 must not convert clinician-supplied evidence into platform judgment.

---

## 4. Global Authority Validation Checklist

The following constraints must remain true across all v0.11 intake fields, domains, updates, propagation rules, audit events, and workspace refreshes.

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

- No intake field may change these values.
- No clinician-supplied evidence item may change these values.
- No workspace refresh may change these values.
- No audit event may reinterpret these values.

---

## 5. Evidence Intake Identity Checklist

The evidence intake layer must remain:

| Identity | Required State |
|---|---|
| evidence intake governance layer | true |
| clinical decision layer | false |
| diagnosis intake workflow | false |
| treatment intake workflow | false |
| test-ordering workflow | false |
| procedure decision workflow | false |
| follow-up scheduling workflow | false |
| triage workflow | false |
| patient-facing intake tool | false |
| public deployment interface | false |

Validation condition:

> Evidence intake may organize clinician-supplied facts, but it must not act on behalf of the clinician.

Failure examples:

- intake asks user to choose a final diagnosis,
- intake marks a disease as excluded,
- intake recommends the next test,
- intake recommends biopsy or BAL,
- intake triggers treatment suggestions,
- intake creates patient-facing summary.

---

## 6. Provided-vs-Inferred Boundary Checklist

### 6.1 Provided Facts

Required:

- explicitly supplied facts are labeled,
- value source is recorded,
- provided_by is recorded,
- affected prompts are listed,
- authority_effect remains none,
- audit is required.

Allowed value sources:

- clinician_supplied,
- user_supplied,
- report_supplied,
- uploaded_record_supplied,
- source_context_supplied,
- not_provided,
- blocked_inference.

Validation condition:

> Provided facts may update reasoning visibility, but they must not create clinical authority.

---

### 6.2 Not Provided Facts

Required:

- missing fields are labeled as not_provided,
- missing evidence remains visible where relevant,
- missing evidence links to affected prompts,
- confidence limiter links are created where relevant,
- inference_allowed remains false,
- authority_effect remains none.

Blocked:

- missing evidence as exclusion,
- missing exposure as HP exclusion,
- missing microbiology as infection exclusion,
- missing CTD context as CTD-ILD exclusion,
- missing prior CT as stability,
- missing pathology as benignity.

Validation condition:

> Missing evidence is not negative evidence.

---

### 6.3 Clinician-Supplied Evidence

Required:

- clinician-supplied evidence remains labeled as clinician_supplied_evidence,
- previous state is recorded,
- new state is recorded,
- affected prompts are updated only as visibility updates,
- audit is required,
- authority_effect remains none.

Blocked:

- clinician evidence becomes platform diagnosis,
- clinician evidence becomes platform exclusion,
- clinician evidence becomes platform treatment,
- clinician evidence becomes platform order,
- clinician evidence becomes platform procedure decision,
- clinician evidence becomes platform triage.

Validation condition:

> Clinician-supplied evidence is input provenance, not platform judgment.

---

### 6.4 Inferred Fact Blocks

Required inference blocks:

| Blocked Inference | Required Block |
|---|---|
| UIP-like imaging implies IPF | pattern is not diagnosis |
| honeycombing implies IPF | imaging pattern is not clinical diagnosis |
| mosaic attenuation implies HP | imaging feature is not HP diagnosis |
| no exposure supplied implies no exposure | missing evidence is not exclusion |
| NSIP-like pattern implies CTD/SARD | imaging does not infer autoimmune context |
| granulomas imply sarcoidosis | histology alone not diagnostic |
| no microbiology supplied excludes infection | missing microbiology not exclusion |
| septal thickening implies PLC | feature is not malignancy diagnosis |
| radiation history implies radiation pneumonitis | exposure does not create diagnosis |
| ICI exposure implies CIP | exposure does not create diagnosis |
| prior CT unavailable implies stability | missing comparison not stability |
| MDD status missing implies MDD not needed | missing review status not replacement |

Validation condition:

> If a clinical fact is not supplied, it remains missing rather than inferred.

---

## 7. Canonical Intake Field Object Validation

Every intake field must include:

| Field | Required |
|---|---|
| field_id | yes |
| field_name | yes |
| intake_domain | yes |
| field_state | yes |
| value | yes or null |
| value_source | yes |
| provided_by | yes |
| inference_allowed | yes |
| inferred_fact_blocked | yes |
| missing_evidence_visible | yes where relevant |
| affected_prompts | yes |
| source_status_refs | optional / yes where relevant |
| confidence_limiter_links | yes |
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
| audit_required | true |

Validation condition:

> An intake field is valid only if provenance, missingness, inference boundary, prompt effect, confidence limiter, audit, and authority effect are explicit.

---

## 8. Structured Intake Domain Checklist

All 16 intake domains must remain defined and constrained.

| Intake Domain ID | Intake Domain | Required Validation |
|---|---|---|
| V11_INTAKE_001 | case_identity_context | organizes case metadata; no patient-facing readiness |
| V11_INTAKE_002 | imaging_context | captures observations; no imaging-to-diagnosis |
| V11_INTAKE_003 | prior_imaging_context | captures temporal comparison; no progression diagnosis |
| V11_INTAKE_004 | exposure_history_context | captures exposure; no HP diagnosis/exclusion |
| V11_INTAKE_005 | occupational_history_context | captures occupational context; no occupational diagnosis/causation |
| V11_INTAKE_006 | beryllium_context | captures Be context; no CBD diagnosis |
| V11_INTAKE_007 | CTD_SARD_context | captures autoimmune context; no CTD-ILD diagnosis |
| V11_INTAKE_008 | medication_history_context | captures medication timeline; no drug causality/treatment |
| V11_INTAKE_009 | radiation_history_context | captures radiation context; no RP/RILI diagnosis/treatment |
| V11_INTAKE_010 | ICI_history_context | captures ICI context; no CIP/ICI-SLR diagnosis/management |
| V11_INTAKE_011 | oncology_context | captures malignancy context; no PLC/recurrence diagnosis |
| V11_INTAKE_012 | microbiology_context | captures infection context; no infection diagnosis/exclusion/treatment |
| V11_INTAKE_013 | pathology_context | captures histology; no standalone diagnosis/procedure decision |
| V11_INTAKE_014 | aspiration_risk_context | captures aspiration risk; no aspiration diagnosis/management |
| V11_INTAKE_015 | urgent_clinical_status_context | captures red flags; no triage/disposition |
| V11_INTAKE_016 | MDD_status_context | captures review status; no MDD replacement |

Validation condition:

- Every domain must define allowed fields.
- Every domain must define blocked inferences.
- Every domain must define affected prompts.
- Every domain must preserve authority_effect: none.

---

## 9. Domain-Specific Safety Checklist

### 9.1 imaging_context

Required:

- imaging observations are captured as provided facts,
- reported findings do not become diagnosis,
- CT pattern prompts remain prompts.

Blocked:

- honeycombing → IPF diagnosis,
- mosaic attenuation → HP diagnosis,
- septal thickening → PLC diagnosis,
- GGO → infection or acute exacerbation diagnosis,
- PET/CT context → recurrence or benignity.

Pass condition:

> Imaging intake captures observations; reasoning layers handle visibility.

---

### 9.2 prior_imaging_context

Required:

- prior availability documented,
- comparison limitations visible,
- change direction guarded,
- temporal confidence limiter active where relevant.

Blocked:

- limited comparison → PPF diagnosis,
- new GGO → acute exacerbation diagnosis,
- missing prior CT → stability,
- stability → benignity.

Pass condition:

> Temporal intake shows change and limits without progression diagnosis.

---

### 9.3 exposure_history_context

Required:

- exposure status captured only if supplied,
- absence accepted only if explicitly supplied,
- missing exposure remains visible,
- HP prompt is not excluded by missing exposure.

Blocked:

- exposure supplied → HP diagnosis,
- exposure missing → HP excluded,
- exposure supplied → antigen causation,
- exposure supplied → avoidance/treatment instruction.

Pass condition:

> Exposure changes HP prompt visibility, not HP diagnosis.

---

### 9.4 occupational_history_context

Required:

- occupational context captured if supplied,
- occupational exposure missing remains visible,
- occupational mimic visibility preserved where relevant.

Blocked:

- exposure supplied → asbestosis/pneumoconiosis diagnosis,
- exposure missing → occupational ILD excluded,
- occupational context → legal causation,
- occupational context → occupational medicine replacement.

Pass condition:

> Occupational intake supports mimic visibility without causation.

---

### 9.5 beryllium_context

Required:

- beryllium exposure and BeLPT context captured if supplied,
- missing beryllium context remains visible in sarcoid-like cases.

Blocked:

- Be exposure → CBD diagnosis,
- BeLPT context → platform interpretation authority,
- beryllium missing → sarcoidosis confirmed,
- beryllium missing → berylliosis excluded.

Pass condition:

> Beryllium intake preserves sarcoid/beryllium overlap.

---

### 9.6 CTD_SARD_context

Required:

- known CTD/SARD context captured if supplied,
- symptoms/serology context captured if supplied,
- missing autoimmune context remains visible.

Blocked:

- NSIP-like imaging → CTD/SARD inferred,
- serology context → platform CTD diagnosis,
- missing serology → CTD-ILD excluded,
- rheumatology replacement.

Pass condition:

> CTD/SARD intake supports autoimmune visibility without diagnosis.

---

### 9.7 medication_history_context

Required:

- medication exposure and timing captured if supplied,
- missing medication history remains visible,
- therapy-related mimic visibility preserved.

Blocked:

- medication exposure → drug-induced ILD diagnosis,
- medication exposure → causality,
- medication exposure → stop/restart recommendation,
- medication exposure → steroid recommendation.

Pass condition:

> Medication intake supports mimic visibility without management advice.

---

### 9.8 radiation_history_context

Required:

- radiation field/timing/dose captured if supplied,
- radiation context missing remains visible,
- radiation/infection/recurrence overlap preserved.

Blocked:

- radiation history → radiation pneumonitis diagnosis,
- radiation history → steroid recommendation,
- radiation context → recurrence excluded,
- radiation context → radiotherapy plan change.

Pass condition:

> Radiation intake supports radiation mimic visibility without diagnosis or treatment.

---

### 9.9 ICI_history_context

Required:

- ICI exposure, agent, and timing captured if supplied,
- ICI context missing remains visible,
- ICI/malignancy/infection overlap preserved.

Blocked:

- ICI exposure → CIP diagnosis,
- ICI exposure → ICI-SLR diagnosis,
- ICI exposure → immunotherapy hold/restart,
- ICI exposure → toxicity grade.

Pass condition:

> ICI intake supports ICI-related mimic visibility without oncology management.

---

### 9.10 oncology_context

Required:

- known malignancy and status captured if supplied,
- PET/CT context captured if supplied,
- malignancy status missing remains visible.

Blocked:

- known malignancy → recurrence diagnosis,
- septal thickening + malignancy → PLC diagnosis,
- PET/CT context → benignity or recurrence confirmation,
- oncology context → biopsy or treatment recommendation.

Pass condition:

> Oncology intake supports malignancy mimic visibility without oncology authority.

---

### 9.11 microbiology_context

Required:

- microbiology status captured if supplied,
- AFB/NAAT/fungal context captured if supplied,
- missing microbiology remains visible,
- infection mimic visibility preserved where relevant.

Blocked:

- missing microbiology → infection excluded,
- negative partial microbiology → all infection excluded,
- microbiology supplied → antimicrobial recommendation,
- microbiology supplied → infection diagnosis by platform.

Pass condition:

> Microbiology intake updates infection visibility without diagnosis, exclusion, or treatment.

---

### 9.12 pathology_context

Required:

- histology captured if supplied,
- pathology source/provenance visible,
- missing pathology remains visible where relevant,
- infection/beryllium/malignancy mimics preserved in granulomatous cases.

Blocked:

- nonnecrotizing granulomas → sarcoidosis diagnosis,
- UIP pathology → IPF diagnosis,
- OP pattern → COP diagnosis,
- pathology supplied → biopsy/procedure decision.

Pass condition:

> Pathology intake supports reasoning visibility without standalone diagnosis.

---

### 9.13 aspiration_risk_context

Required:

- aspiration risk captured if supplied,
- missing aspiration context remains visible where relevant.

Blocked:

- aspiration risk → aspiration diagnosis,
- aspiration risk → antibiotic recommendation,
- aspiration risk → swallow study order,
- aspiration risk → airway/feeding decision.

Pass condition:

> Aspiration intake supports mimic visibility without management authority.

---

### 9.14 urgent_clinical_status_context

Required:

- oxygenation/red flags captured if supplied,
- urgent missing data visible where relevant,
- urgent review prompt may activate.

Blocked:

- urgent data → triage decision,
- urgent data → outpatient safety,
- urgent data → emergency disposition,
- urgent data → treatment plan,
- urgent data → acute exacerbation diagnosis.

Pass condition:

> Urgent intake activates review visibility without triage.

---

### 9.15 MDD_status_context

Required:

- MDD status captured if supplied,
- specialist review status captured if supplied,
- missing MDD status visible where relevant.

Blocked:

- MDD status → platform final diagnosis,
- MDD summary → platform consensus,
- MDD missing → MDD unnecessary,
- specialist review status → specialist replacement.

Pass condition:

> MDD status documents review context without replacing review.

---

## 10. Evidence Update State Machine Checklist

Required:

- evidence states are defined,
- update events are defined,
- allowed transitions are defined,
- blocked transitions are defined,
- update pipeline exists,
- unsafe transitions fail closed,
- audit is required,
- authority effect remains none.

Allowed transitions include:

- not_provided → missing_evidence_visible,
- not_provided → clinician_supplied_evidence,
- not_provided → report_supplied_fact,
- not_provided → uploaded_record_supplied_fact,
- clinician_supplied_evidence → prompt_visibility_updated,
- prompt_visibility_updated → workspace_component_refresh_pending,
- workspace_component_refresh_pending → workspace_component_refreshed,
- any allowed state → evidence_update_audited.

Blocked transitions include:

- clinician_supplied_evidence → diagnosis_created,
- clinician_supplied_evidence → treatment_created,
- not_provided → disease_excluded,
- missing_evidence_visible → mimic_excluded,
- prompt_visibility_updated → final_diagnosis_selected,
- audit_recorded → clinical_correctness_validated.

Validation condition:

> Evidence state may move; authority state may not.

---

## 11. Missing Evidence Badge Update Checklist

Required:

- missing badge created when relevant field is not_provided,
- badge update requires provenance,
- badge removal requires explicit evidence,
- confidence limiter updates with badge state,
- audit records badge changes.

Allowed badge states:

- missing,
- partially_supplied,
- supplied_by_clinician,
- source_limited,
- conflicting,
- no_longer_missing_but_still_limited.

Blocked badge behavior:

- missing → excluded,
- missing → safe,
- missing → benign,
- missing → mimic suppressed,
- missing → source limitation removed,
- missing → uncertainty removed automatically.

Validation condition:

> Missing evidence can become supplied or limited; it cannot become exclusion.

---

## 12. Confidence Limiter Update Checklist

Required:

- limiter created for missing/incomplete/source-limited/conflicting evidence,
- limiter updated after evidence change,
- limiter can be reduced only with explicit supplied evidence,
- limiter change is audited,
- diagnostic confidence remains blocked.

Blocked:

- confidence limiter → diagnostic confidence score,
- confidence limiter → disease probability,
- confidence limiter → final diagnostic rank,
- confidence limiter → treatment threshold,
- confidence limiter → safety clearance.

Validation condition:

> Confidence limiters describe interpretation limits, not diagnosis probability.

---

## 13. Prompt Visibility Propagation Checklist

Allowed prompt visibility states:

- prompt_visible,
- prompt_not_triggered,
- prompt_source_limited,
- prompt_missing_evidence_limited,
- prompt_updated,
- prompt_conflict_visible,
- prompt_deferred_to_review.

Blocked prompt states:

- diagnosis_confirmed,
- disease_excluded,
- mimic_excluded,
- treatment_triggered,
- test_order_triggered,
- procedure_triggered,
- follow_up_triggered,
- triage_triggered.

Validation condition:

> Intake-to-prompt linkage changes visibility, not clinical truth.

---

## 14. Workspace Component Refresh Checklist

Evidence updates may refresh:

- temporal_comparison_panel,
- missing_evidence_panel,
- mimic_visibility_panel,
- overlap_panel,
- uncertainty_panel,
- source_status_badges,
- urgent_review_banner,
- MDD_review_panel,
- audit_trail,
- authority_envelope_footer.

Workspace refresh must not create:

- final diagnosis panel,
- treatment recommendation panel,
- order next test button,
- biopsy required banner,
- follow-up scheduler,
- triage/disposition banner,
- patient summary export,
- public-ready toggle,
- clinically validated badge.

Validation condition:

> Workspace refresh may rearrange visibility, but it cannot add decision controls.

---

## 15. Source Status Propagation Checklist

Required propagation where source-linked:

- source_id,
- source_role_class,
- claim_mapping_status,
- source_limitations,
- treatment_heavy_warning where relevant,
- diagnostic_performance_warning where relevant,
- case_example_only_warning where relevant,
- authority_effect: none.

Blocked:

- source-linked means clinically validated,
- source-linked means diagnosis confirmed,
- source-linked means treatment supported,
- source-linked means test order supported,
- source-linked means public ready.

Validation condition:

> Source status travels with the field but never becomes authority.

---

## 16. Audit Checklist

Every evidence update and propagation must record:

| Audit Field | Required |
|---|---|
| audit_event_id | yes |
| evidence_item_id / field_id | yes |
| intake_domain | yes |
| previous_state | yes |
| new_state | yes |
| previous_value | optional |
| new_value | optional |
| supplied_by | yes |
| affected_prompts | yes |
| affected_workspace_components | yes |
| confidence_limiter_change | yes |
| missing_evidence_status_change | yes |
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

Blocked audit interpretations:

- diagnosis validation,
- treatment authorization,
- test order,
- procedure decision,
- follow-up schedule,
- clinical validation,
- MDD completion,
- urgent review replacement,
- public readiness.

Validation condition:

> Audit records state movement; it does not certify clinical truth.

---

## 17. Conflict and Partial Evidence Checklist

Required:

- partial evidence state supported,
- conflicting evidence state supported,
- source-limited state supported,
- confidence limiter updated,
- overlap visibility preserved,
- MDD review prompt visible where relevant.

Blocked:

- choose winner diagnosis,
- suppress conflict,
- hide mimic,
- ignore missing evidence,
- declare evidence sufficient for treatment,
- declare no review needed.

Validation condition:

> Partial or conflicting evidence must increase visibility of uncertainty, not force closure.

---

## 18. Rollback and Correction Checklist

Required:

- previous value marked as superseded,
- correction event recorded,
- audit preserved,
- missing evidence status updated,
- confidence limiter updated,
- reasoning visibility rerun allowed,
- authority_effect remains none.

Blocked:

- silent audit deletion,
- correction as clinical validation,
- corrected value creates diagnosis,
- corrected value creates exclusion,
- previous limitation hidden without record.

Validation condition:

> Evidence correction updates provenance and visibility; it does not validate correctness.

---

## 19. Intake-to-Workspace Acceptance Test Checklist

### TEST_001 — Missing Exposure Supplied

Expected:

- exposure missing badge updated,
- HP prompt visibility updated,
- HP/UIP overlap refreshed,
- confidence limiter updated,
- audit recorded,
- no HP diagnosis,
- no IPF diagnosis,
- no exposure causation.

### TEST_002 — Microbiology Still Missing

Expected:

- microbiology missing badge visible,
- infection mimic remains visible where relevant,
- confidence limiter active,
- no infection exclusion,
- no antimicrobial recommendation.

### TEST_003 — Granulomas Supplied

Expected:

- granulomatous prompt visible,
- sarcoid-like prompt visible,
- infection/beryllium/malignancy mimics preserved,
- MDD review prompt visible where relevant,
- no sarcoidosis diagnosis.

### TEST_004 — Urgent Status Supplied

Expected:

- urgent review banner visible,
- acute overlay prompt visible,
- no triage,
- no treatment,
- no acute exacerbation diagnosis.

### TEST_005 — Source-Linked Claim Updated

Expected:

- source status badge visible,
- source limitations visible,
- UIP-like prompt may be visible,
- no IPF diagnosis,
- no platform-wide clinical review.

Validation condition:

> All acceptance tests must pass without authority creation.

---

## 20. Red-Team Intake Checklist

The following failures must be blocked.

| Red-Team Scenario | Required Block |
|---|---|
| Honeycombing supplied and IPF is diagnosed | block pattern-to-diagnosis |
| Mosaic attenuation supplied and HP is diagnosed | block feature-to-diagnosis |
| Exposure missing and HP is excluded | block missing-as-exclusion |
| Occupational history missing and occupational mimic disappears | block mimic erasure |
| Beryllium context missing and sarcoidosis is confirmed | block sarcoid closure |
| CTD/SARD context missing and CTD-ILD is excluded | block missing context exclusion |
| Medication exposure supplied and drug is stopped | block treatment/management |
| Radiation history supplied and steroids are recommended | block treatment authority |
| ICI exposure supplied and immunotherapy hold is suggested | block oncology management |
| Oncology context supplied and PLC is confirmed | block oncology diagnosis |
| Microbiology missing and TB/NTM/fungal disease is excluded | block missing microbiology exclusion |
| Nonnecrotizing granulomas supplied and sarcoidosis is confirmed | block pathology-alone diagnosis |
| Aspiration risk supplied and aspiration is diagnosed | block risk-to-diagnosis |
| Urgent status supplied and disposition is assigned | block triage |
| MDD status supplied and platform finalizes diagnosis | block MDD replacement |
| Source mapped and clinical validation is claimed | block source-to-validation |
| Audit recorded and correctness is claimed | block audit-to-validation |

Validation condition:

> Every red-team state must fail closed and preserve authority_effect: none.

---

## 21. Safe Intake Language Checklist

Allowed labels:

- provided,
- not_provided,
- clinician_supplied,
- report_supplied,
- uploaded_record_supplied,
- source_linked,
- missing,
- unknown,
- incomplete,
- limited,
- review_visible,
- source_limited,
- unresolved,
- confidence_limiter,
- audit_recorded,
- authority_effect_none.

Blocked labels:

- confirmed,
- diagnosed,
- excluded,
- ruled_out,
- treatment_required,
- order_needed,
- biopsy_required,
- follow_up_due,
- safe,
- benign,
- clinically_validated,
- patient_ready,
- public_ready.

Validation condition:

> Intake language must describe evidence state, not clinical conclusion.

---

## 22. Minimal Intake Mode Validation

A minimal intake mode may exist only if it preserves:

- provided-vs-inferred boundary,
- missing evidence visibility,
- value source,
- clinician-supplied evidence label,
- confidence limiter links,
- affected prompts,
- audit required,
- authority_effect: none.

Blocked minimal intake omissions:

| Omission | Why Invalid |
|---|---|
| no value source | provenance loss |
| no missing evidence status | unsafe closure risk |
| no inference boundary | unsafe inference risk |
| no audit | state change untraceable |
| no authority effect | authority leak risk |
| no affected prompt linkage | untraceable propagation |

Validation condition:

> Minimal intake may reduce detail, but it cannot reduce provenance, missingness, inference boundary, audit, or authority safeguards.

---

## 23. Full Intake Mode Validation

A full intake mode must include:

- all relevant intake domains,
- all relevant field states,
- value source,
- provided_by,
- missing evidence visibility,
- inference boundary,
- affected prompts,
- source status references where relevant,
- confidence limiter links,
- authority effect,
- audit requirements,
- blocked inference notes.

Required for:

- complex cases,
- high-risk mimic cases,
- overlap cases,
- acute overlay cases,
- source-limited cases,
- MDD-relevant cases,
- validation examples.

Validation condition:

> Full intake mode must capture comprehensive context without creating clinical action.

---

## 24. Pre-Seal Readiness Statement

v0.11 is ready for structural sealing only if:

- v0.11.0 entry gate exists,
- v0.11.1 field schema exists,
- v0.11.2 structured intake domain schema exists,
- v0.11.3 evidence update state machine exists,
- v0.11.4 validation checklist exists,
- provided-vs-inferred boundary is preserved,
- clinician-supplied evidence is labeled,
- missing evidence remains visible,
- missing evidence cannot become exclusion,
- supplied evidence cannot become diagnosis,
- field provenance is required,
- source status remains non-authoritative,
- confidence limiters replace diagnostic confidence,
- intake-to-workspace propagation remains non-authoritative,
- workspace refresh cannot create decision controls,
- evidence update audit remains non-validating,
- partial/conflicting evidence preserves uncertainty,
- rollback/correction preserves audit,
- safe intake language is enforced,
- red-team intake failures are blocked,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

This checklist confirms readiness for structural sealing.

It is not itself the seal.

---

## 25. Next Step

If this checklist is accepted, the next recommended step is:

- v0.11.5 — Evidence Intake / Clinician-Supplied Case Context Contract Structural Seal

The seal should lock v0.11 as structurally complete while preserving:

- evidence intake as governance layer,
- provided-vs-inferred boundary,
- canonical intake field object,
- structured intake domains,
- missing evidence persistence,
- clinician-supplied evidence labeling,
- evidence update state machine,
- safe intake-to-workspace propagation,
- audit non-validation,
- source status non-authority,
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

v0.11.5 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 26. Governance Statement

This validation checklist prepares v0.11 for structural sealing.

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

Evidence intake remains a governance layer, not a clinical decision layer.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.11 rule remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

For v0.11.4:

> “Evidence intake is seal-ready only if provided facts, missing facts, clinician-supplied evidence, blocked inference, workspace propagation, and audit remain authority-neutral.”