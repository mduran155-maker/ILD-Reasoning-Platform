# ILD Reasoning Platform — UI Copy Source Mapping / Safety Language Contract v1

Version: v0.16.3  
Status: ui_copy_source_mapping_safety_language_contract  
Scope: Source-governed UI copy registry, safety language IDs, route-level copy mapping, screen-level copy mapping, component-level copy mapping, disabled control copy mapping, fail-closed copy mapping, export preview copy mapping, red-team quarantine copy mapping, visual safety copy mapping, authority envelope copy mapping, no-decision object copy mapping, blocked copy phrases, and copy validation checklist  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document defines v0.16.3 — UI Copy Source Mapping / Safety Language Contract.

v0.16.3 translates the sealed prototype workspace and build scaffold contracts into a source-governed UI copy registry.

This document does not implement a clinical product.

It does not add new clinical content.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import HRCT images.  
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not perform clinical validation.  
It does not prove diagnostic performance.  
It does not create a deployed clinical workflow.

Its purpose is to make safety-critical UI language source-governed, auditable, reusable, and constrained.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.16.3 copy principle is:

> “No safety-critical UI copy may be invented without source mapping.”

The v0.16.3 language discipline is:

> “UI copy may teach boundaries, but it must not imply diagnosis, treatment, ordering, procedure decision, follow-up, triage, validation, readiness, patient-facing use, or MDD replacement.”

---

## 2. Relationship to v0.16.0–v0.16.2

v0.16.3 inherits:

- v0.16.0 — Source-Governed Prototype Build Scaffold Entry Gate,
- v0.16.1 — Prototype Route / Screen Registry Implementation Plan,
- v0.16.2 — Synthetic Fixture Registry / Demo State Binding Plan.

v0.16.0 opened source-governed build scaffold planning.

v0.16.1 defined allowed and blocked internal prototype routes and screen mappings.

v0.16.2 defined synthetic fixture registry and demo state binding.

v0.16.3 defines the safety language that may appear in those routes, screens, components, disabled controls, fail-closed states, export previews, red-team examples, audit traces, and safety references.

v0.16.3 does not broaden v0.16.0–v0.16.2.

v0.16.3 must not open:

- real patient data,
- deidentified real patient data,
- real clinical intake,
- DICOM import,
- HRCT import,
- real clinical report import,
- PACS integration,
- EHR integration,
- diagnosis generation,
- disease ranking,
- disease exclusion,
- treatment recommendation,
- test ordering,
- procedure recommendation,
- follow-up scheduling,
- triage,
- patient-facing output,
- public-ready output,
- product-ready output,
- clinical validation,
- diagnostic performance measurement,
- MDD replacement.

Copy inheritance rule:

> v0.16.3 may map safety language only; it may not create clinical language.

---

## 3. Global Authority Envelope

Every copy string, label, tooltip, heading, banner, disabled-control explanation, modal text, fail-closed reason, export preview section label, red-team quarantine message, audit trace description, and validation result phrase must inherit the following authority envelope.

```yaml
authority_envelope:
  diagnostic_authority: none
  treatment_authority: none
  test_order_authority: none
  procedure_decision_authority: none
  follow_up_authority: none
  triage_authority: none
  patient_facing_use: not_allowed
  public_ready: false
  product_ready: false
  clinically_reviewed_platform_wide: false
  real_patient_data: not_allowed
  deidentified_real_patient_data: not_allowed
  dicom_import: not_allowed
  hrct_import: not_allowed
  real_report_import: not_allowed
  pacs_connection: not_allowed
  ehr_connection: not_allowed
  clinical_validation: not_opened
  diagnostic_performance_claim: not_allowed
  mdd_replacement: not_allowed
```

No UI copy may override, soften, hide, contradict, or imply an exception to this envelope.

Authority copy rule:

> Safety copy must make lack of authority easier to see, not easier to miss.

---

## 4. Global No-Decision Copy Requirement

Every decision-adjacent route, screen, component, preview, or fail-closed state must include no-decision copy.

Required no-decision meaning:

```yaml
no_decision_copy_meaning:
  diagnosis_made: false
  disease_excluded: false
  mimic_excluded: false
  treatment_selected: false
  test_ordered: false
  procedure_decided: false
  follow_up_scheduled: false
  triage_assigned: false
  mdd_consensus_generated: false
  patient_facing_output_generated: false
```

Required no-decision copy classes:

- no diagnosis generated,
- no disease excluded,
- no mimic excluded,
- no treatment selected,
- no test ordered,
- no procedure decided,
- no follow-up scheduled,
- no triage assigned,
- no MDD consensus generated,
- no patient-facing output generated.

No-decision copy rule:

> UI copy must say what the platform did not do before users can infer clinical action.

---

