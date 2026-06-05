# ILD Reasoning Platform — Evidence Intake / Clinician-Supplied Case Context Contract Entry Gate v1

Version: v0.11.0  
Status: evidence_intake_case_context_entry_gate  
Scope: Evidence intake and clinician-supplied case context governance entry gate  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document opens v0.11 — Evidence Intake / Clinician-Supplied Case Context Contract.

v0.11 defines how clinician-supplied case context, imaging context, clinical history, temporal data, exposure history, microbiology, pathology, oncology context, urgent clinical status, and MDD status may enter the ILD Reasoning Platform safely.

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

Its purpose is to define the entry gate for evidence intake governance.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 sealed principle remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

The v0.11 entry principle is:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

---

## 2. Relationship to Prior Seals

v0.11 inherits:

- v0.3 Superimposed Events Core,
- v0.4 Evidence Layer / Source Review Governance,
- v0.5 Test Case Coverage Expansion,
- v0.6 UIP Parity Upgrade,
- v0.6.R1/R2/R3 source debt and source-status correction,
- v0.7 Non-UIP Fibrotic ILD Differential Reasoning Structural Seal,
- v0.8 High-Risk Mimic Source-Limited Prompt Visibility Structural Seal,
- v0.9 Reasoning Output Contract / Structured Response Schema Structural Seal,
- v0.10 Clinician Review Workspace / Interactive Reasoning UI Contract Structural Seal,
- checkpoint-v0.10 roadmap discipline.

v0.11 must not weaken any prior seal.

v0.11 is an evidence intake governance phase.

It is not:

- a diagnostic phase,
- a treatment phase,
- a test-ordering phase,
- a procedure-decision phase,
- a follow-up scheduling phase,
- a public-readiness phase,
- a patient-facing phase,
- an automated clinical decision-support deployment phase.

---

## 3. v0.11 Entry Gate Scope

v0.11 may define:

- structured case context intake,
- provided facts vs inferred facts boundary,
- clinician-supplied evidence labeling,
- missing evidence persistence,
- evidence update audit,
- prior imaging intake fields,
- temporal comparison intake fields,
- exposure history intake fields,
- occupational history intake fields,
- beryllium context intake fields,
- CTD/SARD context intake fields,
- medication history intake fields,
- therapy timeline intake fields,
- radiation history intake fields,
- checkpoint inhibitor exposure intake fields,
- oncology context intake fields,
- microbiology context intake fields,
- pathology context intake fields,
- aspiration risk context intake fields,
- urgent clinical status intake fields,
- MDD status intake fields,
- safe evidence update behavior,
- unsafe inference blocks,
- no automatic diagnosis from supplied evidence,
- no automatic exclusion from missing evidence.

v0.11 may not define:

- new disease diagnosis,
- treatment pathway,
- test ordering workflow,
- procedure recommendation workflow,
- follow-up schedule,
- patient-facing intake form,
- public-ready interface,
- platform-wide clinical review status,
- autonomous triage,
- autonomous MDD replacement.

---

## 4. Global Authority Constraints

The following constraints remain mandatory across v0.11.

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

No intake field, supplied evidence item, evidence update, or intake audit event may override these constraints.

---

## 5. Evidence Intake Philosophy

Evidence intake must distinguish what was provided from what was inferred.

The platform may accept clinician-supplied facts.

The platform may show that evidence is missing.

The platform may update reasoning visibility after new evidence is supplied.

The platform may reclassify a prompt as visible, not triggered, source-limited, or limited by missing evidence.

The platform must not convert supplied evidence into:

- diagnosis,
- disease exclusion,
- mimic exclusion,
- treatment recommendation,
- test order,
- procedure decision,
- follow-up schedule,
- triage decision,
- public-ready output,
- patient-facing output,
- platform-wide clinical review.

Evidence intake rule:

> Evidence may change what remains visible; it may not decide what is true.

---

## 6. Core Intake State Types

