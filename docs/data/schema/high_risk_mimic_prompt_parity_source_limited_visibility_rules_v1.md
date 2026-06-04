# ILD Reasoning Platform — High-Risk Mimic Prompt Parity / Source-Limited Visibility Rules v1

Version: v0.8.4  
Status: source_limited_prompt_parity  
Scope: High-risk mimic prompt visibility rules under source-limited non-authoritative governance  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines source-limited prompt parity rules for v0.8 high-risk mimics.

It follows:

- `docs/navigation/deferred_source_expansion_high_risk_mimic_source_intake_entry_gate_v1.md`
- `docs/navigation/high_risk_mimic_source_role_map_v1.md`
- `docs/navigation/high_risk_mimic_claim_to_source_mapping_table_v1.md`
- `docs/data/schema/high_risk_mimic_family_matrix_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_7.md`

This document does not open full diagnostic domain parity.

This document does not diagnose occupational ILD.  
This document does not diagnose pneumoconiosis.  
This document does not diagnose asbestosis.  
This document does not diagnose chronic beryllium disease.  
This document does not diagnose tuberculosis.  
This document does not diagnose nontuberculous mycobacterial disease.  
This document does not diagnose fungal infection.  
This document does not diagnose aspiration-related lung disease.  
This document does not diagnose drug-induced ILD.  
This document does not diagnose radiation pneumonitis.  
This document does not diagnose checkpoint inhibitor pneumonitis.  
This document does not diagnose pulmonary lymphangitic carcinomatosis.  
This document does not diagnose lymphoma.  
This document does not diagnose malignancy.  
This document does not diagnose sarcoidosis-like reaction.  
This document does not recommend treatment.  
This document does not decide biopsy, bronchoscopy, BAL, HRCT, PET/CT, microbiology, serology, occupational testing, drug discontinuation, radiation planning, immunotherapy management, or follow-up interval.  
This document does not create public readiness.  
This document does not make v0.8 clinically reviewed.

Its purpose is to ensure that high-risk mimics are visible without becoming diagnoses, exclusions, orders, or management instructions.

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

For v0.8.4:

> “High-risk mimic prompts may be visible, but source-limited prompts are not diagnoses.”

---

## 2. Source-Limited Prompt Parity Meaning

Source-limited prompt parity means:

- the mimic family can be shown,
- the source status can be shown,
- missing evidence can be shown,
- competing explanations can remain visible,
- overlap states can be represented,
- urgent review can be prompted where relevant,
- MDD or specialist review can be prompted where relevant.

Source-limited prompt parity does not mean:

- the mimic is diagnosed,
- the mimic is excluded,
- a test is ordered,
- a procedure is recommended,
- a treatment is selected,
- a therapy is stopped,
- a follow-up interval is set,
- a public-ready output is created,
- clinical review is complete.

---

## 3. Global Authority Constraints

The following constraints are mandatory across v0.8.4.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| full_domain_parity | not_opened |
| automated_diagnosis | not_allowed |
| automated_exclusion | not_allowed |
| automated_treatment_selection | not_allowed |
| automated_drug_discontinuation | not_allowed |
| automated_immunotherapy_hold_or_restart | not_allowed |
| automated_radiotherapy_plan_change | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_bronchoscopy_decision | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_microbiology_order | not_allowed |
| automated_HRCT_order | not_allowed |
| automated_PET_CT_order | not_allowed |
| automated_follow_up_schedule | not_allowed |
| patient_facing_use | not_allowed |
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

No prompt may override these constraints.

---

## 4. Global Prompt Output Contract

Every v0.8.4 mimic prompt should include, where relevant:

| Output Element | Required |
|---|---|
| mimic_family_prompt | yes |
| source_status | yes |
| source_role_class | yes |
| claim_mapping_status | yes |
| supporting_features | yes |
| weakening_features | yes |
| missing_evidence | yes |
| competing_families | yes |
| overlap_state | yes |
| treatment_heavy_warning_where_relevant | yes |
| diagnostic_performance_warning_where_relevant | yes |
| case_example_only_warning_where_relevant | yes |
| MDD_or_specialist_review_prompt | yes |
| urgent_review_prompt_where_relevant | yes |
| diagnostic_authority | yes |
| treatment_authority | yes |
| public_ready | yes |
| clinically_reviewed | yes |

Required values:

- diagnostic_authority: none
- treatment_authority: none
- public_ready: false
- clinically_reviewed: false

---

## 5. Global Prompt Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| HRM_PROMPT_001 | A mimic prompt is not a diagnosis | Show prompt without naming disease as final |
| HRM_PROMPT_002 | Missing evidence is not exclusion | List missing evidence and keep mimic visible |
| HRM_PROMPT_003 | Source-limited status must be visible | Show source class and limitation |
| HRM_PROMPT_004 | Treatment-heavy source cannot import treatment | Block management advice |
| HRM_PROMPT_005 | Diagnostic performance source cannot automate interpretation | Show ambiguity only |
| HRM_PROMPT_006 | Case report cannot become generalized rule | Mark cautionary-only |
| HRM_PROMPT_007 | Competing families must remain visible | Avoid single-label closure |
| HRM_PROMPT_008 | Acute danger outranks chronic family naming | Show urgent review prompt |
| HRM_PROMPT_009 | Specialist/MDD review is prompt-only | Do not replace review |
| HRM_PROMPT_010 | No prompt may create public readiness | public_ready remains false |

---

## 6. Occupational ILD / Pneumoconiosis / Asbestosis Prompt Parity

### 6.1 Allowed Prompt

The platform may show:

- occupational exposure prompt,
- pneumoconiosis/asbestosis mimic prompt,
- missing occupational history prompt,
- latency prompt,
- dust / mineral / irritant exposure prompt,
- occupational medicine review prompt.

### 6.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| silica/asbestos/coal/hard metal/mineral dust exposure possible | occupational exposure prompt visible |
| occupational history missing | missing occupational evidence visible |
| fibrosis with possible exposure context | occupational mimic prompt visible |
| nodular/fibrotic upper-lung or dust-related pattern concern | pneumoconiosis prompt visible |
| lower-lung fibrosis or pleural clue with asbestos context possible | asbestosis prompt visible |
| long latency possible | temporal exposure uncertainty visible |
| HP or granulomatous overlap possible | occupational/HP/beryllium overlap visible |

### 6.3 Required Allowed Language

- “Occupational exposure prompt is visible.”
- “Occupational history is incomplete.”
- “Pneumoconiosis/asbestosis mimic remains visible as a source-limited prompt.”
- “Exposure history does not establish causation.”
- “Occupational medicine review prompt remains visible where relevant.”
- “Final diagnosis is not established by this platform.”

### 6.4 Blocked Language

- “Occupational ILD diagnosed.”
- “Asbestosis confirmed.”
- “Pneumoconiosis diagnosed.”
- “Exposure caused this disease.”
- “Compensation-related causation established.”
- “Surveillance plan set.”
- “Treatment should be started.”

### 6.5 Pass Condition

Occupational mimic remains visible without diagnosis, causation, medicolegal conclusion, treatment, or surveillance authority.

---

## 7. Beryllium / Chronic Beryllium Disease Prompt Parity

### 7.1 Allowed Prompt

The platform may show:

- beryllium exposure prompt,
- BeS/CBD distinction prompt,
- BeLPT context prompt,
- granulomatous sarcoid-mimic prompt,
- occupational medicine review prompt.

### 7.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| beryllium exposure possible or missing | beryllium exposure prompt visible |
| granulomatous disease with occupational exposure gap | berylliosis mimic visible |
| sarcoidosis-like pattern with incomplete occupational history | beryllium/sarcoid overlap visible |
| BeLPT mentioned or missing | BeLPT context visible without interpretation |
| lung pathology missing or not integrated | CBD evidence gap visible |

