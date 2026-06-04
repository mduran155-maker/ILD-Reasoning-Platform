# ILD Reasoning Platform — High-Risk Mimic Family Matrix / Missing Evidence and Review Prompt Model v1

Version: v0.8.3  
Status: high_risk_mimic_family_matrix  
Scope: High-risk mimic families, missing evidence states, overlap states, urgent review states, and specialist review prompts  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the high-risk mimic family matrix for v0.8.

It follows:

- `docs/navigation/deferred_source_expansion_high_risk_mimic_source_intake_entry_gate_v1.md`
- `docs/navigation/high_risk_mimic_source_role_map_v1.md`
- `docs/navigation/high_risk_mimic_claim_to_source_mapping_table_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_differential_seal_v1.md`
- `docs/navigation/project_status_roadmap_checkpoint_v0_7.md`

This document does not open domain parity.

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

Its purpose is to define high-risk mimic families as prompt-visible, source-governed, missing-evidence-sensitive reasoning families before any domain parity is opened.

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

For v domain parity is opened.

The v0.8 rule remains:

> “Source intake precedes source claims. Source claims precede domain parity.”

For v0.8.3, this becomes:

> “High-risk mimics stay visible before they become domain rules.”

---

## 2. Relationship to Prior Layers

v0.8.3 inherits:

- v0.3 superimposed events logic,
- v0.4 source governance,
- v0.5 test case visibility discipline,
- v0.6 UIP parity and source backfill discipline,
- v0.7 non-UIP differential reasoning seal,
- v0.8.0 source intake gate,
- v0.8.1 source role map,
- v0.8.2 claim-to-source mapping.

This matrix is not a diagnostic engine.

It is a governance matrix for high-risk mimic visibility.

---

## 3. Current v0.8 Source Status

| Field | Status |
|---|---|
| source_intake_entry_gate | active |
| source_role_map | present |
| claim_to_source_mapping | initial_non_authoritative_complete |
| domain_parity | not_opened |
| occupational_claims | mapped_for_prompt_visibility |
| beryllium_claims | mapped_for_prompt_visibility |
| TB_claims | mapped_for_prompt_visibility |
| NTM_claims | mapped_for_prompt_visibility |
| fungal_claims | mapped_limited_treatment_heavy_or_cautionary |
| aspiration_claims | mapped_limited |
| drug_induced_ILD_claims | mapped_review_level |
| radiation_pneumonitis_claims | mapped_limited |
| checkpoint_inhibitor_pneumonitis_claims | mapped_review_level |
| PLC_claims | mapped_feature_visibility_limited |
| sarcoid_like_reaction_claims | mapped_ambiguity_limited |
| clinically_reviewed | false |
| public_ready | false |
| diagnostic_authority | none |
| treatment_authority | none |

---

## 4. Authority Constraints

The following constraints are mandatory across this matrix.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| domain_parity_open | false |
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

No mimic family may override these constraints.

---

## 5. Core Matrix Principle

A high-risk mimic prompt means:

- the mimic remains visible,
- source status is declared,
- missing evidence is exposed,
- competing explanations remain visible,
- overlap is allowed,
- review prompts remain visible,
- urgent review remains visible where relevant.

A high-risk mimic prompt does not mean:

- the mimic is diagnosed,
- the mimic is excluded,
- treatment is selected,
- testing is ordered,
- biopsy is decided,
- follow-up is scheduled,
- public-ready interpretation exists.

The platform must teach:

> “Do not name chronic ILD until high-risk mimics, missing evidence, and urgent overlays are visible.”

---

## 6. High-Risk Mimic Family Matrix

