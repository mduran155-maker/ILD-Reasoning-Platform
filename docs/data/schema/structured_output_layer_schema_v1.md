# ILD Reasoning Platform — Structured Output Layer Schema v1

Version: v0.9.1  
Status: structured_output_layer_schema  
Scope: Detailed schema for clinician-facing reasoning output layers  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the detailed structured output layer schema for v0.9.

It follows:

- `docs/navigation/reasoning_output_contract_entry_gate_v1.md`
- `docs/navigation/high_risk_mimic_structural_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_8.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_7.md`

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

Its purpose is to define the required fields, allowed values, blocked values, dependencies, and display order for each structured output layer.

The v0.9 rule remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

For v0.9.1:

> “Every reasoning layer must have a schema before it can be displayed.”

---

## 2. Global Output Contract

Every structured reasoning output must preserve:

| Field | Required Value |
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

Every output must show:

- what was provided,
- what changed,
- which pattern prompts are visible,
- which differential prompts remain visible,
- which overlaps remain unresolved,
- which high-risk mimics remain visible,
- which evidence is missing,
- what limits interpretation,
- whether urgent review is relevant,
- whether MDD or specialist review is relevant,
- which sources support prompt visibility,
- which outputs are blocked,
- the authority envelope.

---

## 3. Case Reasoning Flow Display Order

The output must be grouped into four phases.

| Phase | Phase Name | Layers |
|---|---|---|
| Phase 1 | Grounding | case_context_summary; temporal_change_summary |
| Phase 2 | Reasoning Core | pattern_family_prompts; differential_prompt_layer; overlap_layer |
| Phase 3 | Safety Net | high_risk_mimic_layer; missing_evidence_layer; uncertainty_layer |
| Phase 4 | Escalation and Governance | urgent_review_prompt_layer; MDD_review_prompt_layer; source_status_layer; authority_envelope; blocked_outputs |

Display rule:

> Urgent danger, high-risk mimics, missing evidence, source limits, and uncertainty must not be buried beneath disease naming.

---

## 4. Mandatory Layer Registry

| Layer ID | Layer Name | Required | Phase |
|---|---|---|---|
| V09_LAYER_001 | case_context_summary | yes | Grounding |
| V09_LAYER_002 | temporal_change_summary | yes | Grounding |
| V09_LAYER_003 | pattern_family_prompts | yes | Reasoning Core |
| V09_LAYER_004 | differential_prompt_layer | yes | Reasoning Core |
| V09_LAYER_005 | overlap_layer | yes | Reasoning Core |
| V09_LAYER_006 | high_risk_mimic_layer | yes | Safety Net |
| V09_LAYER_007 | missing_evidence_layer | yes | Safety Net |
| V09_LAYER_008 | uncertainty_layer | yes | Safety Net |
| V09_LAYER_009 | urgent_review_prompt_layer | yes_where_relevant | Escalation and Governance |
| V09_LAYER_010 | MDD_review_prompt_layer | yes_where_relevant | Escalation and Governance |
| V09_LAYER_011 | source_status_layer | yes | Escalation and Governance |
| V09_LAYER_012 | authority_envelope | always_yes | Escalation and Governance |
| V09_LAYER_013 | blocked_outputs | yes | Escalation and Governance |

---

## 5. Global Layer Field Types

The following field types may be used across layers.

| Field Type | Meaning |
|---|---|
| provided_fact | Information explicitly supplied by user, clinician, report, or source context |
| not_provided | Missing or undocumented information |
| prompt_visible | Reasoning prompt remains visible |
| prompt_not_triggered | Prompt not triggered by available data |
| source_limited | Source exists but use is constrained |
| claim_mapped | Claim has source mapping |
| claim_not_mapped | Claim lacks source mapping |
| uncertainty_preserved | Closure is not established |
| urgent_review_visible | Red flag / urgent review prompt visible |
| MDD_review_visible | MDD or specialist review prompt visible |
| blocked_output | Output type is not allowed |
| authority_none | No diagnostic/treatment/procedure authority |

