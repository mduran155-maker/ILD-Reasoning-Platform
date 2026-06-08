# ILD Reasoning Platform — MDD Preparation / Report Overclaim Guard Map v1

Version: v0.20.9  
Status: mdd_preparation_report_overclaim_guard_map  
Scope: Source-governed MDD preparation and report overclaim guard map after v0.20.8  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.9:

- MDD Preparation / Report Overclaim Guard Map.

v0.20.9 follows:

- v0.20.8 — Non-Calibrated Evidence-Weighted Reasoning Surface,
- v0.20.7 — Missing Evidence / Source Status Logic,
- v0.20.6 — Mimic / Overlap Persistence Matrix,
- v0.20.5 — Process-Type Reasoning Map,
- v0.20.4 — Distribution / Temporal Reasoning Map,
- v0.20.3 — HRCT Pattern Reasoning Anchor Map,
- v0.20.2a — ILD Reference Bibliography / Citation Manifest,
- v0.20.2 — ILD Reasoning Vocabulary Foundation,
- v0.20.1 — ILD Source Corpus / Reference Backbone Intake,
- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.3 defined HRCT pattern reasoning anchors.

v0.20.4 defined distribution and temporal reasoning.

v0.20.5 defined process-type reasoning.

v0.20.6 defined mimic and overlap persistence.

v0.20.7 defined missing evidence and source status logic.

v0.20.8 defined non-calibrated evidence-weighted reasoning.

v0.20.9 converts those reasoning layers into two clinician-visible safety/value surfaces:

1. MDD preparation.
2. Report overclaim guard.

This is not MDD consensus.

This is not report generation.

This is not final impression generation.

This is not autonomous diagnosis.

This is not autonomous rule-out.

This is not probability.

This is not treatment.

This is not causality.

This is not patient-facing output.

The platform must be able to prepare better clinician-facing questions:

- Which evidence gap prevents stronger language?
- Which mimic remains dangerous to ignore?
- Which overlap should be discussed?
- Which source conflict should be reconciled?
- Which distribution or temporal feature changes the reasoning?
- Which treatment, exposure, cancer, infection, CTD, pathology, or microbiology context is missing?
- Which report phrase would overclaim?
- Which safer wording preserves uncertainty?
- Which source supports the reasoning surface?
- Which source cannot be used for clinical authority?

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.9 principle is:

> “Prepare better MDD discussion and safer wording without generating clinical conclusions.”

The permanent boundary is:

> “MDD preparation is not MDD consensus; report guard is not report generation.”

---

## 2. Required Previous State

v0.20.9 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.20.8 non-calibrated evidence-weighted reasoning surface exists | true |
| v0.20.7 missing evidence / source status logic exists | true |
| v0.20.6 mimic / overlap persistence matrix exists | true |
| v0.20.5 process-type reasoning map exists | true |
| v0.20.4 distribution / temporal reasoning map exists | true |
| v0.20.3 HRCT pattern anchor map exists | true |
| v0.20.2a bibliography / citation manifest exists | true |
| v0.20.2 vocabulary foundation exists | true |
| v0.20.1 source corpus intake exists | true |
| v0.20.0 content re-entry entry gate exists | true |
| checkpoint-v0.19 exists | true |
| v0.19.9 structural seal exists | true |
| clinical reasoning re-entry doctrine preserved | true |
| prototype file count remains 191 | true |
| working tree before v0.20.9 is clean | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no autonomous mimic exclusion opened | true |
| no calibrated probability opened | true |
| no numeric confidence score opened | true |
| no ranking opened | true |
| no treatment authority opened | true |
| no causality authority opened | true |
| no prognosis authority opened | true |
| no reassurance authority opened | true |
| no patient-facing output opened | true |
| no real patient data opened | true |
| no deidentified patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |

Dependency rule:

> v0.20.9 may define MDD preparation and report overclaim guard only under source-governed vocabulary, citation manifest, pattern anchors, distribution/temporal reasoning, process-type reasoning, mimic persistence, missing evidence/source status logic, evidence-weighted reasoning, and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.9 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.9 |
|---|---|---|
| terminology_core | SRC-001 | report wording precision, descriptor-vs-disease boundary, overclaim reduction |
| classification_core | SRC-002 | broad ILD context, MDD integration need, pattern overlap and unclassifiable ILD awareness |
| consensus_core | SRC-003 | progression-related MDD questions and longitudinal reasoning |
| guideline_core | SRC-004, SRC-005, SRC-006 | diagnostic uncertainty, evidence gaps, alternative-cause visibility, review requirement |
| review_support | SRC-007, SRC-010 | DI-ILD/RILI nonspecificity, treatment-related mimic and exclusion logic |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | infectious, granulomatous, sarcoid-like, lymphoma, malignancy, PLC mimic questions |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | drug/radiation/ICI/cancer-follow-up MDD questions without management authority |
| occupational_exposure_support | SRC-012 | occupational/environmental exposure questions without causality authority |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | red-team overclaim traps and rare mimic reminders only |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | non-autonomous authority envelope, no-decision boundary, source-governed behavior |

Source rule:

> MDD preparation and report overclaim guard must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. Core Concepts

v0.20.9 defines the following core concepts.

| Concept | Meaning | Blocked Misuse |
|---|---|---|
| MDD_preparation | evidence-gap and reasoning-question package for clinician/MDD review | MDD consensus |
| MDD_question | non-autonomous question to support discussion | clinical instruction |
| evidence_gap_question | question created from missing evidence | test order |
| mimic_persistence_question | question created from unresolved mimic | mimic diagnosis |
| overlap_question | question created from overlapping paths | disease ranking |
| source_conflict_question | question created from conflicting or incomplete sources | automatic decision |
| report_overclaim_guard | detects language that overstates evidence | report generation |
| uncertainty_preserving_language | safer wording that keeps limitations visible | final impression |
| forbidden_report_phrase | unsafe closure phrase | editable suggestion as diagnosis |
| review_prompt | request for clinician review | clinical order |
| citation_trail | source trace supporting reasoning surface | clinical validation |
| export_preview_boundary | internal non-clinical preview status | clinical report |

