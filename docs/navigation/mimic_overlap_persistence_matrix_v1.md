# ILD Reasoning Platform — Mimic / Overlap Persistence Matrix v1

Version: v0.20.6  
Status: mimic_overlap_persistence_matrix  
Scope: Source-governed mimic and overlap persistence matrix after v0.20.5  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.6:

- Mimic / Overlap Persistence Matrix.

v0.20.6 follows:

- v0.20.5 — Process-Type Reasoning Map,
- v0.20.4 — Distribution / Temporal Reasoning Map,
- v0.20.3 — HRCT Pattern Reasoning Anchor Map,
- v0.20.2a — ILD Reference Bibliography / Citation Manifest,
- v0.20.2 — ILD Reasoning Vocabulary Foundation,
- v0.20.1 — ILD Source Corpus / Reference Backbone Intake,
- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.3 defined HRCT pattern anchors.

v0.20.4 defined distribution and temporal reasoning.

v0.20.5 defined process-type reasoning.

v0.20.6 now defines how mimics and overlapping reasoning paths must persist.

This is one of the core values of the ILD Reasoning Platform.

A simple differential diagnosis list names possible diseases.

This platform must do more:

- keep unresolved mimics visible,
- prevent premature closure,
- show overlapping reasoning paths,
- distinguish mimic visibility from mimic diagnosis,
- distinguish overlap from ranking,
- distinguish persistence from probability,
- distinguish unresolved status from exclusion,
- preserve missing evidence,
- preserve source status,
- preserve review requirement.

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

It defines how unresolved mimics and overlapping process paths may remain visible in non-autonomous clinician-facing reasoning.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.6 principle is:

> “A mimic that is not safely closed must remain visible.”

The permanent boundary is:

> “Mimic persistence is not diagnosis, exclusion, ranking, probability, treatment, or reassurance.”

---

## 2. Required Previous State

v0.20.6 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
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
| working tree before v0.20.6 is clean | true |
| no autonomous final diagnosis opened | true |
| no autonomous rule-out opened | true |
| no autonomous mimic exclusion opened | true |
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

> v0.20.6 may define mimic and overlap persistence only under source-governed vocabulary, citation manifest, pattern anchors, distribution/temporal reasoning, process-type reasoning, and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.6 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.6 |
|---|---|---|
| terminology_core | SRC-001 | imaging descriptor precision and avoidance of disease-label collapse |
| classification_core | SRC-002 | shared radiologic/histopathologic pattern families and broad ILD taxonomy |
| consensus_core | SRC-003 | progression and fibrotic behavior overlap awareness |
| guideline_core | SRC-004, SRC-005, SRC-006 | disease-boundary awareness, diagnostic uncertainty, review requirement |
| review_support | SRC-007, SRC-010 | DI-ILD and radiation-related overlap with infection, edema, malignancy, and inflammatory patterns |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | infectious, granulomatous, sarcoid-like, lymphomatous, malignancy, and PLC mimic persistence |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | cancer-treatment overlap, RP/RILI/CIP/DI-ILD and recurrence mimic logic |
| occupational_exposure_support | SRC-012 | exposure-related overlap among pneumoconiosis, HP, granulomatous disease, and diffuse fibrosis |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | red-team mimic traps only |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | authority boundaries and non-autonomous behavior |

Source rule:

> Mimic and overlap persistence must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. Core Persistence Concepts

v0.20.6 defines four core concepts.

| Concept | Meaning | Blocked Misuse |
|---|---|---|
| mimic_visibility | an alternative cause or look-alike remains visible | mimic diagnosis |
| mimic_unresolved | evidence is insufficient to close the mimic | mimic excluded |
| overlap_persistence | more than one process/path remains active | disease ranking |
| closure_block | stronger language is blocked until evidence/review supports it | permanent impossibility |

Persistence rule:

> The platform should preserve unresolved alternatives until evidence and human review justify stronger language.

---

## 5. Persistence Object Shape

Future implementation may represent mimic / overlap persistence using this shape:

    {
      "persistence_id": "string",
      "persistence_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-006", "SRC-007"],
      "source_roles": ["guideline_core", "review_support"],
      "linked_pattern_anchor_ids": ["string"],
      "linked_distribution_ids": ["string"],
      "linked_temporal_ids": ["string"],
      "linked_process_ids": ["string"],
      "mimics_visible": ["string"],
      "overlap_paths": ["string"],
      "missing_evidence_prompts": ["string"],
      "source_status_prompts": ["string"],
      "confidence_limiters": ["string"],
      "closure_block_reason": "string",
      "review_required": true,
      "mdd_preparation_relevant": true,
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

> Every mimic / overlap persistence object must carry source IDs, active mimics, overlap paths, missing evidence, source status, confidence limiters, closure blockers, and clinical-authority blockers.

---

## 6. Persistence Families

v0.20.6 defines the following persistence families:

