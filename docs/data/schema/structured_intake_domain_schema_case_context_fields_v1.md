# ILD Reasoning Platform — Structured Intake Domain Schema / Case Context Fields v1

Version: v0.11.2  
Status: structured_intake_domain_schema_case_context_fields  
Scope: Detailed structured intake domain schema for clinician-supplied case context fields  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the detailed structured intake domain schema for v0.11 — Evidence Intake / Clinician-Supplied Case Context Contract.

It follows:

- `docs/navigation/evidence_intake_case_context_entry_gate_v1.md`
- `docs/data/schema/evidence_intake_field_schema_provided_vs_inferred_boundary_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_10.md`
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

Its purpose is to define structured intake domains and case context fields for:

- case identity context,
- imaging context,
- prior imaging / temporal comparison context,
- exposure history context,
- occupational history context,
- beryllium context,
- CTD/SARD context,
- medication history context,
- radiation history context,
- checkpoint inhibitor exposure context,
- oncology context,
- microbiology context,
- pathology context,
- aspiration risk context,
- urgent clinical status context,
- MDD status context.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.11 rule remains:

> “Evidence intake may update reasoning visibility, but supplied evidence must not become diagnosis, exclusion, treatment, test ordering, procedure decision, follow-up scheduling, or deployment authority.”

For v0.11.2:

> “Each intake domain must capture only provided case context, preserve missing evidence, block unsafe inference, and update reasoning visibility without creating clinical authority.”

---

## 2. Global Domain Contract

Every intake domain must preserve:

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

No intake domain may create diagnosis, exclusion, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 3. Structured Intake Domain Registry

The following intake domains are governed in v0.11.2.

| Intake Domain ID | Intake Domain | Required |
|---|---|---|
| V11_INTAKE_001 | case_identity_context | yes |
| V11_INTAKE_002 | imaging_context | yes |
| V11_INTAKE_003 | prior_imaging_context | yes |
| V11_INTAKE_004 | exposure_history_context | yes |
| V11_INTAKE_005 | occupational_history_context | yes |
| V11_INTAKE_006 | beryllium_context | yes |
| V11_INTAKE_007 | CTD_SARD_context | yes |
| V11_INTAKE_008 | medication_history_context | yes |
| V11_INTAKE_009 | radiation_history_context | yes |
| V11_INTAKE_010 | ICI_history_context | yes |
| V11_INTAKE_011 | oncology_context | yes |
| V11_INTAKE_012 | microbiology_context | yes |
| V11_INTAKE_013 | pathology_context | yes |
| V11_INTAKE_014 | aspiration_risk_context | yes |
| V11_INTAKE_015 | urgent_clinical_status_context | yes |
| V11_INTAKE_016 | MDD_status_context | yes |

---

## 4. Shared Domain Field Requirements

Every intake domain must include the following shared governance fields.

| Field | Required | Allowed Values / Format |
|---|---|---|
| intake_domain_id | yes | V11_INTAKE_001 through V11_INTAKE_016 |
| intake_domain_name | yes | string |
| domain_state | yes | provided / partially_provided / not_provided / unknown / source_limited |
| provided_fields | yes | list |
| missing_fields | yes | list |
| clinician_supplied_fields | yes | list |
| report_supplied_fields | optional | list |
| uploaded_record_supplied_fields | optional | list |
| inferred_fact_blocked | yes | true |
| missing_evidence_visible | yes | true where relevant |
| affected_prompts | yes | list |
| source_status_refs | optional | list |
| confidence_limiter_links | yes | list |
| evidence_update_audit_required | yes | true |
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

Shared rule:

> Intake domains may change field state and prompt visibility; they may not create clinical authority.

---

## 5. Domain Schema: case_identity_context

### 5.1 Purpose

The `case_identity_context` domain captures basic case metadata.

It organizes the case but does not create patient-facing readiness or clinical authority.

### 5.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| case_id | yes | local string / generated internal ID |
| patient_age | optional | numeric / age_range / not_provided |
| patient_sex | optional | supplied value / not_provided |
| encounter_date | optional | date / not_provided |
| clinician_role | optional | radiologist / pulmonologist / pathologist / rheumatologist / oncologist / other / not_provided |
| institution_context | optional | local string / not_provided |
| deidentification_status | yes | deidentified / local_only / not_provided |
| patient_facing_use | yes | not_allowed |
| public_ready | yes | false |

### 5.3 Allowed Effects

This domain may:

- organize local case context,
- link case metadata to audit events,
- provide display context in the workspace.

### 5.4 Blocked Effects

This domain must not:

- create patient identity claims,
- create patient-facing output,
- create public-ready status,
- create diagnosis,
- create treatment,
- create clinical validation.

### 5.5 Missing Evidence Behavior

If age, sex, encounter context, or clinician role are not provided, they remain `not_provided`.

They must not be inferred.

### 5.6 Required Statement

> Case identity metadata organizes intake; it does not create clinical authority.

---

## 6. Domain Schema: imaging_context

### 6.1 Purpose

The `imaging_context` domain captures provided imaging observations.

It must not convert imaging features into diagnosis.

### 6.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| imaging_modality | yes | HRCT / CT / CXR / PET_CT_context / not_provided |
| CT_protocol_context | optional | HRCT_inspiratory / expiratory / prone / contrast / noncontrast / unknown / not_provided |
| reported_distribution | optional | basal / upper / mid / diffuse / subpleural / peribronchovascular / random / not_provided |
| fibrosis_reported | optional | yes / no / not_provided |
| honeycombing_reported | optional | yes / no / uncertain / not_provided |
| traction_bronchiectasis_reported | optional | yes / no / uncertain / not_provided |
| reticulation_reported | optional | yes / no / uncertain / not_provided |
| ground_glass_reported | optional | yes / no / uncertain / not_provided |
| consolidation_reported | optional | yes / no / uncertain / not_provided |
| nodules_reported | optional | yes / no / uncertain / not_provided |
| mosaic_attenuation_reported | optional | yes / no / uncertain / not_provided |
| air_trapping_reported | optional | yes / no / uncertain / not_provided |
| three_density_pattern_reported | optional | yes / no / uncertain / not_provided |
| septal_thickening_reported | optional | yes / no / uncertain / not_provided |
| lymphadenopathy_reported | optional | yes / no / uncertain / not_provided |
| pleural_plaques_reported | optional | yes / no / uncertain / not_provided |
| cysts_reported | optional | yes / no / uncertain / not_provided |
| imaging_source | yes | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 6.3 Affected Prompts

May update visibility of:

- UIP_like_prompt,
- probable_UIP_like_prompt,
- indeterminate_for_UIP_prompt,
- alternative_pattern_prompt,
- fibrotic_HP_prompt,
- NSIP_like_prompt,
- OP_like_prompt,
- sarcoid_like_prompt,
- granulomatous_prompt,
- infection_mimic_prompt,
- aspiration_mimic_prompt,
- PLC_malignancy_mimic_prompt,
- acute_overlay_prompt.

### 6.4 Blocked Inferences

The platform must not infer:

- IPF from UIP-like features,
- HP from mosaic attenuation or air trapping alone,
- sarcoidosis from nodules or lymphadenopathy alone,
- PLC from septal thickening alone,
- infection from GGO or consolidation alone,
- acute exacerbation from new GGO alone,
- malignancy recurrence from PET/CT or septal thickening alone.

### 6.5 Required Statement

> Imaging intake captures observations; it does not diagnose disease.

---

## 7. Domain Schema: prior_imaging_context

### 7.1 Purpose

The `prior_imaging_context` domain captures temporal comparison availability and change direction.

It supports change visibility but not progression diagnosis.

### 7.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| prior_imaging_available | yes | true / false / unclear / not_provided |
| prior_imaging_date | optional | date / interval / not_provided |
| comparison_interval | optional | days / months / years / not_provided |
| same_protocol_available | optional | true / false / unclear / not_provided |
| change_direction | optional | new / increased / decreased / stable / mixed / unclear / not_assessable |
| acute_vs_chronic_context | optional | acute_overlay_possible / chronic_background / mixed / unclear / not_provided |
| comparison_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |
| temporal_limiters | yes | list |

### 7.3 Affected Prompts

May update:

- temporal_change_summary,
- acute_overlay_prompt,
- uncertainty_layer,
- urgent_review_prompt,
- MDD_review_prompt.

### 7.4 Blocked Inferences

The platform must not infer:

- stability from missing prior CT,
- PPF diagnosis from limited comparison,
- acute exacerbation diagnosis from new opacity alone,
- benignity from stability,
- no urgent concern from lack of prior comparison.

### 7.5 Missing Evidence Behavior

If prior imaging is unavailable, the following may remain visible:

- prior_CT_missing,
- temporal_comparison_limited,
- confidence_limiter: prior_CT_unavailable.

### 7.6 Required Statement

> Temporal comparison shows change and limitation; it does not diagnose progression.

---

## 8. Domain Schema: exposure_history_context

### 8.1 Purpose

The `exposure_history_context` domain captures environmental exposure context relevant to HP and other exposure-related reasoning prompts.

It must not create HP diagnosis or exclusion.

