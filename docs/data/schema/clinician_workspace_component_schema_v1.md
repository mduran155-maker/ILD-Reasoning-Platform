# ILD Reasoning Platform — Clinician Workspace Component Schema v1

Version: v0.10.1  
Status: clinician_workspace_component_schema  
Scope: Detailed schema for clinician review workspace UI components  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the detailed component schema for v0.10 — Clinician Review Workspace / Interactive Reasoning UI Contract.

It follows:

- `docs/navigation/clinician_review_workspace_entry_gate_v1.md`
- `docs/navigation/reasoning_output_contract_structural_seal_v1.md`
- `docs/data/schema/structured_output_layer_schema_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_9.md`
- `docs/navigation/high_risk_mimic_structural_seal_v1.md`

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

Its purpose is to define the fields, states, interactions, blocked states, and authority guards for each clinician workspace component.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.1:

> “Every workspace component must have a schema before it can become interactive.”

---

## 2. Global Workspace Contract

Every workspace component must preserve:

| Field | Required State |
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

No component may override the authority envelope.

No component may convert clinician interaction into platform authority.

No component may present itself as a diagnostic, treatment, ordering, procedure, follow-up, or patient-facing interface.

---

## 3. Component Registry

The following components are governed in v0.10.1.

| Component ID | Component Name | Required |
|---|---|---|
| V10_COMPONENT_001 | reasoning_flow_layout | yes |
| V10_COMPONENT_002 | layer_cards | yes |
| V10_COMPONENT_003 | source_status_badges | yes |
| V10_COMPONENT_004 | missing_evidence_panel | yes |
| V10_COMPONENT_005 | mimic_visibility_panel | yes |
| V10_COMPONENT_006 | temporal_comparison_panel | yes |
| V10_COMPONENT_007 | overlap_panel | yes |
| V10_COMPONENT_008 | uncertainty_panel | yes |
| V10_COMPONENT_009 | urgent_review_banner | yes where relevant |
| V10_COMPONENT_010 | MDD_review_panel | yes where relevant |
| V10_COMPONENT_011 | blocked_output_guardrails | yes |
| V10_COMPONENT_012 | authority_envelope_footer | always yes |
| V10_COMPONENT_013 | audit_trail | yes |

---

## 4. Global Component State Types

The following state types may be used across workspace components.

| State Type | Meaning |
|---|---|
| visible | Component is shown |
| collapsed | Component is hidden but available |
| expanded | Component is open |
| required_visible | Component must be visible |
| locked_visible | Component cannot be hidden |
| not_triggered | Component not triggered by available input |
| source_limited | Component displays source limitation |
| prompt_visible | Reasoning prompt remains visible |
| missing_evidence_visible | Missing evidence remains visible |
| urgent_prompt_visible | Urgent review prompt visible |
| review_prompt_visible | MDD or specialist review prompt visible |
| authority_block_active | Authority guard is active |
| export_safe | Component can be exported only with authority envelope |
| audit_recorded | Component event is recorded in audit trail |

---

## 5. Global Blocked Component States

No component may enter the following states.

| Blocked State | Reason |
|---|---|
| diagnosis_confirmed | diagnostic authority leak |
| disease_excluded | exclusion authority leak |
| treatment_recommended | treatment authority leak |
| test_order_recommended | test-order authority leak |
| procedure_recommended | procedure authority leak |
| follow_up_interval_set | management authority leak |
| triage_decision_made | triage authority leak |
| MDD_replaced | review replacement |
| urgent_review_replaced | urgent review replacement |
| public_ready_enabled | public readiness leak |
| patient_facing_enabled | patient-facing use leak |
| platform_wide_clinically_reviewed_true | unsupported clinical review claim |

---

## 6. Component Schema: reasoning_flow_layout

### 6.1 Purpose

The `reasoning_flow_layout` component displays the four-phase Case Reasoning Flow from v0.9.

It must organize reasoning without presenting a final diagnosis-first interface.

### 6.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_001 |
| component_name | yes | reasoning_flow_layout |
| phase_order | yes | Grounding; Reasoning Core; Safety Net; Escalation and Governance |
| default_view | yes | four_phase_overview |
| diagnosis_first_layout | yes | false |
| safety_net_visible | yes | true |
| governance_visible | yes | true |
| authority_footer_visible | yes | true |
| audit_enabled | yes | true |

