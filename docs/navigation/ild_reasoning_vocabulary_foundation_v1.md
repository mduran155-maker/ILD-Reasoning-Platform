# ILD Reasoning Platform — ILD Reasoning Vocabulary Foundation v1

Version: v0.20.2  
Status: reasoning_vocabulary_foundation  
Scope: Source-governed non-autonomous ILD reasoning vocabulary after v0.20.1  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.2:

- ILD Reasoning Vocabulary Foundation.

v0.20.2 follows:

- v0.20.1 — ILD Source Corpus / Reference Backbone Intake,
- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.1 admitted the source backbone.

v0.20.2 defines the first platform vocabulary layer for source-governed ILD reasoning.

This vocabulary is not a diagnosis engine.

It is not a disease-ranking system.

It is not a probability model.

It is not a treatment system.

It is a controlled language layer for representing:

- what is observed,
- what is missing,
- what is mixed,
- what overlaps,
- what remains unresolved,
- what evidence supports,
- what evidence weakens,
- what evidence conflicts,
- what requires review,
- why confidence remains limited,
- why mimics remain visible,
- why MDD preparation is needed.

This vocabulary exists to prevent two failures:

1. Clinically weak generic safety language.
2. Unsafe autonomous clinical conclusion language.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.2 principle is:

> “Give the platform clinical reasoning language without giving it clinical authority.”

The permanent boundary is:

> “Vocabulary can structure reasoning; vocabulary must not close diagnosis.”

---

## 2. Required Previous State

v0.20.2 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.20.1 source corpus intake exists | true |
| v0.20.0 content re-entry entry gate exists | true |
| checkpoint-v0.19 exists | true |
| v0.19.9 structural seal exists | true |
| clinical reasoning re-entry doctrine preserved | true |
| prototype file count remains 191 | true |
| working tree before v0.20.2 is clean | true |
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

> v0.20.2 may define vocabulary only under the v0.20.1 source backbone and current non-autonomous authority envelope.

---

## 3. Source-Governed Vocabulary Rule

Every vocabulary family must declare:

- source role,
- reasoning use,
- allowed phrase pattern,
- blocked phrase pattern,
- authority boundary.

Source-governed vocabulary rule:

> No clinical reasoning term may enter the platform unless its source role and authority boundary are visible.

Vocabulary terms may be supported by:

- terminology_core,
- classification_core,
- guideline_core,
- consensus_core,
- review_support,
- mimic_support,
- oncology_treatment_risk_support,
- occupational_exposure_support,
- edge_case_support,
- internal_doctrine.

Vocabulary terms must not claim:

- autonomous final diagnosis,
- autonomous exclusion,
- calibrated probability,
- treatment instruction,
- clinical validation,
- patient-facing conclusion,
- MDD final consensus.

---

## 4. Vocabulary Object Shape

Future vocabulary entries should follow this shape:

    {
      "term_id": "string",
      "display_label": "string",
      "vocabulary_family": "string",
      "source_role": "terminology_core | classification_core | guideline_core | consensus_core | review_support | mimic_support | internal_doctrine",
      "allowed_reasoning_use": "string",
      "blocked_clinical_use": "string",
      "authority_boundary": "non_autonomous_reasoning_only",
      "patient_data_required": false,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "calibrated_probability_allowed": false,
      "treatment_authority_allowed": false,
      "review_required": true
    }

Object-shape rule:

> Vocabulary entries must carry their own safety boundary, not rely on hidden global disclaimers.

---

## 5. Core Vocabulary Families

v0.20.2 defines the following vocabulary families.

| Vocabulary Family | Role |
|---|---|
| observation_status | records whether a feature is observed, absent, partial, mixed, or not assessable |
| pattern_descriptor | describes HRCT pattern-level findings without disease closure |
| distribution_descriptor | describes anatomic distribution relevant to reasoning |
| temporal_descriptor | describes time-course and interval behavior |
| process_type_descriptor | describes fibrotic, inflammatory, airway-centered, nodular, cystic, vascular/lymphatic, or mixed process logic |
| evidence_status | describes evidence as present, missing, conflicting, unsupported, or weak |
| source_status | describes where information came from and whether it is reliable enough for reasoning |
| reasoning_relation | describes how evidence supports, weakens, overlaps, or fails to close a reasoning path |
| mimic_visibility | preserves unresolved mimics and alternative causes |
| confidence_limiter | explains why confidence remains limited without probability |
| review_requirement | marks clinician or MDD review requirement |
| report_safety_language | prevents overclaim in export/report-like surfaces |
| forbidden_closure_language | blocks unsafe final diagnosis / rule-out / treatment terms |

