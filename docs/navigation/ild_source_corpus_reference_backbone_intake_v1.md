# ILD Reasoning Platform — ILD Source Corpus / Reference Backbone Intake v1

Version: v0.20.1  
Status: source_corpus_intake  
Scope: Reference backbone intake for v0.20 ILD Clinical Reasoning Content Re-Entry  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.1:

- ILD Source Corpus / Reference Backbone Intake.

v0.20.1 follows:

- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.0 opened the clinical reasoning content re-entry gate.

v0.20.1 does not yet define the final ILD reasoning vocabulary.

Instead, v0.20.1 admits and classifies the source backbone that will govern the next vocabulary and reasoning-map steps.

This is necessary because v0.20 is no longer generic scaffold work.

v0.20 is the beginning of clinically meaningful ILD reasoning content.

The source corpus must therefore prevent two opposite failures:

1. Clinically weak safety-only drift.
2. Ungoverned clinical overclaim.

The goal is to create a source-governed backbone for:

- ILD terminology,
- HRCT pattern reasoning,
- distribution reasoning,
- temporal reasoning,
- fibrotic behavior reasoning,
- mimic persistence,
- overlap reasoning,
- missing evidence logic,
- source-status logic,
- confidence limitation,
- MDD preparation,
- report overclaim guard.

This document does not make clinical recommendations.

It does not rank diseases.

It does not calculate probability.

It does not diagnose.

It does not rule out disease.

It does not treat.

It does not validate clinical performance.

It does not open real patient data.

It does not open DICOM, HRCT, report, PACS, or EHR integration.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.1 principle is:

> “No reasoning vocabulary without source backbone.”

The permanent boundary is:

> “Sources govern language and reasoning structure; they do not grant autonomous clinical authority.”

---

## 2. Required Previous State

v0.20.1 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.20.0 entry gate exists | true |
| checkpoint-v0.19 exists | true |
| v0.19.9 structural seal exists | true |
| clinical reasoning re-entry doctrine preserved | true |
| prototype file count remains 191 | true |
| working tree before v0.20.1 is clean | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no calibrated probability opened | true |
| no treatment authority opened | true |
| no patient-facing output opened | true |
| no real patient data opened | true |
| no deidentified patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |

Dependency rule:

> v0.20.1 may admit sources only as reasoning-governance references, not as clinical authority.

---

## 3. Source Corpus Role Classes

v0.20.1 classifies sources into role classes.

| Role Class | Meaning |
|---|---|
| terminology_core | controls imaging vocabulary and term precision |
| classification_core | controls broad ILD taxonomy and disease-family framing |
| guideline_core | source with formal guideline process or practice recommendations |
| consensus_core | expert consensus source useful for reasoning where evidence is limited |
| review_support | high-quality review used for background and reasoning context |
| mimic_support | source used to preserve mimics and prevent premature closure |
| oncology_treatment_risk_support | source used for treatment-related ILD/radiation/ICI risk reasoning |
| occupational_exposure_support | source used for exposure-related ILD reasoning |
| edge_case_support | case report or small series used only to reveal traps, not to define general rules |
| internal_doctrine | project-authored governance document defining platform boundaries |

Role class rule:

> A source may support vocabulary and reasoning structure only within its admitted role class.

---

## 4. Source Strength Tiers

v0.20.1 defines source strength tiers.

| Tier | Source Type | Usage |
|---|---|---|
| Tier A | society glossary / formal guideline / major guideline | primary source for vocabulary and boundary framing |
| Tier B | expert consensus / high-quality seminar / major review | supports reasoning structure and uncertainty handling |
| Tier C | focused review / meta-analysis / diagnostic study | supports specific reasoning surface |
| Tier D | case report / case series / editorial | identifies mimic traps and red-team scenarios only |
| Tier E | internal project doctrine | governs platform behavior and authority boundary |

Strength tier rule:

> Lower-tier sources may reveal reasoning hazards, but must not override higher-tier terminology or guideline sources.

---

## 5. Admitted Source Corpus

The following source corpus is admitted for v0.20.1.