| Family ID | Mimic Family | v0.8 Status | Source Status | Allowed Reasoning Role | Blocked Closure |
|---|---|---|---|---|---|
| V08_FAM_OCC | Occupational ILD / pneumoconiosis / asbestosis | active_prompt_family | claims_mapped_non_authoritative | occupational exposure and dust-related mimic visibility | occupational ILD diagnosis |
| V08_FAM_BERYL | Beryllium sensitivity / chronic beryllium disease | active_prompt_family | claims_mapped_non_authoritative | beryllium exposure and sarcoid-mimic visibility | BeS/CBD diagnosis |
| V08_FAM_TB | Tuberculosis mimic | active_prompt_family | claims_mapped_non_authoritative | granulomatous infection mimic and microbiology gap visibility | TB diagnosis or exclusion |
| V08_FAM_NTM | NTM pulmonary disease mimic | active_prompt_family | claims_mapped_non_authoritative | clinical-radiologic-microbiologic integration prompt | NTM diagnosis or exclusion |
| V08_FAM_FUNGAL | Fungal mimic / histoplasmosis / aspergillosis / coccidioidomycosis | active_prompt_family_limited | limited_or_cautionary_claims_mapped | endemic/immunocompromised fungal mimic visibility | fungal diagnosis or exclusion |
| V08_FAM_ASP | Aspiration-related lung disease | active_prompt_family_limited | claims_mapped_limited | aspiration risk, dependent injury, OP-like overlap prompt | aspiration diagnosis |
| V08_FAM_DILD | Drug-induced / therapy-related ILD | active_prompt_family_review_level | review_level_claims_mapped | medication/therapy temporal relationship and alternative-cause prompt | DI-ILD diagnosis or drug causality |
| V08_FAM_RP_RILI | Radiation pneumonitis / radiation-induced lung injury | active_prompt_family_limited | claims_mapped_limited | radiation timing/field/context and mimic visibility | RP/RILI diagnosis |
| V08_FAM_CIP | Checkpoint inhibitor pneumonitis | active_prompt_family_review_level | review_level_claims_mapped | ICI exposure and pneumonitis/progression/infection overlap prompt | CIP diagnosis |
| V08_FAM_ICI_SLR | ICI-associated sarcoidosis-like reaction | active_prompt_family_limited | ambiguity_claims_mapped | recurrence vs sarcoid-like reaction ambiguity prompt | ICI-SLR diagnosis |
| V08_FAM_PLC | Pulmonary lymphangitic carcinomatosis | active_prompt_family_limited | feature_visibility_claims_mapped | malignancy mimic; septal/peribronchovascular pattern prompt | PLC diagnosis |
| V08_FAM_MALIGNANCY_LYMPHOMA | Malignancy / lymphoma / recurrence mimic | active_prompt_family_limited | ambiguity_claims_mapped | recurrence/lymphoma/sarcoid-like ambiguity prompt | malignancy or lymphoma diagnosis |
| V08_FAM_SLR_NEOPLASTIC | Sarcoid-like reaction in neoplastic patients | active_prompt_family_limited | ambiguity_claims_mapped | benign granulomatous lymphadenopathy vs recurrence prompt | SLR diagnosis or malignancy exclusion |
| V08_FAM_ACUTE_DANGER | Acute dangerous mimic / unstable overlay | inherited_active_safety_family | internal_governance_plus_prior_v0_5_v0_7 | urgent review priority prompt | exclusion or treatment |

---

## 7. General Mimic State Model

The following states may be assigned to any high-risk mimic family.

| State | Meaning | Required Behavior |
|---|---|---|
| MIMIC_VISIBLE | Mimic remains visible | Show prompt without diagnosis |
| MIMIC_SUPPORTING_FEATURES_PRESENT | Some features support mimic consideration | List features and limitations |
| MIMIC_WEAKENING_FEATURES_PRESENT | Some features weaken mimic consideration | Keep uncertainty and competing families visible |
| MIMIC_MISSING_EVIDENCE | Required evidence is missing | Show missing evidence; do not exclude |
| MIMIC_SOURCE_LIMITED | Source authority is limited, treatment-heavy, review-level, or case-only | Show source limitation |
| MIMIC_OVERLAP_WITH_ILD_PATTERN | Mimic overlaps UIP/NSIP/OP/HP/sarcoid-like pattern | Preserve both mimic and ILD family |
| MIMIC_OVERLAP_WITH_ACUTE_PROCESS | Mimic overlaps infection, edema, hemorrhage, vascular, or acute injury | Preserve urgent review prompt |
| MIMIC_OVERLAP_WITH_THERAPY | Mimic overlaps drug/radiation/ICI therapy timeline | Preserve therapy-context prompt |
| MIMIC_OVERLAP_WITH_MALIGNANCY | Mimic overlaps malignancy or recurrence concern | Preserve oncology review prompt |
| MIMIC_MDD_PROMPT_VISIBLE | Integrated review needed | Keep MDD/specialist review visible |
| MIMIC_URGENT_REVIEW_VISIBLE | Clinical danger possible | Urgent review prompt visible |
| MIMIC_DEFERRED_PARITY | Source mapping exists but domain parity not opened | Keep prompt only |
| MIMIC_NOT_DIAGNOSED | Explicit non-diagnosis status | Preserve diagnostic_authority none |

