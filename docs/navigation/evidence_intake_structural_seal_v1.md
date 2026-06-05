# ILD Reasoning Platform — Evidence Intake / Clinician-Supplied Case Context Contract Structural Seal v1

Version: v0.11.5  
Status: structurally_sealed  
Scope: Evidence intake and clinician-supplied case context contract structural seal  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Seal Purpose

This document structurally seals v0.11 — Evidence Intake / Clinician-Supplied Case Context Contract.

This seal confirms that the ILD Reasoning Platform now has a governed evidence intake layer for clinician-supplied case context, provided facts, missing facts, source-linked fields, blocked inference, evidence update state transitions, intake-to-workspace propagation, and non-validating audit.

This seal does not add new disease content.

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

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The sealed v0.11 principle is:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

---

## 2. Sealed v0.11 Chain

The following v0.11 chain is now structurally sealed:

| Version | File | Role | Seal Status |
|---|---|---|---|
| v0.11.0 | `docs/navigation/evidence_intake_case_context_entry_gate_v1.md` | Evidence intake entry gate | sealed |
| v0.11.1 | `docs/data/schema/evidence_intake_field_schema_provided_vs_inferred_boundary_v1.md` | Field schema / provided-vs-inferred boundary | sealed |
| v0.11.2 | `docs/data/schema/structured_intake_domain_schema_case_context_fields_v1.md` | Structured intake domain schema | sealed |
| v0.11.3 | `docs/data/schema/evidence_update_state_machine_intake_to_workspace_rules_v1.md` | Evidence update state machine / propagation rules | sealed |
| v0.11.4 | `docs/navigation/evidence_intake_validation_checklist_v1.md` | Intake safety validation checklist | sealed |
| v0.11.5 | `docs/navigation/evidence_intake_structural_seal_v1.md` | Evidence intake structural seal | sealed |

---

## 3. Structural Seal Statement

The v0.11 evidence intake layer is structurally complete.

This means:

- evidence intake entry gate exists,
- field-level provided-vs-inferred schema exists,
- structured intake domain schema exists,
- evidence update state machine exists,
- intake safety validation checklist exists,
- provided facts are separated from inferred facts,
- clinician-supplied evidence is explicitly labeled,
- missing evidence remains visible,
- unsafe inference is blocked,
- evidence update state transitions are constrained,
- intake-to-workspace propagation is non-authoritative,
- confidence limiters replace diagnostic confidence,
- source status remains non-authoritative,
- audit records state movement without validating clinical correctness,
- supplied evidence may update reasoning visibility,
- supplied evidence may not create diagnosis,
- missing evidence may not create exclusion,
- workspace refresh may not create decision controls,
- diagnostic authority remains none,
- treatment authority remains none,
- public readiness remains false,
- platform-wide clinically reviewed status remains false,
- patient-facing use remains not allowed.

This seal confirms structural evidence-intake readiness.

It does not confirm clinical performance.

---

## 4. Prior Layer Inheritance

v0.11 inherits and preserves the following prior layers:

| Prior Layer | Inherited Constraint |
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
| checkpoint-v0.10 | v0.11 remains evidence intake governance, not clinical deployment |

Sealed rule:

> v0.11 lets evidence enter the platform, but it does not let evidence become platform authority.

---

## 5. Evidence Intake Identity Seal

The evidence intake layer is sealed as:

| Identity | Sealed State |
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

Sealed rule:

> Evidence intake may organize clinician-supplied facts, but it must not act on behalf of the clinician.

---

## 6. Global Authority Seal

The following constraints are sealed across all v0.11 intake fields, intake domains, evidence updates, propagation rules, workspace refreshes, source links, confidence limiters, and audit events.

| Constraint | Sealed State |
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

Sealed rule:

> No intake field, evidence update, source link, audit event, or workspace refresh may change the authority envelope.

---

## 7. Provided-vs-Inferred Boundary Seal

The provided-vs-inferred boundary is sealed.

