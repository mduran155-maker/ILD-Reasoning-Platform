# ILD Reasoning Platform — Process-Type Reasoning Map v1

Version: v0.20.5  
Status: process_type_reasoning_map  
Scope: Source-governed process-type reasoning map after v0.20.4  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.5:

- Process-Type Reasoning Map.

v0.20.5 follows:

- v0.20.4 — Distribution / Temporal Reasoning Map,
- v0.20.3 — HRCT Pattern Reasoning Anchor Map,
- v0.20.2a — ILD Reference Bibliography / Citation Manifest,
- v0.20.2 — ILD Reasoning Vocabulary Foundation,
- v0.20.1 — ILD Source Corpus / Reference Backbone Intake,
- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.3 created HRCT pattern reasoning anchors.

v0.20.4 added distribution and temporal reasoning.

v0.20.5 converts pattern + distribution + temporal context into process-type reasoning.

A process type is not a diagnosis.

A process type is a reasoning container that helps the platform ask:

- Is the dominant reasoning surface fibrotic?
- Is there an inflammatory or potentially active component?
- Is the process airway-centered?
- Is a granulomatous process visible?
- Is the process nodular, cystic, lymphatic, vascular, treatment-related, exposure-related, infectious mimic, malignancy mimic, or edema/cardiac mimic?
- Is more than one process active?
- Is the process unresolved because evidence is missing or conflicting?

This document does not diagnose.

It does not assign a disease label.

It does not rank diseases.

It does not calculate probability.

It does not rule out disease.

It does not recommend treatment.

It does not infer causality.

It does not generate a report impression.

It does not generate patient-facing output.

It defines how process-type labels may structure non-autonomous clinician-facing reasoning.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.5 principle is:

> “Process labels organize reasoning; they do not name disease.”

The permanent boundary is:

> “Process type is a reasoning scaffold, not clinical closure.”

---

## 2. Required Previous State

v0.20.5 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
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
| working tree before v0.20.5 is clean | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no calibrated probability opened | true |
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

> v0.20.5 may define process-type reasoning only under source-governed vocabulary, citation manifest, pattern anchors, distribution/temporal reasoning, and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.5 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.5 |
|---|---|---|
| terminology_core | SRC-001 | process descriptor precision and imaging term discipline |
| classification_core | SRC-002 | broad ILD families, inflammation/fibrosis framing, common pattern-process context |
| consensus_core | SRC-003 | progressive fibrotic behavior and progression-aware reasoning |
| guideline_core | SRC-004, SRC-005, SRC-006 | disease-boundary awareness, CTD/sarcoidosis uncertainty, review requirement |
| review_support | SRC-007, SRC-010 | DI-ILD and radiation-related process/mimic context |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | infectious, granulomatous, oncologic, and malignancy mimic persistence |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | drug/radiation/ICI and oncology-treatment process reasoning |
| occupational_exposure_support | SRC-012 | pneumoconiosis, HP, exposure-related granulomatous/fibrotic reasoning |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | mimic traps and red-team scenarios only |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | authority boundaries and non-autonomous behavior |

Source rule:

> Process-type reasoning must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. Process-Type Families

v0.20.5 defines the following process-type reasoning families:

| Process Family | Meaning |
|---|---|
| fibrotic_process | structural fibrotic remodeling reasoning |
| inflammatory_process | potentially active inflammatory or alveolar-interstitial opacity reasoning |
| organizing_process | organizing-pneumonia-like process reasoning |
| airway_centered_process | bronchiolocentric / small-airways process reasoning |
| granulomatous_process | granulomatous / sarcoid-like / perilymphatic process reasoning |
| nodular_process | nodule morphology and distribution process reasoning |
| cystic_process | cystic lung process reasoning |
| lymphatic_vascular_process | septal, peribronchovascular, lymphatic, vascular, or malignancy/edema mimic reasoning |
| treatment_related_process | drug, radiation, ICI, chemotherapy, oncology-treatment context reasoning |
| exposure_related_process | occupational/environmental exposure-linked process reasoning |
| infection_mimic_process | infectious mimic preservation |
| malignancy_mimic_process | malignancy, recurrence, PLC, lymphoma/sarcoid-like mimic preservation |
| edema_cardiac_mimic_process | edema/cardiac-volume mimic preservation |
| mixed_process | multiple active process families |
| unresolved_process | insufficient, conflicting, or not-assessable process state |

Process-family rule:

> Process families organize clinical reasoning; they must not become disease labels, treatment decisions, causality claims, or probability outputs.

---

## 5. Process Object Shape

Future implementation may represent each process type using this shape:

    {
      "process_id": "string",
      "process_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-001", "SRC-002"],
      "source_roles": ["terminology_core", "classification_core"],
      "linked_pattern_anchor_ids": ["string"],
      "linked_distribution_ids": ["string"],
      "linked_temporal_ids": ["string"],
      "allowed_reasoning_use": "string",
      "required_context": ["string"],
      "mimics_to_keep_visible": ["string"],
      "missing_evidence_prompts": ["string"],
      "confidence_limiters": ["string"],
      "review_required": true,
      "mdd_preparation_relevant": true,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "calibrated_probability_allowed": false,
      "treatment_authority_allowed": false,
      "causality_claim_allowed": false,
      "patient_facing_allowed": false
    }

Object rule:

> Every process object must link pattern, distribution, temporal context, source IDs, missing-evidence prompts, mimic visibility, confidence limiters, and clinical-authority blockers.

---

## 6. Fibrotic Process