## 5. UI Copy Registry Object Schema

Every UI copy registry must conform to the following schema.

```yaml
ui_copy_registry:
  registry_id: string
  version: v0.16.3
  registry_scope: source_governed_internal_demo_safety_copy
  internal_demo_only: true
  synthetic_demo_only: true
  clinical_use_allowed: false
  patient_facing_allowed: false
  public_ready: false
  product_ready: false
  clinical_validation_effect: none
  diagnostic_performance_effect: none
  allowed_copy_classes: list
  blocked_copy_classes: list
  required_source_mapping: true
  required_authority_envelope_alignment: true
  required_no_decision_alignment: conditional_required
  required_audit_stub_alignment: true
  validation_required: true
```

UI copy registry rule:

> A UI copy registry is valid only if every safety-critical phrase has source, scope, and blocked-language constraints.

---

## 6. UI Copy Entry Schema

Every safety-critical copy entry must conform to the following schema.

```yaml
ui_copy_entry:
  copy_id: string
  version: v0.16.3
  copy_text: string
  copy_class: enum
  route_id: optional
  screen_id: optional
  component_id: optional
  state_id: optional
  source_contract_version: string
  source_contract_file: string
  source_contract_rule: string
  required_visibility: enum(always_visible, route_visible, decision_adjacent, modal_visible, tooltip_visible, preview_visible)
  allowed_contexts: list
  blocked_contexts: list
  authority_effect: none
  decision_effect: none
  clinical_validation_effect: none
  product_readiness_effect: none
  public_readiness_effect: none
  patient_facing_effect: none
  unsafe_reuse_risk: string
  audit_stub_required: boolean
```

Copy entry rule:

> A copy entry is allowed only if it states its source and preserves non-authority.

---

## 7. Allowed Copy Classes

The following copy classes are allowed.

| Copy Class | Allowed Meaning |
|---|---|
| synthetic_boundary_copy | Identifies synthetic demo-only status |
| non_clinical_boundary_copy | Identifies not-for-clinical-use status |
| not_patient_facing_copy | Blocks patient-facing interpretation |
| public_ready_false_copy | Blocks public-readiness interpretation |
| product_ready_false_copy | Blocks product-readiness interpretation |
| clinical_validation_not_opened_copy | Blocks validation overclaim |
| diagnostic_authority_none_copy | Blocks diagnosis interpretation |
| treatment_authority_none_copy | Blocks treatment interpretation |
| order_authority_none_copy | Blocks test-order interpretation |
| procedure_authority_none_copy | Blocks procedure interpretation |
| follow_up_authority_none_copy | Blocks follow-up interpretation |
| triage_authority_none_copy | Blocks triage interpretation |
| missing_evidence_limiter_copy | Explains missingness as limiter |
| mimic_visibility_boundary_copy | Explains mimic visibility as safety prompt |
| overlap_unresolved_copy | Preserves unresolved boundary |
| source_status_limiter_copy | Explains source status as limitation |
| confidence_limiter_copy | Blocks probability/ranking |
| reasoning_map_safety_copy | Blocks map-as-proof interpretation |
| visual_safety_copy | Blocks visual-as-diagnosis/probability/authority |
| export_preview_boundary_copy | Blocks report interpretation |
| red_team_quarantine_copy | Blocks unsafe phrase reuse |
| fail_closed_copy | Explains blocked unsafe state |
| repair_ui_safety_copy | Explains repair as UI safety only |
| revalidation_ui_safety_copy | Explains revalidation as UI safety only |
| audit_trace_boundary_copy | Blocks audit-as-correctness interpretation |
| mdd_preparation_boundary_copy | Blocks MDD consensus interpretation |

Allowed copy class rule:

> Allowed copy explains boundaries, visibility, limitation, and traceability only.

---

## 8. Blocked Copy Classes

The following copy classes are blocked.

| Blocked Copy Class | Reason |
|---|---|
| diagnostic_result_copy | diagnostic authority blocked |
| final_diagnosis_copy | diagnostic closure blocked |
| most_likely_diagnosis_copy | ranking/probability blocked |
| disease_probability_copy | probability display blocked |
| disease_rule_out_copy | exclusion authority blocked |
| mimic_confirmed_copy | diagnostic authority blocked |
| mimic_excluded_copy | exclusion authority blocked |
| treatment_recommendation_copy | treatment authority blocked |
| test_order_copy | test-order authority blocked |
| procedure_recommendation_copy | procedure authority blocked |
| follow_up_schedule_copy | follow-up authority blocked |
| triage_disposition_copy | triage authority blocked |
| patient_summary_copy | patient-facing use blocked |
| clinical_validation_pass_copy | clinical validation not opened |
| diagnostic_accuracy_copy | diagnostic performance claim blocked |
| product_ready_copy | product readiness false |
| public_ready_copy | public readiness false |
| mdd_consensus_copy | MDD replacement blocked |
| expert_equivalence_copy | clinician replacement risk |

