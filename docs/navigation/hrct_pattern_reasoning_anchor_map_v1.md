# ILD Reasoning Platform — HRCT Pattern Reasoning Anchor Map v1

Version: v0.20.3  
Status: hrct_pattern_reasoning_anchor_map  
Scope: Source-governed HRCT pattern-level reasoning anchors after v0.20.2a  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.3:

- HRCT Pattern Reasoning Anchor Map.

v0.20.3 follows:

- v0.20.2a — ILD Reference Bibliography / Citation Manifest,
- v0.20.2 — ILD Reasoning Vocabulary Foundation,
- v0.20.1 — ILD Source Corpus / Reference Backbone Intake,
- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.1 admitted the source backbone.

v0.20.2 defined the source-governed vocabulary foundation.

v0.20.2a created the bibliography and citation manifest so that future reasoning decisions remain source-traceable.

v0.20.3 turns the vocabulary layer into HRCT pattern reasoning anchors.

This document does not diagnose.

It does not assign a disease label.

It does not rank diseases.

It does not calculate probability.

It does not rule out disease.

It does not recommend treatment.

It does not generate a report impression.

It does not generate patient-facing output.

It defines how HRCT pattern families may structure non-autonomous clinician-facing reasoning.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.3 principle is:

> “Pattern anchors guide reasoning; they do not name disease.”

The permanent boundary is:

> “HRCT pattern is a reasoning surface, not an autonomous diagnosis.”

---

## 2. Required Previous State

v0.20.3 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.20.2a bibliography / citation manifest exists | true |
| v0.20.2 vocabulary foundation exists | true |
| v0.20.1 source corpus intake exists | true |
| v0.20.0 content re-entry entry gate exists | true |
| checkpoint-v0.19 exists | true |
| v0.19.9 structural seal exists | true |
| clinical reasoning re-entry doctrine preserved | true |
| prototype file count remains 191 | true |
| working tree before v0.20.3 is clean | true |
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

> v0.20.3 may define HRCT pattern anchors only under source-governed vocabulary and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.3 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.3 |
|---|---|---|
| terminology_core | SRC-001 | imaging term precision, descriptor discipline |
| classification_core | SRC-002 | ILD family framing and common radiologic-histopathologic pattern context |
| guideline_core | SRC-004, SRC-005, SRC-006 | disease-boundary awareness, diagnostic uncertainty, review requirement |
| consensus_core | SRC-003 | progression and fibrotic behavior awareness |
| review_support | SRC-007, SRC-010 | DI-ILD and radiation-related pattern/mimic context |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | infection, granulomatous, malignancy, and oncology mimic persistence |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | treatment-related injury and risk-context anchors |
| occupational_exposure_support | SRC-012 | exposure-related reasoning prompts |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | mimic traps and red-team examples only |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | authority boundaries and non-autonomous behavior |

Source rule:

> HRCT pattern anchors must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. HRCT Pattern Anchor Families

v0.20.3 defines the following HRCT pattern anchor families:

| Anchor Family | Meaning |
|---|---|
| fibrotic_pattern_anchor | fibrosis-related structural reasoning |
| inflammatory_pattern_anchor | ground-glass / consolidation / inflammatory-activity reasoning |
| organizing_pattern_anchor | organizing-pneumonia-like reasoning |
| airway_centered_pattern_anchor | small-airway / bronchiolocentric / air-trapping reasoning |
| nodular_pattern_anchor | nodule morphology and distribution reasoning |
| cystic_pattern_anchor | cystic lung disease reasoning |
| granulomatous_pattern_anchor | granulomatous / perilymphatic / lymph node reasoning |
| lymphatic_vascular_mimic_anchor | lymphangitic / vascular / septal mimic reasoning |
| treatment_related_pattern_anchor | drug / radiation / ICI / oncology-treatment context reasoning |
| exposure_related_pattern_anchor | occupational/environmental exposure-linked reasoning |
| mixed_pattern_anchor | multiple active pattern families |
| indeterminate_pattern_anchor | insufficient or conflicting pattern evidence |

Anchor family rule:

> Pattern anchor families organize reasoning domains; they must not become disease outputs.

---

## 5. Anchor Object Shape