### 7.3 Required Allowed Language

- “Beryllium / sarcoid-mimic prompt remains visible.”
- “Beryllium exposure context is incomplete.”
- “BeLPT context may be relevant but is not interpreted by the platform.”
- “BeS and CBD distinction remains review-visible.”
- “Final diagnosis is not established by this platform.”

### 7.4 Blocked Language

- “Beryllium sensitivity diagnosed.”
- “Chronic beryllium disease confirmed.”
- “BeLPT proves CBD.”
- “Sarcoidosis confirmed while beryllium context is hidden.”
- “Occupational causation established.”
- “Treatment should be started.”

### 7.5 Pass Condition

Beryllium remains visible as sarcoid-mimic / occupational-mimic prompt without BeLPT interpretation or CBD diagnosis.

---

## 8. TB / NTM / Fungal Mimic Prompt Parity

### 8.1 Allowed Prompt

The platform may show:

- TB mimic prompt,
- NTM mimic prompt,
- fungal mimic prompt,
- microbiology missing-evidence prompt,
- endemic exposure prompt,
- immunosuppression prompt,
- granulomatous infection mimic prompt,
- urgent review prompt where relevant.

### 8.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| granulomatous disease with incomplete microbiology | TB/NTM/fungal mimic visible |
| AFB smear absent/positive/negative but clinical context incomplete | AFB limitation prompt visible |
| NAAT absent/negative/positive but context incomplete | NAAT limitation prompt visible |
| culture context missing | microbiology evidence gap visible |
| repeated sputum/bronchial wash/BAL context missing | NTM microbiology gap visible |
| endemic fungal exposure or travel missing | fungal mimic prompt visible |
| immunosuppression present or unknown | opportunistic infection prompt visible |
| fever/systemic illness/rapid decline | urgent review prompt visible |

### 8.3 Required Allowed Language

- “TB mimic remains visible because microbiology context is incomplete.”
- “AFB smear status does not settle TB diagnosis in this platform.”
- “NTM prompt requires clinical-radiologic-microbiologic integration visibility.”
- “Fungal mimic remains visible; source scope is limited or treatment-heavy where relevant.”
- “Missing microbiology limits confidence.”
- “Urgent review prompt remains visible where clinically relevant.”

### 8.4 Blocked Language

- “TB diagnosed.”
- “TB excluded.”
- “NTM diagnosed.”
- “NTM excluded.”
- “Fungal infection confirmed.”
- “Fungal infection excluded.”
- “Order cultures.”
- “Start antifungal treatment.”
- “Start antimicrobial treatment.”
- “Isolation instruction generated.”

### 8.5 Pass Condition

Infectious mimics remain visible without diagnosis, exclusion, microbiology ordering, public health instruction, or antimicrobial/antifungal recommendation.

---

## 9. Aspiration-Related Lung Disease Prompt Parity

### 9.1 Allowed Prompt

The platform may show:

- aspiration risk prompt,
- silent aspiration / microaspiration context prompt,
- dependent injury prompt,
- OP-like consolidation overlap prompt,
- aspiration/infection ambiguity prompt,
- clinical review prompt.

### 9.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| dependent consolidation or recurrent lower-lobe opacity | aspiration prompt visible |
| OP-like consolidation with aspiration risk unknown | aspiration/OP overlap visible |
| aspiration risk factors missing | missing aspiration evidence visible |
| infection data missing | aspiration/infection overlap visible |
| neurologic/swallow/reflux/altered consciousness context missing | aspiration risk incomplete |
| acute clinical worsening | urgent review visible where relevant |

### 9.3 Required Allowed Language

- “Aspiration risk prompt remains visible.”
- “Aspiration history is incomplete.”
- “OP-like consolidation and aspiration overlap remain visible.”
- “Aspiration and infection ambiguity remains visible.”
- “Final diagnosis is not established by this platform.”

### 9.4 Blocked Language