| Field | Definition |
|---|---|
| process_id | process_fibrotic_v1 |
| process_family | fibrotic_process |
| source_roles | terminology_core; classification_core; consensus_core; guideline_core |
| primary_sources | SRC-001; SRC-002; SRC-003; SRC-004 |
| linked_pattern_anchors | fibrotic_pattern_anchor; mixed_pattern_anchor; indeterminate_pattern_anchor |
| linked_distribution_context | subpleural; basal; upper-lung; peribronchovascular; diffuse; heterogeneous |
| linked_temporal_context | chronic; progressive; stable; slow_progression; acute_on_chronic |
| allowed_reasoning_use | organize fibrosis/remodeling reasoning and progression-aware review |
| required_context | distribution; temporal behavior; prior imaging; CTD context; exposure history; treatment/radiation history |
| mimics_to_keep_visible | IPF/UIP-context; CTD-ILD; fibrotic HP; asbestosis; sarcoidosis; drug/radiation fibrosis; unclassifiable fibrotic ILD |
| missing_evidence_prompts | prior imaging; adequate distribution; exposure history; CTD features/serology; treatment/radiation history; MDD review |
| confidence_limiters | fibrosis overlaps multiple ILD families; progression data may be missing; source context may be incomplete |
| review_required | true |

Allowed language:

- “Fibrotic process reasoning is active.”
- “Fibrotic remodeling features require distribution, temporal, exposure, CTD, and treatment context.”
- “Progression may matter for reasoning, but treatment authority is not opened.”

Blocked language:

- “This is IPF.”
- “This confirms UIP.”
- “This rules out fibrotic HP.”
- “This is progressive pulmonary fibrosis.”
- “Antifibrotic treatment should be started.”

Fibrotic process rule:

> Fibrotic process can structure remodeling and progression reasoning, but it cannot autonomously name IPF/UIP/PPF or decide treatment.

---

## 7. Inflammatory Process

| Field | Definition |
|---|---|
| process_id | process_inflammatory_v1 |
| process_family | inflammatory_process |
| source_roles | terminology_core; classification_core; review_support; mimic_support |
| primary_sources | SRC-001; SRC-002; SRC-007; SRC-010 |
| linked_pattern_anchors | inflammatory_pattern_anchor; organizing_pattern_anchor; treatment_related_pattern_anchor; mixed_pattern_anchor |
| linked_distribution_context | diffuse; patchy; peripheral; peribronchovascular; central; dependent |
| linked_temporal_context | acute; subacute; improving; fluctuating; acute_on_chronic; post_treatment_temporal_link |
| allowed_reasoning_use | organize potentially active opacity/inflammatory reasoning |
| required_context | symptoms; infection context; oxygenation if available; drug/radiation timeline; cardiac/volume context; prior imaging |
| mimics_to_keep_visible | infection; edema; organizing pneumonia; DI-ILD; radiation pneumonitis; ICI pneumonitis; acute exacerbation; hemorrhage; malignancy mimic |
| missing_evidence_prompts | infection data; cardiac/volume status; medication timeline; treatment/radiation dates; prior imaging; clinical review |
| confidence_limiters | ground-glass and consolidation are nonspecific; active opacity has broad mimics |
| review_required | true |

Allowed language:

- “Inflammatory process reasoning is active.”
- “The process may be active but remains nonspecific.”
- “Infection, edema, treatment-related injury, and inflammatory mimics remain visible.”

Blocked language:

- “This is infection.”
- “This is drug toxicity.”
- “This is radiation pneumonitis.”
- “Steroids should be started.”
- “Edema is excluded.”

Inflammatory process rule:

> Inflammatory process organizes active-opacity reasoning; it cannot decide cause or treatment.

---

## 8. Organizing Process

| Field | Definition |
|---|---|
| process_id | process_organizing_v1 |
| process_family | organizing_process |
| source_roles | terminology_core; classification_core; review_support; oncology_treatment_risk_support |
| primary_sources | SRC-001; SRC-002; SRC-007; SRC-008 |
| linked_pattern_anchors | organizing_pattern_anchor; inflammatory_pattern_anchor; treatment_related_pattern_anchor |
| linked_distribution_context | peripheral; bronchocentric; patchy; migratory; lower-lung; peribronchovascular |
| linked_temporal_context | subacute; fluctuating; improving; post_treatment_temporal_link |
| allowed_reasoning_use | organize organizing-pneumonia-like process reasoning |
| required_context | infection context; CTD context; drug exposure; radiation field; cancer/treatment history; prior imaging |
| mimics_to_keep_visible | COP-context; secondary OP; CTD-related OP; DI-ILD; radiation-related OP; infection; malignancy-associated OP-like process |
| missing_evidence_prompts | drug/radiation context; infection evaluation; CTD context; prior imaging; symptoms |
| confidence_limiters | organizing morphology can be primary or secondary; treatment/infection/malignancy contexts overlap |
| review_required | true |

Allowed language:

- “Organizing process reasoning is active.”
- “Organizing morphology may be primary or secondary.”
- “Secondary causes and treatment-related context remain visible.”

Blocked language:

- “This is cryptogenic organizing pneumonia.”
- “This rules out infection.”
- “This confirms DI-ILD.”
- “Steroids are indicated.”

Organizing process rule:

> Organizing process describes a process pattern and context; it does not finalize COP, secondary OP, treatment injury, infection, or therapy.

---

## 9. Airway-Centered Process

| Field | Definition |
|---|---|
| process_id | process_airway_centered_v1 |
| process_family | airway_centered_process |
| source_roles | terminology_core; classification_core; occupational_exposure_support; mimic_support |
| primary_sources | SRC-001; SRC-002; SRC-012 |
| linked_pattern_anchors | airway_centered_pattern_anchor; nodular_pattern_anchor; exposure_related_pattern_anchor |
| linked_distribution_context | centrilobular; lobular; mosaic; air-trapping; airway-centered; patchy |
| linked_temporal_context | subacute; chronic; fluctuating; exposure_latency_relevant |
| allowed_reasoning_use | organize small-airway, bronchiolocentric, and exposure/antigen reasoning |
| required_context | expiratory imaging; antigen/exposure history; smoking history; aspiration context; infection context |
| mimics_to_keep_visible | HP-context; infectious bronchiolitis; aspiration; smoking-related bronchiolitis; CTD airway disease; occupational/environmental exposure |
| missing_evidence_prompts | expiratory imaging; antigen/exposure details; smoking/aspiration context; infection data; occupational review |
| confidence_limiters | airway-centered findings overlap HP, infection, aspiration, smoking, and exposure-related disease |
| review_required | true |

Allowed language:

- “Airway-centered process reasoning is active.”
- “Small-airway and exposure context should be reviewed.”
- “HP-like, infection-like, smoking-related, and aspiration mimics remain visible.”

Blocked language:

- “This is hypersensitivity pneumonitis.”
- “This rules out infection.”
- “Exposure caused this.”
- “This is occupational ILD.”

Airway-centered process rule:

> Airway-centered process prompts small-airway and exposure reasoning; it does not diagnose HP, infection, aspiration, smoking-related disease, or occupational causality.

---

## 10. Granulomatous Process

| Field | Definition |
|---|---|
| process_id | process_granulomatous_v1 |
| process_family | granulomatous_process |
| source_roles | guideline_core; mimic_support; edge_case_support; terminology_core |
| primary_sources | SRC-001; SRC-006; SRC-013; SRC-018; SRC-019; SRC-022 |
| linked_pattern_anchors | granulomatous_pattern_anchor; nodular_pattern_anchor; lymphatic_vascular_mimic_anchor |
| linked_distribution_context | perilymphatic; peribronchovascular; nodal; upper-lung; symmetric/asymmetric |
| linked_temporal_context | acute; subacute; chronic; progressive; treatment_refractory; cancer_follow_up_temporal_context |
| allowed_reasoning_use | organize granulomatous and sarcoid-like mimic reasoning |
| required_context | tissue/pathology context; infection testing context; exposure history; immune status; cancer/treatment history |
| mimics_to_keep_visible | sarcoidosis-context; TB; atypical mycobacteria; histoplasmosis; coccidioidomycosis; beryllium disease; lymphoma; sarcoid-like reaction |
| missing_evidence_prompts | histology/pathology; microbiology/fungal/TB context; exposure history; cancer history; ICI/drug context |
| confidence_limiters | granulomatous imaging and histology are not uniquely specific; alternative causes must remain visible |
| review_required | true |

Allowed language:

- “Granulomatous process reasoning is active.”
- “Alternative granulomatous causes remain visible.”
- “Histology, microbiology, exposure, and cancer/treatment context may be relevant.”

Blocked language:

- “This confirms sarcoidosis.”
- “This excludes TB.”
- “This excludes fungal infection.”
- “This rules out lymphoma.”
- “This is sarcoid-like reaction.”

Granulomatous process rule:

> Granulomatous process exists to preserve alternatives and review requirements, not to autonomously diagnose sarcoidosis or exclude infection/malignancy.

---

## 11. Nodular Process

| Field | Definition |
|---|---|
| process_id | process_nodular_v1 |
| process_family | nodular_process |
| source_roles | terminology_core; classification_core; mimic_support; edge_case_support |
| primary_sources | SRC-001; SRC-002; SRC-006; SRC-013; SRC-020 |
| linked_pattern_anchors | nodular_pattern_anchor; granulomatous_pattern_anchor; airway_centered_pattern_anchor; lymphatic_vascular_mimic_anchor |
| linked_distribution_context | centrilobular; perilymphatic; random; tree-in-bud; subpleural |
| linked_temporal_context | acute; subacute; chronic; progressive; stable |
| allowed_reasoning_use | organize nodule morphology and distribution process reasoning |
| required_context | immune status; infection context; exposure history; cancer history; lymph node/tissue context |
| mimics_to_keep_visible | sarcoidosis; infection; miliary infection; pneumoconiosis; HP; metastases; lymphangitic carcinomatosis |
| missing_evidence_prompts | nodule distribution precision; infectious workup context; exposure history; cancer history; lymph node pattern; tissue context |
| confidence_limiters | nodules overlap infectious, granulomatous, occupational, malignant, and airway-centered contexts |
| review_required | true |

Allowed language:

- “Nodular process reasoning is active.”
- “Nodule distribution should be interpreted with source context.”
- “Granulomatous, infectious, occupational, airway-centered, and malignancy mimics remain visible.”

Blocked language:

- “This confirms sarcoidosis.”
- “This rules out malignancy.”
- “This is metastatic disease.”
- “This excludes infection.”

Nodular process rule:

> Nodular process requires distribution and mimic reasoning; it cannot autonomously diagnose sarcoidosis, infection, pneumoconiosis, HP, or malignancy.

---

## 12. Cystic Process

| Field | Definition |
|---|---|
| process_id | process_cystic_v1 |
| process_family | cystic_process |
| source_roles | terminology_core; classification_core; mimic_support |
| primary_sources | SRC-001; SRC-002 |
| linked_pattern_anchors | cystic_pattern_anchor; fibrotic_pattern_anchor; mixed_pattern_anchor |
| linked_distribution_context | diffuse; upper-lung; lower-lung; perivascular; subpleural; random; basal |
| linked_temporal_context | chronic; progressive; stable |
| allowed_reasoning_use | organize cystic lung process descriptor reasoning |
| required_context | cyst descriptor precision; smoking history; age/sex context; associated nodules; extrapulmonary context; prior imaging |
| mimics_to_keep_visible | LAM-context; PLCH-context; emphysema; honeycombing-like spaces; cystic metastases; infection-related cystic change; autoimmune cystic lung disease |
| missing_evidence_prompts | smoking history; associated nodules; cyst wall/shape/context; emphysema vs cyst vs honeycombing precision; prior imaging |
| confidence_limiters | cystic descriptors overlap emphysema, honeycombing-like spaces, and cystic ILD entities |
| review_required | true |

Allowed language:

- “Cystic process reasoning is active.”
- “Descriptor precision is required.”
- “Cystic process does not assign a disease label.”

Blocked language:

- “This is LAM.”
- “This is PLCH.”
- “This confirms honeycombing.”
- “This excludes emphysema.”

Cystic process rule:

> Cystic process anchors descriptor precision and mimic visibility; it does not assign cystic lung disease labels.

---

## 13. Lymphatic / Vascular Process

