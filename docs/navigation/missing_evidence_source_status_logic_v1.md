# ILD Reasoning Platform — Missing Evidence / Source Status Logic v1

Version: v0.20.7  
Status: missing_evidence_source_status_logic  
Scope: Source-governed missing evidence and source status logic after v0.20.6  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.7:

- Missing Evidence / Source Status Logic.

v0.20.7 follows:

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

v0.20.7 now defines the logic for missing evidence and source status.

This is a core reasoning layer.

The platform must always know:

- what evidence is present,
- what evidence is missing,
- what evidence is partial,
- what evidence is conflicting,
- what evidence is stale,
- what evidence is unverified,
- what evidence is out of scope,
- what source supports a reasoning surface,
- what source cannot support a reasoning surface,
- when a source is only a terminology source,
- when a source is only an edge-case warning,
- when a source is treatment-related but not treatment authority,
- when a citation exists but does not create clinical validation.

This document does not diagnose.

It does not assign a disease label.

It does not rank diseases.

It does not calculate probability.

It does not rule out disease.

It does not exclude mimics.

It does not recommend treatment.

It does not infer causality.

It does not generate a report impression.

It does not generate patient-facing output.

It defines how missing evidence and source status may structure non-autonomous clinician-facing reasoning.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.7 principle is:

> “Missing evidence is not negative evidence; source status is not clinical authority.”

The permanent boundary is:

> “Evidence gaps and source trails guide reasoning, but they do not close clinical decisions.”

---

## 2. Required Previous State

v0.20.7 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
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
| working tree before v0.20.7 is clean | true |
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

> v0.20.7 may define missing evidence and source status logic only under source-governed vocabulary, citation manifest, pattern anchors, distribution/temporal reasoning, process-type reasoning, mimic persistence, and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.7 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.7 |
|---|---|---|
| terminology_core | SRC-001 | descriptor precision and distinction between terminology and diagnosis |
| classification_core | SRC-002 | broad ILD family context and multi-domain reasoning gaps |
| consensus_core | SRC-003 | progression-related evidence and longitudinal missing evidence |
| guideline_core | SRC-004, SRC-005, SRC-006 | diagnostic uncertainty, evidence gaps, review requirements, alternative-cause visibility |
| review_support | SRC-007, SRC-010 | nonspecific DI-ILD/RILI contexts, exclusion logic, temporal and alternative-cause gaps |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | infectious, granulomatous, sarcoid-like, lymphoma, malignancy, PLC mimic gaps |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | drug/radiation/ICI/cancer-follow-up source gaps and treatment-context boundaries |
| occupational_exposure_support | SRC-012 | occupational/environmental exposure history, latency, and source-status prompts |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | edge-case traps only, not general rules |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | authority boundaries, no-decision logic, and source-governed reasoning behavior |

Source rule:

> Missing evidence and source status logic must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. Core Definitions

v0.20.7 defines the following core concepts.

| Concept | Meaning | Blocked Misuse |
|---|---|---|
| missing_evidence | needed evidence is not available | negative evidence |
| partial_evidence | evidence exists but is incomplete | sufficient evidence |
| conflicting_evidence | sources disagree | automatic decision |
| stale_evidence | evidence is old or context may have changed | valid current truth |
| unverified_evidence | source has not been reviewed or confirmed | clinical fact |
| out_of_scope_evidence | current phase cannot assess it | permanent impossibility |
| source_status | how the source may be used | clinical authority |
| citation_trail | source trace for a reasoning surface | clinical validation |
| source_drift | source used outside allowed role | acceptable shortcut |
| closure_block | stronger language is blocked | final diagnosis |

Core rule:

> Evidence state and source state must be visible before stronger reasoning language is allowed.

---

## 5. Missing Evidence Families

v0.20.7 defines the following missing evidence families:

| Missing Evidence Family | Meaning |
|---|---|
| pattern_evidence_missing | HRCT descriptor / pattern detail missing |
| distribution_evidence_missing | spatial distribution detail missing |
| temporal_evidence_missing | onset, prior imaging, interval behavior, or timeline missing |
| clinical_context_missing | symptoms, physiology, labs, or clinical context missing |
| exposure_context_missing | occupational/environmental/antigen/smoking/aspiration context missing |
| treatment_context_missing | drug, radiation, ICI, chemotherapy, or treatment timeline missing |
| cancer_context_missing | cancer history, recurrence/progression context, PET/CT, tissue context missing |
| infection_context_missing | microbiology, immune status, endemic risk, TB/fungal context missing |
| CTD_context_missing | autoimmune features, serology, rheumatology context missing |
| pathology_context_missing | tissue / histology / biopsy context missing where relevant |
| source_metadata_missing | citation or source role metadata incomplete |
| source_quality_missing | source reliability or scope not visible |
| MDD_context_missing | multidisciplinary review questions not prepared |
| real_data_not_opened | real patient/DICOM/HRCT/report data not opened in current phase |
| validation_not_opened | clinical validation evidence not opened in current phase |

Missing evidence family rule:

> Missing evidence families expose what is absent; they must not imply disease absence.

---

## 6. Source Status Families

v0.20.7 defines the following source status families:

| Source Status Family | Meaning |
|---|---|
| source_present | source is available |
| source_not_provided | source was not supplied |
| source_unavailable | source cannot be accessed |
| source_partial | source is incomplete |
| source_conflicting | source conflicts with another source |
| source_stale | source may be outdated |
| source_unverified | source has not been checked |
| source_out_of_scope | source is outside current phase capability |
| source_synthetic_only | source is fictional/internal synthetic fixture |
| source_edge_case_only | source is case report/edge-case warning only |
| source_guideline_context_only | guideline source informs context but not autonomous authority |
| source_treatment_context_only | treatment-related source informs risk/context but not management |
| source_terminology_only | terminology source supports wording, not diagnosis |
| source_citation_pending | metadata incomplete or pending extraction |
| source_role_mismatch | source is being used outside admitted role |

Source status family rule:

> Source status controls how evidence can be used; it must not become diagnostic truth.

---

## 7. Missing Evidence Object Shape

Future implementation may represent missing evidence using this shape:

    {
      "missing_evidence_id": "string",
      "family": "string",
      "display_label": "string",
      "linked_pattern_anchor_ids": ["string"],
      "linked_distribution_ids": ["string"],
      "linked_temporal_ids": ["string"],
      "linked_process_ids": ["string"],
      "linked_persistence_ids": ["string"],
      "source_ids": ["SRC-001"],
      "source_roles": ["terminology_core"],
      "missing_item": "string",
      "why_it_matters": "string",
      "reasoning_effect": "confidence_limited | mimic_persists | overlap_persists | review_required",
      "blocked_conversion": ["diagnosis", "rule_out", "probability", "treatment", "causality"],
      "review_required": true,
      "mdd_preparation_relevant": true,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "calibrated_probability_allowed": false,
      "treatment_authority_allowed": false,
      "causality_claim_allowed": false,
      "patient_facing_allowed": false
    }

Missing evidence object rule:

> A missing evidence object must explain what is missing, why it matters, what it blocks, and which reasoning surface remains active.

---

## 8. Source Status Object Shape

Future implementation may represent source status using this shape:

    {
      "source_status_id": "string",
      "source_id": "SRC-001",
      "source_role": "terminology_core",
      "strength_tier": "Tier A",
      "status_family": "source_present | source_partial | source_conflicting | source_stale | source_unverified | source_out_of_scope",
      "allowed_use": "string",
      "not_allowed_use": "string",
      "linked_reasoning_surface": "string",
      "citation_manifest_link": "string",
      "metadata_complete": true,
      "source_role_match": true,
      "source_drift_flag": false,
      "review_required": true,
      "clinical_authority_allowed": false,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "calibrated_probability_allowed": false,
      "treatment_authority_allowed": false,
      "patient_facing_allowed": false
    }

Source status object rule:

> A source status object must expose source role, strength tier, allowed use, forbidden use, metadata state, and source drift risk.

