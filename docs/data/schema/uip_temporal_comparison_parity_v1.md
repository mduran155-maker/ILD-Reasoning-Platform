# ILD Reasoning Platform — UIP Temporal Comparison Parity v1

Version: v0.6.5  
Status: temporal_comparison_parity  
Scope: UIP-facing temporal comparison, progression, stability, and acute overlay reasoning  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  
Source Review Date: 2026-06-04  

---

## 1. Purpose

This document defines temporal comparison parity for UIP-facing reasoning in the ILD Reasoning Platform.

It follows UIP Mimic and Superimposed Process Parity.

It does not diagnose UIP.  
It does not diagnose IPF.  
It does not diagnose progression.  
It does not diagnose acute exacerbation.  
It does not recommend treatment.  
It does not create public readiness.  
It does not replace radiologist interpretation, clinical correlation, pathology review, microbiology, MDD, or urgent clinical assessment.

Its purpose is to ensure that UIP-facing reasoning respects time.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6.5, this becomes:

> “Read baseline, interval change, stability, progression, and acute overlay before naming UIP.”

---

## 2. Relationship to Prior v0.6 Files

This file follows:

- `docs/navigation/uip_parity_upgrade_entry_gate_v1.md`
- `docs/navigation/uip_source_anchor_review_map_v1.md`
- `docs/data/schema/uip_pattern_boundary_matrix_v1.md`
- `docs/data/schema/uip_reasoning_parity_rules_v1.md`
- `docs/data/schema/uip_mimic_superimposed_process_parity_v1.md`

v0.6.0 opened UIP parity as reasoning parity.

v0.6.1 mapped source anchors.

v0.6.2 defined pattern-boundary states.

v0.6.3 defined reasoning parity rules.

v0.6.4 preserved mimic and superimposed-process visibility.

v0.6.5 now governs time-based reasoning.

This document does not add diagnostic authority.

---

## 3. Source Anchors Used

| Source Anchor ID | Role |
|---|---|
| UIP_SRC_2018_ATS_ERS_JRS_ALAT_DX | Official guideline anchor for UIP-facing pattern reasoning |
| UIP_SRC_2018_FLEISCHNER_WHITE_PAPER | Verified comparative IPF/UIP diagnostic criteria anchor; longitudinal disease behaviour and working diagnosis review context |
| UIP_SRC_2020_FLEISCHNER_ILA_POSITION_PAPER | Incidental ILA / early fibrotic abnormality / progression and follow-up reasoning support; not a primary UIP diagnostic criteria source |
| UIP_SRC_INTERNAL_V03_SUPERIMPOSED_EVENTS_CORE | Internal simultaneous-process and overlay reasoning inheritance |
| UIP_SRC_INTERNAL_V04_SOURCE_GOVERNANCE | Source review and limitation governance |
| UIP_SRC_INTERNAL_V05_TEST_COVERAGE_SEAL | Test coverage, missing evidence, mimic, MDD, urgent review inheritance |
| UIP_INTERNAL_V062_PATTERN_BOUNDARY_MATRIX | Pattern-state dependency |
| UIP_INTERNAL_V063_REASONING_PARITY_RULES | Reasoning parity dependency |
| UIP_INTERNAL_V064_MIMIC_SUPERIMPOSED_PROCESS_PARITY | Mimic / overlay dependency |

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
| automated_progression_diagnosis | not allowed |
| automated_acute_exacerbation_diagnosis | not allowed |
| treatment_selection | not allowed |
| patient_facing_use | not allowed |
| replacement_of_radiologist | not allowed |
| replacement_of_pathology | not allowed |
| replacement_of_microbiology | not allowed |
| replacement_of_clinical_context | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_urgent_review | not allowed |

No temporal comparison row creates a diagnosis.

No progression row creates treatment authority.

Each row creates a comparison requirement, uncertainty constraint, review prompt, or closure block.

---

## 5. Core Temporal Principle

UIP-facing reasoning must separate:

1. baseline fibrotic pattern,
2. interval fibrotic change,
3. new non-fibrotic opacity,
4. acute overlay,
5. technical / acquisition differences,
6. clinical timeline,
7. diagnostic authority.

Central rule:

> Change must be read before disease is named.

A platform output fails temporal parity if it names progression, stability, UIP, IPF, or acute exacerbation without making the comparison basis visible.

---

## 6. Temporal State Model

