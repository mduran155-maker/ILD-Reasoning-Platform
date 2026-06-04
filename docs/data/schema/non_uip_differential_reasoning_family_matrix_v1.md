# ILD Reasoning Platform — Non-UIP Differential Reasoning Family Matrix v1

Version: v0.7.3  
Status: differential_reasoning_family_matrix  
Scope: Non-UIP fibrotic ILD differential reasoning families and boundary states  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Clinically Reviewed: false  

---

## 1. Purpose

This document defines the non-UIP fibrotic ILD differential reasoning family matrix for v0.7.

It follows:

- `docs/navigation/non_uip_fibrotic_ild_differential_reasoning_entry_gate_v1.md`
- `docs/navigation/non_uip_fibrotic_ild_source_anchor_map_v1.md`
- `docs/navigation/non_uip_differential_claim_to_source_mapping_table_v1.md`

This document does not diagnose hypersensitivity pneumonitis.  
This document does not diagnose CTD-ILD.  
This document does not diagnose NSIP.  
This document does not diagnose organizing pneumonia.  
This document does not diagnose sarcoidosis.  
This document does not diagnose occupational ILD.  
This document does not diagnose drug toxicity.  
This document does not diagnose aspiration-related ILD.  
This document does not recommend treatment.  
This document does not decide biopsy.  
This document does not create public readiness.  
This document does not make v0.7 clinically reviewed.

Its purpose is to define reasoning families, boundary states, missing evidence states, overlap states, and closure blocks before domain-specific parity rules are written.

The v0.7 principle remains:

> “Differential reasoning is not differential diagnosis authority.”

The inherited source-governance rule remains:

> “Available source is not mapped source. Mapped source is not clinical review.”

---

## 2. Relationship to Prior Layers

v0.7.3 inherits:

- v0.3 superimposed events logic,
- v0.4 source governance,
- v0.5 test coverage and mimic visibility,
- v0.6 UIP parity and source backfill discipline,
- v0.7.0 entry gate,
- v0.7.1 source anchor map,
- v0.7.2 claim-to-source mapping.

This matrix is not a clinical differential diagnosis engine.

It is a reasoning-governance matrix.

---

## 3. Current Source Mapping Status

The current v0.7 source status is:

| Field | Status |
|---|---|
| v0_7_source_anchor_map | present |
| v0_7_claim_mapping | initial_partial_complete |
| HP_claims_mapped | targeted_partial |
| IIP_NSIP_OP_claims_mapped | targeted_partial |
| SARD_ILD_claims_mapped | targeted_partial |
| sarcoidosis_claims_mapped | targeted_partial |
| occupational_ILD_source | needed |
| drug_toxicity_source | needed |
| aspiration_related_ILD_source | needed |
| infection_overlay_source | needed |
| clinically_reviewed | false |
| public_ready | false |
| diagnostic_authority | none |
| treatment_authority | none |

This matrix may use mapped claim families for internal structural drafting only.

It may not claim clinical review.

---

## 4. Authority Constraints

The following constraints are mandatory across this matrix.

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
| automated_sarcoidosis_diagnosis | not_allowed |
| automated_occupational_ILD_diagnosis | not_allowed |
| automated_drug_toxicity_diagnosis | not_allowed |
| automated_aspiration_ILD_diagnosis | not_allowed |
| automated_infection_diagnosis | not_allowed |
| automated_biopsy_decision | not_allowed |
| automated_treatment_selection | not_allowed |
| patient_facing_use | not_allowed |
| replacement_of_MDD | not_allowed |
| replacement_of_clinician | not_allowed |
| replacement_of_radiologist | not_allowed |
| replacement_of_pathologist | not_allowed |
| replacement_of_pulmonologist | not_allowed |
| replacement_of_rheumatologist | not_allowed |
| replacement_of_occupational_medicine_review | not_allowed |
| replacement_of_microbiology | not_allowed |
| replacement_of_urgent_review | not_allowed |

No reasoning family may override these constraints.

---

## 5. Core Matrix Principle

The platform may create differential prompts.

The platform may not create differential diagnoses.

A family prompt means:

- this family remains visible,
- source status is declared,
- missing evidence is exposed,
- mimics are preserved,
- overlap is allowed,
- MDD/review prompt remains visible where relevant,
- urgent review prompt remains visible where relevant.

A family prompt does not mean:

- the disease is diagnosed,
- the disease is excluded,
- treatment is selected,
- biopsy is decided,
- public-ready interpretation exists.