---

## 9. Pattern Evidence Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| pattern_descriptor_missing | cannot anchor HRCT pattern reasoning | indeterminate pattern / review required | diagnosis |
| pattern_descriptor_partial | pattern may be mixed or incomplete | confidence limited | diagnosis / ranking |
| descriptor_precision_missing | imprecise imaging term may collapse into disease label | terminology review required | disease naming |
| honeycombing_vs_cyst_missing | cystic/fibrotic distinction unclear | cystic and fibrotic mimics persist | UIP / cystic disease closure |
| ground_glass_context_missing | GGO is nonspecific | infection/edema/treatment/inflammatory mimics persist | inflammatory diagnosis |
| nodule_distribution_missing | nodule distribution drives mimic visibility | infection/granulomatous/malignancy mimics persist | sarcoidosis / metastasis closure |
| airway_descriptor_missing | airway-centered process cannot be assessed | HP/infection/aspiration/smoking mimics persist | HP diagnosis |
| lymphatic_descriptor_missing | PLC/edema/sarcoid-like overlap unresolved | lymphatic/vascular mimics persist | cancer or benign closure |

Pattern evidence rule:

> Missing pattern evidence blocks disease closure and activates mimic persistence.

---

## 10. Distribution Evidence Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| craniocaudal_distribution_missing | upper/lower dominance modifies reasoning | distribution confidence limited | sarcoidosis / UIP / HP closure |
| axial_distribution_missing | subpleural/peribronchovascular context missing | axial review required | UIP / NSIP / PLC closure |
| extent_missing | focal/diffuse/patchy context missing | extent uncertainty visible | severity / prognosis |
| symmetry_missing | symmetric/asymmetric mimic context missing | edema/malignancy/infection mimics persist | malignancy or edema closure |
| nodular_distribution_missing | centrilobular/perilymphatic/random distinction missing | nodular mimics persist | infection / sarcoidosis / metastasis closure |
| field_relationship_missing | radiation/treatment spatial relation unknown | treatment and recurrence mimics persist | RP/RILI or recurrence conclusion |
| airway_distribution_missing | expiratory/airway details missing | small-airway mimics persist | HP / airway disease closure |

Distribution evidence rule:

> Missing distribution evidence blocks spatial overclaim and keeps distribution-sensitive mimics visible.

---

## 11. Temporal Evidence Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| symptom_onset_missing | acute/subacute/chronic course unclear | temporal confidence limited | triage/prognosis |
| prior_imaging_missing | progression/stability cannot be assessed | progression closure blocked | PPF/progression claim |
| interval_behavior_missing | stable/progressive/improving unknown | confidence limited | reassurance / treatment decision |
| treatment_timeline_missing | drug/radiation/ICI causality cannot be assessed | treatment mimics persist | DI-ILD/RP/CIP causality |
| radiation_field_timing_missing | field-related timing unknown | RP/RILI and recurrence overlap persist | RP/RILI diagnosis |
| exposure_latency_missing | occupational/environmental latency unknown | exposure causality blocked | occupational ILD claim |
| cancer_followup_timeline_missing | recurrence/treatment mimic timing unclear | malignancy and benign mimics persist | recurrence confirmation/exclusion |
| acute_on_chronic_baseline_missing | superimposed process cannot be separated | acute-on-chronic mimics persist | acute exacerbation diagnosis |

Temporal evidence rule:

> Missing temporal evidence blocks prognosis, causality, treatment, and progression closure.

---

## 12. Clinical Context Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| symptoms_missing | imaging context incomplete | review required | diagnosis / triage |
| physiology_missing | functional severity/context incomplete | confidence limited | severity/prognosis |
| oxygenation_missing | acute clinical status unknown | clinical authority blocked | triage |
| lab_context_missing | infection/CTD/inflammation context incomplete | missing evidence visible | diagnosis |
| smoking_history_missing | cystic/airway/exposure context incomplete | mimics persist | PLCH/emphysema/smoking disease closure |
| immune_status_missing | infection/opportunistic mimic context incomplete | infection mimics persist | infection exclusion |
| cardiac_volume_status_missing | edema/cardiac mimic context incomplete | edema mimics persist | edema exclusion or diagnosis |