Future implementation may represent each anchor using this shape:

    {
      "anchor_id": "string",
      "anchor_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-001", "SRC-002"],
      "source_roles": ["terminology_core", "classification_core"],
      "reasoning_use": "string",
      "key_descriptors": ["string"],
      "distribution_prompts": ["string"],
      "temporal_prompts": ["string"],
      "mimics_to_keep_visible": ["string"],
      "missing_evidence_prompts": ["string"],
      "confidence_limiters": ["string"],
      "review_required": true,
      "diagnosis_closure_allowed": false,
      "rule_out_allowed": false,
      "calibrated_probability_allowed": false,
      "treatment_authority_allowed": false,
      "patient_facing_allowed": false
    }

Object rule:

> Every HRCT pattern anchor must carry source IDs, missing-evidence prompts, mimic visibility, and clinical-authority blockers.

---

## 6. Fibrotic Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_fibrotic_anchor_v1 |
| anchor_family | fibrotic_pattern_anchor |
| source_roles | terminology_core; classification_core; consensus_core; guideline_core |
| primary_sources | SRC-001; SRC-002; SRC-003; SRC-004 |
| reasoning_use | structure reasoning around fibrotic features and progression context |
| key_descriptors | reticulation; architectural distortion; traction bronchiectasis; traction bronchiolectasis; honeycombing; volume loss |
| distribution_prompts | subpleural; basal; heterogeneous; upper-lung; peribronchovascular; diffuse |
| temporal_prompts | chronic; progressive; stable; slow_progression; acute_on_chronic |
| mimics_to_keep_visible | CTD-ILD; fibrotic HP; asbestosis; sarcoidosis; drug-related fibrosis; radiation fibrosis; unclassifiable fibrotic ILD |
| missing_evidence_prompts | prior imaging; distribution detail; exposure history; CTD features/serology; treatment/radiation history; MDD review |
| confidence_limiters | overlap with multiple fibrotic ILD families; missing longitudinal data; missing exposure/CTD context |
| review_required | true |

Allowed language:

- “Fibrotic pattern features are present for reasoning.”
- “Fibrotic behavior requires distribution, temporal, exposure, and CTD context.”
- “Confidence remains limited if longitudinal or exposure evidence is missing.”

Blocked language:

- “This is IPF.”
- “This confirms UIP.”
- “This rules out HP.”
- “This excludes CTD-ILD.”
- “This should be treated with antifibrotic therapy.”

Fibrotic anchor rule:

> Fibrotic pattern can increase the need for structured reasoning, but it cannot autonomously name IPF, UIP, HP, CTD-ILD, asbestosis, or treatment pathway.

---

## 7. Inflammatory Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_inflammatory_anchor_v1 |
| anchor_family | inflammatory_pattern_anchor |
| source_roles | terminology_core; classification_core; review_support; mimic_support |
| primary_sources | SRC-001; SRC-002; SRC-007; SRC-010 |
| reasoning_use | structure reasoning around potentially active inflammatory or alveolar/interstitial opacity patterns |
| key_descriptors | ground-glass opacity; consolidation; crazy paving; diffuse opacity; patchy opacity |
| distribution_prompts | diffuse; patchy; peripheral; peribronchovascular; central; dependent; upper/lower predominance |
| temporal_prompts | acute; subacute; improving; fluctuating; acute_on_chronic; post_treatment_temporal_link |
| mimics_to_keep_visible | infection; edema; organizing pneumonia; DI-ILD; radiation pneumonitis; acute exacerbation; hemorrhage; malignancy-related mimic |
| missing_evidence_prompts | symptoms; oxygenation; fever/infection data; medication history; radiation history; cardiac/volume status; prior imaging |
| confidence_limiters | nonspecific imaging appearance; missing clinical context; overlapping infection/edema/drug/radiation possibilities |
| review_required | true |

Allowed language:

- “Inflammatory-pattern reasoning is active.”
- “Ground-glass/consolidative features are nonspecific and require source context.”
- “Infection, edema, drug, radiation, and inflammatory mimics remain visible.”

Blocked language:

- “This is infection.”
- “This is drug toxicity.”
- “This is radiation pneumonitis.”
- “Steroids should be started.”
- “Edema is excluded.”

Inflammatory anchor rule:

> Inflammatory pattern supports active mimic review; it does not autonomously decide cause or treatment.

---

