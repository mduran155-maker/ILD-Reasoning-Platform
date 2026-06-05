# ILD Reasoning Platform — Evidence Intake Field Schema / Provided-vs-Inferred Boundary v1

Version: v0.11.1  
Status: evidence_intake_field_schema_provided_vs_inferred_boundary  
Scope: Field-level schema for evidence intake, provided facts, missing evidence, clinician-supplied evidence, blocked inference, audit, and authority boundaries  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the field-level schema for v0.11 — Evidence Intake / Clinician-Supplied Case Context Contract.

It follows:

- `docs/navigation/evidence_intake_case_context_entry_gate_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_10.md`
- `docs/navigation/clinician_workspace_structural_seal_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`
- `docs/data/schema/structured_output_layer_schema_v1.md`

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

Its purpose is to define how individual evidence intake fields must represent:

- provided facts,
- not-provided facts,
- clinician-supplied evidence,
- blocked inferred facts,
- missing evidence visibility,
- evidence update audit,
- authority effect,
- affected reasoning prompts,
- source status references,
- confidence limiter links.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.11 rule remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

For v0.11.1:

> “Every intake field must declare whether it is provided, missing, clinician-supplied, source-linked, inferred-blocked, or authority-neutral before it can affect reasoning visibility.”

---

## 2. Global Field Contract

Every evidence intake field must preserve:

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

No field may override the authority envelope.

No field may convert supplied evidence into diagnostic, exclusion, treatment, test-order, procedure, follow-up, triage, patient-facing, public-ready, or platform-wide clinical review authority.

---

## 3. Canonical Intake Field Object

Every intake field should conform to the following canonical structure.