Clinical context rule:

> Missing clinical context limits reasoning and must not become a negative clinical finding.

---

## 13. Exposure Context Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| occupational_history_missing | pneumoconiosis/beryllium/asbestos context incomplete | exposure mimics persist | occupational causality |
| environmental_antigen_missing | HP-like context incomplete | HP/exposure mimics persist | HP closure |
| exposure_duration_missing | dose/time context incomplete | confidence limited | causality |
| exposure_latency_missing | timing relation incomplete | latency review required | causality |
| protective_equipment_missing | exposure intensity uncertain | source status limited | medicolegal/causality claim |
| smoking_exposure_missing | airway/cystic/nodular context incomplete | smoking-related mimics persist | disease closure |
| aspiration_risk_missing | airway/inflammatory mimics incomplete | aspiration mimics persist | aspiration diagnosis/exclusion |

Exposure context rule:

> Exposure gaps should generate better questions, not occupational or environmental causality claims.

---

## 14. Treatment Context Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| medication_list_missing | DI-ILD context incomplete | treatment-related mimics persist | DI-ILD diagnosis |
| medication_start_stop_missing | temporal relation incomplete | causality blocked | drug causality |
| radiation_plan_missing | field/dose unknown | RP/RILI and recurrence overlap persist | radiation pneumonitis diagnosis |
| ICI_history_missing | ICI pneumonitis / sarcoid-like context incomplete | oncology mimics persist | ICI toxicity |
| chemotherapy_timeline_missing | treatment-related context incomplete | treatment mimics persist | causality |
| baseline_ILD_status_missing | treatment risk context incomplete | confidence limited | risk/probability |
| treatment_response_missing | response cannot be interpreted | causality and prognosis blocked | treatment effect claim |

Treatment context rule:

> Treatment context may support mimic visibility and review prompts, not management or causality.

---

## 15. Cancer Context Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| cancer_history_missing | malignancy mimic context incomplete | malignancy mimics persist | cancer diagnosis/exclusion |
| cancer_status_missing | recurrence/progression unknown | recurrence mimic persists | recurrence conclusion |
| PET_CT_context_missing | metabolic context unavailable | source gap visible | malignancy closure |
| tissue_context_missing | pathology absent | confidence limited | benign/malignant closure |
| oncology_treatment_timeline_missing | treatment injury vs progression overlap unresolved | treatment and malignancy mimics persist | causality / recurrence |
| lymph_node_context_missing | sarcoid-like/lymphoma/metastasis overlap unresolved | granulomatous and malignancy mimics persist | sarcoidosis or malignancy closure |

Cancer context rule:

> Cancer context gaps must block both false recurrence closure and false benign reassurance.

---

## 16. Infection Context Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| microbiology_missing | infection cannot be excluded or confirmed | infection mimic persists | infection diagnosis/exclusion |
| TB_context_missing | granulomatous mimic incomplete | TB mimic persists | sarcoidosis closure |
| fungal_context_missing | endemic fungal mimic incomplete | fungal mimic persists | fungal exclusion |
| immune_status_missing | opportunistic infection risk unclear | infection mimics persist | infection exclusion |
| BAL_context_missing | bronchoscopy context absent | source status limited | exclusion |
| fever_symptom_context_missing | clinical infection context incomplete | review required | infection diagnosis |
| antimicrobial_response_missing | response context unavailable | causality/prognosis blocked | infection closure |

Infection context rule:

> Missing infection context keeps infection mimics visible without diagnosing infection.

---

## 17. CTD Context Missing Map

| Missing Evidence | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| CTD_symptoms_missing | autoimmune context incomplete | CTD-ILD mimics persist | CTD diagnosis/exclusion |
| CTD_serology_missing | autoimmune evidence unavailable | confidence limited | CTD closure |
| rheumatology_context_missing | expert review unavailable | review required | CTD diagnosis |
| extrapulmonary_features_missing | systemic context incomplete | source gap visible | CTD exclusion |
| CTD_treatment_history_missing | drug toxicity vs CTD-ILD overlap unresolved | treatment and CTD mimics persist | causality |

