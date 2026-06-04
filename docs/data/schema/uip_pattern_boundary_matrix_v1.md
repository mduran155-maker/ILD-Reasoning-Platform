# ILD Reasoning Platform — UIP Pattern Boundary Matrix v1

Version: v0.6.2  
Status: pattern_boundary_matrix  
Scope: UIP / probable UIP / indeterminate / alternative pattern-boundary reasoning  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document defines the UIP Pattern Boundary Matrix for the ILD Reasoning Platform.

It does not diagnose UIP.  
It does not diagnose IPF.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, clinical correlation, pathology review, source review, or multidisciplinary discussion.

Its purpose is to structure pattern-boundary reasoning.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6, this becomes:

> “Read pattern, boundary, uncertainty, evidence, and change before naming UIP.”

---

## 2. Relationship to Prior v0.6 Files

This file follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`
- `docs/navigation/uip_source_anchor_review_map_v1.md`

v0.6.0 opened UIP parity as a non-authoritative reasoning-quality upgrade.

v0.6.1 mapped source anchors and claim sensitivity.

v0.6.2 now introduces the first structured UIP pattern-boundary matrix.

This matrix must remain source-anchored, uncertainty-preserving, and non-authoritative.

---

## 3. Source Anchors Used

| Source Anchor ID | Role in This Matrix |
|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Primary HRCT pattern category anchor |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Current update / source hierarchy anchor |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Comparative expert consensus anchor |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Missing evidence, mimic, MDD, urgent review inheritance |

This file does not reproduce a full guideline.

It converts source-anchored categories into a reasoning boundary matrix for platform design.

---

## 4. Authority Constraints

The following constraints are mandatory:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| automated_UIP_diagnosis | not allowed |
| automated_IPF_diagnosis | not allowed |
| imaging_alone_final_diagnosis | not allowed |
| treatment_selection | not allowed |
| patient_facing_use | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_radiologist | not allowed |
| replacement_of_pathology | not allowed |
| replacement_of_clinical_context | not allowed |

No row in this matrix creates a diagnosis.

Each row creates a reasoning state, a boundary warning, or a review prompt.

---

## 5. Core Pattern Boundary Principle

UIP pattern-boundary reasoning must separate four things:

1. imaging pattern features,
2. pattern confidence,
3. alternative or competing explanations,
4. clinical diagnostic authority.

The platform may support pattern reasoning.

The platform must not convert pattern reasoning into final disease diagnosis.

Central rule:

> UIP-pattern compatibility is not the same thing as final IPF diagnosis.

---

## 6. UIP Pattern Boundary Matrix

| Matrix State | Pattern Reasoning Meaning | Supporting Feature Family | Boundary Warnings | Required Output Posture |
|---|---|---|---|---|
| UIP_PATTERN_CANDIDATE | Imaging pattern has features compatible with UIP-pattern reasoning | Subpleural and basal predominance; heterogeneous distribution; honeycombing with or without peripheral traction bronchiectasis / bronchiolectasis | Do not infer IPF from imaging alone; exclude known causes; preserve clinical context and MDD | “UIP-pattern compatible features are present; final diagnosis requires clinical correlation / MDD.” |
| PROBABLE_UIP_PATTERN_CANDIDATE | Imaging pattern has probable UIP-type reasoning features but lacks full UIP confidence | Subpleural and basal predominance; heterogeneous distribution; reticular pattern with peripheral traction bronchiectasis / bronchiolectasis; may have mild GGO | Do not upgrade automatically to UIP; mild GGO must not dominate; missing pathology / clinical context visible | “Probable UIP-pattern reasoning may be considered; uncertainty and MDD prompt preserved.” |
| INDETERMINATE_FOR_UIP | Fibrotic features are present but do not meet UIP or probable UIP boundary and do not clearly suggest a specific alternative | Subpleural/basal fibrotic abnormality may be present; subtle reticulation; limited GGO; incomplete or early pattern concern | Do not force UIP label; dependent atelectasis / technique / prone imaging limitations may matter; uncertainty must remain explicit | “Indeterminate for UIP-pattern reasoning; insufficient boundary confidence; missing evidence visible.” |
| ALTERNATIVE_PATTERN_PROMPT | Imaging features or distribution suggest another diagnosis or competing explanation | Marked mosaic attenuation; predominant GGO; profuse micronodules; centrilobular nodules; nodules; consolidation; peribronchovascular, perilymphatic, upper/mid-lung predominance; pleural plaques; dilated esophagus; distal clavicular erosions; extensive lymphadenopathy; pleural effusion/thickening | Alternative diagnosis must not be hidden; UIP/IPF closure must be blocked until reviewed | “Alternative or competing diagnosis prompt; mimic / differential / MDD review required.” |
| ACUTE_SUPERIMPOSED_MODIFIER | Acute GGO/consolidation or acute worsening appears on fibrotic background | New or increased bilateral GGO and/or consolidation on background fibrosis; acute clinical deterioration context | Do not treat as baseline UIP progression by default; infection, edema, hemorrhage, vascular process, drug toxicity, and acute exacerbation must remain visible | “Acute superimposed process prompt; urgent review and mimic evaluation required.” |

---

## 7. Boundary Escalation Rules

This matrix allows reasoning movement only as a structured prompt, not as diagnosis.

| From State | To State | Allowed Only If | Blocked If |
|---|---|---|---|
| INDETERMINATE_FOR_UIP | PROBABLE_UIP_PATTERN_CANDIDATE | Fibrotic features become more clearly subpleural/basal with reticular abnormality and traction bronchiectasis / bronchiolectasis | Alternative features dominate; technique or missing evidence prevents confidence |
| PROBABLE_UIP_PATTERN_CANDIDATE | UIP_PATTERN_CANDIDATE | Honeycombing or stronger UIP-compatible pattern features are present and alternative features do not dominate | Imaging-only IPF inference would result |
| Any UIP-facing state | ALTERNATIVE_PATTERN_PROMPT | Ancillary CT, distribution, clinical, exposure, autoimmune, medication, or other evidence suggests another diagnosis | Alternative explanation is ignored |
| Any chronic fibrotic state | ACUTE_SUPERIMPOSED_MODIFIER | Acute change, new GGO/consolidation, or sudden clinical worsening appears | Acute process is collapsed into chronic progression |
| ACUTE_SUPERIMPOSED_MODIFIER | Chronic pattern state | Acute mimic review is complete and acute process is not driving the finding | Infection, edema, hemorrhage, vascular process, or urgent instability remains unresolved |

No transition creates diagnostic authority.

Every transition must preserve uncertainty.

---

## 8. Boundary Vetoes

The following features act as boundary vetoes against premature UIP/IPF closure.

| Veto Category | Examples | Required Platform Behavior |
|---|---|---|
| Alternative CT features | Marked mosaic attenuation, predominant GGO, profuse micronodules, centrilobular nodules, nodules, consolidation | Trigger alternative pattern prompt |
| Alternative distribution | Peribronchovascular, perilymphatic, upper-lung or mid-lung predominance | Trigger alternative pattern prompt |
| Alternative clinical clue | Exposure history, autoimmune context, medication history, occupational risk, aspiration risk, infection context | Trigger missing evidence / differential prompt |
| Pleural / extrapulmonary clue | Pleural plaques, pleural effusion/thickening, dilated esophagus, distal clavicular erosions, lymphadenopathy | Trigger alternative etiology prompt |
| Acute change clue | New GGO, new consolidation, rapid oxygen worsening, fever/inflammatory markers, hemoptysis, volume overload, vascular concern | Trigger acute superimposed modifier and urgent review prompt |
| Missing comparison | No prior CT when progression or acute change is being inferred | Block confident progression claim |
| Missing HRCT quality context | Unknown technique, motion, dependent opacity, non-prone uncertainty when relevant | Preserve technical uncertainty |
| Discordant evidence | Imaging suggests one pathway but clinical/pathology/exposure data suggest another | Prompt MDD / source review |

Boundary veto does not mean the platform has diagnosed the alternative.

It means premature closure is blocked.

---

## 9. Missing Evidence Matrix

| Missing Evidence | Why It Matters | Required Prompt |
|---|---|---|
| Prior HRCT unavailable | Change cannot be confidently read | “Prior imaging comparison is missing.” |
| Clinical timeline unknown | Acute vs chronic process cannot be separated | “Clinical time course is missing.” |
| HRCT technique unknown | Pattern confidence may be limited | “Technique / acquisition context is incomplete.” |
| Prone imaging unavailable where dependent opacity is possible | Subpleural opacity may be overcalled | “Dependent atelectasis / prone confirmation may be relevant.” |
| Exposure history missing | HP, pneumoconiosis, occupational disease may be hidden | “Exposure history needed for alternative diagnosis review.” |
| Autoimmune context missing | CTD-ILD may be hidden | “Autoimmune / CTD context missing.” |
| Medication history missing | Drug toxicity may be hidden | “Medication-related ILD review missing.” |
| Infection markers / microbiology missing | Infection may mimic or overlay fibrosis | “Infection evaluation incomplete.” |
| Cardiac / volume status missing | Edema may mimic GGO or acute worsening | “Cardiac / volume assessment incomplete.” |
| Hemorrhage context missing | Hemorrhage may mimic diffuse GGO | “Hemorrhage risk/context incomplete.” |
| Pathology unavailable | Pattern may remain uncertain in selected cases | “Pathology context unavailable; MDD prompt preserved.” |
| MDD unavailable | Integrated diagnosis not established | “MDD review not documented.” |

Missing evidence must not be filled by assumption.

---

## 10. Mimic and Superimposed Process Matrix

| Process | How It Can Interfere With UIP Reasoning | Required Platform Response |
|---|---|---|
| Infection | May create new GGO, consolidation, nodules, or acute worsening over fibrosis | Keep infection visible; prompt microbiology / clinical correlation |
| Edema | May create bilateral GGO or septal thickening and mimic acute deterioration | Keep edema visible; prompt cardiac / volume assessment |
| Hemorrhage | May create diffuse or patchy GGO and acute symptoms | Keep hemorrhage visible; prompt urgent review when clinically relevant |
| Vascular process | May contribute to acute dyspnea, hypoxemia, or alternative explanation | Keep vascular concern visible; prompt urgent review when relevant |
| Hypersensitivity pneumonitis | May show mosaic attenuation, air-trapping, upper/mid-lung or bronchocentric features | Trigger alternative pattern prompt |
| CTD-ILD | May show alternative distribution or extrapulmonary clues | Trigger autoimmune / CTD evidence prompt |
| NSIP | May show GGO, subpleural sparing, or distribution less typical for UIP | Trigger alternative / indeterminate prompt |
| Sarcoidosis | May show perilymphatic distribution, lymphadenopathy, upper-lung features, or hilar retraction | Trigger alternative pattern prompt |
| Asbestosis | May overlap with basal fibrosis but pleural plaques matter | Trigger occupational / pleural plaque prompt |
| Drug toxicity | May create GGO, organizing pneumonia pattern, or other alternative pattern | Trigger medication history prompt |

The platform must allow overlap.

A chronic fibrotic pattern and a superimposed acute process may coexist.

---

## 11. Output Language Guardrails

Allowed output posture:

- “features compatible with UIP-pattern reasoning”
- “probable UIP-pattern reasoning may be considered”
- “indeterminate for UIP-pattern reasoning”
- “alternative pattern prompt”
- “superimposed acute process should remain visible”
- “MDD / clinical correlation required”
- “missing evidence limits confidence”

Not allowed output posture:

- “this is UIP”
- “this is IPF”
- “diagnosis confirmed”
- “treatment should be started”
- “no further review needed”
- “mimics excluded” when evidence is missing
- “progression confirmed” without prior comparison
- “acute exacerbation confirmed” without clinical and mimic review

---

## 12. Pattern Boundary State Metadata

Every future UIP parity test case should be able to carry the following metadata.

| Field | Required |
|---|---|
| pattern_state | yes |
| source_anchor_id | yes |
| supporting_features | yes |
| weakening_features | yes |
| boundary_vetoes | yes |
| missing_evidence | yes |
| mimic_prompts | yes |
| temporal_comparison_status | yes |
| mdd_prompt_visible | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| diagnostic_authority | yes |
| treatment_authority | yes |
| public_ready | yes |

Required values:

| Field | Required Value |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

---

## 13. Reasoning Examples

### 13.1 UIP-Pattern Candidate Example

Input reasoning context:

- basal/subpleural fibrotic pattern,
- honeycombing visible,
- no dominant alternative feature stated,
- clinical cause exclusion not documented,
- MDD not documented.

Allowed platform output:

- “UIP-pattern compatible features are present.”
- “This does not establish IPF diagnosis by itself.”
- “Clinical correlation, exclusion of known causes, and MDD remain required.”
- “Missing clinical and MDD evidence should remain visible.”

Blocked output:

- “UIP diagnosed.”
- “IPF confirmed.”
- “Treatment pathway selected.”

---

### 13.2 Probable UIP-Pattern Candidate Example

Input reasoning context:

- basal/subpleural reticulation,
- peripheral traction bronchiectasis,
- no honeycombing,
- mild GGO only,
- prior comparison absent.

Allowed platform output:

- “Probable UIP-pattern reasoning may be considered.”
- “No final diagnosis is made.”
- “Prior imaging and MDD context are missing.”
- “Alternative features and mimics should remain review-visible.”

Blocked output:

- “Definite UIP.”
- “IPF diagnosis.”
- “Progression confirmed without prior comparison.”

---

### 13.3 Indeterminate for UIP Example

Input reasoning context:

- fibrotic abnormality exists,
- pattern does not meet UIP/probable boundary,
- no clear alternative diagnosis feature dominates,
- technique/prone context incomplete.

Allowed platform output:

- “Indeterminate for UIP-pattern reasoning.”
- “Boundary confidence is limited.”
- “Technique and missing evidence should be reviewed.”
- “MDD prompt remains visible.”

Blocked output:

- “UIP likely” without boundary support.
- “Alternative diagnosis excluded.”
- “No further review needed.”

---

### 13.4 Alternative Pattern Prompt Example

Input reasoning context:

- fibrotic abnormality,
- marked mosaic attenuation,
- upper/mid-lung or bronchocentric tendency,
- exposure history missing.

Allowed platform output:

- “Alternative pattern prompt is triggered.”
- “HP or other alternative explanations should remain visible.”
- “Exposure history and MDD review are needed.”
- “UIP/IPF closure is blocked.”

Blocked output:

- “UIP pattern dominates” while alternative features are ignored.
- “IPF confirmed.”
- “Mimics excluded.”

---

### 13.5 Acute Superimposed Modifier Example

Input reasoning context:

- chronic fibrotic background,
- new bilateral GGO or consolidation,
- acute dyspnea or oxygen worsening,
- infection/cardiac/hemorrhage data missing.

Allowed platform output:

- “Acute superimposed process prompt is triggered.”
- “Infection, edema, hemorrhage, vascular process, drug toxicity, and acute exacerbation remain visible.”
- “Urgent clinical review may be appropriate.”
- “Do not collapse acute change into chronic UIP progression.”

Blocked output:

- “UIP progression confirmed.”
- “Acute exacerbation confirmed by imaging alone.”
- “No mimic review required.”

---

## 14. Validation Checklist for This Matrix

v0.6.2 is valid only if:

- UIP, probable UIP, indeterminate for UIP, and alternative pattern states are represented,
- acute superimposed modifier is represented,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false,
- UIP pattern does not equal IPF diagnosis,
- probable UIP is not automatically upgraded to UIP,
- indeterminate UIP preserves uncertainty,
- alternative diagnosis prompts can veto premature closure,
- acute change is not collapsed into chronic progression,
- missing evidence remains visible,
- mimics remain visible,
- MDD prompt remains visible,
- urgent review prompt remains visible where relevant,
- source anchors remain declared.

---

## 15. Drift Risks Blocked

| Drift Risk | Matrix Block |
|---|---|
| UIP pattern becomes diagnosis | authority constraints |
| Probable UIP becomes definite UIP | boundary escalation rules |
| Indeterminate UIP becomes forced label | uncertainty requirement |
| Alternative pattern features ignored | boundary vetoes |
| Acute worsening becomes chronic progression | acute superimposed modifier |
| Infection/edema/hemorrhage hidden | mimic matrix |
| Missing priors ignored | missing evidence matrix |
| MDD disappears | MDD prompt metadata |
| Treatment logic leaks in | treatment_authority none |
| Public readiness implied | public_ready false |

---

## 16. Acceptance Criteria

This file is accepted as v0.6.2 if:

- it defines pattern-boundary states,
- it preserves non-authority,
- it links to v0.6.1 source governance,
- it does not overclaim guideline parity,
- it does not diagnose UIP or IPF,
- it does not recommend treatment,
- it preserves uncertainty,
- it preserves missing evidence visibility,
- it preserves mimic visibility,
- it preserves MDD prompts,
- it preserves urgent review prompts where relevant.

---

## 17. Next Step

The next recommended step is:

- v0.6.3 — UIP / Probable / Indeterminate / Alternative Reasoning Parity

v0.6.3 should convert this boundary matrix into parity rules and testable reasoning expectations.

It should not create diagnostic authority.

---

## 18. Governance Statement

The UIP Pattern Boundary Matrix is a reasoning matrix.

It is not a diagnostic rulebook.  
It is not a treatment protocol.  
It is not public-ready.  
It is not a replacement for clinical, radiological, pathological, microbiological, or multidisciplinary judgment.

It teaches clinicians to read pattern, boundary, uncertainty, evidence, and change before naming UIP.