### 6.3 Allowed Interactions

- expand phase,
- collapse phase,
- inspect phase summary,
- navigate to layer cards,
- view safety and governance sections,
- copy governance-safe phase summary.

### 6.4 Blocked Interactions

- select final diagnosis,
- mark phase as diagnosis complete,
- hide Safety Net permanently,
- hide Escalation and Governance permanently,
- export diagnosis-first summary,
- create patient-facing summary.

### 6.5 Required UI Labels

Allowed labels:

- Grounding
- Reasoning Core
- Safety Net
- Escalation and Governance
- Reasoning Flow
- Review Workspace

Blocked labels:

- Final Diagnosis
- Most Likely Diagnosis
- Treatment Plan
- Patient Summary
- Public Report

### 6.6 Pass Condition

The workspace opens as reasoning flow, not as final diagnostic report.

### 6.7 Failure Condition

The first screen centers final diagnosis, treatment, test ordering, procedure decision, or patient-facing output.

---

## 7. Component Schema: layer_cards

### 7.1 Purpose

The `layer_cards` component displays the 13 structured output layers sealed in v0.9.

Each card must remain a reasoning visibility card, not a clinical authority card.

### 7.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_002 |
| component_name | yes | layer_cards |
| layer_id | yes | V09_LAYER_001 through V09_LAYER_013 |
| layer_name | yes | string |
| layer_phase | yes | Grounding / Reasoning Core / Safety Net / Escalation and Governance |
| card_state | yes | visible / collapsed / expanded |
| source_status_attachment | yes | present / not_applicable |
| missing_evidence_attachment | yes where relevant | present |
| authority_guard | yes | active |
| diagnosis_created | yes | false |
| treatment_created | yes | false |
| export_allowed | yes | export_safe_only |

### 7.3 Required Layer Coverage

Layer cards must support:

- case_context_summary,
- temporal_change_summary,
- pattern_family_prompts,
- differential_prompt_layer,
- overlap_layer,
- high_risk_mimic_layer,
- missing_evidence_layer,
- uncertainty_layer,
- urgent_review_prompt_layer,
- MDD_review_prompt_layer,
- source_status_layer,
- authority_envelope,
- blocked_outputs.

### 7.4 Allowed Interactions

- expand card,
- collapse card,
- inspect supporting features,
- inspect weakening features,
- inspect missing evidence,
- inspect source status,
- inspect confidence limiters,
- copy non-authoritative card summary,
- add clinician note linked to card.

### 7.5 Blocked Interactions

- mark card as diagnosis confirmed,
- mark disease as excluded,
- convert pattern card into diagnosis,
- convert mimic card into diagnosis,
- convert missing evidence card into exclusion,
- convert MDD card into MDD replacement,
- convert urgent card into triage decision.

### 7.6 Required UI Labels

Allowed labels:

- Pattern Prompt
- Differential Prompt
- Mimic Visibility
- Missing Evidence
- Uncertainty
- Review Prompt
- Source Status
- Authority Envelope

Blocked labels:

- Confirmed Diagnosis
- Ruled Out
- Treatment Needed
- Order Test
- Biopsy Required
- Follow-Up Plan

### 7.7 Pass Condition

Each card displays reasoning without creating clinical authority.

### 7.8 Failure Condition

Any card title, state, button, badge, or export implies diagnosis, exclusion, treatment, ordering, procedure decision, or follow-up.

---

## 8. Component Schema: source_status_badges

### 8.1 Purpose

The `source_status_badges` component displays source role, claim mapping, and source limitation.

A source badge must not become a clinical validation badge.

### 8.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_003 |
| component_name | yes | source_status_badges |
| source_id | yes | string |
| source_role_class | yes | approved role class |
| claim_mapping_status | yes | approved mapping status |
| source_limitation | yes | list |
| narrow_reviewed_scope | optional | limited_metadata_only |
| platform_wide_clinically_reviewed | yes | false |
| diagnostic_authority_created | yes | false |
| treatment_authority_created | yes | false |