```yaml
intake_field:
  field_id: string
  field_name: string
  intake_domain: string
  field_state: provided_fact | not_provided | clinician_supplied_evidence | inferred_fact_blocked | missing_evidence_visible | source_linked | evidence_update_audited
  value: any_or_null
  value_source: clinician_supplied | report_supplied | uploaded_record_supplied | source_context_supplied | not_provided | blocked_inference
  provided_by: clinician | user | report | uploaded_record | source_context | platform
  supplied_timestamp: implementation_defined_or_null
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

Canonical rule:

> An intake field is never just a value; it is a value plus provenance, missingness, inference boundary, affected prompts, source status, confidence limiter, audit state, and authority effect.

---

## 4. Field State Registry

Allowed field states:

| Field State | Meaning |
|---|---|
| provided_fact | Explicitly supplied before platform reasoning |
| not_provided | Missing or undocumented in the current intake |
| clinician_supplied_evidence | Explicitly supplied by clinician during workspace interaction |
| report_supplied_fact | Supplied by an uploaded or pasted report |
| uploaded_record_supplied_fact | Supplied by uploaded record or file |
| source_context_supplied_fact | Supplied by reviewed source context |
| inferred_fact_blocked | Platform is explicitly blocked from inferring this fact |
| missing_evidence_visible | Missingness remains visible as interpretation limiter |
| source_linked | Field links to source status or claim mapping |
| evidence_update_audited | Field state change recorded in audit trail |
| reasoning_visibility_updated | Downstream prompt visibility updated |
| authority_effect_none | Field has no authority effect |

Blocked field states:

| Blocked Field State | Why Blocked |
|---|---|
| diagnosis_created | diagnostic authority leak |
| exclusion_created | exclusion authority leak |
| treatment_created | treatment authority leak |
| test_order_created | test-order authority leak |
| procedure_decision_created | procedure authority leak |
| follow_up_created | follow-up authority leak |
| triage_created | triage authority leak |
| public_ready_created | deployment authority leak |
| patient_facing_created | patient-facing use leak |
| platform_wide_clinical_review_created | unsupported clinical review claim |
| MDD_replaced | review replacement |
| urgent_review_replaced | urgent review replacement |

Field state rule:

> Field state may change visibility; field state may not create authority.

---

## 5. Value Source Registry

Allowed value sources:

| Value Source | Meaning |
|---|---|
| clinician_supplied | Entered by clinician |
| user_supplied | Entered by user in current workspace |
| report_supplied | Extracted from supplied report text |
| uploaded_record_supplied | Extracted from uploaded record/file |
| source_context_supplied | Derived from source review or claim mapping context |
| not_provided | No value supplied |
| blocked_inference | Platform explicitly blocked from inferring value |

Blocked value source interpretations:

| Source Interpretation | Why Blocked |
|---|---|
| platform_inferred_clinical_fact | unsafe inference |
| imaging_implies_exposure_history | exposure inference leak |
| imaging_implies_autoimmune_context | CTD inference leak |
| missing_microbiology_implies_no_infection | missing data as exclusion |
| no_prior_CT_implies_stability | temporal inference leak |
| source_mapping_implies_clinical_validation | review inflation |
| audit_event_implies_correctness | audit misuse |

Value source rule:

> The platform must know where every field value came from before using it to update reasoning visibility.

---

## 6. Provided Fact Schema

### 6.1 Purpose

A `provided_fact` is information explicitly supplied by clinician, report, uploaded record, or source context.

It may update reasoning visibility.

It must not create clinical closure.

### 6.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| field_state | yes | provided_fact |
| value_source | yes | clinician_supplied / report_supplied / uploaded_record_supplied / source_context_supplied |
| value | yes | explicit supplied value |
| inference_allowed | yes | false unless non-clinical metadata |
| affected_prompts | yes | list |
| authority_effect | yes | none |
| audit_required | yes | true |

### 6.3 Allowed Effects

A provided fact may:

- remove a missing evidence badge,
- update prompt visibility,
- update confidence limiter list,
- update overlap visibility,
- update mimic visibility,
- update urgent review prompt visibility,
- update MDD review prompt visibility,
- update source-status-linked context,
- trigger audit event.

### 6.4 Blocked Effects

A provided fact must not:

- diagnose disease,
- exclude disease,
- exclude mimic,
- recommend treatment,
- order test,
- recommend procedure,
- schedule follow-up,
- triage patient,
- mark public ready,
- mark patient-facing ready,
- mark platform-wide clinically reviewed.

### 6.5 Required Statement

> Provided facts can update reasoning visibility, but they do not create platform clinical authority.

---

## 7. Not Provided Schema

### 7.1 Purpose

A `not_provided` field records that a relevant fact is missing or undocumented.

It must remain visible when it limits interpretation.

### 7.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| field_state | yes | not_provided |
| value | yes | null |
| missing_evidence_visible | yes | true if relevant |
| affected_prompts | yes | list |
| confidence_limiter_links | yes | list |
| inference_allowed | yes | false |
| authority_effect | yes | none |
| audit_required | yes | true where field affects reasoning |

### 7.3 Allowed Effects

A not-provided field may:

- create missing evidence visibility,
- create confidence limiter,
- preserve mimic visibility,
- preserve overlap,
- preserve uncertainty,
- trigger MDD or review visibility where relevant,
- prevent closure.

### 7.4 Blocked Effects

A not-provided field must not:

- exclude disease,
- exclude mimic,
- prove absence of exposure,
- prove absence of infection,
- prove stability,
- prove benignity,
- prove no urgent concern,
- weaken a mimic into invisibility without evidence.

### 7.5 Required Statement

> Missing evidence is not negative evidence and does not exclude a disease family or mimic.

---

## 8. Clinician-Supplied Evidence Schema

### 8.1 Purpose

`clinician_supplied_evidence` represents evidence explicitly entered by a clinician during workspace use.

It must remain labeled as clinician supplied.

### 8.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| field_state | yes | clinician_supplied_evidence |
| value_source | yes | clinician_supplied |
| provided_by | yes | clinician |
| value | yes | explicit supplied value |
| previous_state | yes | not_provided / provided_fact / source_limited / unknown |
| affected_prompts | yes | list |
| source_status_refs | optional | list |
| confidence_limiter_links | yes | list or empty |
| evidence_update_audited | yes | true |
| authority_effect | yes | none |

### 8.3 Allowed Effects

Clinician-supplied evidence may:

- change `not_provided` to `clinician_supplied_evidence`,
- reduce a confidence limiter,
- add a new confidence limiter,
- update mimic prompt visibility,
- update overlap visibility,
- update urgent review prompt visibility,
- update MDD prompt visibility,
- update missing evidence panel,
- trigger reasoning visibility rerun.

### 8.4 Blocked Effects

Clinician-supplied evidence must not:

- become platform diagnosis,
- become platform exclusion,
- become platform treatment,
- become platform order,
- become platform procedure decision,
- become platform follow-up schedule,
- become platform triage,
- become platform-wide clinical review.

### 8.5 Clinician Evidence Boundary

Clinician-supplied evidence may represent human-entered clinical context, but the platform must not reinterpret it as its own clinical judgment.

Required label:

```yaml
value_source: clinician_supplied
authority_effect: none
platform_conclusion_created: false
```

---

## 9. Inferred Fact Block Schema

### 9.1 Purpose

`inferred_fact_blocked` prevents the platform from filling missing clinical facts from patterns, sources, or adjacent fields.

### 9.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| field_state | yes | inferred_fact_blocked |
| blocked_inference_type | yes | string |
| source_field | optional | field_id |
| target_field | yes | field_id |
| reason_for_block | yes | string |
| missing_evidence_visible | yes | true |
| authority_effect | yes | none |
| audit_required | yes | true |

### 9.3 Required Inference Blocks

The following inference blocks are mandatory.

| Blocked Inference | Required Reason |
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

### 9.4 Required Statement

> The platform must leave unsupplied clinical facts missing rather than infer them from pattern recognition.

---

## 10. Missing Evidence Visibility Schema

### 10.1 Purpose

`missing_evidence_visible` ensures that missing evidence remains visible to the clinician.

### 10.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| field_state | yes | missing_evidence_visible |
| missing_item_id | yes | string |
| affected_prompts | yes | list |
| confidence_limiter_links | yes | list |
| mimic_visibility_links | optional | list |
| overlap_links | optional | list |
| review_prompt_links | optional | list |
| exclusion_effect | yes | none |
| authority_effect | yes | none |

### 10.3 Allowed Missing Evidence Categories

- prior_imaging_context
- temporal_comparison_context
- exposure_history_context
- occupational_history_context
- beryllium_context
- CTD_SARD_context
- medication_history_context
- radiation_history_context
- ICI_history_context
- oncology_context
- microbiology_context
- AFB_culture_NAAT_context
- fungal_testing_context
- pathology_context
- aspiration_risk_context
- urgent_clinical_status_context
- MDD_status_context

### 10.4 Blocked Missing Evidence Effects

Missing evidence must not produce:

- HP exclusion,
- infection exclusion,
- CTD-ILD exclusion,
- occupational ILD exclusion,
- malignancy exclusion,
- stability confirmation,
- benignity,
- urgent review dismissal,
- MDD dismissal.

### 10.5 Required Statement

> Missing evidence remains visible because it limits interpretation; it does not close reasoning.

---

## 11. Evidence Update Audit Schema

### 11.1 Purpose

Every evidence update must be auditable.

Audit records state change and downstream visibility update.

It does not validate clinical correctness.

### 11.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| audit_event_id | yes | string |
| evidence_item_id | yes | field_id |
| intake_domain | yes | string |
| previous_state | yes | field_state |
| new_state | yes | field_state |
| previous_value | optional | any_or_null |
| new_value | optional | any_or_null |
| supplied_by | yes | clinician / user / report / uploaded_record / source_context |
| affected_prompts | yes | list |
| affected_workspace_components | yes | list |
| confidence_limiter_change | yes | added / removed / unchanged / updated |
| missing_evidence_status_change | yes | added / removed / unchanged / updated |
| authority_effect | yes | none |
| diagnosis_created | yes | false |
| exclusion_created | yes | false |
| treatment_created | yes | false |
| test_order_created | yes | false |
| procedure_decision_created | yes | false |
| follow_up_created | yes | false |
| triage_created | yes | false |
| public_ready_created | yes | false |
| patient_facing_created | yes | false |
| platform_wide_clinical_review_created | yes | false |

### 11.3 Blocked Audit Interpretations

The audit trail must not be interpreted as:

- diagnosis validation,
- treatment authorization,
- test order,
- procedure decision,
- follow-up schedule,
- clinical validation,
- MDD completion,
- urgent review replacement,
- public readiness.

### 11.4 Required Statement

> Evidence audit records what changed in the intake state; it does not prove clinical correctness.

---

## 12. Authority Effect Schema

### 12.1 Purpose

Every intake field must explicitly declare authority effect.

### 12.2 Required Field

```yaml
authority_effect: none
```

### 12.3 Required Authority Fields

Every intake field must preserve:

```yaml
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