| Source ID | Source / File | Role Class | Strength Tier | Admitted Use |
|---|---|---|---|---|
| SRC-001 | Fleischner Society Glossary of Terms for Thoracic Imaging, 2024 | terminology_core | Tier A | thoracic imaging vocabulary, descriptors, anatomy/pathology/physiology labels |
| SRC-002 | Lancet Seminar — Interstitial Lung Diseases, 2022 | classification_core | Tier B | broad ILD taxonomy, common patterns, disease-family framing |
| SRC-003 | Progressive Pulmonary Fibrosis Expert Group Consensus, ERJ 2023 | consensus_core | Tier B | progression reasoning, PPF terminology, monitoring logic |
| SRC-004 | ATS/ERS/JRS/ALAT IPF / PPF guideline source | guideline_core | Tier A | IPF/PPF boundary awareness, guideline-level progression terminology |
| SRC-005 | ERS/EULAR CTD-ILD guideline source | guideline_core | Tier A | CTD-ILD screening, assessment, monitoring, evidence-certainty framing |
| SRC-006 | ATS Sarcoidosis Diagnosis Guideline, 2020 | guideline_core / mimic_support | Tier A | granulomatous mimic discipline, exclusion of alternative causes |
| SRC-007 | ERJ Drug-Induced ILD Review, 2022 | review_support / oncology_treatment_risk_support | Tier B | DI-ILD reasoning, drug exposure, temporal association, exclusion logic |
| SRC-008 | Anti-cancer Therapy DI-ILD Multidisciplinary Viewpoint, 2024 | oncology_treatment_risk_support | Tier C | oncology-related DI-ILD source-status and multidisciplinary framing |
| SRC-009 | ESTRO Radiation Pneumonitis Guideline, 2025 | oncology_treatment_risk_support | Tier A | radiation pneumonitis diagnostic-exclusion and risk reasoning |
| SRC-010 | CHEST Radiation-Induced Lung Injury Review, 2019 | review_support / oncology_treatment_risk_support | Tier B | RILI temporal reasoning and differential diagnosis support |
| SRC-011 | Pre-existing ILD and Radiation / Checkpoint Pneumonitis Meta-analysis, 2025 | oncology_treatment_risk_support | Tier C | pre-existing ILD as risk context for RP/CIP reasoning |
| SRC-012 | ACOEM Occupational ILD Guideline, 2015 | occupational_exposure_support | Tier A | occupational exposure reasoning, surveillance/evaluation framing |
| SRC-013 | IDSA Histoplasmosis Guideline Update, 2025 | mimic_support | Tier A | fungal granulomatous mimic boundary |
| SRC-014 | Sarcoidosis-like Reaction in Adjuvant Immunotherapy Review, 2026 | mimic_support / oncology_treatment_risk_support | Tier C | ICI-associated sarcoid-like reaction mimic logic |
| SRC-015 | Sarcoidosis–Lymphoma Mechanism Review, 2025 | mimic_support | Tier C | sarcoidosis/lymphoma overlap and mimic persistence |
| SRC-016 | Sarcoidosis after Lymphoma Series / Review | mimic_support | Tier C | lymphoma relapse vs sarcoidosis mimic boundary |
| SRC-017 | Sarcoid-like Lymphadenopathy in Neoplastic Patients | mimic_support | Tier C | benign sarcoid-like lymphadenopathy during cancer follow-up |
| SRC-018 | Sarcoidosis / Coccidioidomycosis Case Report | edge_case_support | Tier D | infectious mimic trap only |
| SRC-019 | Sarcoidosis / Histoplasmosis Case Report | edge_case_support | Tier D | fungal mimic trap only |
| SRC-020 | Pulmonary Lymphangitic Carcinomatosis HRCT / PET Study | mimic_support | Tier C | malignancy mimic and lymphangitic carcinomatosis reasoning |
| SRC-021 | Pulmonary Lymphangitic Carcinomatosis Mimicking ILD Case Report | edge_case_support | Tier D | malignancy mimic red-team scenario |
| SRC-022 | Internal v0.19.3 Clinical Reasoning Re-Entry Doctrine | internal_doctrine | Tier E | scaffold-phase vs long-term product boundary |
| SRC-023 | Internal checkpoint-v0.19 | internal_doctrine | Tier E | sealed v0.19 status and v0.20 entry conditions |
| SRC-024 | Internal v0.20.0 Clinical Reasoning Content Re-Entry Entry Gate | internal_doctrine | Tier E | current v0.20 authority boundary |