### 8.3 Allowed Badge Types

Source role badges:

- primary_high_authority
- primary_limited_scope
- auxiliary_review
- diagnostic_performance_study
- case_example_cautionary
- internal_governance

Claim mapping badges:

- claim_mapped
- partially_mapped
- source_limited
- treatment_heavy_limited
- diagnostic_performance_limited
- cautionary_case_only
- internal_governance_only
- not_mapped

Clinical review badges:

- narrow_reviewed_scope
- platform_wide_review_false

### 8.4 Blocked Badge Types

- diagnosis_confirmed
- disease_excluded
- clinically_validated
- public_ready
- patient_ready
- treatment_recommended
- test_order_supported
- biopsy_required
- follow_up_plan_supported

### 8.5 Allowed Interactions

- hover for source limitation,
- click to inspect source role,
- click to inspect claim mapping,
- click to inspect why source does not create authority,
- filter by source role,
- filter by source limitation.

### 8.6 Blocked Interactions

- click source badge to confirm diagnosis,
- click source badge to recommend treatment,
- click source badge to order test,
- click source badge to bypass MDD,
- hide source limitations permanently.

### 8.7 Required Badge Statement

Every source badge group must preserve:

> Source status supports reasoning visibility, not diagnosis or treatment authority.

### 8.8 Pass Condition

Source badges increase transparency without implying clinical validation.

### 8.9 Failure Condition

A source badge implies clinical validation, diagnostic confirmation, treatment support, or public readiness.

---

## 9. Component Schema: missing_evidence_panel

### 9.1 Purpose

The `missing_evidence_panel` displays missing or incomplete evidence and links it to affected reasoning prompts.

Missing evidence must not become exclusion.

### 9.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_004 |
| component_name | yes | missing_evidence_panel |
| missing_item_id | yes | string |
| missing_item_label | yes | string |
| affected_prompts | yes | list |
| severity_for_reasoning | optional | high / moderate / low / unclear |
| exclusion_effect | yes | none |
| user_can_supply_evidence | yes | true |
| evidence_update_audit | yes | required |
| auto_fill_allowed | yes | false |

### 9.3 Allowed Missing Evidence Items

- prior_CT
- exposure_history
- occupational_history
- beryllium_exposure_context
- medication_history
- therapy_history
- radiation_history
- checkpoint_inhibitor_exposure
- autoimmune_context
- serology_context
- expiratory_HRCT
- BAL_context
- microbiology
- AFB_culture_NAAT_context
- fungal_testing_context
- pathology_context
- malignancy_status
- PET_CT_context
- aspiration_risk
- urgent_clinical_status
- MDD_status

### 9.4 Allowed Interactions

- view missing item,
- inspect affected prompts,
- mark evidence as supplied by clinician,
- attach clinician note,
- rerun reasoning visibility after new evidence is supplied,
- export missing evidence checklist.

### 9.5 Blocked Interactions

- mark missing evidence as exclusion,
- auto-fill missing evidence,
- infer missing exposure from imaging,
- infer missing CTD/SARD context,
- infer missing microbiology,
- infer missing malignancy status,
- hide critical missing evidence permanently.

### 9.6 Required UI Statement

> Missing evidence limits interpretation and does not exclude a mimic or disease family.

### 9.7 Pass Condition

Missing evidence remains visible and linked to prompts until explicitly supplied.

### 9.8 Failure Condition

Missing evidence is treated as negative evidence or exclusion.

---

## 10. Component Schema: mimic_visibility_panel

### 10.1 Purpose

The `mimic_visibility_panel` displays high-risk mimics and the reasons they remain visible.

It must prevent mimic erasure and mimic overdiagnosis.

### 10.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_005 |
| component_name | yes | mimic_visibility_panel |
| mimic_prompt_id | yes | string |
| mimic_family | yes | allowed mimic family |
| visibility_status | yes | prompt_visible / not_triggered / source_limited |
| supporting_features | yes | list |
| weakening_features | yes | list |
| missing_evidence | yes | list |
| source_status_refs | yes | list |
| diagnosis_status | yes | not_diagnosed |
| exclusion_status | yes | not_excluded |
| treatment_status | yes | not_recommended |