### 12.4 Blocked Authority Effects

Blocked values:

- diagnostic_authority_created
- exclusion_authority_created
- treatment_authority_created
- test_order_authority_created
- procedure_authority_created
- follow_up_authority_created
- triage_authority_created
- public_ready_authority_created
- patient_facing_authority_created
- platform_wide_clinical_review_created

### 12.5 Required Statement

> Intake fields have authority effect none, regardless of how clinically important the supplied evidence may be.

---

## 13. Affected Prompts Schema

### 13.1 Purpose

Intake fields may link to affected reasoning prompts.

This link updates visibility only.

### 13.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| affected_prompt_id | yes | string |
| prompt_family | yes | pattern / differential / mimic / overlap / urgent / MDD / uncertainty / source_status |
| effect_type | yes | visible / not_triggered / source_limited / confidence_limited / missing_evidence_limited / updated |
| authority_effect | yes | none |

### 13.3 Allowed Prompt Families

- UIP_like_prompt
- probable_UIP_like_prompt
- fibrotic_HP_prompt
- CTD_ILD_prompt
- NSIP_like_prompt
- OP_like_prompt
- sarcoid_like_prompt
- granulomatous_prompt
- occupational_mimic_prompt
- beryllium_mimic_prompt
- infection_mimic_prompt
- TB_mimic_prompt
- NTM_mimic_prompt
- fungal_mimic_prompt
- aspiration_mimic_prompt
- drug_therapy_related_mimic_prompt
- radiation_related_mimic_prompt
- ICI_related_mimic_prompt
- malignancy_PLC_mimic_prompt
- acute_overlay_prompt
- urgent_review_prompt
- MDD_review_prompt
- uncertainty_prompt
- source_status_prompt

