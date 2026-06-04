# ILD Reasoning Platform — UIP Parity Upgrade Entry Gate / Scope Contract v1

Version: v0.6.0  
Status: entry_gate  
Scope: UIP parity upgrade scope contract  
Public Ready: false  
Diagnostic Authority: none  
Treatment Authority: none  

---

## 1. Purpose

This document opens v0.6 — UIP Parity Upgrade.

The purpose of v0.6 is to strengthen UIP reasoning parity inside the ILD Reasoning Platform.

This does not mean that the platform diagnoses UIP.  
This does not mean that the platform diagnoses IPF.  
This does not mean that the platform replaces radiology, pathology, clinical judgment, or multidisciplinary discussion.  
This does not mean public readiness.

The purpose is narrower and safer:

- improve pattern-boundary reasoning,
- preserve uncertainty,
- expose missing evidence,
- make mimics visible,
- prevent overconfident UIP labeling,
- prevent UIP-compatible imaging from becoming final disease diagnosis,
- improve structured reasoning around UIP, probable UIP, indeterminate patterns, and alternative explanations.

The platform principle remains:

> “It teaches clinicians to read change before naming disease.”

For v0.6, this becomes:

> “It teaches clinicians to read pattern, boundary, uncertainty, and change before naming UIP.”

---

## 2. Relationship to Previous Phases

v0.6 begins after the following structural seals:

| Version | Layer | Status |
|---|---|---|
| v0.3 | Superimposed Events Core | structurally sealed |
| v0.4 | Evidence Layer / Source Review Governance | structurally sealed |
| v0.5 | Test Case Coverage Expansion | structurally sealed |

v0.6 must inherit all prior constraints.

Especially:

- superimposed processes remain visible,
- evidence review governance remains active,
- test coverage governance remains active,
- uncertainty remains visible,
- missing pieces remain visible,
- mimics remain visible,
- MDD prompts remain visible,
- urgent review prompts remain visible where relevant.

v0.6 must not weaken any previous seal.

---

## 3. UIP Parity Definition

In this platform, UIP parity means reasoning parity, not diagnostic authority.

UIP parity means the platform should better reflect how careful clinical reasoning handles UIP-pattern questions.

It should help structure questions such as:

- Is the imaging pattern UIP-compatible?
- What features support a UIP-pattern interpretation?
- What features weaken or complicate that interpretation?
- Is the pattern better treated as probable, indeterminate, or alternative?
- What evidence is missing?
- Are there mimics or superimposed processes?
- Is temporal change available?
- Is MDD review needed?
- Is urgent review needed because of acute change or dangerous overlap?

UIP parity does not mean:

- final diagnosis,
- automated IPF diagnosis,
- treatment recommendation,
- clinical deployment readiness,
- patient-facing interpretation,
- replacement of guideline review,
- replacement of radiologist interpretation,
- replacement of MDD.

---

## 4. Authority Constraints

The following constraints are mandatory throughout v0.6:

| Constraint | Required State |
|---|---|
| diagnostic_authority | none |
| treatment_authority | none |
| public_ready | false |
| patient_facing_use | not allowed |
| automated_IPF_diagnosis | not allowed |
| automated_UIP_diagnosis | not allowed |
| replacement_of_MDD | not allowed |
| replacement_of_radiologist | not allowed |
| replacement_of_clinical_context | not allowed |
| replacement_of_pathology | not allowed |
| replacement_of_source_review | not allowed |

No v0.6 document may imply that UIP-pattern reasoning equals final diagnosis.

No v0.6 document may imply treatment selection.

No v0.6 document may imply that the platform is ready for clinical deployment.

---

## 5. Core v0.6 Reasoning Contract

The UIP Parity Upgrade must preserve this reasoning sequence:

1. identify the imaging pattern being discussed,
2. identify whether prior imaging exists,
3. identify what changed if prior imaging exists,
4. identify UIP-supporting features,
5. identify features that weaken UIP confidence,
6. identify indeterminate or alternative-pattern signals,
7. identify mimics and superimposed processes,
8. expose missing evidence,
9. preserve uncertainty,
10. prompt MDD where appropriate,
11. prompt urgent review where acute or dangerous overlap is possible,
12. avoid final disease naming without appropriate clinical context.

The central rule:

Disease naming must not outrun pattern uncertainty.

---

## 6. Required v0.6 Invariants

Every v0.6 UIP parity document must preserve:

- diagnostic_authority: none
- treatment_authority: none
- public_ready: false
- uncertainty_preserved: true
- missing_pieces_visible: true
- mimics_visible: true
- mdd_prompt_visible: true
- urgent_review_prompt_visible_where_relevant: true
- uip_pattern_not_equal_final_diagnosis: true
- ipf_not_inferred_from_imaging_alone: true
- source_review_required_for_guideline_claims: true