Core rule:

> MDD and report surfaces must turn reasoning into better questions and safer wording, not clinical conclusions.

---

## 5. MDD Preparation Families

v0.20.9 defines the following MDD preparation families:

| MDD Preparation Family | Meaning |
|---|---|
| pattern_mdd_question | pattern-level question |
| distribution_mdd_question | spatial distribution question |
| temporal_mdd_question | onset, prior imaging, interval, progression, treatment timing question |
| process_mdd_question | process-type reasoning question |
| mimic_mdd_question | unresolved mimic question |
| overlap_mdd_question | unresolved overlap question |
| missing_evidence_mdd_question | missing evidence question |
| source_status_mdd_question | source conflict / source quality / citation question |
| exposure_mdd_question | occupational/environmental/antigen/smoking/aspiration question |
| treatment_mdd_question | drug/radiation/ICI/chemotherapy/treatment timeline question |
| cancer_mdd_question | recurrence/progression/treatment injury/PLC/sarcoid-like question |
| infection_mdd_question | TB/fungal/atypical/bacterial/viral/opportunistic infection question |
| CTD_mdd_question | autoimmune features, serology, rheumatology context question |
| pathology_mdd_question | tissue/histology/BAL/microbiology context question |
| report_language_mdd_question | overclaim or uncertainty wording question |

MDD family rule:

> MDD preparation families create review questions, not answers.

---

## 6. Report Overclaim Guard Families

v0.20.9 defines the following report overclaim guard families:

| Guard Family | Meaning |
|---|---|
| diagnosis_overclaim_guard | blocks final diagnosis wording |
| rule_out_overclaim_guard | blocks exclusion/rule-out wording |
| probability_overclaim_guard | blocks numeric probability/confidence wording |
| ranking_overclaim_guard | blocks disease ranking wording |
| treatment_overclaim_guard | blocks treatment/management instruction wording |
| causality_overclaim_guard | blocks drug/radiation/exposure causality wording |
| prognosis_overclaim_guard | blocks prognosis/severity prediction wording |
| reassurance_overclaim_guard | blocks patient reassurance/negative inference wording |
| MDD_consensus_overclaim_guard | blocks final MDD consensus wording |
| validation_overclaim_guard | blocks clinical validation/performance wording |
| report_generation_guard | blocks final impression/report generation |
| patient_facing_guard | blocks patient-facing language |
| source_overclaim_guard | blocks citation/source becoming authority |
| edge_case_generalization_guard | blocks case report becoming general rule |
| uncertainty_erasure_guard | blocks removal of limitation/mimic/missing evidence |

Guard family rule:

> Report guards protect wording from clinical closure and authority drift.

---

## 7. MDD Preparation Object Shape

Future implementation may represent MDD preparation using this shape:

    {
      "mdd_item_id": "string",
      "mdd_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-001"],
      "source_roles": ["terminology_core"],
      "strength_tiers": ["Tier A"],
      "linked_pattern_anchor_ids": ["string"],
      "linked_distribution_ids": ["string"],
      "linked_temporal_ids": ["string"],
      "linked_process_ids": ["string"],
      "linked_persistence_ids": ["string"],
      "linked_missing_evidence_ids": ["string"],
      "linked_evidence_weight_ids": ["string"],
      "question_text": "string",
      "why_it_matters": "string",
      "missing_evidence_named": ["string"],
      "mimics_visible": ["string"],
      "source_status": "string",
      "allowed_claim_level": "MDD_preparation_question",
      "blocked_claim_level": ["MDD_consensus", "diagnosis", "rule_out", "probability", "treatment", "causality"],
      "review_required": true,
      "consensus_generation_allowed": false,
      "diagnosis_closure_allowed": false,
      "treatment_authority_allowed": false,
      "patient_facing_allowed": false,
      "audit_trace_enabled": true,
      "citation_manifest_link": "string"
    }

MDD object rule:

> Every MDD preparation object must expose source trail, reasoning links, question text, missing evidence, mimics, source status, and consensus blockers.

---

## 8. Report Overclaim Guard Object Shape

Future implementation may represent report overclaim guard using this shape:

    {
      "guard_id": "string",
      "guard_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-001"],
      "source_roles": ["terminology_core"],
      "trigger_phrase": "string",
      "overclaim_type": "diagnosis | rule_out | probability | ranking | treatment | causality | prognosis | reassurance | validation | MDD_consensus | report_generation | patient_facing",
      "why_unsafe": "string",
      "safer_language_pattern": "string",
      "required_uncertainty_elements": ["missing_evidence", "mimic_visibility", "source_status", "review_required"],
      "linked_reasoning_surface": "string",
      "allowed_output": "uncertainty_preserving_language",
      "blocked_output": "final_impression",
      "repair_required": true,
      "review_required": true,
      "export_preview_only": true,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "calibrated_probability_allowed": false,
      "treatment_authority_allowed": false,
      "causality_claim_allowed": false,
      "patient_facing_allowed": false,
      "audit_trace_enabled": true,
      "citation_manifest_link": "string"
    }

Overclaim object rule:

> Every report guard object must name the unsafe phrase, why it is unsafe, what uncertainty must remain, and what clinical closure is blocked.

---

## 9. Pattern MDD Question Map