Family rule:

> Vocabulary families must improve clinical reasoning precision without creating clinical authority.

---

## 6. Observation Status Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| observed | a feature is visible in the synthetic/internal reasoning context | proof of diagnosis |
| not_observed | a feature is not visible in the available context | disease ruled out |
| partially_observed | feature is incompletely visible | partial diagnosis |
| mixed | multiple descriptor families coexist | final overlap diagnosis |
| indeterminate | available evidence does not support stronger language | diagnostic failure claim |
| not_assessable | required source or view is unavailable | negative result |
| not_provided | clinician/input source did not supply the field | absence of disease |
| source_unavailable | source is missing | evidence against disease |
| requires_review | clinician/MDD review needed | automatic escalation |
| out_of_scope_current_phase | cannot be assessed in current prototype phase | permanent product prohibition |

Observation rule:

> Absence of visibility is not disease exclusion.

---

## 7. Pattern Descriptor Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| fibrotic_pattern | fibrosis-related pattern features are being reasoned about | final fibrotic ILD diagnosis |
| inflammatory_pattern | inflammatory or potentially active pattern features are being reasoned about | treatment selection |
| airway_centered_pattern | small-airways / bronchiolocentric reasoning surface | final HP diagnosis |
| nodular_pattern | nodule-distribution reasoning surface | final sarcoidosis / infection / malignancy diagnosis |
| cystic_pattern | cystic lung disease reasoning surface | final cystic disease diagnosis |
| organizing_pattern | organizing-pneumonia-like reasoning surface | final OP diagnosis |
| vascular_or_lymphatic_pattern | vascular/lymphatic mimic reasoning surface | final malignancy claim |
| mixed_pattern | more than one pattern family is visible | forced single disease label |
| indeterminate_pattern | pattern does not safely support stronger classification | diagnostic endpoint |
| pattern_not_assessable | pattern cannot be assessed from available synthetic source | negative finding |

Pattern rule:

> A pattern descriptor is not a disease name.

---

## 8. Distribution Descriptor Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| upper_lung_predominant | distribution reasoning | automatic sarcoidosis / HP / pneumoconiosis conclusion |
| lower_lung_predominant | distribution reasoning | automatic UIP/IPF conclusion |
| diffuse | extent reasoning | severity score |
| focal | localization reasoning | benign/malignant conclusion |
| patchy | heterogeneity reasoning | final OP/HP label |
| symmetric | distribution symmetry reasoning | diagnosis |
| asymmetric | distribution asymmetry reasoning | malignancy conclusion |
| subpleural | peripheral distribution reasoning | automatic UIP/IPF conclusion |
| peribronchovascular | axial distribution reasoning | automatic sarcoidosis/NSIP/PLC conclusion |
| central | axial distribution reasoning | diagnosis |
| peripheral | axial distribution reasoning | diagnosis |
| basal | craniocaudal reasoning | diagnosis |
| apical | craniocaudal reasoning | diagnosis |
| random_distribution | nodule distribution reasoning | final hematogenous spread claim |
| perilymphatic_distribution | nodule distribution reasoning | final sarcoidosis/PLC claim |
| centrilobular_distribution | nodule/airway-centered reasoning | final HP/infection claim |

Distribution rule:

> Distribution changes reasoning weight; it does not close diagnosis.

---

## 9. Temporal Descriptor Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| acute | time-course reasoning | emergency triage decision |
| subacute | time-course reasoning | diagnosis |
| chronic | time-course reasoning | diagnosis |
| progressive | interval worsening reasoning | treatment decision |
| stable | interval stability reasoning | reassurance |
| improving | interval improvement reasoning | disease excluded |
| fluctuating | variable behavior reasoning | final inflammatory diagnosis |
| acute_on_chronic | superimposed process reasoning | treatment recommendation |
| rapid_progression | high-concern reasoning prompt | automatic triage |
| slow_progression | fibrotic behavior reasoning | diagnostic probability |
| post_treatment_temporal_link | treatment-related context reasoning | treatment causality conclusion |
| exposure_latency_relevant | exposure-related context reasoning | occupational causality conclusion |
| temporal_data_missing | missing evidence | negative temporal evidence |

Temporal rule:

> Temporal behavior modifies reasoning; it must not become automatic prognosis, diagnosis, or treatment.