| Persistence Family | Meaning |
|---|---|
| fibrotic_overlap_persistence | fibrotic mimics and overlapping fibrotic disease contexts remain visible |
| inflammatory_overlap_persistence | inflammatory, infectious, edema, treatment-related, and acute-on-chronic mimics remain visible |
| organizing_overlap_persistence | primary and secondary organizing-like contexts remain visible |
| airway_centered_overlap_persistence | HP, infection, aspiration, smoking, CTD airway, and exposure contexts remain visible |
| granulomatous_overlap_persistence | sarcoidosis, infection, beryllium, lymphoma, sarcoid-like, and immune mimic contexts remain visible |
| nodular_overlap_persistence | infectious, granulomatous, occupational, malignant, airway-centered, and HP nodular mimics remain visible |
| cystic_overlap_persistence | cystic disease, emphysema, honeycombing-like, autoimmune, and malignant cystic mimics remain visible |
| lymphatic_vascular_overlap_persistence | PLC, edema, sarcoid-like, infection, treatment injury, and recurrence mimics remain visible |
| treatment_related_overlap_persistence | drug, radiation, ICI, infection, edema, malignancy progression, and sarcoid-like mimics remain visible |
| exposure_related_overlap_persistence | pneumoconiosis, HP, beryllium, sarcoidosis, smoking, and idiopathic fibrotic contexts remain visible |
| infection_mimic_persistence | infection remains visible across inflammatory, nodular, granulomatous, airway, and mixed processes |
| malignancy_mimic_persistence | recurrence, PLC, metastases, lymphoma, sarcoid-like, infection, edema, and treatment injury remain visible |
| edema_cardiac_mimic_persistence | edema/cardiac-volume mimics remain visible against inflammatory, lymphatic, treatment, and malignancy paths |
| mixed_process_persistence | multiple active process families remain visible without forced unification |
| unresolved_process_persistence | unresolved state persists without becoming negative or reassuring |

Persistence-family rule:

> Persistence families preserve uncertainty safely; they must not become diagnostic categories.

---

## 7. Fibrotic Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_fibrotic_overlap_v1 |
| persistence_family | fibrotic_overlap_persistence |
| source_roles | terminology_core; classification_core; consensus_core; guideline_core; occupational_exposure_support |
| primary_sources | SRC-001; SRC-002; SRC-003; SRC-004; SRC-012 |
| linked_process_ids | process_fibrotic_v1; process_exposure_related_v1; process_mixed_v1; process_unresolved_v1 |
| mimics_visible | IPF/UIP-context; CTD-ILD; fibrotic HP; asbestosis; sarcoidosis; drug/radiation fibrosis; unclassifiable fibrotic ILD |
| overlap_paths | UIP-like pattern across IPF, RA-ILD, fibrotic HP, SSc-ILD, sarcoidosis, asbestosis; progressive fibrosis across multiple non-IPF ILDs |
| missing_evidence_prompts | prior imaging; CTD context; exposure history; drug/radiation history; distribution detail; MDD review |
| confidence_limiters | fibrotic patterns overlap multiple ILD families; progression does not determine etiology; exposure and CTD context may be missing |
| closure_block_reason | fibrotic pattern and progression cannot autonomously identify a disease family or treatment pathway |
| review_required | true |

Allowed language:

- “Fibrotic overlap persists.”
- “Several fibrotic reasoning paths remain visible.”
- “Progression modifies reasoning but does not close etiology.”

Blocked language:

- “This is IPF.”
- “This confirms UIP.”
- “This rules out HP.”
- “This is PPF.”
- “Antifibrotic treatment should be started.”

Fibrotic persistence rule:

> Fibrotic overlap persistence prevents UIP-like or progressive fibrosis language from collapsing into IPF, PPF, HP, CTD-ILD, asbestosis, or treatment decisions.

---

## 8. Inflammatory Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_inflammatory_overlap_v1 |
| persistence_family | inflammatory_overlap_persistence |
| source_roles | terminology_core; classification_core; review_support; mimic_support; oncology_treatment_risk_support |
| primary_sources | SRC-001; SRC-002; SRC-007; SRC-010; SRC-009 |
| linked_process_ids | process_inflammatory_v1; process_infection_mimic_v1; process_edema_cardiac_mimic_v1; process_treatment_related_v1; process_mixed_v1 |
| mimics_visible | infection; edema; DI-ILD; RP/RILI; ICI pneumonitis; organizing pneumonia; acute exacerbation; hemorrhage; malignancy mimic |
| overlap_paths | ground-glass/consolidation across infection, edema, inflammatory ILD, treatment injury, malignancy-related opacity, acute exacerbation |
| missing_evidence_prompts | infection data; cardiac/volume status; medication timeline; radiation/treatment history; symptoms; prior imaging |
| confidence_limiters | inflammatory opacities are nonspecific; infection/edema/treatment/cancer overlap may remain unresolved |
| closure_block_reason | inflammatory opacity cannot autonomously decide cause, treatment, or exclusion |
| review_required | true |

Allowed language:

- “Inflammatory overlap persists.”
- “Infection, edema, treatment-related injury, and inflammatory mimics remain visible.”
- “Confidence remains limited by nonspecific opacity and missing context.”

Blocked language:

- “This is infection.”
- “This is drug toxicity.”
- “This is radiation pneumonitis.”
- “Edema is excluded.”
- “Steroids should be started.”

Inflammatory persistence rule:

> Inflammatory overlap persistence prevents ground-glass or consolidation from collapsing into infection, edema, treatment injury, acute exacerbation, or treatment instruction.

---

## 9. Organizing Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_organizing_overlap_v1 |
| persistence_family | organizing_overlap_persistence |
| source_roles | terminology_core; classification_core; review_support; oncology_treatment_risk_support |
| primary_sources | SRC-001; SRC-002; SRC-007; SRC-008 |
| linked_process_ids | process_organizing_v1; process_inflammatory_v1; process_treatment_related_v1; process_mixed_v1 |
| mimics_visible | COP-context; secondary OP; CTD-related OP; DI-ILD; radiation-related OP; infection; malignancy-associated OP-like process |
| overlap_paths | organizing morphology across cryptogenic, CTD, drug, radiation, infection, malignancy-associated, and secondary contexts |
| missing_evidence_prompts | drug/radiation context; infection context; CTD context; malignancy context; prior imaging |
| confidence_limiters | organizing morphology may be primary or secondary; secondary causes may overlap |
| closure_block_reason | organizing-like pattern cannot autonomously decide COP, secondary OP, infection, malignancy, or treatment |
| review_required | true |