---

## 6. Differential Family Matrix

| Family ID | Differential Family | Current v0.7 Status | Primary Source Status | Allowed Reasoning Role | Blocked Closure |
|---|---|---|---|---|---|
| V07_FAM_HP_FIBROTIC | Fibrotic hypersensitivity pneumonitis | active_candidate_family | mapped_targeted_partial | HP-like fibrotic differential prompt; exposure/small-airway/MDD visibility | HP diagnosis |
| V07_FAM_HP_NONFIBROTIC | Nonfibrotic HP as overlap or mimic | active_candidate_family | mapped_targeted_partial | inflammatory/small-airway HP prompt where relevant | HP diagnosis |
| V07_FAM_CTD_SARD_ILD | CTD-ILD / SARD-ILD | active_candidate_family | mapped_targeted_partial | autoimmune/SARD context prompt; HRCT/PFT evidence gap visibility | CTD-ILD diagnosis |
| V07_FAM_NSIP | Fibrotic NSIP / NSIP-like pattern | active_candidate_family | mapped_targeted_partial | NSIP-like pattern prompt; secondary cause visibility | idiopathic NSIP diagnosis |
| V07_FAM_OP | Organizing pneumonia / fibrotic OP overlap | active_candidate_family | mapped_targeted_partial | OP-like consolidation/migratory/peribronchial prompt | OP or COP diagnosis |
| V07_FAM_UNCLASSIFIABLE | Unclassifiable IIP / mixed pattern ILD | active_candidate_family | mapped_targeted_partial | uncertainty/discordance/mixed-pattern prompt | forced diagnosis |
| V07_FAM_SARCOID | Sarcoidosis / sarcoid-like granulomatous differential | active_candidate_family | mapped_targeted_partial | granulomatous/perilymphatic/lymphadenopathy prompt | sarcoidosis diagnosis |
| V07_FAM_SMOKING_CPFE | Smoking-related IIP / CPFE context | candidate_limited_family | mapped_targeted_partial | smoking/emphysema/fibrosis coexistence prompt | smoking-related ILD diagnosis |
| V07_FAM_OCCUPATIONAL | Occupational ILD / pneumoconiosis / asbestosis | deferred_family | source_needed | exposure prompt only | occupational ILD diagnosis |
| V07_FAM_DRUG_TOXICITY | Drug toxicity / therapy-related ILD | deferred_family | source_needed | medication/therapy prompt only | drug toxicity diagnosis |
| V07_FAM_ASPIRATION | Aspiration-related ILD / OP overlap | deferred_family | source_needed | aspiration/OP-overlap prompt only | aspiration ILD diagnosis |
| V07_FAM_INFECTION | Infection mimic / overlay | deferred_family | source_needed | acute infection overlay prompt only | infection diagnosis |
| V07_FAM_EDEMA_HEMORRHAGE_VASCULAR | Edema / hemorrhage / vascular acute overlay | inherited_visibility_family | v0.5/v0.6 internal inheritance; dedicated sources pending | urgent mimic/overlay visibility | edema/hemorrhage/vascular diagnosis |

---

## 7. Reasoning State Model

The following states may be assigned to any differential family.

| State | Meaning | Required Behavior |
|---|---|---|
| FAMILY_VISIBLE | Family remains visible as possible reasoning pathway | Show family prompt without diagnosis |
| FAMILY_SUPPORTING_FEATURES_PRESENT | Some features support the family | List supporting features and limitations |
| FAMILY_WEAKENING_FEATURES_PRESENT | Some features reduce confidence | Preserve uncertainty and competing families |
| FAMILY_MISSING_EVIDENCE | Required evidence is missing | Show missing evidence; do not exclude family |
| FAMILY_OVERLAP_WITH_UIP | Family may overlap with UIP-facing fibrosis | Preserve UIP/non-UIP boundary; do not force closure |
| FAMILY_OVERLAP_WITH_OTHER_NON_UIP | Family overlaps another non-UIP family | Keep both visible |
| FAMILY_ALTERNATIVE_TO_IPF | Family may challenge IPF/UIP closure | Block premature IPF/UIP closure |
| FAMILY_ACUTE_OVERLAY_POSSIBLE | Acute or superimposed process may coexist | Trigger urgent/mimic visibility where relevant |
| FAMILY_MDD_PROMPT_VISIBLE | MDD or integrated review is needed | Preserve review prompt |
| FAMILY_SOURCE_NEEDED | Source is missing for deeper expansion | Do not create domain parity |
| FAMILY_MAPPING_PENDING | Source exists but claim mapping incomplete | Limit use to draft scope |
| FAMILY_DEFERRED | Family is recognized but not opened | Keep only minimal prompt visibility |