| Field | Definition |
|---|---|
| process_id | process_lymphatic_vascular_v1 |
| process_family | lymphatic_vascular_process |
| source_roles | terminology_core; mimic_support; oncology_treatment_risk_support; edge_case_support |
| primary_sources | SRC-001; SRC-020; SRC-021; SRC-015; SRC-016 |
| linked_pattern_anchors | lymphatic_vascular_mimic_anchor; nodular_pattern_anchor; granulomatous_pattern_anchor; inflammatory_pattern_anchor |
| linked_distribution_context | interlobular septal; peribronchovascular; subpleural; lymphatic; asymmetric; unilateral/bilateral |
| linked_temporal_context | progressive; rapid_progression; cancer_follow_up_temporal_context; recurrence_mimic_temporal_context |
| allowed_reasoning_use | organize lymphatic, vascular, septal, edema, and malignancy mimic reasoning |
| required_context | cancer history; PET/CT context if available; edema/cardiac context; infection context; treatment history; tissue context |
| mimics_to_keep_visible | pulmonary lymphangitic carcinomatosis; edema; sarcoidosis; sarcoid-like reaction; infection; drug/radiation injury; recurrence/progression |
| missing_evidence_prompts | cancer/treatment history; PET/CT context; tissue confirmation context; cardiac/volume status; infection data |
| confidence_limiters | septal/peribronchovascular findings overlap PLC, edema, sarcoid-like, infection, and treatment-related injury |
| review_required | true |

Allowed language:

- “Lymphatic/vascular process reasoning is active.”
- “Malignancy, edema, sarcoid-like, infection, and treatment-related mimics remain visible.”
- “Confidence remains limited without clinical, temporal, and source context.”

Blocked language:

- “This is lymphangitic carcinomatosis.”
- “This rules out edema.”
- “This confirms recurrence.”
- “This excludes malignancy.”

Lymphatic / vascular process rule:

> Lymphatic or vascular process reasoning raises mimic visibility and review need; it does not produce autonomous cancer or non-cancer conclusions.

---

## 14. Treatment-Related Process

| Field | Definition |
|---|---|
| process_id | process_treatment_related_v1 |
| process_family | treatment_related_process |
| source_roles | oncology_treatment_risk_support; review_support; mimic_support |
| primary_sources | SRC-007; SRC-008; SRC-009; SRC-010; SRC-011; SRC-014 |
| linked_pattern_anchors | treatment_related_pattern_anchor; inflammatory_pattern_anchor; organizing_pattern_anchor; lymphatic_vascular_mimic_anchor |
| linked_distribution_context | radiation-field-related; diffuse; patchy; bilateral; unilateral; peripheral; peribronchovascular |
| linked_temporal_context | post_treatment_temporal_link; drug_temporal_link_possible; ICI_temporal_link_possible; radiation_temporal_link_possible; delayed_post_radiation_change_possible |
| allowed_reasoning_use | organize drug, radiation, ICI, chemotherapy, and oncology-treatment-related process context |
| required_context | medication timeline; radiation field/dose/timing; ICI/chemotherapy timing; cancer status; infection/cardiac context; baseline ILD |
| mimics_to_keep_visible | infection; edema; malignancy progression; DI-ILD; RILI/RP; ICI pneumonitis; sarcoid-like reaction; acute exacerbation |
| missing_evidence_prompts | drug list; start/stop dates; radiation plan/field/dose; ICI history; baseline ILD; infection/cancer context |
| confidence_limiters | treatment-related injury is nonspecific and requires exclusion of alternatives |
| review_required | true |

Allowed language:

- “Treatment-related process context is relevant.”
- “Temporal association and alternative-cause visibility are required.”
- “Oncology/pulmonology review may be relevant.”

Blocked language:

- “Stop the drug.”
- “Start corticosteroids.”
- “This is radiation pneumonitis.”
- “This is checkpoint inhibitor pneumonitis.”
- “Cancer progression is excluded.”

Treatment-related process rule:

> Treatment-related process anchors context and risk; it does not decide therapy, causality, or cancer status.

---

## 15. Exposure-Related Process

| Field | Definition |
|---|---|
| process_id | process_exposure_related_v1 |
| process_family | exposure_related_process |
| source_roles | occupational_exposure_support; classification_core; terminology_core |
| primary_sources | SRC-012; SRC-002; SRC-001 |
| linked_pattern_anchors | exposure_related_pattern_anchor; airway_centered_pattern_anchor; fibrotic_pattern_anchor; nodular_pattern_anchor; granulomatous_pattern_anchor |
| linked_distribution_context | upper-lung; diffuse; centrilobular; perilymphatic; subpleural; pleural-associated |
| linked_temporal_context | occupational_latency_relevant; environmental_latency_relevant; recurrent_exposure_possible; chronic; progressive |
| allowed_reasoning_use | organize occupational/environmental exposure-linked reasoning |
| required_context | occupational history; environmental exposure; duration/latency; protective equipment; antigen source; smoking history |
| mimics_to_keep_visible | asbestosis-context; silicosis-context; coal workers pneumoconiosis-context; beryllium disease; HP; sarcoidosis; smoking-related disease; idiopathic fibrotic ILD |
| missing_evidence_prompts | job history; exposure duration/intensity; latency; environmental/antigen history; protective equipment; smoking history |
| confidence_limiters | exposure history may be incomplete; imaging overlap exists with idiopathic, granulomatous, CTD, and smoking-related ILD |
| review_required | true |

Allowed language:

- “Exposure-related process reasoning is active.”
- “Occupational/environmental history is a missing-evidence category.”
- “Exposure context may be relevant for MDD preparation.”

Blocked language:

- “This is occupational ILD.”
- “Workplace exposure caused this.”
- “This proves compensation-related causality.”
- “This rules out idiopathic disease.”

Exposure-related process rule:

> Exposure-related process prompts better questions; it does not establish occupational or environmental causality.

---

## 16. Infection Mimic Process