### 13.4 Blocked Prompt Effects

A prompt link must not create:

- diagnosis,
- exclusion,
- treatment,
- order,
- procedure,
- follow-up,
- triage,
- public readiness,
- patient-facing output.

### 13.5 Required Statement

> Intake-to-prompt linkage changes visibility, not clinical truth.

---

## 14. Source Status Reference Schema

### 14.1 Purpose

Intake fields may link to source status references where source governance is relevant.

### 14.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| source_status_ref_id | yes | string |
| source_id | yes | string |
| source_role_class | yes | allowed source role |
| claim_mapping_status | yes | mapped / partial / source_limited / not_mapped |
| source_limitations | yes | list |
| treatment_heavy_warning | yes where relevant | text |
| diagnostic_performance_warning | yes where relevant | text |
| case_example_only_warning | yes where relevant | text |
| authority_effect | yes | none |

### 14.3 Allowed Source Role Classes

- primary_high_authority
- primary_limited_scope
- auxiliary_review
- diagnostic_performance_study
- case_example_cautionary
- internal_governance

### 14.4 Blocked Source Effects

Source reference must not mean:

- clinically validated,
- diagnosis confirmed,
- treatment supported,
- test order supported,
- procedure supported,
- public ready,
- patient ready.

### 14.5 Required Statement

> Source linkage explains why a field matters; it does not authorize a clinical conclusion.

---

