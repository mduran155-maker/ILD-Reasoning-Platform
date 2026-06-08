# ILD Reasoning Platform — Non-Calibrated Evidence-Weighted Reasoning Surface v1

Version: v0.20.8  
Status: non_calibrated_evidence_weighted_reasoning_surface  
Scope: Source-governed non-calibrated evidence-weighted reasoning after v0.20.7  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.8:

- Non-Calibrated Evidence-Weighted Reasoning Surface.

v0.20.8 follows:

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

v0.20.8 now defines how evidence may directionally affect reasoning without becoming:

- probability,
- diagnosis,
- rule-out,
- ranking,
- treatment,
- causality,
- prognosis,
- reassurance,
- clinical validation,
- MDD consensus.

This is a central platform layer.

The platform must be able to say:

- evidence supports a reasoning path,
- evidence weakens a reasoning path,
- evidence is missing,
- evidence is conflicting,
- evidence is nonspecific,
- evidence requires review,
- evidence increases mimic visibility,
- evidence increases overlap persistence,
- evidence limits confidence,
- evidence supports MDD preparation.

But the platform must not say:

- probability is X percent,
- diagnosis is confirmed,
- disease is ruled out,
- mimic is excluded,
- disease A is ranked above disease B,
- treatment should be started,
- causality is established,
- prognosis is determined,
- patient should be reassured,
- clinical validation is proven,
- MDD consensus is generated.

This document does not diagnose.

It does not assign a disease label.

It does not rank diseases.

It does not calculate probability.

It does not rule out disease.

It does not exclude mimics.

It does not recommend treatment.

It does not infer causality.

It does not provide prognosis.

It does not reassure.

It does not generate a report impression.

It does not generate patient-facing output.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.8 principle is:

> “Evidence can move reasoning, but it cannot close the clinical answer.”

The permanent boundary is:

> “Evidence weight is directionality, not probability.”

---

## 2. Required Previous State

v0.20.8 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
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
| working tree before v0.20.8 is clean | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no autonomous mimic exclusion opened | true |
| no calibrated probability opened | true |
| no ranking opened | true |
| no treatment authority opened | true |
| no causality authority opened | true |
| no patient-facing output opened | true |
| no real patient data opened | true |
| no deidentified patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |

Dependency rule:

> v0.20.8 may define non-calibrated evidence weighting only under source-governed vocabulary, citation manifest, pattern anchors, distribution/temporal reasoning, process-type reasoning, mimic persistence, missing evidence/source status logic, and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.8 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.8 |
|---|---|---|
| terminology_core | SRC-001 | evidence wording precision and descriptor-vs-diagnosis boundary |
| classification_core | SRC-002 | shared ILD patterns, broad ILD families, and multi-context interpretation |
| consensus_core | SRC-003 | qualitative progression relevance without probability or treatment closure |
| guideline_core | SRC-004, SRC-005, SRC-006 | uncertainty, alternative-cause visibility, review requirement, evidence-quality awareness |
| review_support | SRC-007, SRC-010 | nonspecific DI-ILD/RILI evidence and alternative-cause review |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | infectious, granulomatous, sarcoid-like, lymphoma, malignancy, and PLC mimic weighting |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | treatment-context relevance without causality or management |
| occupational_exposure_support | SRC-012 | exposure relevance without occupational/environmental causality |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | red-team trap weighting only, not general rule |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | non-autonomous authority envelope and evidence-weight boundary |

Source rule:

> Evidence weighting must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. Core Evidence-Weight Concepts

v0.20.8 defines the following core concepts.

| Concept | Meaning | Blocked Misuse |
|---|---|---|
| evidence_supports | evidence increases directional support for a reasoning path | diagnosis |
| evidence_weakens | evidence decreases directional support for a reasoning path | rule-out |
| evidence_missing | required evidence is absent | negative evidence |
| evidence_conflicting | sources or findings conflict | automatic decision |
| evidence_nonspecific | evidence fits more than one path | useless evidence |
| evidence_requires_review | evidence needs human review | MDD consensus |
| evidence_raises_mimic_visibility | evidence makes a mimic harder to ignore | mimic diagnosis |
| evidence_raises_overlap_persistence | evidence keeps multiple paths active | ranking |
| evidence_limits_confidence | evidence state blocks stronger language | probability |
| evidence_supports_mdd_preparation | evidence should be discussed or clarified | MDD decision |

Core rule:

> Evidence weight changes reasoning posture; it must not create clinical closure.

---

## 5. Evidence Weight Families

v0.20.8 defines the following evidence weight families:

| Evidence Weight Family | Meaning |
|---|---|
| supportive_evidence_weight | evidence directionally supports a reasoning path |
| weakening_evidence_weight | evidence directionally weakens a reasoning path |
| missing_evidence_weight | absent evidence limits stronger language |
| conflicting_evidence_weight | conflicting evidence blocks closure |
| nonspecific_evidence_weight | evidence fits multiple reasoning paths |
| mimic_visibility_weight | evidence keeps mimic visible |
| overlap_persistence_weight | evidence keeps more than one path active |
| confidence_limiter_weight | evidence state explains why confidence remains limited |
| source_quality_weight | source role/status modifies how evidence may be used |
| temporal_weight | time-course modifies reasoning direction |
| distribution_weight | spatial distribution modifies reasoning direction |
| process_weight | process-type label modifies reasoning direction |
| mdd_preparation_weight | evidence supports MDD preparation questions |
| overclaim_guard_weight | evidence triggers wording caution |
| hard_block_weight | evidence/source state blocks stronger language |

Evidence family rule:

> Evidence weight families must remain qualitative and non-calibrated.

---

## 6. Non-Calibrated Weight Object Shape

Future implementation may represent non-calibrated evidence weighting using this shape:

    {
      "weight_id": "string",
      "weight_family": "string",
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
      "evidence_statement": "string",
      "directional_effect": "supports | weakens | missing | conflicting | nonspecific | limits_confidence | raises_mimic_visibility | raises_overlap_persistence | requires_review",
      "allowed_claim_level": "descriptor | reasoning_direction | review_prompt | mdd_preparation",
      "blocked_claim_level": ["diagnosis", "rule_out", "probability", "ranking", "treatment", "causality", "validation", "patient_facing_output"],
      "confidence_limiter": "string",
      "review_required": true,
      "mdd_preparation_relevant": true,
      "citation_manifest_link": "string",
      "audit_trace_enabled": true,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "mimic_exclusion_allowed": false,
      "calibrated_probability_allowed": false,
      "ranking_allowed": false,
      "treatment_authority_allowed": false,
      "causality_claim_allowed": false,
      "patient_facing_allowed": false
    }

Object rule:

> Every evidence weight object must expose source trail, directional effect, allowed claim level, blocked claim level, confidence limiter, review requirement, and authority blockers.

---

## 7. Supportive Evidence Weight

| Field | Definition |
|---|---|
| weight_id | weight_supportive_evidence_v1 |
| weight_family | supportive_evidence_weight |
| directional_effect | supports |
| allowed_claim_level | descriptor / reasoning_direction / review_prompt |
| blocked_claim_level | diagnosis; probability; ranking; treatment; causality |
| reasoning_use | mark evidence that directionally supports a reasoning path without closing it |

Allowed language:

- “This evidence supports reasoning toward this process.”
- “This feature supports this pattern anchor.”
- “This temporal behavior supports review of this reasoning path.”
- “This source supports descriptor-level language.”

Blocked language:

- “This confirms the diagnosis.”
- “This is the most likely diagnosis.”
- “This proves the disease.”
- “This is X percent likely.”
- “Treatment should be started.”

Supportive evidence rule:

> Support means directional relevance, not diagnosis, probability, ranking, treatment, or causality.

---

## 8. Weakening Evidence Weight

| Field | Definition |
|---|---|
| weight_id | weight_weakening_evidence_v1 |
| weight_family | weakening_evidence_weight |
| directional_effect | weakens |
| allowed_claim_level | reasoning_direction / confidence_limiter / review_prompt |
| blocked_claim_level | rule_out; mimic_exclusion; probability; ranking |
| reasoning_use | mark evidence that directionally weakens a reasoning path without excluding it |

Allowed language:

- “This evidence weakens reasoning toward this path.”
- “This source makes this path less supported.”
- “This finding reduces support but does not close the mimic.”
- “This pathway remains visible because exclusion is not allowed.”

Blocked language:

- “This rules out the disease.”
- “This excludes the mimic.”
- “This diagnosis is unlikely as a final claim.”
- “This path has low probability.”
- “This can be removed from the differential.”

Weakening evidence rule:

> Weakening means less support, not rule-out, mimic exclusion, ranking, or probability.

---

## 9. Missing Evidence Weight