| Field | Definition |
|---|---|
| process_id | process_infection_mimic_v1 |
| process_family | infection_mimic_process |
| source_roles | mimic_support; guideline_core; edge_case_support; review_support |
| primary_sources | SRC-006; SRC-013; SRC-018; SRC-019; SRC-007 |
| linked_pattern_anchors | inflammatory_pattern_anchor; nodular_pattern_anchor; granulomatous_pattern_anchor; airway_centered_pattern_anchor; mixed_pattern_anchor |
| linked_distribution_context | tree-in-bud; random nodules; cavitary/nodular context; diffuse; focal; airway-centered |
| linked_temporal_context | acute; subacute; progressive; treatment_refractory; acute_on_chronic |
| allowed_reasoning_use | preserve infectious mimics when imaging/process patterns overlap ILD |
| required_context | symptoms; immune status; microbiology context; endemic exposure; TB/fungal risk; treatment history |
| mimics_to_keep_visible | TB; atypical mycobacteria; fungal infection; viral infection; bacterial bronchiolitis; opportunistic infection |
| missing_evidence_prompts | microbiology; immune status; fever/symptoms; endemic exposure; BAL/tissue context if available; prior imaging |
| confidence_limiters | infection can mimic inflammatory, nodular, granulomatous, and airway-centered processes |
| review_required | true |

Allowed language:

- “Infection mimic process remains visible.”
- “Infectious alternatives should not disappear when inflammatory, nodular, or granulomatous patterns are present.”
- “Microbiology/source context is a missing-evidence category.”

Blocked language:

- “This is infection.”
- “Infection is excluded.”
- “Antibiotics should be started.”
- “Fungal disease is ruled out.”

Infection mimic process rule:

> Infection mimic process keeps infectious alternatives visible; it does not diagnose or exclude infection.

---

## 17. Malignancy Mimic Process

| Field | Definition |
|---|---|
| process_id | process_malignancy_mimic_v1 |
| process_family | malignancy_mimic_process |
| source_roles | mimic_support; oncology_treatment_risk_support; edge_case_support |
| primary_sources | SRC-020; SRC-021; SRC-014; SRC-015; SRC-016; SRC-017 |
| linked_pattern_anchors | lymphatic_vascular_mimic_anchor; nodular_pattern_anchor; granulomatous_pattern_anchor; treatment_related_pattern_anchor |
| linked_distribution_context | peribronchovascular; septal; subpleural nodularity; asymmetric; unilateral/bilateral; random nodules |
| linked_temporal_context | cancer_follow_up_temporal_context; recurrence_mimic_temporal_context; rapid_progression; post_treatment_change_delayed |
| allowed_reasoning_use | preserve malignancy/recurrence mimics and non-malignant mimics in cancer follow-up contexts |
| required_context | cancer history; treatment timeline; PET/CT context; tissue confirmation context; infection/edema/treatment-related context |
| mimics_to_keep_visible | pulmonary lymphangitic carcinomatosis; metastases; lymphoma; recurrence/progression; sarcoid-like reaction; infection; edema; treatment-related injury |
| missing_evidence_prompts | oncology timeline; PET/CT context; tissue/pathology context; treatment field; infection/cardiac context |
| confidence_limiters | malignancy and non-malignant mimics overlap on surveillance imaging |
| review_required | true |

Allowed language:

- “Malignancy mimic process remains visible.”
- “Cancer recurrence and non-recurrence mimics both remain visible.”
- “Tissue/source context may be relevant if management would change.”

Blocked language:

- “This confirms recurrence.”
- “Cancer progression is excluded.”
- “This is lymphangitic carcinomatosis.”
- “This is benign.”

Malignancy mimic process rule:

> Malignancy mimic process keeps recurrence/progression and benign mimics visible; it does not decide cancer status.

---

## 18. Edema / Cardiac Mimic Process

| Field | Definition |
|---|---|
| process_id | process_edema_cardiac_mimic_v1 |
| process_family | edema_cardiac_mimic_process |
| source_roles | review_support; mimic_support; internal_doctrine |
| primary_sources | SRC-007; SRC-010; SRC-020; INT-005 |
| linked_pattern_anchors | inflammatory_pattern_anchor; lymphatic_vascular_mimic_anchor; mixed_pattern_anchor |
| linked_distribution_context | central; dependent; diffuse; septal; peribronchovascular; symmetric/asymmetric |
| linked_temporal_context | acute; improving; fluctuating; acute_on_chronic |
| allowed_reasoning_use | preserve edema/cardiac/volume-status mimics when interstitial or ground-glass patterns appear |
| required_context | cardiac/volume status; BNP/echo context if available; symptoms; infection/treatment/cancer context; prior imaging |
| mimics_to_keep_visible | pulmonary edema; heart failure; volume overload; infection; inflammatory ILD; treatment injury; PLC |
| missing_evidence_prompts | cardiac/volume data; symptom onset; response to therapy; prior imaging; infection and treatment context |
| confidence_limiters | edema/cardiac patterns overlap inflammatory, lymphatic, treatment-related, and malignancy mimics |
| review_required | true |

Allowed language:

- “Edema/cardiac mimic process remains visible.”
- “Volume/cardiac context may be relevant before stronger language.”
- “Confidence remains limited if cardiac/volume data are missing.”

Blocked language:

- “This is edema.”
- “Heart failure is excluded.”
- “Diuresis should be given.”
- “This rules out ILD.”

Edema/cardiac mimic process rule:

> Edema/cardiac mimic process preserves non-ILD and overlap alternatives; it does not diagnose or treat them.

---

## 19. Mixed Process

| Field | Definition |
|---|---|
| process_id | process_mixed_v1 |
| process_family | mixed_process |
| source_roles | terminology_core; classification_core; guideline_core; internal_doctrine |
| primary_sources | SRC-001; SRC-002; SRC-006; INT-005 |
| linked_pattern_anchors | mixed_pattern_anchor; all active process-compatible pattern anchors |
| linked_distribution_context | multi-distribution; discordant; heterogeneous; regional mismatch |
| linked_temporal_context | acute_on_chronic; progressive_with_superimposed_change; fluctuating; mixed_temporal_behavior |
| allowed_reasoning_use | organize cases where multiple process families remain active |
| required_context | dominant process review; prior imaging; clinical timeline; exposure/treatment/cancer/infection/CTD context; MDD review |
| mimics_to_keep_visible | all active-process mimics |
| missing_evidence_prompts | dominant process; source conflict; temporal behavior; prior imaging; clinician/MDD review |
| confidence_limiters | multiple active processes increase premature closure risk |
| review_required | true |