### 10.3 Allowed Mimic Families

- infection_mimic
- TB_mimic
- NTM_mimic
- fungal_mimic
- aspiration_mimic
- occupational_ILD_mimic
- beryllium_sarcoid_mimic
- drug_induced_ILD_mimic
- radiation_pneumonitis_mimic
- checkpoint_inhibitor_pneumonitis_mimic
- ICI_sarcoid_like_reaction_mimic
- PLC_malignancy_mimic
- lymphoma_recurrence_mimic
- sarcoid_like_reaction_mimic
- acute_danger_overlay

### 10.4 Allowed Interactions

- expand mimic family,
- inspect why visible,
- inspect missing evidence,
- inspect source limitation,
- inspect overlap with other prompts,
- export mimic visibility summary,
- add clinician note.

### 10.5 Blocked Interactions

- confirm mimic,
- exclude mimic,
- recommend treatment for mimic,
- order test for mimic,
- recommend biopsy for mimic,
- recommend oncology or radiation management,
- hide high-risk mimic in high-risk context.

### 10.6 Required UI Statement

> Mimic visibility is not mimic diagnosis or exclusion.

### 10.7 Pass Condition

Mimics remain visible with reasons, limitations, and non-authority statements.

### 10.8 Failure Condition

A mimic is confirmed, excluded, or used to generate treatment or test-order advice.

---

## 11. Component Schema: temporal_comparison_panel

### 11.1 Purpose

The `temporal_comparison_panel` displays change, stability, or comparison limitations before disease naming.

### 11.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_006 |
| component_name | yes | temporal_comparison_panel |
| prior_comparison_available | yes | true / false / unclear |
| comparison_timepoint | yes | date / interval / not_provided |
| change_direction | yes | new / increased / decreased / stable / mixed / unclear / not_assessable |
| acute_vs_chronic_context | yes | acute_overlay_possible / chronic_background / mixed / unclear |
| temporal_limiters | yes | list |
| narrow_reviewed_scope | optional | temporal_comparison_methodology |
| diagnosis_created | yes | false |

### 11.3 Allowed Interactions

- inspect prior comparison status,
- view temporal limiters,
- view acute vs chronic uncertainty,
- add clinician-supplied prior imaging context,
- rerun temporal visibility after comparison data supplied.

### 11.4 Blocked Interactions

- diagnose progression,
- diagnose PPF,
- diagnose acute exacerbation,
- infer stability without prior comparison,
- infer benignity from stability,
- hide missing prior CT.

### 11.5 Required UI Statement

> Temporal comparison shows change and limitation; it does not establish diagnosis.

### 11.6 Pass Condition

Change is displayed without diagnostic closure.

### 11.7 Failure Condition

Temporal change is converted into PPF, acute exacerbation, progression diagnosis, or stability-based reassurance.

---

## 12. Component Schema: overlap_panel

### 12.1 Purpose

The `overlap_panel` displays coexistence and unresolved boundaries.

It must prevent forced single-label closure.

### 12.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_007 |
| component_name | yes | overlap_panel |
| overlap_state_id | yes | string |
| involved_prompts | yes | list |
| overlap_status | yes | unresolved / visible / source_limited |
| hidden_process_guard | yes | active |
| source_status_refs | yes | list |
| closure_status | yes | not_established |

### 12.3 Allowed Overlap States

- UIP_vs_HP_overlap
- UIP_vs_CTD_ILD_overlap
- HP_vs_CTD_ILD_overlap
- CTD_ILD_vs_NSIP_overlap
- NSIP_vs_OP_overlap
- OP_vs_infection_overlap
- OP_vs_aspiration_overlap
- sarcoidosis_vs_infection_overlap
- sarcoidosis_vs_beryllium_overlap
- sarcoidosis_vs_malignancy_overlap
- drug_induced_ILD_vs_NSIP_OP_overlap
- radiation_pneumonitis_vs_infection_recurrence_overlap
- CIP_vs_infection_progression_overlap
- PLC_vs_ILD_infection_edema_overlap
- acute_overlay_vs_chronic_fibrosis_overlap