---

## 10. Process-Type Descriptor Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| fibrotic_process | fibrosis reasoning | final fibrotic diagnosis |
| inflammatory_process | inflammatory reasoning | steroid recommendation |
| airway_centered_process | airway/small-airway reasoning | final HP/infectious bronchiolitis claim |
| granulomatous_process | granulomatous reasoning | final sarcoidosis claim |
| nodular_process | nodule reasoning | final malignant/infectious/granulomatous claim |
| cystic_process | cystic reasoning | final cystic disease diagnosis |
| lymphatic_process | lymphangitic/perilymphatic reasoning | final malignancy or sarcoidosis claim |
| treatment_related_process | drug/radiation/ICI context reasoning | treatment management decision |
| exposure_related_process | occupational/environmental context reasoning | causality/legal conclusion |
| infection_mimic_process | infectious mimic visibility | infection diagnosis |
| malignancy_mimic_process | malignancy mimic visibility | cancer diagnosis |
| edema_or_cardiac_mimic_process | edema/cardiac mimic visibility | cardiac diagnosis |
| mixed_process | multiple process families remain active | final unifying diagnosis |
| unresolved_process | process cannot be safely assigned | diagnostic closure |

Process-type rule:

> Process language helps organize reasoning before disease naming.

---

## 11. Evidence Status Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| evidence_present | evidence exists in the synthetic/internal source | proof |
| evidence_absent_from_source | source does not show/supply evidence | disease absent |
| evidence_missing | required evidence not provided | negative evidence |
| evidence_conflicting | sources disagree | automatic uncertainty score |
| evidence_weak | limited support | probability |
| evidence_strong_for_reasoning | stronger support for a reasoning path | final diagnosis |
| evidence_nonspecific | evidence can support multiple possibilities | useless evidence |
| evidence_unverified | source not verified | false evidence |
| evidence_out_of_scope | current prototype cannot assess it | impossible future capability |
| evidence_requires_review | evidence needs clinician/MDD review | autonomous escalation |

Evidence rule:

> Evidence status supports reasoning transparency; it does not certify truth.

---

## 12. Source Status Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| synthetic_fixture_source | internal fictional source | real case |
| clinician_supplied_source | clinician-entered structured field | verified truth |
| literature_backbone_source | source corpus term | direct clinical instruction |
| source_not_provided | missing source | negative result |
| source_conflict | conflicting source fields | automatic decision |
| source_stale | old source / outdated context | automatic exclusion |
| source_unverified | not independently checked | clinical fact |
| source_requires_review | needs expert interpretation | automatic validation |
| source_supports_reasoning_only | may structure reasoning | clinical authority |

Source rule:

> Source status controls how evidence can be used; it must not become clinical authority.

---

## 13. Reasoning Relation Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| supports_reasoning_toward | evidence supports a candidate reasoning path | diagnosis |
| weakens_reasoning_toward | evidence weakens a path | rule-out |
| compatible_with | evidence is compatible with a path | confirmation |
| not_specific_for | evidence is nonspecific | dismissal |
| overlaps_with | evidence overlaps multiple paths | forced ranking |
| does_not_close | evidence insufficient for closure | failure |
| raises_mimic_visibility | mimic should remain visible | mimic diagnosis |
| requires_missing_evidence_review | gap must be reviewed | automatic test order |
| requires_mdd_discussion | topic belongs in MDD preparation | MDD consensus |
| cannot_be_closed_currently | closure unsafe in current evidence state | permanent impossibility |

Reasoning relation rule:

> Reasoning relations describe directionality, not clinical endpoint.

---

## 14. Mimic Visibility Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| mimic_visible | mimic remains visible | mimic diagnosis |
| mimic_unresolved | mimic not closed | mimic confirmed |
| mimic_evidence_missing | needed evidence absent | mimic excluded |
| mimic_overlap_present | overlapping features exist | final overlap diagnosis |
| infection_mimic_visible | infection remains a consideration | infection diagnosis |
| granulomatous_mimic_visible | granulomatous mimic remains visible | sarcoidosis diagnosis |
| malignancy_mimic_visible | malignancy mimic remains visible | malignancy diagnosis |
| drug_related_mimic_visible | drug-related injury remains visible | DI-ILD diagnosis |
| radiation_related_mimic_visible | radiation-related injury remains visible | RP/RILI diagnosis |
| edema_mimic_visible | edema/cardiac mimic remains visible | cardiac diagnosis |
| occupational_mimic_visible | occupational/exposure mimic remains visible | occupational causality claim |