Allowed language:

- “Organizing overlap persists.”
- “Primary and secondary organizing contexts remain visible.”
- “Secondary causes require review before stronger language.”

Blocked language:

- “This is cryptogenic organizing pneumonia.”
- “This rules out infection.”
- “This confirms DI-ILD.”
- “Steroids are indicated.”

Organizing persistence rule:

> Organizing overlap persistence keeps secondary causes visible and blocks OP-like morphology from becoming a final diagnosis or therapy prompt.

---

## 10. Airway-Centered Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_airway_centered_overlap_v1 |
| persistence_family | airway_centered_overlap_persistence |
| source_roles | terminology_core; classification_core; occupational_exposure_support; mimic_support |
| primary_sources | SRC-001; SRC-002; SRC-012; SRC-013 |
| linked_process_ids | process_airway_centered_v1; process_exposure_related_v1; process_infection_mimic_v1; process_mixed_v1 |
| mimics_visible | HP-context; infection/bronchiolitis; aspiration; smoking-related bronchiolitis; CTD airway disease; occupational/environmental exposure |
| overlap_paths | centrilobular/mosaic/air-trapping across HP, infection, aspiration, smoking, occupational exposure, and CTD airway disease |
| missing_evidence_prompts | expiratory imaging; antigen/exposure history; smoking history; aspiration context; infection context |
| confidence_limiters | airway-centered findings overlap multiple small-airway and exposure-related processes |
| closure_block_reason | airway-centered pattern cannot autonomously diagnose HP, infection, aspiration, smoking disease, or occupational causality |
| review_required | true |

Allowed language:

- “Airway-centered overlap persists.”
- “HP-like, infection-like, aspiration, smoking, CTD airway, and exposure contexts remain visible.”
- “Expiratory imaging and exposure context may be missing.”

Blocked language:

- “This is hypersensitivity pneumonitis.”
- “This rules out infection.”
- “Exposure caused this.”
- “This is occupational ILD.”

Airway-centered persistence rule:

> Airway-centered overlap persistence keeps exposure, small-airway, infection, smoking, and aspiration contexts visible without diagnosing any of them.

---

## 11. Granulomatous Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_granulomatous_overlap_v1 |
| persistence_family | granulomatous_overlap_persistence |
| source_roles | guideline_core; mimic_support; edge_case_support; terminology_core |
| primary_sources | SRC-006; SRC-013; SRC-018; SRC-019; SRC-022; SRC-001 |
| linked_process_ids | process_granulomatous_v1; process_nodular_v1; process_infection_mimic_v1; process_malignancy_mimic_v1; process_unresolved_v1 |
| mimics_visible | sarcoidosis; TB; atypical mycobacteria; histoplasmosis; coccidioidomycosis; beryllium disease; lymphoma; sarcoid-like reaction; GLILD; IgG4-related disease |
| overlap_paths | granulomatous imaging/histology across sarcoidosis, infection, exposure, immune, lymphoma, and sarcoid-like reaction contexts |
| missing_evidence_prompts | tissue/pathology context; infection testing; fungal/TB context; exposure history; immune status; cancer/treatment history |
| confidence_limiters | granulomas and granulomatous imaging are not uniquely specific; alternatives must remain visible |
| closure_block_reason | granulomatous pattern cannot autonomously diagnose sarcoidosis or exclude infection, lymphoma, exposure disease, or immune mimics |
| review_required | true |

Allowed language:

- “Granulomatous overlap persists.”
- “Alternative granulomatous causes remain visible.”
- “Negative single-source testing should not automatically close mimics.”

Blocked language:

- “This confirms sarcoidosis.”
- “This excludes TB.”
- “This excludes fungal infection.”
- “This rules out lymphoma.”
- “This is sarcoid-like reaction.”

Granulomatous persistence rule:

> Granulomatous overlap persistence protects against sarcoidosis closure before infectious, exposure-related, malignant, immune, and treatment-related alternatives remain reviewed.

---

## 12. Nodular Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_nodular_overlap_v1 |
| persistence_family | nodular_overlap_persistence |
| source_roles | terminology_core; classification_core; mimic_support; edge_case_support |
| primary_sources | SRC-001; SRC-002; SRC-006; SRC-013; SRC-020; SRC-021 |
| linked_process_ids | process_nodular_v1; process_granulomatous_v1; process_airway_centered_v1; process_malignancy_mimic_v1; process_infection_mimic_v1 |
| mimics_visible | sarcoidosis; infection; miliary infection; pneumoconiosis; HP; metastases; lymphangitic carcinomatosis |
| overlap_paths | centrilobular, perilymphatic, random, tree-in-bud, and subpleural nodularity across infectious, granulomatous, occupational, malignant, and airway-centered contexts |
| missing_evidence_prompts | nodule distribution precision; immune status; infection workup; exposure history; cancer history; lymph node/tissue context |
| confidence_limiters | nodular patterns overlap broad infectious, granulomatous, occupational, malignant, and airway-centered contexts |
| closure_block_reason | nodular distribution cannot autonomously diagnose or exclude sarcoidosis, infection, pneumoconiosis, HP, or malignancy |
| review_required | true |