- “Aspiration pneumonia diagnosed.”
- “Aspiration-related ILD confirmed.”
- “Infection excluded.”
- “Antibiotics should be started.”
- “Swallow study should be ordered.”
- “Feeding plan should be changed.”
- “Follow-up every X months.”

### 9.5 Pass Condition

Aspiration remains visible as a mimic/overlap prompt without diagnosis, antibiotic recommendation, swallow/airway decision, or schedule authority.

---

## 10. Drug-Induced / Therapy-Related ILD Prompt Parity

### 10.1 Allowed Prompt

The platform may show:

- medication history prompt,
- drug / therapy temporal relationship prompt,
- alternative-cause visibility prompt,
- OP-like / NSIP-like / acute injury mimic prompt,
- oncology therapy context prompt,
- treatment-heavy source warning.

### 10.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| medication or therapy exposure temporally relevant | drug-induced mimic visible |
| medication history missing | medication evidence gap visible |
| OP-like or NSIP-like pattern with medication gap | DILD overlap visible |
| infection/progression/radiation/ICI context incomplete | competing mimic visibility |
| cancer therapy exposure present | oncology review prompt visible |
| rapid respiratory decline | urgent review visible |

### 10.3 Required Allowed Language

- “Medication / therapy-related ILD mimic remains visible.”
- “Temporal relationship is review-visible but does not establish causality.”
- “Alternative causes remain visible.”
- “Drug-induced ILD source authority is review-level or limited where relevant.”
- “Treatment authority remains none.”

### 10.4 Blocked Language

- “Drug-induced ILD confirmed.”
- “This drug caused the ILD.”
- “Stop the drug.”
- “Restart the drug.”
- “Start steroids.”
- “Change oncologic therapy.”
- “Treatment should be started.”

### 10.5 Pass Condition

Drug/therapy-related ILD remains visible without causality assignment, discontinuation/rechallenge advice, steroid recommendation, or oncology management authority.

---

## 11. Radiation Pneumonitis / Radiation-Induced Lung Injury Prompt Parity

### 11.1 Allowed Prompt

The platform may show:

- radiation history prompt,
- radiation field/timing/dose context prompt,
- acute RP vs chronic RPF temporal prompt,
- infection / recurrence / drug / ICI overlap prompt,
- radiation oncology review prompt.

### 11.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| thoracic radiation history present or missing | RP/RILI prompt visible |
| new GGO/consolidation after radiation | RP/infection/recurrence overlap visible |
| radiation field/timing/dose context missing | missing radiation evidence visible |
| chronic fibrotic change after radiation | chronic RILI/RPF context visible |
| prior imaging unavailable | temporal uncertainty visible |
| ICI or drug therapy overlaps radiation | therapy-overlap prompt visible |
| rapid hypoxemia or severe symptoms | urgent review visible |

### 11.3 Required Allowed Language

- “Radiation timing and field context are missing.”
- “Radiation pneumonitis / RILI mimic prompt remains visible.”
- “Infection, recurrence, drug toxicity, and ICI pneumonitis remain competing prompts.”
- “Radiation source is treatment-heavy where relevant; treatment authority remains none.”
- “Final diagnosis is not established by this platform.”

### 11.4 Blocked Language

- “Radiation pneumonitis diagnosed.”
- “Radiation fibrosis confirmed.”
- “Start steroids.”
- “Change radiation plan.”
- “Recurrence excluded.”
- “Follow-up every X months.”

### 11.5 Pass Condition

Radiation injury remains visible as source-limited mimic prompt without RP/RPF diagnosis, steroid recommendation, radiotherapy modification, recurrence exclusion, or schedule authority.

---

## 12. Checkpoint Inhibitor Pneumonitis / ICI-SLR Prompt Parity

### 12.1 Allowed Prompt

The platform may show:

- ICI exposure prompt,
- checkpoint inhibitor pneumonitis mimic prompt,
- ICI-associated sarcoid-like reaction prompt,
- infection / radiation / progression / drug overlap prompt,
- oncology review prompt.

