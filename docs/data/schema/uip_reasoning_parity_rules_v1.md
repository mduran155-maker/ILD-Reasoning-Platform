# ILD Reasoning Platform — UIP Reasoning Parity Rules v1

Version: v0.6.3  
Status: reasoning_parity_rules  
Scope: UIP / probable UIP / indeterminate / alternative reasoning parity  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document defines reasoning parity rules for UIP-facing pattern states in the ILD Reasoning Platform.

It follows the UIP Pattern Boundary Matrix.

It does not diagnose UIP.  
It does not diagnose IPF.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, pathology review, clinical correlation, source review, or multidisciplinary discussion.

Its purpose is to convert pattern-boundary states into testable reasoning expectations.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6, this becomes:

> “Read pattern, boundary, uncertainty, evidence, and change before naming UIP.”

---

## 2. Relationship to Prior v0.6 Files

This file follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`
- `docs/navigation/uip_source_anchor_review_map_v1.md`
- `docs/data/schema/uip_pattern_boundary_matrix_v1.md`

v0.6.0 opened the UIP parity upgrade.

v0.6.1 mapped source anchors.

v0.6.2 defined pattern-boundary states.

v0.6.3 defines parity rules for those states.

This file does not add new diagnostic criteria.

It defines how the platform should reason when those states appear.

---

## 3. Source Anchors Used

| Source Anchor ID | Role |
|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Primary HRCT pattern category anchor |
| UIP_SRC_2022_ATS_ERS_JRS_ALAT_IPF_PPF | Current guideline update / source hierarchy anchor |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Comparative expert consensus anchor |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Test coverage, mimic, missing evidence, MDD, urgent review inheritance |
| UIP_INTERNAL_V062_PATTERN_BOUNDARY_MATRIX | Immediate internal boundary matrix dependency |

---

## 4. Parity Definition

In this document, parity means reasoning parity.

Reasoning parity means the platform must treat each UIP-facing state with the correct reasoning posture.

It does not mean diagnostic certainty.

It does not mean the platform reaches the same final diagnosis as a clinician.

It means:

- UIP-pattern candidate states must not become final IPF diagnosis.
- Probable UIP states must not be automatically upgraded to UIP.
- Indeterminate states must preserve uncertainty.
- Alternative pattern prompts must block premature UIP/IPF closure.
- Acute superimposed modifiers must prevent acute change from being collapsed into chronic fibrosis progression.
- Missing evidence must remain visible.
- Mimics must remain visible.
- MDD prompts must remain visible.
- Urgent review prompts must remain visible where relevant.

---

## 5. Authority Constraints

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
| replacement_of_radiologist | not allowed |
| replacement_of_pathology | not allowed |
| replacement_of_clinical_context | not allowed |
| replacement_of_MDD | not allowed |

No parity rule may create clinical authority.

---

## 6. Global UIP Reasoning Parity Rules

The following rules apply to all UIP-facing states.

| Rule ID | Rule | Required Behavior |
|---|---|---|
| UIP_PARITY_001 | Pattern is not diagnosis | Any UIP-facing pattern must remain a reasoning state, not final diagnosis |
| UIP_PARITY_002 | IPF is not inferred from imaging alone | Imaging pattern cannot independently establish IPF |
| UIP_PARITY_003 | Boundary uncertainty is preserved | Probable, indeterminate, and alternative states must not be collapsed |
| UIP_PARITY_004 | Missing evidence remains visible | Missing priors, clinical timeline, HRCT technique, exposure, autoimmune, infection, cardiac, pathology, and MDD context must not be hidden |
| UIP_PARITY_005 | Mimics remain visible | Infection, edema, hemorrhage, vascular process, HP, CTD-ILD, NSIP, sarcoidosis, asbestosis, and drug toxicity must remain visible where relevant |
| UIP_PARITY_006 | MDD prompt remains visible | MDD must remain visible whenever integrated diagnosis is uncertain |
| UIP_PARITY_007 | Urgent review remains visible | Acute worsening, vascular concern, hemorrhage, severe infection, or unstable clinical context must trigger urgent review visibility |
| UIP_PARITY_008 | Temporal comparison matters | Progression or acute change cannot be confidently claimed without appropriate comparison or timeline |
| UIP_PARITY_009 | Boundary vetoes override closure | Alternative features, acute change, or missing evidence can block premature UIP/IPF closure |
| UIP_PARITY_010 | Treatment logic is blocked | No rule may recommend treatment or management |

---

## 7. State Parity Rules

### 7.1 UIP Pattern Candidate Parity

Pattern state:

- UIP_PATTERN_CANDIDATE

Required reasoning posture:

- Recognize UIP-compatible pattern features.
- Preserve clinical context dependency.
- Preserve MDD dependency.
- Preserve known-cause exclusion dependency.
- Block imaging-alone IPF conclusion.

Allowed output posture:

- “UIP-pattern compatible features are present.”
- “Final diagnosis requires clinical correlation and MDD.”
- “Known causes and competing explanations must remain review-visible.”
- “Missing evidence limits certainty.”

Blocked output posture:

- “UIP diagnosed.”
- “IPF confirmed.”
- “Treatment should begin.”
- “MDD is unnecessary.”
- “Mimics are excluded” when evidence is missing.

Parity pass condition:

- UIP-compatible features are acknowledged without diagnostic closure.

Parity failure condition:

- UIP-pattern compatibility is converted into final disease diagnosis.

---

### 7.2 Probable UIP Pattern Candidate Parity

Pattern state:

- PROBABLE_UIP_PATTERN_CANDIDATE

Required reasoning posture:

- Recognize probable UIP-type features.
- Preserve the distinction between probable UIP and UIP.
- Prevent automatic upgrade to UIP.
- Preserve mild GGO limitations.
- Preserve missing evidence and MDD visibility.

Allowed output posture:

- “Probable UIP-pattern reasoning may be considered.”
- “This is not automatically upgraded to UIP.”
- “Clinical context, missing evidence, and MDD remain relevant.”
- “Alternative features must remain visible.”

Blocked output posture:

- “Definite UIP.”
- “IPF diagnosed.”
- “Probable UIP is equivalent to UIP.”
- “No further review needed.”

Parity pass condition:

- Probable UIP remains a boundary-limited reasoning state.

Parity failure condition:

- Probable UIP is treated as definite UIP or final IPF.

---

### 7.3 Indeterminate for UIP Parity

Pattern state:

- INDETERMINATE_FOR_UIP

Required reasoning posture:

- Preserve uncertainty.
- Avoid forced label assignment.
- Expose technical and evidence limitations.
- Preserve prone/dependent opacity concern where relevant.
- Preserve MDD prompt.

Allowed output posture:

- “Indeterminate for UIP-pattern reasoning.”
- “Boundary confidence is limited.”
- “Missing evidence and technique context should be reviewed.”
- “MDD review remains appropriate.”

Blocked output posture:

- “UIP likely” without supporting boundary evidence.
- “Alternative diagnosis excluded.”
- “No further review needed.”
- “Indeterminate resolved automatically.”

Parity pass condition:

- Indeterminate state remains uncertain and review-visible.

Parity failure condition:

- Indeterminate state is forced into UIP, probable UIP, or alternative diagnosis without evidence.

---

### 7.4 Alternative Pattern Prompt Parity

Pattern state:

- ALTERNATIVE_PATTERN_PROMPT

Required reasoning posture:

- Detect alternative-pattern features.
- Block premature UIP/IPF closure.
- Preserve mimic and differential visibility.
- Preserve exposure, autoimmune, medication, infection, edema, vascular, and pathology review prompts where relevant.
- Preserve MDD prompt.

Allowed output posture:

- “Alternative or competing pattern prompt is triggered.”
- “UIP/IPF closure is blocked until reviewed.”
- “Mimics and differentials remain visible.”
- “MDD and clinical correlation are required.”

Blocked output posture:

- “UIP dominates despite alternative features” without review.
- “IPF confirmed.”
- “Alternative diagnosis excluded.”
- “Mimics irrelevant.”

Parity pass condition:

- Alternative features prevent premature closure.

Parity failure condition:

- Alternative features are ignored or downranked invisibly.

---

### 7.5 Acute Superimposed Modifier Parity

Pattern state:

- ACUTE_SUPERIMPOSED_MODIFIER

Required reasoning posture:

- Recognize acute process possibility on chronic fibrotic background.
- Avoid collapsing acute change into chronic UIP progression.
- Preserve infection, edema, hemorrhage, vascular process, drug toxicity, and acute exacerbation as possibilities.
- Preserve urgent review visibility.
- Preserve temporal comparison need.

Allowed output posture:

- “Acute superimposed process prompt is triggered.”
- “Do not collapse acute change into chronic UIP progression.”
- “Infection, edema, hemorrhage, vascular process, drug toxicity, and acute exacerbation remain visible.”
- “Urgent review may be appropriate depending on clinical context.”

Blocked output posture:

- “UIP progression confirmed.”
- “Acute exacerbation confirmed by imaging alone.”
- “Infection excluded” without evidence.
- “Edema excluded” without evidence.
- “No urgent review concern.”

Parity pass condition:

- Acute change remains separated from chronic baseline reasoning.

Parity failure condition:

- Acute change is treated as ordinary chronic progression or a single definitive label.

---

## 8. Boundary Veto Priority Rules

Boundary vetoes must be applied before confident UIP-facing output.

Priority order:

1. urgent clinical danger,
2. acute superimposed process,
3. alternative pattern features,
4. missing evidence that limits confidence,
5. temporal comparison uncertainty,
6. UIP-facing pattern state.

This means:

- urgent danger can override routine pattern framing,
- acute process can modify chronic pattern interpretation,
- alternative features can veto UIP/IPF closure,
- missing evidence can reduce confidence,
- lack of prior imaging can block progression claims,
- pattern state can be reported only after these checks remain visible.

---

## 9. Temporal Parity Rules

Temporal comparison is mandatory whenever change is being discussed.

| Temporal Situation | Required Reasoning |
|---|---|
| Prior imaging available | Compare pattern, distribution, extent, new opacity, and fibrosis progression |
| Prior imaging unavailable | Do not claim progression confidently |
| Acute symptoms present | Separate acute process from chronic fibrotic background |
| New GGO/consolidation | Trigger acute superimposed modifier |
| Stable fibrosis | Do not invent progression |
| Mixed chronic and acute findings | Allow coexisting chronic baseline and acute overlay |

Temporal parity failure occurs when:

- progression is claimed without prior comparison,
- acute change is treated as chronic fibrosis,
- stability is inferred without comparison,
- new GGO is assigned to UIP progression by default.

---

## 10. Missing Evidence Parity Rules

Missing evidence must be represented as active reasoning constraints.

| Missing Evidence | Required Parity Behavior |
|---|---|
| Prior HRCT missing | Block confident progression claim |
| Clinical timeline missing | Block acute/chronic confidence |
| HRCT technique unknown | Preserve technical uncertainty |
| Prone imaging missing where dependent opacity matters | Preserve dependent atelectasis concern |
| Exposure history missing | Keep HP / occupational mimic visible |
| Autoimmune context missing | Keep CTD-ILD mimic visible |
| Medication history missing | Keep drug toxicity visible |
| Infection data missing | Keep infection visible |
| Cardiac / volume data missing | Keep edema visible |
| Hemorrhage context missing | Keep hemorrhage visible |
| Pathology unavailable | Preserve selected-case uncertainty |
| MDD unavailable | Preserve integrated diagnosis uncertainty |

Parity failure occurs when missing evidence is silently filled by assumption.

---

## 11. Mimic Parity Rules

Mimics must remain visible when their feature family is present or when necessary evidence is missing.

| Mimic / Overlap | Required Trigger |
|---|---|
| Infection | acute GGO/consolidation, fever/inflammatory context, microbiology missing, acute deterioration |
| Edema | bilateral GGO/septal thickening, cardiac/volume uncertainty, acute dyspnea |
| Hemorrhage | diffuse or patchy GGO, hemoptysis/risk context missing, acute deterioration |
| Vascular process | acute hypoxemia, dyspnea, vascular concern, unstable clinical context |
| HP | mosaic attenuation, air-trapping, upper/mid-lung or bronchocentric features, exposure missing |
| CTD-ILD | autoimmune context missing or extrapulmonary clues |
| NSIP | extensive GGO, subpleural sparing, less typical UIP distribution |
| Sarcoidosis | perilymphatic/upper-lung features, lymphadenopathy, hilar retraction |
| Asbestosis | basal fibrosis with pleural plaques or occupational context |
| Drug toxicity | medication exposure missing or organizing/GGO pattern concern |

Parity failure occurs when mimics are excluded without evidence.

---

## 12. Output Parity Requirements

Every UIP-facing output should include the following where relevant:

| Output Element | Required |
|---|---|
| Pattern state | yes |
| Confidence limitation | yes |
| Missing evidence | yes |
| Mimic / differential prompt | yes |
| Temporal comparison status | yes |
| MDD prompt | yes |
| Urgent review prompt where relevant | yes |
| Diagnostic authority statement | yes |
| Treatment authority statement | yes |
| Public readiness statement | yes |

Required authority values:

- diagnostic_authority: none
- treatment_authority: none
- public_ready: false

---

## 13. Allowed and Blocked Language

### 13.1 Allowed Language

Allowed:

- “UIP-pattern compatible features”
- “probable UIP-pattern reasoning”
- “indeterminate for UIP-pattern reasoning”
- “alternative pattern prompt”
- “acute superimposed process prompt”
- “missing evidence limits confidence”
- “MDD review remains appropriate”
- “urgent clinical review may be appropriate depending on context”
- “final diagnosis is not established by this platform”

### 13.2 Blocked Language

Blocked:

- “UIP diagnosed”
- “IPF confirmed”
- “probable UIP equals UIP”
- “indeterminate UIP resolved automatically”
- “alternative diagnosis excluded”
- “acute exacerbation confirmed by imaging alone”
- “progression confirmed without prior comparison”
- “treatment should be started”
- “no MDD needed”
- “public-ready”

---

## 14. Testable Parity Expectations

Future v0.6 test cases should evaluate whether the platform output satisfies the following expectations.

| Expectation ID | Expectation |
|---|---|
| UPE_001 | Correct pattern state is preserved |
| UPE_002 | Diagnostic authority remains none |
| UPE_003 | Treatment authority remains none |
| UPE_004 | Public readiness remains false |
| UPE_005 | UIP pattern is not converted into IPF diagnosis |
| UPE_006 | Probable UIP is not upgraded automatically |
| UPE_007 | Indeterminate state preserves uncertainty |
| UPE_008 | Alternative pattern prompt blocks premature closure |
| UPE_009 | Acute superimposed modifier blocks chronic-progression default |
| UPE_010 | Missing evidence is listed |
| UPE_011 | Mimics remain visible |
| UPE_012 | MDD prompt remains visible |
| UPE_013 | Urgent review prompt remains visible where relevant |
| UPE_014 | Temporal comparison is handled explicitly |
| UPE_015 | Blocked language is absent |

---

## 15. Parity Failure Modes

The following are explicit parity failures:

| Failure Mode | Why It Fails |
|---|---|
| UIP pattern reported as final diagnosis | Creates diagnostic authority |
| Probable UIP treated as definite UIP | Collapses boundary state |
| Indeterminate UIP forced into a label | Erases uncertainty |
| Alternative features ignored | Hides mimics / differential |
| Acute GGO treated as chronic UIP progression | Erases superimposed process |
| Progression claimed without priors | Violates temporal comparison |
| Missing evidence not shown | Hides uncertainty |
| MDD prompt absent in uncertain reasoning | Weakens review governance |
| Urgent danger hidden | Weakens safety prompt visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public readiness implied | Violates public_ready false |

---

## 16. Metadata Required for Future Test Cases

Each UIP parity test case should carry:

| Field | Required |
|---|---|
| test_case_id | yes |
| pattern_state | yes |
| source_anchor_id | yes |
| input_features | yes |
| supporting_features | yes |
| weakening_features | yes |
| boundary_vetoes | yes |
| missing_evidence | yes |
| mimic_prompts | yes |
| temporal_comparison_status | yes |
| expected_allowed_output | yes |
| expected_blocked_output | yes |
| mdd_prompt_visible | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| diagnostic_authority | yes |
| treatment_authority | yes |
| public_ready | yes |

Required authority values:

| Field | Required Value |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |

---

## 17. Acceptance Criteria

v0.6.3 is accepted only if:

- it defines parity as reasoning parity, not diagnostic parity,
- it preserves all v0.6.0 authority constraints,
- it uses v0.6.1 source governance,
- it depends on v0.6.2 pattern boundary states,
- UIP pattern does not equal IPF diagnosis,
- probable UIP is not automatically upgraded,
- indeterminate UIP preserves uncertainty,
- alternative pattern prompts block premature closure,
- acute superimposed modifiers remain visible,
- temporal comparison remains explicit,
- missing evidence remains visible,
- mimics remain visible,
- MDD prompt remains visible,
- urgent review prompt remains visible where relevant,
- treatment logic is blocked,
- public readiness remains false.

---

## 18. Next Step

The next recommended step is:

- v0.6.4 — UIP Mimic and Superimposed Process Parity

v0.6.4 should deepen mimic and overlap handling for UIP-facing reasoning.

It should not create diagnostic authority.

---

## 19. Governance Statement

UIP Reasoning Parity Rules convert boundary states into testable reasoning expectations.

They do not diagnose.  
They do not treat.  
They do not replace clinician judgment.  
They do not replace radiologist interpretation.  
They do not replace pathology review.  
They do not replace MDD.  
They do not claim public readiness.

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read pattern, boundary, uncertainty, evidence, and change before naming UIP.