States may coexist.

Example:

- `MIMIC_VISIBLE`
- plus `MIMIC_MISSING_EVIDENCE`
- plus `MIMIC_OVERLAP_WITH_ILD_PATTERN`
- plus `MIMIC_SOURCE_LIMITED`
- plus `MIMIC_MDD_PROMPT_VISIBLE`

is valid.

The platform must not collapse this into diagnosis.

---

## 8. Occupational / Pneumoconiosis / Asbestosis Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| OCC_EXPOSURE_PROMPT | silica, asbestos, coal, hard metal, irritant gas, mineral dust, mixed occupational exposure possible | Keep occupational mimic visible |
| OCC_HISTORY_MISSING | occupational history absent or incomplete | Missing history does not exclude occupational ILD |
| OCC_LATENCY_PROMPT | exposure may have long latency | Show temporal uncertainty |
| OCC_PNEUMOCONIOSIS_PROMPT | nodular/fibrotic pattern and dust exposure context possible | Prompt only |
| OCC_ASBESTOSIS_PROMPT | asbestos exposure or lower-lung fibrosis/pleural clue context possible | Prompt only |
| OCC_HP_OVERLAP_PROMPT | workplace antigen exposure could overlap HP reasoning | Preserve HP and occupational prompts |
| OCC_GRANULOMATOUS_OVERLAP_PROMPT | beryllium or other granulomatous occupational mimic possible | Preserve sarcoid/beryllium mimic |
| OCC_MEDICOLEGAL_BLOCK | exposure causation or compensation implication appears | Block conclusion |
| OCC_REVIEW_PROMPT | occupational medicine review may be relevant | Show review prompt |

Blocked closure:

- occupational ILD diagnosed,
- asbestosis diagnosed,
- pneumoconiosis diagnosed,
- exposure causation assigned,
- compensation implication made,
- treatment or surveillance plan generated.

---

## 9. Beryllium / CBD Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| BERYL_EXPOSURE_PROMPT | beryllium occupational/environmental context possible | Keep beryllium prompt visible |
| BERYL_EXPOSURE_MISSING | beryllium exposure history incomplete | Show missing evidence |
| BERYL_BELPT_CONTEXT_PROMPT | BeLPT mentioned or missing | Show test context without interpretation |
| BERYL_BES_CBD_DISTINCTION_PROMPT | sensitization vs lung disease distinction relevant | Preserve distinction |
| BERYL_GRANULOMATOUS_PROMPT | granulomatous disease overlaps sarcoidosis | Keep berylliosis/sarcoid mimic visible |
| BERYL_PATHOLOGY_CONTEXT_MISSING | lung pathology not available/integrated | Show missing evidence |
| BERYL_OCC_REVIEW_PROMPT | occupational medicine review relevant | Show review prompt |

Blocked closure:

- BeS diagnosed,
- CBD diagnosed,
- BeLPT interpreted,
- sarcoidosis confirmed while beryllium context hidden,
- treatment plan created.

---

## 10. TB / NTM / Fungal Mimic Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| TB_MIMIC_VISIBLE | granulomatous disease, systemic symptoms, risk exposure, microbiology missing | Keep TB visible |
| TB_AFB_LIMITATION_PROMPT | AFB smear status present or absent | Show smear limitation; no interpretation authority |
| TB_NAAT_LIMITATION_PROMPT | NAAT status present or absent | Show limitation; no exclusion/confirmation |
| TB_CULTURE_CONTEXT_MISSING | culture not available/integrated | Show microbiology gap |
| NTM_MIMIC_VISIBLE | nodular/bronchiectatic/cavitary/chronic infection context possible | Keep NTM visible |
| NTM_MULTI_DOMAIN_PROMPT | clinical/radiologic/microbiologic integration needed | Preserve review prompt |
| NTM_FOLLOWUP_UNCERTAINTY | NTM suspicion incomplete | No interval; review prompt only |
| FUNGAL_MIMIC_VISIBLE | endemic exposure, immunosuppression, granuloma, nodules, consolidation, sarcoid-like pattern possible | Keep fungal mimic visible |
| FUNGAL_SOURCE_LIMITED | source treatment-heavy or case-only | Show source limitation |
| FUNGAL_MICROBIOLOGY_MISSING | fungal testing/culture/antigen/pathology context missing | Show evidence gap |
| INFECTION_URGENT_PROMPT | fever/systemic illness/immunosuppression/acute worsening | Urgent review visible |