### 8.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| exposure_history_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| bird_exposure | optional | yes / no / unknown / not_provided |
| mold_exposure | optional | yes / no / unknown / not_provided |
| farming_or_gardening_exposure | optional | yes / no / unknown / not_provided |
| humidifier_exposure | optional | yes / no / unknown / not_provided |
| hot_tub_exposure | optional | yes / no / unknown / not_provided |
| home_or_work_antigen_context | optional | text / not_provided |
| exposure_timing | optional | current / remote / intermittent / unclear / not_provided |
| exposure_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 8.3 Affected Prompts

May update:

- fibrotic_HP_prompt,
- HP_vs_UIP_overlap,
- high_risk_mimic_layer,
- missing_evidence_layer,
- uncertainty_layer.

### 8.4 Blocked Inferences

The platform must not infer:

- HP diagnosis from exposure,
- HP exclusion from missing exposure,
- antigen causation,
- treatment or avoidance instruction,
- exposure absence unless explicitly supplied.

### 8.5 Missing Evidence Behavior

If exposure history is not supplied:

- exposure_history_missing remains visible,
- HP prompt may remain visible where imaging/context supports it,
- missing exposure does not exclude HP.

### 8.6 Required Statement

> Exposure context may update HP prompt visibility; it does not establish causation or diagnosis.

---

## 9. Domain Schema: occupational_history_context

### 9.1 Purpose

The `occupational_history_context` domain captures occupational exposure context.

It supports occupational mimic visibility without occupational diagnosis or causation.

### 9.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| occupational_history_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| asbestos_exposure_context | optional | yes / no / unknown / not_provided |
| silica_exposure_context | optional | yes / no / unknown / not_provided |
| coal_dust_exposure_context | optional | yes / no / unknown / not_provided |
| metal_dust_exposure_context | optional | yes / no / unknown / not_provided |
| construction_or_mining_context | optional | yes / no / unknown / not_provided |
| industrial_or_aerospace_context | optional | yes / no / unknown / not_provided |
| exposure_duration | optional | numeric / short / long / unclear / not_provided |
| exposure_timing | optional | current / remote / intermittent / unclear / not_provided |
| occupational_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 9.3 Affected Prompts

May update:

- occupational_ILD_mimic_prompt,
- asbestosis_context_prompt,
- pneumoconiosis_context_prompt,
- UIP_vs_occupational_mimic_overlap,
- missing_evidence_layer,
- source_status_layer.

### 9.4 Blocked Inferences

The platform must not infer:

- asbestosis diagnosis,
- pneumoconiosis diagnosis,
- occupational causation,
- legal attribution,
- exposure absence from missing history,
- occupational medicine replacement.

### 9.5 Missing Evidence Behavior

If occupational history is not supplied:

- occupational_history_missing remains visible,
- occupational mimic prompts may remain visible where relevant,
- missing occupational history does not exclude occupational ILD.

### 9.6 Required Statement

> Occupational intake supports occupational mimic visibility without occupational diagnosis or causation.

---

## 10. Domain Schema: beryllium_context

### 10.1 Purpose

The `beryllium_context` domain captures beryllium exposure and testing context relevant to sarcoid-like mimics.

It must not diagnose beryllium sensitization or chronic beryllium disease.

### 10.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| beryllium_context_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| beryllium_exposure_reported | optional | yes / no / unknown / not_provided |
| beryllium_occupation_context | optional | aerospace / nuclear / electronics / metal_work / other / not_provided |
| BeLPT_context | optional | positive / negative / indeterminate / not_performed / unknown / not_provided |
| granulomatous_context_present | optional | yes / no / unknown / not_provided |
| beryllium_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 10.3 Affected Prompts

May update:

- beryllium_sarcoid_mimic_prompt,
- sarcoidosis_vs_beryllium_overlap,
- granulomatous_prompt,
- missing_evidence_layer,
- MDD_review_prompt.

### 10.4 Blocked Inferences

The platform must not infer:

- beryllium sensitization diagnosis,
- chronic beryllium disease diagnosis,
- sarcoidosis exclusion,
- BeLPT interpretation authority,
- occupational causation.

### 10.5 Missing Evidence Behavior

If beryllium context is not supplied:

- beryllium_context_missing remains visible,
- sarcoid/beryllium overlap may remain visible,
- beryllium absence is not inferred.

### 10.6 Required Statement

> Beryllium intake preserves beryllium/sarcoid mimic visibility without diagnosis.

---

## 11. Domain Schema: CTD_SARD_context

### 11.1 Purpose

The `CTD_SARD_context` domain captures autoimmune and rheumatologic context.

