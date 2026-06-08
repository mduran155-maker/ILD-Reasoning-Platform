# ILD Reasoning Platform — Clinical Reasoning Re-Entry Doctrine v1

Version: v0.19.3  
Status: doctrine_clarification  
Scope: Clinical reasoning re-entry doctrine and non-autonomous diagnostic reasoning boundary after v0.19.2  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.19.3:

- Clinical Reasoning Re-Entry Doctrine / Non-Autonomous Diagnostic Reasoning Boundary.

This doctrine is created after external academic critique that the platform may risk drifting too far from clinical value if all future work is interpreted as permanently excluding diagnostic reasoning, prioritization, or clinically meaningful support.

The critique is important.

The platform should not become merely:

- a generic safety layer,
- a passive checklist,
- a scaffold without clinical reasoning depth,
- a safer wrapper around ordinary differential diagnosis lists.

The platform must remain safety-governed, but it must also preserve its intended clinical value:

> clinician-facing ILD reasoning support.

This document clarifies that previous statements such as:

- no diagnosis,
- no rule-out,
- no probability,
- no treatment,
- no clinical validation,
- no real patient data,

were valid as current scaffold-phase capability restrictions.

They are not a permanent prohibition against future governed clinician-facing diagnostic reasoning support.

This document does not rewrite prior seals.

It does not invalidate prior documents.

It does not open clinical deployment.

It does not open real patient data.

It does not open DICOM, HRCT, report, PACS, or EHR integration.

It does not open autonomous diagnosis.

It does not open autonomous disease exclusion.

It does not open treatment authority.

It does not open patient-facing use.

It does not open clinical validation in this phase.

It does not open product readiness.

It does not replace MDD.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.19.3 doctrine principle is:

> “Scaffold-phase prohibition is not permanent product philosophy.”

The corrected product direction is:

> “The platform must not make autonomous final clinical decisions, but it may later support clinician-facing, evidence-weighted ILD reasoning under explicit governance.”

---

## 2. Why This Doctrine Is Needed

The prior roadmap repeatedly sealed the current scaffold with boundaries such as:

- no diagnosis,
- no rule-out,
- no probability,
- no treatment,
- no clinical validation,
- no real patient data.

Those boundaries were necessary because the project was building:

- contracts,
- scaffold,
- local skeleton,
- placeholder files,
- synthetic fixtures,
- safe internal demo wiring.

However, if those boundaries are interpreted as permanent product doctrine, the platform would lose clinical relevance.

The platform would risk becoming:

> safe but clinically weak.

That is not the intended product.

The intended product is:

> safe, non-autonomous, clinician-facing ILD reasoning support.

This doctrine separates two concepts:

| Concept | Meaning |
|---|---|
| Current scaffold-phase restriction | What the current prototype is not allowed to do now |
| Future governed product capability | What may later be opened deliberately under new safety, evidence, review, and validation rules |

Doctrine need rule:

> Prior safety seals remain valid as phase boundaries, but they must not erase the platform’s future clinical reasoning mission.

---

## 3. No Rewrite / No Deletion Rule

This doctrine does not require deleting or rewriting previous files.

The following remain valid:

- v0.16 source-governed prototype build scaffold,
- v0.17 local file/folder scaffold planning,
- v0.18 local prototype skeleton materialization,
- checkpoint-v0.18,
- v0.19.0 static internal demo wiring entry gate,
- v0.19.1 route-to-screen binding map,
- v0.19.2 screen-to-component binding map.

No historical rewrite is required because prior documents were correct for their phase.

No repository history should be rewritten.

No prior tag should be removed.

No prior structural seal should be weakened.

Clarification rule:

> The previous seals describe what was not opened in those phases; they do not permanently ban future governed clinical reasoning support.

---

## 4. Corrected Boundary Language

The platform should no longer describe its long-term purpose as simply:

- no diagnosis,
- no rule-out,
- no probability,
- no clinical reasoning.

That framing is too broad and risks removing clinical value.

The corrected long-term boundary is:

| Area | Correct Boundary |
|---|---|
| final diagnosis | no autonomous final diagnosis |
| disease exclusion | no autonomous disease exclusion / rule-out |
| probability | no unvalidated calibrated diagnostic probability claim |
| treatment | no treatment authority |
| testing | no autonomous test-order authority |
| procedures | no autonomous procedure decision authority |
| follow-up | no autonomous follow-up scheduling authority |
| triage | no autonomous triage/disposition authority |
| patient output | no patient-facing clinical conclusion |
| MDD | no MDD replacement |
| validation | no clinical deployment before governed validation |
| data | no real/deidentified patient data until explicitly governed |

Corrected language rule:

> The platform may support clinician reasoning without becoming the clinician.

---

## 5. What Remains Blocked

The following remain blocked in the current phase and as autonomous product behavior:

| Capability | State |
|---|---|
| autonomous final diagnosis | blocked |
| autonomous disease exclusion / rule-out | blocked |
| autonomous treatment recommendation | blocked |
| autonomous test ordering | blocked |
| autonomous procedure recommendation | blocked |
| autonomous follow-up scheduling | blocked |
| autonomous triage / disposition | blocked |
| patient-facing diagnosis or reassurance | blocked |
| patient-facing report | blocked |
| MDD final consensus generation | blocked |
| MDD replacement | blocked |
| unvalidated clinical deployment | blocked |
| unvalidated diagnostic performance claim | blocked |
| hidden clinical override | blocked |
| real patient data use without governance | blocked |
| deidentified real patient data use without governance | blocked |
| DICOM/HRCT/report/PACS/EHR integration without governance | blocked |

Blocked rule:

> The platform must not cross from clinician-facing reasoning support into autonomous clinical authority.

---

## 6. What May Be Re-Opened Later Under Governance

The following may be developed later under explicit governance, source control, expert review, and appropriate validation pathways:

| Future Capability Candidate | Allowed Direction |
|---|---|
| ILD pattern reasoning | clinician-facing pattern interpretation support |
| distribution reasoning | axial/cranio-caudal/peribronchovascular/subpleural reasoning support |
| temporal reasoning | progression, stability, acute-on-chronic reasoning support |
| evidence-weighted differential reasoning | transparent evidence-weighted reasoning, not autonomous final diagnosis |
| mimic persistence | keeping mimics visible until evidence justifies closure |
| overlap reasoning | showing why patterns overlap rather than forcing one label |
| missing evidence logic | identifying evidence needed before stronger interpretation |
| source status logic | separating strong, weak, absent, conflicting, and unsupported evidence |
| confidence limitation | explaining why confidence must remain limited |
| MDD preparation | preparing clinician-facing reasoning questions and evidence gaps |
| report safety support | highlighting overclaim, premature closure, and missing evidence language |
| clinician review workspace | supporting expert review without replacing it |

Future allowance rule:

> Future clinical reasoning support is allowed only when it is non-autonomous, clinician-facing, evidence-transparent, source-governed, and explicitly separated from final clinical authority.

---

## 7. Diagnosis vs Diagnostic Reasoning

The platform must distinguish:

| Not Allowed | Potentially Allowed Later |
|---|---|
| “The diagnosis is X.” | “The current evidence supports reasoning toward/against these possibilities, with stated limitations.” |
| “This rules out Y.” | “Y remains less supported / still unresolved because specific evidence is missing.” |
| “Probability is 82%.” | “Evidence weight appears stronger/weaker, without calibrated probability claim unless validated.” |
| “Treat with Z.” | “Management decisions remain outside this platform; MDD/clinician review required.” |
| “Final MDD conclusion is X.” | “MDD preparation questions and evidence summary.” |

Diagnostic reasoning rule:

> The platform may help clinicians reason diagnostically; it must not autonomously close diagnosis.

---

## 8. Differential List vs Reasoning Platform

The platform should not compete by merely listing differential diagnoses.

A simple differential list says:

- UIP,
- NSIP,
- HP,
- sarcoidosis,
- organizing pneumonia,
- drug toxicity,
- CTD-ILD,
- edema,
- infection,
- malignancy.

That is not enough.