Blocked closure:

- TB diagnosed or excluded,
- NTM diagnosed or excluded,
- fungal infection diagnosed or excluded,
- microbiology ordered,
- isolation/public health instruction,
- antimicrobial/antifungal recommendation.

---

## 11. Aspiration Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| ASP_RISK_PROMPT | dysphagia, reflux, altered consciousness, neurologic disease, aspiration risk, dependent opacity possible | Keep aspiration visible |
| ASP_RISK_MISSING | aspiration risk not documented | Show missing evidence |
| ASP_SILENT_MICROASPIRATION_PROMPT | recurrent/dependent/OP-like or unexplained findings with incomplete history | Prompt only |
| ASP_OP_OVERLAP_PROMPT | OP-like consolidation overlaps aspiration risk | Preserve OP and aspiration prompts |
| ASP_INFECTION_OVERLAP_PROMPT | aspiration and infection overlap possible | Keep infection visible |
| ASP_DEPENDENT_INJURY_PROMPT | dependent distribution or dependent consolidation relevant | Show pattern prompt |
| ASP_REVIEW_PROMPT | clinical/swallow/pulmonary review relevant | Show review prompt |

Blocked closure:

- aspiration pneumonia diagnosed,
- aspiration-related ILD diagnosed,
- antibiotics recommended,
- swallow study ordered,
- airway/feeding management advised,
- follow-up interval set.

---

## 12. Drug-Induced / Therapy-Related ILD Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| DILD_MEDICATION_PROMPT | medication or therapy exposure temporally relevant | Keep drug-induced mimic visible |
| DILD_MEDICATION_HISTORY_MISSING | medication history incomplete | Show missing evidence |
| DILD_TEMPORAL_PROMPT | onset after drug/therapy exposure possible | Show temporal relationship without causality |
| DILD_ALTERNATIVE_CAUSE_PROMPT | infection, progression, edema, radiation, ICI, HP, CTD, OP/NSIP overlap possible | Preserve alternatives |
| DILD_PATTERN_OVERLAP_PROMPT | NSIP-like, OP-like, DAD-like, acute injury, or fibrosis pattern possible | Prompt only |
| DILD_ONCOLOGY_CONTEXT_PROMPT | anti-cancer therapy context relevant | Oncology review visible |
| DILD_SOURCE_LIMITED | review-level source authority | Show limitation |
| DILD_URGENT_PROMPT | acute/worsening respiratory status possible | Urgent review visible |

Blocked closure:

- DI-ILD diagnosed,
- causality assigned to a drug,
- drug stopped/rechallenged,
- steroids recommended,
- oncology therapy changed,
- treatment plan created.

---

## 13. Radiation Pneumonitis / RILI Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| RP_RADIATION_HISTORY_PROMPT | thoracic radiation history present or missing | Keep RP/RILI visible |
| RP_FIELD_TIMING_MISSING | radiation field, timing, dose, fractionation, prior imaging incomplete | Show missing evidence |
| RP_TEMPORAL_PROMPT | timing may support acute RP vs chronic RPF context | Temporal prompt only |
| RP_FIELD_CONFORMITY_PROMPT | imaging may relate to radiation field | Show context without diagnosis |
| RP_INFECTION_OVERLAP_PROMPT | infection can mimic or coexist | Keep infection visible |
| RP_TUMOR_PROGRESSION_OVERLAP_PROMPT | tumor progression/recurrence possible | Keep oncology mimic visible |
| RP_DILD_CIP_OVERLAP_PROMPT | drug/ICI pneumonitis overlap possible | Keep therapy-related prompts visible |
| RP_SOURCE_LIMITED | treatment-heavy source | Show limitation |
| RP_URGENT_PROMPT | severe respiratory decline possible | Urgent review visible |

