# ILD Reasoning Platform — Non-UIP Fibrotic ILD Differential Lock Checklist v1

Version: v0.7.9  
Status: pre_seal_lock_checklist  
Scope: Non-UIP fibrotic ILD differential reasoning lock readiness  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This checklist verifies that v0.7 — Non-UIP Fibrotic ILD Differential Reasoning Expansion is ready for structural sealing.

It does not seal v0.7.  
It does not diagnose hypersensitivity pneumonitis.  
It does not diagnose CTD-ILD.  
It does not diagnose NSIP.  
It does not diagnose organizing pneumonia.  
It does not diagnose sarcoidosis.  
It does not diagnose occupational ILD.  
It does not diagnose drug toxicity.  
It does not diagnose infection.  
It does not recommend treatment.  
It does not decide biopsy, BAL, serum IgG, HRCT, PFT, serology, microbiology, tissue sampling, or follow-up interval.  
It does not create public readiness.  
It does not make v0.7 clinically reviewed.

Its role is to confirm that the non-UIP differential reasoning chain is present, source-governed, testable, and non-authoritative before structural seal.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

---

## 2. v0.7 Chain Under Lock Review

The following v0.7 files must be present before sealing.

| Version | File | Role | Lock Readiness |
|---|---|---|---|
| v0.7.0 | docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md | Entry gate and source-governed scope contract | required |
| v0.7.1 | docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md | Source anchor map and source debt register | required |
| v0.7.2 | docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md | Claim-to-source mapping table | required |
| v0.7.3 | docs/data/schema/non_uip_differential_reasoning_family_matrix_v1.md | Differential family matrix | required |
| v0.7.4 | docs/data/schema/fibrotic_hp_reasoning_parity_v1.md | Fibrotic HP reasoning parity | required |
| v0.7.5 | docs/data/schema/ctd_ild_sard_ild_context_prompt_parity_v1.md | CTD-ILD / SARD-ILD context prompt parity | required |
| v0.7.6 | docs/data/schema/nsip_op_unclassifiable_iip_reasoning_parity_v1.md | NSIP / OP / unclassifiable IIP reasoning parity | required |
| v0.7.7 | docs/data/schema/sarcoidosis_granulomatous_differential_prompt_parity_v1.md | Sarcoidosis / granulomatous differential prompt parity | required |
| v0.7.8 | docs/test_cases/non_uip_fibrotic_ild_differential_test_case_pack_v1.md | Non-UIP differential test case pack | required |
| v0.7.9 | docs/navigation/non_uip_fibrotic_ild_differential_lock_checklist_v1.md | Pre-seal lock checklist | current |

Lock condition:

- All v0.7.0 through v0.7.8 files must exist.
- Each file must preserve non-authority.
- Each file must preserve source status visibility.
- Each file must preserve missing evidence visibility.
- Each file must preserve mimic and overlap visibility.
- Each file must preserve MDD prompt visibility where relevant.
- Each file must preserve urgent review prompt visibility where relevant.
- No v0.7 file may weaken v0.3, v0.4, v0.5, v0.6, or v0.6.R1/R2/R3 constraints.

---

## 3. Prior Layer Inheritance Checklist

v0.7 must inherit the following platform layers.

| Prior Layer | Required Inheritance |
|---|---|
| v0.3 Superimposed Events Core | Multiple processes may coexist; single-label closure remains blocked |
| v0.4 Evidence Layer / Source Review Governance | Source-sensitive claims require anchor, review status, and limitation visibility |
| v0.5 Test Case Coverage Expansion | Missing evidence, mimics, MDD, urgent review, and non-authority remain visible |
| v0.6 UIP Parity Seal | UIP-facing pattern reasoning remains non-diagnostic and source-governed |
| v0.6.R1 Source Review Debt Register | Source-review debt remains visible |
| v0.6.R2 Claim-to-Source Mapping Table | Claim mapping is required before stronger claims |
| v0.6.R3 Source Status Correction / Backfill Lock | Structural seal is not clinical source-review seal |

Lock condition:

- v0.7 must not become a diagnostic engine.
- v0.7 must not hide source debt.
- v0.7 must not convert available sources into clinically reviewed status.
- v0.7 must not convert differential prompts into differential diagnoses.
- v0.7 must not convert test cases into public readiness.

---

## 4. Source Anchor Lock Checklist

The following v0.7 source anchors must be declared and role-separated.

| Source ID | Required Role | Lock Readiness |
|---|---|---|
| V07_SRC_2020_ATS_JRS_ALAT_HP_GUIDELINE | Primary HP reasoning source | required |
| V07_SRC_2013_ATS_ERS_IIP_CLASSIFICATION | Primary IIP / NSIP / OP / unclassifiable source | required |
| V07_SRC_2023_ACR_CHEST_SARD_ILD_SCREEN_MONITOR | Primary SARD-ILD / CTD-ILD context source | required |
| V07_SRC_2020_ATS_SARCOIDOSIS_GUIDELINE | Primary sarcoidosis / granulomatous differential source | required |
| V07_SRC_2020_HP_CLINICIAN_SUMMARY | Auxiliary HP summary source | optional_auxiliary |
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | UIP/IPF boundary inheritance source | required_inheritance |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | PPF / progression inheritance source | required_inheritance |
| V07_SRC_INTERNAL_V06_R1_R2_R3_BACKFILL | Source-debt discipline inheritance | required |

Lock condition:

- Primary source roles must remain domain-limited.
- Auxiliary sources must not become primary authority.
- Internal governance sources must not replace clinical sources.
- Source availability must not be interpreted as clinical review.
- Source mapping must not be interpreted as public readiness.
- Dedicated parity for occupational ILD, drug toxicity, aspiration, and broad infection remains blocked until primary sources are selected and mapped.

---

## 5. Source Debt Lock Checklist

The following source debt must remain explicit.

| Debt Area | Required Status |
|---|---|
| Occupational ILD / pneumoconiosis / asbestosis | source_needed |
| Drug toxicity / therapy-related ILD | source_needed |
| Aspiration-related ILD | source_needed |
| Broad infection mimic / overlay | source_needed |
| Berylliosis dedicated parity | source_needed |
| TB / NTM / fungal dedicated parity | source_needed |
| Malignancy / lymphoma mimic dedicated parity | source_needed |
| Public readiness validation | not_allowed |
| Clinical review | false |

Lock condition:

- Source-needed domains may remain visible as prompts.
- Source-needed domains may not receive full parity rules.
- Source-needed domains may not be structurally sealed as domain parity.
- Source-needed domains may not diagnose, exclude, or recommend treatment.

---

## 6. Authority Lock Checklist

The following constraints must remain true across all v0.7 files.

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| clinically_reviewed | false |
| automated_HP_diagnosis | not_allowed |
| automated_CTD_ILD_diagnosis | not_allowed |
| automated_NSIP_diagnosis | not_allowed |
| automated_OP_diagnosis | not_allowed |
| automated_COP_diagnosis | not_allowed |
| automated_sarcoidosis_diagnosis | not_allowed |
| automated_occupational_ILD_diagnosis | not_allowed |
| automated_drug_toxicity_diagnosis | not_allowed |
| automated_infection_diagnosis | not_allowed |
| automated_aspiration_diagnosis | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_BAL_decision | not_allowed |
| automated_serology_order | not_allowed |
| automated_HRCT_order | not_allowed |
| automated_PFT_order | not_allowed |
| automated_microbiology_order | not_allowed |
| automated_follow_up_schedule | not_allowed |
| automated_treatment_selection | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_rheumatologist | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_occupational_medicine_review | not_allowed |
| replacement_of_urgent_review | not_allowed |

Lock condition:

- No v0.7 document may imply final diagnosis.
- No v0.7 document may imply treatment selection.
- No v0.7 document may imply public or patient-facing readiness.
- No v0.7 document may replace MDD, clinical review, radiology, pathology, microbiology, rheumatology, pulmonology, occupational medicine, or urgent clinical assessment.

---

## 7. Differential Family Lock Checklist