CTD context rule:

> Missing CTD context preserves CTD-ILD reasoning without diagnosing or excluding CTD.

---

## 18. Pathology / Microbiology Source Status Map

| Source Status | Meaning | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| pathology_not_available | no tissue source | confidence limited | diagnosis |
| pathology_partial | tissue source incomplete | review required | definitive diagnosis |
| granuloma_present_source | granuloma reported | granulomatous mimics persist | sarcoidosis confirmation |
| granuloma_absent_source | granuloma not reported | source-status visible | sarcoidosis exclusion |
| pathology_conflict | pathology and imaging/clinical context conflict | MDD preparation relevant | final diagnosis |
| microbiology_negative_partial | limited negative microbiology | infection mimic may persist | infection exclusion |
| microbiology_pending | results not available | infection mimic persists | infection exclusion |
| tissue_culture_missing | culture absent where relevant | infection/granulomatous mimics persist | infectious exclusion |

Pathology/microbiology rule:

> Tissue or microbiology source status may strengthen review context but must not create autonomous diagnosis or exclusion.

---

## 19. Source Metadata Missing Map

| Source Metadata Gap | Why It Matters | Required Reasoning Effect | Blocked Conversion |
|---|---|---|---|
| source_id_missing | source trail absent | reasoning not ready | UI/export use |
| source_role_missing | allowed source use unknown | source drift flag | reasoning output |
| strength_tier_missing | authority level unclear | review required | claim escalation |
| DOI_or_identifier_pending | bibliography incomplete | metadata backlog visible | citation certainty |
| source_scope_missing | what source supports unknown | source use blocked | reasoning decision |
| source_limitation_missing | forbidden uses unknown | source drift risk | authority claim |
| citation_manifest_link_missing | decision cannot be traced | audit incomplete | export readiness |
| edge_case_flag_missing | case report may be misused | source drift flag | general rule |

Source metadata rule:

> Bibliographic incompleteness must be visible and must block untraceable reasoning escalation.

---

## 20. Source Status Action Matrix

| Source Status | Allowed Action | Required Guard | Blocked Action |
|---|---|---|---|
| source_present | use within admitted role | citation visible | clinical authority |
| source_not_provided | mark missing evidence | confidence limited | negative finding |
| source_unavailable | mark unavailable | review required | disease absence |
| source_partial | use cautiously | partial-state visible | closure |
| source_conflicting | expose conflict | MDD preparation relevant | automatic decision |
| source_stale | flag staleness | current-context review | current truth |
| source_unverified | mark unverified | review required | clinical fact |
| source_out_of_scope | block current use | phase boundary visible | permanent impossibility |
| source_synthetic_only | use for demo structure | synthetic label visible | real case claim |
| source_edge_case_only | use as red-team trap | not general rule | generalization |
| source_guideline_context_only | use for evidence context | not autonomous authority | automatic guideline enforcement |
| source_treatment_context_only | use for mimic/context | no management authority | treatment instruction |
| source_terminology_only | use for descriptor precision | not disease logic | diagnosis |
| source_citation_pending | keep metadata backlog | no citation-complete claim | final citation claim |
| source_role_mismatch | block use | repair required | reasoning output |

Source status action rule:

> Source status determines safe use; unsafe source use must fail closed.

---

## 21. Missing Evidence to Reasoning Effect Matrix