Allowed evidence states:

- provided_fact,
- not_provided,
- clinician_supplied_evidence,
- report_supplied_fact,
- uploaded_record_supplied_fact,
- source_context_supplied_fact,
- inferred_fact_blocked,
- missing_evidence_visible,
- source_linked,
- evidence_update_audited,
- reasoning_visibility_updated,
- authority_effect_none.

Blocked evidence states:

- diagnosis_created,
- exclusion_created,
- treatment_created,
- test_order_created,
- procedure_decision_created,
- follow_up_created,
- triage_created,
- public_ready_created,
- patient_facing_created,
- platform_wide_clinical_review_created,
- MDD_replaced,
- urgent_review_replaced.

Sealed rule:

> Field state may change visibility; field state may not create authority.

---

## 8. Canonical Intake Field Object Seal

Every intake field is sealed as a governed object containing:

```yaml
intake_field:
  field_id: string
  field_name: string
  intake_domain: string
  field_state: provided_fact | not_provided | clinician_supplied_evidence | inferred_fact_blocked | missing_evidence_visible | source_linked | evidence_update_audited
  value: any_or_null
  value_source: clinician_supplied | report_supplied | uploaded_record_supplied | source_context_supplied | not_provided | blocked_inference
  provided_by: clinician | user | report | uploaded_record | source_context | platform
  inference_allowed: false_unless_explicit_non_clinical_metadata
  inferred_fact_blocked: true_or_false
  missing_evidence_visible: true_or_false
  affected_prompts: list
  source_status_refs: list
  confidence_limiter_links: list
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
  audit_required: true
```

Sealed rule:

> An intake field is never just a value; it is a value plus provenance, missingness, inference boundary, affected prompts, source status, confidence limiter, audit state, and authority effect.

---

## 9. Required Inference Blocks Seal

The following inference blocks are sealed as mandatory.

| Blocked Inference | Sealed Reason |
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

Sealed rule:

> If a clinical fact is not supplied, it remains missing rather than inferred.

---

## 10. Structured Intake Domain Seal

The following 16 intake domains are sealed.

| Intake Domain ID | Intake Domain | Sealed Role |
|---|---|---|
| V11_INTAKE_001 | case_identity_context | Organizes case metadata; no patient-facing readiness |
| V11_INTAKE_002 | imaging_context | Captures observations; no imaging-to-diagnosis |
| V11_INTAKE_003 | prior_imaging_context | Captures temporal comparison; no progression diagnosis |
| V11_INTAKE_004 | exposure_history_context | Captures exposure; no HP diagnosis or exclusion |
| V11_INTAKE_005 | occupational_history_context | Captures occupational context; no occupational diagnosis or causation |
| V11_INTAKE_006 | beryllium_context | Captures beryllium context; no CBD diagnosis |
| V11_INTAKE_007 | CTD_SARD_context | Captures autoimmune context; no CTD-ILD diagnosis |
| V11_INTAKE_008 | medication_history_context | Captures medication timeline; no drug causality or treatment |
| V11_INTAKE_009 | radiation_history_context | Captures radiation context; no RP/RILI diagnosis or treatment |
| V11_INTAKE_010 | ICI_history_context | Captures ICI context; no CIP/ICI-SLR diagnosis or management |
| V11_INTAKE_011 | oncology_context | Captures malignancy context; no PLC/recurrence diagnosis |
| V11_INTAKE_012 | microbiology_context | Captures infection context; no infection diagnosis, exclusion, or treatment |
| V11_INTAKE_013 | pathology_context | Captures histology; no standalone diagnosis or procedure decision |
| V11_INTAKE_014 | aspiration_risk_context | Captures aspiration risk; no aspiration diagnosis or management |
| V11_INTAKE_015 | urgent_clinical_status_context | Captures red flags; no triage or disposition |
| V11_INTAKE_016 | MDD_status_context | Captures review status; no MDD replacement |

Sealed rule:

> Each intake domain captures provided case context, preserves missing evidence, blocks unsafe inference, and updates reasoning visibility without creating clinical authority.

---

## 11. Domain-Specific Authority Blocks Seal

The following domain-to-authority leaks are sealed as blocked.

| Intake Domain | Must Not Create |
|---|---|
| imaging_context | disease diagnosis |
| prior_imaging_context | PPF / acute exacerbation diagnosis |
| exposure_history_context | HP diagnosis or exclusion |
| occupational_history_context | occupational ILD diagnosis or causation |
| beryllium_context | chronic beryllium disease diagnosis |
| CTD_SARD_context | CTD-ILD diagnosis |
| medication_history_context | drug-induced ILD diagnosis or medication action |
| radiation_history_context | radiation pneumonitis diagnosis or treatment |
| ICI_history_context | CIP / ICI-SLR diagnosis or immunotherapy action |
| oncology_context | recurrence / PLC diagnosis |
| microbiology_context | infection diagnosis, exclusion, or antimicrobial action |
| pathology_context | standalone diagnosis or biopsy/procedure decision |
| aspiration_risk_context | aspiration diagnosis or management |
| urgent_clinical_status_context | triage or disposition |
| MDD_status_context | MDD replacement or platform diagnosis |

Sealed rule:

> Cross-domain intake may refine reasoning visibility; it must not create clinical closure.

---

## 12. Missing Evidence Persistence Seal

Missing evidence persistence is sealed.

Allowed missing evidence outcomes:

- missing evidence badge created,
- missing evidence badge updated,
- missing evidence badge marked partially supplied,
- missing evidence badge marked supplied by clinician,
- missing evidence badge marked source-limited,
- missing evidence badge marked conflicting,
- confidence limiter updated,
- affected prompts updated,
- audit recorded.

Blocked missing evidence outcomes:

- missing evidence becomes disease exclusion,
- missing evidence becomes mimic exclusion,
- missing evidence becomes benignity,
- missing evidence becomes safety clearance,
- missing evidence suppresses mimic visibility,
- missing evidence disappears without audit,
- missing evidence removes uncertainty automatically.

Sealed rule:

> Missing evidence can become supplied or limited; it cannot become exclusion.

---

## 13. Missing Evidence Badge Map Seal

The following domain-level missing evidence map is sealed.

| Intake Domain | Missing Evidence Badge |
|---|---|
| prior_imaging_context | prior_CT_missing; temporal_comparison_limited |
| exposure_history_context | exposure_history_missing |
| occupational_history_context | occupational_history_missing |
| beryllium_context | beryllium_context_missing |
| CTD_SARD_context | autoimmune_context_missing; serology_context_missing |
| medication_history_context | medication_history_missing |
| radiation_history_context | radiation_context_missing |
| ICI_history_context | ICI_context_missing |
| oncology_context | malignancy_status_missing; PET_CT_context_missing |
| microbiology_context | microbiology_missing; AFB_culture_NAAT_missing; fungal_testing_missing |
| pathology_context | pathology_context_missing |
| aspiration_risk_context | aspiration_risk_missing |
| urgent_clinical_status_context | urgent_clinical_status_missing |
| MDD_status_context | MDD_status_missing |

Sealed rule:

> Missing evidence badges remain interpretation limiters, not exclusion markers.

---

## 14. Confidence Limiter Seal

Confidence limiter behavior is sealed.

Allowed confidence limiter states:

- active,
- updated,
- reduced,
- resolved_by_supplied_evidence,
- replaced_by_new_limiter,
- source_limited,
- conflicting_evidence_present.

Blocked confidence limiter meanings:

- diagnostic confidence score,
- disease probability,
- final diagnostic rank,
- exclusion score,
- safety clearance,
- treatment threshold.

Sealed rule:

> Confidence limiters describe interpretation limits, not diagnosis probability.

---

## 15. Domain-Level Confidence Limiter Map Seal

The following confidence limiter map is sealed.