| Trigger | MDD Preparation Question | Required Guard |
|---|---|---|
| fibrotic pattern active | What distribution, temporal behavior, CTD context, exposure history, and prior imaging affect fibrotic reasoning? | no IPF/UIP closure |
| inflammatory pattern active | What infection, edema, treatment, acute-on-chronic, and clinical context should be reviewed? | no treatment/cause decision |
| organizing pattern active | Is the organizing-like pattern primary or secondary to CTD, drug, radiation, infection, or malignancy context? | no OP/COP diagnosis |
| airway-centered pattern active | Is expiratory imaging, antigen/exposure history, smoking, aspiration, or infection context missing? | no HP/infection closure |
| nodular pattern active | Is nodule distribution precise enough and are infection, granulomatous, occupational, and malignancy mimics visible? | no sarcoidosis/metastasis closure |
| cystic pattern active | Is the descriptor precise enough to separate cysts from emphysema or honeycombing-like spaces? | no cystic disease closure |
| granulomatous pattern active | What infectious, exposure-related, lymphoma, sarcoid-like, and immune mimics remain unresolved? | no sarcoidosis closure |
| lymphatic/vascular pattern active | What cancer, edema, sarcoid-like, infection, and treatment-related contexts should be reconciled? | no recurrence/PLC closure |
| treatment-related pattern active | Is the drug/radiation/ICI timeline complete and are infection, edema, and progression mimics visible? | no causality/management |
| exposure-related pattern active | Is occupational/environmental exposure detail sufficient for reasoning but not causality? | no occupational causality |
| mixed pattern active | Which process families remain active and what prevents forced unification? | no ranking/unifying diagnosis |
| indeterminate pattern active | What missing evidence prevents stronger pattern language? | no negative/reassuring conclusion |

Pattern MDD rule:

> Pattern MDD questions transform pattern anchors into review questions, not diagnoses.

---

## 10. Distribution MDD Question Map

| Trigger | MDD Preparation Question | Required Guard |
|---|---|---|
| upper-lung predominance | Does upper-zone distribution modify sarcoidosis, HP, pneumoconiosis, PLCH, or prior infection context? | no automatic diagnosis |
| lower-lung predominance | Does basal/lower-zone distribution modify UIP/IPF-context, CTD-ILD, fibrotic HP, asbestosis, or edema context? | no UIP/IPF closure |
| subpleural distribution | Is this descriptor sufficient and are dependent change, asbestosis, CTD-ILD, and UIP-context visible? | no UIP closure |
| peribronchovascular distribution | Are sarcoidosis, NSIP-context, PLC, edema, and treatment-related mimics visible? | no NSIP/sarcoidosis/PLC closure |
| centrilobular distribution | Are HP, infection, aspiration, smoking, and airway-centered mimics visible? | no HP/infection closure |
| perilymphatic distribution | Are sarcoidosis, PLC, pneumoconiosis, lymphoma/sarcoid-like mimics visible? | no sarcoidosis/PLC closure |
| random nodules | Are miliary infection, fungal infection, and hematogenous metastasis contexts visible? | no metastasis/infection closure |
| field-related distribution | Does field relation require radiation/treatment timeline review? | no RP/RILI/recurrence closure |
| asymmetric distribution | Are malignancy, infection, aspiration, radiation, and asymmetric fibrosis contexts visible? | no malignancy closure |
| distribution not assessable | What spatial evidence is missing before stronger language? | no negative inference |

Distribution MDD rule:

> Distribution MDD questions refine spatial reasoning without closing disease labels.

---

## 11. Temporal MDD Question Map

| Trigger | MDD Preparation Question | Required Guard |
|---|---|---|
| acute course | What infection, edema, hemorrhage, acute exacerbation, or treatment injury context should be reviewed? | no triage/diagnosis |
| subacute course | What OP, HP, DI-ILD, infection, sarcoidosis, or malignancy mimic context remains visible? | no diagnosis |
| chronic course | What fibrotic, occupational, CTD, sarcoidosis, chronic HP, or malignancy context remains visible? | no diagnosis |
| progression | Is progression confirmed by prior imaging and does it modify reasoning without treatment closure? | no PPF/treatment closure |
| stability | Is the interval sufficient and does stability avoid false reassurance? | no reassurance |
| improvement | What resolving infection, edema, treatment response, or fluctuating inflammatory context remains visible? | no exclusion |
| fluctuating behavior | What OP, HP, edema, infection, or treatment-related contexts remain visible? | no diagnosis |
| acute-on-chronic | What superimposed infection, edema, exacerbation, hemorrhage, treatment injury, or malignancy mimic should be reviewed? | no treatment decision |
| treatment-linked timing | Is the medication/radiation/ICI/chemo timeline complete and are alternatives visible? | no causality |
| exposure latency | Is exposure duration/intensity/latency sufficient for questioning but not causality? | no occupational causality |
| cancer follow-up timing | Does recurrence/progression vs treatment injury vs sarcoid-like reaction require review? | no recurrence closure |

Temporal MDD rule:

> Temporal MDD questions refine time-course reasoning without generating prognosis, causality, treatment, or reassurance.

---

## 12. Process-Type MDD Question Map

| Process Family | MDD Preparation Question | Required Guard |
|---|---|---|
| fibrotic_process | Which fibrotic contexts remain active and what evidence is missing for stronger classification? | no IPF/UIP/PPF closure |
| inflammatory_process | Which infection, edema, treatment, acute-on-chronic, or inflammatory mimics remain visible? | no cause/treatment |
| organizing_process | Is organizing morphology primary or secondary to CTD, drug, radiation, infection, or malignancy context? | no OP/COP closure |
| airway_centered_process | Is expiratory imaging and exposure/antigen/aspiration/infection context complete? | no HP/infection closure |
| granulomatous_process | Are infectious, exposure, lymphoma, sarcoid-like, and immune granulomatous alternatives visible? | no sarcoidosis closure |
| nodular_process | Is nodule distribution precise and are infectious/granulomatous/malignancy/exposure contexts visible? | no malignancy/sarcoidosis closure |
| cystic_process | Are cystic descriptor, smoking, nodules, emphysema, and honeycombing-like distinctions reviewed? | no LAM/PLCH/emphysema closure |
| lymphatic_vascular_process | Are PLC, edema, sarcoid-like, infection, recurrence, and treatment-related contexts visible? | no cancer/edema closure |
| treatment_related_process | Is treatment timeline complete and alternatives reviewed before causality language? | no management/causality |
| exposure_related_process | Is exposure history sufficient for reasoning but not causality? | no occupational claim |
| infection_mimic_process | What infection context is missing before infection can be downgraded or contextualized? | no infection exclusion |
| malignancy_mimic_process | What oncology/tissue/PET context is needed before recurrence or benign language? | no recurrence/exclusion |
| edema_cardiac_mimic_process | What cardiac/volume source is missing before edema language is stronger? | no edema diagnosis/exclusion |
| mixed_process | What prevents forced unification and which processes remain active? | no ranking |
| unresolved_process | What specific evidence is missing and which mimics remain unresolved? | no negative conclusion |