Allowed language:

- “Mixed process reasoning is active.”
- “Multiple process families remain active.”
- “Closure is unsafe until dominant process, temporal behavior, and mimics are reviewed.”

Blocked language:

- “The unifying diagnosis is...”
- “The dominant disease is...”
- “Other causes are excluded.”
- “This is definitely mixed ILD.”

Mixed process rule:

> Mixed process increases need for structured reasoning; it must not force a unifying diagnosis.

---

## 20. Unresolved Process

| Field | Definition |
|---|---|
| process_id | process_unresolved_v1 |
| process_family | unresolved_process |
| source_roles | internal_doctrine; terminology_core; classification_core; guideline_core |
| primary_sources | INT-005; SRC-001; SRC-002; SRC-006 |
| linked_pattern_anchors | indeterminate_pattern_anchor; mixed_pattern_anchor; all context-relevant anchors |
| linked_distribution_context | not_assessable; conflicting; incomplete; discordant |
| linked_temporal_context | temporal_data_missing; course_unknown; interval_behavior_unknown; temporal_conflict |
| allowed_reasoning_use | preserve uncertainty when process evidence is insufficient, missing, conflicting, or not assessable |
| required_context | adequate descriptors; prior imaging; clinical context; exposure/treatment/CTD/infection/cancer context; review |
| mimics_to_keep_visible | all context-relevant unresolved mimics |
| missing_evidence_prompts | pattern precision; distribution; temporal data; clinical context; source verification; MDD review |
| confidence_limiters | missing source; incomplete descriptors; unresolved mimics; lack of longitudinal data |
| review_required | true |

Allowed language:

- “Process remains unresolved.”
- “Evidence is insufficient for stronger process language.”
- “Missing evidence should be visible before stronger reasoning.”

Blocked language:

- “No disease.”
- “Normal.”
- “Process cannot be assigned ever.”
- “This rules out ILD.”
- “Unresolved equals negative.”

Unresolved process rule:

> Unresolved means “insufficient for closure,” not “absence of disease.”

---

## 21. Process-to-Pattern Anchor Matrix

| Process Family | Primary Pattern Anchors |
|---|---|
| fibrotic_process | fibrotic_pattern_anchor; mixed_pattern_anchor |
| inflammatory_process | inflammatory_pattern_anchor; organizing_pattern_anchor; treatment_related_pattern_anchor |
| organizing_process | organizing_pattern_anchor; inflammatory_pattern_anchor |
| airway_centered_process | airway_centered_pattern_anchor; nodular_pattern_anchor; exposure_related_pattern_anchor |
| granulomatous_process | granulomatous_pattern_anchor; nodular_pattern_anchor; lymphatic_vascular_mimic_anchor |
| nodular_process | nodular_pattern_anchor; granulomatous_pattern_anchor; airway_centered_pattern_anchor |
| cystic_process | cystic_pattern_anchor; fibrotic_pattern_anchor |
| lymphatic_vascular_process | lymphatic_vascular_mimic_anchor; nodular_pattern_anchor; inflammatory_pattern_anchor |
| treatment_related_process | treatment_related_pattern_anchor; inflammatory_pattern_anchor; organizing_pattern_anchor |
| exposure_related_process | exposure_related_pattern_anchor; airway_centered_pattern_anchor; fibrotic_pattern_anchor |
| infection_mimic_process | inflammatory_pattern_anchor; nodular_pattern_anchor; granulomatous_pattern_anchor; airway_centered_pattern_anchor |
| malignancy_mimic_process | lymphatic_vascular_mimic_anchor; nodular_pattern_anchor; granulomatous_pattern_anchor |
| edema_cardiac_mimic_process | inflammatory_pattern_anchor; lymphatic_vascular_mimic_anchor |
| mixed_process | mixed_pattern_anchor; all active anchors |
| unresolved_process | indeterminate_pattern_anchor; all context-relevant anchors |

Matrix rule:

> A process may aggregate pattern anchors, but it must not convert pattern anchors into disease labels.

---

## 22. Process-to-Distribution / Temporal Matrix

| Process Family | Distribution Contexts | Temporal Contexts |
|---|---|---|
| fibrotic_process | subpleural; basal; upper-lung; peribronchovascular; diffuse | chronic; progressive; stable; slow_progression; acute_on_chronic |
| inflammatory_process | diffuse; patchy; peripheral; central; dependent | acute; subacute; improving; fluctuating; acute_on_chronic |
| organizing_process | peripheral; bronchocentric; patchy; migratory | subacute; fluctuating; improving; post_treatment_linked |
| airway_centered_process | centrilobular; lobular; mosaic; air-trapping | subacute; chronic; fluctuating; exposure_latency |
| granulomatous_process | perilymphatic; nodal; upper-lung; symmetric/asymmetric | subacute; chronic; progressive; treatment_refractory |
| nodular_process | centrilobular; perilymphatic; random; tree-in-bud | acute; subacute; chronic; progressive |
| cystic_process | diffuse; upper/lower; subpleural; random | chronic; progressive; stable |
| lymphatic_vascular_process | septal; peribronchovascular; subpleural; asymmetric | progressive; rapid; recurrence_mimic |
| treatment_related_process | field-related; diffuse; patchy; peripheral; bilateral/unilateral | post-treatment; delayed; acute/subacute; fluctuating |
| exposure_related_process | upper-lung; pleural-associated; airway-centered; nodular | latency-relevant; chronic; progressive |
| infection_mimic_process | tree-in-bud; random; focal/diffuse; airway-centered | acute; subacute; progressive; treatment_refractory |
| malignancy_mimic_process | lymphatic; septal; random nodules; asymmetric | progressive; recurrence_mimic; cancer_follow_up |
| edema_cardiac_mimic_process | central; dependent; diffuse; septal | acute; improving; fluctuating |
| mixed_process | multi-distribution; discordant | acute-on-chronic; mixed temporal behavior |
| unresolved_process | not_assessable; conflicting | unknown; missing; conflicting |

Matrix rule:

> Distribution and temporal context refine process reasoning, but never create diagnosis, prognosis, causality, or treatment authority.

---

## 23. Process-to-Mimic Visibility Matrix

| Process Family | Mimics / Alternatives That Must Stay Visible |
|---|---|
| fibrotic_process | CTD-ILD; fibrotic HP; asbestosis; sarcoidosis; drug/radiation fibrosis; unclassifiable fibrotic ILD |
| inflammatory_process | infection; edema; DI-ILD; RP/RILI; ICI pneumonitis; OP; acute exacerbation; hemorrhage; malignancy mimic |
| organizing_process | COP-context; secondary OP; CTD-OP; DI-ILD; radiation-related OP; infection; malignancy-associated OP-like pattern |
| airway_centered_process | HP-context; infection/bronchiolitis; aspiration; smoking-related bronchiolitis; CTD airway disease; occupational/environmental exposure |
| granulomatous_process | sarcoidosis; TB; atypical mycobacteria; fungal infection; beryllium disease; lymphoma; sarcoid-like reaction |
| nodular_process | sarcoidosis; infection; pneumoconiosis; HP; metastases; lymphangitic carcinomatosis |
| cystic_process | LAM-context; PLCH-context; emphysema; honeycombing-like spaces; cystic metastases; autoimmune cystic lung disease |
| lymphatic_vascular_process | PLC; edema; sarcoid-like reaction; infection; recurrence/progression; radiation/drug injury |
| treatment_related_process | infection; edema; malignancy progression; DI-ILD; RP/RILI; ICI pneumonitis; sarcoid-like reaction |
| exposure_related_process | pneumoconiosis; HP; beryllium disease; sarcoidosis; smoking-related disease; idiopathic fibrotic ILD |
| infection_mimic_process | TB; atypical mycobacteria; fungal infection; bacterial/viral/opportunistic infection |
| malignancy_mimic_process | PLC; metastases; lymphoma; recurrence; sarcoid-like reaction; infection; edema; treatment injury |
| edema_cardiac_mimic_process | edema; heart failure; volume overload; infection; inflammatory ILD; treatment injury; PLC |
| mixed_process | all active-process mimics |
| unresolved_process | all context-relevant unresolved mimics |

Mimic matrix rule:

> Process-type reasoning must make dangerous mimics harder to forget, not easier to dismiss.

---

## 24. Process-to-Missing Evidence Matrix

| Process Family | Missing Evidence Prompts |
|---|---|
| fibrotic_process | prior imaging; distribution detail; exposure history; CTD context; treatment/radiation history |
| inflammatory_process | infection data; cardiac/volume status; medication timeline; radiation/treatment history; symptoms/prior imaging |
| organizing_process | drug/radiation context; infection context; CTD context; prior imaging |
| airway_centered_process | expiratory imaging; antigen/exposure history; infection context; smoking/aspiration context |
| granulomatous_process | tissue/pathology context; infection testing; exposure history; cancer/treatment history |
| nodular_process | nodule distribution precision; infection workup; exposure history; cancer history; lymph node/tissue context |
| cystic_process | smoking history; cyst descriptor precision; associated nodules; emphysema vs cyst vs honeycombing distinction |
| lymphatic_vascular_process | cancer history; PET/CT context; tissue confirmation context; edema/cardiac context |
| treatment_related_process | drug list; dose/timing; radiation field/dose; ICI/chemo timeline; baseline ILD; infection/cancer context |
| exposure_related_process | occupational/environmental exposure; latency; duration/intensity; antigen source; protective equipment |
| infection_mimic_process | microbiology; immune status; fever/symptoms; endemic exposure; BAL/tissue context |
| malignancy_mimic_process | oncology timeline; PET/CT context; tissue/pathology context; treatment field; infection/cardiac context |
| edema_cardiac_mimic_process | cardiac/volume data; symptom onset; response context; prior imaging; infection/treatment context |
| mixed_process | dominant process; source conflict; temporal behavior; prior imaging; MDD review |
| unresolved_process | pattern precision; distribution; temporal data; clinical context; source verification; MDD review |

Missing evidence rule:

> Process-type reasoning must name what is missing before stronger language is allowed.

---

## 25. Process-to-Confidence Limiter Matrix

| Process Family | Confidence Limiter |
|---|---|
| fibrotic_process | fibrosis overlaps multiple ILD families; progression and context may be missing |
| inflammatory_process | inflammatory opacities are nonspecific; infection/edema/treatment-related causes overlap |
| organizing_process | organizing morphology may be primary or secondary |
| airway_centered_process | small-airway findings overlap HP, infection, aspiration, smoking, and exposure |
| granulomatous_process | granulomatous patterns are not uniquely specific; alternatives must be excluded clinically |
| nodular_process | nodules overlap infectious, granulomatous, occupational, malignant, and airway-centered contexts |
| cystic_process | cystic descriptors overlap emphysema and honeycombing-like spaces |
| lymphatic_vascular_process | septal/peribronchovascular findings overlap PLC, edema, sarcoid-like, infection, and treatment injury |
| treatment_related_process | treatment-related lung injury is nonspecific and requires alternative-cause review |
| exposure_related_process | exposure history may be incomplete and causality cannot be inferred from imaging alone |
| infection_mimic_process | infection can mimic inflammatory, nodular, granulomatous, and airway-centered processes |
| malignancy_mimic_process | malignancy and non-malignant mimics overlap in surveillance contexts |
| edema_cardiac_mimic_process | edema overlaps inflammatory, lymphatic, treatment-related, and malignancy mimics |
| mixed_process | multiple active processes increase premature closure risk |
| unresolved_process | insufficient or conflicting evidence prevents stronger process language |

Confidence limiter rule:

> Confidence limitation must explain uncertainty qualitatively and must not become a numeric probability.

---

## 26. Forbidden Process Closure

The following conversions are blocked:

| Process Label | Blocked Conversion |
|---|---|
| fibrotic_process | IPF/UIP/PPF/CTD-ILD/fibrotic HP diagnosis |
| inflammatory_process | infection/DI-ILD/RP/edema/acute exacerbation diagnosis or treatment |
| organizing_process | COP/OP diagnosis or steroid recommendation |
| airway_centered_process | HP/infection/aspiration/smoking-related disease diagnosis |
| granulomatous_process | sarcoidosis/TB/fungal disease/beryllium/lymphoma diagnosis |
| nodular_process | sarcoidosis/metastases/infection/pneumoconiosis diagnosis |
| cystic_process | LAM/PLCH/emphysema/honeycombing diagnosis |
| lymphatic_vascular_process | PLC/edema/recurrence diagnosis |
| treatment_related_process | drug/radiation/ICI causality or management decision |
| exposure_related_process | occupational/environmental causality |
| infection_mimic_process | infection diagnosis or exclusion |
| malignancy_mimic_process | cancer recurrence/progression diagnosis or exclusion |
| edema_cardiac_mimic_process | heart failure/edema diagnosis or exclusion |
| mixed_process | forced unifying diagnosis |
| unresolved_process | negative result or disease absence |

Forbidden closure rule:

> Process-to-disease, process-to-causality, process-to-treatment, process-to-prognosis, process-to-probability, and process-to-reassurance conversions are blocked in the current phase.

---

## 27. Allowed Non-Autonomous Process Phrases

Allowed phrase patterns include:

- “Process-type reasoning is active.”
- “This process label organizes the reasoning surface.”
- “This process remains compatible with more than one clinical context.”
- “Mimics remain visible.”
- “Missing evidence limits stronger process language.”
- “Distribution and temporal behavior should be reviewed.”
- “Source status should remain visible.”
- “Confidence remains limited because...”
- “Clinician review is required before stronger language.”
- “This may be relevant for MDD preparation.”
- “This process label does not create autonomous final diagnosis.”

Allowed phrase rule:

> Process phrases must make clinical reasoning more precise without closing the clinical answer.

---

## 28. Future Implementation Requirements

When implemented later, every process-type reasoning object must expose:

| Field | Required |
|---|---|
| process_id | true |
| source_ids | true |
| source_roles | true |
| linked_pattern_anchor_ids | true |
| linked_distribution_ids | true |
| linked_temporal_ids | true |
| process_family | true |
| required_context | true |
| missing_evidence_prompts | true |
| mimic_visibility_list | true |
| confidence_limiters | true |
| review_required | true |
| mdd_preparation_relevant | true |
| forbidden_closure_list | true |
| citation_manifest_link | true |
| audit_trace_enabled | true |
| diagnosis_closure_allowed | false |
| rule_out_allowed | false |
| calibrated_probability_allowed | false |
| treatment_authority_allowed | false |
| causality_claim_allowed | false |
| patient_facing_allowed | false |

Implementation rule:

> Process-type reasoning objects must be source-linked, auditable, missing-evidence-aware, mimic-preserving, review-required, and closure-blocked before they are used in any UI or export surface.

---

## 29. Current-Phase Authority Envelope

The current-phase authority envelope remains:

| Capability | State |
|---|---|
| autonomous final diagnosis | blocked |
| autonomous disease exclusion / rule-out | blocked |
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

> Process-type reasoning improves reasoning structure; it does not change current clinical authority.

---

## 30. Prototype File Count Preservation

v0.20.5 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.5 is docs-only process-type reasoning governance; the materialized prototype skeleton remains unchanged.

---

## 31. Acceptance Criteria

v0.20.5 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.4 dependency listed | true |
| v0.20.3 dependency listed | true |
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| process-type families defined | true |
| process object shape defined | true |
| fibrotic process defined | true |
| inflammatory process defined | true |
| organizing process defined | true |
| airway-centered process defined | true |
| granulomatous process defined | true |
| nodular process defined | true |
| cystic process defined | true |
| lymphatic / vascular process defined | true |
| treatment-related process defined | true |
| exposure-related process defined | true |
| infection mimic process defined | true |
| malignancy mimic process defined | true |
| edema/cardiac mimic process defined | true |
| mixed process defined | true |
| unresolved process defined | true |
| process-to-pattern anchor matrix defined | true |
| process-to-distribution/temporal matrix defined | true |
| process-to-mimic visibility matrix defined | true |
| process-to-missing evidence matrix defined | true |
| process-to-confidence limiter matrix defined | true |
| forbidden process closure defined | true |
| allowed non-autonomous process phrases defined | true |
| future implementation requirements defined | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no calibrated probability opened | true |
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

> v0.20.5 is valid only if process-type reasoning becomes clinically meaningful while diagnosis, causality, treatment, probability, prognosis, and reassurance closure remain blocked.

---

## 32. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Process-type mapping verifies reasoning structure only; it does not certify clinical performance.

---

## 33. Next Step

The next recommended step is:

    v0.20.6 — Mimic / Overlap Persistence Matrix

v0.20.6 should define source-governed mimic and overlap persistence logic for:

- fibrotic overlap,
- inflammatory overlap,
- airway-centered overlap,
- granulomatous overlap,
- nodular overlap,
- cystic overlap,
- lymphatic / vascular overlap,
- treatment-related overlap,
- exposure-related overlap,
- infection mimic persistence,
- malignancy mimic persistence,
- edema/cardiac mimic persistence,
- mixed-process persistence,
- unresolved-process persistence.

v0.20.6 must preserve:

- mimic visibility not diagnosis,
- overlap not ranking,
- persistence not probability,
- mimic unresolved not exclusion,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no causality authority,
- no patient-facing output,
- no clinical validation,
- no MDD replacement.

Next-step rule:

> v0.20.6 should make mimic and overlap persistence explicit without turning unresolved alternatives into diagnosis, exclusion, or ranking.

---

## 34. Governance Statement

This document records v0.20.5 Process-Type Reasoning Map.

It does not implement a clinical product.

It does not diagnose autonomously.  
It does not rule out disease autonomously.  
It does not treat.  
It does not infer clinical causality.  
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

The v0.20.5 discipline is:

> “Create process-type reasoning without creating disease, causality, treatment, probability, prognosis, or reassurance closure.”

The final v0.20.5 boundary is:

> “The platform can now reason about process type; it still cannot decide what disease it is.”