These states may coexist.

Example:

- `FAMILY_VISIBLE`
- plus `FAMILY_SUPPORTING_FEATURES_PRESENT`
- plus `FAMILY_MISSING_EVIDENCE`
- plus `FAMILY_OVERLAP_WITH_UIP`
- plus `FAMILY_MDD_PROMPT_VISIBLE`

is valid.

The platform must not collapse the case into one family.

---

## 8. Family-Specific Boundary States

### 8.1 Fibrotic HP Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| HP_EXPOSURE_PROMPT | exposure history positive, incomplete, or suspicious | Keep HP visible; do not diagnose HP |
| HP_EXPOSURE_UNKNOWN | no culprit exposure identified or history incomplete | Missing exposure does not exclude HP |
| HP_SMALL_AIRWAY_FEATURE_PROMPT | mosaic attenuation, air trapping, centrilobular nodules, three-density pattern | Keep HP-like reasoning visible |
| HP_FIBROTIC_OVERLAP_PROMPT | fibrosis plus HP-like features | Preserve HP/IPF/NSIP overlap |
| HP_UIP_PATTERN_ALONE_INDETERMINATE | UIP-like pattern without HP-supporting features | Do not force HP diagnosis |
| HP_MDD_PROMPT | HP vs IPF/IIP overlap or incomplete evidence | MDD visibility required |

Blocked closure:

- HP diagnosed.
- HP excluded because exposure is unidentified.
- IPF diagnosed while HP-supporting features are hidden.
- BAL/biopsy decision automated.
- treatment recommended.

---

### 8.2 CTD-ILD / SARD-ILD Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| CTD_CONTEXT_MISSING | autoimmune history, symptoms, signs, serology, or known SARD status incomplete | Keep CTD-ILD visible |
| SARD_RISK_CONTEXT_VISIBLE | known RA, systemic sclerosis, IIM, MCTD, or Sjögren context | Show SARD-ILD context prompt |
| CTD_NSIP_OVERLAP_PROMPT | NSIP-like pattern plus autoimmune context | Keep CTD-ILD and NSIP visible |
| CTD_OP_OVERLAP_PROMPT | OP-like pattern plus autoimmune context | Keep CTD-ILD and OP visible |
| CTD_SCREEN_MONITOR_CONTEXT | HRCT/PFT screening or monitoring evidence relevant | Show context without ordering tests |
| CTD_MDD_PROMPT | clinical/imaging/rheumatologic data incomplete or discordant | MDD/review prompt visible |

Blocked closure:

- CTD-ILD diagnosed.
- CTD-ILD excluded when autoimmune context is missing.
- screening ordered by platform.
- monitoring schedule dictated by platform.
- treatment recommended.

---

### 8.3 NSIP Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| NSIP_LIKE_PATTERN_PROMPT | bilateral GGO, reticulation, traction bronchiectasis, possible subpleural sparing | Keep NSIP-like pattern visible |
| NSIP_SECONDARY_CAUSE_PROMPT | CTD, HP, drug toxicity, familial fibrosis, or exposure context possible | Do not label idiopathic NSIP prematurely |
| NSIP_UIP_DIFFERENTIATION_PROMPT | NSIP-like features coexist with UIP-facing features | Preserve boundary uncertainty |
| NSIP_OP_OVERLAP_PROMPT | OP-like findings coexist with NSIP-like pattern | Keep both visible |
| NSIP_MDD_PROMPT | pattern/context discordance or missing evidence | MDD prompt visible |

Blocked closure:

- idiopathic NSIP diagnosed.
- CTD/HP/drug causes excluded without evidence.
- UIP excluded solely from NSIP-like prompt.
- treatment recommended.

---

### 8.4 Organizing Pneumonia Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| OP_PATTERN_PROMPT | patchy/migratory consolidation, peribronchial/subpleural/bandlike pattern, reverse halo where relevant | Keep OP-like pattern visible |
| OP_SECONDARY_CAUSE_PROMPT | CTD, infection, aspiration, drug reaction, therapy-related injury possible | Do not label cryptogenic OP prematurely |
| FIBROTIC_OP_OVERLAP_PROMPT | OP-like process plus reticulation/fibrosis | Preserve fibrotic OP overlap |
| OP_ACUTE_OVERLAY_PROMPT | acute symptoms or new consolidation | Preserve infection/aspiration/urgent review visibility |
| OP_MDD_PROMPT | OP-like pattern with fibrosis or discordant context | MDD prompt visible |