Blocked copy class rule:

> If a copy class sounds like a clinical conclusion, action, validation, or readiness claim, it is blocked.

---

## 9. Core Safety Language Registry

The following core safety copy entries are required.

| Copy ID | Copy Text | Copy Class |
|---|---|---|
| COPY_SYN_001 | Synthetic demo only. | synthetic_boundary_copy |
| COPY_SYN_002 | This prototype uses sealed fictional demo fixtures only. | synthetic_boundary_copy |
| COPY_CLIN_001 | Not for clinical use. | non_clinical_boundary_copy |
| COPY_CLIN_002 | This workspace is an internal non-clinical prototype demonstration. | non_clinical_boundary_copy |
| COPY_PAT_001 | Not patient-facing. | not_patient_facing_copy |
| COPY_PAT_002 | Patient-facing use is not allowed. | not_patient_facing_copy |
| COPY_READY_001 | Public ready: false. | public_ready_false_copy |
| COPY_READY_002 | Product ready: false. | product_ready_false_copy |
| COPY_VAL_001 | Clinical validation: not opened. | clinical_validation_not_opened_copy |
| COPY_VAL_002 | UI safety validation is not clinical validation. | clinical_validation_not_opened_copy |
| COPY_DX_001 | No diagnosis generated. | diagnostic_authority_none_copy |
| COPY_DX_002 | Diagnostic authority is none. | diagnostic_authority_none_copy |
| COPY_TX_001 | No treatment selected. | treatment_authority_none_copy |
| COPY_TX_002 | Treatment authority is none. | treatment_authority_none_copy |
| COPY_ORDER_001 | No tests ordered. | order_authority_none_copy |
| COPY_PROC_001 | No procedures decided. | procedure_authority_none_copy |
| COPY_FU_001 | No follow-up scheduled. | follow_up_authority_none_copy |
| COPY_TRIAGE_001 | No triage assigned. | triage_authority_none_copy |
| COPY_MDD_001 | MDD preparation preview is not MDD consensus. | mdd_preparation_boundary_copy |
| COPY_AUDIT_001 | Audit trace explains UI state, not medical correctness. | audit_trace_boundary_copy |

Core safety copy rule:

> Core safety copy must be available before any prototype screen can be treated as build-plannable.

---

## 10. Route-Level Copy Mapping

Every allowed route must map to required source-governed copy.

| Route | Required Copy IDs |
|---|---|
| `/prototype` | COPY_SYN_001; COPY_CLIN_001; COPY_PAT_001; COPY_READY_001; COPY_READY_002; COPY_DX_002 |
| `/prototype/cases` | COPY_SYN_002; COPY_CLIN_002; COPY_VAL_001 |
| `/prototype/cases/:synthetic_case_id/intake` | COPY_SYN_002; COPY_CLIN_001; COPY_DX_001 |
| `/prototype/cases/:synthetic_case_id/map` | COPY_SYN_001; COPY_DX_002; COPY_AUDIT_001 |
| `/prototype/cases/:synthetic_case_id/evidence` | COPY_SYN_001; COPY_CLIN_001; COPY_DX_001 |
| `/prototype/cases/:synthetic_case_id/evidence/missing` | COPY_SYN_001; COPY_DX_001 |
| `/prototype/cases/:synthetic_case_id/evidence/mimics` | COPY_SYN_001; COPY_DX_001 |
| `/prototype/cases/:synthetic_case_id/evidence/overlap` | COPY_SYN_001; COPY_DX_001 |
| `/prototype/cases/:synthetic_case_id/evidence/source-status` | COPY_SYN_001; COPY_DX_002 |
| `/prototype/cases/:synthetic_case_id/evidence/confidence-limiter` | COPY_SYN_001; COPY_DX_002 |
| `/prototype/cases/:synthetic_case_id/evidence/review-prompts` | COPY_SYN_001; COPY_ORDER_001; COPY_PROC_001; COPY_FU_001; COPY_TRIAGE_001 |
| `/prototype/cases/:synthetic_case_id/export-preview` | COPY_SYN_001; COPY_CLIN_001; COPY_PAT_001; COPY_MDD_001; COPY_DX_001; COPY_TX_001; COPY_ORDER_001 |
| `/prototype/red-team` | COPY_SYN_001; COPY_CLIN_001; COPY_VAL_002 |
| `/prototype/red-team/:scenario_id` | COPY_SYN_001; COPY_CLIN_001; COPY_VAL_002 |
| `/prototype/cases/:synthetic_case_id/audit` | COPY_AUDIT_001; COPY_VAL_002 |
| `/prototype/safety` | COPY_SYN_001; COPY_CLIN_001; COPY_PAT_001; COPY_DX_002; COPY_TX_002; COPY_VAL_001 |