## 8. Organizing Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_organizing_anchor_v1 |
| anchor_family | organizing_pattern_anchor |
| source_roles | terminology_core; classification_core; review_support; oncology_treatment_risk_support |
| primary_sources | SRC-001; SRC-002; SRC-007; SRC-008 |
| reasoning_use | structure reasoning around organizing-pneumonia-like distribution and morphology |
| key_descriptors | peripheral consolidation; perilobular opacity; band-like consolidation; reversed halo context; air bronchograms |
| distribution_prompts | peripheral; bronchocentric; patchy; migratory; lower-lung; peribronchovascular |
| temporal_prompts | subacute; fluctuating; improving; post_treatment_temporal_link |
| mimics_to_keep_visible | cryptogenic organizing pneumonia; CTD-related organizing pneumonia; DI-ILD; radiation-related OP; infection; malignancy-associated OP-like pattern |
| missing_evidence_prompts | drug exposure; radiation field; CTD context; infection exclusion context; prior imaging; symptoms |
| confidence_limiters | organizing pattern can be secondary to multiple contexts; treatment-related and infection mimics may overlap |
| review_required | true |

Allowed language:

- “Organizing-pattern reasoning is active.”
- “This pattern can be seen in multiple clinical contexts.”
- “Secondary causes and treatment-related context remain visible.”

Blocked language:

- “This is cryptogenic organizing pneumonia.”
- “This rules out infection.”
- “This confirms DI-ILD.”
- “Steroids are indicated.”

Organizing anchor rule:

> Organizing pattern is a morphology-and-context anchor, not a final OP diagnosis.

---

## 9. Airway-Centered Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_airway_centered_anchor_v1 |
| anchor_family | airway_centered_pattern_anchor |
| source_roles | terminology_core; classification_core; occupational_exposure_support; mimic_support |
| primary_sources | SRC-001; SRC-002; SRC-012 |
| reasoning_use | structure reasoning around small-airways, bronchiolocentric, mosaic attenuation, air-trapping, and centrilobular context |
| key_descriptors | centrilobular nodules; tree-in-bud; mosaic attenuation; air-trapping; bronchial wall thickening; bronchiolectasis |
| distribution_prompts | centrilobular; diffuse; upper/mid/lower; patchy; lobular; airway-centered |
| temporal_prompts | subacute; chronic; exposure_latency_relevant; fluctuating |
| mimics_to_keep_visible | HP; infection/bronchiolitis; smoking-related bronchiolitis; occupational exposure-related disease; CTD airway disease; aspiration |
| missing_evidence_prompts | expiratory imaging; exposure history; antigen history; smoking history; infection context; occupational context |
| confidence_limiters | airway-centered findings overlap HP, infection, smoking, aspiration, and exposure-related processes |
| review_required | true |

Allowed language:

- “Airway-centered reasoning is active.”
- “Exposure and expiratory imaging context are relevant.”
- “HP-like and infection-like mimics remain visible.”

Blocked language:

- “This is hypersensitivity pneumonitis.”
- “This rules out infection.”
- “This proves occupational causality.”
- “Exposure caused the disease.”

Airway-centered anchor rule:

> Airway-centered pattern prompts exposure and small-airway reasoning; it does not autonomously diagnose HP, infection, aspiration, or occupational causality.

---

## 10. Nodular Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_nodular_anchor_v1 |
| anchor_family | nodular_pattern_anchor |
| source_roles | terminology_core; classification_core; mimic_support; edge_case_support |
| primary_sources | SRC-001; SRC-002; SRC-006; SRC-013; SRC-018; SRC-020 |
| reasoning_use | structure reasoning around nodule morphology and distribution |
| key_descriptors | micronodules; centrilobular nodules; perilymphatic nodules; random nodules; tree-in-bud nodules; subpleural nodularity |
| distribution_prompts | perilymphatic; centrilobular; random; upper-lung; peribronchovascular; subpleural |
| temporal_prompts | acute; subacute; chronic; progressive; stable |
| mimics_to_keep_visible | sarcoidosis; infection; miliary infection; pneumoconiosis; lymphangitic carcinomatosis; metastases; HP |
| missing_evidence_prompts | immune status; infectious workup context; exposure history; cancer history; lymph node pattern; tissue/pathology context |
| confidence_limiters | nodular patterns have broad infectious, granulomatous, occupational, and malignant mimics |
| review_required | true |

Allowed language:

- “Nodular-pattern reasoning is active.”
- “Nodule distribution should be interpreted with source context.”
- “Granulomatous, infectious, exposure-related, and malignancy mimics remain visible.”

Blocked language:

- “This confirms sarcoidosis.”
- “This rules out malignancy.”
- “This is metastatic disease.”
- “This excludes infection.”

Nodular anchor rule:

> Nodular pattern requires distribution and mimic reasoning; it cannot autonomously diagnose sarcoidosis, infection, pneumoconiosis, HP, or malignancy.