---

## 6. Global Blocked Values

No layer may output the following values as final clinical conclusions.

| Blocked Value | Reason |
|---|---|
| diagnosis_confirmed | diagnostic authority leak |
| disease_excluded | exclusion authority leak |
| treatment_recommended | treatment authority leak |
| test_order_recommended | test-order authority leak |
| procedure_recommended | procedure authority leak |
| follow_up_interval_set | management authority leak |
| public_ready_true | deployment authority leak |
| platform_wide_clinically_reviewed_true | unsupported clinical review claim |
| MDD_unnecessary | review replacement |
| urgent_review_unnecessary | unsafe reassurance |
| patient_facing_ready | public/patient-facing authority leak |

---

## 7. Layer Schema: case_context_summary

### 7.1 Purpose

The `case_context_summary` layer confirms what the platform understood from the provided input.

It must not infer missing facts.

### 7.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_001 |
| layer_name | yes | case_context_summary |
| provided_demographics | yes | list or not_provided |
| provided_clinical_context | yes | list or not_provided |
| provided_imaging_context | yes | list or not_provided |
| provided_history | yes | list or not_provided |
| provided_prior_imaging_status | yes | available / unavailable / not_provided |
| inferred_facts | yes | must be empty |
| missing_context_summary | yes | list |
| source_attachment_required | yes | no unless source-specific claim is made |

### 7.3 Allowed Values

- provided age if explicitly given,
- provided sex if explicitly given,
- provided diagnosis history if explicitly given,
- provided exposure history if explicitly given,
- provided therapy history if explicitly given,
- provided CT/HRCT comparison status if explicitly given,
- not_provided for missing items.

### 7.4 Blocked Values

- inferred exposure,
- inferred autoimmune history,
- inferred treatment history,
- inferred diagnosis,
- inferred prior CT,
- inferred symptom timeline,
- inferred pathology.

### 7.5 Required Language

- “Provided context includes...”
- “Not provided / not documented...”
- “The platform does not infer missing clinical facts.”

### 7.6 Dependency

This layer must appear before all reasoning layers.

---

## 8. Layer Schema: temporal_change_summary

### 8.1 Purpose

The `temporal_change_summary` layer shows change before disease naming.

### 8.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_002 |
| layer_name | yes | temporal_change_summary |
| prior_comparison_available | yes | true / false / unclear |
| comparison_timepoint | yes | date / interval / not_provided |
| change_direction | yes | new / increased / decreased / stable / mixed / unclear / not_assessable |
| acute_vs_chronic_context | yes | acute_overlay_possible / chronic_background / mixed / unclear |
| temporal_limiters | yes | list |
| temporal_claim_source_status | yes | source_mapped / source_limited / not_applicable |
| closure_status | yes | not_established |

### 8.3 Allowed Values

- new finding visible,
- interval worsening visible,
- stability visible,
- improvement visible,
- prior comparison unavailable,
- temporal comparison limited.

### 8.4 Blocked Values

- PPF diagnosed,
- acute exacerbation diagnosed,
- disease progression confirmed,
- stability proves benignity,
- no urgent issue because chronic disease exists.

### 8.5 Required Language

- “Compared with prior imaging, if available...”
- “Temporal comparison is limited because...”
- “New change is visible, but cause is not established.”

### 8.6 Dependency

Depends on `case_context_summary`.

Must precede `pattern_family_prompts`.

---

## 9. Layer Schema: pattern_family_prompts

### 9.1 Purpose

The `pattern_family_prompts` layer shows pattern-family reasoning without disease diagnosis.

### 9.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_003 |
| layer_name | yes | pattern_family_prompts |
| active_pattern_prompts | yes | list |
| supporting_features | yes | list |
| weakening_features | yes | list |
| pattern_limiters | yes | list |
| pattern_to_diagnosis_block | yes | true |
| source_status_refs | yes | list |
| closure_status | yes | not_established |

### 9.3 Allowed Pattern Prompts