Mimic rule:

> Mimic visibility means “do not forget,” not “diagnose.”

---

## 15. Confidence Limiter Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| confidence_limited_by_missing_evidence | gap limits confidence | numeric probability |
| confidence_limited_by_source_conflict | conflicting source limits confidence | automatic downgrade score |
| confidence_limited_by_overlap | overlap limits confidence | ranking |
| confidence_limited_by_mimic_persistence | mimic remains unresolved | mimic exclusion |
| confidence_limited_by_temporal_uncertainty | timing unclear | prognosis |
| confidence_limited_by_distribution_uncertainty | distribution uncertain | diagnosis |
| confidence_limited_by_no_patient_data | no real data in current phase | product failure |
| confidence_limited_by_current_phase_boundary | prototype limitation | permanent prohibition |
| no_calibrated_probability_available | probability not opened | hidden score |
| review_required_before_stronger_language | review needed | final MDD decision |

Confidence rule:

> Confidence limitation prevents overclaim; it does not compute probability.

---

## 16. Review Requirement Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| clinician_review_required | clinician interpretation required | automatic clinician decision |
| mdd_preparation_relevant | useful for MDD preparation | MDD consensus |
| radiology_review_relevant | radiology review relevant | final radiology report |
| pulmonology_review_relevant | pulmonology review relevant | treatment plan |
| rheumatology_review_relevant | CTD context review relevant | CTD diagnosis |
| occupational_review_relevant | exposure context review relevant | occupational causality |
| oncology_review_relevant | cancer/treatment context review relevant | oncology management |
| pathology_review_relevant | tissue/source review relevant | pathology diagnosis |
| microbiology_review_relevant | infection mimic review relevant | infection diagnosis |

Review rule:

> Review vocabulary routes uncertainty to humans; it must not simulate expert consensus.

---

## 17. Report Safety Vocabulary

| Term | Allowed Use | Blocked Use |
|---|---|---|
| overclaim_risk | phrase may overstate conclusion | automatic deletion without review |
| premature_closure_risk | reasoning may close too early | final warning to patient |
| uncertainty_preserving_language_needed | safer language needed | clinical report generation |
| missing_evidence_should_be_named | gap should be visible | test order |
| mimic_should_remain_visible | mimic should not disappear | mimic diagnosis |
| source_status_should_be_visible | source status should be displayed | validation claim |
| review_required_phrase_needed | review requirement should be stated | MDD conclusion |
| export_preview_only | internal preview only | clinical report |
| not_patient_facing | not for patient output | patient advice |

Report safety rule:

> Report safety vocabulary protects wording; it must not generate final report conclusions.

---

## 18. Forbidden Closure Language

The following terms are blocked unless a future separately governed clinical-authority phase explicitly redefines them.

| Forbidden Language | Reason |
|---|---|
| diagnosis is | autonomous final diagnosis |
| confirms | diagnostic closure |
| rules out | autonomous exclusion |
| excludes | autonomous exclusion |
| definitive | overclaim |
| pathognomonic | overclaim unless source-specific and governed |
| probability is X percent | calibrated probability |
| ranked first | disease ranking |
| most likely diagnosis | final-priority claim |
| treat with | treatment authority |
| start / stop medication | treatment authority |
| order test | test-order authority |
| schedule follow-up | follow-up authority |
| triage to | triage authority |
| patient should | patient-facing clinical instruction |
| MDD consensus is | MDD replacement |
| clinically validated | validation claim |
| product ready | product readiness claim |

Forbidden language rule:

> Closure language must be blocked before it appears in UI copy, export preview, or reasoning output.

---

## 19. Allowed Non-Autonomous Reasoning Phrases

The platform may use non-autonomous phrases such as:

- “This feature supports reasoning toward...”
- “This feature weakens reasoning toward...”
- “This finding is compatible with more than one reasoning path.”
- “This mimic remains visible.”
- “This evidence is missing.”
- “This source is not sufficient for closure.”
- “Confidence remains limited because...”
- “This should be reviewed by a clinician.”
- “This may be relevant for MDD preparation.”
- “This wording may overclaim.”
- “A safer phrasing should preserve uncertainty.”

Allowed phrase rule:

> Non-autonomous phrases should make the reasoning path visible without closing the clinical answer.

---

## 20. Disease-Name Boundary

Disease names may appear only as candidate reasoning labels or source-context labels.