---

## 11. Cystic Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_cystic_anchor_v1 |
| anchor_family | cystic_pattern_anchor |
| source_roles | terminology_core; classification_core; mimic_support |
| primary_sources | SRC-001; SRC-002 |
| reasoning_use | structure reasoning around cystic lung pattern descriptors and distribution |
| key_descriptors | cysts; diffuse cystic change; clustered cysts; thin-walled cysts; honeycombing-like cystic spaces; emphysema mimic |
| distribution_prompts | diffuse; upper-lung; lower-lung; perivascular; subpleural; random; basal |
| temporal_prompts | chronic; progressive; stable |
| mimics_to_keep_visible | LAM; PLCH; emphysema; honeycombing; cystic metastases; infection-related cystic change; autoimmune cystic lung disease |
| missing_evidence_prompts | age/sex context; smoking history; associated nodules; extrapulmonary context; prior imaging; CT descriptor precision |
| confidence_limiters | cystic descriptors overlap emphysema, honeycombing, and cystic ILD entities |
| review_required | true |

Allowed language:

- “Cystic-pattern reasoning is active.”
- “Descriptor precision is required to separate cystic change from emphysema or honeycombing-like spaces.”
- “Disease-label closure is not allowed.”

Blocked language:

- “This is LAM.”
- “This is PLCH.”
- “This confirms honeycombing.”
- “This excludes emphysema.”

Cystic anchor rule:

> Cystic pattern anchors descriptor precision and mimic visibility; it does not assign cystic lung disease labels.

---

## 12. Granulomatous Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_granulomatous_anchor_v1 |
| anchor_family | granulomatous_pattern_anchor |
| source_roles | guideline_core; mimic_support; edge_case_support; terminology_core |
| primary_sources | SRC-001; SRC-006; SRC-013; SRC-018; SRC-019; SRC-022 |
| reasoning_use | structure reasoning around granulomatous mimic visibility and sarcoidosis-like patterns |
| key_descriptors | perilymphatic nodules; hilar/mediastinal lymphadenopathy context; upper-lung nodules; granulomatous mimic context |
| distribution_prompts | perilymphatic; peribronchovascular; upper-lung; nodal; symmetric/asymmetric |
| temporal_prompts | acute; subacute; chronic; progressive; treatment_refractory |
| mimics_to_keep_visible | sarcoidosis; TB; atypical mycobacterial infection; histoplasmosis; coccidioidomycosis; beryllium disease; sarcoid-like reaction; lymphoma |
| missing_evidence_prompts | tissue/pathology context; infection testing context; exposure history; immune status; cancer history; treatment history |
| confidence_limiters | granulomas are not uniquely specific; alternative granulomatous causes must remain visible |
| review_required | true |

Allowed language:

- “Granulomatous-pattern reasoning is active.”
- “Alternative granulomatous causes remain visible.”
- “Histology and exclusion context may be relevant for review.”

Blocked language:

- “This confirms sarcoidosis.”
- “This excludes TB.”
- “This excludes fungal infection.”
- “This is sarcoid-like reaction.”
- “This rules out lymphoma.”

Granulomatous anchor rule:

> Granulomatous pattern exists to preserve alternative causes and review requirements, not to autonomously diagnose sarcoidosis.

---

## 13. Lymphatic / Vascular Mimic Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_lymphatic_vascular_mimic_anchor_v1 |
| anchor_family | lymphatic_vascular_mimic_anchor |
| source_roles | terminology_core; mimic_support; oncology_treatment_risk_support; edge_case_support |
| primary_sources | SRC-001; SRC-020; SRC-021; SRC-015; SRC-016 |
| reasoning_use | structure reasoning around septal/peribronchovascular/lymphatic or vascular mimic patterns |
| key_descriptors | interlobular septal thickening; peribronchovascular thickening; subpleural nodularity; lymphatic distribution; asymmetric interstitial thickening |
| distribution_prompts | peribronchovascular; septal; subpleural; asymmetric; unilateral; bilateral; peritumoral |
| temporal_prompts | progressive; rapid_progression; cancer_follow_up_context; treatment_context |
| mimics_to_keep_visible | pulmonary lymphangitic carcinomatosis; sarcoidosis; sarcoid-like reaction; edema; infection; radiation/drug-related injury |
| missing_evidence_prompts | cancer history; PET/CT context; tissue confirmation context; edema/cardiac context; infection context; treatment history |
| confidence_limiters | septal and lymphatic patterns can overlap malignancy, edema, sarcoid-like, infection, and treatment-related contexts |
| review_required | true |