The ILD Reasoning Platform should instead answer reasoning questions such as:

- Which finding changes interpretation most?
- Which missing evidence prevents closure?
- Which mimic remains dangerous to ignore?
- Which pattern overlap is unresolved?
- Which exposure or serology would change the reasoning?
- Which HRCT distribution feature is carrying the most weight?
- Which report phrase would overclaim?
- Which MDD question should be asked next?
- Why should confidence remain limited?
- What evidence would strengthen or weaken a candidate reasoning path?

Differentiation rule:

> The platform’s value is not listing diseases; its value is governing how clinicians reason before naming disease.

---

## 9. Evidence-Weighted Reasoning Boundary

Future evidence-weighted reasoning may be permitted if it remains:

- clinician-facing,
- transparent,
- source-governed,
- evidence-specific,
- uncertainty-preserving,
- review-required,
- non-autonomous,
- non-patient-facing.

It must not become:

- hidden probability,
- unvalidated numeric diagnostic score,
- final diagnosis,
- disease exclusion,
- treatment recommendation,
- clinical validation claim,
- MDD replacement.

Evidence weighting rule:

> Evidence may be weighted for reasoning transparency, but not converted into autonomous clinical truth.

---

## 10. Clinical Validation Boundary

Current phase state remains:

| Field | State |
|---|---|
| clinical_validation | not_opened |
| diagnostic_performance_claim | not_allowed |
| real_patient_data | not_allowed |
| DICOM/HRCT/report/PACS/EHR | not_opened |

However, future validation should not be philosophically banned.

Future clinical validation may be opened only through a separate governed phase that defines:

- data governance,
- ethics/IRB requirements when applicable,
- deidentification rules,
- expert review workflow,
- ground-truth limitations,
- performance metrics,
- failure analysis,
- intended use,
- non-autonomous labeling,
- regulatory pathway review,
- deployment restrictions.

Validation doctrine rule:

> Clinical validation is not opened now, but it may become necessary later before any clinical claims or deployment.

---

## 11. Real Patient Data Boundary

Current phase state remains:

| Field | State |
|---|---|
| real_patient_data | not_allowed |
| deidentified_real_patient_data | not_allowed |
| DICOM_import | not_allowed |
| HRCT_import | not_allowed |
| real_report_import | not_allowed |
| PACS_connection | not_allowed |
| EHR_connection | not_allowed |

This remains correct for the current local synthetic prototype.

Future real or deidentified patient data work may be considered only if a separate governance layer opens:

- data source authority,
- consent/ethics requirements,
- deidentification requirements,
- storage rules,
- access controls,
- audit rules,
- clinical validation scope,
- non-patient-facing restrictions,
- regulatory considerations.

Data doctrine rule:

> Real patient data is not opened now; future patient-data phases require explicit governance before any use.

---

## 12. MDD Boundary

The platform must not replace MDD.

However, it may later support MDD preparation by organizing:

- evidence gaps,
- mimic persistence,
- overlap reasoning,
- source status,
- uncertainty boundaries,
- questions for discussion,
- report overclaim warnings,
- reasoning summary for expert review.

MDD support rule:

> The platform may prepare better MDD discussion, but it must not generate MDD final consensus.

---

## 13. Roadmap Correction

The roadmap should shift from safety-only framing toward clinically meaningful governed reasoning.

The current path remains:

- v0.18 — local skeleton materialized,
- v0.19 — static internal demo wiring.

The recommended upcoming direction is:

| Version | Direction |
|---|---|
| v0.19.4 | Component-to-Synthetic ILD Reasoning Fixture Binding Map |
| v0.19.5 | Safety / Authority / No-Decision Placement Map |
| v0.19.6 | Fail-Closed / Disabled Controls Display Binding Plan |
| v0.19.7 | Audit / Export / Red-Team Walkthrough Binding Plan |
| v0.19.8 | Static Internal Demo Wiring Checklist |
| v0.19.9 | Static Internal Demo Wiring Structural Seal |
| checkpoint-v0.19 | Project status checkpoint |
| v0.20 | ILD Clinical Reasoning Content Re-Entry / Non-Autonomous Diagnostic Reasoning Kernel |