## 15. Confidence Limiter Link Schema

### 15.1 Purpose

Intake fields may create or resolve confidence limiters.

Confidence limiters replace diagnostic confidence.

### 15.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| confidence_limiter_id | yes | string |
| linked_field_id | yes | field_id |
| limiter_type | yes | missing / incomplete / source_limited / unresolved / conflicting |
| affected_prompts | yes | list |
| status | yes | active / updated / resolved_by_supplied_evidence / not_applicable |
| diagnostic_confidence_created | yes | false |
| authority_effect | yes | none |

### 15.3 Allowed Limiter Types

- prior_CT_unavailable
- exposure_history_incomplete
- occupational_history_incomplete
- beryllium_context_incomplete
- CTD_SARD_context_incomplete
- medication_history_incomplete
- radiation_context_incomplete
- ICI_context_incomplete
- oncology_context_incomplete
- microbiology_not_integrated
- pathology_context_missing
- urgent_status_incomplete
- MDD_not_documented
- source_limitation_present
- conflicting_evidence_present

### 15.4 Blocked Limiter Effects

A confidence limiter must not become:

- diagnostic confidence score,
- disease probability,
- final diagnostic rank,
- exclusion score,
- safety clearance.

### 15.5 Required Statement

> Confidence limiters explain what limits interpretation, not how certain the platform is about a diagnosis.

---

## 16. Intake Field Dependency Rules

### 16.1 Allowed Dependencies

Allowed:

- prior_imaging_context may feed temporal_comparison_panel,
- exposure_history_context may feed fibrotic_HP_prompt visibility,
- occupational_history_context may feed occupational_mimic_prompt visibility,
- CTD_SARD_context may feed CTD_ILD_prompt visibility,
- medication_history_context may feed drug_therapy_related_mimic visibility,
- radiation_history_context may feed radiation_related_mimic visibility,
- ICI_history_context may feed ICI_related_mimic visibility,
- oncology_context may feed malignancy_PLC_mimic visibility,
- microbiology_context may feed infection_mimic visibility,
- pathology_context may feed granulomatous/pathology-context visibility,
- urgent_clinical_status_context may feed urgent_review_prompt visibility,
- MDD_status_context may feed MDD_review_panel visibility.

### 16.2 Blocked Dependencies

Blocked:

- exposure_history_context → HP diagnosis,
- occupational_history_context → occupational ILD diagnosis,
- CTD_SARD_context → CTD-ILD diagnosis,
- medication_history_context → drug-induced ILD diagnosis,
- radiation_history_context → radiation pneumonitis diagnosis,
- ICI_history_context → CIP diagnosis,
- oncology_context → PLC/recurrence diagnosis,
- microbiology_context → infection diagnosis or exclusion,
- pathology_context → standalone diagnosis,
- urgent_clinical_status_context → triage/disposition,
- MDD_status_context → platform diagnosis.

Dependency rule:

> Intake dependencies may update visibility routes, but cannot create clinical decision routes.

---

## 17. Minimal Field Requirements by Intake Domain

Each intake domain must support at least:

| Intake Domain | Minimal Required Fields |
|---|---|
| case_identity_context | case_id; age_if_supplied; sex_if_supplied; source |
| imaging_context | imaging_modality; reported_findings; distribution_if_supplied; source |
| prior_imaging_context | prior_available; comparison_interval; change_direction; limitation |
| exposure_history_context | exposure_status; exposure_type_if_supplied; uncertainty |
| occupational_history_context | occupational_exposure_status; exposure_type_if_supplied; uncertainty |
| beryllium_context | beryllium_exposure_status; BeLPT_context_if_supplied; uncertainty |
| CTD_SARD_context | CTD_status_if_supplied; symptoms_if_supplied; serology_if_supplied |
| medication_history_context | medication_exposure; timing_if_supplied; uncertainty |
| radiation_history_context | radiation_exposure; field_if_supplied; timing_if_supplied |
| ICI_history_context | ICI_exposure; agent_if_supplied; timing_if_supplied |
| oncology_context | malignancy_status_if_supplied; tumor_type_if_supplied; recurrence_context_if_supplied |
| microbiology_context | microbiology_available; organism_context_if_supplied; limitation |
| pathology_context | pathology_available; histology_summary_if_supplied; limitation |
| aspiration_risk_context | aspiration_risk_status; risk_factor_if_supplied; uncertainty |
| urgent_clinical_status_context | oxygenation_if_supplied; rapid_worsening; systemic_illness_if_supplied |
| MDD_status_context | MDD_status; specialist_review_status; limitation |
| clinician_supplied_evidence_labeling | supplied_by; field_id; previous_state; new_state |
| evidence_update_audit | event_id; previous_state; new_state; authority_effect |