| Temporal State | Meaning | Required Platform Behavior |
|---|---|---|
| PRIOR_AVAILABLE | A prior CT or relevant imaging comparator exists | Compare distribution, extent, fibrotic features, and new opacity |
| PRIOR_UNAVAILABLE | No prior imaging is available | Block confident progression or stability claims |
| BASELINE_PATTERN_ONLY | Current scan shows a fibrotic pattern but no temporal comparison is available | Describe pattern state, not progression |
| STABLE_FIBROSIS_PROMPT | Prior comparison suggests no meaningful interval fibrotic increase | State stability only within comparison limits |
| FIBROTIC_PROGRESSION_PROMPT | Prior comparison suggests increased fibrosis, traction bronchiectasis, honeycombing, or extent | Prompt progression reasoning without diagnosing IPF |
| NEW_GGO_OR_CONSOLIDATION_PROMPT | New ground-glass opacity or consolidation appears over fibrosis | Trigger acute overlay / mimic review |
| ACUTE_OVERLAY_TEMPORAL_PROMPT | Clinical or imaging time course suggests acute process over chronic fibrosis | Preserve infection, edema, hemorrhage, vascular, drug toxicity, and acute exacerbation prompts |
| MIXED_CHRONIC_ACUTE_PROMPT | Chronic fibrosis and acute abnormality coexist | Preserve both baseline and overlay |
| TECHNIQUE_LIMITED_COMPARISON | Acquisition differences limit comparison | Preserve technical uncertainty |
| DISCORDANT_TEMPORAL_BEHAVIOUR | Imaging change, clinical course, or prior diagnosis do not align | Prompt MDD / re-review |

Temporal states may coexist.

Example:

- `PROBABLE_UIP_PATTERN_CANDIDATE`
- plus `PRIOR_AVAILABLE`
- plus `NEW_GGO_OR_CONSOLIDATION_PROMPT`
- plus `ACUTE_OVERLAY_TEMPORAL_PROMPT`
- plus `MDD_ESCALATION_PROMPT`

is valid.

The platform must not force a single temporal label.

---

## 7. Temporal Comparison Matrix

| Temporal Situation | Required Reasoning | Blocked Closure |
|---|---|---|
| No prior imaging | Pattern may be described; progression and stability cannot be confidently claimed | “progression confirmed” or “stable disease” |
| Prior imaging available and similar technique | Compare fibrosis extent, honeycombing, traction bronchiectasis, reticulation, GGO, consolidation, and distribution | single-scan conclusion |
| Fibrosis increased | Report fibrotic progression prompt, preserve diagnosis limits | “IPF progression” as final diagnosis |
| Fibrosis stable | Report stability within interval and technique limits | “disease inactive” or “no clinical concern” |
| New GGO/consolidation over fibrosis | Trigger acute overlay and mimic review | “UIP progression” by default |
| GGO decreases on follow-up | Consider resolving overlay / non-fibrotic process prompt | “fibrosis improved” without feature separation |
| Traction bronchiectasis/honeycombing increases | Fibrotic progression prompt may be visible | treatment selection or IPF confirmation |
| Distribution shifts or becomes atypical | Alternative pattern / MDD prompt | UIP closure without review |
| Scan technique differs | Technical limitation visible | confident comparison |
| Clinical timeline acute but fibrosis chronic | Mixed chronic-acute prompt | single chronic-progression label |
| Longitudinal behaviour conflicts with prior diagnosis | Re-review / MDD prompt | old diagnosis carried forward unchallenged |

---

## 8. Progression Reasoning Rules

| Rule ID | Rule | Required Behavior |
|---|---|---|
| UIP_TEMP_001 | Progression requires comparison | Do not claim progression without prior imaging or documented temporal evidence |
| UIP_TEMP_002 | Stability requires comparison | Do not claim stability without comparable prior data |
| UIP_TEMP_003 | Fibrotic progression is feature-specific | Identify whether reticulation, traction bronchiectasis, honeycombing, architectural distortion, or extent changed |
| UIP_TEMP_004 | New GGO/consolidation is not automatically fibrosis progression | Trigger acute overlay / mimic review |
| UIP_TEMP_005 | Clinical timeline modifies imaging interpretation | Acute symptoms should force acute overlay visibility |
| UIP_TEMP_006 | Technique differences limit confidence | Slice thickness, inspiration, prone/expiratory acquisition, dose, reconstruction, and incomplete scan coverage must remain visible where relevant |
| UIP_TEMP_007 | Longitudinal discordance triggers review | If clinical course does not match the prior pattern label, prompt MDD / re-review |
| UIP_TEMP_008 | Working diagnosis can change | Prior working diagnosis must not become immutable |
| UIP_TEMP_009 | Temporal comparison does not create treatment authority | No progression state may recommend therapy |
| UIP_TEMP_010 | Temporal comparison does not create public readiness | No output may imply patient-facing readiness |