The following intake state types are opened for v0.11 governance.

| State Type | Meaning |
|---|---|
| provided_fact | Explicitly supplied by clinician, user, report, source context, or uploaded record |
| not_provided | Missing or undocumented in the current intake |
| clinician_supplied_evidence | Evidence explicitly supplied by clinician during workspace interaction |
| platform_inferred_fact | Blocked unless explicitly allowed as non-clinical derived metadata |
| inferred_fact_blocked | Platform must not infer this field |
| missing_evidence_visible | Missing evidence remains visible |
| evidence_supplied_by_clinician | Previously missing item now supplied by clinician |
| evidence_update_audited | Evidence update recorded in audit trail |
| reasoning_visibility_updated | Prompt visibility updated after evidence intake |
| authority_effect_none | Evidence update creates no authority |
| source_status_linked | Evidence item linked to source status where relevant |
| uncertainty_updated | Confidence limiter or unresolved question updated |
| closure_status_not_established | Diagnostic closure remains not established |

---

## 7. Blocked Intake States

No intake field may enter the following states.

| Blocked State | Why Blocked |
|---|---|
| diagnosis_created_from_intake | diagnostic authority leak |
| disease_excluded_from_missing_data | exclusion authority leak |
| mimic_excluded_from_missing_data | unsafe mimic closure |
| treatment_recommended_from_intake | treatment authority leak |
| test_order_generated_from_intake | test-order authority leak |
| procedure_recommended_from_intake | procedure authority leak |
| follow_up_interval_generated_from_intake | follow-up authority leak |
| triage_decision_generated_from_intake | triage authority leak |
| MDD_replaced_by_intake | review replacement |
| urgent_review_replaced_by_intake | urgent review replacement |
| patient_facing_summary_generated | patient-facing use leak |
| public_ready_enabled_from_intake | deployment leak |
| platform_wide_clinically_reviewed_true | unsupported clinical review claim |

Blocked state rule:

> Intake data may inform reasoning visibility, but it must not produce clinical action or closure.

---

## 8. Provided Facts vs Inferred Facts Boundary

### 8.1 Provided Facts

Allowed provided facts include:

- clinician-entered demographics,
- clinician-entered symptoms,
- clinician-entered oxygenation status,
- clinician-entered prior imaging status,
- report-stated CT findings,
- explicitly supplied exposure history,
- explicitly supplied occupational history,
- explicitly supplied CTD/SARD context,
- explicitly supplied medication history,
- explicitly supplied radiation history,
- explicitly supplied checkpoint inhibitor exposure,
- explicitly supplied oncology context,
- explicitly supplied microbiology context,
- explicitly supplied pathology context,
- explicitly supplied MDD status.

### 8.2 Inferred Facts

The platform must not infer:

- exposure history from imaging pattern,
- occupational history from fibrosis pattern,
- CTD/SARD context from NSIP-like pattern,
- infection status from GGO alone,
- malignancy status from septal thickening alone,
- beryllium exposure from granulomas,
- TB/NTM/fungal exclusion from absent microbiology,
- prior CT stability from lack of prior CT,
- treatment history from imaging pattern,
- MDD conclusion from source mapping,
- urgent clinical stability from absence of urgent data.

### 8.3 Boundary Rule

> If a fact was not supplied, it remains not_provided. If it matters, it becomes missing_evidence_visible, not inferred truth.

---

## 9. Structured Intake Domain Registry

The following intake domains are opened for schema design in v0.11.