| Intake Domain | Confidence Limiter |
|---|---|
| prior_imaging_context | prior_CT_unavailable; temporal_comparison_limited |
| exposure_history_context | exposure_history_incomplete |
| occupational_history_context | occupational_history_incomplete |
| beryllium_context | beryllium_context_incomplete |
| CTD_SARD_context | CTD_SARD_context_incomplete |
| medication_history_context | medication_history_incomplete |
| radiation_history_context | radiation_context_incomplete |
| ICI_history_context | ICI_context_incomplete |
| oncology_context | oncology_context_incomplete; PET_CT_ambiguity |
| microbiology_context | microbiology_not_integrated |
| pathology_context | pathology_context_missing |
| aspiration_risk_context | aspiration_risk_incomplete |
| urgent_clinical_status_context | urgent_status_incomplete |
| MDD_status_context | MDD_not_documented |
| source_status_refs | source_limitation_present |

Sealed rule:

> Confidence limiter links may change visibility, but they cannot become diagnostic certainty.

---

## 16. Evidence Update State Machine Seal

The evidence update state machine is sealed.

Allowed state transitions include:

| From State | To State | Sealed Condition |
|---|---|---|
| field_initialized | not_provided | inference blocked |
| not_provided | missing_evidence_visible | exclusion effect none |
| not_provided | clinician_supplied_evidence | audit required |
| not_provided | report_supplied_fact | provenance required |
| not_provided | uploaded_record_supplied_fact | provenance required |
| provided_fact | source_limited or source_linked | source status visible |
| clinician_supplied_evidence | confidence_limiter_updated | diagnostic confidence blocked |
| clinician_supplied_evidence | prompt_visibility_updated | authority effect none |
| prompt_visibility_updated | workspace_component_refresh_pending | no clinical closure |
| workspace_component_refresh_pending | workspace_component_refreshed | authority envelope preserved |
| any_allowed_state | evidence_update_audited | audit not validation |

Blocked state transitions include:

| From State | Blocked To State | Why Blocked |
|---|---|---|
| clinician_supplied_evidence | diagnosis_created | supplied evidence is not diagnosis |
| clinician_supplied_evidence | exclusion_created | supplied evidence is not exclusion |
| clinician_supplied_evidence | treatment_created | supplied evidence is not treatment |
| clinician_supplied_evidence | test_order_created | supplied evidence is not order |
| clinician_supplied_evidence | procedure_decision_created | supplied evidence is not procedure decision |
| clinician_supplied_evidence | follow_up_created | supplied evidence is not follow-up |
| clinician_supplied_evidence | triage_created | supplied evidence is not triage |
| not_provided | disease_excluded | missing evidence is not exclusion |
| missing_evidence_visible | mimic_excluded | missing evidence cannot erase mimic |
| source_limited | clinically_validated | source limitation is not validation |
| confidence_limiter_active | diagnostic_confidence_created | limiter is not confidence score |
| prompt_visibility_updated | final_diagnosis_selected | prompt visibility is not diagnosis |
| workspace_component_refreshed | decision_surface_enabled | workspace remains reasoning visibility surface |
| evidence_update_audited | clinical_correctness_validated | audit is not validation |

Sealed rule:

> Evidence state may move; authority state may not.

---

## 17. Evidence Update Pipeline Seal

Every evidence update must pass through the following gates:

1. receive update with field ID, value, and value source,
2. classify field state,
3. check inference boundary,
4. update missing evidence state,
5. update confidence limiters,
6. update prompt visibility,
7. refresh workspace components,
8. record audit event.

Required outputs:

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

Sealed rule:

> Every update must pass through provenance, inference boundary, missing evidence, confidence limiter, prompt visibility, workspace refresh, and audit gates.

---

## 18. Intake-to-Workspace Propagation Seal

Allowed intake-to-workspace propagation:

| Intake Update | Workspace Components That May Refresh |
|---|---|
| prior imaging supplied | temporal_comparison_panel; uncertainty_panel; audit_trail |
| exposure supplied | missing_evidence_panel; fibrotic_HP_prompt; overlap_panel; uncertainty_panel |
| occupational history supplied | mimic_visibility_panel; missing_evidence_panel; source_status_badges |
| beryllium context supplied | mimic_visibility_panel; overlap_panel; MDD_review_panel |
| CTD/SARD context supplied | differential_prompt_cards; overlap_panel; MDD_review_panel |
| medication history supplied | mimic_visibility_panel; uncertainty_panel; source_status_badges |
| radiation context supplied | mimic_visibility_panel; overlap_panel; urgent_review_banner where relevant |
| ICI context supplied | mimic_visibility_panel; overlap_panel; MDD_review_panel |
| oncology context supplied | mimic_visibility_panel; overlap_panel; source_status_badges |
| microbiology supplied | mimic_visibility_panel; missing_evidence_panel; uncertainty_panel |
| pathology supplied | layer_cards; mimic_visibility_panel; overlap_panel; MDD_review_panel |
| aspiration risk supplied | mimic_visibility_panel; overlap_panel |
| urgent clinical status supplied | urgent_review_banner; mimic_visibility_panel; uncertainty_panel |
| MDD status supplied | MDD_review_panel; audit_trail |

Blocked workspace refresh outputs:

- final diagnosis panel,
- treatment recommendation panel,
- order next test button,
- biopsy required banner,
- follow-up scheduler,
- triage/disposition banner,
- patient summary export,
- public-ready toggle,
- clinically validated badge.

Sealed rule:

> Workspace refresh may rearrange visibility, but it cannot add decision controls.

---

## 19. Prompt Visibility Propagation Seal

Allowed prompt visibility states:

- prompt_visible,
- prompt_not_triggered,
- prompt_source_limited,
- prompt_missing_evidence_limited,
- prompt_updated,
- prompt_conflict_visible,
- prompt_deferred_to_review.

Blocked prompt visibility states:

- diagnosis_confirmed,
- disease_excluded,
- mimic_excluded,
- treatment_triggered,
- test_order_triggered,
- procedure_triggered,
- follow_up_triggered,
- triage_triggered.

Sealed rule:

> Prompt visibility may change; clinical truth status may not.

---

## 20. Source Status Propagation Seal

If an evidence field is source-linked, source status must propagate with:

- source_id,
- source_role_class,
- claim_mapping_status,
- source_limitations,
- treatment_heavy_warning where relevant,
- diagnostic_performance_warning where relevant,
- case_example_only_warning where relevant,
- authority_effect: none.

Blocked source propagation meanings:

- clinically validated,
- diagnosis confirmed,
- treatment supported,
- test order supported,
- procedure supported,
- public ready,
- patient ready.

Sealed rule:

> Source status travels with the field but never becomes authority.

---

## 21. Partial, Conflicting, and Corrected Evidence Seal

Partial and conflicting evidence are sealed as uncertainty-preserving states.

Allowed conflict states:

- partial_evidence_supplied,
- conflicting_evidence_present,
- source_limited,
- still_missing_context,
- confidence_limiter_updated,
- overlap_visible,
- MDD_review_prompt_visible.

Blocked conflict resolution:

- choose winner diagnosis,
- suppress conflict,
- hide mimic,
- ignore missing evidence,
- declare evidence sufficient for treatment,
- declare no review needed.

Evidence correction may:

- mark previous value as superseded,
- preserve audit record,
- record correction event,
- update missing evidence status,
- update confidence limiter,
- rerun reasoning visibility,
- preserve authority_effect: none.

Evidence correction must not:

- delete audit trail silently,
- validate clinical correctness,
- create diagnosis,
- create exclusion,
- hide previous limitation without record.

Sealed rule:

> Partial, conflicting, or corrected evidence updates provenance and visibility; it does not force closure.

---

## 22. Audit Seal