---

## 9. Feature-Level Temporal Comparison

When prior imaging exists, the platform should compare features separately.

| Feature | Temporal Question | Required Output Posture |
|---|---|---|
| Reticulation | Increased, decreased, stable, or technique-limited? | Feature-level comparison |
| Traction bronchiectasis / bronchiolectasis | New or increased? | Fibrotic progression prompt if supported |
| Honeycombing | New, increased, stable, or uncertain? | Pattern-confidence and progression prompt, not diagnosis |
| Architectural distortion | Increased or stable? | Fibrotic change prompt |
| Ground-glass opacity | New, increased, decreased, or fibrotic-admixed? | Separate fibrotic-admixed GGO from pure/new GGO |
| Consolidation | New or resolving? | Infection / organizing pneumonia / acute overlay prompt |
| Mosaic attenuation / air trapping | New, increased, extensive, or technique-dependent? | Alternative pattern / HP-like prompt |
| Distribution | Same, more basal/subpleural, more diffuse, upper/mid-lung shift, peribronchovascular? | Boundary-state update / alternative prompt |
| Extent | More lung zones or larger involved area? | Extent-change prompt |
| Emphysema / cystic change | Stable or confounding honeycombing assessment? | Technical / mimic caution |
| Pleural / extrapulmonary clue | New or newly recognized? | Alternative etiology prompt |
| Scan quality | Comparable or limited? | Comparison-confidence modifier |

---

## 10. Acute Overlay Separation Rules

Acute overlay must be separated from chronic fibrotic progression.

| Acute Finding | Required Prompt |
|---|---|
| New bilateral GGO | infection, edema, hemorrhage, drug toxicity, acute exacerbation, urgent review visibility |
| New consolidation | infection, aspiration, organizing pneumonia, acute overlay review |
| Rapid oxygen worsening | urgent clinical review visibility |
| Fever / inflammatory marker context | infection visibility |
| Volume overload / cardiac uncertainty | edema visibility |
| Hemoptysis / anemia / anticoagulation context | hemorrhage visibility |
| Acute dyspnea or hypoxemia | vascular concern visibility |
| Medication exposure or recent therapy | drug toxicity visibility |
| Recent surgery / chemotherapy / radiotherapy / immunotherapy context | therapy-related lung injury / acute acceleration visibility |

Blocked closure:

- “UIP progression confirmed” when acute overlay is plausible.
- “acute exacerbation confirmed” from imaging alone.
- “infection excluded” without clinical/microbiology evidence.
- “edema excluded” without cardiac/volume review.
- “hemorrhage excluded” without clinical context.

---

## 11. Prior-Unavailable Rules

When prior imaging is unavailable, the platform must show temporal humility.

Allowed output posture:

- “Current scan shows UIP-facing pattern features.”
- “Progression cannot be determined without prior comparison.”
- “A baseline may be established for future comparison.”
- “Clinical timeline and prior imaging availability limit temporal confidence.”
- “MDD / clinical correlation remains appropriate.”

Blocked output posture:

- “Progressive fibrosis.”
- “Stable fibrosis.”
- “new abnormality” unless a documented prior exists.
- “acute on chronic change” without clinical or imaging support.
- “IPF progression.”

---

## 12. Technique-Limited Comparison Rules

Comparison can be limited by scan technique.

| Limitation | Required Prompt |
|---|---|
| Different slice thickness | “Comparison may be limited by slice thickness.” |
| Different reconstruction kernel | “Fine reticulation / honeycombing comparison may be limited.” |
| Incomplete prior scan coverage | “Extent comparison is limited.” |
| Different inspiratory effort | “Apparent GGO/attenuation may be technique-influenced.” |
| No prone imaging where dependent opacity matters | “Dependent atelectasis remains possible.” |
| No expiratory imaging where air trapping matters | “Air trapping / HP-like clue may be under-assessed.” |
| Motion artifact | “Feature confidence is limited.” |
| Ultra-low-dose or low-detail acquisition | “Subtle fibrosis comparison is limited.” |

Technique limitation must not be hidden behind confident temporal claims.

---

## 13. Longitudinal Behaviour and Re-Review Rules

UIP-facing reasoning must allow prior interpretation to change.