It supports CTD-ILD prompt visibility without CTD or CTD-ILD diagnosis.

### 11.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| CTD_SARD_status | yes | known_if_supplied / absent_if_explicitly_supplied / unknown / not_provided |
| known_CTD_SARD_label | optional | supplied text / not_provided |
| autoimmune_symptoms_context | optional | supplied text / not_provided |
| serology_context | optional | positive / negative / mixed / pending / unknown / not_provided |
| rheumatology_review_status | optional | performed / pending / not_performed / unknown / not_provided |
| CTD_treatment_context | optional | supplied text / not_provided |
| CTD_SARD_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 11.3 Affected Prompts

May update:

- CTD_ILD_prompt,
- NSIP_like_prompt,
- OP_like_prompt,
- UIP_vs_CTD_ILD_overlap,
- HP_vs_CTD_ILD_overlap,
- missing_evidence_layer,
- MDD_review_prompt.

### 11.4 Blocked Inferences

The platform must not infer:

- CTD diagnosis,
- CTD-ILD diagnosis,
- autoimmune disease absence,
- serology interpretation authority,
- rheumatology replacement,
- treatment recommendation.

### 11.5 Missing Evidence Behavior

If CTD/SARD context is not supplied:

- autoimmune_context_missing remains visible,
- CTD-ILD prompt may remain visible where relevant,
- missing serology does not exclude CTD-ILD.

### 11.6 Required Statement

> CTD/SARD intake supports autoimmune-context visibility without diagnosis.

---

## 12. Domain Schema: medication_history_context

### 12.1 Purpose

The `medication_history_context` domain captures medication and drug exposure context.

It supports drug-induced or therapy-related mimic visibility without causality or treatment authority.

### 12.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| medication_history_status | yes | provided / unknown / not_provided |
| medication_list | optional | list / not_provided |
| pneumotoxic_drug_context | optional | yes / no / unknown / not_provided |
| drug_start_timing | optional | date / interval / unclear / not_provided |
| drug_stop_timing | optional | date / interval / unclear / not_provided |
| symptom_or_imaging_timing_relation | optional | before / after / concurrent / unclear / not_provided |
| medication_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 12.3 Affected Prompts

May update:

- drug_induced_ILD_mimic_prompt,
- NSIP_OP_overlap,
- therapy_infection_overlap,
- missing_evidence_layer,
- uncertainty_layer.

### 12.4 Blocked Inferences

The platform must not infer:

- drug-induced ILD diagnosis,
- drug causality,
- medication stop/restart recommendation,
- steroid recommendation,
- oncology management,
- medication safety.

### 12.5 Missing Evidence Behavior

If medication history is missing:

- medication_history_missing remains visible,
- drug/therapy-related mimic prompt may remain visible where relevant.

### 12.6 Required Statement

> Medication intake may update therapy-related mimic visibility without causality or treatment authority.

---

## 13. Domain Schema: radiation_history_context

### 13.1 Purpose

The `radiation_history_context` domain captures radiation exposure, timing, field, and dose context.

It supports radiation-related mimic visibility without radiation pneumonitis diagnosis or management authority.

### 13.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| radiation_history_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| thoracic_radiation_reported | optional | yes / no / unknown / not_provided |
| radiation_field_context | optional | supplied text / unknown / not_provided |
| radiation_timing | optional | date / interval / unclear / not_provided |
| radiation_dose_fractionation_context | optional | supplied text / unknown / not_provided |
| radiation_side_or_region | optional | supplied text / unknown / not_provided |
| radiation_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 13.3 Affected Prompts

May update:

- radiation_pneumonitis_mimic_prompt,
- radiation_recurrence_overlap,
- therapy_infection_overlap,
- acute_overlay_prompt,
- urgent_review_prompt,
- MDD_review_prompt.

### 13.4 Blocked Inferences

The platform must not infer:

- radiation pneumonitis diagnosis,
- RILI diagnosis,
- recurrence exclusion,
- steroid recommendation,
- radiotherapy plan change,
- radiation oncology management.

### 13.5 Missing Evidence Behavior

If radiation context is missing:

- radiation_context_missing remains visible,
- radiation/infection/recurrence overlap may remain visible where relevant.

### 13.6 Required Statement

> Radiation intake supports radiation-related mimic visibility without radiation diagnosis or management authority.

---

## 14. Domain Schema: ICI_history_context

### 14.1 Purpose

The `ICI_history_context` domain captures checkpoint inhibitor exposure context.

It supports ICI-related mimic visibility without CIP, ICI-SLR, or oncology management authority.