- UIP_like_prompt
- probable_UIP_like_prompt
- indeterminate_for_UIP_prompt
- alternative_pattern_prompt
- NSIP_like_prompt
- OP_like_prompt
- HP_like_prompt
- CTD_ILD_context_prompt
- sarcoid_like_prompt
- granulomatous_prompt
- high_risk_mimic_pattern_prompt
- acute_overlay_prompt
- unclassifiable_or_mixed_pattern_prompt

### 9.4 Blocked Pattern Conclusions

- UIP equals IPF,
- probable UIP equals IPF,
- NSIP pattern equals idiopathic NSIP,
- OP pattern equals COP,
- granulomas equal sarcoidosis,
- HP-like features equal HP diagnosis,
- sarcoid-like features equal sarcoidosis diagnosis.

### 9.5 Required Language

- “Pattern prompt is visible.”
- “Pattern supports reasoning but does not establish diagnosis.”

### 9.6 Dependency

Depends on:

- `case_context_summary`
- `temporal_change_summary`

Must feed:

- `differential_prompt_layer`
- `overlap_layer`
- `high_risk_mimic_layer`

---

## 10. Layer Schema: differential_prompt_layer

### 10.1 Purpose

The `differential_prompt_layer` lists active reasoning families without final diagnosis.

### 10.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_004 |
| layer_name | yes | differential_prompt_layer |
| active_differential_prompts | yes | list |
| competing_families | yes | list |
| prompt_strength_descriptors | optional | supports / suggests / weakens / source_limited |
| diagnostic_closure | yes | not_allowed |
| source_status_refs | yes | list |
| unresolved_questions | yes | list |

### 10.3 Allowed Differential Prompts

- IPF_context_prompt
- fibrotic_HP_prompt
- CTD_ILD_prompt
- NSIP_like_prompt
- OP_like_prompt
- sarcoidosis_granulomatous_prompt
- occupational_mimic_prompt
- infection_mimic_prompt
- drug_therapy_related_mimic_prompt
- radiation_or_ICI_mimic_prompt
- malignancy_or_PLC_mimic_prompt
- aspiration_mimic_prompt
- unclassifiable_mixed_prompt

### 10.4 Blocked Outputs

- final diagnosis,
- ranked diagnosis as final,
- disease exclusion,
- management recommendation,
- “most likely diagnosis is...” as conclusion.

### 10.5 Required Language

- “Differential prompts remain visible.”
- “Final diagnosis is not established by this platform.”

### 10.6 Dependency

Depends on `pattern_family_prompts`.

Must feed:

- `overlap_layer`
- `missing_evidence_layer`
- `uncertainty_layer`

---

## 11. Layer Schema: overlap_layer

### 11.1 Purpose

The `overlap_layer` preserves coexistence and competing explanations.

### 11.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_005 |
| layer_name | yes | overlap_layer |
| overlap_states | yes | list |
| coexisting_processes_possible | yes | true / false / unclear |
| unresolved_boundaries | yes | list |
| hidden_process_guard | yes | active |
| source_status_refs | yes | list |
| closure_status | yes | not_established |

### 11.3 Allowed Overlap States

- UIP_vs_HP_overlap
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

### 11.4 Blocked Outputs

- one winning label without evidence,
- secondary process hidden,
- acute process collapsed into chronic ILD,
- mimic excluded because another pattern is visible.

### 11.5 Required Language

- “Overlap remains unresolved.”
- “Coexistence is possible and should remain visible.”

### 11.6 Dependency

Depends on:

- `pattern_family_prompts`
- `differential_prompt_layer`

Must feed:

- `high_risk_mimic_layer`
- `uncertainty_layer`
- `MDD_review_prompt_layer`

---

## 12. Layer Schema: high_risk_mimic_layer

### 12.1 Purpose

The `high_risk_mimic_layer` prevents unsafe mimic erasure.