| Scenario | Required Response |
|---|---|
| Prior working diagnosis conflicts with new exposure history | Re-review / MDD prompt |
| Prior IPF label conflicts with new autoimmune evidence | Re-review / MDD prompt |
| Prior UIP-compatible pattern develops strong alternative features | Alternative pattern / MDD prompt |
| Disease behaves unexpectedly | Longitudinal discordance prompt |
| Acute episodes recur | Superimposed process review |
| Fibrosis progresses despite uncertain baseline category | Progression prompt without final diagnosis |
| Previously indeterminate pattern becomes more classifiable | Boundary-state update with uncertainty preserved |
| Previously probable pattern gains honeycombing | UIP-pattern candidate prompt without IPF closure |
| Previously UIP-facing pattern loses GGO after treatment/interval | Resolving overlay prompt; do not call fibrosis reversal automatically |

The platform must not treat earlier working labels as permanent truth.

---

## 14. Temporal Output Language Guardrails

Allowed language:

- “prior comparison is unavailable”
- “progression cannot be determined from a single scan”
- “interval increase in fibrotic features is suggested”
- “new ground-glass opacity should trigger acute overlay review”
- “stable within the limits of the available comparison”
- “comparison is limited by technique”
- “longitudinal behaviour is discordant and should prompt re-review”
- “working diagnosis may need re-evaluation”
- “MDD remains appropriate”
- “urgent review may be appropriate depending on clinical context”

Blocked language:

- “progression confirmed” without prior comparison
- “stable disease” without prior comparison
- “IPF progression” from imaging alone
- “UIP progression” when new GGO/consolidation may represent acute overlay
- “acute exacerbation confirmed by imaging alone”
- “no mimic review needed”
- “no MDD needed”
- “treatment should be started”
- “public-ready”

---

## 15. Testable Temporal Parity Expectations

Future v0.6 test cases should evaluate:

| Expectation ID | Expectation |
|---|---|
| UTP_001 | Prior availability is explicitly stated |
| UTP_002 | Progression is not claimed without comparison |
| UTP_003 | Stability is not claimed without comparison |
| UTP_004 | Feature-level change is separated |
| UTP_005 | New GGO/consolidation triggers acute overlay review |
| UTP_006 | Acute overlay is not collapsed into chronic progression |
| UTP_007 | Technique limitations remain visible |
| UTP_008 | Clinical timeline remains visible |
| UTP_009 | Missing evidence remains visible |
| UTP_010 | Mimics remain visible |
| UTP_011 | MDD / re-review prompt remains visible where relevant |
| UTP_012 | Urgent review prompt remains visible where relevant |
| UTP_013 | Working diagnosis is not immutable |
| UTP_014 | Diagnostic authority remains none |
| UTP_015 | Treatment authority remains none |
| UTP_016 | Public readiness remains false |

---

## 16. Example Reasoning Scenarios

### 16.1 Single Scan With UIP-Compatible Features

Input reasoning context:

- basal/subpleural fibrosis,
- honeycombing,
- no prior imaging,
- clinical context incomplete.

Allowed platform output:

- “UIP-pattern compatible features are present.”
- “Progression cannot be determined without prior comparison.”
- “Clinical context and MDD remain required.”
- “Diagnostic authority remains none.”

Blocked output:

- “Progressive UIP.”
- “IPF progression.”
- “IPF confirmed.”

---

### 16.2 Prior CT Shows Increased Honeycombing

Input reasoning context:

- prior CT available,
- comparable technique,
- increased honeycombing and traction bronchiectasis,
- no new GGO/consolidation,
- clinical context incomplete.

Allowed platform output:

- “Interval increase in fibrotic features is suggested.”
- “This supports a fibrotic progression prompt.”
- “Final diagnosis is not established by this platform.”
- “MDD / clinical correlation remains appropriate.”

Blocked output:

- “IPF progression confirmed.”
- “Treatment should be started.”
- “No further review needed.”

---

### 16.3 Chronic Fibrosis With New GGO

Input reasoning context:

- prior CT shows chronic fibrotic background,
- current CT shows new bilateral GGO,
- acute dyspnea present,
- infection/cardiac/hemorrhage data missing.

Allowed platform output:

- “New GGO triggers acute overlay review.”
- “Infection, edema, hemorrhage, vascular concern, drug toxicity, and acute exacerbation remain visible.”
- “Do not collapse acute change into chronic UIP progression.”
- “Urgent clinical review may be appropriate depending on clinical context.”

Blocked output:

- “UIP progression confirmed.”
- “Acute exacerbation confirmed by imaging alone.”
- “Mimics excluded.”