Allowed language:

- “Lymphatic/vascular mimic reasoning is active.”
- “Malignancy, edema, sarcoid-like, infection, and treatment-related mimics remain visible.”
- “Confidence remains limited without clinical, temporal, and source context.”

Blocked language:

- “This is lymphangitic carcinomatosis.”
- “This rules out edema.”
- “This confirms recurrence.”
- “This excludes malignancy.”

Lymphatic / vascular mimic rule:

> Lymphatic or vascular mimic pattern should raise visibility and review needs, not produce autonomous cancer or non-cancer conclusions.

---

## 14. Treatment-Related Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_treatment_related_anchor_v1 |
| anchor_family | treatment_related_pattern_anchor |
| source_roles | oncology_treatment_risk_support; review_support; mimic_support |
| primary_sources | SRC-007; SRC-008; SRC-009; SRC-010; SRC-011; SRC-014 |
| reasoning_use | structure reasoning around drug, radiation, immune-checkpoint, and oncology-treatment-related lung injury contexts |
| key_descriptors | ground-glass opacity; consolidation; organizing pattern; diffuse opacity; in-field change; out-of-field change; fibrosis; pneumonitis-like pattern |
| distribution_prompts | radiation-field-related; diffuse; patchy; bilateral; unilateral; peribronchovascular; peripheral |
| temporal_prompts | post_treatment_temporal_link; acute; subacute; chronic; delayed; radiation_pneumonitis_window; radiation_fibrosis_window |
| mimics_to_keep_visible | infection; edema; malignancy progression; lymphangitic carcinomatosis; DI-ILD; RILI/RP; ICI pneumonitis; sarcoid-like reaction |
| missing_evidence_prompts | medication timeline; radiation field/dose context; immune therapy history; cancer status; infection evaluation context; baseline ILD context |
| confidence_limiters | treatment-related injury is nonspecific and requires exclusion of alternative causes |
| review_required | true |

Allowed language:

- “Treatment-related pattern context is relevant.”
- “Temporal association and alternative-cause visibility are required.”
- “Oncology/pulmonology review may be relevant.”

Blocked language:

- “Stop the drug.”
- “Start corticosteroids.”
- “This is radiation pneumonitis.”
- “This is checkpoint inhibitor pneumonitis.”
- “Cancer progression is excluded.”

Treatment-related anchor rule:

> Treatment-related pattern anchors context and risk; it does not decide therapy, causality, or cancer status.

---

## 15. Exposure-Related Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_exposure_related_anchor_v1 |
| anchor_family | exposure_related_pattern_anchor |
| source_roles | occupational_exposure_support; classification_core; terminology_core |
| primary_sources | SRC-012; SRC-002; SRC-001 |
| reasoning_use | structure reasoning around occupational/environmental exposure relevance |
| key_descriptors | pneumoconiosis-like nodularity; upper-lung fibrosis; pleural plaque context; airway-centered context; HP-like context |
| distribution_prompts | upper-lung; diffuse; centrilobular; perilymphatic; subpleural; pleural-associated |
| temporal_prompts | exposure_latency_relevant; chronic; progressive; stable |
| mimics_to_keep_visible | asbestosis; silicosis; coal workers pneumoconiosis; beryllium disease; HP; sarcoidosis; smoking-related disease |
| missing_evidence_prompts | occupational history; environmental exposure; duration/latency; protective equipment; antigen source; smoking history |
| confidence_limiters | exposure history may be incomplete; imaging overlap exists with idiopathic, granulomatous, and CTD-related ILD |
| review_required | true |

Allowed language:

- “Exposure-related reasoning is active.”
- “Occupational/environmental history is a missing-evidence category.”
- “Exposure context may be relevant for MDD preparation.”

Blocked language:

- “This is occupational ILD.”
- “Workplace exposure caused this.”
- “This proves compensation-related causality.”
- “This rules out idiopathic disease.”

Exposure-related anchor rule:

> Exposure-related pattern prompts better questions; it does not establish occupational causality.

---