The following differential families must be represented as reasoning prompts, not diagnoses.

| Family | Required Lock Behavior |
|---|---|
| Fibrotic HP | HP-like prompt visible without HP diagnosis |
| Nonfibrotic HP as overlap / mimic | HP-like inflammatory/small-airway prompt visible without HP diagnosis |
| CTD-ILD / SARD-ILD | autoimmune/SARD context visible without CTD-ILD diagnosis |
| NSIP-like pattern | NSIP-like prompt visible without idiopathic NSIP diagnosis |
| OP-like pattern | OP-like prompt visible without OP/COP diagnosis |
| Unclassifiable / mixed pattern IIP | uncertainty and discordance visible without forced label |
| Sarcoidosis / granulomatous differential | sarcoid-like prompt visible without sarcoidosis diagnosis |
| Smoking-related IIP / CPFE context | smoking/emphysema/fibrosis context visible without diagnosis |
| Occupational ILD | source-needed prompt only |
| Drug toxicity | source-needed prompt only |
| Aspiration-related ILD | source-needed prompt only |
| Infection mimic / overlay | source-needed prompt only unless urgent review visibility is required |
| Edema / hemorrhage / vascular acute overlay | urgent mimic visibility inherited; no diagnosis |

Lock condition:

- Family visibility is not diagnosis.
- Family visibility is not exclusion of competing families.
- Multiple family prompts may coexist.
- Single-label closure remains blocked.

---

## 8. Fibrotic HP Lock Checklist

Fibrotic HP parity is lock-ready only if the following remain true.

| Requirement | Required State |
|---|---|
| HP-like prompt without diagnosis | true |
| Exposure status explicitly represented | true |
| Missing exposure does not exclude HP | true |
| Identified exposure does not diagnose HP | true |
| Mosaic attenuation visible without diagnostic closure | true |
| Air trapping tied to expiratory context | true |
| Three-density pattern supports prompt without diagnosis | true |
| Fibrosis plus small-airway features preserves HP visibility | true |
| UIP/probable UIP overlap preserved | true |
| NSIP/OP/CTD overlap preserved | true |
| Serum IgG evidence supportive only | true |
| BAL evidence supportive only | true |
| Pathology evidence requires integration | true |
| MDD prompt visible where relevant | true |
| No BAL decision | true |
| No biopsy decision | true |
| No treatment authority | true |

Lock condition:

- HP must not be erased.
- HP must not be overdiagnosed.
- HP-like features must not suppress competing families.

---

## 9. CTD-ILD / SARD-ILD Lock Checklist

CTD-ILD / SARD-ILD parity is lock-ready only if the following remain true.

| Requirement | Required State |
|---|---|
| CTD/SARD context visible without diagnosis | true |
| Known SARD status represented | true |
| Unknown SARD status does not exclude CTD-ILD | true |
| Autoimmune symptom/sign context visible | true |
| Serology context visible | true |
| Missing serology does not exclude CTD-ILD | true |
| HRCT evidence domain visible without order authority | true |
| PFT evidence domain visible without order authority | true |
| Screening context does not become screening order | true |
| Monitoring context does not become monitoring schedule | true |
| NSIP overlap preserved | true |
| OP overlap preserved | true |
| UIP/IPF overlap preserved | true |
| HP overlap preserved | true |
| Rheumatology/pulmonology review visible | true |
| MDD prompt visible where relevant | true |
| No treatment authority | true |

Lock condition:

- Autoimmune context must not be hidden.
- Autoimmune context must not become diagnosis.
- Screening/monitoring context must not become orders or schedules.

---

## 10. NSIP / OP / Unclassifiable IIP Lock Checklist

NSIP / OP / unclassifiable IIP parity is lock-ready only if the following remain true.