| Field | Definition |
|---|---|
| weight_id | weight_missing_evidence_v1 |
| weight_family | missing_evidence_weight |
| directional_effect | missing |
| allowed_claim_level | confidence_limiter / missing_evidence_prompt / review_prompt |
| blocked_claim_level | negative_evidence; rule_out; reassurance |
| reasoning_use | mark absent evidence that blocks stronger language |

Allowed language:

- “Evidence is missing.”
- “Missing evidence limits stronger language.”
- “This missing item keeps mimics visible.”
- “This gap should be reviewed.”

Blocked language:

- “Because this is missing, the disease is absent.”
- “No source means negative.”
- “This rules out the mimic.”
- “Nothing concerning is present.”
- “Reassurance is appropriate.”

Missing evidence rule:

> Missing evidence limits reasoning; it is not negative evidence.

---

## 10. Conflicting Evidence Weight

| Field | Definition |
|---|---|
| weight_id | weight_conflicting_evidence_v1 |
| weight_family | conflicting_evidence_weight |
| directional_effect | conflicting |
| allowed_claim_level | source_conflict / confidence_limiter / review_prompt |
| blocked_claim_level | automatic_decision; ranking; diagnosis; rule_out |
| reasoning_use | show source or finding conflict that blocks closure |

Allowed language:

- “Evidence is conflicting.”
- “Source conflict blocks stronger language.”
- “This conflict should be reviewed.”
- “MDD preparation may be relevant.”

Blocked language:

- “The system resolves the conflict automatically.”
- “One source wins.”
- “This confirms the diagnosis.”
- “This rules out the alternative.”
- “This path is ranked higher.”

Conflicting evidence rule:

> Conflict triggers visibility and review, not automatic decision.

---

## 11. Nonspecific Evidence Weight

| Field | Definition |
|---|---|
| weight_id | weight_nonspecific_evidence_v1 |
| weight_family | nonspecific_evidence_weight |
| directional_effect | nonspecific |
| allowed_claim_level | overlap_persistence / mimic_visibility / confidence_limiter |
| blocked_claim_level | dismissal; closure; ranking |
| reasoning_use | mark evidence that fits multiple contexts |

Allowed language:

- “This evidence is nonspecific.”
- “This feature is compatible with more than one reasoning path.”
- “Overlap persists.”
- “Mimics remain visible.”

Blocked language:

- “This evidence is useless.”
- “This confirms one path.”
- “This removes the alternative.”
- “This ranks the disease.”

Nonspecific evidence rule:

> Nonspecific evidence is useful for preserving overlap; it must not be discarded or overclaimed.

---

## 12. Mimic Visibility Weight

| Field | Definition |
|---|---|
| weight_id | weight_mimic_visibility_v1 |
| weight_family | mimic_visibility_weight |
| directional_effect | raises_mimic_visibility |
| allowed_claim_level | mimic_visible / mimic_unresolved / review_prompt |
| blocked_claim_level | mimic_diagnosis; mimic_exclusion |
| reasoning_use | mark evidence that requires a mimic to remain visible |

Allowed language:

- “This evidence raises mimic visibility.”
- “This mimic remains unresolved.”
- “This alternative should remain visible.”
- “This source supports mimic visibility, not diagnosis.”

Blocked language:

- “This is the mimic diagnosis.”
- “This excludes the mimic.”
- “This mimic can be removed.”
- “This alternative is no longer relevant.”

Mimic visibility rule:

> Evidence may keep a mimic visible; it must not diagnose or exclude the mimic.

---

## 13. Overlap Persistence Weight

| Field | Definition |
|---|---|
| weight_id | weight_overlap_persistence_v1 |
| weight_family | overlap_persistence_weight |
| directional_effect | raises_overlap_persistence |
| allowed_claim_level | overlap_visible / mixed_process / confidence_limiter |
| blocked_claim_level | ranking; final_unifying_diagnosis |
| reasoning_use | mark evidence that keeps multiple reasoning paths active |

Allowed language:

- “Overlap persists.”
- “Multiple reasoning paths remain active.”
- “A forced unifying diagnosis is not supported.”
- “Review is required before stronger language.”

Blocked language:

- “This path is ranked first.”
- “The unifying diagnosis is...”
- “Other paths are removed.”
- “This resolves the overlap.”

Overlap persistence rule:

> Overlap means multiple paths remain active, not ranking or unification.

---

## 14. Confidence Limiter Weight