## 16. Mixed Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_mixed_anchor_v1 |
| anchor_family | mixed_pattern_anchor |
| source_roles | terminology_core; classification_core; guideline_core; internal_doctrine |
| primary_sources | SRC-001; SRC-002; SRC-006; INT-005 |
| reasoning_use | structure reasoning when more than one pattern family is active |
| key_descriptors | mixed_pattern; fibrotic-plus-inflammatory; fibrotic-plus-airway-centered; nodular-plus-lymphatic; organizing-plus-treatment-related |
| distribution_prompts | multi-distribution; discordant distribution; heterogeneous; regional mismatch |
| temporal_prompts | acute_on_chronic; progressive_with_superimposed_change; fluctuating; mixed_temporal_behavior |
| mimics_to_keep_visible | acute exacerbation; infection; edema; drug/radiation injury; CTD-ILD; HP; malignancy; sarcoidosis |
| missing_evidence_prompts | prior imaging; clinical timeline; exposure history; treatment history; source conflict; multidisciplinary review |
| confidence_limiters | mixed patterns increase uncertainty and premature closure risk |
| review_required | true |

Allowed language:

- “Mixed-pattern reasoning is active.”
- “Multiple pattern families remain active.”
- “Closure is unsafe without resolving the dominant process, temporal behavior, and mimics.”

Blocked language:

- “The unifying diagnosis is...”
- “This is definitely mixed ILD.”
- “The dominant disease is...”
- “Other causes are excluded.”

Mixed anchor rule:

> Mixed pattern increases the need for structured reasoning; it must not force a unifying diagnosis.

---

## 17. Indeterminate Pattern Anchor

| Field | Definition |
|---|---|
| anchor_id | hrct_pattern_indeterminate_anchor_v1 |
| anchor_family | indeterminate_pattern_anchor |
| source_roles | internal_doctrine; terminology_core; classification_core; guideline_core |
| primary_sources | INT-005; SRC-001; SRC-002; SRC-006 |
| reasoning_use | preserve uncertainty when pattern evidence is insufficient, conflicting, or not assessable |
| key_descriptors | indeterminate_pattern; not_assessable; source_unavailable; evidence_missing; evidence_conflicting |
| distribution_prompts | distribution_not_assessable; incomplete_distribution; source_conflict |
| temporal_prompts | temporal_data_missing; no_prior_imaging; uncertain_timing |
| mimics_to_keep_visible | all unresolved mimics relevant to context |
| missing_evidence_prompts | adequate HRCT descriptors; prior imaging; clinical context; exposure/drug/radiation/CTD/infection/cancer context; review |
| confidence_limiters | missing source; incomplete pattern description; unresolved mimics; lack of longitudinal data |
| review_required | true |

Allowed language:

- “Pattern remains indeterminate.”
- “Evidence is insufficient for stronger pattern language.”
- “Missing evidence should be visible before stronger reasoning.”

Blocked language:

- “No disease.”
- “Normal.”
- “Diagnosis cannot be made ever.”
- “This rules out ILD.”
- “Indeterminate equals negative.”

Indeterminate anchor rule:

> Indeterminate means “insufficient for closure,” not “absence of disease.”

---

## 18. Pattern-to-Mimic Visibility Matrix

| Pattern Anchor | Mimics / Alternatives That Must Stay Visible |
|---|---|
| fibrotic_pattern_anchor | CTD-ILD; fibrotic HP; asbestosis; sarcoidosis; drug/radiation fibrosis; unclassifiable fibrotic ILD |
| inflammatory_pattern_anchor | infection; edema; DI-ILD; RP/RILI; OP; acute exacerbation; hemorrhage; malignancy mimic |
| organizing_pattern_anchor | COP; secondary OP; CTD-OP; DI-ILD; radiation-related OP; infection; malignancy-associated OP-like pattern |
| airway_centered_pattern_anchor | HP; infectious bronchiolitis; smoking-related bronchiolitis; aspiration; occupational/environmental exposure |
| nodular_pattern_anchor | sarcoidosis; infection; pneumoconiosis; HP; metastases; lymphangitic carcinomatosis |
| cystic_pattern_anchor | LAM; PLCH; emphysema; honeycombing-like spaces; cystic metastases; autoimmune cystic lung disease |
| granulomatous_pattern_anchor | sarcoidosis; TB; atypical mycobacteria; fungal infection; beryllium disease; lymphoma; sarcoid-like reaction |
| lymphatic_vascular_mimic_anchor | PLC; edema; sarcoid-like reaction; infection; recurrence/progression; radiation/drug injury |
| treatment_related_pattern_anchor | infection; edema; malignancy progression; DI-ILD; RP/RILI; ICI pneumonitis; sarcoid-like reaction |
| exposure_related_pattern_anchor | pneumoconiosis; HP; beryllium disease; sarcoidosis; smoking-related disease |
| mixed_pattern_anchor | all active pattern-family mimics |
| indeterminate_pattern_anchor | all context-relevant unresolved mimics |

