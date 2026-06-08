# ILD Reasoning Platform — Distribution / Temporal Reasoning Map v1

Version: v0.20.4  
Status: distribution_temporal_reasoning_map  
Scope: Source-governed distribution and temporal reasoning map after v0.20.3  
Public Ready: false  
Product Ready: false  
Diagnostic Authority: none_current_phase  
Treatment Authority: none  
Clinically Reviewed: false  
Patient-Facing Use: not_allowed  

---

## 1. Purpose

This document records v0.20.4:

- Distribution / Temporal Reasoning Map.

v0.20.4 follows:

- v0.20.3 — HRCT Pattern Reasoning Anchor Map,
- v0.20.2a — ILD Reference Bibliography / Citation Manifest,
- v0.20.2 — ILD Reasoning Vocabulary Foundation,
- v0.20.1 — ILD Source Corpus / Reference Backbone Intake,
- v0.20.0 — ILD Clinical Reasoning Content Re-Entry Entry Gate,
- checkpoint-v0.19 — Project Status / Roadmap Checkpoint after v0.19,
- v0.19.9 — Static Internal Demo Wiring Structural Seal.

v0.20.3 created HRCT pattern reasoning anchors.

v0.20.4 adds two essential reasoning axes:

1. Distribution.
2. Temporal behavior.

ILD reasoning cannot rely on pattern vocabulary alone.

The same pattern descriptor can carry different reasoning meaning depending on:

- axial distribution,
- craniocaudal distribution,
- subpleural or peribronchovascular distribution,
- focal/diffuse/patchy extent,
- symmetry/asymmetry,
- nodular distribution,
- radiation-field relationship,
- treatment timing,
- exposure latency,
- acute/subacute/chronic course,
- progression/stability/improvement/fluctuation,
- acute-on-chronic behavior.

This document does not diagnose.

It does not assign a disease label.

It does not rank diseases.

It does not calculate probability.

It does not rule out disease.

It does not recommend treatment.

It does not generate a report impression.

It does not generate patient-facing output.

It defines how distribution and temporal behavior may structure non-autonomous clinician-facing reasoning.

The central platform principle remains:

> “It teaches clinicians to read change before naming disease.”

The v0.20.4 principle is:

> “Distribution and time change reasoning; they do not close diagnosis.”

The permanent boundary is:

> “Where and when matter, but neither becomes autonomous clinical authority.”

---

## 2. Required Previous State

v0.20.4 may be valid only if the following previous state is true:

| Previous State | Required |
|---|---|
| v0.20.3 HRCT pattern anchor map exists | true |
| v0.20.2a bibliography / citation manifest exists | true |
| v0.20.2 vocabulary foundation exists | true |
| v0.20.1 source corpus intake exists | true |
| v0.20.0 content re-entry entry gate exists | true |
| checkpoint-v0.19 exists | true |
| v0.19.9 structural seal exists | true |
| clinical reasoning re-entry doctrine preserved | true |
| prototype file count remains 191 | true |
| working tree before v0.20.4 is clean | true |
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

> v0.20.4 may define distribution and temporal reasoning only under source-governed vocabulary, citation manifest, and current non-autonomous authority boundaries.

---

## 3. Source Backbone Applied

v0.20.4 uses the following source backbone roles:

| Source Role | Source IDs | Use in v0.20.4 |
|---|---|---|
| terminology_core | SRC-001 | distribution and temporal descriptor precision |
| classification_core | SRC-002 | ILD family framing, acute/subacute/chronic disease-course framing, clinical-radiologic-pathologic integration |
| consensus_core | SRC-003 | progression and fibrotic behavior reasoning |
| guideline_core | SRC-004, SRC-005, SRC-006 | disease-boundary awareness, diagnostic uncertainty, review requirement |
| review_support | SRC-007, SRC-010 | DI-ILD and radiation-related temporal/mimic context |
| mimic_support | SRC-013, SRC-014, SRC-015, SRC-016, SRC-017, SRC-020 | granulomatous, infectious, malignancy, and oncologic mimic persistence |
| oncology_treatment_risk_support | SRC-008, SRC-009, SRC-010, SRC-011, SRC-014 | drug/radiation/ICI timing and risk-context reasoning |
| occupational_exposure_support | SRC-012 | exposure latency, occupational/environmental history prompts |
| edge_case_support | SRC-018, SRC-019, SRC-021, SRC-022 | mimic traps and red-team scenarios only |
| internal_doctrine | INT-001, INT-002, INT-003, INT-004, INT-005 | authority boundaries and non-autonomous behavior |