| Requirement | Required State |
|---|---|
| NSIP-like prompt visible without NSIP diagnosis | true |
| Idiopathic NSIP closure blocked until secondary causes reviewed | true |
| CTD-ILD context visible in NSIP-like pattern | true |
| HP context visible in NSIP-like pattern | true |
| Drug toxicity context visible in NSIP-like pattern | true |
| OP-like prompt visible without OP/COP diagnosis | true |
| Infection visible in OP-like consolidation | true |
| Aspiration visible in OP-like consolidation | true |
| CTD-ILD visible in OP-like pattern | true |
| Drug toxicity visible in OP-like pattern | true |
| Fibrotic OP overlap visible | true |
| Mixed HRCT/pathology patterns visible | true |
| Unclassifiable state preserves uncertainty | true |
| Inadequate data listed | true |
| Discordance triggers MDD/re-review prompt | true |
| Disease behavior does not become treatment plan | true |
| No biopsy decision | true |
| No treatment authority | true |

Lock condition:

- Pattern-to-diagnosis collapse remains blocked.
- Secondary causes remain visible.
- Mixed and unclassifiable states preserve uncertainty.

---

## 11. Sarcoidosis / Granulomatous Differential Lock Checklist

Sarcoidosis / granulomatous differential parity is lock-ready only if the following remain true.

| Requirement | Required State |
|---|---|
| Sarcoid-like prompt visible without sarcoidosis diagnosis | true |
| Compatible presentation represented as prompt | true |
| Nonnecrotizing granulomas supportive but not diagnostic alone | true |
| Alternative granulomatous causes visible | true |
| Infection mimics visible | true |
| Berylliosis / occupational mimic visible where relevant | true |
| HP mimic visible | true |
| Malignancy / lymphoma / sarcoid-like reaction visible | true |
| Drug reaction visible where relevant | true |
| Histopathology alone does not settle diagnosis | true |
| Missing microbiology listed | true |
| Missing occupational / exposure history listed | true |
| Sampling uncertainty preserved | true |
| Follow-up prompt does not become schedule | true |
| MDD prompt visible | true |
| Urgent review visible where relevant | true |
| Source-needed mimic domains not over-expanded | true |
| No tissue or lymph node sampling decision | true |
| No treatment authority | true |

Lock condition:

- Sarcoid-like prompt must not become sarcoidosis diagnosis.
- Granulomas must not erase infection or occupational mimics.
- Sampling and follow-up must remain outside platform authority.

---

## 12. Test Case Pack Lock Checklist

The v0.7.8 test case pack is lock-ready only if the following coverage exists.

| Coverage Domain | Required Coverage |
|---|---|
| Fibrotic HP visibility without diagnosis | present |
| Missing exposure does not exclude HP | present |
| HP / UIP boundary | present |
| CTD-ILD / SARD-ILD context prompt | present |
| NSIP-like prompt with secondary-cause visibility | present |
| OP-like prompt with secondary-cause visibility | present |
| Mixed / unclassifiable reasoning | present |
| Sarcoid-like prompt without diagnosis | present |
| Nonnecrotizing granulomas not diagnostic alone | present |
| Deferred source-needed domains | present |
| Acute danger / urgent review | present |
| Multi-family overlap | present |
| MDD prompt visibility | present |
| Source status visibility | present |
| Diagnostic authority none | present across all test cases |
| Treatment authority none | present across all test cases |
| Public readiness false | present across all test cases |
| Clinically reviewed false | present across all test cases |

Lock condition:

- Every test case must include allowed output and blocked output.
- Every test case must include authority fields.
- Test cases must not become clinical protocols.
- Test cases must not create public readiness.

---

## 13. Missing Evidence Lock Checklist

The following missing evidence domains must remain visible where relevant.