Detailed domain-specific schema should be expanded in later v0.11 steps.

---

## 18. Safe Field Language

Allowed field labels:

- provided,
- not_provided,
- clinician_supplied,
- report_supplied,
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

Blocked field labels:

- diagnosed,
- confirmed,
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

Field language rule:

> Intake fields must describe evidence state, not clinical conclusion.

---

## 19. Intake Red-Team Scenarios

The following intake failures must be blocked.

| Scenario | Required Block |
|---|---|
| Honeycombing supplied, platform marks IPF diagnosis | block pattern-to-diagnosis |
| Mosaic attenuation supplied, platform marks HP diagnosis | block feature-to-diagnosis |
| Exposure not supplied, platform suppresses HP | block missing-as-exclusion |
| NSIP-like findings supplied, platform infers CTD/SARD | block imaging-to-autoimmune inference |
| Nonnecrotizing granulomas supplied, platform confirms sarcoidosis | block pathology-alone diagnosis |
| No microbiology supplied, platform excludes TB | block missing microbiology exclusion |
| Radiation history supplied, platform recommends steroids | block treatment authority |
| ICI exposure supplied, platform recommends immunotherapy hold | block oncology management |
| Malignancy context supplied, platform confirms PLC | block oncology diagnosis |
| Urgent status supplied, platform assigns disposition | block triage authority |
| MDD status supplied, platform generates final diagnosis | block MDD replacement |
| Clinician note added, platform treats it as source-reviewed claim | block note-to-source inflation |

---

## 20. v0.11.1 Acceptance Criteria

v0.11.1 is accepted only if:

- canonical intake field object is defined,
- field state registry is defined,
- blocked field states are defined,
- value source registry is defined,
- provided fact schema is defined,
- not-provided schema is defined,
- clinician-supplied evidence schema is defined,
- inferred fact block schema is defined,
- missing evidence visibility schema is defined,
- evidence update audit schema is defined,
- authority effect schema is defined,
- affected prompts schema is defined,
- source status reference schema is defined,
- confidence limiter link schema is defined,
- intake dependency rules are defined,
- minimal field requirements by intake domain are listed,
- safe field language is defined,
- red-team intake failures are blocked,
- supplied evidence may update reasoning visibility only,
- missing evidence cannot become exclusion,
- no automatic diagnosis from supplied evidence,
- no treatment authority,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no public readiness,
- no patient-facing use,
- no platform-wide clinical review.

---

## 21. Next Step

The next recommended step is:

- v0.11.2 — Structured Intake Domain Schema / Case Context Fields

v0.11.2 should define detailed domain schemas for:

- case_identity_context,
- imaging_context,
- prior_imaging_context,
- exposure_history_context,
- occupational_history_context,
- beryllium_context,
- CTD_SARD_context,
- medication_history_context,
- radiation_history_context,
- ICI_history_context,
- oncology_context,
- microbiology_context,
- pathology_context,
- aspiration_risk_context,
- urgent_clinical_status_context,
- MDD_status_context.

v0.11.2 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 22. Governance Statement

This field schema defines how evidence intake fields behave.

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

For v0.11.1:

> “Every intake field must declare whether it is provided, missing, clinician-supplied, source-linked, inferred-blocked, or authority-neutral before it can affect reasoning visibility.”