Route copy rule:

> Every route must display copy that prevents the route from being read as clinical workflow.

---

## 11. Screen-Level Copy Mapping

Every registered screen must map to required source-governed copy.

| Screen | Required Copy Meaning |
|---|---|
| Prototype Boundary Landing Screen | synthetic-only, not clinical, not patient-facing, no authority |
| Synthetic Demo Case Selector | fictional governance scenario selection only |
| Demo Intake Review Screen | fictional fields only; not clinical intake |
| Reasoning Map Screen | visual guidance, not diagnostic proof |
| Missing Evidence Panel | missing evidence limits interpretation; it does not exclude disease |
| Mimic Visibility Panel | mimic visibility is a safety prompt, not diagnosis or exclusion |
| Overlap Panel | overlap remains unresolved; no winner selected |
| Source Status Panel | source status shows role and limitation; it does not grant authority |
| Confidence Limiter Panel | confidence limiter is not probability |
| Review Prompt Panel | review prompt is not order, procedure, follow-up, or triage |
| Red-Team Fail-Closed Screen | blocked unsafe example only; not reusable output |
| Safe Export Preview Screen | export preview is not clinical report |
| Authority Envelope Display | authority remains none |
| No-Decision Object Display | no clinical decision made |
| Audit Trace Screen | audit trace is not correctness proof |
| Visual Safety Label Display | visual is not diagnosis; diagram is not proof |

Screen copy rule:

> Screen copy must state the screen’s boundary before the user can infer clinical meaning.

---

## 12. Component-Level Copy Mapping

Every safety-critical component must map to required copy.

| Component | Required Copy Meaning |
|---|---|
| safety_banner | synthetic demo only; not for clinical use |
| case_card | fictional governance scenario |
| intake_field_table | fictional supplied/missing fields |
| missing_evidence_card | missing evidence is limiter, not exclusion |
| mimic_visibility_card | mimic visibility is safety prompt, not diagnosis |
| overlap_card | unresolved boundary; no winner |
| source_status_card | source limits claims; source does not grant authority |
| limitation_card | limitation is not probability |
| review_prompt_card | prompt is not recommendation or order |
| export_preview_section | preview is not clinical report |
| fail_closed_card | unsafe state blocked before reuse |
| authority_card | diagnostic/treatment/action authority none |
| no_decision_card | no diagnosis/treatment/order/follow-up/triage generated |
| audit_event_row | traceability only; not correctness proof |
| visual_safety_label | visual is not diagnosis/proof/probability/authority |

Component copy rule:

> Component copy must explain what the component cannot do.

---

## 13. Disabled Control Copy Mapping

Disabled controls must teach the boundary.

| Disabled Control | Required Copy |
|---|---|
| Upload real patient data | Real patient data is not allowed in this internal prototype. |
| Upload deidentified patient data | Deidentified real patient data is not allowed. |
| Import DICOM | DICOM import is not opened. |
| Import HRCT image | HRCT image import is not opened. |
| Paste real report | Real clinical report import is not opened. |
| Connect PACS | PACS integration is not opened. |
| Connect EHR | EHR integration is not opened. |
| Generate diagnosis | Diagnostic authority is none. |
| Rank diagnoses | Disease ranking and probability display are blocked. |
| Rule out disease | Disease exclusion authority is none. |
| Confirm mimic | Mimic confirmation is not allowed. |
| Exclude mimic | Mimic exclusion is not allowed. |
| Recommend treatment | Treatment authority is none. |
| Order test | Test-order authority is none. |
| Recommend procedure | Procedure decision authority is none. |
| Schedule follow-up | Follow-up authority is none. |
| Assign triage | Triage authority is none. |
| Generate patient summary | Patient-facing output is not allowed. |
| Mark clinically validated | Clinical validation is not opened. |
| Mark product ready | Product readiness is false. |
| Publish public demo | Public readiness is false. |
| Generate MDD consensus | MDD replacement is not allowed. |

Disabled control copy rule:

> Disabled control copy must teach governance, not advertise hidden clinical features.

---

## 14. Fail-Closed Copy Mapping

Fail-closed states must use source-governed copy.

Required fail-closed copy patterns:

```yaml
fail_closed_copy_patterns:
  unsafe_route_blocked:
    text: "This route is blocked because it would create clinical, patient-facing, validation, product-readiness, public-readiness, or MDD-replacement behavior."
  real_patient_data_blocked:
    text: "Real patient data is not allowed in this internal synthetic prototype."
  dicom_import_blocked:
    text: "DICOM import is not opened in this scaffold."
  report_import_blocked:
    text: "Real clinical report import is not opened in this scaffold."
  diagnosis_language_blocked:
    text: "Diagnostic language is blocked because diagnostic authority is none."
  exclusion_language_blocked:
    text: "Exclusion language is blocked because disease and mimic exclusion authority is none."
  action_language_blocked:
    text: "Clinical action language is blocked because treatment, ordering, procedure, follow-up, and triage authority are none."
  validation_overclaim_blocked:
    text: "Clinical validation language is blocked because clinical validation is not opened."
  readiness_overclaim_blocked:
    text: "Product/public readiness language is blocked because product_ready and public_ready are false."
```

Fail-closed copy rule:

> Fail-closed copy must explain the blocked authority, not merely say “error.”

---

## 15. Export Preview Copy Mapping

Safe export preview copy must prevent report interpretation.

Required export preview copy:

| Copy Meaning | Required Text |
|---|---|
| export boundary | Export preview is not a clinical report. |
| MDD boundary | MDD preparation preview is not MDD consensus. |
| diagnosis boundary | No diagnosis generated. |
| exclusion boundary | No disease or mimic excluded. |
| treatment boundary | No treatment selected. |
| order boundary | No tests ordered. |
| procedure boundary | No procedures decided. |
| follow-up boundary | No follow-up scheduled. |
| triage boundary | No triage assigned. |
| patient boundary | Patient-facing output is not generated. |
| validation boundary | Clinical validation is not opened. |
| audit boundary | Audit references explain UI state, not medical correctness. |

Blocked export preview copy:

- Impression,
- Diagnosis,
- Final diagnosis,
- Most likely diagnosis,
- Ruled out,
- Excluded,
- Recommended treatment,
- Order,
- Biopsy required,
- Follow-up in,
- Safe for outpatient,
- Patient summary,
- MDD consensus,
- Clinically validated,
- Product ready,
- Public ready.

Export preview copy rule:

> Export preview copy must keep the preview from becoming a report.

---

## 16. Red-Team Quarantine Copy Mapping

Red-team copy must quarantine unsafe examples.

Required red-team copy:

```yaml
red_team_quarantine_copy:
  blocked_example_label: "Blocked unsafe example — not reusable clinical output."
  unsafe_phrase_warning: "This phrase is displayed only to demonstrate fail-closed behavior."
  not_advice_warning: "This is not advice, diagnosis, exclusion, treatment, order, procedure decision, follow-up, triage, patient-facing material, clinical validation, or MDD consensus."
  copy_export_disabled_warning: "Copy and export are disabled for unsafe examples."
  red_team_validation_boundary: "Red-team fail-closed behavior demonstrates UI safety containment only. It does not validate clinical performance."
```

Blocked red-team copy:

- Example report,
- Suggested wording for clinical use,
- Use this instead,
- Clinically safe phrase,
- Validated safe output,
- Product-safe output,
- Public-ready output.

Red-team copy rule:

> Red-team copy must explain containment, not provide reusable language.

---

## 17. Visual Safety Copy Mapping

Visual safety copy must appear wherever visual meaning risk exists.

Required visual safety copy:

| Visual Risk | Required Copy |
|---|---|
| visual mistaken for diagnosis | Visual is not diagnosis. |
| diagram mistaken for proof | Diagram is not proof. |
| color mistaken for probability | Color is not probability. |
| icon mistaken for authority | Icon is not authority. |
| edge mistaken for likelihood | Edge is not likelihood. |
| flow mistaken for treatment pathway | Flow is not treatment pathway. |
| map mistaken for diagnosis | Reasoning map is visual guidance, not diagnostic proof. |
| audit flow mistaken for validation | Audit trace is not correctness proof. |

Visual copy rule:

> Visual safety copy must tell users how not to read the interface.

---

## 18. Authority Envelope Copy Mapping

Authority envelope copy must remain explicit.

Required authority copy:

```yaml
authority_envelope_copy:
  diagnostic_authority: "Diagnostic authority: none."
  treatment_authority: "Treatment authority: none."
  test_order_authority: "Test-order authority: none."
  procedure_decision_authority: "Procedure decision authority: none."
  follow_up_authority: "Follow-up authority: none."
  triage_authority: "Triage authority: none."
  patient_facing_use: "Patient-facing use: not allowed."
  public_ready: "Public ready: false."
  product_ready: "Product ready: false."
  clinical_validation: "Clinical validation: not opened."
  mdd_replacement: "MDD replacement: not allowed."
```

Authority copy rule:

> Authority copy must be plain, repeated, and impossible to confuse with permission.

---

## 19. No-Decision Object Copy Mapping

No-decision copy must remain explicit.

Required no-decision copy:

```yaml
no_decision_copy:
  diagnosis_made: "Diagnosis made: false."
  disease_excluded: "Disease excluded: false."
  mimic_excluded: "Mimic excluded: false."
  treatment_selected: "Treatment selected: false."
  test_ordered: "Test ordered: false."
  procedure_decided: "Procedure decided: false."
  follow_up_scheduled: "Follow-up scheduled: false."
  triage_assigned: "Triage assigned: false."
  mdd_consensus_generated: "MDD consensus generated: false."
  patient_facing_output_generated: "Patient-facing output generated: false."
```

No-decision copy rule:

> No-decision copy must name the decision not made.

---

## 20. Missing Evidence Copy Mapping

Missing evidence copy must block missing-as-negative interpretation.

Required missing evidence copy:

```yaml
missing_evidence_copy:
  primary: "Missing evidence limits interpretation; it does not exclude disease."
  exposure_missing: "Exposure history not provided; HP-related visibility cannot be closed by absence of information."
  prior_ct_missing: "Prior CT unavailable; stability or progression cannot be claimed."
  ctd_context_missing: "CTD/SARD context not provided; CTD-ILD visibility cannot be closed by absence of information."
  microbiology_missing: "Microbiology context not provided; infection visibility cannot be closed by absence of information."
  oncology_context_missing: "Oncology or therapy context not provided; malignancy or treatment-related mimic visibility cannot be closed by absence of information."
```

Blocked missing evidence copy:

- “negative,”
- “absent,”
- “not present,”
- “ruled out,”
- “excluded,”
- “no evidence of” when based on missingness.

Missing evidence copy rule:

> Missing evidence copy must preserve uncertainty.

---

## 21. Mimic Visibility Copy Mapping

Mimic visibility copy must block diagnosis/exclusion interpretation.

Required mimic copy:

```yaml
mimic_visibility_copy:
  primary: "Mimic visibility is a safety prompt, not a diagnosis or exclusion list."
  source_limited: "This mimic prompt is source-limited and non-authoritative."
  not_confirmed: "Visible does not mean confirmed."
  not_excluded: "Not emphasized does not mean excluded."
  review_visibility: "Human review visibility is preserved; no clinical decision is made."
```

Blocked mimic copy:

- confirmed mimic,
- excluded mimic,
- most likely mimic,
- mimic ruled out,
- mimic probability,
- mimic diagnosis.

Mimic copy rule:

> Mimic copy must keep risk visible without naming or dismissing disease.

---

## 22. Overlap Copy Mapping

Overlap copy must block winner-selection interpretation.

Required overlap copy:

```yaml
overlap_copy:
  primary: "Overlap remains unresolved; no winner is selected."
  boundary: "Boundary uncertainty is preserved for human review."
  no_collapse: "The platform does not collapse overlap into a single diagnosis."
  no_ranking: "The platform does not rank overlapping processes."
```

Blocked overlap copy:

- winner selected,
- primary diagnosis selected,
- secondary process excluded,
- final choice,
- dominant disease confirmed,
- resolved.

Overlap copy rule:

> Overlap copy must preserve unresolved coexistence.

---

## 23. Source Status Copy Mapping

Source status copy must block source-as-authority interpretation.

Required source status copy:

```yaml
source_status_copy:
  primary: "Source status shows role and limitation; it does not grant clinical authority."
  limitation: "Source-limited means claim strength is limited."
  no_confirmation: "Source status does not confirm diagnosis."
  no_validation: "Source status does not validate platform performance."
  no_action: "Source status does not authorize treatment, ordering, procedures, follow-up, or triage."
```

Blocked source copy:

- source confirms diagnosis,
- source proves correctness,
- source validates result,
- source authorizes action,
- source establishes probability.

Source copy rule:

> Source status copy must anchor limitation, not authority.

---

## 24. Confidence Limiter Copy Mapping

Confidence limiter copy must block probability interpretation.

Required confidence limiter copy:

```yaml
confidence_limiter_copy:
  primary: "Confidence limiter is not diagnostic probability."
  no_score: "No confidence score is generated."
  no_ranking: "No disease ranking is generated."
  no_performance: "No accuracy, sensitivity, specificity, or AUC is claimed."
  bounded_reasoning: "The limiter explains why interpretation remains bounded."
```

Blocked confidence copy:

- high confidence,
- low probability,
- likely,
- unlikely,
- accuracy,
- sensitivity,
- specificity,
- AUC,
- diagnostic confidence score.

Confidence copy rule:

> Confidence limiter copy explains limitation, not likelihood.

---

## 25. Review Prompt Copy Mapping

Review prompt copy must block action interpretation.

Required review prompt copy:

```yaml
review_prompt_copy:
  primary: "Review prompt visibility is not a clinical order or recommendation."
  mdd: "MDD preparation prompt is not MDD consensus."
  specialist: "Specialist review visibility does not replace specialist judgment."
  urgent: "Urgent review visibility does not assign triage or disposition."
  no_order: "No test is ordered."
  no_procedure: "No procedure is decided."
  no_follow_up: "No follow-up is scheduled."
```

Blocked review prompt copy:

- order required,
- biopsy required,
- follow-up due,
- safe outpatient,
- admit,
- triage level,
- management plan.

Review prompt copy rule:

> A review prompt may preserve visibility; it may not command action.

---

## 26. Audit Trace Copy Mapping

Audit trace copy must block correctness interpretation.

Required audit copy:

```yaml
audit_trace_copy:
  primary: "Audit trace explains UI state, not medical correctness."
  no_validation: "Audit trace is not clinical validation."
  no_performance: "Audit trace does not measure diagnostic performance."
  state_movement: "Audit events record prototype state movement."
  authority_none: "Audit events have authority effect none."
  decision_none: "Audit events have decision effect none."
```

Blocked audit copy:

- correctness proven,
- diagnosis validated,
- safe clinically,
- clinical validation passed,
- performance verified,
- expert equivalent.

Audit copy rule:

> Audit copy must preserve traceability without claiming truth.

---

## 27. Blocked Phrase Registry

The following phrase classes are blocked across safety-critical UI copy.

```yaml
blocked_phrase_registry:
  diagnosis:
    - "diagnosis"
    - "final diagnosis"
    - "diagnostic of"
    - "confirms"
    - "confirmed"
  ranking_probability:
    - "most likely"
    - "probability"
    - "likelihood"
    - "ranked"
    - "confidence score"
  exclusion:
    - "ruled out"
    - "excluded"
    - "no evidence of" 
    - "not present"
  treatment:
    - "treat with"
    - "start treatment"
    - "management plan"
    - "therapy should"
  ordering:
    - "order"
    - "next test"
    - "recommended test"
    - "must obtain"
  procedure:
    - "biopsy required"
    - "procedure indicated"
    - "perform"
  follow_up:
    - "follow-up in"
    - "repeat CT in"
    - "due for follow-up"
  triage:
    - "safe for outpatient"
    - "admit"
    - "disposition"
    - "triage"
  patient_facing:
    - "for the patient"
    - "patient summary"
    - "share with patient"
  validation:
    - "clinically validated"
    - "accuracy"
    - "sensitivity"
    - "specificity"
    - "AUC"
  readiness:
    - "product ready"
    - "public ready"
    - "deployment ready"
    - "safe for clinical use"
  mdd_replacement:
    - "MDD consensus"
    - "MDD complete"
    - "multidisciplinary final decision"
```

Blocked phrase rule:

> Blocked phrases may appear only inside quarantined red-team examples, never as usable UI copy.

---

## 28. Copy Repair Rules

Unsafe copy must trigger repair.

Allowed repair actions:

- replace clinical heading with governance heading,
- replace diagnosis phrase with visibility phrase,
- replace exclusion phrase with missingness/visibility limiter,
- replace treatment phrase with authority boundary,
- replace order phrase with no-order boundary,
- replace follow-up phrase with no-follow-up boundary,
- replace triage phrase with no-triage boundary,
- replace validation phrase with UI safety boundary,
- replace readiness phrase with public_ready/product_ready false boundary,
- restore authority envelope copy,
- restore no-decision copy.

Blocked repair meanings:

- clinical correction,
- diagnostic correction,
- treatment correction,
- probability recalculation,
- performance correction,
- clinical validation,
- product readiness approval.

Copy repair rule:

> Copy repair fixes unsafe UI language, not medical content.

---

## 29. Copy Validation Checklist

v0.16.3 copy validation passes only if all checks pass.