### 12.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| checkpoint inhibitor exposure present or missing | ICI-related mimic visible |
| new GGO/consolidation/nodules during or after ICI | CIP/progression/infection overlap visible |
| new lymphadenopathy or FDG-avid nodes during/after ICI | ICI-SLR/recurrence ambiguity visible |
| prior radiation overlaps ICI | RP/CIP overlap visible |
| infection data missing | infection prompt visible |
| malignancy status uncertain | progression/recurrence prompt visible |
| hypoxemia or rapid worsening | urgent review visible |

### 12.3 Required Allowed Language

- “ICI exposure creates therapy-related mimic visibility but not diagnosis.”
- “Checkpoint inhibitor pneumonitis, infection, radiation pneumonitis, and progression remain competing prompts.”
- “ICI-associated sarcoid-like reaction and recurrence remain ambiguous.”
- “Oncology / pulmonary review prompt remains visible.”
- “Treatment authority remains none.”

### 12.4 Blocked Language

- “Checkpoint inhibitor pneumonitis confirmed.”
- “ICI-associated sarcoid-like reaction diagnosed.”
- “Infection excluded.”
- “Progression excluded.”
- “Hold immunotherapy.”
- “Restart immunotherapy.”
- “Start steroids.”
- “Toxicity grade assigned.”

### 12.5 Pass Condition

ICI-related mimics remain visible without CIP/SLR diagnosis, infection/progression exclusion, immunotherapy management, steroid recommendation, or toxicity grading.

---

## 13. Pulmonary Lymphangitic Carcinomatosis / Malignancy Mimic Prompt Parity

### 13.1 Allowed Prompt

The platform may show:

- PLC mimic prompt,
- malignancy recurrence/progression prompt,
- septal/peribronchovascular feature prompt,
- asymmetric interstitial process prompt,
- PET/CT ambiguity prompt,
- oncology review prompt.

### 13.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| known malignancy plus new interstitial/septal abnormality | PLC/malignancy mimic visible |
| septal thickening or peribronchovascular thickening/infiltration | PLC feature prompt visible |
| pleural effusion, lymphadenopathy, nodularity, asymmetric disease | malignancy mimic prompt visible |
| ILD/infection/edema-like appearance with nonresponse or progression | re-review prompt visible |
| PET/CT ambiguity present | PET/CT ambiguity visible |
| malignancy history missing | malignancy context incomplete |
| rapid dyspnea progression | urgent review prompt visible |

### 13.3 Required Allowed Language

- “PLC mimic prompt is visible, especially with malignancy context and compatible imaging ambiguity.”
- “Septal/peribronchovascular features are prompt-level features, not diagnosis.”
- “PET/CT ambiguity does not settle recurrence.”
- “Oncology review prompt remains visible where relevant.”
- “Final diagnosis is not established by this platform.”

### 13.4 Blocked Language

- “Pulmonary lymphangitic carcinomatosis diagnosed.”
- “Cancer recurrence diagnosed.”
- “Malignancy excluded.”
- “PET/CT confirms recurrence.”
- “Biopsy should be performed.”
- “Oncology treatment should change.”

### 13.5 Pass Condition

PLC/malignancy mimic remains visible without diagnosis, recurrence confirmation/exclusion, PET/CT interpretation authority, biopsy decision, or oncology management.

---

## 14. Sarcoid-Like Reaction / Lymphoma / Recurrence Ambiguity Prompt Parity

### 14.1 Allowed Prompt

The platform may show:

- sarcoid-like reaction prompt,
- lymphoma relapse mimic prompt,
- malignancy recurrence ambiguity prompt,
- FDG-avid lymphadenopathy ambiguity prompt,
- tissue/pathology context prompt,
- oncology/pulmonology/pathology review prompt.