Allowed language:

- “Nodular overlap persists.”
- “Nodule distribution should be source-checked.”
- “Infectious, granulomatous, occupational, airway-centered, and malignancy mimics remain visible.”

Blocked language:

- “This confirms sarcoidosis.”
- “This is metastatic disease.”
- “This rules out malignancy.”
- “This excludes infection.”

Nodular persistence rule:

> Nodular overlap persistence prevents nodule distribution from collapsing into sarcoidosis, infection, pneumoconiosis, HP, metastasis, or PLC.

---

## 13. Cystic Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_cystic_overlap_v1 |
| persistence_family | cystic_overlap_persistence |
| source_roles | terminology_core; classification_core; mimic_support |
| primary_sources | SRC-001; SRC-002 |
| linked_process_ids | process_cystic_v1; process_fibrotic_v1; process_mixed_v1; process_unresolved_v1 |
| mimics_visible | LAM-context; PLCH-context; emphysema; honeycombing-like spaces; cystic metastases; infection-related cystic change; autoimmune cystic lung disease |
| overlap_paths | cystic descriptor overlap across cysts, emphysema, honeycombing-like spaces, fibrotic cystic remodeling, and cystic disease entities |
| missing_evidence_prompts | cyst wall/shape/size; associated nodules; smoking history; age/sex context; emphysema vs cyst vs honeycombing precision |
| confidence_limiters | cystic descriptors overlap emphysema and honeycombing-like spaces; entity labels require context |
| closure_block_reason | cystic pattern cannot autonomously diagnose LAM, PLCH, emphysema, honeycombing, or cystic metastasis |
| review_required | true |

Allowed language:

- “Cystic overlap persists.”
- “Descriptor precision is required before stronger language.”
- “Cyst, emphysema, and honeycombing-like possibilities remain distinct.”

Blocked language:

- “This is LAM.”
- “This is PLCH.”
- “This confirms honeycombing.”
- “This excludes emphysema.”

Cystic persistence rule:

> Cystic overlap persistence blocks cyst-like language from becoming a disease label or excluding emphysema/honeycombing-like mimics.

---

## 14. Lymphatic / Vascular Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_lymphatic_vascular_overlap_v1 |
| persistence_family | lymphatic_vascular_overlap_persistence |
| source_roles | terminology_core; mimic_support; oncology_treatment_risk_support; edge_case_support |
| primary_sources | SRC-001; SRC-020; SRC-021; SRC-015; SRC-016; SRC-017 |
| linked_process_ids | process_lymphatic_vascular_v1; process_malignancy_mimic_v1; process_edema_cardiac_mimic_v1; process_granulomatous_v1; process_treatment_related_v1 |
| mimics_visible | pulmonary lymphangitic carcinomatosis; edema; sarcoidosis; sarcoid-like reaction; infection; recurrence/progression; radiation/drug injury |
| overlap_paths | septal/peribronchovascular/subpleural/lymphatic findings across PLC, edema, sarcoidosis, sarcoid-like reaction, infection, recurrence, and treatment injury |
| missing_evidence_prompts | cancer history; PET/CT context; tissue confirmation context; cardiac/volume status; infection context; treatment timeline |
| confidence_limiters | septal and lymphatic findings overlap malignancy and non-malignancy contexts |
| closure_block_reason | lymphatic/vascular pattern cannot autonomously decide malignancy, edema, sarcoid-like reaction, infection, or recurrence status |
| review_required | true |

Allowed language:

- “Lymphatic/vascular overlap persists.”
- “Malignancy and non-malignancy mimics remain visible.”
- “Cancer follow-up context requires source-status visibility.”

Blocked language:

- “This is lymphangitic carcinomatosis.”
- “This rules out edema.”
- “This confirms recurrence.”
- “This excludes malignancy.”

Lymphatic / vascular persistence rule:

> Lymphatic/vascular overlap persistence protects against both false recurrence closure and false benign reassurance.

---

## 15. Treatment-Related Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_treatment_related_overlap_v1 |
| persistence_family | treatment_related_overlap_persistence |
| source_roles | oncology_treatment_risk_support; review_support; mimic_support |
| primary_sources | SRC-007; SRC-008; SRC-009; SRC-010; SRC-011; SRC-014 |
| linked_process_ids | process_treatment_related_v1; process_inflammatory_v1; process_organizing_v1; process_malignancy_mimic_v1; process_infection_mimic_v1; process_edema_cardiac_mimic_v1 |
| mimics_visible | DI-ILD; RP/RILI; ICI pneumonitis; sarcoid-like reaction; infection; edema; malignancy progression; acute exacerbation; organizing pneumonia |
| overlap_paths | post-treatment opacity across drug toxicity, radiation injury, ICI pneumonitis, infection, edema, cancer progression, sarcoid-like reaction, and OP-like patterns |
| missing_evidence_prompts | medication list; drug timing; radiation field/dose/timing; ICI/chemo timeline; infection/cardiac context; cancer status; baseline ILD |
| confidence_limiters | treatment-related lung injury is nonspecific and requires alternative-cause review |
| closure_block_reason | post-treatment timing cannot establish causality, management, recurrence status, or exclusion |
| review_required | true |

Allowed language:

- “Treatment-related overlap persists.”
- “Treatment timing is relevant but not causal by itself.”
- “Infection, edema, progression, and treatment injury remain visible.”

Blocked language:

- “This is drug-induced ILD.”
- “This is radiation pneumonitis.”
- “This is checkpoint inhibitor pneumonitis.”
- “Cancer progression is excluded.”
- “Stop the drug.”