### 12.4 Allowed Interactions

- expand overlap state,
- inspect involved prompts,
- inspect missing evidence affecting overlap,
- inspect source status,
- add clinician note,
- export overlap summary.

### 12.5 Blocked Interactions

- select single winner,
- hide secondary process,
- hide acute overlay,
- hide mimic,
- convert overlap into final diagnosis.

### 12.6 Required UI Statement

> Overlap is displayed as coexistence, not forced closure.

### 12.7 Pass Condition

Coexisting processes remain visible without final label selection.

### 12.8 Failure Condition

UI interaction forces a single winning diagnosis or hides competing processes.

---

## 13. Component Schema: uncertainty_panel

### 13.1 Purpose

The `uncertainty_panel` displays unresolved questions and confidence limiters.

It must not display diagnostic confidence scores.

### 13.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_008 |
| component_name | yes | uncertainty_panel |
| unresolved_questions | yes | list |
| confidence_limiter | yes | list |
| diagnostic_confidence | yes | not_allowed |
| numeric_probability | yes | not_allowed |
| closure_status | yes | not_established |
| source_uncertainty | yes | list |
| review_needed | yes | yes / no / unclear |

### 13.3 Allowed Confidence Limiters

- prior_CT_unavailable
- exposure_history_incomplete
- occupational_history_incomplete
- expiratory_HRCT_unavailable
- microbiology_not_integrated
- autoimmune_context_incomplete
- medication_history_incomplete
- radiation_history_incomplete
- ICI_history_incomplete
- malignancy_status_incomplete
- pathology_context_missing
- MDD_not_documented
- source_limitation_present

### 13.4 Allowed Interactions

- inspect unresolved questions,
- inspect confidence limiters,
- inspect source uncertainty,
- add clinician-supplied evidence,
- export uncertainty summary.

### 13.5 Blocked Interactions

- assign diagnostic confidence,
- assign disease probability,
- rank final diagnosis,
- close uncertainty,
- mark diagnosis as established.

### 13.6 Required UI Statement

> The workspace shows what limits interpretation, not what diagnosis it owns.

### 13.7 Pass Condition

Uncertainty is visible as structured information.

### 13.8 Failure Condition

The panel displays confidence scores, disease probabilities, final rankings, or diagnostic closure.

---

## 14. Component Schema: urgent_review_banner

### 14.1 Purpose

The `urgent_review_banner` displays urgent review prompts where clinical danger may exist.

It must not triage, diagnose, treat, or assign disposition.

### 14.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_009 |
| component_name | yes | urgent_review_banner |
| banner_visible | yes | true / false / unclear |
| trigger_list | yes_if_visible | list |
| display_priority | yes | highest_when_active |
| triage_authority | yes | none |
| diagnosis_authority | yes | none |
| treatment_authority | yes | none |
| dismissible | yes | no_if_active_high_risk |
| audit_recorded | yes | true |

### 14.3 Allowed Triggers

- acute_hypoxemia
- rapid_dyspnea_progression
- fever_or_systemic_illness
- hemoptysis_or_anemia
- vascular_concern
- severe_infection_possible
- immunosuppression_with_new_findings
- known_malignancy_with_new_findings
- post_radiation_new_opacity
- ICI_exposure_with_new_pulmonary_findings
- severe_or_worsening_respiratory_status

### 14.4 Allowed Interactions

- inspect why urgent prompt is visible,
- inspect missing urgent clinical data,
- add clinician note,
- mark additional clinical context as supplied,
- audit banner visibility.

### 14.5 Blocked Interactions

- triage patient,
- recommend emergency disposition,
- recommend outpatient management,
- start treatment,
- diagnose acute exacerbation,
- declare no urgent review needed when danger data are incomplete,
- permanently dismiss active high-risk banner.

### 14.6 Required UI Statement

> Urgent review prompt is safety visibility, not triage authority.

### 14.7 Pass Condition

Urgent review is visually prioritized without creating triage or treatment authority.

### 14.8 Failure Condition

The banner gives disposition, treatment, reassurance, or diagnostic closure.

---

## 15. Component Schema: MDD_review_panel

### 15.1 Purpose