Process MDD rule:

> Process MDD questions clarify process uncertainty without converting process labels into disease labels.

---

## 13. Missing Evidence MDD Question Map

| Missing Evidence Family | MDD Preparation Question | Required Guard |
|---|---|---|
| pattern_evidence_missing | What descriptor is missing before a pattern anchor can be strengthened? | no diagnosis |
| distribution_evidence_missing | What spatial descriptor is missing before distribution can modify reasoning safely? | no closure |
| temporal_evidence_missing | What prior imaging, onset, or interval detail is missing? | no progression/prognosis |
| clinical_context_missing | What symptoms, physiology, labs, smoking, immune, or cardiac context is missing? | no clinical decision |
| exposure_context_missing | What occupational/environmental/antigen/smoking/aspiration evidence is missing? | no causality |
| treatment_context_missing | What drug/radiation/ICI/chemo timeline is missing? | no treatment causality |
| cancer_context_missing | What cancer status, PET/CT, tissue, or treatment field data are missing? | no recurrence decision |
| infection_context_missing | What microbiology, TB/fungal, immune, BAL, or endemic context is missing? | no infection exclusion |
| CTD_context_missing | What autoimmune features, serology, or rheumatology context is missing? | no CTD closure |
| pathology_context_missing | Is tissue/histology/BAL/microbiology relevant and missing? | no definitive diagnosis |
| source_metadata_missing | Which source metadata or citation field is incomplete? | no citation-complete claim |
| source_quality_missing | Which source role/status is unclear? | no source authority |
| MDD_context_missing | Which MDD question must be prepared? | no MDD consensus |
| real_data_not_opened | Current phase has no real patient/DICOM/HRCT data. | no clinical implementation claim |
| validation_not_opened | Clinical validation is not opened. | no performance claim |

Missing evidence MDD rule:

> Missing evidence MDD questions turn gaps into review prompts, not test orders or negative evidence.

---

## 14. Source Status MDD Question Map

| Source Status | MDD Preparation Question | Required Guard |
|---|---|---|
| source_not_provided | What source is missing and how does that limit reasoning? | no negative finding |
| source_partial | Which part of the source is incomplete? | no closure |
| source_conflicting | Which sources conflict and what needs reconciliation? | no automatic decision |
| source_stale | Does current context need review before relying on this source? | no current truth claim |
| source_unverified | What review is needed before this source becomes usable? | no clinical fact |
| source_edge_case_only | Is this source only a red-team warning rather than a general rule? | no generalization |
| source_guideline_context_only | What context does the guideline support without granting platform authority? | no autonomous authority |
| source_treatment_context_only | What treatment-related context is relevant without management advice? | no treatment instruction |
| source_terminology_only | Does this source support wording only, not disease logic? | no diagnosis |
| source_role_mismatch | Which role mismatch requires repair before display/export? | hard block |
| citation_manifest_missing | What source trail is missing before reasoning is export-ready? | no audit-ready claim |

Source status MDD rule:

> Source status MDD questions make provenance visible without turning sources into clinical authority.

---

## 15. Mimic / Overlap MDD Question Map

| Mimic / Overlap Trigger | MDD Preparation Question | Required Guard |
|---|---|---|
| fibrotic overlap persists | Which fibrotic contexts remain active and what prevents classification? | no IPF/UIP/PPF closure |
| inflammatory overlap persists | Which infection, edema, treatment, and inflammatory mimics remain visible? | no cause/treatment |
| airway-centered overlap persists | Which HP, infection, aspiration, smoking, CTD airway, or exposure contexts remain visible? | no HP closure |
| granulomatous overlap persists | Which infectious, exposure, lymphoma, sarcoid-like, and immune mimics remain unresolved? | no sarcoidosis closure |
| nodular overlap persists | Which distribution-sensitive infectious, granulomatous, occupational, HP, or malignancy mimics persist? | no ranking |
| cystic overlap persists | What descriptor precision is needed before cystic entity language? | no cystic disease closure |
| lymphatic/vascular overlap persists | Which PLC, edema, sarcoid-like, infection, recurrence, or treatment injury contexts remain visible? | no recurrence/benign closure |
| treatment-related overlap persists | What treatment timing and alternative-cause evidence is missing? | no causality/management |
| exposure-related overlap persists | What exposure history is missing and what non-exposure mimics remain visible? | no causality |
| infection mimic persists | What microbiology/immune/endemic context is needed? | no infection diagnosis/exclusion |
| malignancy mimic persists | What oncology/PET/tissue/treatment context is needed? | no recurrence/benign closure |
| edema/cardiac mimic persists | What cardiac/volume context is missing? | no edema diagnosis/exclusion |
| mixed process persists | Which active paths must remain visible? | no unifying diagnosis |
| unresolved process persists | What evidence prevents stronger language? | no negative conclusion |

Mimic / overlap MDD rule:

> Mimic and overlap questions preserve alternatives without ranking, diagnosing, or excluding them.

---

## 16. Evidence-Weighted MDD Question Map

| Evidence Weight State | MDD Preparation Question | Required Guard |
|---|---|---|
| supports_reasoning | What exactly does this evidence support and at what claim level? | no diagnosis |
| weakens_reasoning | What does this evidence weaken without ruling out? | no rule-out |
| evidence_missing | What missing item blocks stronger language? | no negative evidence |
| evidence_conflicting | Which conflict must be reviewed? | no automatic decision |
| evidence_nonspecific | Which multiple reasoning paths remain compatible? | no dismissal |
| raises_mimic_visibility | Which mimic must remain visible? | no mimic diagnosis |
| raises_overlap_persistence | Which paths remain active? | no ranking |
| limits_confidence | Why is confidence qualitatively limited? | no probability |
| source_quality_modifies_use | What source boundary applies? | no authority |
| overclaim_guard_triggered | Which phrase overclaims and what uncertainty must be preserved? | no final impression |