Mimic matrix rule:

> The pattern anchor must make dangerous mimics harder to forget, not easier to dismiss.

---

## 19. Pattern-to-Missing Evidence Matrix

| Pattern Anchor | Missing Evidence Prompts |
|---|---|
| fibrotic_pattern_anchor | prior imaging; distribution detail; exposure history; CTD context; treatment/radiation history |
| inflammatory_pattern_anchor | symptoms; infection data; cardiac/volume status; medication timeline; treatment/radiation history |
| organizing_pattern_anchor | drug/radiation context; infection context; CTD context; prior imaging |
| airway_centered_pattern_anchor | expiratory imaging; antigen/exposure history; infection context; smoking/aspiration context |
| nodular_pattern_anchor | immune status; infection workup; exposure history; cancer history; lymph node/tissue context |
| cystic_pattern_anchor | smoking; age/sex context; associated nodules; emphysema vs cyst vs honeycombing precision |
| granulomatous_pattern_anchor | tissue/pathology context; infection testing; exposure history; cancer history; treatment history |
| lymphatic_vascular_mimic_anchor | cancer history; PET/CT context; tissue confirmation context; edema/cardiac context |
| treatment_related_pattern_anchor | drug list; dose/timing; radiation field/dose; ICI history; baseline ILD; infection/cancer context |
| exposure_related_pattern_anchor | occupational/environmental exposure; latency; duration; antigen source; protective equipment |
| mixed_pattern_anchor | prior imaging; clinical timeline; source conflict; dominant process; MDD review |
| indeterminate_pattern_anchor | adequate descriptors; prior imaging; clinical and exposure/treatment context |

Missing evidence rule:

> Pattern reasoning must name what is missing before it can safely become stronger.

---

## 20. Pattern-to-Confidence Limiter Matrix

| Pattern Anchor | Confidence Limiter |
|---|---|
| fibrotic_pattern_anchor | fibrosis overlaps multiple ILD families; progression data may be missing |
| inflammatory_pattern_anchor | ground-glass/consolidation is nonspecific; infection/edema/treatment-related causes overlap |
| organizing_pattern_anchor | organizing morphology may be primary or secondary |
| airway_centered_pattern_anchor | small-airway findings overlap HP, infection, aspiration, smoking, exposure |
| nodular_pattern_anchor | nodules overlap granulomatous, infectious, occupational, malignant, and HP contexts |
| cystic_pattern_anchor | cystic descriptors overlap emphysema and honeycombing-like spaces |
| granulomatous_pattern_anchor | granulomas and granulomatous imaging patterns are not uniquely specific |
| lymphatic_vascular_mimic_anchor | septal/peribronchovascular findings overlap PLC, edema, sarcoid-like, infection, and treatment-related injury |
| treatment_related_pattern_anchor | treatment-related lung injury is nonspecific and requires exclusion of alternatives |
| exposure_related_pattern_anchor | exposure history may be incomplete and causality cannot be inferred from imaging alone |
| mixed_pattern_anchor | multiple active pattern families increase premature closure risk |
| indeterminate_pattern_anchor | insufficient or conflicting evidence prevents stronger pattern language |

Confidence limiter rule:

> Each pattern anchor must explain why confidence remains limited without producing a numeric score.

---

## 21. Forbidden Pattern Closure

The following pattern-to-closure conversions are blocked:

| Pattern Statement | Blocked Conversion |
|---|---|
| fibrotic pattern | IPF / UIP / CTD-ILD final diagnosis |
| inflammatory pattern | infection / DI-ILD / RP / edema final diagnosis |
| organizing pattern | COP / OP final diagnosis |
| airway-centered pattern | HP / infectious bronchiolitis final diagnosis |
| nodular pattern | sarcoidosis / metastasis / infection final diagnosis |
| cystic pattern | LAM / PLCH / emphysema / honeycombing final diagnosis |
| granulomatous pattern | sarcoidosis / TB / fungal disease / lymphoma final diagnosis |
| lymphatic/vascular pattern | lymphangitic carcinomatosis / edema / recurrence final diagnosis |
| treatment-related context | drug causality / radiation causality / ICI pneumonitis final diagnosis |
| exposure-related context | occupational causality final diagnosis |
| mixed pattern | forced unifying diagnosis |
| indeterminate pattern | negative result / disease absence |