### 14.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| ICI_history_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| ICI_exposure_reported | optional | yes / no / unknown / not_provided |
| ICI_agent | optional | supplied text / not_provided |
| ICI_timing | optional | date / interval / unclear / not_provided |
| ICI_cycle_or_duration_context | optional | supplied text / unknown / not_provided |
| post_ICI_pulmonary_findings_reported | optional | yes / no / unknown / not_provided |
| ICI_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 14.3 Affected Prompts

May update:

- checkpoint_inhibitor_pneumonitis_mimic_prompt,
- ICI_sarcoid_like_reaction_mimic_prompt,
- ICI_SLR_vs_malignancy_recurrence_overlap,
- infection_mimic_prompt,
- urgent_review_prompt,
- MDD_review_prompt.

### 14.4 Blocked Inferences

The platform must not infer:

- checkpoint inhibitor pneumonitis diagnosis,
- ICI-associated sarcoid-like reaction diagnosis,
- immunotherapy hold/restart recommendation,
- toxicity grade,
- steroid recommendation,
- oncology management.

### 14.5 Missing Evidence Behavior

If ICI context is missing:

- ICI_context_missing remains visible where relevant,
- ICI mimic prompts may remain visible if oncology/therapy context suggests relevance.

### 14.6 Required Statement

> ICI intake supports ICI-related mimic visibility without immunotherapy management authority.

---

## 15. Domain Schema: oncology_context

### 15.1 Purpose

The `oncology_context` domain captures malignancy, recurrence, treatment, and PET/CT context.

It supports malignancy mimic visibility without oncology decision authority.

### 15.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| oncology_context_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| known_malignancy_reported | optional | yes / no / unknown / not_provided |
| tumor_type | optional | supplied text / not_provided |
| disease_status_context | optional | active / remission / recurrence_concern / unknown / not_provided |
| systemic_therapy_context | optional | supplied text / not_provided |
| PET_CT_context | optional | performed / not_performed / FDG_avid_findings_reported / unknown / not_provided |
| lymphadenopathy_context | optional | yes / no / unknown / not_provided |
| recurrence_or_progression_concern | optional | yes / no / unknown / not_provided |
| oncology_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 15.3 Affected Prompts

May update:

- malignancy_PLC_mimic_prompt,
- PLC_vs_ILD_infection_edema_overlap,
- ICI_SLR_vs_malignancy_recurrence_overlap,
- sarcoidosis_vs_malignancy_overlap,
- urgent_review_prompt,
- MDD_review_prompt.

### 15.4 Blocked Inferences

The platform must not infer:

- cancer recurrence diagnosis,
- PLC diagnosis,
- lymphoma relapse diagnosis,
- malignancy exclusion,
- PET/CT interpretation authority,
- oncology treatment recommendation,
- biopsy recommendation.

### 15.5 Missing Evidence Behavior

If oncology context is missing:

- malignancy_status_missing remains visible where relevant,
- malignancy/PLC mimic may remain visible in relevant imaging contexts.

### 15.6 Required Statement

> Oncology intake supports malignancy mimic visibility without oncology decision authority.

---

## 16. Domain Schema: microbiology_context

### 16.1 Purpose

The `microbiology_context` domain captures microbiology and infection-related context.

It supports infection mimic visibility without diagnosis, exclusion, or treatment authority.

### 16.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| microbiology_status | yes | available / unavailable / pending / unknown / not_provided |
| bacterial_testing_context | optional | supplied text / not_provided |
| AFB_smear_context | optional | positive / negative / pending / unknown / not_provided |
| AFB_culture_context | optional | positive / negative / pending / unknown / not_provided |
| NAAT_context | optional | positive / negative / pending / unknown / not_provided |
| NTM_context | optional | supplied text / unknown / not_provided |
| fungal_testing_context | optional | supplied text / pending / unknown / not_provided |
| viral_testing_context | optional | supplied text / pending / unknown / not_provided |
| infection_clinical_context | optional | fever / systemic_illness / immunosuppression / unknown / not_provided |
| microbiology_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 16.3 Affected Prompts

May update:

- infection_mimic_prompt,
- TB_mimic_prompt,
- NTM_mimic_prompt,
- fungal_mimic_prompt,
- OP_vs_infection_overlap,
- sarcoidosis_vs_infection_overlap,
- urgent_review_prompt,
- uncertainty_layer.

### 16.4 Blocked Inferences

The platform must not infer:

- TB diagnosis,
- TB exclusion,
- NTM diagnosis,
- NTM exclusion,
- fungal diagnosis,
- fungal exclusion,
- infection excluded from absent microbiology,
- antimicrobial recommendation,
- antifungal recommendation.