Blocked closure:

- radiation pneumonitis diagnosed,
- radiation fibrosis diagnosed,
- steroids recommended,
- radiation plan changed,
- follow-up interval set,
- recurrence excluded.

---

## 14. Checkpoint Inhibitor Pneumonitis / ICI-SLR Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| ICI_EXPOSURE_PROMPT | checkpoint inhibitor exposure present or missing | Keep ICI-related mimic visible |
| CIP_MIMIC_PROMPT | new GGO/consolidation/nodules/respiratory symptoms during or after ICI | Prompt only |
| CIP_INFECTION_OVERLAP_PROMPT | infection possible or microbiology missing | Keep infection visible |
| CIP_RP_OVERLAP_PROMPT | prior radiation overlaps ICI exposure | Keep RP/CIP overlap visible |
| CIP_PROGRESSION_OVERLAP_PROMPT | tumor progression possible | Keep oncology prompt visible |
| ICI_SLR_PROMPT | new lymphadenopathy/nodules/FDG uptake after ICI | Keep SLR/recurrence ambiguity visible |
| ICI_SOURCE_LIMITED | review-level or treatment-heavy source | Show limitation |
| ICI_URGENT_PROMPT | hypoxemia or rapid respiratory decline | Urgent review visible |

Blocked closure:

- CIP diagnosed,
- ICI-SLR diagnosed,
- infection excluded,
- progression excluded,
- immunotherapy held/restarted,
- steroids recommended,
- toxicity grade assigned.

---

## 15. Pulmonary Lymphangitic Carcinomatosis / Malignancy Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| PLC_MIMIC_VISIBLE | malignancy history or unexplained septal/peribronchovascular pattern possible | Keep PLC mimic visible |
| PLC_FEATURE_PROMPT | septal thickening, peribronchovascular thickening, nodularity, lymphadenopathy, pleural effusion, asymmetric process possible | Feature prompt only |
| PLC_INFECTION_EDEMA_OVERLAP | infection or edema could mimic PLC or vice versa | Keep all visible |
| PLC_ILD_MIMIC_PROMPT | chronic ILD-like pattern or nonresponse to empiric therapy | Prompt malignancy mimic review |
| PLC_PET_CT_AMBIGUITY | PET/CT or HRCT ambiguity present | No interpretation authority |
| MALIGNANCY_HISTORY_MISSING | cancer history incomplete or not integrated | Show missing evidence |
| ONCOLOGY_REVIEW_PROMPT | recurrence/progression concern possible | Oncology review visible |
| PLC_SOURCE_LIMITED | diagnostic performance/case-level source | Show limitation |
| PLC_URGENT_PROMPT | rapid dyspnea/progression or severe symptoms | Urgent review visible |

Blocked closure:

- PLC diagnosed,
- malignancy diagnosed,
- recurrence diagnosed,
- PET/CT interpreted,
- biopsy decided,
- oncology management recommended.

---

## 16. Sarcoid-Like Reaction / Lymphoma / Recurrence Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| SLR_NEOPLASTIC_PROMPT | new lymphadenopathy or granulomatous findings in cancer patient | Keep SLR and malignancy visible |
| LYMPHOMA_RELAPSE_MIMIC_PROMPT | lymphoma history plus new FDG-avid nodes or granulomatous findings | Preserve relapse vs SLR ambiguity |
| PET_CT_AMBIGUITY_PROMPT | FDG-avid lymphadenopathy or nodules | Show ambiguity; no diagnosis |
| HISTOLOGY_CONFIRMATION_CONTEXT | tissue confirmation discussed by source | Review prompt only; no biopsy decision |
| ICI_SLR_OVERLAP_PROMPT | ICI exposure and sarcoid-like findings | Keep ICI-SLR vs recurrence prompt visible |
| MALIGNANCY_NOT_EXCLUDED_PROMPT | malignancy context incomplete | Do not exclude malignancy |
| SLR_SOURCE_LIMITED | auxiliary/case-series source | Show limitation |
| ONCOLOGY_MDD_PROMPT | oncology/pulmonology/pathology review relevant | Show review prompt |

Blocked closure:

- sarcoid-like reaction diagnosed,
- lymphoma relapse excluded,
- malignancy excluded,
- biopsy recommended,
- oncology treatment changed,
- follow-up scheduled.

---

## 17. Missing Evidence Matrix

| Missing Evidence | Protected Mimic Families |
|---|---|
| occupational exposure history | occupational ILD; beryllium; pneumoconiosis; asbestosis; sarcoid mimic |
| beryllium exposure context | berylliosis; sarcoidosis mimic |
| BeLPT context | beryllium sensitization / CBD prompt |
| microbiology data | TB; NTM; fungal; sarcoidosis mimic; OP-like consolidation |
| AFB smear / culture / NAAT context | TB mimic |
| repeated sputum / bronchial wash / lavage context | NTM mimic |
| fungal culture / antigen / serology / pathology context | fungal mimic |
| endemic travel or residence | histoplasmosis; coccidioidomycosis; fungal mimic |
| immunosuppression context | fungal; TB; NTM; opportunistic infection; therapy toxicity |
| aspiration risk | aspiration-related lung disease; OP-like consolidation; infection |
| medication / therapy history | DI-ILD; OP-like; NSIP-like; acute injury; ICI-SLR |
| radiation history | RP/RILI; recurrence mimic; drug/ICI overlap |
| radiation field / timing / dose context | RP/RILI |
| checkpoint inhibitor exposure | CIP; ICI-SLR; recurrence mimic |
| malignancy history | PLC; lymphoma; recurrence; SLR |
| PET/CT context | PLC; recurrence; lymphoma; SLR |
| tissue/pathology context | malignancy; infection; granulomatous disease; beryllium; PLC |
| prior imaging | therapy toxicity; recurrence; infection; progression |
| response/nonresponse to empiric therapy | infection; malignancy; DI-ILD; RP; CIP; PLC |
| urgent clinical status | acute infection; severe therapy toxicity; malignancy progression; acute respiratory failure |
| MDD/specialist review status | all high-risk mimic families |

Rule:

> Missing evidence must stay visible and must not become exclusion.

---

## 18. Overlap Matrix

| Overlap | Required Behavior |
|---|---|
| Occupational ILD vs HP | Preserve exposure and HP prompts |
| Occupational ILD vs UIP/IPF | Preserve occupational and UIP/IPF boundary prompts |
| Berylliosis vs sarcoidosis | Preserve beryllium exposure and sarcoid-like prompts |
| TB vs sarcoidosis | Preserve TB and sarcoid-like prompts |
| NTM vs sarcoidosis | Preserve NTM and sarcoid-like prompts |
| Fungal infection vs sarcoidosis | Preserve fungal and sarcoid-like prompts |
| Aspiration vs OP | Preserve aspiration and OP-like prompts |
| Aspiration vs infection | Preserve aspiration and infection prompts |
| DI-ILD vs NSIP/OP | Preserve medication history and NSIP/OP prompts |
| DI-ILD vs infection | Preserve medication and infection prompts |
| Radiation pneumonitis vs infection | Preserve RP and infection prompts |
| Radiation pneumonitis vs recurrence | Preserve RP and oncology prompts |
| Radiation pneumonitis vs CIP | Preserve radiation and ICI exposure prompts |
| CIP vs infection | Preserve ICI and infection prompts |
| CIP vs progression | Preserve ICI toxicity and oncology progression prompts |
| ICI-SLR vs malignancy recurrence | Preserve SLR and recurrence ambiguity |
| PLC vs ILD | Preserve PLC and ILD family prompts |
| PLC vs infection/edema | Preserve PLC, infection, and edema prompts |
| Sarcoid-like reaction vs lymphoma relapse | Preserve SLR and lymphoma relapse ambiguity |
| Acute mimic vs chronic fibrosis | Preserve acute danger separately from chronic baseline |

Rule:

> Overlap must be represented as coexistence, not as one winning label.

---

## 19. Urgent Review Matrix