| Missing Evidence Type | Reasoning Effect |
|---|---|
| pattern_evidence_missing | indeterminate pattern; mimic persistence; review required |
| distribution_evidence_missing | distribution confidence limited; pattern closure blocked |
| temporal_evidence_missing | progression/stability/causality blocked |
| clinical_context_missing | clinical authority blocked; review required |
| exposure_context_missing | exposure-related mimics persist; causality blocked |
| treatment_context_missing | treatment-related mimics persist; management/causality blocked |
| cancer_context_missing | malignancy and benign mimics persist; recurrence closure blocked |
| infection_context_missing | infection mimics persist; infection exclusion blocked |
| CTD_context_missing | CTD-ILD context persists; CTD closure blocked |
| pathology_context_missing | tissue-dependent closure blocked |
| source_metadata_missing | reasoning output not export-ready |
| source_quality_missing | source status review required |
| MDD_context_missing | MDD preparation relevant |
| real_data_not_opened | current-phase synthetic-only boundary visible |
| validation_not_opened | no performance or clinical readiness claim |

Reasoning effect rule:

> Missing evidence should activate limitation, persistence, and review; it must not activate diagnosis, exclusion, or probability.

---

## 22. Source Drift Protection

A source drift flag must be raised if:

| Drift Type | Example | Required Behavior |
|---|---|---|
| terminology_to_diagnosis_drift | Fleischner descriptor used as disease diagnosis | block reasoning output |
| guideline_to_autonomy_drift | guideline source used as platform decision authority | fail closed |
| review_to_rule_drift | review article used as definitive rule | downgrade / review |
| case_report_to_general_rule_drift | case report used as general truth | block generalization |
| treatment_source_to_management_drift | treatment-related source used to recommend therapy | hard block |
| exposure_source_to_causality_drift | occupational source used for causality | hard block |
| mimic_source_to_exclusion_drift | mimic source used to exclude mimic | hard block |
| citation_to_validation_drift | citation used as clinical validation | hard block |
| synthetic_source_to_patient_truth_drift | synthetic fixture treated as real case | hard block |
| stale_source_to_current_truth_drift | stale context used as current fact | review required |

Source drift rule:

> The wrong use of a source is as unsafe as no source.

---

## 23. Citation Manifest Linkage Requirements

Every future reasoning object must carry citation linkage.

| Field | Required |
|---|---|
| source_ids | true |
| source_roles | true |
| strength_tiers | true |
| bibliography_reference | true |
| citation_manifest_link | true |
| allowed_source_use | true |
| forbidden_source_use | true |
| metadata_status | true |
| source_drift_flag | true |
| audit_trace_enabled | true |

Citation linkage rule:

> A reasoning object without a source trail is not ready for UI, export, or audit.

---

## 24. Hard Block Conditions

The system must hard block stronger reasoning language if any are true:

| Hard Block | Meaning |
|---|---|
| source_id_missing | no source trail |
| source_role_mismatch | source used outside admitted role |
| missing_evidence_critical | required evidence absent |
| source_conflict_unresolved | evidence conflict unresolved |
| edge_case_used_as_general_rule | case report generalized |
| terminology_used_as_diagnosis | descriptor collapsed into disease |
| treatment_context_used_as_management | treatment source used to treat |
| exposure_context_used_as_causality | exposure source used to establish cause |
| mimic_visibility_used_as_exclusion | mimic visibility converted to rule-out |
| citation_used_as_validation | citation treated as performance evidence |
| real_data_required_but_not_opened | current phase cannot assess real data |
| clinical_validation_required_but_not_opened | validation claim attempted |
| patient_facing_output_attempted | patient-facing use attempted |

Hard block rule:

> Hard blocks are stop-states, not warnings.

---

## 25. Allowed Non-Autonomous Missing Evidence / Source Status Phrases

Allowed phrase patterns include:

- “Evidence is missing.”
- “The source was not provided.”
- “The source is partial.”
- “The source is conflicting.”
- “The source is not sufficient for closure.”
- “This source supports terminology, not diagnosis.”
- “This source supports mimic visibility, not exclusion.”
- “This source is an edge-case warning, not a general rule.”
- “This treatment-related source supports context, not management.”
- “This exposure-related source supports questioning, not causality.”
- “Citation is available, but clinical validation is not opened.”
- “Confidence remains limited because source status is incomplete.”
- “MDD preparation may be relevant because evidence is incomplete.”

Allowed phrase rule:

> Missing evidence and source status phrases must preserve uncertainty without closing the clinical answer.

---

## 26. Forbidden Missing Evidence / Source Status Closure

The following conversions are blocked:

| Source / Evidence State | Blocked Conversion |
|---|---|
| evidence missing | disease absent |
| source not provided | negative evidence |
| source unavailable | no disease |
| partial source | sufficient source |
| conflicting source | automatic decision |
| stale source | current truth |
| unverified source | clinical fact |
| terminology source | diagnosis |
| guideline source | autonomous authority |
| treatment source | treatment recommendation |
| exposure source | causality |
| edge-case source | general rule |
| citation trail | clinical validation |
| synthetic fixture | real patient data |
| validation not opened | product readiness |
| real data not opened | clinical implementation readiness |

Forbidden closure rule:

> Evidence and source states must never collapse into diagnosis, exclusion, probability, treatment, causality, validation, readiness, or reassurance.

---

## 27. Missing Evidence Release Conditions

v0.20.7 does not permit autonomous release of missing evidence blocks.

Future governed release may be considered only if all are true:

| Release Condition | Required |
|---|---|
| missing evidence item explicitly addressed | true |
| source ID present | true |
| source role present | true |
| source status visible | true |
| source conflict resolved or acknowledged | true |
| metadata complete or pending state visible | true |
| clinician review documented | true |
| MDD preparation state visible when relevant | true |
| no autonomous final diagnosis | true |
| no autonomous rule-out | true |
| no calibrated probability | true |
| no treatment authority | true |
| no patient-facing output | true |

Release rule:

> Missing evidence may become contextualized, but it cannot be autonomously converted into closure.

---

## 28. Audit Requirements

Every missing evidence or source status event must be audit-visible as scaffold traceability.

Allowed audit events:

- missing evidence item created,
- source status item created,
- source role checked,
- source drift blocked,
- source conflict displayed,
- stale source displayed,
- unverified source displayed,
- source metadata pending displayed,
- citation manifest linked,
- hard block triggered,
- review requirement generated,
- MDD preparation relevance generated.

Blocked audit meanings:

- clinical correctness proof,
- diagnostic validation,
- treatment correctness,
- patient care audit,
- PACS/EHR audit,
- regulatory evidence,
- product readiness proof.

Audit rule:

> Audit records reasoning governance, not clinical correctness.

---

## 29. Future Implementation Requirements

When implemented later, every missing evidence and source status object must expose:

| Field | Required |
|---|---|
| object_id | true |
| family | true |
| source_ids | true |
| source_roles | true |
| strength_tiers | true |
| linked_pattern_anchor_ids | true |
| linked_distribution_ids | true |
| linked_temporal_ids | true |
| linked_process_ids | true |
| linked_persistence_ids | true |
| missing_item_or_source_status | true |
| why_it_matters | true |
| reasoning_effect | true |
| blocked_conversion | true |
| confidence_limiters | true |
| review_required | true |
| mdd_preparation_relevant | true |
| citation_manifest_link | true |
| audit_trace_enabled | true |
| source_drift_flag | true |
| diagnosis_closure_allowed | false |
| rule_out_allowed | false |
| mimic_exclusion_allowed | false |
| calibrated_probability_allowed | false |
| ranking_allowed | false |
| treatment_authority_allowed | false |
| causality_claim_allowed | false |
| patient_facing_allowed | false |

Implementation rule:

> Missing evidence and source status objects must be source-linked, auditable, role-aware, drift-protected, review-required, and closure-blocked before they are used in any UI or export surface.

---

## 30. Current-Phase Authority Envelope

The current-phase authority envelope remains:

| Capability | State |
|---|---|
| autonomous final diagnosis | blocked |
| autonomous disease exclusion / rule-out | blocked |
| autonomous mimic exclusion | blocked |
| calibrated diagnostic probability | not_opened |
| disease ranking | not_opened |
| treatment authority | none |
| test-order authority | none |
| procedure authority | none |
| follow-up authority | none |
| triage authority | none |
| causality authority | none |
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