Treatment-related persistence rule:

> Treatment-related overlap persistence blocks post-treatment timing from becoming causality, toxicity diagnosis, recurrence exclusion, or management instruction.

---

## 16. Exposure-Related Overlap Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_exposure_related_overlap_v1 |
| persistence_family | exposure_related_overlap_persistence |
| source_roles | occupational_exposure_support; classification_core; terminology_core |
| primary_sources | SRC-012; SRC-002; SRC-001 |
| linked_process_ids | process_exposure_related_v1; process_airway_centered_v1; process_fibrotic_v1; process_granulomatous_v1; process_mixed_v1 |
| mimics_visible | asbestosis-context; silicosis-context; coal workers pneumoconiosis-context; beryllium disease; HP; sarcoidosis; smoking-related disease; idiopathic fibrotic ILD |
| overlap_paths | exposure-linked pattern overlap across pneumoconiosis, HP, beryllium disease, sarcoidosis, smoking-related disease, CTD-like or idiopathic fibrosis contexts |
| missing_evidence_prompts | occupational history; environmental exposure; exposure duration/intensity; latency; protective equipment; antigen source; smoking history |
| confidence_limiters | exposure history may be incomplete; imaging overlap exists with idiopathic, granulomatous, CTD, and smoking-related disease |
| closure_block_reason | exposure-related context cannot establish occupational/environmental causality or exclude non-exposure causes |
| review_required | true |

Allowed language:

- “Exposure-related overlap persists.”
- “Exposure history is a missing-evidence category.”
- “Occupational/environmental review may be relevant.”

Blocked language:

- “This is occupational ILD.”
- “Workplace exposure caused this.”
- “This proves compensation-related causality.”
- “This rules out idiopathic disease.”

Exposure-related persistence rule:

> Exposure-related overlap persistence keeps exposure reasoning visible without converting exposure context into causality.

---

## 17. Infection Mimic Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_infection_mimic_v1 |
| persistence_family | infection_mimic_persistence |
| source_roles | mimic_support; guideline_core; edge_case_support; review_support |
| primary_sources | SRC-006; SRC-013; SRC-018; SRC-019; SRC-007 |
| linked_process_ids | process_infection_mimic_v1; process_inflammatory_v1; process_nodular_v1; process_granulomatous_v1; process_airway_centered_v1 |
| mimics_visible | TB; atypical mycobacteria; fungal infection; bacterial infection; viral infection; opportunistic infection; aspiration/infectious bronchiolitis |
| overlap_paths | infection mimicking sarcoidosis, nodular disease, airway-centered disease, inflammatory opacity, DI-ILD, acute exacerbation, or malignancy |
| missing_evidence_prompts | symptoms; immune status; microbiology context; endemic exposure; fungal/TB risk; BAL/tissue context if available |
| confidence_limiters | infection can mimic multiple ILD patterns and may not be excluded by incomplete source data |
| closure_block_reason | infection mimic cannot be diagnosed or excluded autonomously |
| review_required | true |

Allowed language:

- “Infection mimic persists.”
- “Infectious alternatives remain visible.”
- “Microbiology/source context may be missing.”

Blocked language:

- “This is infection.”
- “Infection is excluded.”
- “Fungal disease is ruled out.”
- “Antibiotics should be started.”

Infection persistence rule:

> Infection mimic persistence blocks both infection overcall and infection erasure.

---

## 18. Malignancy Mimic Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_malignancy_mimic_v1 |
| persistence_family | malignancy_mimic_persistence |
| source_roles | mimic_support; oncology_treatment_risk_support; edge_case_support |
| primary_sources | SRC-020; SRC-021; SRC-014; SRC-015; SRC-016; SRC-017 |
| linked_process_ids | process_malignancy_mimic_v1; process_lymphatic_vascular_v1; process_nodular_v1; process_granulomatous_v1; process_treatment_related_v1 |
| mimics_visible | PLC; metastases; lymphoma; recurrence/progression; sarcoid-like reaction; infection; edema; treatment-related injury |
| overlap_paths | cancer follow-up findings overlapping malignancy progression, treatment injury, sarcoid-like reaction, granulomatous disease, infection, and edema |
| missing_evidence_prompts | oncology timeline; PET/CT context; tissue/pathology context; treatment field; infection/cardiac context |
| confidence_limiters | malignancy and non-malignant mimics overlap in surveillance and post-treatment contexts |
| closure_block_reason | malignancy mimic cannot be diagnosed or excluded autonomously |
| review_required | true |

Allowed language:

- “Malignancy mimic persists.”
- “Recurrence/progression and non-malignant mimics both remain visible.”
- “Cancer follow-up context should preserve uncertainty.”

Blocked language:

- “This confirms recurrence.”
- “Cancer progression is excluded.”
- “This is lymphangitic carcinomatosis.”
- “This is benign.”

Malignancy persistence rule:

> Malignancy mimic persistence blocks both false cancer closure and false benign reassurance.

---