| Field | Definition |
|---|---|
| weight_id | weight_confidence_limiter_v1 |
| weight_family | confidence_limiter_weight |
| directional_effect | limits_confidence |
| allowed_claim_level | qualitative_confidence_limitation |
| blocked_claim_level | numeric_probability; diagnostic_confidence_score |
| reasoning_use | explain why stronger language is unsafe |

Allowed language:

- “Confidence remains limited because...”
- “Source status limits confidence.”
- “Missing evidence limits confidence.”
- “Overlap limits confidence.”
- “Mimic persistence limits confidence.”

Blocked language:

- “Confidence is 80%.”
- “Probability is low.”
- “This score confirms diagnosis.”
- “This confidence level rules out disease.”

Confidence limiter rule:

> Confidence limitation is qualitative; it must not become calibrated probability or score.

---

## 15. Source Quality Weight

| Field | Definition |
|---|---|
| weight_id | weight_source_quality_v1 |
| weight_family | source_quality_weight |
| directional_effect | source_quality_modifies_use |
| allowed_claim_level | source_status / citation_manifest / review_prompt |
| blocked_claim_level | clinical_authority; validation |
| reasoning_use | adjust safe use based on source role, tier, and status |

Allowed language:

- “This source supports terminology, not diagnosis.”
- “This source supports context, not management.”
- “This source is an edge-case warning, not a general rule.”
- “This citation supports traceability, not clinical validation.”

Blocked language:

- “This guideline makes the platform authoritative.”
- “This citation validates clinical performance.”
- “This case report establishes a general rule.”
- “This treatment source authorizes treatment advice.”

Source quality rule:

> Source quality modifies allowed use; it must not become platform authority.

---

## 16. Temporal Weight

| Field | Definition |
|---|---|
| weight_id | weight_temporal_v1 |
| weight_family | temporal_weight |
| directional_effect | modifies_reasoning_by_time |
| allowed_claim_level | time_course_context / review_prompt / confidence_limiter |
| blocked_claim_level | prognosis; causality; treatment |
| reasoning_use | mark time-course relevance without closure |

Allowed language:

- “Temporal behavior modifies reasoning.”
- “Progression supports review of this path.”
- “Treatment timing is relevant but not causal by itself.”
- “Prior imaging is needed before stronger language.”

Blocked language:

- “Progression proves diagnosis.”
- “Progression means treatment should start.”
- “Post-treatment timing proves causality.”
- “Stability reassures.”
- “Improvement excludes disease.”

Temporal weight rule:

> Time modifies reasoning; it must not become prognosis, causality, treatment, or reassurance.

---

## 17. Distribution Weight

| Field | Definition |
|---|---|
| weight_id | weight_distribution_v1 |
| weight_family | distribution_weight |
| directional_effect | modifies_reasoning_by_space |
| allowed_claim_level | distribution_context / review_prompt / confidence_limiter |
| blocked_claim_level | diagnosis; rule_out |
| reasoning_use | mark spatial relevance without closure |

Allowed language:

- “Distribution modifies reasoning.”
- “This distribution supports review of this anchor.”
- “This distribution is compatible with multiple paths.”
- “Distribution evidence is incomplete.”

Blocked language:

- “Basal subpleural distribution confirms UIP.”
- “Perilymphatic distribution confirms sarcoidosis.”
- “Random nodules confirm metastases.”
- “This distribution rules out infection.”

Distribution weight rule:

> Distribution modifies reasoning; it must not diagnose or rule out.

---

## 18. Process Weight

| Field | Definition |
|---|---|
| weight_id | weight_process_v1 |
| weight_family | process_weight |
| directional_effect | modifies_reasoning_by_process_type |
| allowed_claim_level | process_context / mimic_visibility / review_prompt |
| blocked_claim_level | disease_label; treatment; causality |
| reasoning_use | mark process-type relevance without disease naming |

Allowed language:

- “Fibrotic process reasoning is active.”
- “Inflammatory process reasoning is active.”
- “Treatment-related process context is relevant.”
- “Exposure-related process context is relevant.”

Blocked language:

- “This is IPF.”
- “This is DI-ILD.”
- “This is occupational ILD.”
- “This process requires treatment.”

Process weight rule:

> Process weight organizes clinical reasoning, not disease identity.

---

## 19. MDD Preparation Weight