Evidence-weighted MDD rule:

> Evidence-weighted MDD questions make directional reasoning discussable without becoming answers.

---

## 17. MDD Preparation Package Structure

Future implementation may generate an internal, non-clinical MDD preparation package with these sections:

| Section | Content | Boundary |
|---|---|---|
| case_scope_notice | synthetic/internal/current-phase boundary | not patient-facing |
| source_status_summary | source IDs, roles, tiers, conflicts, missing metadata | not validation |
| active_pattern_anchors | pattern reasoning surfaces | not diagnosis |
| distribution_temporal_summary | where/when reasoning | not diagnosis/prognosis |
| process_type_summary | active process families | not disease labels |
| mimic_overlap_summary | unresolved mimics and overlaps | not ranking |
| missing_evidence_summary | evidence gaps and why they matter | not test orders |
| evidence_weight_summary | qualitative support/weakening/conflict/nonspecificity | not probability |
| confidence_limiter_summary | qualitative limitations | not numeric score |
| MDD_questions | review questions | not MDD answers |
| report_overclaim_warnings | unsafe wording and safer patterns | not report impression |
| audit_trace_summary | traceability events | not clinical correctness proof |

MDD package rule:

> The package prepares discussion; it must not generate clinical conclusions.

---

## 18. Report Overclaim Trigger Phrase Map

| Unsafe Trigger Phrase | Overclaim Type | Required Guard |
|---|---|---|
| diagnosis is | diagnosis_overclaim_guard |
| consistent with [disease] as final statement | diagnosis_overclaim_guard |
| diagnostic of | diagnosis_overclaim_guard |
| confirms | diagnosis_overclaim_guard |
| definitive | diagnosis_overclaim_guard |
| pathognomonic | diagnosis_overclaim_guard unless separately governed |
| rules out | rule_out_overclaim_guard |
| excludes | rule_out_overclaim_guard |
| no evidence of [disease] | rule_out_overclaim_guard when source incomplete |
| probability is | probability_overclaim_guard |
| likelihood is X percent | probability_overclaim_guard |
| confidence score | probability_overclaim_guard |
| most likely diagnosis | ranking_overclaim_guard |
| ranked first | ranking_overclaim_guard |
| treat with | treatment_overclaim_guard |
| start medication | treatment_overclaim_guard |
| stop medication | treatment_overclaim_guard |
| order test | treatment_overclaim_guard / test_order_guard |
| follow-up in | treatment_overclaim_guard / follow_up_guard |
| caused by drug | causality_overclaim_guard |
| caused by radiation | causality_overclaim_guard |
| caused by exposure | causality_overclaim_guard |
| prognosis is | prognosis_overclaim_guard |
| stable therefore reassuring | reassurance_overclaim_guard |
| benign | reassurance_overclaim_guard / malignancy overclaim |
| MDD consensus is | MDD_consensus_overclaim_guard |
| final impression | report_generation_guard |
| clinically validated | validation_overclaim_guard |
| product ready | validation_overclaim_guard |
| patient should | patient_facing_guard |

Trigger phrase rule:

> Closure phrases must be blocked or repaired before UI, export preview, or MDD preparation package display.

---

## 19. Uncertainty-Preserving Language Patterns

The following safer language patterns may be used only as non-final, clinician-facing reasoning support.

| Unsafe Meaning | Safer Pattern |
|---|---|
| diagnosis is X | evidence supports reasoning toward X-context, with stated limitations |
| confirms X | supports X-related reasoning but does not close diagnosis |
| rules out Y | weakens support for Y, but Y remains unresolved if closure evidence is incomplete |
| probability is X percent | evidence appears qualitatively stronger/weaker; no calibrated probability is available |
| most likely diagnosis | one reasoning path is more supported by available evidence, but no ranking/final diagnosis is generated |
| treatment should start | management remains outside platform authority; clinician/MDD review required |
| caused by drug/radiation/exposure | temporal/exposure/treatment context is relevant, but causality is not established |
| cancer recurrence excluded | recurrence and non-recurrence mimics remain visible until reviewed |
| stable therefore benign | stability modifies reasoning but does not reassure or exclude disease |
| MDD consensus is X | this issue may be relevant for MDD preparation |
| final impression | internal reasoning preview only; not a clinical report |
| clinically validated | citation exists for reasoning provenance; clinical validation is not opened |

Safer language rule:

> Safer wording must preserve uncertainty, source status, missing evidence, mimic visibility, and review requirement.

---

## 20. Report Overclaim Guard by Reasoning Surface

| Reasoning Surface | Common Overclaim | Guard |
|---|---|---|
| pattern anchor | pattern becomes disease | pattern not diagnosis |
| distribution | distribution becomes diagnosis | distribution not closure |
| temporal behavior | progression/stability becomes prognosis or treatment | temporal not prognosis/treatment |
| process type | process becomes disease label | process not diagnosis |
| mimic visibility | mimic becomes diagnosis | visibility not diagnosis |
| mimic unresolved | mimic becomes excluded | unresolved not exclusion |
| overlap persistence | overlap becomes ranking | overlap not ranking |
| missing evidence | missing becomes negative evidence | missing not negative |
| source status | source becomes authority | source not authority |
| evidence weight | support becomes diagnosis | support not diagnosis |
| confidence limiter | limitation becomes probability | limitation not probability |
| MDD preparation | question becomes consensus | preparation not consensus |
| report guard | safer language becomes final report | guard not generation |
| citation trail | citation becomes validation | citation not validation |
| audit trace | audit becomes clinical correctness proof | audit not correctness proof |

Surface guard rule:

> Each reasoning surface must carry its own overclaim guard.

---