| Urgent Trigger | Mimic Families Protected | Required Behavior |
|---|---|---|
| acute hypoxemia | infection; CIP; RP; hemorrhage; vascular; acute respiratory failure | urgent review prompt visible |
| rapid dyspnea progression | infection; PLC; RP; CIP; acute exacerbation-like overlay | urgent review prompt visible |
| fever or systemic illness | TB; NTM; fungal; aspiration; drug reaction; malignancy | infection/systemic mimic visible |
| hemoptysis or anemia | infection; malignancy; hemorrhage; vascular | urgent review prompt visible |
| immunosuppression | fungal; TB; NTM; opportunistic infection; therapy toxicity | infection and toxicity prompts visible |
| known malignancy with new septal thickening | PLC; recurrence; infection; edema | oncology mimic visible |
| new FDG-avid lymphadenopathy after cancer therapy | recurrence; lymphoma; SLR; sarcoidosis | PET ambiguity visible |
| post-radiation new GGO/consolidation | RP; infection; recurrence; DI-ILD; CIP | therapy overlap visible |
| ICI exposure with new pulmonary findings | CIP; infection; RP; progression; SLR | ICI mimic visible |
| nonresponse to empiric therapy | PLC; infection; DI-ILD; RP; CIP | re-review prompt visible |
| severe or worsening respiratory status | all acute high-risk families | urgent review visible |

Urgent review rule:

> Urgent review prompts do not diagnose, triage, or treat; they prevent unsafe closure.

---

## 20. Specialist / MDD Review Matrix

| Review Domain | Trigger | Required Prompt |
|---|---|---|
| pulmonology | ILD or mimic uncertainty | pulmonary review visible |
| thoracic radiology | HRCT pattern, temporal change, PET/CT ambiguity | radiology review visible |
| pathology | granuloma, malignancy, infection, PLC, unclear tissue findings | pathology review visible |
| microbiology | TB/NTM/fungal/infectious mimic possible | microbiology review visible |
| occupational medicine | occupational/beryllium/asbestos/silica/hard metal context possible | occupational review visible |
| rheumatology | sarcoid/CTD/immune overlap possible | rheumatology review visible |
| oncology | malignancy recurrence, PLC, lymphoma, ICI-SLR, therapy toxicity possible | oncology review visible |
| radiation oncology | RP/RILI/radiation field context possible | radiation oncology review visible |
| MDD | cross-domain uncertainty or discordance | MDD prompt visible |
| urgent clinical assessment | instability or dangerous acute mimic possible | urgent review visible |

Review rule:

> Specialist review visibility is not specialist replacement.

---

## 21. Output Requirements for Future v0.8 Files

Every future v0.8 high-risk mimic-facing output should include where relevant:

| Output Element | Required |
|---|---|
| mimic_family_prompt | yes |
| supporting_features | yes |
| weakening_features | yes |
| missing_evidence | yes |
| competing_families | yes |
| overlap_state | yes |
| source_status | yes |
| claim_mapping_status | yes |
| source_role_class | yes |
| treatment_heavy_warning_where_relevant | yes |
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

## 22. Allowed Language

Allowed language examples:

- “Occupational exposure prompt is visible.”
- “Beryllium / sarcoid-mimic prompt remains visible.”
- “TB mimic remains visible because microbiology context is incomplete.”
- “NTM prompt requires clinical-radiologic-microbiologic integration visibility.”
- “Fungal mimic remains visible; source scope is treatment-heavy and limited.”
- “Aspiration risk prompt remains visible.”
- “Medication / therapy-related ILD mimic remains visible.”
- “Radiation timing and field context are missing.”
- “ICI exposure creates therapy-related mimic visibility but not diagnosis.”
- “PLC mimic prompt is visible, especially with malignancy context and compatible imaging ambiguity.”
- “Sarcoid-like reaction and malignancy recurrence remain ambiguous.”
- “PET/CT ambiguity does not settle recurrence.”
- “MDD / specialist review prompt remains visible.”
- “Urgent review prompt remains visible where relevant.”
- “Final diagnosis is not established by this platform.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”
- “clinically_reviewed: false”

---

## 23. Blocked Language

Blocked language examples:

- “Occupational ILD diagnosed.”
- “Asbestosis diagnosed.”
- “Berylliosis confirmed.”
- “TB excluded.”
- “NTM excluded.”
- “Fungal infection excluded.”
- “Aspiration pneumonia diagnosed.”
- “Drug-induced ILD confirmed.”
- “Radiation pneumonitis diagnosed.”
- “Checkpoint inhibitor pneumonitis confirmed.”
- “Pulmonary lymphangitic carcinomatosis diagnosed.”
- “Cancer recurrence diagnosed.”
- “Lymphoma relapse excluded.”
- “Sarcoid-like reaction confirmed.”
- “Order PET/CT.”
- “Perform biopsy.”
- “Perform bronchoscopy.”
- “Start antifungal treatment.”
- “Start steroids.”
- “Stop immunotherapy.”
- “Change radiation plan.”
- “Follow up every X months.”
- “No MDD needed.”
- “Public-ready.”
- “Clinically reviewed.”

---

## 24. Testable Expectations for Future v0.8 Test Cases

Future v0.8 test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| HRM_001 | Mimic prompt remains visible without diagnosis |
| HRM_002 | Missing evidence is listed |
| HRM_003 | Missing evidence does not exclude mimic |
| HRM_004 | Source role class is visible |
| HRM_005 | Treatment-heavy source warning is visible where relevant |
| HRM_006 | Case-example source does not become rule |
| HRM_007 | Diagnostic-performance source does not create test interpretation |
| HRM_008 | Competing families remain visible |
| HRM_009 | Overlap states are preserved |
| HRM_010 | Urgent review prompt remains visible where relevant |
| HRM_011 | MDD/specialist review prompt remains visible |
| HRM_012 | Domain parity remains closed until specific parity step |
| HRM_013 | Diagnostic authority remains none |
| HRM_014 | Treatment authority remains none |
| HRM_015 | Public readiness remains false |
| HRM_016 | Clinically reviewed remains false |

---

## 25. Failure Modes

The following are explicit v0.8.3 failures.

| Failure Mode | Why It Fails |
|---|---|
| Mimic prompt becomes diagnosis | Violates diagnostic_authority none |
| Missing evidence becomes exclusion | Violates evidence governance |
| Treatment-heavy source imports therapy recommendation | Violates treatment_authority none |
| Diagnostic-performance source becomes automated test interpretation | Creates test authority |
| Case report becomes generalized rule | Violates evidence hierarchy |
| Source-limited family receives parity prematurely | Violates v0.8 sequencing |
| PET/CT ambiguity settles recurrence | Creates diagnostic authority |
| PLC feature prompt becomes PLC diagnosis | Violates diagnostic_authority none |
| Sarcoid-like reaction source excludes malignancy | Unsafe closure |
| TB/NTM/fungal prompt excludes infection | Unsafe exclusion |
| RP/CIP prompt creates steroid or therapy decision | Treatment authority leak |
| Occupational source creates causation or medicolegal conclusion | Scope violation |
| BeLPT context becomes BeS/CBD diagnosis | Test interpretation authority leak |
| MDD omitted in cross-domain uncertainty | Weakens review governance |
| Urgent review omitted in acute danger | Weakens safety visibility |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 26. Acceptance Criteria

v0.8.3 is accepted only if:

- high-risk mimic families are represented,
- families are prompt states, not diagnoses,
- source status remains visible,
- source role class remains visible,
- treatment-heavy sources remain constrained,
- diagnostic-performance sources remain constrained,
- case-example sources remain constrained,
- missing evidence states are represented,
- overlap states are represented,
- urgent review states are represented,
- specialist/MDD review prompts are represented,
- domain parity remains closed,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 27. Next Step

The next recommended step is:

- v0.8.4 — High-Risk Mimic Prompt Parity / Source-Limited Visibility Rules

v0.8.4 should convert this family matrix into source-limited prompt parity rules.

It should cover:

- occupational / beryllium prompt visibility,
- TB / NTM / fungal mimic visibility,
- aspiration / OP-overlap visibility,
- drug / radiation / ICI therapy-related mimic visibility,
- PLC / malignancy / lymphoma / sarcoid-like reaction visibility,
- missing evidence visibility,
- urgent review visibility,
- MDD/specialist review visibility,
- source limitation visibility,
- no diagnostic authority,
- no treatment authority,
- public_ready remains false,
- clinically_reviewed remains false.

v0.8.4 must not create full diagnostic domain parity.

---

## 28. Governance Statement

This high-risk mimic family matrix organizes v0.8 mimic visibility.

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

For v0.8.3:

> “High-risk mimics stay visible before they become domain rules.”