Admission rule:

> v0.20.1 admits sources into the reference backbone; it does not transform them into executable medical logic.

---

## 6. Source Role Map by Reasoning Surface

The admitted corpus supports future reasoning surfaces as follows.

| Reasoning Surface | Primary Source Roles | Supporting Source Roles |
|---|---|---|
| imaging vocabulary | terminology_core | classification_core |
| HRCT pattern reasoning | terminology_core; classification_core | guideline_core; review_support |
| distribution reasoning | terminology_core; classification_core | review_support |
| temporal reasoning | classification_core; consensus_core | oncology_treatment_risk_support |
| fibrotic behavior reasoning | consensus_core; guideline_core | classification_core |
| inflammatory / organizing reasoning | terminology_core; classification_core | review_support |
| airway-centered reasoning | terminology_core | classification_core |
| nodular reasoning | terminology_core | mimic_support |
| cystic reasoning | terminology_core | classification_core |
| CTD-ILD reasoning | guideline_core | classification_core |
| sarcoidosis reasoning | guideline_core; mimic_support | edge_case_support |
| drug-induced ILD reasoning | review_support; oncology_treatment_risk_support | mimic_support |
| radiation pneumonitis reasoning | oncology_treatment_risk_support | review_support |
| occupational ILD reasoning | occupational_exposure_support | classification_core |
| infection mimic reasoning | mimic_support; edge_case_support | guideline_core |
| malignancy mimic reasoning | mimic_support; edge_case_support | oncology_treatment_risk_support |
| missing evidence logic | guideline_core; consensus_core | internal_doctrine |
| source-status logic | guideline_core; internal_doctrine | review_support |
| confidence limitation | guideline_core; consensus_core; internal_doctrine | mimic_support |
| MDD preparation | guideline_core; consensus_core; internal_doctrine | classification_core |
| report overclaim guard | terminology_core; guideline_core; internal_doctrine | mimic_support |

Reasoning surface rule:

> Each future reasoning surface must declare which source roles support it.

---

## 7. Vocabulary Source Priority

Future v0.20.2 vocabulary must prioritize sources in this order:

1. Fleischner Society terminology for thoracic imaging terms.
2. Formal society guidelines for disease-specific diagnostic boundaries.
3. Consensus documents for areas with limited evidence.
4. Major reviews/seminars for broad classification and context.
5. Focused reviews/meta-analyses for specific risk or mimic context.
6. Case reports/series only for traps and red-team examples.
7. Internal doctrine for authority and safety boundaries.

Vocabulary priority rule:

> Descriptive imaging terms should come from terminology sources; disease reasoning boundaries should come from guideline/consensus sources; edge cases should not define general vocabulary.

---

## 8. Source Use Boundaries

The admitted sources may be used for:

- terminology normalization,
- reasoning vocabulary,
- pattern descriptors,
- distribution descriptors,
- temporal descriptors,
- process-type descriptors,
- mimic visibility,
- missing evidence categories,
- source-status categories,
- confidence limitation language,
- MDD preparation prompts,
- report overclaim warnings,
- red-team clinical ambiguity scenarios.

The admitted sources may not be used for:

- autonomous final diagnosis,
- autonomous rule-out,
- calibrated probability,
- disease ranking as final priority,
- treatment recommendation,
- test-order recommendation,
- procedure recommendation,
- follow-up scheduling,
- triage or disposition,
- patient-facing output,
- clinical validation claim,
- diagnostic performance claim,
- product readiness claim,
- MDD final consensus.

Source use rule:

> Sources may strengthen reasoning, but they must not create autonomous clinical authority.

---

## 9. Guideline vs Platform Boundary

Some admitted sources include guideline or treatment content.

The ILD Reasoning Platform must not copy that authority.