## 21. MDD Question Generation Rules

A future MDD question may be generated only if:

| Requirement | Required |
|---|---|
| linked reasoning surface exists | true |
| source IDs visible | true |
| source roles visible | true |
| missing evidence or mimic/overlap/evidence weight trigger exists | true |
| question is phrased as review prompt | true |
| no final diagnosis wording | true |
| no rule-out wording | true |
| no probability wording | true |
| no treatment instruction | true |
| no causality claim | true |
| no patient-facing language | true |
| MDD consensus generation blocked | true |

MDD question rule:

> MDD questions are allowed only when they remain questions, not answers.

---

## 22. Report Guard Repair Rules

A future report guard may repair unsafe wording only if:

| Requirement | Required |
|---|---|
| unsafe trigger phrase identified | true |
| overclaim type identified | true |
| required uncertainty element identified | true |
| missing evidence preserved when relevant | true |
| mimic visibility preserved when relevant | true |
| source status preserved when relevant | true |
| review requirement preserved when relevant | true |
| safer phrase remains non-final | true |
| no clinical report generated | true |
| no final impression generated | true |
| no patient-facing output generated | true |

Repair rule:

> Repair creates safer internal wording, not a clinical report.

---

## 23. MDD Preparation Hard Blocks

MDD preparation must hard block if any are attempted:

| Attempt | Required Behavior |
|---|---|
| generate final MDD diagnosis | hard block |
| generate MDD consensus | hard block |
| generate MDD treatment plan | hard block |
| generate MDD follow-up plan | hard block |
| generate MDD triage decision | hard block |
| rank diseases for MDD | hard block |
| convert evidence weight to probability | hard block |
| remove unresolved mimic | hard block |
| hide source conflict | hard block |
| hide missing evidence | hard block |
| use edge-case source as general rule | hard block |
| use treatment source for management | hard block |
| use exposure source for causality | hard block |
| create patient-facing MDD output | hard block |

MDD hard block rule:

> MDD preparation is a question package, not a decision package.

---

## 24. Report Overclaim Hard Blocks

Report overclaim guard must hard block if any are attempted:

| Attempt | Required Behavior |
|---|---|
| generate final impression | hard block |
| generate clinical report | hard block |
| generate diagnosis | hard block |
| generate rule-out | hard block |
| generate probability | hard block |
| generate disease ranking | hard block |
| generate treatment recommendation | hard block |
| generate causality claim | hard block |
| generate prognosis | hard block |
| generate reassurance | hard block |
| generate patient-facing summary | hard block |
| claim clinical validation | hard block |
| claim product readiness | hard block |
| cite source as validation proof | hard block |
| present synthetic data as real case | hard block |

Report hard block rule:

> Report guard prevents unsafe report-like output; it must not become report generation.

---

## 25. MDD Preparation Display Policy

A future internal UI may display MDD preparation content only as:

| Display Element | Allowed Content | Blocked Content |
|---|---|---|
| MDD question card | source-linked review question | MDD answer |
| missing evidence card | evidence gap and why it matters | test order |
| mimic card | unresolved mimic visibility | mimic diagnosis/exclusion |
| overlap card | active overlap paths | ranking |
| source card | source ID/role/status | clinical authority |
| confidence limiter card | qualitative limitation | probability |
| report warning card | overclaim trigger and safer pattern | final impression |
| audit card | traceability event | correctness proof |
| export preview card | internal non-clinical package preview | clinical report |

Display rule:

> MDD preparation display must help experts see what to discuss, not decide for them.

---

## 26. Report Guard Display Policy

A future internal UI may display report guard content only as:

| Display Element | Allowed Content | Blocked Content |
|---|---|---|
| unsafe phrase badge | phrase marked as overclaim | diagnosis |
| overclaim type badge | diagnosis/rule-out/probability/etc. category | clinical conclusion |
| safer wording suggestion | uncertainty-preserving pattern | final report sentence |
| missing evidence reminder | named gap | test order |
| mimic reminder | unresolved mimic | mimic diagnosis |
| source reminder | source role and limitation | authority |
| review-required badge | review needed | clinical instruction |
| export-only notice | internal preview only | report generation |

Display rule:

> Report guard display must preserve uncertainty and review requirement.

---

## 27. Source/Citation Policy for MDD and Report Guard

Every MDD preparation or report guard item must expose:

| Field | Required |
|---|---|
| source_ids | true |
| source_roles | true |
| strength_tiers | true |
| bibliography_reference | true |
| citation_manifest_link | true |
| allowed_source_use | true |
| forbidden_source_use | true |
| source_status | true |
| source_drift_flag | true |
| metadata_status | true |
| audit_trace_enabled | true |

Citation policy rule:

> A source trail explains why the question or guard exists; it does not authorize a clinical conclusion.

---

## 28. MDD Preparation / Report Guard Integration Matrix

| Input Surface | MDD Preparation Output | Report Guard Output |
|---|---|---|
| pattern anchor | pattern review question | pattern-not-diagnosis guard |
| distribution reasoning | spatial review question | distribution-not-closure guard |
| temporal reasoning | timeline/prior-imaging question | temporal-not-prognosis guard |
| process type | process review question | process-not-disease guard |
| mimic persistence | unresolved mimic question | mimic-not-diagnosis/exclusion guard |
| overlap persistence | overlap review question | overlap-not-ranking guard |
| missing evidence | gap review question | missing-not-negative guard |
| source status | source reconciliation question | source-not-authority guard |
| evidence weight | directional reasoning question | evidence-not-probability guard |
| confidence limiter | limitation review question | limitation-not-score guard |
| edge-case source | red-team caution question | edge-case-not-general-rule guard |
| treatment source | treatment-context question | context-not-management guard |
| exposure source | exposure-history question | context-not-causality guard |
| oncology source | recurrence/treatment-mimic question | cancer-status-not-decided guard |

Integration rule:

> Every reasoning input must produce either a safe MDD question, a safe overclaim guard, or both.

---

## 29. Example Non-Autonomous MDD Questions