---

### 16.4 Apparent Increase With Technique Difference

Input reasoning context:

- prior CT thicker slices,
- current HRCT thin sections,
- apparent increase in fine reticulation,
- inspiratory effort differs.

Allowed platform output:

- “Comparison is technique-limited.”
- “Fine reticulation confidence may be affected by acquisition differences.”
- “Progression should not be overcalled.”
- “Repeat or standardized comparison may be needed depending on clinical context.”

Blocked output:

- “Definite progression.”
- “Stable disease excluded.”
- “IPF progression.”

---

### 16.5 Prior Working Diagnosis Becomes Discordant

Input reasoning context:

- previous working diagnosis of IPF,
- new autoimmune signs or exposure history,
- pattern remains fibrotic,
- longitudinal course discordant.

Allowed platform output:

- “Longitudinal behaviour and new clinical evidence are discordant with prior working diagnosis.”
- “Re-review / MDD prompt is triggered.”
- “Prior working diagnosis should not be treated as immutable.”
- “Alternative explanation remains visible.”

Blocked output:

- “Prior diagnosis stands automatically.”
- “UIP/IPF closure preserved despite new evidence.”
- “MDD unnecessary.”

---

## 17. Required Metadata for Future Test Cases

Each UIP temporal comparison test case should carry:

| Field | Required |
|---|---|
| test_case_id | yes |
| baseline_pattern_state | yes |
| current_pattern_state | yes |
| prior_available | yes |
| prior_date_or_interval | yes |
| comparison_quality | yes |
| technique_limitations | yes |
| feature_level_changes | yes |
| new_ggo_or_consolidation | yes |
| acute_overlay_prompt | yes |
| mimic_prompts | yes |
| missing_evidence | yes |
| clinical_timeline_status | yes |
| mdd_prompt_visible | yes |
| urgent_review_prompt_visible_where_relevant | yes |
| expected_allowed_output | yes |
| expected_blocked_output | yes |
| source_anchor_id | yes |
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

## 18. Failure Modes

The following are explicit v0.6.5 failures:

| Failure Mode | Why It Fails |
|---|---|
| Progression claimed without prior comparison | Violates temporal reasoning |
| Stability claimed without prior comparison | Violates temporal reasoning |
| New GGO collapsed into chronic progression | Erases acute overlay |
| Acute exacerbation confirmed by imaging alone | Creates diagnostic authority |
| Technique limitations hidden | Creates false confidence |
| Missing clinical timeline hidden | Weakens acute/chronic separation |
| Prior working diagnosis treated as immutable | Blocks longitudinal re-review |
| Mimics hidden during temporal change | Violates v0.6.4 |
| MDD prompt absent in discordant change | Weakens review governance |
| Urgent review prompt absent in acute danger | Weakens safety visibility |
| Treatment recommendation appears | Violates treatment_authority none |
| Public readiness implied | Violates public_ready false |

---

## 19. Acceptance Criteria

v0.6.5 is accepted only if:

- temporal comparison is explicitly represented,
- prior availability is required,
- progression requires comparison,
- stability requires comparison,
- feature-level change is separated,
- acute overlay is separated from chronic progression,
- technique limitations remain visible,
- clinical timeline remains visible,
- missing evidence remains visible,
- mimics remain visible,
- prior working diagnosis remains reviewable,
- MDD / re-review prompts remain visible,
- urgent review prompts remain visible where relevant,
- diagnostic_authority remains none,
- treatment_authority remains none,
- public_ready remains false.

---

## 20. Next Step

The next recommended step is:

- v0.6.6 — UIP MDD and Missing Evidence Prompt Parity

v0.6.6 should strengthen:

- MDD prompt visibility,
- missing clinical/radiological/pathological evidence prompts,
- clinical context dependency,
- pathology/biopsy uncertainty,
- exposure/autoimmune/medication evidence gaps,
- review-trigger logic.

It should not create diagnostic authority.

---

## 21. Governance Statement

UIP Temporal Comparison Parity protects the platform from timeless disease labeling.

It does not diagnose.  
It does not treat.  
It does not confirm progression by itself.  
It does not confirm acute exacerbation.  
It does not replace radiologist interpretation.  
It does not replace clinical correlation.  
It does not replace pathology, microbiology, MDD, or urgent clinical assessment.  
It does not claim public readiness.

The platform remains an evidence-governed clinical reasoning platform.

It teaches clinicians to read baseline, interval change, stability, progression, acute overlay, uncertainty, and evidence before naming UIP.