| Field | Definition |
|---|---|
| weight_id | weight_mdd_preparation_v1 |
| weight_family | mdd_preparation_weight |
| directional_effect | supports_mdd_preparation |
| allowed_claim_level | MDD_question / evidence_gap / review_prompt |
| blocked_claim_level | MDD_consensus |
| reasoning_use | mark evidence that should become a discussion question |

Allowed language:

- “This may be relevant for MDD preparation.”
- “This gap should be reviewed in MDD.”
- “This overlap should be discussed.”
- “This source conflict should be visible.”

Blocked language:

- “MDD consensus is...”
- “The MDD diagnosis is...”
- “The MDD treatment plan is...”
- “The platform resolves this for MDD.”

MDD preparation rule:

> MDD preparation organizes questions; it does not generate consensus.

---

## 20. Overclaim Guard Weight

| Field | Definition |
|---|---|
| weight_id | weight_overclaim_guard_v1 |
| weight_family | overclaim_guard_weight |
| directional_effect | triggers_wording_caution |
| allowed_claim_level | wording_guard / uncertainty_preserving_phrase |
| blocked_claim_level | report_impression; diagnosis; rule_out |
| reasoning_use | identify wording that overstates evidence |

Allowed language:

- “This wording may overclaim.”
- “Uncertainty-preserving language is needed.”
- “Mimic visibility should be preserved.”
- “Missing evidence should be named.”

Blocked language:

- “Final impression generated.”
- “Diagnosis confirmed.”
- “Disease excluded.”
- “Patient-facing summary generated.”

Overclaim guard rule:

> Overclaim guard protects language; it must not generate final report conclusions.

---

## 21. Hard Block Weight

| Field | Definition |
|---|---|
| weight_id | weight_hard_block_v1 |
| weight_family | hard_block_weight |
| directional_effect | blocks_stronger_language |
| allowed_claim_level | stop_state / repair_required / review_required |
| blocked_claim_level | all clinical closure |
| reasoning_use | stop unsafe evidence-to-closure conversion |

Hard block triggers:

| Trigger | Required Behavior |
|---|---|
| evidence weight converted to probability | hard block |
| support converted to diagnosis | hard block |
| weakening converted to rule-out | hard block |
| mimic visibility converted to mimic diagnosis | hard block |
| mimic unresolved converted to exclusion | hard block |
| overlap converted to ranking | hard block |
| source citation converted to validation | hard block |
| guideline converted to platform authority | hard block |
| treatment source converted to management | hard block |
| exposure context converted to causality | hard block |
| missing evidence converted to negative evidence | hard block |
| real patient data required but not opened | hard block |
| patient-facing output attempted | hard block |

Hard block rule:

> Unsafe evidence-to-closure conversion must stop, not warn.

---

## 22. Qualitative Evidence Weight Scale

v0.20.8 permits only qualitative, non-calibrated weight states.

| Weight State | Meaning | Blocked Misuse |
|---|---|---|
| supports_reasoning | directionally supports a path | diagnosis |
| weakens_reasoning | directionally weakens a path | rule-out |
| insufficient_for_closure | not enough for stronger language | failure / negative |
| nonspecific_overlap | fits multiple paths | useless evidence |
| conflict_requires_review | conflicting evidence exists | automatic decision |
| missing_blocks_closure | missing evidence blocks stronger language | negative evidence |
| mimic_visibility_increased | mimic should remain visible | mimic diagnosis |
| overlap_persistence_increased | multiple paths remain active | ranking |
| confidence_limited | stronger language unsafe | probability |
| mdd_preparation_relevant | should be discussed | MDD consensus |
| hard_block_required | unsafe conversion attempted | proceed anyway |

Qualitative scale rule:

> This scale is ordinal-free and numeric-free. It must never be treated as a calibrated probability model.

---

## 23. Evidence Direction Matrix

| Evidence Direction | Allowed Effect | Blocked Conversion |
|---|---|---|
| supports fibrotic reasoning | fibrotic process review stronger | IPF/UIP diagnosis |
| weakens fibrotic reasoning | fibrotic path less supported | fibrotic ILD ruled out |
| supports inflammatory reasoning | active-opacity review stronger | infection/DI-ILD/RP diagnosis |
| weakens inflammatory reasoning | active inflammatory path less supported | infection/edema excluded |
| supports airway-centered reasoning | airway/exposure review stronger | HP diagnosis |
| weakens airway-centered reasoning | airway path less supported | HP ruled out |
| supports granulomatous reasoning | granulomatous mimic review stronger | sarcoidosis diagnosis |
| weakens granulomatous reasoning | granulomatous path less supported | sarcoidosis/TB/fungal excluded |
| supports malignancy mimic visibility | cancer context review stronger | cancer diagnosis |
| weakens malignancy mimic visibility | cancer path less supported | malignancy excluded |
| supports treatment-related context | treatment timeline review stronger | DI-ILD/RP/CIP causality |
| weakens treatment-related context | treatment path less supported | treatment injury excluded |
| supports exposure context | exposure review stronger | occupational causality |
| weakens exposure context | exposure path less supported | exposure cause excluded |