The `MDD_review_panel` displays multidisciplinary or specialist review prompts.

It must not replace MDD or specialist judgment.

### 15.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_010 |
| component_name | yes | MDD_review_panel |
| MDD_prompt_visible | yes | true / false / unclear |
| specialist_review_prompts | yes | list |
| review_reason | yes_if_visible | list |
| review_not_replaced_statement | yes | true |
| source_status_refs | optional | list |
| diagnosis_created | yes | false |

### 15.3 Allowed Specialist Review Prompts

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

### 15.4 Allowed Interactions

- inspect review reason,
- inspect specialist domains,
- export MDD preparation draft,
- add clinician note,
- record that clinician reviewed the prompt.

### 15.5 Blocked Interactions

- declare MDD unnecessary,
- replace MDD with platform conclusion,
- generate final diagnosis,
- generate treatment plan,
- generate single-specialty closure when cross-domain uncertainty persists.

### 15.6 Required UI Statement

> MDD / specialist review visibility is not MDD replacement.

### 15.7 Pass Condition

Review prompts support safer discussion without replacing review.

### 15.8 Failure Condition

The panel functions as an autonomous MDD or final decision surface.

---

## 16. Component Schema: blocked_output_guardrails

### 16.1 Purpose

The `blocked_output_guardrails` component prevents unsafe requests and unsafe output states.

It must block both explicit and disguised authority leaks.

### 16.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_011 |
| component_name | yes | blocked_output_guardrails |
| guardrail_active | yes | true |
| blocked_request_type | yes | diagnosis / exclusion / treatment / test_order / procedure / follow_up / public_ready / patient_facing / clinical_review |
| intercept_message | yes | safe_reframe |
| authority_envelope_required | yes | true |
| audit_recorded | yes | true |
| hidden_advice_check | yes | active |

### 16.3 Blocked Request Types

- diagnosis request,
- exclusion request,
- treatment request,
- test order request,
- procedure decision request,
- follow-up interval request,
- public-ready export request,
- patient-facing summary request,
- platform-wide clinical review claim request,
- urgent review replacement request,
- MDD replacement request.

### 16.4 Required Reframe Protocol

When blocked request is detected:

1. refuse closure,
2. reframe into prompt visibility,
3. show missing evidence,
4. preserve mimics and competing families,
5. show review prompt where relevant,
6. show authority envelope,
7. record audit event.

### 16.5 Allowed Interactions

- view why request is blocked,
- view safe alternative output,
- copy non-authoritative reframe,
- audit guardrail trigger.

### 16.6 Blocked Interactions

- override guardrail,
- bypass with softer wording,
- produce hidden advice,
- produce action-oriented recommendation,
- export blocked output.

### 16.7 Required UI Statement

> The platform can show reasoning prompts and limitations, but it cannot provide diagnosis, treatment, test ordering, procedure decisions, or follow-up scheduling.

### 16.8 Pass Condition

Blocked requests are intercepted and reframed safely.

### 16.9 Failure Condition

The UI answers a blocked request directly or disguises advice as reasoning.

---

## 17. Component Schema: authority_envelope_footer

### 17.1 Purpose

The `authority_envelope_footer` keeps authority limits always visible.

It must not be permanently hidden or changed through interaction.

### 17.2 Required Fields

| Field | Required | Required Value |
|---|---|---|
| component_id | yes | V10_COMPONENT_012 |
| component_name | yes | authority_envelope_footer |
| diagnostic_authority | yes | none |
| treatment_authority | yes | none |
| public_ready | yes | false |
| clinically_reviewed.platform_wide | yes | false |
| patient_facing_use | yes | not_allowed |
| automated_diagnosis | yes | not_allowed |
| automated_exclusion | yes | not_allowed |
| automated_treatment_selection | yes | not_allowed |
| automated_test_order | yes | not_allowed |
| automated_procedure_decision | yes | not_allowed |
| automated_follow_up_schedule | yes | not_allowed |
| footer_visibility | yes | locked_visible |

### 17.3 Optional Narrow Scope Display

Allowed:

```yaml
narrow_reviewed_scopes:
  - temporal_comparison_methodology
  - ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping
```