| Missing Evidence | Protected Families |
|---|---|
| Exposure history | HP; occupational ILD; pneumoconiosis; asbestosis |
| Home/work/recreational/environmental history | HP; occupational ILD |
| Serum IgG context | HP evidence support |
| BAL lymphocyte context | HP evidence support |
| Autoimmune symptoms/signs/serology | CTD-ILD; NSIP secondary cause |
| Known SARD status | CTD-ILD / SARD-ILD |
| Medication / therapy history | drug toxicity; OP; NSIP secondary cause |
| Infection data / microbiology | infection overlay; OP; sarcoidosis mimic; acute overlay |
| Aspiration risk | aspiration-related OP/ILD |
| Occupational / beryllium context | sarcoidosis mimic; occupational ILD |
| Smoking history | smoking-related IIP; CPFE |
| HRCT technique | HP air trapping; early fibrosis; dependent opacity; CTD-ILD; NSIP |
| Expiratory imaging | HP air trapping; small airway disease |
| Prior imaging | progression/stability; PPF context; acute vs chronic change |
| Pathology | sarcoidosis; HP; NSIP; OP; unclassifiable IIP |
| MDD | all uncertain/mixed/discordant families |
| Urgent clinical status | acute overlay danger |

Lock condition:

- Missing evidence must not be silently filled.
- Missing evidence must not be treated as exclusion.
- Missing evidence must not be hidden behind family naming.

---

## 14. Overlap Lock Checklist

The following overlaps must remain visible where relevant.

| Overlap | Required Behavior |
|---|---|
| HP vs IPF/UIP | Preserve HP and UIP/IPF prompts |
| HP vs NSIP | Preserve HP and NSIP prompts |
| HP vs CTD-ILD | Preserve exposure/small-airway and autoimmune prompts |
| CTD-ILD vs NSIP | Preserve autoimmune and NSIP-like prompts |
| CTD-ILD vs OP | Preserve autoimmune and OP-like prompts |
| CTD-ILD vs UIP/IPF | Preserve autoimmune and UIP/IPF boundary prompts |
| OP vs infection | Preserve infection and OP prompts |
| OP vs aspiration | Preserve aspiration and OP prompts |
| Sarcoidosis vs infection | Preserve infection mimic |
| Sarcoidosis vs HP | Preserve granulomatous and HP prompts |
| Sarcoidosis vs berylliosis/occupational | Preserve occupational exposure prompt |
| Sarcoidosis vs malignancy | Preserve malignancy / lymphoma prompt |
| Mixed UIP/NSIP/OP | Preserve mixed-pattern uncertainty |
| Acute overlay vs chronic fibrosis | Preserve acute process separately from chronic baseline |

Lock condition:

- Overlap must be represented as coexistence.
- Coexistence must not silently become one winning label.
- Competing families must not disappear.

---

## 15. Urgent Review Lock Checklist

Urgent review visibility must outrank differential family naming.

| Urgent Context | Required Behavior |
|---|---|
| Rapid dyspnea or oxygen worsening | urgent review prompt visible |
| New GGO or consolidation | acute overlay / mimic prompts visible |
| Fever / systemic illness | infection/inflammatory prompt visible |
| Hemoptysis / anemia | hemorrhage prompt visible |
| Vascular risk / acute hypoxemia | vascular concern visible |
| Immunosuppression | infection and drug/toxicity prompts visible |
| Cardiac symptoms / syncope | urgent review prompt visible |
| Neurologic symptoms | urgent review prompt visible |
| Hypercalcemia symptoms | systemic/urgent review visible |
| Rapid lymph node enlargement | infection/malignancy prompt visible |

Lock condition:

- Acute danger must not wait for differential label.
- Chronic differential naming must not suppress urgent review prompts.
- No urgent condition may be declared excluded by the platform.

---

## 16. Language Guardrail Lock Checklist

Allowed posture examples:

- “Fibrotic HP-like differential prompt is visible.”
- “CTD-ILD / SARD-ILD context prompt is visible.”
- “NSIP-like pattern prompt is visible.”
- “OP-like pattern prompt is visible.”
- “Mixed-pattern / unclassifiable reasoning remains visible.”
- “Sarcoid-like granulomatous differential prompt is visible.”
- “Missing evidence limits confidence.”
- “Competing families remain visible.”
- “MDD prompt remains visible.”
- “Urgent review prompt remains visible where relevant.”
- “Final diagnosis is not established by this platform.”
- “diagnostic_authority: none”
- “treatment_authority: none”
- “public_ready: false”
- “clinically_reviewed: false”

Blocked posture examples:

- “HP diagnosed.”
- “CTD-ILD confirmed.”
- “NSIP diagnosed.”
- “COP confirmed.”
- “Sarcoidosis diagnosed.”
- “Occupational ILD diagnosed.”
- “Drug toxicity confirmed.”
- “Infection excluded.”
- “Aspiration excluded.”
- “Biopsy should be performed.”
- “BAL should be performed.”
- “Order HRCT.”
- “Order PFTs.”
- “Treatment should be started.”
- “Follow-up every X months.”
- “MDD unnecessary.”
- “Public-ready.”
- “Clinically reviewed.”

Lock condition:

- Blocked language must not appear as platform-approved output.
- Allowed language must preserve uncertainty and review need.

---

## 17. Drift Risks Blocked Before Seal

This checklist blocks the following risks before v0.7 seal.

| Drift Risk | Required Block |
|---|---|
| Differential prompt becomes diagnosis | diagnostic_authority none |
| Source availability becomes clinical review | clinically_reviewed false |
| Test cases become clinical protocol | non-authority envelope |
| HP erased by UIP/IPF closure | HP/UIP boundary lock |
| HP overdiagnosed from small-airway features | HP diagnosis blocked |
| CTD context hidden | CTD prompt visibility |
| CTD context becomes diagnosis | CTD diagnosis blocked |
| NSIP-like pattern becomes idiopathic NSIP | secondary-cause visibility |
| OP-like pattern becomes COP | secondary-cause visibility |
| Mixed pattern forced into label | unclassifiable / mixed-pattern lock |
| Sarcoid-like prompt becomes sarcoidosis diagnosis | sarcoidosis diagnosis blocked |
| Granulomas erase infection/occupational mimics | alternative cause visibility |
| Source-needed domains over-expanded | source-needed lock |
| Acute danger hidden by chronic label | urgent review lock |
| Treatment logic leaks in | treatment_authority none |
| Public readiness implied | public_ready false |

---

## 18. Pre-Seal Readiness Statement

The v0.7 Non-UIP Fibrotic ILD Differential Reasoning Expansion is ready for structural sealing only if:

- v0.7.0 through v0.7.8 exist,
- source anchor map exists,
- claim-to-source mapping table exists,
- family matrix exists,
- fibrotic HP reasoning parity exists,
- CTD-ILD / SARD-ILD context prompt parity exists,
- NSIP / OP / unclassifiable IIP reasoning parity exists,
- sarcoidosis / granulomatous differential prompt parity exists,
- test case pack exists,
- source-needed domains remain blocked,
- missing evidence remains visible,
- competing families remain visible,
- overlap states remain visible,
- MDD prompts remain visible where relevant,
- urgent review prompts remain visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

This checklist confirms readiness for structural sealing.

It is not itself the seal.

---

## 19. Next Step

If this checklist is accepted, the next step is:

- v0.7.10 — Non-UIP Fibrotic ILD Differential Reasoning Structural Seal

The seal should lock v0.7 as structurally complete while preserving:

- non-authority,
- source-status visibility,
- source-needed deferred domains,
- differential prompts without diagnoses,
- missing evidence visibility,
- competing family visibility,
- overlap logic,
- MDD visibility,
- urgent review visibility,
- public_ready false,
- clinically_reviewed false.

v0.7.10 must not create diagnostic authority or treatment authority.

---

## 20. Governance Statement

The Non-UIP Differential Lock Checklist prepares v0.7 for structural sealing.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not decide BAL.  
It does not decide serology.  
It does not decide HRCT or PFT.  
It does not decide microbiology.  
It does not schedule follow-up.  
It does not confirm HP.  
It does not confirm CTD-ILD.  
It does not confirm NSIP.  
It does not confirm OP.  
It does not confirm sarcoidosis.  
It does not confirm occupational ILD.  
It does not confirm drug toxicity.  
It does not exclude mimics.  
It does not replace MDD.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

This checklist verifies that the platform keeps differential pattern, source status, missing evidence, mimics, overlap, MDD need, urgent review need, uncertainty, and change visible before naming non-UIP fibrotic ILD.