### 12.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_006 |
| layer_name | yes | high_risk_mimic_layer |
| active_mimic_prompts | yes | list |
| mimic_supporting_features | yes | list |
| mimic_weakening_features | yes | list |
| mimic_missing_evidence | yes | list |
| mimic_source_limitations | yes | list |
| mimic_not_diagnosed_statement | yes | true |
| mimic_not_excluded_statement | yes | true |
| source_status_refs | yes | list |
| urgent_review_link | optional | yes / no / not_applicable |

### 12.3 Allowed Mimic Prompts

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

### 12.4 Blocked Outputs

- mimic diagnosed,
- mimic excluded,
- treatment started,
- test ordered,
- procedure recommended,
- oncology/radiation/occupational management recommended.

### 12.5 Required Language

- “High-risk mimic prompt remains visible.”
- “Mimic is not diagnosed or excluded by this platform.”

### 12.6 Dependency

Depends on:

- `overlap_layer`
- `missing_evidence_layer`
- `source_status_layer`

Must feed:

- `urgent_review_prompt_layer`
- `uncertainty_layer`

---

## 13. Layer Schema: missing_evidence_layer

### 13.1 Purpose

The `missing_evidence_layer` lists absent or incomplete evidence.

### 13.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_007 |
| layer_name | yes | missing_evidence_layer |
| missing_items | yes | list |
| affected_prompts | yes | list |
| missing_evidence_is_not_exclusion | yes | true |
| critical_missing_items | optional | list |
| source_status_refs | yes | list |
| confidence_limiter_link | yes | true |

### 13.3 Allowed Missing Evidence Items

- prior_CT
- temporal_comparison
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
- MDD_status
- urgent_clinical_status

### 13.4 Blocked Outputs

- missing exposure excludes HP,
- missing microbiology excludes infection,
- missing occupational history excludes occupational ILD,
- missing serology excludes CTD-ILD,
- missing prior CT proves stability,
- missing pathology proves benign disease.

### 13.5 Required Language

- “Missing evidence limits interpretation.”
- “Missing evidence is not exclusion.”

### 13.6 Dependency

Feeds:

- `uncertainty_layer`
- `source_status_layer`
- `MDD_review_prompt_layer`
- `urgent_review_prompt_layer`

---

## 14. Layer Schema: uncertainty_layer

### 14.1 Purpose

The `uncertainty_layer` displays what remains unresolved and what limits interpretation.

It must use confidence limiters, not diagnostic confidence scores.

### 14.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_008 |
| layer_name | yes | uncertainty_layer |
| unresolved_questions | yes | list |
| confidence_limiter | yes | list |
| diagnostic_confidence | yes | must be not_allowed |
| closure_status | yes | not_established |
| source_uncertainty | yes | list |
| review_needed | yes | yes / no / unclear |

### 14.3 Allowed Values

- unresolved UIP vs fibrotic HP,
- unresolved CTD-ILD vs idiopathic NSIP,
- unresolved OP vs infection/aspiration,
- unresolved sarcoidosis vs infection/beryllium/malignancy,
- unresolved therapy toxicity vs infection/progression,
- unresolved acute overlay vs chronic progression,
- source limitation,
- missing evidence.

### 14.4 Blocked Values

- high confidence IPF,
- low confidence HP,
- numeric disease probability,
- final diagnostic rank,
- closure established.

### 14.5 Required Language

- “Uncertainty remains unresolved.”
- “Interpretation is limited by...”
- “Final diagnosis is not established.”

### 14.6 Dependency

Depends on:

- `missing_evidence_layer`
- `overlap_layer`
- `source_status_layer`

---

## 15. Layer Schema: urgent_review_prompt_layer

### 15.1 Purpose

The `urgent_review_prompt_layer` shows urgent clinical danger prompts where relevant.

It must not triage, diagnose, or treat.

### 15.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_009 |
| layer_name | yes | urgent_review_prompt_layer |
| urgent_prompt_visible | yes | true / false / unclear |
| urgent_triggers | yes_if_visible | list |
| acute_danger_prompts | yes_if_visible | list |
| urgent_review_statement | yes_if_visible | text |
| triage_authority | yes | none |
| treatment_authority | yes | none |
| source_status_refs | optional | list |