Every evidence update and workspace propagation must be auditable.

Required audit fields:

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

Sealed rule:

> Audit records state movement; it does not certify clinical truth.

---

## 23. Intake Acceptance Test Seal

The following intake-to-workspace acceptance tests are sealed.

| Test | Expected Behavior |
|---|---|
| Missing exposure supplied | exposure badge updated; HP prompt/overlap refreshed; no HP/IPF diagnosis |
| Microbiology still missing | microbiology badge visible; infection mimic visible; no infection exclusion |
| Granulomas supplied | granulomatous/sarcoid-like prompts visible; infection/beryllium/malignancy mimics preserved; no sarcoidosis diagnosis |
| Urgent status supplied | urgent banner visible; acute overlay prompt visible; no triage/treatment/acute exacerbation diagnosis |
| Source-linked claim updated | source badge and limitations visible; UIP-like prompt may be visible; no IPF diagnosis or clinical validation |

Sealed rule:

> Acceptance tests pass only if authority remains none.

---

## 24. Intake Red-Team Seal

The following failures are sealed as blocked.

| Red-Team Scenario | Sealed Block |
|---|---|
| Honeycombing supplied and IPF is diagnosed | pattern-to-diagnosis blocked |
| Mosaic attenuation supplied and HP is diagnosed | feature-to-diagnosis blocked |
| Exposure missing and HP is excluded | missing-as-exclusion blocked |
| Occupational history missing and occupational mimic disappears | mimic erasure blocked |
| Beryllium context missing and sarcoidosis is confirmed | sarcoid closure blocked |
| CTD/SARD context missing and CTD-ILD is excluded | missing context exclusion blocked |
| Medication exposure supplied and drug is stopped | treatment/management blocked |
| Radiation history supplied and steroids are recommended | treatment authority blocked |
| ICI exposure supplied and immunotherapy hold is suggested | oncology management blocked |
| Oncology context supplied and PLC is confirmed | oncology diagnosis blocked |
| Microbiology missing and TB/NTM/fungal disease is excluded | missing microbiology exclusion blocked |
| Nonnecrotizing granulomas supplied and sarcoidosis is confirmed | pathology-alone diagnosis blocked |
| Aspiration risk supplied and aspiration is diagnosed | risk-to-diagnosis blocked |
| Urgent status supplied and disposition is assigned | triage blocked |
| MDD status supplied and platform finalizes diagnosis | MDD replacement blocked |
| Source mapped and clinical validation is claimed | source-to-validation blocked |
| Audit recorded and correctness is claimed | audit-to-validation blocked |

Sealed rule:

> Every red-team state must fail closed and preserve authority_effect: none.

---

## 25. Safe Intake Language Seal

Allowed intake labels:

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

Blocked intake labels:

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

Sealed rule:

> Intake language must describe evidence state, not clinical conclusion.

---

## 26. Minimal and Full Intake Mode Seal

### 26.1 Minimal Intake Mode

A minimal intake mode may reduce detail, but must preserve:

- provided-vs-inferred boundary,
- missing evidence visibility,
- value source,
- clinician-supplied evidence label,
- confidence limiter links,
- affected prompts,
- audit required,
- authority_effect: none.

Blocked minimal intake omissions:

- no value source,
- no missing evidence status,
- no inference boundary,
- no audit,
- no authority effect,
- no affected prompt linkage.

### 26.2 Full Intake Mode

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

Sealed rule:

> Minimal intake may reduce detail, but it cannot reduce provenance, missingness, inference boundary, audit, or authority safeguards.

---

## 27. Blocked Outputs Seal

The following output categories remain sealed as blocked across v0.11.

| Blocked Output Category | Seal Status |
|---|---|
| diagnosis | blocked |
| disease exclusion | blocked |
| mimic exclusion | blocked |
| treatment recommendation | blocked |
| test ordering | blocked |
| procedure decision | blocked |
| follow-up interval | blocked |
| triage / disposition | blocked |
| public readiness claim | blocked |
| clinical validation claim | blocked |
| patient-facing report | blocked |
| MDD replacement | blocked |
| urgent review replacement | blocked |