Guideline content may inform:

- what evidence is relevant,
- what uncertainty exists,
- what alternative causes should remain visible,
- what clinical context should trigger review,
- what source-status category applies.

Guideline content must not become:

- treatment instruction,
- test-order instruction,
- procedure instruction,
- patient-facing care advice,
- autonomous management pathway,
- automatic guideline enforcement,
- MDD replacement.

Guideline boundary rule:

> The platform can learn what evidence matters; it cannot independently decide what care should be delivered.

---

## 10. Case Report and Edge-Case Boundary

Case reports and small case series are admitted only as edge-case support.

They may be used to identify:

- mimic traps,
- misleading imaging overlap,
- diagnostic delay hazards,
- red-team scenarios,
- premature closure risks,
- source-status warnings.

They must not be used to define:

- prevalence,
- diagnostic rule,
- disease probability,
- final ranking,
- treatment strategy,
- validation claim,
- generalizable performance.

Edge-case rule:

> Case reports warn the system where reasoning can fail; they do not teach the system what is generally true.

---

## 11. Oncology / Treatment-Related ILD Boundary

Oncology and treatment-related ILD sources are admitted because ILD reasoning must recognize treatment-related mimics and hazards.

Allowed reasoning use:

- prior therapy relevance,
- temporal association,
- radiation-field context,
- checkpoint inhibitor context,
- drug exposure context,
- malignancy progression mimic,
- infection / edema / malignancy alternative visibility,
- multidisciplinary review prompt.

Blocked use:

- cancer therapy recommendation,
- radiation planning recommendation,
- immunotherapy continuation/discontinuation instruction,
- steroid treatment instruction,
- oncology management decision,
- patient-facing risk communication,
- automated adverse-event grading.

Oncology boundary rule:

> Treatment-related sources inform mimic and context awareness, not oncologic decision-making.

---

## 12. Occupational / Exposure Source Boundary

Occupational and exposure sources are admitted because exposure history is central to ILD reasoning.

Allowed reasoning use:

- exposure category visibility,
- occupational/environmental source prompts,
- latency awareness,
- pneumoconiosis / HP / beryllium-like reasoning prompts,
- missing exposure evidence category,
- MDD question generation.

Blocked use:

- occupational diagnosis automation,
- workplace fitness decision,
- compensation / medicolegal determination,
- exposure causality claim,
- treatment or surveillance instruction.

Exposure boundary rule:

> Exposure sources help the platform ask better questions; they do not automate occupational causality decisions.

---

## 13. Internal Doctrine Boundary

Internal project doctrine sources govern platform behavior.

They define:

- non-autonomous diagnostic reasoning,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no patient-facing use,
- no clinical validation claim,
- no MDD replacement,
- safe clinical reasoning re-entry.

Internal doctrine must not override external medical terminology or evidence.

Internal doctrine rule:

> Internal doctrine governs what the platform is allowed to do; external sources govern medical language and reasoning content.

---

## 14. Current-Phase Authority Envelope

The current-phase authority envelope remains:

| Capability | State |
|---|---|
| autonomous final diagnosis | blocked |
| autonomous disease exclusion / rule-out | blocked |
| calibrated diagnostic probability | not_opened |
| treatment authority | none |
| test-order authority | none |
| procedure authority | none |
| follow-up authority | none |
| triage authority | none |
| patient-facing output | not_allowed |
| real patient data | not_allowed |
| deidentified patient data | not_allowed |
| DICOM import | not_opened |
| HRCT import | not_opened |
| report import | not_opened |
| PACS connection | not_opened |
| EHR connection | not_opened |
| clinical validation | not_opened |
| diagnostic performance claim | not_allowed |
| public readiness | false |
| product readiness | false |
| MDD replacement | blocked |

Authority rule:

> Source intake changes the quality of future reasoning content; it does not change current clinical authority.

---

## 15. Prototype File Count Preservation

v0.20.1 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.1 is docs-only source intake; the materialized prototype skeleton remains unchanged.

---

## 16. Roadmap Adjustment

v0.20.0 initially proposed v0.20.1 as ILD Reasoning Vocabulary Foundation.