## 19. Edema / Cardiac Mimic Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_edema_cardiac_mimic_v1 |
| persistence_family | edema_cardiac_mimic_persistence |
| source_roles | review_support; mimic_support; internal_doctrine |
| primary_sources | SRC-007; SRC-010; SRC-020; INT-005 |
| linked_process_ids | process_edema_cardiac_mimic_v1; process_inflammatory_v1; process_lymphatic_vascular_v1; process_treatment_related_v1; process_mixed_v1 |
| mimics_visible | pulmonary edema; heart failure; volume overload; infection; inflammatory ILD; treatment injury; PLC |
| overlap_paths | central/dependent/septal/diffuse patterns overlapping edema, infection, inflammation, treatment injury, and malignancy mimics |
| missing_evidence_prompts | cardiac/volume data; symptom onset; response context; prior imaging; infection and treatment context |
| confidence_limiters | edema/cardiac mimics overlap inflammatory, lymphatic, treatment-related, and malignancy contexts |
| closure_block_reason | edema/cardiac mimic cannot be diagnosed or excluded autonomously |
| review_required | true |

Allowed language:

- “Edema/cardiac mimic persists.”
- “Volume/cardiac context may be relevant.”
- “Confidence remains limited if cardiac/volume data are missing.”

Blocked language:

- “This is edema.”
- “Heart failure is excluded.”
- “Diuresis should be given.”
- “This rules out ILD.”

Edema/cardiac persistence rule:

> Edema/cardiac mimic persistence preserves non-ILD and overlap alternatives without diagnosing or treating them.

---

## 20. Mixed Process Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_mixed_process_v1 |
| persistence_family | mixed_process_persistence |
| source_roles | terminology_core; classification_core; guideline_core; internal_doctrine |
| primary_sources | SRC-001; SRC-002; SRC-006; INT-005 |
| linked_process_ids | process_mixed_v1; all active process IDs |
| mimics_visible | all active-process mimics |
| overlap_paths | multiple simultaneous process families, discordant pattern/distribution/time-course, acute-on-chronic change, source conflict |
| missing_evidence_prompts | dominant process; prior imaging; clinical timeline; source conflict; exposure/treatment/cancer/infection/CTD context |
| confidence_limiters | multiple active processes increase premature closure risk |
| closure_block_reason | mixed process cannot force a unifying diagnosis or rank disease families |
| review_required | true |

Allowed language:

- “Mixed-process persistence is active.”
- “Multiple process families remain visible.”
- “Closure is unsafe until active overlaps are reviewed.”

Blocked language:

- “The unifying diagnosis is...”
- “The dominant disease is...”
- “Other causes are excluded.”
- “This is definitely mixed ILD.”

Mixed persistence rule:

> Mixed process persistence prevents forced unification.

---

## 21. Unresolved Process Persistence

| Field | Definition |
|---|---|
| persistence_id | persistence_unresolved_process_v1 |
| persistence_family | unresolved_process_persistence |
| source_roles | internal_doctrine; terminology_core; classification_core; guideline_core |
| primary_sources | INT-005; SRC-001; SRC-002; SRC-006 |
| linked_process_ids | process_unresolved_v1; all context-relevant process IDs |
| mimics_visible | all context-relevant unresolved mimics |
| overlap_paths | incomplete pattern, incomplete distribution, missing temporal data, source conflict, absent clinical context |
| missing_evidence_prompts | pattern precision; distribution; temporal data; clinical context; source verification; MDD review |
| confidence_limiters | missing source, incomplete descriptors, unresolved mimics, and absent longitudinal data prevent stronger language |
| closure_block_reason | unresolved state cannot become negative, reassuring, or exclusionary |
| review_required | true |

Allowed language:

- “Unresolved persistence is active.”
- “Evidence is insufficient for stronger language.”
- “Unresolved does not mean negative.”

Blocked language:

- “No disease.”
- “Normal.”
- “This rules out ILD.”
- “Unresolved equals negative.”
- “Nothing concerning.”

Unresolved persistence rule:

> Unresolved means “cannot safely close,” not “absence of disease.”

---

## 22. Pairwise Overlap Matrix

| Overlap Pair | Persistence Meaning | Required Guard |
|---|---|---|
| fibrotic + inflammatory | chronic remodeling with possible active superimposed process | acute-on-chronic mimics remain visible |
| fibrotic + airway-centered | UIP-like / fibrotic HP / exposure / CTD overlap | exposure and expiratory imaging gaps remain visible |
| fibrotic + granulomatous | sarcoidosis/asbestosis/HP/fibrotic overlap | granulomatous and exposure alternatives persist |
| inflammatory + infection | active opacity may be infectious or noninfectious | infection not diagnosed or excluded |
| inflammatory + edema | GGO/septal opacity may reflect volume/cardiac context | edema not diagnosed or excluded |
| inflammatory + treatment-related | DI-ILD/RP/CIP/infection/edema overlap | treatment timing not causality |
| organizing + treatment-related | secondary OP-like treatment reaction possible | OP-like morphology not final OP diagnosis |
| airway-centered + exposure | HP/occupational/smoking/aspiration overlap | exposure not causality |
| nodular + granulomatous | sarcoidosis/infection/pneumoconiosis/lymphoma overlap | granulomatous mimic persistence |
| nodular + malignancy | metastases/PLC/infection/sarcoid-like overlap | malignancy not confirmed or excluded |
| cystic + fibrotic | honeycombing-like vs cystic/emphysema overlap | descriptor precision required |
| lymphatic/vascular + edema | septal/peribronchovascular overlap | edema and PLC both persist |
| lymphatic/vascular + malignancy | PLC/recurrence/sarcoid-like/treatment overlap | cancer status not decided |
| treatment-related + malignancy | toxicity vs recurrence/progression overlap | both remain visible |
| treatment-related + infection | toxicity vs infection overlap | neither diagnosis nor exclusion |
| exposure-related + fibrotic | pneumoconiosis/HP/asbestosis/idiopathic overlap | occupational causality blocked |
| infection + granulomatous | fungal/TB/mycobacterial vs sarcoidosis overlap | infection alternatives persist |
| malignancy + granulomatous | lymphoma/sarcoid-like/sarcoidosis overlap | benign/malignant closure blocked |
| mixed + unresolved | multiple active uncertainties | no forced unifying diagnosis |