| Intake Domain ID | Intake Domain | Purpose | Authority Risk |
|---|---|---|---|
| V11_INTAKE_001 | case_identity_context | Basic case metadata without patient-facing readiness | identity overreach |
| V11_INTAKE_002 | imaging_context | HRCT/report findings as provided facts | pattern-to-diagnosis leak |
| V11_INTAKE_003 | prior_imaging_context | Temporal comparison availability | progression overclaim |
| V11_INTAKE_004 | exposure_history_context | HP/environmental exposure context | causation leak |
| V11_INTAKE_005 | occupational_history_context | Occupational/pneumoconiosis/asbestos context | occupational diagnosis leak |
| V11_INTAKE_006 | beryllium_context | Be exposure / BeLPT context | berylliosis diagnosis leak |
| V11_INTAKE_007 | CTD_SARD_context | Autoimmune/rheumatologic context | CTD-ILD diagnosis leak |
| V11_INTAKE_008 | medication_history_context | Drug/therapy exposure timeline | drug-causality leak |
| V11_INTAKE_009 | radiation_history_context | Radiation timing/field/dose context | RP/RILI diagnosis leak |
| V11_INTAKE_010 | ICI_history_context | Checkpoint inhibitor exposure context | CIP/ICI-SLR diagnosis leak |
| V11_INTAKE_011 | oncology_context | Malignancy/recurrence/PLC context | oncology decision leak |
| V11_INTAKE_012 | microbiology_context | TB/NTM/fungal/infection context | infection exclusion/treatment leak |
| V11_INTAKE_013 | pathology_context | Histology/tissue context | pathology-to-diagnosis leak |
| V11_INTAKE_014 | aspiration_risk_context | Aspiration risk context | aspiration diagnosis leak |
| V11_INTAKE_015 | urgent_clinical_status_context | Instability/red flag context | triage authority leak |
| V11_INTAKE_016 | MDD_status_context | Review status context | MDD replacement leak |
| V11_INTAKE_017 | clinician_supplied_evidence_labeling | Label supplied evidence safely | authority inflation |
| V11_INTAKE_018 | evidence_update_audit | Record evidence changes | audit-as-validation leak |

---

## 10. Intake Domain Rules

### 10.1 case_identity_context

May capture:

- case ID,
- age if supplied,
- sex if supplied,
- date/time if supplied,
- clinician role if supplied,
- institution/local context if supplied.

Must not create:

- patient-facing readiness,
- clinical validation,
- diagnosis,
- treatment authority.

Rule:

> Case identity metadata organizes intake; it does not create clinical authority.

---

### 10.2 imaging_context

May capture provided imaging facts:

- HRCT availability,
- CT protocol context if supplied,
- reported fibrosis,
- reported honeycombing,
- reported traction bronchiectasis,
- reported GGO,
- reported consolidation,
- reported nodules,
- reported mosaic attenuation,
- reported air trapping,
- reported septal thickening,
- reported lymphadenopathy,
- reported pleural plaques,
- reported distribution.

Must not infer:

- IPF from UIP-like findings,
- HP from mosaic attenuation alone,
- sarcoidosis from perilymphatic nodules alone,
- PLC from septal thickening alone,
- infection from GGO alone,
- acute exacerbation from new GGO alone.

Rule:

> Imaging intake captures observations; reasoning layers interpret visibility without diagnosis.

---

### 10.3 prior_imaging_context

May capture:

- prior CT available,
- prior CT unavailable,
- comparison date,
- interval,
- new findings,
- increased findings,
- decreased findings,
- stable findings,
- mixed findings,
- unclear comparison.

Must not create:

- PPF diagnosis,
- acute exacerbation diagnosis,
- stability reassurance,
- benignity,
- progression diagnosis without sufficient context.

Rule:

> Temporal intake supports change visibility; it does not diagnose progression.

---

### 10.4 exposure_history_context

May capture:

- bird exposure,
- mold exposure,
- farming/gardening exposure,
- humidifier exposure,
- hot tub exposure,
- occupational/environmental antigen exposure,
- exposure absent if explicitly supplied,
- exposure unknown.

Must not create:

- HP diagnosis,
- HP exclusion,
- antigen causation,
- treatment or avoidance instruction.

Rule:

> Exposure intake may update HP-related prompt visibility; it does not establish causation or diagnosis.

---

### 10.5 occupational_history_context