> Missing evidence and source status logic improves reasoning governance; it does not change current clinical authority.

---

## 31. Prototype File Count Preservation

v0.20.7 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.7 is docs-only missing evidence / source status reasoning governance; the materialized prototype skeleton remains unchanged.

---

## 32. Acceptance Criteria

v0.20.7 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.6 dependency listed | true |
| v0.20.5 dependency listed | true |
| v0.20.4 dependency listed | true |
| v0.20.3 dependency listed | true |
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| core definitions defined | true |
| missing evidence families defined | true |
| source status families defined | true |
| missing evidence object shape defined | true |
| source status object shape defined | true |
| pattern evidence missing map defined | true |
| distribution evidence missing map defined | true |
| temporal evidence missing map defined | true |
| clinical context missing map defined | true |
| exposure context missing map defined | true |
| treatment context missing map defined | true |
| cancer context missing map defined | true |
| infection context missing map defined | true |
| CTD context missing map defined | true |
| pathology/microbiology source status map defined | true |
| source metadata missing map defined | true |
| source status action matrix defined | true |
| missing evidence to reasoning effect matrix defined | true |
| source drift protection defined | true |
| citation manifest linkage requirements defined | true |
| hard block conditions defined | true |
| allowed non-autonomous phrases defined | true |
| forbidden source/evidence closure defined | true |
| release conditions defined as non-autonomous | true |
| audit requirements defined | true |
| future implementation requirements defined | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no autonomous mimic exclusion opened | true |
| no calibrated probability opened | true |
| no ranking opened | true |
| no treatment authority opened | true |
| no causality authority opened | true |
| no patient-facing output opened | true |
| no real patient data opened | true |
| no DICOM/HRCT/report/PACS/EHR opened | true |
| no clinical validation opened | true |
| no diagnostic performance claim opened | true |
| no MDD replacement opened | true |
| prototype file count remains 191 | true |

Acceptance rule:

> v0.20.7 is valid only if missing evidence and source status become clinically meaningful while absence, conflict, citation, and source role never become diagnosis, exclusion, probability, causality, treatment, validation, readiness, or reassurance.

---

## 33. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Missing evidence / source status mapping verifies reasoning governance only; it does not certify clinical performance.

---

## 34. Next Step

The next recommended step is:

    v0.20.8 — Non-Calibrated Evidence-Weighted Reasoning Surface

v0.20.8 should define source-governed, non-calibrated evidence-weighting language for:

- evidence supports reasoning,
- evidence weakens reasoning,
- evidence is missing,
- evidence is conflicting,
- evidence is nonspecific,
- evidence requires review,
- evidence increases mimic visibility,
- evidence increases overlap persistence,
- evidence limits confidence,
- evidence supports MDD preparation.

v0.20.8 must preserve:

- evidence weight not probability,
- support not diagnosis,
- weakening not rule-out,
- conflict not decision,
- missing evidence not negative evidence,
- citation not validation,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no causality authority,
- no patient-facing output,
- no clinical validation,
- no MDD replacement.

Next-step rule:

> v0.20.8 should let evidence affect reasoning direction without becoming numeric probability, diagnosis, rule-out, treatment, or validation.

---

## 35. Governance Statement

This document records v0.20.7 Missing Evidence / Source Status Logic.

It does not implement a clinical product.

It does not diagnose autonomously.  
It does not rule out disease autonomously.  
It does not exclude mimics autonomously.  
It does not rank diseases.  
It does not calculate probability.  
It does not treat.  
It does not infer clinical causality.  
It does not validate clinical performance.  
It does not decide tests.  
It does not decide procedures.  
It does not schedule follow-up.  
It does not triage.  
It does not reassure.  
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

The v0.20.7 discipline is:

> “Create missing evidence and source status logic without creating diagnosis, exclusion, probability, causality, treatment, validation, readiness, or reassurance closure.”

The final v0.20.7 boundary is:

> “The platform can now explain what evidence is missing and what each source can support; it still cannot decide what disease it is.”