Blocked closure:

- OP diagnosed.
- COP diagnosed.
- infection excluded.
- aspiration excluded.
- drug toxicity excluded.
- treatment recommended.

---

### 8.5 Sarcoidosis / Granulomatous Differential Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| SARCOID_COMPATIBLE_PRESENTATION_PROMPT | compatible clinical/radiologic/extrapulmonary context | Keep sarcoid-like prompt visible |
| SARCOID_GRANULOMA_PROMPT | nonnecrotizing granulomatous inflammation reported | Require alternative cause visibility |
| SARCOID_ALTERNATIVE_CAUSE_PROMPT | infection, malignancy, berylliosis, HP, drug reaction, immune disorder possible | Block sarcoidosis closure |
| SARCOID_LYMPHADENOPATHY_PROMPT | bilateral hilar/mediastinal lymphadenopathy or perilymphatic pattern | Keep sarcoid-like prompt visible |
| SARCOID_UNCERTAINTY_PROMPT | criteria incomplete or alternative not excluded | Preserve diagnostic uncertainty |
| SARCOID_MDD_PROMPT | granulomatous differential complex or discordant | MDD/review prompt visible |

Blocked closure:

- sarcoidosis diagnosed.
- alternative granulomatous causes excluded without evidence.
- tissue sampling decided by platform.
- infection excluded.
- treatment recommended.

---

### 8.6 Unclassifiable / Mixed Pattern Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| UNCLASSIFIABLE_INADEQUATE_DATA | clinical, radiologic, or pathology data insufficient | Preserve uncertainty |
| UNCLASSIFIABLE_DISCORDANCE | clinical/radiologic/pathologic findings conflict | Prompt MDD/re-review |
| MIXED_HRCT_PATTERN | multiple HRCT patterns coexist | Preserve all visible patterns |
| MIXED_PATHOLOGY_PATTERN | multiple pathologic patterns coexist | Preserve pathology integration prompt |
| DISEASE_BEHAVIOR_PROMPT | behavior pattern may help review | Do not convert behavior into treatment plan |
| WORKING_DIAGNOSIS_REVIEWABLE | provisional reasoning may be needed | Keep reviewability visible |

Blocked closure:

- forced diagnosis.
- mixed pattern ignored.
- disease behavior used as treatment instruction.
- MDD omitted.

---

### 8.7 Smoking-Related IIP / CPFE Boundary States

| State | Trigger | Required Behavior |
|---|---|---|
| SMOKING_CONTEXT_VISIBLE | smoking history or emphysema context present | Keep smoking-related context visible |
| RB_ILD_DİP_PATTERN_PROMPT | GGO, centrilobular nodules, smoker’s macrophage context, DIP/RB-ILD-like reasoning | Prompt only; no diagnosis |
| CPFE_CONTEXT_PROMPT | emphysema plus fibrosis coexistence | Preserve coexistence and pulmonary hypertension concern visibility |
| SMOKING_HP_CONFUSION_PROMPT | small airway features overlap HP or smoking-related disease | Keep both visible |
| SMOKING_MDD_PROMPT | mixed emphysema/fibrosis/pattern uncertainty | MDD prompt visible |

Blocked closure:

- smoking-related ILD diagnosed.
- CPFE diagnosed.
- HP excluded.
- UIP/IPF confirmed solely because smoking/emphysema exists.
- treatment recommended.

---

### 8.8 Deferred Family Boundary States

Deferred families include:

- occupational ILD,
- pneumoconiosis,
- asbestosis,
- drug toxicity,
- therapy-related ILD,
- aspiration-related ILD,
- broader infection overlay.

Allowed behavior:

- keep prompt visible if evidence gap or suggestive feature exists,
- mark source_needed,
- block domain parity expansion,
- require future source mapping.

Blocked behavior:

- detailed domain rules,
- diagnosis,
- exclusion,
- treatment,
- seal.

---

## 9. Missing Evidence Matrix