Allowed:

- “UIP-pattern reasoning anchor”
- “NSIP-pattern reasoning anchor”
- “organizing-pattern reasoning anchor”
- “sarcoidosis mimic visibility”
- “drug-induced ILD context”
- “radiation pneumonitis mimic context”
- “lymphangitic carcinomatosis mimic context”
- “hypersensitivity pneumonitis overlap context”
- “CTD-ILD context”

Blocked:

- “The diagnosis is UIP.”
- “This is IPF.”
- “This rules out HP.”
- “This confirms sarcoidosis.”
- “This is drug-induced ILD.”
- “This is radiation pneumonitis.”
- “This is lymphangitic carcinomatosis.”
- “This excludes infection.”
- “This excludes malignancy.”

Disease-name rule:

> Disease names may label reasoning contexts; they must not become final outputs.

---

## 21. Vocabulary Governance Matrix

| Vocabulary Family | Source Role | Authority Boundary |
|---|---|---|
| observation_status | internal_doctrine | non-autonomous visibility |
| pattern_descriptor | terminology_core / classification_core | pattern not diagnosis |
| distribution_descriptor | terminology_core / classification_core | distribution not closure |
| temporal_descriptor | classification_core / consensus_core | time-course not prognosis |
| process_type_descriptor | terminology_core / review_support | process not disease |
| evidence_status | guideline_core / internal_doctrine | evidence not truth |
| source_status | internal_doctrine / guideline_core | source not authority |
| reasoning_relation | internal_doctrine / guideline_core | relation not endpoint |
| mimic_visibility | guideline_core / mimic_support | mimic not diagnosis |
| confidence_limiter | internal_doctrine / consensus_core | limitation not probability |
| review_requirement | guideline_core / internal_doctrine | review not consensus |
| report_safety_language | terminology_core / internal_doctrine | safety not report generation |
| forbidden_closure_language | internal_doctrine | hard block |

Governance matrix rule:

> Every vocabulary family must preserve its source role and boundary.

---

## 22. Current-Phase Authority Envelope

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

> Vocabulary improves reasoning expression; it does not change current clinical authority.

---

## 23. Prototype File Count Preservation

v0.20.2 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.2 is docs-only vocabulary governance; the materialized prototype skeleton remains unchanged.

---

## 24. Acceptance Criteria

v0.20.2 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.1 dependency listed | true |
| source-governed vocabulary rule defined | true |
| vocabulary object shape defined | true |
| core vocabulary families defined | true |
| observation status vocabulary defined | true |
| pattern descriptor vocabulary defined | true |
| distribution descriptor vocabulary defined | true |
| temporal descriptor vocabulary defined | true |
| process-type descriptor vocabulary defined | true |
| evidence status vocabulary defined | true |
| source status vocabulary defined | true |
| reasoning relation vocabulary defined | true |
| mimic visibility vocabulary defined | true |
| confidence limiter vocabulary defined | true |
| review requirement vocabulary defined | true |
| report safety vocabulary defined | true |
| forbidden closure language defined | true |
| disease-name boundary defined | true |
| vocabulary governance matrix defined | true |
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

> v0.20.2 is valid only if ILD reasoning vocabulary becomes clinically meaningful while remaining non-autonomous.

---

## 25. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Vocabulary foundation verifies reasoning-language governance only; it does not certify clinical performance.

---

## 26. Next Step

The next recommended step is:

    v0.20.3 — HRCT Pattern Reasoning Anchor Map

v0.20.3 should define source-governed pattern-level anchors for:

- fibrotic pattern,
- inflammatory pattern,
- airway-centered pattern,
- nodular pattern,
- cystic pattern,
- organizing pattern,
- lymphatic / vascular mimic pattern,
- mixed pattern,
- indeterminate pattern.

v0.20.3 must preserve:

- pattern not diagnosis,
- descriptor not disease,
- mimic visibility,
- missing evidence,
- confidence limitation,
- review required,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no patient-facing output,
- no clinical validation,
- no MDD replacement.

Next-step rule:

> v0.20.3 should turn vocabulary into HRCT pattern reasoning anchors without closing disease labels.

---

## 27. Governance Statement

This document records v0.20.2 ILD Reasoning Vocabulary Foundation.

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

The v0.20.2 discipline is:

> “Create clinical reasoning vocabulary without creating clinical closure.”

The final v0.20.2 boundary is:

> “The platform can now speak clinically meaningful reasoning language; it still cannot decide.”