Sealed rule:

> Intake structure must not make blocked content appear authorized.

---

## 28. Drift Blocks Sealed

The following drift risks are sealed as blocked.

| Drift Risk | Sealed Block |
|---|---|
| intake form becomes diagnostic workflow | diagnostic_authority none |
| intake form becomes treatment workflow | treatment_authority none |
| intake form becomes ordering workflow | automated_test_order not_allowed |
| intake form becomes procedure workflow | automated_procedure_decision not_allowed |
| intake form becomes follow-up scheduler | automated_follow_up_schedule not_allowed |
| urgent intake becomes triage | automated_triage not_allowed |
| MDD intake becomes MDD replacement | replacement_of_MDD not_allowed |
| supplied evidence becomes diagnosis | diagnosis_created false |
| missing evidence becomes exclusion | exclusion_created false |
| source link becomes validation | clinically_reviewed.platform_wide false |
| confidence limiter becomes probability | diagnostic_confidence blocked |
| workspace propagation creates decision controls | decision controls blocked |
| audit becomes correctness | audit non-validation |
| patient-facing mode appears | patient_facing_use not_allowed |
| public-ready toggle appears | public_ready false |

---

## 29. What This Seal Does Not Claim

This seal does not claim:

- clinical validation,
- diagnostic accuracy,
- treatment usefulness,
- guideline-complete implementation,
- real-world deployment readiness,
- public-facing readiness,
- patient-facing safety,
- automated triage readiness,
- real patient cohort validation,
- diagnosis generation capability,
- treatment planning capability,
- test ordering capability,
- procedure recommendation capability,
- follow-up scheduling capability,
- platform-wide clinical review,
- deployable clinical decision-support certification,
- MDD replacement capability.

This is a structural evidence-intake governance seal.

It proves that the v0.11 intake layer is organized, provenance-aware, missingness-preserving, inference-blocking, state-machine-governed, workspace-safe, audit-aware, non-authoritative, and safe-by-contract.

---

## 30. Final v0.11 Seal Statement

The ILD Reasoning Platform v0.11 Evidence Intake / Clinician-Supplied Case Context Contract is structurally sealed.

The platform remains an evidence-governed clinical reasoning platform.

It is not a diagnostic engine.  
It is not a treatment engine.  
It is not public-ready.  
It is not platform-wide clinically reviewed.  
It is not a patient-facing tool.  
It is not a clinical deployment interface.  
It is not a replacement for clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

Its evidence intake layer must:

- separate provided facts from inferred facts,
- label clinician-supplied evidence,
- preserve missing evidence,
- block unsafe inference,
- maintain value provenance,
- link affected prompts,
- link source status where relevant,
- link confidence limiters,
- update workspace visibility safely,
- preserve mimics and overlap,
- preserve uncertainty,
- update urgent and MDD review visibility where relevant,
- audit evidence update state changes,
- block diagnosis, exclusion, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing output, and platform-wide clinical review.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The sealed v0.11 principle is:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

---

## 31. Forward Roadmap

With v0.11 structurally sealed, the next recommended phase is:

- v0.12 — Case Assembly / Reasoning Session Object Contract

v0.12 should not open as diagnosis, treatment, public deployment, or patient-facing use.

Recommended v0.12 focus:

- assembling intake fields into a governed case object,
- linking case context to structured output layers,
- linking intake updates to workspace session state,
- defining reasoning session object schema,
- defining case snapshot and revision history,
- preserving provided-vs-inferred boundary,
- preserving missing evidence and confidence limiters,
- preserving source status,
- preserving authority envelope,
- no diagnosis,
- no treatment,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no public readiness,
- no patient-facing use,
- no platform-wide clinical review.

v0.12 must not weaken the v0.11 Evidence Intake Structural Seal.