Required interpretation:

- narrow scope is metadata,
- platform-wide clinical review remains false,
- no diagnostic or treatment authority is created.

### 17.4 Allowed Interactions

- expand authority details,
- inspect blocked authority categories,
- inspect narrow reviewed scope explanation,
- copy authority envelope.

### 17.5 Blocked Interactions

- hide footer permanently,
- change authority values,
- mark public_ready true,
- mark platform_wide clinically reviewed true,
- enable patient-facing mode,
- override authority envelope.

### 17.6 Required UI Statement

> Authority limits remain active across all workspace interactions.

### 17.7 Pass Condition

Authority envelope remains always visible and immutable.

### 17.8 Failure Condition

Authority limits are hidden, editable, or bypassed.

---

## 18. Component Schema: audit_trail

### 18.1 Purpose

The `audit_trail` records reasoning visibility events and guardrail events.

It must not become clinical validation.

### 18.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| component_id | yes | V10_COMPONENT_013 |
| component_name | yes | audit_trail |
| event_id | yes | string |
| event_type | yes | allowed event type |
| timestamp | optional | implementation_defined |
| actor | yes | platform / clinician / system |
| event_payload | yes | structured summary |
| authority_effect | yes | none |
| diagnosis_created | yes | false |
| treatment_created | yes | false |
| clinical_validation_created | yes | false |

### 18.3 Allowed Event Types

- layer_expanded,
- layer_collapsed,
- source_badge_viewed,
- missing_evidence_viewed,
- evidence_supplied_by_clinician,
- mimic_prompt_viewed,
- overlap_state_viewed,
- confidence_limiter_viewed,
- urgent_banner_shown,
- MDD_prompt_viewed,
- guardrail_triggered,
- authority_envelope_viewed,
- governance_safe_export_created,
- clinician_note_added.

### 18.4 Blocked Event Types

- diagnosis_confirmed,
- disease_excluded,
- treatment_recommended,
- test_ordered,
- procedure_recommended,
- follow_up_scheduled,
- MDD_replaced,
- urgent_review_replaced,
- public_ready_enabled,
- patient_summary_generated,
- clinical_validation_confirmed.

### 18.5 Allowed Interactions

- inspect audit event,
- export governance-safe audit trail,
- distinguish platform event from clinician-authored note,
- inspect guardrail trigger history.

### 18.6 Blocked Interactions

- use audit trail as diagnosis,
- use audit trail as clinical validation,
- use audit trail as treatment authorization,
- use audit trail as MDD replacement,
- edit audit event to create authority.

### 18.7 Required UI Statement

> Audit trail records reasoning visibility; it does not validate clinical correctness.

### 18.8 Pass Condition

Audit trail documents visibility and guardrails without clinical validation.

### 18.9 Failure Condition

Audit trail is used to imply diagnosis, correctness, treatment, or deployment readiness.

---

## 19. Clinician Notes Schema

### 19.1 Purpose

Clinician notes may exist only as clinician-authored content separate from platform reasoning.

### 19.2 Required Fields

| Field | Required | Allowed Values |
|---|---|---|
| note_id | yes | string |
| note_author | yes | clinician |
| note_type | yes | clinician_authored_note |
| linked_component | optional | component_id |
| platform_generated | yes | false |
| source_reviewed_by_platform | yes | false |
| creates_platform_authority | yes | false |
| audit_recorded | yes | true |

### 19.3 Allowed Note Labels

- clinician_authored_note
- clinician_supplied_evidence
- clinician_review_comment
- MDD_preparation_note
- local_workflow_note

### 19.4 Blocked Note Effects

- platform diagnosis,
- platform treatment,
- platform exclusion,
- platform clinical review,
- public readiness,
- patient-facing advice.

### 19.5 Required Rule

> Clinician-authored notes are not platform conclusions.

---

## 20. Safe Export Schema

### 20.1 Purpose

Safe export may produce governance-safe summaries only.

### 20.2 Allowed Export Types

- governance_safe_structured_reasoning_draft
- source_status_summary
- missing_evidence_checklist
- mimic_visibility_summary
- MDD_preparation_draft
- prompt_visibility_audit_trail
- authority_envelope_export