### 15.3 Allowed Urgent Triggers

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

### 15.4 Blocked Outputs

- emergency triage decision,
- outpatient management recommendation,
- treatment plan,
- “no urgent review needed” when danger data are incomplete,
- acute exacerbation diagnosis.

### 15.5 Required Language

- “Urgent review prompt remains visible.”
- “The platform does not triage, diagnose, or treat.”

### 15.6 Dependency

Urgent review outranks all other output layers in display priority when active.

---

## 16. Layer Schema: MDD_review_prompt_layer

### 16.1 Purpose

The `MDD_review_prompt_layer` displays multidisciplinary or specialist review prompts.

### 16.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_010 |
| layer_name | yes | MDD_review_prompt_layer |
| MDD_prompt_visible | yes | true / false / unclear |
| specialist_review_prompts | yes | list |
| review_reason | yes_if_visible | list |
| review_not_replaced_statement | yes | true |
| source_status_refs | optional | list |

### 16.3 Allowed Specialist Review Prompts

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

### 16.4 Blocked Outputs

- MDD unnecessary,
- specialist review replaced,
- working diagnosis final,
- single-specialty closure when cross-domain uncertainty persists.

### 16.5 Required Language

- “MDD / specialist review prompt remains visible.”
- “Integrated review is not replaced by this platform.”

### 16.6 Dependency

Depends on:

- `uncertainty_layer`
- `overlap_layer`
- `high_risk_mimic_layer`
- `source_status_layer`

---

## 17. Layer Schema: source_status_layer

### 17.1 Purpose

The `source_status_layer` displays source support, role, mapping status, and limitations.

It must appear as both:

- a dedicated layer,
- claim-level source attachment where possible.

### 17.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_011 |
| layer_name | yes | source_status_layer |
| source_ids | yes | list |
| source_role_class | yes | list |
| claim_mapping_status | yes | mapped / partial / source_limited / not_mapped |
| source_limitations | yes | list |
| treatment_heavy_warning | yes_where_relevant | text |
| diagnostic_performance_warning | yes_where_relevant | text |
| case_example_only_warning | yes_where_relevant | text |
| narrow_reviewed_scope | optional | list |
| platform_wide_clinically_reviewed | yes | false |

### 17.3 Allowed Source Role Classes

- primary_high_authority
- primary_limited_scope
- auxiliary_review
- diagnostic_performance_study
- case_example_cautionary
- internal_governance

### 17.4 Allowed Claim Mapping Status Values

- claim_mapped
- partially_mapped
- source_limited
- treatment_heavy_limited
- diagnostic_performance_limited
- cautionary_case_only
- internal_governance_only
- not_mapped

### 17.5 Blocked Outputs

- source availability equals clinical review,
- claim mapping equals diagnosis,
- case report equals generalized rule,
- treatment-heavy source imports management,
- diagnostic performance automates interpretation.

### 17.6 Required Language

- “Source status must remain visible.”
- “Source mapping does not create diagnostic authority.”
- “Platform-wide clinically reviewed status remains false.”

---

## 18. Layer Schema: authority_envelope

### 18.1 Purpose

The `authority_envelope` is mandatory in every structured output.

### 18.2 Required Fields

| Field | Required | Required Value |
|---|---|---|
| layer_id | yes | V09_LAYER_012 |
| layer_name | yes | authority_envelope |
| diagnostic_authority | yes | none |
| treatment_authority | yes | none |
| public_ready | yes | false |
| clinically_reviewed.platform_wide | yes | false |
| clinically_reviewed.narrow_reviewed_scopes | optional | list |
| patient_facing_use | yes | not_allowed |
| automated_diagnosis | yes | not_allowed |
| automated_exclusion | yes | not_allowed |
| automated_treatment_selection | yes | not_allowed |
| automated_test_order | yes | not_allowed |
| automated_procedure_decision | yes | not_allowed |
| automated_follow_up_schedule | yes | not_allowed |