### 14.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| cancer history plus new hilar/mediastinal lymphadenopathy | recurrence vs SLR ambiguity visible |
| lymphoma history plus FDG-avid nodes | lymphoma relapse vs sarcoid-like ambiguity visible |
| nonnecrotizing granulomas in cancer patient | malignancy not excluded by platform |
| ICI exposure plus sarcoid-like nodes/nodules | ICI-SLR vs recurrence prompt visible |
| tissue/pathology context missing | pathology evidence gap visible |
| PET/CT ambiguity present | PET ambiguity prompt visible |
| systemic symptoms or rapid progression | urgent review visible where relevant |

### 14.3 Required Allowed Language

- “Sarcoid-like reaction and malignancy recurrence remain ambiguous.”
- “FDG-avid lymphadenopathy does not settle recurrence in this platform.”
- “Histology/pathology context remains review-visible, but biopsy decision is outside platform authority.”
- “Lymphoma relapse is not excluded by this platform.”
- “Final diagnosis is not established by this platform.”

### 14.4 Blocked Language

- “Sarcoid-like reaction confirmed.”
- “Lymphoma relapse excluded.”
- “Cancer recurrence excluded.”
- “Biopsy should be performed.”
- “PET/CT proves benign sarcoid-like reaction.”
- “Oncology management should change.”

### 14.5 Pass Condition

Sarcoid-like reaction / lymphoma / recurrence ambiguity remains visible without SLR diagnosis, malignancy exclusion, biopsy decision, or oncology management.

---

## 15. Acute Danger / Urgent Review Prompt Parity

### 15.1 Allowed Prompt

The platform may show:

- urgent review prompt,
- acute overlay prompt,
- infection / hemorrhage / vascular / edema / therapy toxicity prompt,
- severe respiratory status warning,
- unstable-context prompt.

### 15.2 Trigger States

| Trigger State | Required Prompt |
|---|---|
| acute hypoxemia | urgent review visible |
| rapid dyspnea progression | urgent review visible |
| fever or systemic illness | infection/systemic mimic visible |
| hemoptysis or anemia | hemorrhage/malignancy/infection prompt visible |
| immunosuppression | opportunistic infection and therapy toxicity visible |
| known malignancy with new findings | malignancy/PLC/recurrence prompt visible |
| post-radiation new opacity | RP/infection/recurrence/drug/ICI overlap visible |
| ICI exposure with new pulmonary findings | CIP/infection/progression/SLR prompt visible |
| severe or worsening respiratory status | urgent review visible |

### 15.3 Required Allowed Language

- “Urgent review prompt remains visible where relevant.”
- “Acute danger must not wait for differential naming.”
- “Infection, hemorrhage, vascular, edema, therapy toxicity, and malignancy prompts remain visible where relevant.”
- “The platform does not triage, diagnose, or treat.”

### 15.4 Blocked Language

- “No urgent review needed.”
- “Infection excluded.”
- “Hemorrhage excluded.”
- “Vascular cause excluded.”
- “Acute exacerbation confirmed.”
- “Start treatment.”
- “Manage as outpatient.”
- “Emergency triage decision made.”

### 15.5 Pass Condition

Urgent review remains visible without triage, diagnosis, exclusion, or treatment authority.

---

## 16. Cross-Mimic Priority Order

When multiple prompts are present, visibility priority is:

1. acute instability / urgent danger,
2. infection / hemorrhage / vascular / severe therapy toxicity,
3. malignancy / recurrence / PLC / lymphoma concern,
4. therapy-related mimics: radiation, ICI, drug-induced,
5. occupational / beryllium / exposure-related mimics,
6. aspiration / dependent injury / OP-overlap,
7. fungal / TB / NTM granulomatous mimics,
8. chronic ILD pattern family,
9. missing evidence,
10. source status and source limitation,
11. specialist/MDD review prompt,
12. working diagnosis caveat.

Priority rule:

> Chronic ILD family naming must not suppress acute danger, malignancy concern, infection concern, or treatment-related mimic visibility.

---

## 17. Source Limitation Display Rules