### 20.3 Blocked Export Types

- final_diagnostic_report
- treatment_recommendation_report
- patient_facing_report
- test_order_recommendation
- procedure_recommendation
- follow_up_schedule
- public_ready_output
- clinically_validated_output

### 20.4 Required Export Fields

| Field | Required |
|---|---|
| export_type | yes |
| authority_envelope | yes |
| source_status_summary | yes |
| missing_evidence_summary | yes where relevant |
| mimic_visibility_summary | yes where relevant |
| blocked_output_notice | yes |
| patient_facing_use | not_allowed |

### 20.5 Required Rule

> Exported content must preserve the authority envelope.

---

## 21. Component Dependency Matrix

| Component | Depends On | Feeds |
|---|---|---|
| reasoning_flow_layout | v0.9 output contract | all components |
| layer_cards | structured output layer schema | source_status_badges; audit_trail |
| source_status_badges | source governance docs | layer_cards; source_status_layer; audit_trail |
| missing_evidence_panel | missing_evidence_layer | uncertainty_panel; MDD_review_panel; audit_trail |
| mimic_visibility_panel | high_risk_mimic_layer | urgent_review_banner; overlap_panel; audit_trail |
| temporal_comparison_panel | temporal_change_summary | reasoning_flow_layout; uncertainty_panel |
| overlap_panel | overlap_layer | uncertainty_panel; MDD_review_panel |
| uncertainty_panel | uncertainty_layer | MDD_review_panel; authority_envelope_footer |
| urgent_review_banner | urgent_review_prompt_layer | authority_envelope_footer; audit_trail |
| MDD_review_panel | MDD_review_prompt_layer | audit_trail |
| blocked_output_guardrails | blocked_outputs layer | authority_envelope_footer; audit_trail |
| authority_envelope_footer | authority_envelope layer | all components |
| audit_trail | all component events | governance-safe export |

---

## 22. Workspace Display Priority

When components compete for attention, display priority is:

1. urgent_review_banner,
2. mimic_visibility_panel,
3. missing_evidence_panel,
4. source_status_badges,
5. uncertainty_panel,
6. overlap_panel,
7. temporal_comparison_panel,
8. reasoning_flow_layout,
9. layer_cards,
10. MDD_review_panel,
11. authority_envelope_footer,
12. blocked_output_guardrails,
13. audit_trail.

Priority rule:

> Safety, mimics, missing evidence, source limits, and uncertainty must not be visually buried.

---

## 23. Component Acceptance Criteria

v0.10.1 is accepted only if:

- all 13 workspace components have schemas,
- each component has purpose,
- each component has required fields,
- each component has allowed interactions,
- each component has blocked interactions,
- each component has authority guardrails,
- source badges are constrained,
- missing evidence cannot become exclusion,
- mimic visibility cannot become diagnosis,
- temporal comparison cannot become diagnosis,
- overlap cannot become forced closure,
- uncertainty uses confidence limiters,
- urgent review banner has no triage authority,
- MDD panel has no replacement authority,
- blocked output guardrails are active,
- authority footer is always visible,
- audit trail does not become validation,
- clinician notes are separated from platform reasoning,
- safe export preserves authority envelope,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false,
- patient_facing_use remains not_allowed.

---

## 24. Next Step

The next recommended step is:

- v0.10.2 — Workspace Interaction Rules / Allowed-Blocked Interaction Map

v0.10.2 should define:

- allowed user interactions,
- blocked user interactions,
- guardrail response behavior,
- state transitions,
- safe update after clinician supplies evidence,
- unsafe click/selection patterns,
- export restrictions,
- clinician note boundaries,
- audit event behavior.

v0.10.2 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, public readiness, patient-facing use, or platform-wide clinical review.

---

## 25. Governance Statement

This component schema defines clinician workspace UI components.

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

The workspace remains a reasoning visibility surface, not a decision surface.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.10 rule remains:

> “Interactive review may organize reasoning, but interaction must not become diagnosis, treatment, test ordering, procedure decision, or deployment authority.”

For v0.10.1:

> “Every workspace component must have a schema before it can become interactive.”