Evidence direction rule:

> Evidence direction changes what remains visible and review-relevant; it does not decide.

---

## 24. Evidence Weight to Mimic Persistence Matrix

| Evidence Weight | Mimic Persistence Effect |
|---|---|
| evidence_supports_mimic_visibility | mimic remains visible |
| evidence_weakens_mimic_visibility | mimic remains visible but with reduced directional support |
| evidence_missing_for_mimic | mimic remains unresolved |
| evidence_conflicting_for_mimic | mimic remains unresolved and review-required |
| evidence_nonspecific_for_mimic | mimic remains visible with overlap persistence |
| source_edge_case_only_for_mimic | mimic becomes red-team / caution surface only |
| source_guideline_context_for_mimic | mimic visibility supported but not diagnosed |
| source_treatment_context_for_mimic | treatment-related mimic visible but causality blocked |

Mimic persistence rule:

> No evidence weight state autonomously removes a mimic.

---

## 25. Evidence Weight to Missing Evidence Matrix

| Evidence Weight | Missing Evidence Effect |
|---|---|
| support_with_missing_context | support remains limited |
| weakens_with_missing_context | weakening remains non-exclusionary |
| nonspecific_due_to_missing_context | overlap persists |
| conflict_due_to_missing_context | review required |
| source_missing | source gap visible |
| source_partial | partial state visible |
| source_unverified | review required |
| citation_pending | metadata backlog visible |
| real_data_not_opened | current-phase boundary visible |
| validation_not_opened | no performance claim |

Missing evidence rule:

> Missing evidence modulates evidence weight downward qualitatively, but never converts it to negative evidence.

---

## 26. Evidence Weight to Source Status Matrix

| Source Status | Evidence Weight Behavior |
|---|---|
| terminology_core | supports descriptor precision only |
| classification_core | supports broad reasoning context only |
| guideline_core | supports evidence relevance and review boundary, not autonomous authority |
| consensus_core | supports reasoning in uncertainty areas, not proof |
| review_support | supports context and nonspecificity awareness |
| mimic_support | supports mimic visibility, not mimic diagnosis |
| oncology_treatment_risk_support | supports risk/context visibility, not management |
| occupational_exposure_support | supports exposure questioning, not causality |
| edge_case_support | supports red-team trap, not general rule |
| internal_doctrine | supports authority boundary, not medical facts |
| source_conflicting | evidence weight becomes conflict_requires_review |
| source_missing | evidence weight becomes missing_blocks_closure |
| source_unverified | evidence weight becomes review_required |
| source_role_mismatch | evidence weight becomes hard_block_required |

Source status rule:

> Source role determines allowed evidence weight behavior.

---

## 27. Evidence Weight to MDD Preparation Matrix

| Evidence State | MDD Preparation Effect |
|---|---|
| unresolved mimic | add mimic discussion question |
| overlapping process | add overlap discussion question |
| missing temporal evidence | add prior imaging / timeline question |
| missing exposure context | add occupational/environmental history question |
| missing treatment context | add medication/radiation/ICI timeline question |
| missing cancer context | add recurrence vs treatment injury question |
| missing infection context | add infection/microbiology question |
| missing CTD context | add rheumatology/serology question |
| source conflict | add source reconciliation question |
| overclaim risk | add wording caution question |

MDD matrix rule:

> Evidence weight may prepare better MDD questions, but it must not produce MDD answers.

---

## 28. Evidence Weight to Report Overclaim Matrix