May capture:

- asbestos exposure context,
- silica exposure context,
- coal exposure context,
- metal dust exposure context,
- construction/mining/industrial work context,
- occupational exposure absent if explicitly supplied,
- occupational exposure unknown.

Must not create:

- asbestosis diagnosis,
- pneumoconiosis diagnosis,
- occupational causation,
- legal/occupational attribution,
- occupational medicine replacement.

Rule:

> Occupational intake supports occupational mimic visibility without occupational diagnosis or causation.

---

### 10.6 beryllium_context

May capture:

- beryllium exposure context,
- aerospace/nuclear/electronics/metal work context if supplied,
- BeLPT status if supplied,
- beryllium context unknown.

Must not create:

- beryllium sensitization diagnosis,
- chronic beryllium disease diagnosis,
- sarcoidosis exclusion,
- BeLPT interpretation authority.

Rule:

> Beryllium intake preserves beryllium/sarcoid mimic visibility without diagnosis.

---

### 10.7 CTD_SARD_context

May capture:

- known CTD/SARD diagnosis if explicitly supplied,
- autoimmune symptoms if supplied,
- serology context if supplied,
- rheumatology status if supplied,
- CTD/SARD context unknown.

Must not create:

- CTD-ILD diagnosis,
- autoimmune disease diagnosis,
- serology interpretation authority,
- rheumatology replacement.

Rule:

> CTD/SARD intake supports autoimmune-context visibility without diagnosis.

---

### 10.8 medication_history_context

May capture:

- medication exposure,
- drug start/stop timing,
- chemotherapy/immunotherapy timeline,
- known pneumotoxic drug context,
- medication history unknown.

Must not create:

- drug-induced ILD diagnosis,
- drug causality,
- medication stop/restart recommendation,
- steroid recommendation,
- oncology management.

Rule:

> Medication intake may update therapy-related mimic visibility without causality or treatment authority.

---

### 10.9 radiation_history_context

May capture:

- radiation exposure,
- radiation field if supplied,
- radiation timing if supplied,
- radiation dose/fractionation if supplied,
- radiation context unknown.

Must not create:

- radiation pneumonitis diagnosis,
- RILI diagnosis,
- recurrence exclusion,
- steroid recommendation,
- radiotherapy plan change.

Rule:

> Radiation intake supports radiation-related mimic visibility without radiation diagnosis or management authority.

---

### 10.10 ICI_history_context

May capture:

- checkpoint inhibitor exposure,
- timing of ICI therapy,
- ICI agent if supplied,
- pulmonary findings after ICI if supplied,
- ICI context unknown.

Must not create:

- checkpoint inhibitor pneumonitis diagnosis,
- ICI-associated sarcoid-like reaction diagnosis,
- immunotherapy hold/restart recommendation,
- toxicity grade,
- steroid recommendation.

Rule:

> ICI intake supports ICI-related mimic visibility without immunotherapy management authority.

---

### 10.11 oncology_context

May capture:

- known malignancy,
- tumor type if supplied,
- treatment status if supplied,
- recurrence concern if supplied,
- PET/CT context if supplied,
- oncology status unknown.

Must not create:

- cancer recurrence diagnosis,
- PLC diagnosis,
- lymphoma relapse diagnosis,
- malignancy exclusion,
- PET/CT interpretation authority,
- oncology management.

Rule:

> Oncology intake supports malignancy mimic visibility without oncology decision authority.

---

### 10.12 microbiology_context

May capture:

- microbiology available,
- AFB smear/culture/NAAT context if supplied,
- bacterial culture context if supplied,
- fungal testing context if supplied,
- NTM microbiology context if supplied,
- microbiology unknown.

Must not create:

- TB diagnosis,
- TB exclusion,
- NTM diagnosis,
- NTM exclusion,
- fungal diagnosis,
- fungal exclusion,
- antimicrobial or antifungal recommendation.

Rule:

> Microbiology intake may update infection mimic visibility, but it does not diagnose, exclude, or treat infection.

---

### 10.13 pathology_context

May capture:

- pathology available,
- biopsy/tissue result if supplied,
- granulomas if supplied,
- nonnecrotizing granulomatous inflammation if supplied,
- malignancy if supplied,
- organizing pneumonia pattern if supplied,
- UIP pattern if supplied,
- pathology unknown.

Must not create:

- sarcoidosis diagnosis from granulomas alone,
- IPF diagnosis from UIP pathology alone,
- malignancy exclusion,
- infection exclusion,
- biopsy recommendation,
- procedure decision.

Rule:

> Pathology intake supports reasoning visibility but must be integrated with clinical, radiologic, microbiologic, exposure, and MDD context.

---

### 10.14 aspiration_risk_context

May capture:

- dysphagia risk,
- neurologic swallowing risk,
- reflux/GERD context,
- dependent distribution context if supplied,
- recurrent aspiration history if supplied,
- aspiration risk unknown.

Must not create:

- aspiration diagnosis,
- antibiotic recommendation,
- swallow study order,
- airway/feeding decision,
- follow-up schedule.

Rule:

> Aspiration intake supports aspiration mimic visibility without diagnosis or management authority.

---

### 10.15 urgent_clinical_status_context

May capture:

- oxygenation status,
- rapid dyspnea progression,
- fever/systemic illness,
- hemoptysis,
- anemia,
- hemodynamic instability if supplied,
- severe/worsening respiratory status,
- urgent status unknown.

Must not create:

- triage decision,
- emergency disposition,
- outpatient safety,
- treatment plan,
- acute exacerbation diagnosis.

Rule:

> Urgent clinical status intake may activate urgent review visibility; it does not triage.

---

### 10.16 MDD_status_context

May capture:

- MDD performed,
- MDD not performed,
- MDD pending,
- specialist review performed,
- specialist review pending,
- MDD status unknown.

Must not create:

- MDD replacement,
- MDD conclusion,
- platform consensus,
- final diagnosis,
- treatment plan.

Rule:

> MDD status intake documents review context; it does not replace review.

---

## 11. Evidence Update Behavior

When new evidence is supplied, the platform may:

- update missing evidence status,
- update prompt visibility,
- update source-status-linked context,
- update confidence limiters,
- update overlap visibility,
- update mimic visibility,
- update urgent review prompt visibility,
- update MDD review prompt visibility,
- record audit event.

When new evidence is supplied, the platform must not:

- create diagnosis,
- exclude disease,
- exclude mimic,
- recommend treatment,
- order tests,
- recommend procedures,
- schedule follow-up,
- triage,
- enable public readiness,
- enable patient-facing use,
- mark platform-wide clinically reviewed.

Evidence update rule:

> New evidence may move a field from not_provided to clinician_supplied_evidence, but it cannot move the platform into authority.

---

## 12. Missing Evidence Persistence

Missing evidence must remain visible until explicitly supplied.

The platform must not:

- hide missing evidence after a pattern prompt appears,
- infer missing evidence,
- auto-fill missing evidence,
- treat missing evidence as negative evidence,
- treat missing evidence as exclusion,
- treat missing evidence as proof of stability,
- treat missing evidence as proof of benignity.

Missing evidence rule:

> Missing evidence is not absence of disease; it is a limiter of interpretation.

---

## 13. Intake Audit Requirements

Every evidence intake update must be auditable.

Required audit fields:

| Field | Required |
|---|---|
| evidence_item_id | yes |
| intake_domain | yes |
| previous_state | yes |
| new_state | yes |
| supplied_by | yes |
| clinician_supplied_evidence_label | yes where applicable |
| affected_prompts | yes |
| missing_evidence_status_change | yes |
| authority_effect | none |
| diagnosis_created | false |
| treatment_created | false |
| exclusion_created | false |
| procedure_created | false |
| test_order_created | false |
| follow_up_created | false |
| public_ready_created | false |
| patient_facing_created | false |