Because additional source documents were uploaded before vocabulary drafting, the roadmap is adjusted:

| Version | Updated Step | Role |
|---|---|---|
| v0.20.0 | ILD Clinical Reasoning Content Re-Entry Entry Gate | completed |
| v0.20.1 | ILD Source Corpus / Reference Backbone Intake | current |
| v0.20.2 | ILD Reasoning Vocabulary Foundation | next |
| v0.20.3 | HRCT Pattern Reasoning Anchor Map | planned |
| v0.20.4 | Distribution / Temporal Reasoning Map | planned |
| v0.20.5 | Process-Type Reasoning Map | planned |
| v0.20.6 | Mimic / Overlap Persistence Matrix | planned |
| v0.20.7 | Missing Evidence / Source Status Logic | planned |
| v0.20.8 | Non-Calibrated Evidence-Weighted Reasoning Surface | planned |
| v0.20.9 | MDD Preparation / Report Overclaim Guard Map | planned |
| v0.20.10 | ILD Clinical Reasoning Content Structural Seal | planned |
| checkpoint-v0.20 | Project Status / Roadmap Checkpoint after v0.20 | planned |

Roadmap adjustment rule:

> Source corpus intake is inserted before vocabulary so that clinical language is source-governed rather than improvised.

---

## 17. Acceptance Criteria

v0.20.1 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.0 dependency listed | true |
| checkpoint-v0.19 dependency listed | true |
| source role classes defined | true |
| source strength tiers defined | true |
| admitted source corpus listed | true |
| source role map by reasoning surface defined | true |
| vocabulary source priority defined | true |
| source use boundaries defined | true |
| guideline vs platform boundary defined | true |
| case report / edge-case boundary defined | true |
| oncology treatment-related ILD boundary defined | true |
| occupational exposure boundary defined | true |
| internal doctrine boundary defined | true |
| roadmap adjusted before vocabulary | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no calibrated probability opened | true |
| no treatment authority opened | true |
| no patient-facing output opened | true |
| no real patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |
| prototype file count remains 191 | true |

Acceptance rule:

> v0.20.1 is valid only if it admits sources as a reasoning backbone without granting autonomous clinical authority.

---

## 18. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Source intake verifies reference governance only; it does not certify clinical performance.

---

## 19. Next Step

The next recommended step is:

    v0.20.2 — ILD Reasoning Vocabulary Foundation

v0.20.2 should define source-governed vocabulary for:

- pattern present,
- pattern absent,
- pattern mixed,
- distribution relevant,
- temporal behavior relevant,
- evidence supports,
- evidence weakens,
- evidence missing,
- evidence conflicting,
- mimic persists,
- overlap unresolved,
- confidence limited,
- review required,
- MDD preparation.

v0.20.2 must avoid vocabulary that creates:

- final diagnosis,
- rule-out,
- calibrated probability,
- treatment,
- clinical validation claim,
- patient-facing conclusion,
- MDD consensus.

Next-step rule:

> v0.20.2 should give the platform clinical reasoning language without giving it clinical authority.

---

## 20. Governance Statement

This document records v0.20.1 ILD Source Corpus / Reference Backbone Intake.

It does not implement a clinical product.

It does not diagnose autonomously.  
It does not rule out disease autonomously.  
It does not treat.  
It does not validate clinical performance.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not create public readiness.  
It does not create product readiness.  
It does not make the platform clinically reviewed.  
It does not create patient-facing use.  
It does not use real patient data.  
It does not ingest deidentified real patient data.  
It does not import DICOM.  
It does not import HRCT images.  
It does not import real clinical reports.  
It does not connect to PACS.  
It does not connect to EHR.  
It does not replace clinicians, radiologists, pulmonologists, rheumatologists, pathologists, microbiologists, occupational medicine review, oncology review, radiation oncology review, MDD, or urgent clinical assessment.

The platform remains an evidence-governed clinical reasoning platform.

The central project principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.1 discipline is:

> “Admit sources before vocabulary.”

The final v0.20.1 boundary is:

> “The reference backbone is admitted; clinical authority remains closed.”