Allowed examples:

- “Which missing evidence prevents stronger fibrotic-pattern language?”
- “Does the distribution support more than one reasoning path?”
- “Is prior imaging available to assess progression, stability, or acute-on-chronic change?”
- “Which infectious mimics remain unresolved?”
- “Is drug, radiation, or ICI timing complete enough for treatment-related context review?”
- “Is exposure history sufficient to discuss occupational/environmental context without causality?”
- “What source conflict should be reconciled before stronger language?”
- “Which phrase would overclaim in a report-like export?”
- “Which mimic should remain visible in the MDD discussion?”
- “Why should confidence remain limited?”

Blocked examples:

- “What is the final MDD diagnosis?”
- “Which disease is most likely?”
- “Which diagnosis can be ruled out?”
- “What treatment should be recommended?”
- “What is the probability?”
- “What should the report impression say?”
- “What should the patient be told?”

MDD example rule:

> The question format must remain review-oriented and non-autonomous.

---

## 30. Example Report Guard Repairs

Allowed internal safer patterns:

| Unsafe Phrase | Safer Internal Pattern |
|---|---|
| “Findings confirm UIP.” | “Findings support fibrotic/UIP-pattern reasoning, but diagnosis is not closed.” |
| “HP is ruled out.” | “Current evidence weakens HP-context support, but HP remains unresolved if exposure/airway evidence is incomplete.” |
| “This is sarcoidosis.” | “Granulomatous/sarcoidosis-context reasoning is active; infectious, exposure-related, lymphoma, and sarcoid-like mimics remain visible.” |
| “This is drug-induced ILD.” | “Treatment-related context is relevant; causality is not established and alternatives remain visible.” |
| “No malignancy.” | “Malignancy mimic visibility is reduced or unsupported only within available evidence; recurrence/progression is not autonomously excluded.” |
| “Stable, benign.” | “Stability modifies reasoning but does not create reassurance or disease exclusion.” |
| “MDD consensus: IPF.” | “MDD preparation item: fibrotic reasoning, missing evidence, and mimics to review.” |
| “Final impression generated.” | “Internal non-clinical export preview; not a clinical report or final impression.” |

Repair example rule:

> Safer patterns must preserve the limitation that makes the original phrase unsafe.

---

## 31. Export Preview Boundary

v0.20.9 allows only internal non-clinical export preview structure.

Allowed export preview content:

- source status summary,
- active reasoning surfaces,
- missing evidence list,
- mimic persistence list,
- overlap persistence list,
- non-calibrated evidence-weight summary,
- qualitative confidence limitations,
- MDD preparation questions,
- report overclaim warnings,
- audit trace summary,
- no-decision statement.

Blocked export preview content:

- final diagnosis,
- rule-out,
- calibrated probability,
- disease ranking,
- treatment plan,
- causality conclusion,
- prognosis,
- reassurance,
- clinical report impression,
- patient-facing summary,
- MDD consensus,
- clinical validation claim,
- product readiness claim.

Export preview rule:

> Export preview packages reasoning for review; it must not become a clinical report.

---

## 32. No-Decision Object Preservation

The no-decision object remains preserved:

| Field | Required State |
|---|---|
| final_diagnosis_made | false |
| disease_excluded_autonomously | false |
| mimic_excluded_autonomously | false |
| disease_ranked | false |
| calibrated_probability_generated | false |
| numeric_confidence_generated | false |
| treatment_selected | false |
| test_ordered | false |
| procedure_decided | false |
| follow_up_scheduled | false |
| triage_assigned | false |
| causality_claim_generated | false |
| prognosis_generated | false |
| reassurance_generated | false |
| mdd_consensus_generated | false |
| clinical_report_generated | false |
| final_impression_generated | false |
| patient_facing_output_generated | false |

No-decision rule:

> MDD preparation and report guard may organize review, but they must not close decisions.

---

## 33. Audit Requirements

Every MDD preparation or report overclaim guard event must be audit-visible as scaffold traceability.

Allowed audit events:

- MDD question generated,
- source-linked MDD item created,
- missing evidence linked to MDD item,
- mimic persistence linked to MDD item,
- overlap persistence linked to MDD item,
- evidence weight linked to MDD item,
- report overclaim trigger detected,
- unsafe phrase blocked,
- safer wording pattern generated,
- source role checked,
- source drift blocked,
- export preview boundary displayed,
- review-required badge displayed,
- no-decision object preserved.

Blocked audit meanings:

- clinical correctness proof,
- diagnostic validation,
- treatment correctness,
- MDD correctness,
- patient care audit,
- PACS/EHR audit,
- regulatory evidence,
- product readiness proof,
- probability calibration proof.

Audit rule:

> Audit records review-preparation governance, not clinical correctness.

---

## 34. Future Implementation Requirements

When implemented later, every MDD preparation and report overclaim object must expose:

| Field | Required |
|---|---|
| object_id | true |
| object_family | true |
| source_ids | true |
| source_roles | true |
| strength_tiers | true |
| citation_manifest_link | true |
| linked_pattern_anchor_ids | true |
| linked_distribution_ids | true |
| linked_temporal_ids | true |
| linked_process_ids | true |
| linked_persistence_ids | true |
| linked_missing_evidence_ids | true |
| linked_evidence_weight_ids | true |
| question_or_guard_text | true |
| why_it_matters | true |
| missing_evidence_named | true |
| mimic_visibility_named | true |
| source_status_named | true |
| confidence_limiter_named | true |
| review_required | true |
| export_preview_only | true |
| audit_trace_enabled | true |
| diagnosis_closure_allowed | false |
| rule_out_allowed | false |
| mimic_exclusion_allowed | false |
| calibrated_probability_allowed | false |
| numeric_confidence_allowed | false |
| ranking_allowed | false |
| treatment_authority_allowed | false |
| causality_claim_allowed | false |
| prognosis_allowed | false |
| reassurance_allowed | false |
| mdd_consensus_allowed | false |
| report_generation_allowed | false |
| final_impression_allowed | false |
| patient_facing_allowed | false |