Roadmap correction rule:

> Future steps should preserve safety while returning clinical reasoning to the center of the platform.

---

## 14. Naming Correction for Future Steps

Future step names should avoid implying that the product is only a safety wrapper.

Better future names include:

- ILD reasoning fixture,
- pattern reasoning surface,
- mimic persistence surface,
- missing evidence reasoning,
- source-weighted reasoning,
- overlap reasoning,
- confidence limitation reasoning,
- MDD preparation reasoning,
- report overclaim guard,
- non-autonomous differential reasoning.

Avoid overusing generic names such as:

- safety layer only,
- blocked use only,
- no diagnosis only,
- no probability only,
- no clinical reasoning.

Naming rule:

> Names should communicate safety and clinical reasoning value together.

---

## 15. Current Phase Still Closed

This doctrine does not immediately open new capabilities.

Current phase remains:

| Capability | State |
|---|---|
| clinical implementation | not_opened |
| real patient data | not_allowed |
| deidentified patient data | not_allowed |
| DICOM/HRCT/report/PACS/EHR | not_opened |
| autonomous diagnosis | blocked |
| autonomous rule-out | blocked |
| calibrated probability | not_opened |
| treatment authority | none |
| clinical validation | not_opened |
| patient-facing use | not_allowed |
| public readiness | false |
| product readiness | false |
| MDD replacement | not_allowed |

Current phase rule:

> v0.19.3 clarifies doctrine; it does not open clinical capability.

---

## 16. Acceptance Criteria

v0.19.3 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| prior scaffold seals preserved | true |
| no prior files require deletion | true |
| no prior tags require removal | true |
| previous no-diagnosis/no-probability/no-rule-out statements clarified as phase-scoped | true |
| autonomous final diagnosis remains blocked | true |
| autonomous disease exclusion remains blocked | true |
| treatment authority remains none | true |
| patient-facing use remains not_allowed | true |
| clinical validation remains not_opened in current phase | true |
| real patient data remains not_allowed in current phase | true |
| DICOM/HRCT/report/PACS/EHR remains not_opened in current phase | true |
| future clinician-facing diagnostic reasoning support is not permanently prohibited | true |
| future evidence-weighted ILD reasoning may be opened only under governance | true |
| future clinical validation may be opened only through explicit governed phase | true |
| MDD replacement remains blocked | true |
| roadmap correction defined | true |
| prototype file count remains 191 | true |
| authority envelope preserved for current phase | true |
| no-decision object preserved for current phase | true |

Acceptance rule:

> v0.19.3 is valid only if it restores clinical reasoning direction without opening autonomous clinical authority.

---

## 17. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected prototype count remains:

    prototype file count = 191

Verification rule:

> This doctrine adds a docs clarification only; it must not mutate the prototype skeleton.

---

## 18. Next Step

The next recommended step is:

    v0.19.4 — Component-to-Synthetic ILD Reasoning Fixture Binding Map

This step should map components not merely to generic fixtures, but to synthetic ILD reasoning fixture roles such as:

- missing evidence visibility,
- mimic visibility,
- overlap reasoning,
- source status,
- confidence limitation,
- review prompt,
- safe export preview,
- MDD preparation structure,
- red-team containment.

v0.19.4 must still remain:

- internal,
- synthetic,
- non-clinical,
- no real patient data,
- no deidentified patient data,
- no DICOM/HRCT/report/PACS/EHR,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no treatment authority,
- no clinical validation opened,
- no patient-facing use,
- no public readiness,
- no product readiness,
- no MDD replacement.

Next-step rule:

> Future wiring should reconnect safety surfaces to clinically meaningful ILD reasoning surfaces.

---

## 19. Governance Statement

This document records a doctrine clarification.

It does not implement a clinical product.

It does not diagnose autonomously.  
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

The v0.19.3 discipline is:

> “Keep autonomous clinical authority closed, but reopen the roadmap toward clinician-facing ILD reasoning value.”

The final v0.19.3 boundary is:

> “Safety is the guardrail; clinical reasoning is the destination.”