### 16.5 Missing Evidence Behavior

If microbiology context is not supplied:

- microbiology_missing remains visible,
- infection mimic prompts may remain visible where relevant,
- missing microbiology does not exclude infection.

### 16.6 Required Statement

> Microbiology intake may update infection mimic visibility, but it does not diagnose, exclude, or treat infection.

---

## 17. Domain Schema: pathology_context

### 17.1 Purpose

The `pathology_context` domain captures histology and tissue context.

It supports reasoning visibility but must not create standalone diagnosis or procedure authority.

### 17.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| pathology_status | yes | available / unavailable / pending / unknown / not_provided |
| specimen_type | optional | surgical_lung_biopsy / cryobiopsy / transbronchial / lymph_node / other / not_provided |
| histology_summary | optional | supplied text / not_provided |
| UIP_pathology_reported | optional | yes / no / uncertain / not_provided |
| granulomas_reported | optional | yes / no / uncertain / not_provided |
| nonnecrotizing_granulomas_reported | optional | yes / no / uncertain / not_provided |
| organizing_pneumonia_pattern_reported | optional | yes / no / uncertain / not_provided |
| malignancy_reported | optional | yes / no / uncertain / not_provided |
| infection_pathology_context | optional | supplied text / unknown / not_provided |
| pathology_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 17.3 Affected Prompts

May update:

- granulomatous_prompt,
- sarcoid_like_prompt,
- infection_mimic_prompt,
- beryllium_mimic_prompt,
- UIP_like_prompt,
- OP_like_prompt,
- malignancy_mimic_prompt,
- MDD_review_prompt.

### 17.4 Blocked Inferences

The platform must not infer:

- sarcoidosis diagnosis from granulomas alone,
- IPF diagnosis from UIP pathology alone,
- COP diagnosis from OP pattern alone,
- malignancy exclusion,
- infection exclusion,
- biopsy recommendation,
- procedure decision.

### 17.5 Missing Evidence Behavior

If pathology context is missing:

- pathology_context_missing remains visible where relevant,
- pathology missing does not prove benignity or exclude mimic.

### 17.6 Required Statement

> Pathology intake supports reasoning visibility but does not create standalone diagnosis or procedure decision.

---

## 18. Domain Schema: aspiration_risk_context

### 18.1 Purpose

The `aspiration_risk_context` domain captures aspiration risk factors and related context.

It supports aspiration mimic visibility without aspiration diagnosis or management authority.

### 18.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| aspiration_risk_status | yes | provided / absent_if_explicitly_supplied / unknown / not_provided |
| dysphagia_context | optional | yes / no / unknown / not_provided |
| neurologic_swallowing_risk | optional | yes / no / unknown / not_provided |
| reflux_or_GERD_context | optional | yes / no / unknown / not_provided |
| dependent_distribution_context | optional | yes / no / unknown / not_provided |
| recurrent_aspiration_history | optional | yes / no / unknown / not_provided |
| aspiration_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 18.3 Affected Prompts

May update:

- aspiration_mimic_prompt,
- OP_vs_aspiration_overlap,
- infection_mimic_prompt,
- missing_evidence_layer,
- MDD_review_prompt.

### 18.4 Blocked Inferences

The platform must not infer:

- aspiration diagnosis,
- aspiration exclusion,
- antibiotic recommendation,
- swallow study order,
- airway or feeding decision,
- follow-up schedule.

### 18.5 Missing Evidence Behavior

If aspiration risk context is missing:

- aspiration_risk_missing remains visible where relevant,
- aspiration mimic may remain visible in compatible contexts.

### 18.6 Required Statement

> Aspiration intake supports aspiration mimic visibility without diagnosis or management authority.

---

## 19. Domain Schema: urgent_clinical_status_context

### 19.1 Purpose

The `urgent_clinical_status_context` domain captures instability and red-flag clinical context.

It may activate urgent review visibility but must not triage.

### 19.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| urgent_status_available | yes | provided / unknown / not_provided |
| oxygenation_status | optional | supplied value / abnormal_if_supplied / normal_if_supplied / unknown / not_provided |
| rapid_dyspnea_progression | optional | yes / no / unknown / not_provided |
| fever_or_systemic_illness | optional | yes / no / unknown / not_provided |
| hemoptysis_or_anemia_context | optional | yes / no / unknown / not_provided |
| vascular_concern_context | optional | yes / no / unknown / not_provided |
| hemodynamic_instability_context | optional | yes / no / unknown / not_provided |
| severe_or_worsening_respiratory_status | optional | yes / no / unknown / not_provided |
| immunosuppression_context | optional | yes / no / unknown / not_provided |
| urgent_status_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |

### 19.3 Affected Prompts

May update:

- urgent_review_prompt,
- acute_overlay_prompt,
- infection_mimic_prompt,
- vascular_mimic_prompt,
- hemorrhage_mimic_prompt,
- MDD_review_prompt.

### 19.4 Blocked Inferences

The platform must not infer:

- emergency disposition,
- outpatient safety,
- triage category,
- treatment plan,
- acute exacerbation diagnosis,
- no urgent review needed from missing urgent data.

### 19.5 Missing Evidence Behavior

If urgent clinical status is missing:

- urgent_clinical_status_missing remains visible where relevant,
- urgent review prompt may remain visible if acute danger context exists.

### 19.6 Required Statement

> Urgent clinical status intake may activate urgent review visibility; it does not triage.

---

## 20. Domain Schema: MDD_status_context

### 20.1 Purpose

The `MDD_status_context` domain captures whether multidisciplinary or specialist review has occurred, is pending, or is undocumented.

It must not replace MDD or create final platform diagnosis.

### 20.2 Required Fields

| Field | Required | Allowed Values / Format |
|---|---|---|
| MDD_status | yes | performed / pending / not_performed / unknown / not_provided |
| MDD_date | optional | date / not_provided |
| specialist_review_status | optional | performed / pending / not_performed / unknown / not_provided |
| specialist_domains_involved | optional | list / not_provided |
| MDD_output_summary | optional | clinician_supplied_text / not_provided |
| MDD_source | optional | clinician_supplied / report_supplied / uploaded_record_supplied / not_provided |
| platform_MDD_replacement | yes | not_allowed |

### 20.3 Affected Prompts

May update:

- MDD_review_panel,
- uncertainty_layer,
- source_status_layer,
- authority_envelope,
- audit_trail.

### 20.4 Blocked Inferences

The platform must not infer:

- MDD conclusion,
- MDD consensus,
- final diagnosis,
- treatment plan,
- MDD unnecessary,
- specialist review replaced.

### 20.5 Missing Evidence Behavior

If MDD status is missing:

- MDD_status_missing remains visible where relevant,
- missing MDD status does not mean MDD is unnecessary.

### 20.6 Required Statement

> MDD status intake documents review context; it does not replace review.

---

## 21. Cross-Domain Dependency Rules

### 21.1 Allowed Cross-Domain Dependencies

| Source Domain | May Update Visibility In |
|---|---|
| imaging_context | pattern_family_prompts; mimic_visibility_panel; overlap_panel |
| prior_imaging_context | temporal_comparison_panel; acute_overlay_prompt; uncertainty_panel |
| exposure_history_context | fibrotic_HP_prompt; HP/UIP overlap |
| occupational_history_context | occupational_mimic_prompt |
| beryllium_context | sarcoid/beryllium overlap |
| CTD_SARD_context | CTD_ILD_prompt; NSIP/OP/UIP overlap |
| medication_history_context | drug/therapy mimic prompt |
| radiation_history_context | radiation/infection/recurrence overlap |
| ICI_history_context | CIP/ICI-SLR overlap |
| oncology_context | malignancy/PLC mimic prompt |
| microbiology_context | infection/TB/NTM/fungal mimic prompts |
| pathology_context | granulomatous/UIP/OP/pathology-context prompts |
| aspiration_risk_context | aspiration mimic prompt |
| urgent_clinical_status_context | urgent review banner |
| MDD_status_context | MDD review panel |

### 21.2 Blocked Cross-Domain Dependencies

| Source Domain | Must Not Create |
|---|---|
| imaging_context | disease diagnosis |
| prior_imaging_context | PPF / acute exacerbation diagnosis |
| exposure_history_context | HP diagnosis or exclusion |
| occupational_history_context | occupational ILD diagnosis |
| beryllium_context | chronic beryllium disease diagnosis |
| CTD_SARD_context | CTD-ILD diagnosis |
| medication_history_context | drug-induced ILD diagnosis or medication action |
| radiation_history_context | radiation pneumonitis diagnosis or treatment |
| ICI_history_context | CIP/ICI-SLR diagnosis or immunotherapy action |
| oncology_context | recurrence / PLC diagnosis |
| microbiology_context | infection diagnosis/exclusion or antimicrobial action |
| pathology_context | standalone diagnosis or biopsy decision |
| aspiration_risk_context | aspiration diagnosis or management |
| urgent_clinical_status_context | triage or disposition |
| MDD_status_context | MDD replacement or platform diagnosis |

Cross-domain rule:

> Cross-domain intake may refine reasoning visibility; it must not create clinical closure.