| Source Limitation | Required Display |
|---|---|
| treatment-heavy source | “Treatment content not imported; treatment_authority: none.” |
| diagnostic-performance source | “Feature visibility only; no automated interpretation.” |
| case-example source | “Cautionary example only; not a generalized rule.” |
| review-level source | “Review-level support; not primary diagnostic authority.” |
| limited-scope guideline | “Source scope limited; prompt visibility only.” |
| internal governance source | “Governance constraint only; not a clinical source.” |

---

## 18. Example Combined Prompt Outputs

### 18.1 Chronic Fibrosis With Missing Occupational History

Allowed output:

- “Occupational exposure prompt is visible.”
- “Occupational history is incomplete.”
- “HP, UIP/IPF, CTD-ILD, and occupational mimic prompts remain visible.”
- “Exposure history does not establish causation.”
- “Final diagnosis is not established by this platform.”

Blocked output:

- “Occupational ILD diagnosed.”
- “Asbestosis confirmed.”
- “Exposure caused disease.”

---

### 18.2 Granulomas With Missing Microbiology and Beryllium History

Allowed output:

- “Sarcoid-like, TB/NTM/fungal, HP, and beryllium prompts remain visible.”
- “Microbiology and occupational/beryllium exposure contexts are incomplete.”
- “Granulomas do not settle diagnosis.”
- “MDD / specialist review prompt remains visible.”

Blocked output:

- “Sarcoidosis confirmed.”
- “TB excluded.”
- “Berylliosis excluded.”
- “Biopsy or treatment decision made.”

---

### 18.3 Post-Radiation New GGO

Allowed output:

- “Radiation pneumonitis / RILI prompt is visible.”
- “Infection, tumor recurrence, drug toxicity, ICI pneumonitis, and ILD progression remain competing prompts.”
- “Radiation field, timing, dose, and prior imaging context should remain visible.”
- “Treatment authority remains none.”

Blocked output:

- “Radiation pneumonitis diagnosed.”
- “Start steroids.”
- “Recurrence excluded.”
- “Radiation plan should change.”

---

### 18.4 ICI Exposure With FDG-Avid Nodes

Allowed output:

- “ICI-associated sarcoid-like reaction and malignancy recurrence remain ambiguous.”
- “FDG-avid lymphadenopathy does not settle recurrence in this platform.”
- “Infection and sarcoidosis-like mimics remain visible where relevant.”
- “Oncology / pulmonology / pathology review prompt remains visible.”

Blocked output:

- “ICI-SLR diagnosed.”
- “Recurrence excluded.”
- “Biopsy should be performed.”
- “Stop immunotherapy.”

---

### 18.5 Septal Thickening in Known Malignancy

Allowed output:

- “PLC mimic prompt is visible.”
- “Septal/peribronchovascular features are prompt-level features, not diagnosis.”
- “Infection, edema, chronic ILD, and malignancy recurrence remain competing prompts.”
- “Oncology review prompt remains visible where relevant.”

Blocked output:

- “PLC diagnosed.”
- “Cancer recurrence confirmed.”
- “Infection excluded.”
- “Oncology treatment should change.”

---

## 19. Testable Expectations for v0.8.4

Future test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| HRMP_001 | Occupational prompt remains visible without diagnosis |
| HRMP_002 | Beryllium prompt remains visible without BeS/CBD diagnosis |
| HRMP_003 | TB/NTM/fungal prompts remain visible without infection diagnosis/exclusion |
| HRMP_004 | Aspiration prompt remains visible without aspiration diagnosis |
| HRMP_005 | Drug-induced ILD prompt remains visible without causality assignment |
| HRMP_006 | Radiation pneumonitis prompt remains visible without RP diagnosis |
| HRMP_007 | ICI pneumonitis / ICI-SLR prompts remain visible without oncology management |
| HRMP_008 | PLC prompt remains visible without malignancy diagnosis |
| HRMP_009 | Sarcoid-like reaction / lymphoma / recurrence ambiguity is preserved |
| HRMP_010 | Acute danger outranks chronic pattern naming |
| HRMP_011 | Missing evidence is listed |
| HRMP_012 | Missing evidence is not exclusion |
| HRMP_013 | Source limitations are visible |
| HRMP_014 | Treatment-heavy source warnings are visible |
| HRMP_015 | Case examples do not become generalized rules |
| HRMP_016 | Diagnostic-performance sources do not automate interpretation |
| HRMP_017 | MDD/specialist review prompt remains visible |
| HRMP_018 | Diagnostic authority remains none |
| HRMP_019 | Treatment authority remains none |
| HRMP_020 | Public readiness remains false |
| HRMP_021 | Clinically reviewed remains false |