Audit rule:

> Intake audit records evidence state changes; it does not validate clinical correctness.

---

## 14. Intake-to-Workspace Boundary

Evidence intake may feed v0.10 workspace components.

Allowed intake effects:

| Intake Effect | Allowed Workspace Update |
|---|---|
| prior CT supplied | temporal comparison panel may update |
| exposure supplied | HP/exposure prompt visibility may update |
| occupational history supplied | occupational mimic panel may update |
| CTD/SARD context supplied | CTD-ILD prompt visibility may update |
| medication history supplied | drug/therapy mimic panel may update |
| radiation context supplied | radiation mimic overlap may update |
| ICI context supplied | ICI mimic overlap may update |
| oncology context supplied | malignancy/PLC mimic panel may update |
| microbiology supplied | infection mimic visibility may update |
| pathology supplied | pathology-context prompt may update |
| urgent status supplied | urgent review banner may update |
| MDD status supplied | MDD panel may update |

Blocked intake effects:

| Intake Effect | Blocked Outcome |
|---|---|
| prior CT supplied | automatic PPF or progression diagnosis |
| exposure supplied | HP diagnosis |
| occupational history supplied | occupational ILD diagnosis |
| CTD/SARD context supplied | CTD-ILD diagnosis |
| medication history supplied | drug-induced ILD diagnosis or drug stop |
| radiation context supplied | radiation pneumonitis diagnosis or steroid recommendation |
| ICI context supplied | CIP diagnosis or immunotherapy management |
| oncology context supplied | PLC/recurrence diagnosis |
| microbiology supplied | infection diagnosis/exclusion or antimicrobial recommendation |
| pathology supplied | standalone diagnosis or biopsy decision |
| urgent status supplied | triage/disposition |
| MDD status supplied | platform diagnosis or MDD replacement |

Boundary rule:

> Intake updates workspace visibility; it does not create workspace authority.

---

## 15. Safe Intake Language

Allowed intake labels:

- provided,
- not provided,
- clinician supplied,
- missing,
- unknown,
- limited,
- review-visible,
- source-linked,
- updated,
- audited,
- unresolved,
- confidence limiter.

Blocked intake labels:

- confirmed,
- diagnosed,
- excluded,
- ruled out,
- treatment required,
- order needed,
- biopsy required,
- follow-up due,
- safe,
- benign,
- clinically validated,
- patient-ready,
- public-ready.

Language rule:

> Intake language must describe evidence state, not clinical conclusion.

---

## 16. v0.11.0 Acceptance Criteria

v0.11.0 is accepted only if:

- v0.11 opens as evidence intake governance,
- evidence intake is not diagnosis,
- clinician-supplied evidence is labeled,
- provided facts are separated from inferred facts,
- inferred facts are blocked unless explicitly allowed as non-clinical metadata,
- structured intake domains are defined,
- missing evidence persistence is required,
- evidence update audit is required,
- intake-to-workspace boundary is defined,
- no automatic diagnosis from supplied evidence,
- no automatic exclusion from missing evidence,
- no treatment authority,
- no test ordering,
- no procedure decision,
- no follow-up scheduling,
- no triage,
- no public readiness,
- no patient-facing use,
- no platform-wide clinical review.

---

## 17. Next Step

The next recommended step is:

- v0.11.1 — Evidence Intake Field Schema / Provided-vs-Inferred Boundary

v0.11.1 should define detailed fields for:

- provided_fact,
- not_provided,
- clinician_supplied_evidence,
- inferred_fact_blocked,
- missing_evidence_visible,
- evidence_update_audited,
- authority_effect_none,
- affected_prompts,
- source_status_refs,
- confidence_limiter_links.

v0.11.1 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 18. Governance Statement

This entry gate opens evidence intake governance.

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

The v0.11 entry rule is:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”