### 18.3 Narrow Reviewed Scope Values

Allowed narrow scopes currently:

- temporal_comparison_methodology
- ATS_ERS_JRS_ALAT_2022_UIP_claim_to_source_mapping

### 18.4 Blocked Authority Values

- diagnostic_authority: any
- treatment_authority: any
- public_ready: true
- clinically_reviewed.platform_wide: true
- patient_facing_use: allowed
- automated_diagnosis: allowed
- automated_exclusion: allowed
- automated_treatment_selection: allowed

### 18.5 Required Language

- “Diagnostic authority remains none.”
- “Treatment authority remains none.”
- “Platform-wide clinically reviewed status remains false.”

---

## 19. Layer Schema: blocked_outputs

### 19.1 Purpose

The `blocked_outputs` layer explicitly lists outputs that must not be generated.

### 19.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| layer_id | yes | V09_LAYER_013 |
| layer_name | yes | blocked_outputs |
| blocked_diagnosis_outputs | yes | list |
| blocked_exclusion_outputs | yes | list |
| blocked_treatment_outputs | yes | list |
| blocked_test_order_outputs | yes | list |
| blocked_procedure_outputs | yes | list |
| blocked_followup_outputs | yes | list |
| blocked_public_ready_outputs | yes | list |
| blocked_clinical_review_outputs | yes | list |
| blocked_MDD_replacement_outputs | yes | list |
| refusal_reframe_protocol | yes | active |

### 19.3 Required Blocked Categories

- diagnosis,
- exclusion,
- treatment,
- test ordering,
- procedure decision,
- follow-up interval,
- public readiness,
- clinical validation,
- MDD replacement,
- urgent review replacement.

### 19.4 Required Refusal / Reframe Protocol

When asked for a blocked output, the platform must:

1. refuse closure,
2. reframe into prompt visibility,
3. show missing evidence,
4. preserve mimics and overlap,
5. show review prompt where relevant,
6. print authority envelope.

### 19.5 Required Language

- “The platform does not provide this type of output.”
- “The platform can show reasoning prompts and limitations instead.”
- “Final diagnosis is not established.”

---

## 20. Claim-Level Source Attachment Schema

Every claim-like statement should be attachable to a source status object.

### 20.1 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| claim_id | yes | string |
| claim_text | yes | prompt-level non-authoritative statement |
| source_ids | yes | list |
| source_role_class | yes | list |
| claim_mapping_status | yes | mapped / partial / source_limited / not_mapped |
| source_limitations | yes | list |
| authority_effect | yes | none |
| diagnosis_created | yes | false |
| treatment_created | yes | false |

### 20.2 Blocked Claim Effects

- diagnosis_created: true
- treatment_created: true
- exclusion_created: true
- test_order_created: true
- procedure_decision_created: true
- followup_schedule_created: true

Rule:

> A claim can be source-attached without becoming a clinical conclusion.

---

## 21. Layer Dependency Matrix

| Layer | Depends On | Feeds |
|---|---|---|
| case_context_summary | none | all layers |
| temporal_change_summary | case_context_summary | pattern_family_prompts; high_risk_mimic_layer; uncertainty_layer |
| pattern_family_prompts | case_context_summary; temporal_change_summary | differential_prompt_layer; overlap_layer |
| differential_prompt_layer | pattern_family_prompts | overlap_layer; missing_evidence_layer |
| overlap_layer | pattern_family_prompts; differential_prompt_layer | high_risk_mimic_layer; uncertainty_layer; MDD_review_prompt_layer |
| high_risk_mimic_layer | overlap_layer; missing_evidence_layer; source_status_layer | urgent_review_prompt_layer; uncertainty_layer |
| missing_evidence_layer | all prior reasoning layers | uncertainty_layer; source_status_layer; MDD_review_prompt_layer |
| uncertainty_layer | missing_evidence_layer; overlap_layer; source_status_layer | MDD_review_prompt_layer; authority_envelope |
| urgent_review_prompt_layer | temporal_change_summary; high_risk_mimic_layer; missing_evidence_layer | authority_envelope |
| MDD_review_prompt_layer | uncertainty_layer; overlap_layer; source_status_layer | authority_envelope |
| source_status_layer | source governance docs | all claim-level outputs |
| authority_envelope | global constraints | final output |
| blocked_outputs | v0.9.0 entry gate | final output guard |