---

## 20. Failure Modes

The following are explicit v0.8.4 failures.

| Failure Mode | Why It Fails |
|---|---|
| Source-limited prompt becomes diagnosis | Violates diagnostic_authority none |
| Missing evidence becomes exclusion | Violates evidence governance |
| Treatment-heavy source imports treatment | Violates treatment_authority none |
| Diagnostic-performance source automates HRCT/PET interpretation | Creates test authority |
| Case report becomes general rule | Violates source hierarchy |
| Occupational exposure becomes causation | Scope violation |
| BeLPT context becomes CBD diagnosis | Test interpretation authority leak |
| TB/NTM/fungal mimic becomes infection exclusion | Unsafe closure |
| Aspiration prompt becomes aspiration diagnosis | Diagnostic authority leak |
| DI-ILD prompt becomes drug causality | Treatment/diagnostic authority leak |
| RP/CIP prompt becomes steroid or therapy decision | Treatment authority leak |
| PLC prompt becomes malignancy diagnosis | Diagnostic authority leak |
| Sarcoid-like reaction source excludes malignancy | Unsafe closure |
| PET/CT ambiguity settles recurrence | Test interpretation authority leak |
| Urgent review omitted in acute danger | Safety visibility failure |
| MDD/specialist review omitted in cross-domain uncertainty | Review governance failure |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 21. Acceptance Criteria

v0.8.4 is accepted only if:

- high-risk mimic prompts remain prompts, not diagnoses,
- all major v0.8 high-risk mimic families have source-limited prompt rules,
- missing evidence remains visible,
- overlap states remain visible,
- urgent review remains visible where relevant,
- MDD/specialist review remains visible where relevant,
- treatment-heavy source warnings are preserved,
- diagnostic-performance sources are constrained,
- case-example sources are constrained,
- no treatment recommendations appear,
- no test/procedure orders appear,
- no follow-up intervals appear,
- full domain parity remains unopened,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 22. Next Step

The next recommended step is:

- v0.8.5 — High-Risk Mimic Test Case Pack

v0.8.5 should test:

- occupational exposure missing evidence,
- beryllium vs sarcoidosis mimic,
- granulomas with missing microbiology,
- TB/NTM/fungal mimic visibility,
- aspiration / OP-like overlap,
- drug-induced ILD temporal prompt,
- radiation pneumonitis vs infection/recurrence/drug/ICI overlap,
- ICI pneumonitis / ICI-SLR vs recurrence ambiguity,
- PLC mimicking ILD/infection/edema,
- sarcoid-like reaction vs lymphoma recurrence,
- urgent review priority,
- source limitation visibility,
- no diagnosis,
- no treatment,
- no public readiness,
- no clinical review.

---

## 23. Governance Statement

This high-risk mimic prompt parity file protects the platform from unsafe mimic erasure and unsafe mimic overdiagnosis.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not decide bronchoscopy.  
It does not decide BAL.  
It does not decide HRCT, PET/CT, microbiology, serology, occupational testing, or follow-up interval.  
It does not confirm infection.  
It does not exclude infection.  
It does not confirm malignancy.  
It does not exclude malignancy.  
It does not confirm therapy-related toxicity.  
It does not replace MDD.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The current principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

The v0.8.4 rule is:

> “High-risk mimic prompts may be visible, but source-limited prompts are not diagnoses.”