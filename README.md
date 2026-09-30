# Awesome-Clinical-Decision-Support

## Top Clinical Decision Support (CDS) Platforms Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**
*Focused on Evidence-Based Point-of-Care Reference, Differential Diagnosis & Medication Safety*
**Last updated: September 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Clinical Decision Support (CDS)**. These tools help clinicians access evidence-based medical knowledge, generate differential diagnoses, check drug interactions, and make informed decisions at the point of care.

**Examples** include Wolters Kluwer UpToDate, VisualDx, OpenEvidence, Isabel Healthcare, Elsevier ClinicalKey AI, EBSCO DynaMed, Epocrates, Infermedica, DXplain, and Zynx Health (the category leaders).

**Open-source emphasis**: CDS has a **small but focused open-source ecosystem**. **OneHealth+** is a production-deployed open-source clinical platform for explainable, clinician-in-the-loop brain tumor MRI classification with Docker Compose deployment and a pending-verification workflow . **TriageGuard** provides a multi-modal CDS methodology for emergency department triage with calibrated uncertainty and clinical explainability . Open-source **terminology infrastructure** (SNOMED CT, LOINC, RxNorm) and **drug databases** (DrugBank, OpenFDA) provide foundational building blocks. This section documents these focused solutions honestly.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Wolters Kluwer UpToDate](https://www.wolterskluwer.com/en/solutions/uptodate)**
  The market-leading evidence-based clinical decision support resource, used by care teams worldwide. Content is authored by thousands of clinical experts following a rigorous synthesis process. **UpToDate Enterprise Edition** adds AI-Enhanced Search and an AI-powered Analytics Dashboard for organizational insights .

- **[OpenEvidence](https://www.openevidence.com/)**
  **The most widely used medical AI clinical decision-making tool among U.S. physicians.** Free for all verified U.S. clinicians. **Patient-aware clinical AI**: partnership with Cedars-Sinai integrates patient context from Epic directly into OpenEvidence, enabling answers tailored to prior procedures, comorbidities, medications, and allergies .

- **[Elsevier ClinicalKey AI](https://www.elsevier.com/products/clinicalkey/ai)**
  Clinical decision support tool with a comprehensive full-text knowledge base including major journals. **Traceability**: responses traced to the exact paragraph cited. Content updated frequently. Supports SMART on FHIR and API integration.

- **[EBSCO DynaMed](https://www.dynamed.com/)**
  Evidence-based clinical decision support with **explicit, transparent levels of evidence** (Level 1-3). Updated multiple times daily across 35+ medical specialties. **DynaMedex** bundles DynaMed with Micromedex drug insights and Isabel differential diagnosis generator.

- **[Isabel Healthcare](https://www.isabelhealthcare.com/)**
  **Differential diagnosis (DDx) generator** used worldwide. Peer-reviewed studies show Isabel can increase diagnostic accuracy. **Efficiency advantage**: uses minimal historical data yet achieves strong accuracy, making real-time integration feasible . Can be integrated into EHR or used standalone.

- **[DXplain](http://dxplain.org/)**
  Classic web-based differential diagnosis system developed by Massachusetts General Hospital. **Case Analysis mode**: enter clinical findings to receive ranked disease lists. **Disease Comparison** feature dynamically refreshes Common and Rare disease lists as findings are entered. Knowledge base: 4,000+ term descriptors.

- **[Infermedica](https://infermedica.com/)**
  API-first symptom assessment and triage engine. **Diagnosis endpoint** accepts sex, age, and evidence to return ranked conditions, follow-up questions, and stop flags. **NLP endpoint** parses free-text medical concepts with spelling correction and negation detection.

- **[VisualDx](https://www.visualdx.com/)**
  Visual clinical decision support for dermatology and other specialties. Image-based differential diagnosis with 50,000+ medical images.

- **[Epocrates](https://www.epocrates.com/)**
  Mobile drug reference and clinical decision support. Drug interaction checking, dosing, formulary, and black box warnings . Widely used by clinicians for medication decisions at the point of care.

- **[Zynx Health](https://www.zynxhealth.com/)**
  Evidence-based care plans and order sets for chronic care management and primary care. **Zynx for Primary Care**: point-of-care solution with 100+ care topics and curated order bundles.

## Open-Source GitHub Projects

### Clinical Decision Support Platforms

- **[OneHealth+](https://github.com/)]**
  **Production-deployed open-source clinical platform for explainable, clinician-in-the-loop brain tumor MRI classification.** **Verification-first pipeline**: MRI validator rejects non-medical inputs → classifier → each prediction paired with confidence score and **Grad-CAM overlay** → prediction held in **Pending Doctor Verification** state → clinician records verdict (agree/disagree/uncertain) . **Auditable record**: verdict category, re-run discrepancy, and timestamp persisted for every decision. **Deployment**: Docker Compose with Laravel (web), FastAPI (model), MySQL (db). No GPU required. **Open source** (published in *SoftwareX*).

- **[TriageGuard](https://zenodo.org/records/20445507)**
  **Multi-modal clinical decision support for emergency department triage** . **Methodology**: Multi-modal feature integration (vitals + clinical composite scores + comorbidity profiles + chief complaint NLP); **missingness-as-clinical-signal** encoding; **calibrated uncertainty quantification** (Shannon entropy + ensemble epistemic uncertainty for mandatory human review flagging); **clinical explainability** (feature importance grouped by clinical category). Addresses structural limitations of LLM triage assistants: overconfidence, demographic biases, and black-box outputs .

- **[PIE-Med](https://github.com/picuslab/PIE-Med)**
  **Interpretable Clinical Decision Support System integrating Graph Convolutional Networks (GCNs) and Large Language Models (LLMs).** GCNs generate recommendations based on patients' health data and validated medical knowledge; interpretability algorithms evaluate reasoning; LLM agents translate insights into natural language explanations. **Key design**: LLMs used as auxiliary reasoning agents rather than primary decision-makers, mitigating hallucination and bias risks .

### Differential Diagnosis & Symptom Checkers

- **[Differential Diagnosis Assistant](https://github.com/kennedyraju55/differential-diagnosis-assistant)**
  **HIPAA-friendly medical AI tool powered by local Gemma LLM via Ollama.** **No patient data leaves your machine** — all processing happens locally . Analyzes symptoms and generates differential diagnosis lists with evidence-based reasoning. **Tech stack**: Python, FastAPI, Streamlit, Ollama, Gemma 3. **MIT License** .

- **[LLM Reasoning for Differential Diagnosis](https://github.com/bsenst/llm-reasoning)**
  Experimental application serving open-source Llama-2 model connected to Streamlit interface. User defines custom symptoms or ICD-10 symptoms as input; a two-step chain of prompts outputs a list of differential diagnoses followed by examinations to work up those diagnoses .

- **[DDxT: Differential Diagnosis Using Transformers](https://github.com/MahmudulAlam/Differential-Diagnosis-Using-Transformers)**
  Deep generative transformer models for differential diagnosis. Research implementation for generating differential diagnosis lists from clinical presentations .

### Medication Safety & Drug Interactions

- **[LLM-Drug-Interaction-Checker](https://github.com/AdarshBP/LLM-Drug-Interaction-Checker)**
  **Streamlit-based application using LLMs from Hugging Face to detect potential drug-drug interactions and side effects.** Uses free foundation models including GPT-2, GPT-J, and BioGPT. Simple UI for entering medications and receiving interaction results . **6 stars, 2 forks**.

- **[Drug Interaction Checker (PubChem)](https://github.com/agnivadas/Drug-Interaction-Checker)**
  **Python tool using PubChem's public API to identify interactions between specified drugs.** Fetches interaction data, processes into CSV files, and highlights interactions in the terminal. **Designed for quick exploration of interactions between multiple drugs** .

- **[Drug Interaction Checker (Simple)](https://github.com/mohamedhenady/drug-interaction-checker)**
  **Simple tool to check drug-drug interactions using an open-source database.** Designed as a starting point for pharmacy professionals interested in pharmacy automation. Input two drug names to check for interactions .

- **[CoMed](https://deps.dev/project/github/studentiz%2fcomed)**
  **Comprehensive framework for analyzing drug co-medication risks using Chain-of-Thought (CoT) reasoning and large language models.** Automates searching medical literature, analyzing drug interactions, and generating detailed risk assessment reports. **20 stars, 3 forks** .

### Terminology & Drug Databases

- **[SNOMED CT](https://www.snomed.org/)**
  **The most comprehensive clinical terminology standard.** SNOMED International maintains the terminology used in EHRs worldwide. **Snowstorm** is the official open-source SNOMED CT terminology server. Provides the semantic foundation for CDS logic.

- **[LOINC](https://loinc.org/)**
  **Logical Observation Identifiers Names and Codes** for laboratory and clinical observations. Essential for standardizing lab results and clinical measurements in CDS systems.

- **[RxNorm](https://www.nlm.nih.gov/research/umls/rxnorm/)**
  Normalized names for clinical drugs from the U.S. National Library of Medicine. Maps drug names across systems for interaction checking and medication reconciliation.

- **[DrugBank](https://go.drugbank.com/)**
  **Comprehensive database with pharmacological drug information on drugs and their targets.** Used for drug interaction checking, target identification, and medication safety in CDS applications.

- **[OpenFDA](https://open.fda.gov/)**
  **Public API on reported adverse effects, drug labeling, and drug recall reports.** Data consists of individual reports that must be aggregated for use. Free and open.

### Additional Strong Open-Source Options

- **Clinical AI Platforms**: **OneHealth+** (verification-first, clinician-in-the-loop, Docker) , **PIE-Med** (GCN + LLM, interpretable) .
- **Triage & Emergency**: **TriageGuard** (multi-modal, calibrated uncertainty, explainable) .
- **Differential Diagnosis**: **Differential Diagnosis Assistant** (local Gemma, HIPAA-friendly) , **LLM Reasoning** (Llama-2, symptom-to-DDx) , **DDxT** (transformer-based) .
- **Drug Safety**: **LLM-Drug-Interaction-Checker** (Hugging Face models) , **PubChem Drug Checker** (PubChem API) , **CoMed** (CoT reasoning, 20 stars) .
- **Terminology**: **SNOMED CT** (Snowstorm server), **LOINC**, **RxNorm**.
- **Knowledge Graphs**: **LanDis** (44M+ hereditary disease pairs, interactome-based) .

**Frameworks for building custom systems**: Combine **SNOMED CT** (Snowstorm) for terminology standardization, **RxNorm** and **DrugBank** for medication safety, **OpenFDA** for adverse event data, **OneHealth+** for verification-first clinical AI patterns, and **TriageGuard** methodology for emergency triage CDS. Add **PostgreSQL** for persistence and **Docker** for deployment.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- CDS platforms handle sensitive patient health data; ensure compliance with HIPAA, GDPR, FDA guidance on clinical decision support software, and applicable medical device regulations.
- **Open-source reality**: The open-source ecosystem for clinical decision support is **focused and emerging**. **OneHealth+** provides a production-deployed verification-first clinical AI platform . **TriageGuard** contributes rigorous methodology for emergency triage with calibrated uncertainty . **PIE-Med** demonstrates interpretable CDS combining GCNs and LLMs . **SNOMED CT**, **LOINC**, and **RxNorm** provide essential terminology infrastructure, while **DrugBank** and **OpenFDA** supply drug safety data. However, **commercial platforms** (UpToDate, OpenEvidence, ClinicalKey AI, DynaMed, Isabel) provide **comprehensive evidence-based content libraries, multi-specialty coverage, and enterprise integration** that open-source alternatives cannot match without significant institutional investment. The open-source path is most viable for **specific clinical AI applications, terminology infrastructure, or organizations with strong engineering and clinical informatics capacity**.

---

**Made for clinicians, clinical informaticists, medical librarians, and healthcare AI developers.**
Let's make clinical decision support more open, transparent, and evidence-based.