Source rule:

> Distribution and temporal reasoning must cite source roles in future implementation and may not use any source outside its admitted role.

---

## 4. Why Distribution and Temporal Reasoning Matter

Distribution matters because the same HRCT pattern can be interpreted differently when it is:

- upper-lung predominant,
- lower-lung predominant,
- subpleural,
- peribronchovascular,
- central,
- peripheral,
- diffuse,
- focal,
- patchy,
- symmetric,
- asymmetric,
- centrilobular,
- perilymphatic,
- random,
- radiation-field-related.

Temporal behavior matters because the same HRCT pattern can be interpreted differently when it is:

- acute,
- subacute,
- chronic,
- progressive,
- stable,
- improving,
- fluctuating,
- acute-on-chronic,
- post-treatment linked,
- exposure-latency linked,
- radiation-field linked,
- recurrent or delayed.

Distribution and temporal reasoning should answer:

- Where is the abnormality?
- Is distribution coherent with the active pattern anchor?
- Is the distribution typical, atypical, conflicting, or incomplete?
- How fast did the abnormality develop?
- Is there progression, stability, improvement, or fluctuation?
- Is there a treatment-linked time course?
- Is there exposure latency?
- Is the temporal relationship sufficient, missing, conflicting, or misleading?
- Which mimics remain visible because of distribution or time-course?

Distribution / temporal principle:

> Distribution and time modify reasoning weight, but they do not produce a final diagnosis, rule-out, probability, treatment decision, or prognosis.

---

## 5. Distribution Reasoning Families

v0.20.4 defines the following distribution reasoning families:

| Distribution Family | Meaning |
|---|---|
| craniocaudal_distribution | upper/mid/lower/apical/basal predominance |
| axial_distribution | subpleural/peripheral/peribronchovascular/central distribution |
| extent_distribution | focal/multifocal/diffuse/patchy distribution |
| symmetry_distribution | symmetric/asymmetric/unilateral/bilateral distribution |
| nodular_distribution | centrilobular/perilymphatic/random/tree-in-bud/subpleural nodular distribution |
| field_related_distribution | radiation-field-related or treatment-field-related distribution |
| airway_distribution | airway-centered, lobular, mosaic, air-trapping-related distribution |
| pleural_associated_distribution | pleural/subpleural/plaque-associated distribution |
| discordant_distribution | distribution conflicts with expected pattern context |
| not_assessable_distribution | distribution cannot be assessed or source is missing |

Distribution family rule:

> Distribution families describe spatial reasoning; they do not diagnose disease.

---

## 6. Temporal Reasoning Families

v0.20.4 defines the following temporal reasoning families:

| Temporal Family | Meaning |
|---|---|
| course_duration | acute/subacute/chronic/unknown course |
| interval_behavior | progressive/stable/improving/fluctuating behavior |
| rate_of_change | rapid/slow/stepwise/indolent progression |
| acute_on_chronic_behavior | acute superimposed change on chronic abnormality |
| treatment_linked_temporal_context | drug/radiation/ICI/oncology-treatment timing context |
| exposure_latency_context | occupational/environmental exposure latency context |
| recurrence_mimic_temporal_context | delayed post-treatment change vs recurrence/progression context |
| temporal_conflict | sources disagree on timing or interval behavior |
| temporal_data_missing | no prior imaging, missing onset, or missing treatment/exposure timeline |

Temporal family rule:

> Temporal families describe time-course reasoning; they do not determine prognosis or management.

---

## 7. Distribution Object Shape

Future implementation may represent distribution reasoning using this shape:

    {
      "distribution_id": "string",
      "distribution_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-001", "SRC-002"],
      "source_roles": ["terminology_core", "classification_core"],
      "linked_pattern_anchor_ids": ["string"],
      "allowed_reasoning_use": "string",
      "spatial_descriptor": "string",
      "distribution_confidence_state": "observed | partial | conflicting | missing | not_assessable",
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