| Evidence State | Overclaim Risk | Required Wording Guard |
|---|---|---|
| supports_reasoning | may overstate as diagnosis | use “supports reasoning toward” |
| weakens_reasoning | may overstate as rule-out | use “weakens support for” |
| missing_evidence | may be misread as negative | state missing evidence explicitly |
| conflicting_evidence | may be hidden | state conflict explicitly |
| nonspecific_evidence | may be dismissed | state overlap explicitly |
| mimic_visible | may be converted to diagnosis | state mimic remains visible |
| overlap_persistent | may be converted to ranking | state multiple paths remain active |
| confidence_limited | may be converted to probability | state qualitative limitation only |
| source_edge_case_only | may be generalized | state edge-case warning only |
| citation_present | may be treated as validation | state citation is traceability only |

Overclaim matrix rule:

> Evidence-weighted wording must reduce overclaim, not generate report impressions.

---

## 29. Forbidden Evidence-Weight Closure

The following conversions are blocked:

| Evidence-Weight Meaning | Blocked Conversion |
|---|---|
| supports reasoning | diagnosis |
| weakens reasoning | rule-out |
| evidence missing | negative evidence |
| evidence conflicting | automatic decision |
| evidence nonspecific | useless / ignored |
| mimic visibility increased | mimic diagnosis |
| mimic visibility weakened | mimic exclusion |
| overlap persists | disease ranking |
| confidence limited | numeric probability |
| source present | clinical validation |
| guideline source present | autonomous platform authority |
| treatment source present | treatment instruction |
| exposure source present | causality |
| case report source present | general rule |
| MDD preparation relevant | MDD consensus |
| overclaim guard triggered | final report impression |
| hard block triggered | proceed anyway |

Forbidden closure rule:

> Evidence weight must never collapse into diagnosis, exclusion, probability, ranking, causality, treatment, validation, reassurance, or consensus.

---

## 30. Allowed Evidence-Weighted Phrases

Allowed phrase patterns include:

- “This evidence supports reasoning toward...”
- “This evidence weakens support for...”
- “This evidence is insufficient for closure.”
- “This evidence is nonspecific and overlaps multiple paths.”
- “This source conflict requires review.”
- “This missing evidence limits stronger language.”
- “This feature raises mimic visibility.”
- “This evidence increases overlap persistence.”
- “Confidence remains limited because...”
- “This source supports terminology, not diagnosis.”
- “This source supports context, not management.”
- “This source is an edge-case warning, not a general rule.”
- “This evidence may be relevant for MDD preparation.”
- “This wording may overclaim.”

Allowed phrase rule:

> Evidence-weighted phrases must describe reasoning direction, limitation, or review need without clinical closure.

---

## 31. Evidence Weight Release Conditions

v0.20.8 does not permit autonomous evidence-weight release into clinical closure.

Future governed escalation may be considered only if all are true:

| Release Condition | Required |
|---|---|
| source IDs present | true |
| source roles present | true |
| source status visible | true |
| evidence state visible | true |
| missing evidence addressed or visible | true |
| source conflict resolved or acknowledged | true |
| mimic persistence addressed or visible | true |
| overlap persistence addressed or visible | true |
| clinician review documented | true |
| MDD preparation state visible when relevant | true |
| no autonomous final diagnosis | true |
| no autonomous rule-out | true |
| no calibrated probability | true |
| no treatment authority | true |
| no causality authority | true |
| no patient-facing output | true |

Release rule:

> Evidence weight may become better contextualized, but it cannot be autonomously promoted into clinical closure.

---

## 32. Audit Requirements

Every evidence-weighted reasoning event must be audit-visible as scaffold traceability.

Allowed audit events:

- evidence weight object created,
- source role checked,
- source status checked,
- directional effect assigned,
- missing evidence linked,
- mimic persistence linked,
- overlap persistence linked,
- confidence limiter generated,
- MDD preparation relevance generated,
- overclaim guard generated,
- hard block triggered,
- forbidden conversion blocked,
- citation manifest linked.

Blocked audit meanings:

- clinical correctness proof,
- diagnostic validation,
- treatment correctness,
- patient care audit,
- PACS/EHR audit,
- regulatory evidence,
- product readiness proof,
- probability calibration proof.

Audit rule:

> Audit records evidence-weight governance, not clinical correctness.

---

## 33. Future Implementation Requirements

When implemented later, every evidence-weighted reasoning object must expose:

| Field | Required |
|---|---|
| weight_id | true |
| weight_family | true |
| source_ids | true |
| source_roles | true |
| strength_tiers | true |
| linked_pattern_anchor_ids | true |
| linked_distribution_ids | true |
| linked_temporal_ids | true |
| linked_process_ids | true |
| linked_persistence_ids | true |
| linked_missing_evidence_ids | true |
| evidence_statement | true |
| directional_effect | true |
| allowed_claim_level | true |
| blocked_claim_level | true |
| confidence_limiter | true |
| review_required | true |
| mdd_preparation_relevant | true |
| overclaim_guard_relevant | true |
| citation_manifest_link | true |
| audit_trace_enabled | true |
| diagnosis_closure_allowed | false |
| rule_out_allowed | false |
| mimic_exclusion_allowed | false |
| calibrated_probability_allowed | false |
| ranking_allowed | false |
| treatment_authority_allowed | false |
| causality_claim_allowed | false |
| patient_facing_allowed | false |

Implementation rule:

> Evidence-weighted reasoning objects must be source-linked, auditable, qualitative, missing-evidence-aware, mimic-preserving, review-required, and closure-blocked before they are used in any UI or export surface.

---

## 34. Current-Phase Authority Envelope

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

> Non-calibrated evidence-weighted reasoning improves reasoning directionality; it does not change current clinical authority.

---

## 35. Prototype File Count Preservation

v0.20.8 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.8 is docs-only non-calibrated evidence-weight reasoning governance; the materialized prototype skeleton remains unchanged.

---

## 36. Acceptance Criteria

v0.20.8 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.7 dependency listed | true |
| v0.20.6 dependency listed | true |
| v0.20.5 dependency listed | true |
| v0.20.4 dependency listed | true |
| v0.20.3 dependency listed | true |
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| core evidence-weight concepts defined | true |
| evidence weight families defined | true |
| evidence weight object shape defined | true |
| supportive evidence weight defined | true |
| weakening evidence weight defined | true |
| missing evidence weight defined | true |
| conflicting evidence weight defined | true |
| nonspecific evidence weight defined | true |
| mimic visibility weight defined | true |
| overlap persistence weight defined | true |
| confidence limiter weight defined | true |
| source quality weight defined | true |
| temporal weight defined | true |
| distribution weight defined | true |
| process weight defined | true |
| MDD preparation weight defined | true |
| overclaim guard weight defined | true |
| hard block weight defined | true |
| qualitative evidence weight scale defined | true |
| evidence direction matrix defined | true |
| evidence weight to mimic persistence matrix defined | true |
| evidence weight to missing evidence matrix defined | true |
| evidence weight to source status matrix defined | true |
| evidence weight to MDD preparation matrix defined | true |
| evidence weight to report overclaim matrix defined | true |
| forbidden evidence-weight closure defined | true |
| allowed evidence-weighted phrases defined | true |
| release conditions defined as non-autonomous | true |
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
| no patient-facing output opened | true |
| no real patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |
| prototype file count remains 191 | true |

Acceptance rule:

> v0.20.8 is valid only if evidence can directionally shape reasoning while probability, diagnosis, rule-out, ranking, causality, treatment, prognosis, reassurance, validation, and consensus closure remain blocked.

---

## 37. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Non-calibrated evidence-weight mapping verifies reasoning governance only; it does not certify clinical performance.

---

## 38. Next Step

The next recommended step is:

    v0.20.9 — MDD Preparation / Report Overclaim Guard Map

v0.20.9 should define source-governed MDD preparation and report overclaim guard logic for:

- evidence-gap questions,
- mimic persistence questions,
- overlap questions,
- source conflict questions,
- distribution / temporal questions,
- treatment / exposure / cancer / infection / CTD context questions,
- MDD preparation package structure,
- overclaim phrase detection,
- uncertainty-preserving language,
- report-like export boundary.

v0.20.9 must preserve:

- MDD preparation not MDD consensus,
- report guard not report generation,
- safer wording not final impression,
- review prompt not clinical instruction,
- evidence weight not probability,
- source citation not validation,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no causality authority,
- no patient-facing output,
- no clinical validation,
- no MDD replacement.

Next-step rule:

> v0.20.9 should turn evidence-weighted reasoning into MDD preparation and overclaim prevention without generating clinical conclusions.

---

## 39. Governance Statement

This document records v0.20.8 Non-Calibrated Evidence-Weighted Reasoning Surface.

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

The v0.20.8 discipline is:

> “Create evidence-weighted reasoning without creating probability, diagnosis, exclusion, ranking, causality, treatment, prognosis, reassurance, validation, or consensus closure.”

The final v0.20.8 boundary is:

> “The platform can now let evidence guide reasoning direction; it still cannot decide what disease it is.”