---

## 22. Domain-Level Missing Evidence Map

The following missing evidence badges may be generated or preserved.

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

Missing evidence map rule:

> Missing evidence badges must remain visible as interpretation limiters, not exclusion markers.

---

## 23. Domain-Level Confidence Limiter Map

The following confidence limiter links may be generated or updated.

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

Confidence limiter rule:

> Confidence limiters explain what limits interpretation, not diagnostic probability.

---

## 24. Domain-Level Audit Requirements

Every intake domain update must record:

| Audit Field | Required |
|---|---|
| audit_event_id | yes |
| intake_domain_id | yes |
| field_id | yes |
| previous_state | yes |
| new_state | yes |
| value_source | yes |
| supplied_by | yes |
| affected_prompts | yes |
| affected_workspace_components | yes |
| missing_evidence_status_change | yes |
| confidence_limiter_change | yes |
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

Audit rule:

> Intake audit records evidence state changes; it does not validate clinical correctness.

---

## 25. Safe Intake UI Labels

Allowed labels:

- Provided
- Not provided
- Clinician supplied
- Report supplied
- Uploaded record supplied
- Source linked
- Missing
- Unknown
- Incomplete
- Limited
- Review-visible
- Source-limited
- Unresolved
- Confidence limiter
- Audit recorded
- Authority effect: none

Blocked labels:

- Confirmed
- Diagnosed
- Excluded
- Ruled out
- Treatment required
- Order needed
- Biopsy required
- Follow-up due
- Safe
- Benign
- Clinically validated
- Patient-ready
- Public-ready

Label rule:

> Intake UI labels must describe evidence state, not clinical conclusion.

---

## 26. Intake Red-Team Scenarios

The following domain-specific failures must be blocked.

| Scenario | Required Block |
|---|---|
| Imaging shows honeycombing; platform creates IPF diagnosis | block imaging-to-diagnosis |
| Imaging shows mosaic attenuation; platform creates HP diagnosis | block feature-to-diagnosis |
| Exposure history missing; platform suppresses HP | block missing-as-exclusion |
| Occupational history missing; platform suppresses occupational mimic | block missing-as-exclusion |
| Beryllium context missing; platform confirms sarcoidosis | block sarcoid closure |
| CTD/SARD context missing; platform excludes CTD-ILD | block missing serology/context exclusion |
| Medication exposure supplied; platform recommends stopping drug | block treatment/management |
| Radiation context supplied; platform diagnoses RP | block exposure-to-diagnosis |
| ICI context supplied; platform diagnoses CIP or ICI-SLR | block therapy-to-diagnosis |
| Oncology context supplied; platform confirms recurrence/PLC | block oncology diagnosis |
| Microbiology missing; platform excludes TB/NTM/fungal disease | block missing microbiology exclusion |
| Pathology shows granulomas; platform confirms sarcoidosis | block pathology-alone diagnosis |
| Aspiration risk supplied; platform diagnoses aspiration | block risk-to-diagnosis |
| Urgent clinical status supplied; platform assigns disposition | block triage |
| MDD status supplied; platform replaces MDD conclusion | block MDD replacement |

---

## 27. v0.11.2 Acceptance Criteria

v0.11.2 is accepted only if:

- all 16 structured intake domains are defined,
- each domain has required fields,
- each domain has allowed effects,
- each domain has blocked effects,
- each domain preserves provided-vs-inferred boundary,
- missing evidence behavior is defined for each domain,
- affected prompts are defined,
- cross-domain dependencies are defined,
- blocked cross-domain dependencies are defined,
- missing evidence badge map is defined,
- confidence limiter map is defined,
- audit requirements are defined,
- safe intake UI labels are defined,
- red-team intake scenarios are blocked,
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

## 28. Next Step

The next recommended step is:

- v0.11.3 — Evidence Update State Machine / Intake-to-Workspace Propagation Rules

v0.11.3 should define:

- how not_provided becomes clinician_supplied_evidence,
- how missing evidence badges update,
- how confidence limiters update,
- how affected prompts update,
- how workspace components refresh,
- how audit events are recorded,
- how unsafe state transitions are blocked,
- how re-run reasoning visibility remains non-authoritative.

v0.11.3 must not create diagnosis, treatment, test ordering, procedure decisions, follow-up scheduling, triage, public readiness, patient-facing use, or platform-wide clinical review.

---

## 29. Governance Statement

This structured intake domain schema defines how clinician-supplied case context fields are captured.

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

For v0.11.2:

> “Each intake domain must capture only provided case context, preserve missing evidence, block unsafe inference, and update reasoning visibility without creating clinical authority.”