Distribution object rule:

> Every distribution object must carry source IDs, linked pattern anchors, missing-evidence prompts, mimic visibility, and clinical-authority blockers.

---

## 8. Temporal Object Shape

Future implementation may represent temporal reasoning using this shape:

    {
      "temporal_id": "string",
      "temporal_family": "string",
      "display_label": "string",
      "source_ids": ["SRC-002", "SRC-003"],
      "source_roles": ["classification_core", "consensus_core"],
      "linked_pattern_anchor_ids": ["string"],
      "allowed_reasoning_use": "string",
      "time_course_descriptor": "string",
      "interval_behavior": "progressive | stable | improving | fluctuating | unknown",
      "timeline_confidence_state": "observed | partial | conflicting | missing | not_assessable",
      "treatment_or_exposure_link": "none | drug | radiation | ICI | occupational | environmental | unknown",
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

Temporal object rule:

> Every temporal object must carry source IDs, timeline confidence state, missing-evidence prompts, mimic visibility, and clinical-authority blockers.

---

## 9. Craniocaudal Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| upper_lung_predominant | describe upper-zone predominance | sarcoidosis; HP; pneumoconiosis; PLCH; prior infection; apical fibrosis | automatic sarcoidosis/HP/pneumoconiosis diagnosis |
| mid_lung_predominant | describe mid-zone emphasis | HP; sarcoidosis; treatment-related change; mixed ILD | diagnosis |
| lower_lung_predominant | describe basal/lower-zone emphasis | IPF/UIP context; CTD-ILD; fibrotic HP; asbestosis; drug-related fibrosis | automatic UIP/IPF diagnosis |
| apical_predominant | describe apical distribution | prior infection; pneumoconiosis; PLCH; sarcoidosis; pleuroparenchymal fibroelastosis context | diagnosis |
| basal_predominant | describe basal distribution | UIP/IPF context; CTD-ILD; asbestosis; edema; dependent atelectasis | diagnosis |
| diffuse_craniocaudal | describe no clear craniocaudal dominance | inflammatory; treatment-related; infection; edema; diffuse fibrotic disease | severity score |
| craniocaudal_not_assessable | source insufficient | all context-relevant mimics remain visible | negative result |

Craniocaudal rule:

> Craniocaudal predominance changes reasoning context but does not close disease identity.

---

## 10. Axial Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| subpleural_distribution | peripheral/subpleural reasoning | UIP/IPF context; asbestosis; CTD-ILD; OP; dependent change | automatic UIP/IPF |
| peripheral_distribution | peripheral involvement | OP; eosinophilic pneumonia context; infection; infarct; treatment-related injury | diagnosis |
| peribronchovascular_distribution | bronchovascular-axis reasoning | NSIP context; sarcoidosis; PLC; edema; treatment-related change | automatic sarcoidosis/NSIP/PLC |
| central_distribution | central axial emphasis | edema; infection; hemorrhage; treatment-related change | diagnosis |
| subpleural_sparing | axial distribution modifier | NSIP context; CTD-ILD context; HP context | final NSIP/CTD diagnosis |
| random_axial_distribution | no coherent axial pattern | infection; metastases; mixed ILD; technical/source limitation | diagnosis |
| axial_distribution_not_assessable | source insufficient | all context-relevant mimics remain visible | negative result |

Axial rule:

> Axial distribution is a reasoning modifier, not a diagnostic endpoint.

---

## 11. Extent / Focality Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| focal | localized abnormality | infection; malignancy; focal fibrosis; aspiration; radiation-field change | benign/malignant conclusion |
| multifocal | multiple separate regions | infection; OP; metastases; inflammatory disease; treatment-related change | diagnosis |
| diffuse | widespread abnormality | edema; infection; inflammatory ILD; fibrotic ILD; drug/radiation injury | severity or prognosis claim |
| patchy | heterogeneous abnormality | OP; HP; infection; treatment-related injury; fibrotic heterogeneity | final OP/HP label |
| regional | regional pattern | radiation field; aspiration; prior infection; localized fibrosis | diagnosis |
| extent_not_assessable | extent unclear | all relevant mimics remain visible | negative result |

Extent rule:

> Extent and focality describe spread; they do not determine etiology, severity, prognosis, or treatment.

---

## 12. Symmetry Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| symmetric | bilateral balanced involvement | edema; NSIP context; inflammatory ILD; sarcoidosis context | diagnosis |
| asymmetric | unequal involvement | PLC; infection; aspiration; radiation change; malignancy; asymmetric fibrosis | malignancy conclusion |
| unilateral | one-lung predominance | infection; aspiration; radiation; malignancy; unilateral edema; post-surgical context | diagnosis |
| bilateral | both lungs involved | inflammatory; fibrotic; edema; infection; treatment-related | severity claim |
| symmetry_conflicting | sources disagree | all context-relevant mimics remain visible | forced interpretation |
| symmetry_not_assessable | source insufficient | all context-relevant mimics remain visible | negative result |

Symmetry rule:

> Symmetry affects mimic visibility but cannot decide cause.

---

## 13. Nodular Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| centrilobular_distribution | airway-centered/nodular reasoning | HP; infection/bronchiolitis; aspiration; smoking-related disease | final HP/infection |
| perilymphatic_distribution | lymphatic/granulomatous reasoning | sarcoidosis; PLC; pneumoconiosis; lymphoma/sarcoid-like reaction | final sarcoidosis/PLC |
| random_distribution | random nodular reasoning | miliary infection; hematogenous metastases; fungal infection | final metastasis/infection |
| tree_in_bud_distribution | bronchiolar spread reasoning | infection; aspiration; inflammatory bronchiolitis; airway-centered disease | infection diagnosis |
| subpleural_nodularity | pleural/lymphatic context | sarcoidosis; PLC; pneumoconiosis; malignancy | diagnosis |
| nodular_distribution_not_assessable | distribution unclear | infectious, granulomatous, occupational, malignant mimics remain visible | negative result |

Nodular distribution rule:

> Nodule distribution keeps the correct mimics visible; it must not diagnose the mimic.

---

## 14. Field-Related Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| radiation_field_concordant | abnormality appears related to known radiation field | radiation pneumonitis/fibrosis; recurrence; infection; drug/ICI pneumonitis | RP/RILI diagnosis |
| radiation_field_discordant | abnormality extends beyond expected field | infection; drug/ICI pneumonitis; OP-like reaction; malignancy progression; edema | excludes radiation injury |
| treatment_region_related | spatial relation to treatment region | treatment injury; recurrence; infection; post-surgical change | management decision |
| post_surgical_region_related | post-operative regional context | scarring; recurrence; infection; aspiration | diagnosis |
| field_relation_unknown | treatment field unavailable | all treatment and malignancy mimics remain visible | negative evidence |

Field-related rule:

> Treatment-field relationship is a context prompt; it does not prove or exclude treatment injury or recurrence.

---

## 15. Airway Distribution Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| airway_centered_distribution | bronchiolocentric reasoning | HP; infection; aspiration; smoking-related disease; CTD airway disease | final HP diagnosis |
| lobular_distribution | lobular/small-airway context | air-trapping; mosaic attenuation; HP; vascular disease; bronchiolitis | diagnosis |
| mosaic_distribution | mosaic attenuation reasoning | small-airway disease; vascular disease; HP; chronic thromboembolic context | diagnosis |
| air_trapping_distribution | expiratory air-trapping context | HP; asthma/COPD; bronchiolitis; small-airway disease | diagnosis |
| airway_distribution_not_assessable | source lacks expiratory/airway detail | HP/small-airway mimics remain visible | negative result |

Airway distribution rule:

> Airway distribution prompts small-airway and exposure reasoning; it does not close HP, infection, or airway disease.

---

## 16. Course Duration Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| acute_course | recent/short time-course reasoning | infection; edema; hemorrhage; acute exacerbation; drug/radiation injury | triage decision |
| subacute_course | intermediate time-course reasoning | OP; HP; DI-ILD; infection; sarcoidosis; malignancy mimic | diagnosis |
| chronic_course | long-standing process reasoning | fibrotic ILD; occupational ILD; CTD-ILD; sarcoidosis; chronic HP | diagnosis |
| insidious_onset | slow symptom/imaging emergence | fibrotic ILD; occupational/exposure ILD; CTD-ILD; malignancy mimic | prognosis |
| abrupt_onset | sudden change | infection; edema; hemorrhage; acute exacerbation; treatment toxicity | emergency triage |
| course_unknown | time-course missing | all context-relevant mimics remain visible | negative evidence |

Course duration rule:

> Course duration is a reasoning axis; it must not become triage, diagnosis, prognosis, or treatment.

---

## 17. Interval Behavior Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| progressive | worsening over time | PPF context; malignancy; infection; treatment injury; edema; acute exacerbation | treatment decision |
| stable | no meaningful interval change | indolent fibrosis; scarring; stable disease; insufficient interval | reassurance |
| improving | interval improvement | resolving infection; edema; treatment response; fluctuating inflammatory process | disease excluded |
| fluctuating | variable interval behavior | OP; HP; edema; infection; treatment-related injury | diagnosis |
| relapsing | repeated worsening/improvement | HP; sarcoidosis; OP; treatment-related injury; infection | diagnosis |
| interval_behavior_unknown | no prior comparison | all context-relevant mimics remain visible | negative evidence |

Interval behavior rule:

> Interval behavior informs reasoning but does not decide treatment, prognosis, or disease exclusion.

---

## 18. Rate-of-Change Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| rapid_progression | fast worsening context | infection; edema; acute exacerbation; malignancy/PLC; DI-ILD; RP/CIP | automatic triage/prognosis |
| slow_progression | gradual worsening context | fibrotic ILD; occupational ILD; CTD-ILD; chronic HP; malignancy mimic | probability |
| stepwise_progression | episodic worsening | HP; OP; infection; exacerbations; exposure recurrence | diagnosis |
| indolent_behavior | slow/minimal change | chronic fibrosis; sarcoidosis; occupational ILD; indolent malignancy mimic | reassurance |
| rate_unknown | insufficient interval data | all relevant mimics remain visible | negative evidence |

Rate rule:

> Rate of change should trigger review and missing-evidence prompts, not automatic clinical action.

---

## 19. Acute-on-Chronic Behavior Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| acute_on_chronic | new acute abnormality superimposed on chronic pattern | infection; edema; acute exacerbation; hemorrhage; treatment injury; malignancy progression | treatment decision |
| chronic_with_new_ground_glass | chronic fibrotic pattern plus new GGO | infection; edema; exacerbation; DI-ILD; RP/CIP; hemorrhage | diagnosis |
| chronic_with_new_consolidation | chronic pattern plus new consolidation | infection; OP; aspiration; malignancy; treatment injury | diagnosis |
| chronic_with_new_nodules | chronic pattern plus new nodules | infection; sarcoidosis; malignancy; HP; occupational exposure | diagnosis |
| acute_on_chronic_unknown | insufficient prior imaging/context | all relevant mimics remain visible | negative evidence |

Acute-on-chronic rule:

> Acute-on-chronic behavior is a high-value review prompt, not a treatment or diagnosis instruction.

---

## 20. Treatment-Linked Temporal Context Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| drug_temporal_link_possible | timing may relate to medication exposure | DI-ILD; infection; edema; underlying disease; malignancy; radiation injury | drug causality |
| ICI_temporal_link_possible | timing may relate to immune checkpoint therapy | ICI pneumonitis; sarcoid-like reaction; infection; progression; radiation pneumonitis | ICI toxicity diagnosis |
| radiation_temporal_link_possible | timing may relate to radiation | RP/RILI; infection; recurrence/progression; drug/ICI pneumonitis | radiation pneumonitis diagnosis |
| chemotherapy_temporal_link_possible | timing may relate to chemotherapy | DI-ILD; infection; edema; progression | treatment decision |
| post_treatment_change_delayed | delayed treatment-region change | fibrosis; recurrence; infection; post-treatment inflammation | recurrence call |
| treatment_timeline_missing | treatment history unavailable | all treatment-related and non-treatment mimics remain visible | negative evidence |

Treatment-linked rule:

> Post-treatment timing can raise suspicion and review need; it cannot establish causality or management.

---

## 21. Exposure-Latency Context Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| occupational_latency_relevant | exposure latency may matter | pneumoconiosis; beryllium disease; HP; smoking-related disease; idiopathic fibrotic ILD | occupational causality |
| environmental_latency_relevant | environmental/antigen exposure timing may matter | HP; infection; sarcoidosis; exposure-related ILD | causality |
| recurrent_exposure_possible | repeated exposure may matter | HP; occupational ILD; infection; aspiration | diagnosis |
| exposure_timeline_missing | exposure history incomplete | exposure-related and non-exposure mimics remain visible | negative evidence |
| exposure_context_conflicting | exposure data conflict | all relevant mimics remain visible | forced conclusion |

Exposure-latency rule:

> Exposure latency helps ask better questions; it does not prove occupational/environmental causality.

---

## 22. Recurrence-Mimic Temporal Context Map

| Term | Allowed Reasoning Use | Mimics / Alternatives to Keep Visible | Blocked Use |
|---|---|---|---|
| recurrence_mimic_visible | timing/imaging could mimic recurrence | post-treatment fibrosis; infection; edema; malignancy progression; sarcoid-like reaction | recurrence diagnosis |
| delayed_post_radiation_change_possible | delayed radiation-related change possible | recurrence; infection; radiation fibrosis; OP-like change | excludes malignancy |
| cancer_follow_up_temporal_context | cancer surveillance context relevant | recurrence; PLC; sarcoid-like reaction; infection; treatment injury | cancer diagnosis |
| post_treatment_enlarging_opacity_context | enlarging opacity after treatment requires careful review | recurrence; radiation fibrosis; infection; inflammation | malignancy claim |
| recurrence_mimic_context_missing | cancer/treatment timeline missing | recurrence and non-recurrence mimics stay visible | negative evidence |

Recurrence-mimic rule:

> Cancer follow-up timing must preserve both recurrence and non-recurrence mimics until reviewed.

---

## 23. Distribution-to-Pattern Anchor Matrix

| Distribution Family | Pattern Anchors Most Affected |
|---|---|
| craniocaudal_distribution | fibrotic; airway-centered; nodular; granulomatous; exposure-related |
| axial_distribution | fibrotic; inflammatory; organizing; granulomatous; lymphatic/vascular |
| extent_distribution | inflammatory; organizing; treatment-related; mixed; indeterminate |
| symmetry_distribution | inflammatory; lymphatic/vascular; granulomatous; treatment-related |
| nodular_distribution | nodular; granulomatous; airway-centered; lymphatic/vascular; exposure-related |
| field_related_distribution | treatment-related; inflammatory; organizing; lymphatic/vascular |
| airway_distribution | airway-centered; nodular; exposure-related; inflammatory |
| pleural_associated_distribution | fibrotic; exposure-related; cystic; lymphatic/vascular |
| discordant_distribution | mixed; indeterminate; all active anchors |
| not_assessable_distribution | indeterminate; all context-relevant anchors |

Distribution-anchor rule:

> Distribution should activate pattern-specific missing evidence and mimic visibility, not disease closure.

---

## 24. Temporal-to-Pattern Anchor Matrix

| Temporal Family | Pattern Anchors Most Affected |
|---|---|
| course_duration | all pattern anchors |
| interval_behavior | fibrotic; inflammatory; organizing; treatment-related; mixed |
| rate_of_change | fibrotic; inflammatory; lymphatic/vascular; treatment-related; mixed |
| acute_on_chronic_behavior | fibrotic; inflammatory; organizing; treatment-related; mixed |
| treatment_linked_temporal_context | treatment-related; inflammatory; organizing; lymphatic/vascular; granulomatous |
| exposure_latency_context | exposure-related; airway-centered; nodular; fibrotic |
| recurrence_mimic_temporal_context | lymphatic/vascular; treatment-related; nodular; granulomatous |
| temporal_conflict | mixed; indeterminate; all active anchors |
| temporal_data_missing | indeterminate; all context-relevant anchors |

Temporal-anchor rule:

> Temporal behavior should refine pattern reasoning and identify missing evidence, not decide diagnosis, causality, prognosis, or treatment.

---

## 25. Distribution / Temporal Missing Evidence Matrix

| Reasoning Context | Missing Evidence Prompts |
|---|---|
| upper/lower predominance unclear | complete distribution description; slice/region consistency; prior imaging |
| subpleural/peribronchovascular distinction unclear | axial descriptor review; pattern anchor review; source quality |
| focal vs diffuse unclear | extent descriptor; total lung involvement context; technical/source limitation |
| symmetric vs asymmetric unclear | bilateral comparison; region map; prior imaging |
| nodular distribution unclear | centrilobular/perilymphatic/random/tree-in-bud descriptor precision |
| field relationship unclear | radiation field/dose map; treatment records; oncology timeline |
| airway distribution unclear | expiratory imaging; mosaic/air-trapping assessment; airway descriptor precision |
| acute/subacute/chronic unclear | symptom onset; prior imaging; clinician timeline |
| progression unclear | interval comparison; measurement/qualitative change; prior studies |
| stability unclear | adequate interval; prior imaging quality; source consistency |
| improvement unclear | treatment/exposure changes; infection/edema context; follow-up timing |
| acute-on-chronic unclear | chronic baseline; new abnormality timing; superimposed mimic review |
| treatment timing unclear | medication list; start/stop dates; radiation dates; ICI/chemo timeline |
| exposure latency unclear | occupational/environmental history; duration; intensity; latency; recurrence |
| recurrence mimic unclear | cancer status; PET/CT context; biopsy/tissue context; treatment field; follow-up pattern |

Missing evidence rule:

> Distribution and temporal reasoning must reveal what is missing before stronger language is allowed.

---

## 26. Distribution / Temporal Confidence Limiter Matrix

| Limiter | Meaning |
|---|---|
| confidence_limited_by_incomplete_distribution | spatial description incomplete |
| confidence_limited_by_distribution_overlap | distribution fits multiple pattern/disease contexts |
| confidence_limited_by_distribution_conflict | sources disagree on spatial pattern |
| confidence_limited_by_no_prior_imaging | no interval comparison available |
| confidence_limited_by_temporal_uncertainty | onset or course unclear |
| confidence_limited_by_treatment_timeline_uncertainty | drug/radiation/ICI timing incomplete |
| confidence_limited_by_exposure_timeline_uncertainty | occupational/environmental latency incomplete |
| confidence_limited_by_recurrence_mimic | cancer follow-up/treatment change can mimic recurrence |
| confidence_limited_by_acute_on_chronic_overlap | acute change on chronic disease has broad differential |
| confidence_limited_by_current_phase_boundary | current prototype cannot assess real images or patient data |

Confidence limiter rule:

> Confidence limitation must explain uncertainty qualitatively and must not become a numeric probability.

---

## 27. Forbidden Distribution / Temporal Closure

The following conversions are blocked:

| Descriptor | Blocked Conversion |
|---|---|
| upper-lung predominant | sarcoidosis / HP / pneumoconiosis diagnosis |
| lower-lung predominant | UIP / IPF diagnosis |
| subpleural | UIP / IPF diagnosis |
| peribronchovascular | NSIP / sarcoidosis / PLC diagnosis |
| centrilobular | HP / infection diagnosis |
| perilymphatic | sarcoidosis / PLC diagnosis |
| random nodules | metastasis / miliary infection diagnosis |
| radiation-field-related | radiation pneumonitis diagnosis |
| post-treatment timing | treatment causality |
| exposure latency | occupational causality |
| progressive | treatment decision or prognosis |
| stable | reassurance or disease exclusion |
| improving | disease excluded |
| acute-on-chronic | acute exacerbation diagnosis or treatment |
| delayed post-radiation change | recurrence excluded |
| asymmetric septal thickening | lymphangitic carcinomatosis diagnosis |
| temporal missing | negative evidence |
| distribution not assessable | absence of disease |

Forbidden closure rule:

> Distribution and temporal descriptors must never be converted into diagnosis, rule-out, probability, prognosis, causality, treatment, or reassurance in the current phase.

---

## 28. Allowed Non-Autonomous Distribution / Temporal Phrases

Allowed phrase patterns include:

- “Distribution modifies the reasoning context.”
- “Temporal behavior modifies the reasoning context.”
- “This distribution is compatible with more than one reasoning path.”
- “This time-course is compatible with more than one reasoning path.”
- “Mimics remain visible because distribution is nonspecific.”
- “Mimics remain visible because the timeline is incomplete.”
- “Confidence remains limited by missing prior imaging.”
- “Confidence remains limited by incomplete treatment timeline.”
- “Exposure latency should be reviewed.”
- “Treatment timing should be reviewed.”
- “Field relationship should be reviewed.”
- “MDD preparation may be relevant.”
- “This descriptor does not create autonomous final diagnosis.”

Allowed phrase rule:

> Distribution and temporal phrases must make reasoning more precise without closing the clinical answer.

---

## 29. Future Implementation Requirements

When implemented later, every distribution or temporal reasoning object must expose:

| Field | Required |
|---|---|
| object_id | true |
| source_ids | true |
| source_roles | true |
| linked_pattern_anchor_ids | true |
| distribution_or_temporal_family | true |
| descriptor | true |
| confidence_state | true |
| missing_evidence_prompts | true |
| mimic_visibility_list | true |
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

> Distribution and temporal reasoning objects must be source-linked, auditable, missing-evidence-aware, mimic-preserving, and closure-blocked before they are used in any UI or export surface.

---

## 30. Current-Phase Authority Envelope

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

> Distribution and temporal reasoning improve reasoning structure; they do not change current clinical authority.

---

## 31. Prototype File Count Preservation

v0.20.4 does not add files inside the prototype skeleton.

The sealed prototype file count remains:

| Field | Count |
|---|---:|
| Total prototype skeleton files | 191 |

File-count rule:

> v0.20.4 is docs-only distribution and temporal reasoning governance; the materialized prototype skeleton remains unchanged.

---

## 32. Acceptance Criteria

v0.20.4 is accepted only if all are true:

| Criterion | Required State |
|---|---|
| v0.20.3 dependency listed | true |
| v0.20.2a dependency listed | true |
| v0.20.2 dependency listed | true |
| v0.20.1 dependency listed | true |
| source backbone applied | true |
| distribution reasoning families defined | true |
| temporal reasoning families defined | true |
| distribution object shape defined | true |
| temporal object shape defined | true |
| craniocaudal distribution map defined | true |
| axial distribution map defined | true |
| extent/focality distribution map defined | true |
| symmetry distribution map defined | true |
| nodular distribution map defined | true |
| field-related distribution map defined | true |
| airway distribution map defined | true |
| course duration map defined | true |
| interval behavior map defined | true |
| rate-of-change map defined | true |
| acute-on-chronic behavior map defined | true |
| treatment-linked temporal context map defined | true |
| exposure-latency context map defined | true |
| recurrence-mimic temporal context map defined | true |
| distribution-to-pattern anchor matrix defined | true |
| temporal-to-pattern anchor matrix defined | true |
| missing evidence matrix defined | true |
| confidence limiter matrix defined | true |
| forbidden distribution/temporal closure defined | true |
| allowed non-autonomous phrases defined | true |
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

> v0.20.4 is valid only if distribution and temporal reasoning become clinically meaningful while diagnosis, causality, prognosis, treatment, and probability closure remain blocked.

---

## 33. Recommended Local Verification Commands

The following commands may be used for local verification:

    git status --short
    Get-ChildItem prototype -Recurse -File | Measure-Object

Expected count:

    prototype total file count = 191

Verification rule:

> Distribution / temporal mapping verifies reasoning structure only; it does not certify clinical performance.

---

## 34. Next Step

The next recommended step is:

    v0.20.5 — Process-Type Reasoning Map

v0.20.5 should define source-governed process-type reasoning for:

- fibrotic process,
- inflammatory process,
- airway-centered process,
- granulomatous process,
- nodular process,
- cystic process,
- lymphatic / vascular process,
- treatment-related process,
- exposure-related process,
- infection mimic process,
- malignancy mimic process,
- edema/cardiac mimic process,
- mixed process,
- unresolved process.

v0.20.5 must preserve:

- process not diagnosis,
- process not treatment,
- process not causality,
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

> v0.20.5 should make process-type reasoning explicit without turning process labels into disease labels.

---

## 35. Governance Statement

This document records v0.20.4 Distribution / Temporal Reasoning Map.

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

The v0.20.4 discipline is:

> “Create distribution and temporal reasoning without creating diagnosis, causality, prognosis, treatment, or probability closure.”

The final v0.20.4 boundary is:

> “The platform can now reason about where and when; it still cannot decide what disease it is.”