| Missing Evidence | Families Protected |
|---|---|
| Exposure history missing | HP; occupational ILD; pneumoconiosis; asbestosis |
| Home/work/recreational antigen history missing | HP |
| Serum IgG context missing | HP evidence support |
| BAL lymphocyte context missing | HP evidence support |
| Autoimmune history/signs/serology missing | CTD-ILD; NSIP secondary cause |
| Known SARD status unknown | CTD-ILD / SARD-ILD |
| Medication/therapy history missing | drug toxicity; OP; NSIP secondary cause |
| Infection data missing | infection overlay; OP; sarcoidosis mimic; acute overlay |
| Aspiration risk missing | aspiration-related ILD; OP overlap |
| Occupational history missing | occupational ILD; pneumoconiosis; asbestosis |
| Smoking history missing | smoking-related IIP; CPFE; RB-ILD/DIP context |
| Pathology context missing | sarcoidosis; HP; NSIP; unclassifiable IIP |
| HRCT technique incomplete | HP air trapping; early fibrosis; dependent opacity; CTD-ILD; NSIP |
| Expiratory imaging missing | HP air trapping; small airway disease |
| Prior imaging missing | progression/stability; PPF context; chronic vs acute change |
| MDD unavailable | all uncertain/mixed/discordant families |
| Urgent clinical context missing | acute overlay, infection, hemorrhage, vascular, severe exacerbation-like states |

Rule:

> Missing evidence must remain visible and must not be converted into exclusion.

---

## 10. Overlap Matrix

| Overlap | Required Behavior |
|---|---|
| HP vs IPF/UIP | Preserve exposure/small-airway/three-density prompts; do not force IPF or HP |
| HP vs NSIP | Preserve HP and NSIP prompts; MDD visible |
| CTD-ILD vs NSIP | Preserve autoimmune context and NSIP-like pattern |
| CTD-ILD vs OP | Preserve autoimmune context and OP-like pattern |
| Sarcoidosis vs infection | Preserve infection mimic; do not confirm sarcoidosis |
| Sarcoidosis vs HP | Preserve granulomatous differential and exposure context |
| OP vs infection | Preserve infection and OP-like pattern |
| OP vs aspiration | Preserve aspiration risk |
| Smoking-related fibrosis vs HP | Preserve smoking context and exposure/small airway context |
| CPFE vs UIP/IPF | Preserve emphysema/fibrosis coexistence and UIP boundary |
| Acute overlay vs chronic fibrosis | Preserve acute process separately from chronic baseline |
| Unclassifiable vs forced label | Preserve uncertainty and mixed pattern visibility |

Overlap rule:

> Multiple differential families may be visible at the same time.

---

## 11. Priority Order for Reasoning Visibility

When multiple prompts are present, visibility should follow this order:

1. urgent clinical danger,
2. acute overlay or unstable clinical context,
3. infection / hemorrhage / vascular / edema mimic prompts,
4. major alternative differential family prompt,
5. missing evidence that blocks safe closure,
6. source-needed or mapping-pending status,
7. MDD / re-review prompt,
8. temporal comparison prompt,
9. chronic pattern-family prompt,
10. working diagnosis caveat.

Pattern-family naming must not outrank safety, missing evidence, source status, or review need.

---

## 12. Family Output Requirements

Every future v0.7 family-facing output should include where relevant:

| Output Element | Required |
|---|---|
| differential_family_prompt | yes |
| supporting_features | yes |
| weakening_features | yes |
| missing_evidence | yes |
| competing_families | yes |
| overlap_state | yes |
| source_status | yes |
| claim_mapping_status | yes |
| MDD_prompt_visible_where_relevant | yes |
| urgent_review_prompt_visible_where_relevant | yes |
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

## 13. Allowed Language

Allowed language examples:

- “HP-like differential prompt is visible.”
- “Fibrotic HP overlap should remain review-visible.”
- “CTD-ILD context is incomplete.”
- “NSIP-like pattern prompt is triggered.”
- “OP-like consolidation pattern remains visible.”
- “Sarcoid-like granulomatous differential remains visible.”
- “Alternative granulomatous causes are not excluded.”
- “Unclassifiable / mixed-pattern reasoning remains possible.”
- “Source mapping is partial.”
- “MDD prompt remains visible.”
- “Final diagnosis is not established by this platform.”

---

## 14. Blocked Language

Blocked language examples:

- “HP diagnosed.”
- “CTD-ILD confirmed.”
- “NSIP diagnosed.”
- “COP diagnosed.”
- “Sarcoidosis diagnosed.”
- “Occupational ILD diagnosed.”
- “Drug toxicity confirmed.”
- “Infection excluded.”
- “Aspiration excluded.”
- “No MDD needed.”
- “Biopsy should be performed.”
- “Treatment should be started.”
- “Public-ready.”
- “Patient-facing diagnosis.”
- “Clinically reviewed.”

---

## 15. Testable Expectations for Future v0.7 Test Cases

Future v0.7 test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| NUF_001 | Differential family prompt is visible without diagnosis |
| NUF_002 | Supporting features are listed |
| NUF_003 | Weakening features are listed |
| NUF_004 | Missing evidence is listed |
| NUF_005 | Missing evidence is not treated as exclusion |
| NUF_006 | Competing families remain visible |
| NUF_007 | Overlap states are preserved |
| NUF_008 | Source status is visible |
| NUF_009 | Claim mapping status is visible |
| NUF_010 | MDD prompt remains visible where relevant |
| NUF_011 | Urgent review prompt remains visible where relevant |
| NUF_012 | Deferred families are not over-expanded |
| NUF_013 | Source-needed families remain blocked from parity lock |
| NUF_014 | Diagnostic authority remains none |
| NUF_015 | Treatment authority remains none |
| NUF_016 | Public readiness remains false |
| NUF_017 | Clinically reviewed remains false |

---

## 16. Failure Modes

The following are explicit v0.7.3 failures:

| Failure Mode | Why It Fails |
|---|---|
| Differential prompt becomes diagnosis | Violates v0.7 authority |
| Missing evidence treated as exclusion | Violates evidence governance |
| Single family suppresses competing families | Violates overlap logic |
| HP features hidden in UIP/NSIP-like fibrosis | Violates HP mimic visibility |
| CTD context hidden in NSIP/OP-like pattern | Violates CTD-ILD visibility |
| Sarcoidosis prompt ignores infection/beryllium/HP/drug mimics | Violates granulomatous mimic visibility |
| OP-like pattern excludes infection/aspiration/drug/CTD | Violates mimic visibility |
| Unclassifiable case forced into label | Violates uncertainty preservation |
| Source-needed family expanded into rules | Violates source governance |
| MDD prompt absent in discordance | Violates review governance |
| Urgent review prompt absent in acute danger | Violates safety visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Biopsy decision appears | Violates biopsy authority none |
| Public-ready claim appears | Violates public_ready false |
| Clinically reviewed claim appears | Violates clinically_reviewed false |

---

## 17. Acceptance Criteria

v0.7.3 is accepted only if:

- non-UIP differential families are represented,
- family states are reasoning states, not diagnoses,
- source status remains visible,
- missing evidence states are represented,
- overlap states are represented,
- HP, CTD-ILD, NSIP, OP, sarcoidosis, unclassifiable IIP, and smoking-related contexts are included,
- occupational, drug toxicity, aspiration, and infection families remain deferred where source is needed,
- MDD prompts remain visible,
- urgent review prompts remain visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- clinically_reviewed remains false.

---

## 18. Next Step

The next recommended step is:

- v0.7.4 — Fibrotic HP Reasoning Parity

v0.7.4 should use the mapped HP source claims to define HP-specific reasoning parity.

It should cover:

- HP as newly identified ILD differential,
- fibrotic vs nonfibrotic HP distinction,
- exposure known vs missing,
- small-airway features,
- mosaic attenuation / air trapping / three-density pattern,
- UIP/IPF/NSIP overlap,
- MDD prompt,
- BAL/serum IgG/pathology evidence prompts without decision authority,
- no HP diagnosis,
- no treatment authority,
- no public readiness.

---

## 19. Governance Statement

This family matrix organizes non-UIP fibrotic ILD differential reasoning.

It does not diagnose.  
It does not treat.  
It does not decide biopsy.  
It does not confirm HP.  
It does not confirm CTD-ILD.  
It does not confirm NSIP.  
It does not confirm OP.  
It does not confirm sarcoidosis.  
It does not confirm occupational ILD.  
It does not confirm drug toxicity.  
It does not confirm infection.  
It does not claim public readiness.  
It does not claim clinical review.

The platform remains an evidence-governed clinical reasoning platform.

The v0.7 rule remains:

> “Differential reasoning is not differential diagnosis authority.”

The platform teaches clinicians to keep differential families, overlap, missing evidence, source status, review need, uncertainty, and change visible before naming non-UIP fibrotic ILD.