Pairwise overlap rule:

> Overlap pairs must preserve both sides of the overlap until evidence and review justify stronger language.

---

## 23. Mimic Closure State Machine

v0.20.6 defines the following allowed closure states:

| State | Meaning | Allowed Next State | Blocked Meaning |
|---|---|---|---|
| mimic_visible | mimic is present in reasoning surface | mimic_unresolved; mimic_context_reviewed | diagnosis |
| mimic_unresolved | evidence insufficient for closure | missing_evidence_named; review_required | exclusion |
| missing_evidence_named | specific missing evidence is visible | review_required; source_status_reviewed | test order |
| source_status_reviewed | source quality/scope is visible | review_required | validation |
| review_required | clinician/MDD review required | mdd_preparation_relevant | MDD consensus |
| mdd_preparation_relevant | MDD discussion may include this | remains_non_autonomous | final MDD decision |
| closure_blocked | stronger language blocked | repair/review required | diagnosis/rule-out/probability |

State machine rule:

> No current-phase state transitions to final diagnosis, rule-out, probability, treatment, causality, reassurance, or MDD consensus.

---

## 24. Mimic Persistence Trigger Matrix

A mimic must persist if any trigger is true.

| Trigger | Persistence Required |
|---|---|
| evidence_missing | mimic remains visible |
| source_not_provided | mimic remains visible |
| source_conflict | mimic remains visible |
| pattern_overlap_present | mimic remains visible |
| distribution_overlap_present | mimic remains visible |
| temporal_overlap_present | mimic remains visible |
| treatment_timeline_incomplete | treatment-related mimics remain visible |
| exposure_history_incomplete | exposure-related mimics remain visible |
| prior_imaging_missing | progression/stability-based closure blocked |
| cancer_history_present | malignancy and non-malignancy mimics remain visible |
| immunosuppression_or_immune_context_present | infection and immune mimics remain visible |
| granulomatous_pattern_present | infectious, exposure, lymphoma, sarcoid-like mimics remain visible |
| nodular_distribution_unclear | infectious, granulomatous, malignant, occupational mimics remain visible |
| acute_on_chronic_behavior_present | infection, edema, exacerbation, treatment injury, malignancy mimics remain visible |
| current_phase_boundary_applies | all unresolved mimics remain non-autonomous |

Trigger rule:

> Persistence is the default when closure evidence is missing, conflicting, incomplete, or outside current authority.

---

## 25. Mimic Persistence Release Conditions

v0.20.6 does not permit autonomous mimic release.

Future governed release may be considered only if all are true:

| Release Condition | Required |
|---|---|
| source IDs available | true |
| source roles visible | true |
| relevant missing evidence addressed | true |
| source conflict resolved or acknowledged | true |
| clinician review documented | true |
| MDD preparation status visible when relevant | true |
| no autonomous final diagnosis | true |
| no autonomous rule-out | true |
| no calibrated probability | true |
| no treatment authority | true |
| no patient-facing output | true |

Release rule:

> In the current phase, mimics may become better contextualized but not autonomously closed.

---

## 26. Overlap Severity Tiers

v0.20.6 defines overlap severity tiers.

| Tier | Meaning | Example | Required Behavior |
|---|---|---|---|
| Tier 1 | low-risk descriptive overlap | distribution nonspecific | show confidence limiter |
| Tier 2 | clinically meaningful overlap | fibrotic HP vs UIP-like context | show missing evidence and review |
| Tier 3 | dangerous mimic overlap | infection vs inflammatory/treatment injury | keep mimic visible and review-required |
| Tier 4 | malignancy/recurrence overlap | PLC/recurrence vs sarcoid-like/treatment injury | hard block diagnosis/exclusion |
| Tier 5 | treatment/causality overlap | DI-ILD/RP/CIP vs infection/progression | block causality and management |
| Tier 6 | unresolved high-stakes overlap | multiple active mimics + missing source | fail stronger language; MDD preparation relevant |

Severity rule:

> Higher-risk overlap requires stronger persistence and stronger closure blocking.

---

## 27. Source Status Requirements

Every mimic / overlap surface must expose source status.

| Source Status Field | Required Meaning |
|---|---|
| source_ids | which sources support the reasoning surface |
| source_roles | guideline, glossary, review, mimic support, edge case, internal doctrine |
| strength_tiers | Tier A/B/C/D/E |
| source_scope | what the source is allowed to support |
| source_limitation | what the source cannot support |
| missing_source_flag | source absent or not provided |
| source_conflict_flag | sources conflict |
| edge_case_only_flag | case report/edge case not general rule |
| treatment_source_boundary | treatment-related source not management authority |
| guideline_source_boundary | guideline source not autonomous platform authority |

Source status rule:

> A mimic / overlap decision without source status is not ready for UI or export.

---

## 28. Forbidden Mimic / Overlap Closure

The following conversions are blocked:

| Persistence Meaning | Blocked Conversion |
|---|---|
| mimic visible | mimic diagnosed |
| mimic unresolved | mimic excluded |
| overlap present | disease ranking |
| overlap persistence | probability |
| missing evidence | negative evidence |
| source unavailable | absence of disease |
| granulomatous overlap | sarcoidosis confirmed |
| infection mimic visible | infection diagnosed or excluded |
| malignancy mimic visible | recurrence confirmed or excluded |
| treatment-related overlap | treatment causality |
| exposure-related overlap | occupational causality |
| edema/cardiac mimic visible | edema diagnosed or excluded |
| mixed process | unifying diagnosis |
| unresolved process | negative / normal / reassuring |
| review required | MDD consensus |
| MDD preparation relevant | final MDD conclusion |

Forbidden closure rule:

> Mimic and overlap persistence must never collapse into diagnosis, exclusion, ranking, probability, causality, treatment, reassurance, or consensus.

---

## 29. Allowed Non-Autonomous Mimic / Overlap Phrases

Allowed phrase patterns include:

- “This mimic remains visible.”
- “This alternative remains unresolved.”
- “Overlap persists between these reasoning paths.”
- “The current evidence does not safely close this mimic.”
- “Missing evidence limits stronger language.”
- “Source status should remain visible.”
- “This overlap should be reviewed.”
- “This may be relevant for MDD preparation.”
- “This source supports mimic visibility, not diagnosis.”
- “This case-report source is an edge-case warning, not a general rule.”
- “This treatment-related context is not causality.”
- “This cancer follow-up context does not decide recurrence.”
- “This unresolved state does not equal negative.”

Allowed phrase rule:

> Mimic and overlap phrases must keep reasoning honest without closing the clinical answer.

---

## 30. Future Implementation Requirements

When implemented later, every mimic / overlap object must expose:

| Field | Required |
|---|---|
| persistence_id | true |
| source_ids | true |
| source_roles | true |
| strength_tiers | true |
| linked_pattern_anchor_ids | true |
| linked_distribution_ids | true |
| linked_temporal_ids | true |
| linked_process_ids | true |
| active_mimic_list | true |
| active_overlap_paths | true |
| missing_evidence_prompts | true |
| source_status_prompts | true |
| confidence_limiters | true |
| closure_block_reason | true |
| review_required | true |
| mdd_preparation_relevant | true |
| forbidden_closure_list | true |
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

> Mimic / overlap persistence objects must be source-linked, auditable, missing-evidence-aware, source-status-aware, mimic-preserving, review-required, and closure-blocked before they are used in any UI or export surface.

---

## 31. Current-Phase Authority Envelope

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

> Mimic and overlap persistence improves reasoning safety and clinical usefulness; it does not change current clinical authority.

---

## 32. Prototype File Count Preservation

v0.20.6 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.6 is docs-only mimic / overlap reasoning governance; the materialized prototype skeleton remains unchanged.

---

## 33. Acceptance Criteria

v0.20.6 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.5 dependency listed | true |
| v0.20.4 dependency listed | true |
| v0.20.3 dependency listed | true |
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| core persistence concepts defined | true |
| persistence object shape defined | true |
| persistence families defined | true |
| fibrotic overlap persistence defined | true |
| inflammatory overlap persistence defined | true |
| organizing overlap persistence defined | true |
| airway-centered overlap persistence defined | true |
| granulomatous overlap persistence defined | true |
| nodular overlap persistence defined | true |
| cystic overlap persistence defined | true |
| lymphatic / vascular overlap persistence defined | true |
| treatment-related overlap persistence defined | true |
| exposure-related overlap persistence defined | true |
| infection mimic persistence defined | true |
| malignancy mimic persistence defined | true |
| edema/cardiac mimic persistence defined | true |
| mixed process persistence defined | true |
| unresolved process persistence defined | true |
| pairwise overlap matrix defined | true |
| mimic closure state machine defined | true |
| persistence trigger matrix defined | true |
| release conditions defined as non-autonomous | true |
| overlap severity tiers defined | true |
| source status requirements defined | true |
| forbidden mimic / overlap closure defined | true |
| allowed non-autonomous mimic / overlap phrases defined | true |
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

> v0.20.6 is valid only if mimic and overlap persistence become clinically meaningful while diagnosis, exclusion, ranking, probability, causality, treatment, prognosis, reassurance, and consensus closure remain blocked.

---

## 34. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Mimic / overlap persistence mapping verifies reasoning structure only; it does not certify clinical performance.

---

## 35. Next Step

The next recommended step is:

    v0.20.7 — Missing Evidence / Source Status Logic

v0.20.7 should define source-governed missing evidence and source status logic for:

- pattern evidence missing,
- distribution evidence missing,
- temporal evidence missing,
- clinical context missing,
- exposure context missing,
- treatment context missing,
- cancer context missing,
- infection context missing,
- CTD context missing,
- source not provided,
- source conflict,
- source stale,
- source unverified,
- source out of scope,
- citation manifest linkage,
- source-status display policy.

v0.20.7 must preserve:

- missing evidence not negative evidence,
- source absence not disease absence,
- source conflict not diagnosis,
- source status not authority,
- citation not clinical validation,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no causality authority,
- no patient-facing output,
- no clinical validation,
- no MDD replacement.

Next-step rule:

> v0.20.7 should make missing evidence and source status explicit without turning absence, conflict, or citation into clinical closure.

---

## 36. Governance Statement

This document records v0.20.6 Mimic / Overlap Persistence Matrix.

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

The v0.20.6 discipline is:

> “Create mimic and overlap persistence without creating diagnosis, exclusion, ranking, probability, causality, treatment, prognosis, reassurance, or consensus closure.”

The final v0.20.6 boundary is:

> “The platform can now keep dangerous alternatives visible; it still cannot decide what disease it is.”