Implementation rule:

> MDD preparation and report guard objects must be source-linked, auditable, uncertainty-preserving, review-required, export-preview-only, and closure-blocked before they are used in any UI or export surface.

---

## 35. Current-Phase Authority Envelope

The current-phase authority envelope remains:

| Capability | State |
|---|---|
| autonomous final diagnosis | blocked |
| autonomous disease exclusion / rule-out | blocked |
| autonomous mimic exclusion | blocked |
| calibrated diagnostic probability | not_opened |
| numeric confidence score | not_opened |
| disease ranking | not_opened |
| treatment authority | none |
| test-order authority | none |
| procedure authority | none |
| follow-up authority | none |
| triage authority | none |
| causality authority | none |
| prognosis authority | none |
| reassurance authority | none |
| MDD consensus generation | blocked |
| clinical report generation | blocked |
| final impression generation | blocked |
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

> MDD preparation and report overclaim guard improve review readiness and language safety; they do not change current clinical authority.

---

## 36. Prototype File Count Preservation

v0.20.9 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.9 is docs-only MDD preparation and report overclaim guard governance; the materialized prototype skeleton remains unchanged.

---

## 37. Acceptance Criteria

v0.20.9 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.8 dependency listed | true |
| v0.20.7 dependency listed | true |
| v0.20.6 dependency listed | true |
| v0.20.5 dependency listed | true |
| v0.20.4 dependency listed | true |
| v0.20.3 dependency listed | true |
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| core concepts defined | true |
| MDD preparation families defined | true |
| report overclaim guard families defined | true |
| MDD preparation object shape defined | true |
| report overclaim guard object shape defined | true |
| pattern MDD question map defined | true |
| distribution MDD question map defined | true |
| temporal MDD question map defined | true |
| process-type MDD question map defined | true |
| missing evidence MDD question map defined | true |
| source status MDD question map defined | true |
| mimic / overlap MDD question map defined | true |
| evidence-weighted MDD question map defined | true |
| MDD preparation package structure defined | true |
| report overclaim trigger phrase map defined | true |
| uncertainty-preserving language patterns defined | true |
| report overclaim guard by reasoning surface defined | true |
| MDD question generation rules defined | true |
| report guard repair rules defined | true |
| MDD hard blocks defined | true |
| report overclaim hard blocks defined | true |
| MDD preparation display policy defined | true |
| report guard display policy defined | true |
| source/citation policy defined | true |
| integration matrix defined | true |
| example non-autonomous MDD questions defined | true |
| example report guard repairs defined | true |
| export preview boundary defined | true |
| no-decision object preserved | true |
| audit requirements defined | true |
| future implementation requirements defined | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no autonomous mimic exclusion opened | true |
| no calibrated probability opened | true |
| no numeric confidence score opened | true |
| no ranking opened | true |
| no treatment authority opened | true |
| no causality authority opened | true |
| no prognosis authority opened | true |
| no reassurance authority opened | true |
| no MDD consensus opened | true |
| no clinical report generation opened | true |
| no final impression opened | true |
| no patient-facing output opened | true |
| no real patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |
| prototype file count remains 191 | true |

Acceptance rule:

> v0.20.9 is valid only if MDD preparation and report overclaim guard become clinically meaningful while consensus, report generation, diagnosis, exclusion, probability, ranking, causality, treatment, prognosis, reassurance, validation, and patient-facing closure remain blocked.

---

## 38. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> MDD preparation / report overclaim guard mapping verifies reasoning governance only; it does not certify clinical performance.

---

## 39. Next Step

The next recommended step is:

    v0.20.10 — ILD Clinical Reasoning Content Structural Seal

v0.20.10 should structurally seal:

- v0.20.0 Clinical Reasoning Content Re-Entry Entry Gate,
- v0.20.1 Source Corpus / Reference Backbone Intake,
- v0.20.2 ILD Reasoning Vocabulary Foundation,
- v0.20.2a Reference Bibliography / Citation Manifest,
- v0.20.3 HRCT Pattern Reasoning Anchor Map,
- v0.20.4 Distribution / Temporal Reasoning Map,
- v0.20.5 Process-Type Reasoning Map,
- v0.20.6 Mimic / Overlap Persistence Matrix,
- v0.20.7 Missing Evidence / Source Status Logic,
- v0.20.8 Non-Calibrated Evidence-Weighted Reasoning Surface,
- v0.20.9 MDD Preparation / Report Overclaim Guard Map.

v0.20.10 must preserve:

- clinical reasoning content opened,
- autonomous clinical authority closed,
- source backbone preserved,
- citation manifest preserved,
- pattern / distribution / temporal / process / mimic / missing evidence / evidence-weight / MDD/report guard layers sealed,
- no real patient data,
- no DICOM/HRCT/report/PACS/EHR,
- no clinical validation,
- no patient-facing output,
- no product readiness,
- no MDD replacement.

Next-step rule:

> v0.20.10 should seal the clinical reasoning content layer before any working vertical slice is built.

---

## 40. Governance Statement

This document records v0.20.9 MDD Preparation / Report Overclaim Guard Map.

It does not implement a clinical product.

It does not diagnose autonomously.  
It does not rule out disease autonomously.  
It does not exclude mimics autonomously.  
It does not rank diseases.  
It does not calculate probability.  
It does not create numeric diagnostic confidence.  
It does not treat.  
It does not infer clinical causality.  
It does not provide prognosis.  
It does not reassure.  
It does not generate MDD consensus.  
It does not generate a clinical report.  
It does not generate a final impression.  
It does not generate patient-facing output.  
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

The v0.20.9 discipline is:

> “Create MDD preparation and report overclaim guard without creating consensus, report generation, diagnosis, exclusion, probability, ranking, causality, treatment, prognosis, reassurance, validation, or patient-facing closure.”

The final v0.20.9 boundary is:

> “The platform can now prepare better MDD questions and safer report language; it still cannot decide what disease it is.”