---

## 22. Output Priority Rules

When conflict exists, display priority is:

1. urgent_review_prompt_layer,
2. high_risk_mimic_layer,
3. missing_evidence_layer,
4. source_status_layer,
5. uncertainty_layer,
6. overlap_layer,
7. temporal_change_summary,
8. pattern_family_prompts,
9. differential_prompt_layer,
10. MDD_review_prompt_layer,
11. authority_envelope,
12. blocked_outputs.

Priority rule:

> Safety, mimics, missing evidence, source limits, and uncertainty outrank disease naming.

---

## 23. Minimal Output Mode

A minimal structured output may omit long explanatory prose, but it must not omit:

| Layer | Minimal Requirement |
|---|---|
| case_context_summary | provided facts and not_provided fields |
| temporal_change_summary | comparison status and limitation |
| high_risk_mimic_layer | active mimics or none_visible_with_limits |
| missing_evidence_layer | key missing evidence |
| uncertainty_layer | confidence_limiter |
| urgent_review_prompt_layer | visible if relevant |
| source_status_layer | source status summary |
| authority_envelope | always included |

Minimal output must still preserve:

- diagnostic_authority: none,
- treatment_authority: none,
- public_ready: false,
- clinically_reviewed.platform_wide: false.

---

## 24. Full Output Mode

A full structured output should include all 13 layers.

It should be used for:

- complex cases,
- multi-pattern cases,
- high-risk mimic cases,
- source-limited cases,
- acute overlay cases,
- MDD-relevant cases,
- roadmap validation examples,
- test case evaluation.

Full output must show:

- all active prompts,
- all relevant missing evidence,
- source statuses,
- claim mapping statuses,
- uncertainty and confidence limiters,
- blocked output categories,
- authority envelope.

---

## 25. Schema Acceptance Criteria

v0.9.1 is accepted only if:

- all 13 output layers have schemas,
- each layer has required fields,
- each layer has allowed values,
- each layer has blocked values,
- layer dependencies are defined,
- display priority is defined,
- source-status attachment is defined,
- authority envelope is mandatory,
- confidence limiter replaces diagnostic confidence,
- narrow reviewed scope remains separate from platform-wide clinical review,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed.platform_wide remains false.

---

## 26. Next Step

The next recommended step is:

- v0.9.2 — Structured Output Example Pack / Safe Response Templates

v0.9.2 should create safe example outputs for:

- UIP-like pattern with missing exposure history,
- fibrotic HP vs UIP overlap,
- NSIP/OP overlap with missing CTD and infection context,
- sarcoid-like granulomatous pattern with missing microbiology and beryllium context,
- post-radiation new GGO with infection/recurrence/ICI overlap,
- ICI exposure with FDG-avid nodes,
- known malignancy with septal thickening / PLC mimic,
- urgent review prompt over chronic ILD naming.

v0.9.2 must not create diagnosis, treatment, test ordering, procedure decisions, public readiness, or platform-wide clinical review.

---

## 27. Governance Statement

This schema defines how structured reasoning output layers must behave.

It does not diagnose.  
It does not treat.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not exclude mimics.  
It does not replace MDD.  
It does not create public readiness.  
It does not make the platform clinically reviewed.

The platform remains an evidence-governed clinical reasoning platform.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.9 rule remains:

> “Structured output must display uncertainty, sources, missing evidence, mimics, overlap, review prompts, and authority limits before any disease name is allowed to dominate the response.”

For v0.9.1:

> “Every reasoning layer must have a schema before it can be displayed.”