| Check ID | Check | Required State |
|---|---|---|
| COPY_CHECK_001 | UI copy registry schema defined | true |
| COPY_CHECK_002 | UI copy entry schema defined | true |
| COPY_CHECK_003 | allowed copy classes defined | true |
| COPY_CHECK_004 | blocked copy classes defined | true |
| COPY_CHECK_005 | core safety language registry defined | true |
| COPY_CHECK_006 | route-level copy mapping defined | true |
| COPY_CHECK_007 | screen-level copy mapping defined | true |
| COPY_CHECK_008 | component-level copy mapping defined | true |
| COPY_CHECK_009 | disabled control copy mapping defined | true |
| COPY_CHECK_010 | fail-closed copy mapping defined | true |
| COPY_CHECK_011 | export preview copy mapping defined | true |
| COPY_CHECK_012 | red-team quarantine copy mapping defined | true |
| COPY_CHECK_013 | visual safety copy mapping defined | true |
| COPY_CHECK_014 | authority envelope copy mapping defined | true |
| COPY_CHECK_015 | no-decision object copy mapping defined | true |
| COPY_CHECK_016 | missing evidence copy mapping defined | true |
| COPY_CHECK_017 | mimic visibility copy mapping defined | true |
| COPY_CHECK_018 | overlap copy mapping defined | true |
| COPY_CHECK_019 | source status copy mapping defined | true |
| COPY_CHECK_020 | confidence limiter copy mapping defined | true |
| COPY_CHECK_021 | review prompt copy mapping defined | true |
| COPY_CHECK_022 | audit trace copy mapping defined | true |
| COPY_CHECK_023 | blocked phrase registry defined | true |
| COPY_CHECK_024 | copy repair rules defined | true |
| COPY_CHECK_025 | all safety-critical copy requires source mapping | true |
| COPY_CHECK_026 | diagnostic/action/readiness copy blocked | true |
| COPY_CHECK_027 | red-team unsafe copy quarantined | true |
| COPY_CHECK_028 | real patient data remains blocked | true |
| COPY_CHECK_029 | clinical validation remains not_opened | true |
| COPY_CHECK_030 | public_ready and product_ready remain false | true |

Copy validation rule:

> Copy validation passes only if UI language cannot be mistaken for clinical output, validation, readiness, or patient-facing content.

---

## 30. v0.16.3 Acceptance Criteria

v0.16.3 may be considered complete only if all of the following are true.

| Criterion | Required State |
|---|---|
| source-governed UI copy registry defined | true |
| safety language IDs defined | true |
| route-level copy mapping defined | true |
| screen-level copy mapping defined | true |
| component-level copy mapping defined | true |
| disabled control copy mapping defined | true |
| fail-closed copy mapping defined | true |
| export preview copy mapping defined | true |
| red-team quarantine copy mapping defined | true |
| visual safety copy mapping defined | true |
| authority envelope copy mapping defined | true |
| no-decision object copy mapping defined | true |
| missing evidence copy mapping defined | true |
| mimic visibility copy mapping defined | true |
| overlap copy mapping defined | true |
| source status copy mapping defined | true |
| confidence limiter copy mapping defined | true |
| review prompt copy mapping defined | true |
| audit trace copy mapping defined | true |
| blocked copy phrases defined | true |
| copy repair rules defined | true |
| copy validation checklist defined | true |
| real patient data remains blocked | true |
| deidentified real patient data remains blocked | true |
| DICOM import remains blocked | true |
| HRCT import remains blocked | true |
| real report import remains blocked | true |
| PACS/EHR integration remains blocked | true |
| patient-facing use remains not_allowed | true |
| clinical validation remains not_opened | true |
| diagnostic performance claim remains not_allowed | true |
| product readiness remains false | true |
| public readiness remains false | true |
| diagnostic authority remains none | true |
| treatment authority remains none | true |
| order/procedure/follow-up/triage authority remains none | true |
| MDD replacement remains blocked | true |

v0.16.3 acceptance rule:

> The UI copy source mapping contract is accepted only if every safety-critical phrase remains source-governed, non-clinical, non-authoritative, non-patient-facing, non-validating, non-ready, and fail-closed.

---

## 31. Next Step

The next recommended step is:

- v0.16.4 — Fail-Closed State Stub / Disabled Clinical Control Plan

v0.16.4 should define:

- fail-closed state stub registry,
- disabled clinical control registry,
- unsafe route attempt stub,
- real patient data attempt stub,
- DICOM/report import attempt stub,
- diagnosis/action attempt stub,
- patient-facing leak attempt stub,
- validation/readiness overclaim attempt stub,
- unsafe copy/export attempt stub,
- authority envelope missing stub,
- no-decision object missing stub,
- disabled control explanation requirements,
- fail-closed audit event binding,
- repair-required and UI safety revalidation stub behavior.

v0.16.4 must not open clinical deployment, real patient data, deidentified real patient data, DICOM/report import, PACS/EHR integration, public readiness, product readiness, patient-facing use, clinical validation, diagnostic authority, treatment authority, test ordering, procedure decision, follow-up scheduling, triage, or MDD replacement.

---

## 32. Governance Statement

This document defines source-governed UI copy mapping and safety language constraints.

It opens safety language scaffold planning only.

It does not implement a clinical product.

It does not diagnose.  
It does not treat.  
It does not validate clinical performance.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import HRCT images.  
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not replace clinicians, radiologists, pathologists, pulmonologists, rheumatologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The current project principle is:

> “It teaches clinicians to read change before naming disease.”

The v0.16.3 governance discipline is:

> “Do not let UI copy become clinical language.”

The safety language discipline is:

> “Every safety-critical UI phrase must trace to a sealed contract before it can appear in the internal prototype scaffold.”