Forbidden closure rule:

> Pattern-to-disease conversion is blocked in the current phase.

---

## 22. Allowed Non-Autonomous Pattern Phrases

Allowed phrase patterns include:

- “Pattern-level reasoning is active.”
- “This descriptor supports reasoning toward a pattern family.”
- “This descriptor is compatible with more than one context.”
- “Distribution modifies the reasoning but does not close diagnosis.”
- “Temporal behavior should be reviewed before stronger language.”
- “Mimics remain visible.”
- “Missing evidence limits confidence.”
- “MDD preparation may be relevant.”
- “This pattern anchor does not create autonomous final diagnosis.”

Allowed phrase rule:

> Pattern phrases must preserve reasoning direction without clinical closure.

---

## 23. Future Implementation Requirements

When implemented later, every HRCT pattern anchor must expose:

| Field | Required |
|---|---|
| anchor_id | true |
| source_ids | true |
| source_roles | true |
| pattern_family | true |
| descriptor_list | true |
| distribution_prompts | true |
| temporal_prompts | true |
| mimic_visibility_list | true |
| missing_evidence_prompts | true |
| confidence_limiters | true |
| review_required | true |
| forbidden_closure_list | true |
| citation_manifest_link | true |
| audit_trace_enabled | true |
| diagnosis_closure_allowed | false |
| rule_out_allowed | false |
| calibrated_probability_allowed | false |
| treatment_authority_allowed | false |
| patient_facing_allowed | false |

Implementation rule:

> Pattern anchors must be auditable, source-linked, and closure-blocked before they are used in any UI or export surface.

---

## 24. Current-Phase Authority Envelope

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

> HRCT pattern anchors improve reasoning structure; they do not change current clinical authority.

---

## 25. Prototype File Count Preservation

v0.20.3 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.3 is docs-only pattern reasoning governance; the materialized prototype skeleton remains unchanged.

---

## 26. Acceptance Criteria

v0.20.3 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| HRCT pattern anchor families defined | true |
| anchor object shape defined | true |
| fibrotic pattern anchor defined | true |
| inflammatory pattern anchor defined | true |
| organizing pattern anchor defined | true |
| airway-centered pattern anchor defined | true |
| nodular pattern anchor defined | true |
| cystic pattern anchor defined | true |
| granulomatous pattern anchor defined | true |
| lymphatic/vascular mimic anchor defined | true |
| treatment-related pattern anchor defined | true |
| exposure-related pattern anchor defined | true |
| mixed pattern anchor defined | true |
| indeterminate pattern anchor defined | true |
| pattern-to-mimic visibility matrix defined | true |
| pattern-to-missing evidence matrix defined | true |
| pattern-to-confidence limiter matrix defined | true |
| forbidden pattern closure defined | true |
| allowed non-autonomous pattern phrases defined | true |
| future implementation requirements defined | true |
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

> v0.20.3 is valid only if HRCT pattern reasoning becomes clinically meaningful while pattern-to-disease closure remains blocked.

---

## 27. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Pattern anchor mapping verifies reasoning structure only; it does not certify clinical performance.

---

## 28. Next Step

The next recommended step is:

    v0.20.4 — Distribution / Temporal Reasoning Map

v0.20.4 should define source-governed distribution and temporal reasoning logic for:

- axial distribution,
- craniocaudal distribution,
- central/peripheral distribution,
- subpleural/peribronchovascular distribution,
- nodular distribution,
- focal/diffuse distribution,
- acute/subacute/chronic time-course,
- progressive/stable/improving/fluctuating behavior,
- acute-on-chronic behavior,
- treatment-linked temporal context,
- exposure-latency context.

v0.20.4 must preserve:

- distribution not diagnosis,
- temporal behavior not prognosis,
- progression not treatment decision,
- exposure latency not causality,
- post-treatment timing not causality,
- no autonomous final diagnosis,
- no autonomous rule-out,
- no calibrated probability,
- no treatment authority,
- no patient-facing output,
- no clinical validation,
- no MDD replacement.

Next-step rule:

> v0.20.4 should make distribution and temporal behavior reasoned, not decisive.

---

## 29. Governance Statement

This document records v0.20.3 HRCT Pattern Reasoning Anchor Map.

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

The v0.20.3 discipline is:

> “Create HRCT pattern reasoning anchors without creating pattern-to-disease closure.”

The final v0.20.3 boundary is:

> “The platform can now structure HRCT pattern reasoning; it still cannot diagnose.”