These invariants are inherited from v0.3, v0.4, and v0.5.

---

## 7. Source Governance Requirement

v0.6 must use the v0.4 Evidence Layer / Source Review Governance before making any guideline-sensitive parity claim.

This means:

- guideline-sensitive claims require source anchoring,
- dated or uncertain claims must remain review-visible,
- source limitations must remain visible,
- disagreement or ambiguity must not be hidden,
- source review must not be converted into diagnostic authority.

The v0.6 entry gate does not itself define final UIP criteria.

Instead, it opens the pathway for a governed UIP parity upgrade.

Specific UIP criteria, pattern categories, and evidence anchors should be handled in later v0.6 documents.

---

## 8. v0.6 Upgrade Targets

The v0.6 phase should improve the following areas:

| Upgrade Target | Purpose |
|---|---|
| UIP pattern boundary reasoning | Better separation of UIP-compatible, probable, indeterminate, and alternative reasoning states |
| Missing evidence handling | Make absent priors, incomplete HRCT context, and missing clinical data visible |
| Mimic visibility | Prevent edema, infection, hemorrhage, vascular process, or other mimics from disappearing |
| Superimposed event handling | Prevent acute change from being misread as baseline UIP progression |
| Temporal comparison | Make change-over-time central when priors exist |
| MDD prompt clarity | Preserve multidisciplinary review as a reasoning requirement |
| Non-authority framing | Prevent imaging pattern from becoming final diagnosis |
| Test parity | Upgrade test cases so UIP reasoning boundaries are actively checked |

---

## 9. v0.6 Non-Goals

v0.6 does not attempt to create:

- a diagnostic model,
- a treatment engine,
- a public-facing tool,
- a patient-facing report,
- a validated clinical device,
- a replacement for radiologists,
- a replacement for MDD,
- full ILD ontology coverage,
- automated guideline adjudication,
- automated IPF diagnosis,
- real-world clinical validation.

v0.6 is a reasoning quality upgrade.

It improves structured UIP reasoning while preserving uncertainty and non-authority.

---

## 10. Expected v0.6 Chain

The expected v0.6 chain may include:

| Step | Planned Role |
|---|---|
| v0.6.0 | UIP Parity Upgrade Entry Gate / Scope Contract |
| v0.6.1 | UIP Source Anchor Review Map |
| v0.6.2 | UIP Pattern Boundary Matrix |
| v0.6.3 | UIP / Probable / Indeterminate / Alternative Reasoning Parity |
| v0.6.4 | UIP Mimic and Superimposed Process Parity |
| v0.6.5 | UIP Temporal Comparison Parity |
| v0.6.6 | UIP MDD and Missing Evidence Prompt Parity |
| v0.6.7 | UIP Parity Test Case Upgrade Pack |
| v0.6.8 | UIP Parity Lock Checklist |
| v0.6.9 | UIP Parity Seal |

This roadmap is provisional.

Each step must remain evidence-governed and non-authoritative.

---

## 11. Entry Gate Acceptance Criteria

v0.6.0 is accepted only if the following are true:

- v0.5 seal exists,
- UIP parity is defined as reasoning parity,
- diagnostic authority remains none,
- treatment authority remains none,
- public_ready remains false,
- UIP pattern is not treated as final diagnosis,
- IPF is not inferred from imaging alone,
- source review is required for guideline-sensitive claims,
- uncertainty remains visible,
- missing evidence remains visible,
- mimics remain visible,
- MDD prompts remain visible,
- urgent review prompts remain visible where relevant,
- v0.6 does not claim clinical validation.

---

## 12. Drift Risks Blocked at Entry

This entry gate blocks the following risks:

| Drift Risk | Entry Gate Block |
|---|---|
| UIP parity becomes diagnostic authority | diagnostic_authority none |
| UIP pattern becomes IPF diagnosis | imaging-alone inference blocked |
| Guideline claims appear without source governance | source review required |
| Missing priors are ignored | missing evidence visibility required |
| Acute change is mislabeled as baseline UIP | temporal and superimposed reasoning required |
| Mimics disappear | mimic visibility required |
| MDD becomes optional | MDD prompt required |
| Public readiness is implied | public_ready false |
| v0.6 weakens v0.5 seal | prior seals inherited |

---

## 13. Entry Gate Statement

v0.6 — UIP Parity Upgrade is now opened as a governed reasoning-quality upgrade.

It does not create diagnostic authority.  
It does not create treatment authority.  
It does not create public readiness.

It opens a structured path to improve UIP reasoning parity while preserving the central philosophy of the ILD Reasoning Platform:

> “It teaches clinicians to read change before naming disease.”

For v0.6, the working expansion is:

> “Read pattern, boundary, uncertainty, and change before naming UIP.”