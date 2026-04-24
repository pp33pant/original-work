# Original Work: AI Deployment, Decision Workflows, and Research Systems

This repository is a landing page for selected professional and academic projects viewed through an applied AI and Forward Deployment Engineer lens.

The common thread across these projects is not one model family or one research domain. It is end-to-end delivery: taking ambiguous stakeholder problems, defining the right system boundary, building human-in-the-loop workflows, validating the outputs, and shipping an inspectable surface that other people can use.

If you arrived here from my resume, the fastest way to read this page is:

1. Start with [Professional Experience](#professional-experience).
2. Open the public notebooks linked under Sunflower and Causal Representation Learning.
3. Use the academic sections to see the workflow-design and validation layer behind the research work.

## What This Page Is For

This README is not a full CV and not a dump of raw research notes. It is a project portfolio page organized around two buckets of work:

1. Professional experience: customer-facing deployment, decision workflows, and operator-aware AI systems.
2. Academic experience: multimodal research systems, hybrid data integration, causal inference, and reproducibility-oriented delivery.

## What I Tend To Deliver End To End

- Discovery with operators, stakeholders, or domain users rather than model-first prototyping.
- Workflow and system-boundary design over messy structured and unstructured data.
- Human-in-the-loop AI systems with explicit review, exception handling, and release constraints.
- Validation, robustness, and audit surfaces strong enough for downstream users to trust the output.
- Public or reusable artifacts such as notebooks, codebooks, rerun wrappers, and documentation.

## Portfolio Map

| Area | Project | Delivery focus | Engineering focus | Public artifact |
| --- | --- | --- | --- | --- |
| Professional | Fairlane Group / Libertas Funding | AI-assisted underwriting workflow redesign | LangChain / LangGraph, Python, SQL, Redshift-backed workflows | Confidential summary only |
| Professional | Sunflower AI Labs | Creator strategy and sponsor-matching workflow | Chunking, embeddings, clustering, retrieval, LLM-grounded theme labeling | [topic_themes.ipynb](topic_themes.ipynb) |
| Academic | Multimodal Causal Workflow for Oral Histories | Multimodal causal research system | Transcript/audio/video retrieval, fusion design, codebooks, rerun wrappers | Summary here |
| Academic | University of Oxford / Said Business School | Hybrid structured-textual analysis workflow | API ingestion, entity reconciliation, timing alignment, DML validation | [Related paper](https://doi.org/10.1007/s11577-025-01045-6) |
| Academic | Causal Representation Learning | Representation learning inside causal estimation | Transformer embeddings, dimensionality reduction, cross-fitted DML, balance-aware extension | [causal_representation_learning.ipynb](causal_representation_learning.ipynb) |
| Academic | Harvard University and Brown University | Validation-first observational workflows | Doubly robust ML, multilevel models, demographic simulation | [Related paper](https://journals.sagepub.com/eprint/JMTX4WJKGRIHIUIGVPKS/full) |

## Professional Experience

### Fairlane Group / Libertas Funding

**Role:** Data Scientist / AI Engineer  
**Period:** Mar 2025 - Sep 2025  
**Setting:** Customer-facing AI deployment with Libertas Funding underwriting operations

#### Context

Libertas Funding's underwriting process relied on heavy manual verification across borrower diligence, bank-statement review, front-end intake, Redshift-backed data storage, and downstream risk review. The main problem was not just predictive modeling. It was that key evidence capture and review logic were still trapped inside manual operating steps.

#### End-to-end delivery

1. Embedded with leadership, processors, and underwriters in the live workflow to identify the highest-friction verification and data-entry bottlenecks.
2. Translated those bottlenecks into a scoped orchestration problem rather than a vague "apply AI to underwriting" prompt.
3. Designed an assistive workflow that fit into existing review practices instead of pretending the lending decision could be fully automated.
4. Moved the solution from pilot and stakeholder demo to authorized full-sample rollout inside a next-generation underwriting workflow.

#### Technical engineering details

- Built a LangChain / LangGraph orchestration layer supported by Python and SQL workflows over 3M+ loan records.
- Routed richer unstructured evidence into downstream review while preserving structured capture for verification and sector classification.
- Worked across front-end intake, operational review, and Redshift-backed data systems instead of treating the problem as a notebook-only exercise.
- Kept the workflow human-in-the-loop, with underwriters and processors remaining the accountable decision layer.

#### Why this is here

This project is representative of the kind of FDE-style work I care about most: customer-embedded discovery, workflow redesign in a high-consequence environment, and delivery of a governed system that fits real operations.

#### Public artifact note

The underlying production workflow and client data are confidential. This page therefore documents the project at the delivery and system-design level rather than releasing source code.

### Sunflower AI Labs

**Role:** Data Scientist  
**Period:** Oct 2024 - Present  
**Setting:** AI-native creator intelligence and sponsor-matching workflow design

#### Context

This work started from a two-sided marketplace problem, not a generic analytics request. Creators needed better guidance on what to make next in order to improve viewership, subscription growth, and monetization. Sponsors and MCNs needed stronger creator matching and more reliable decision support than platform-native heuristics.

#### End-to-end delivery

1. Interviewed creators and sponsors / MCNs in the US and Thailand to define the actual decision problem on both sides of the market.
2. Converted comments, transcripts, and metadata into an audience-segmented content-intelligence workflow rather than leaving them as raw engagement exhaust.
3. Built decision surfaces for two user groups: creator-side strategy and sponsor / MCN-side creator selection.
4. Extended the workflow from analysis into semi-automated execution support through report generation and LLM-assisted scripting.

#### Technical engineering details

- Organized the workflow around a core / community / crowd audience taxonomy so recommendation logic had a stable operational representation.
- Used chunking, embeddings, clustering, centroid assignment, retrieval, and LLM-grounded naming to turn noisy creator-content data into canonical themes.
- The public notebook [topic_themes.ipynb](topic_themes.ipynb) shows representative pieces of that workflow, including HDBSCAN or KMeans clustering, centroid storage, reassignment of new chunks to existing themes, FAISS-backed retrieval, and grounded LLM label generation.
- Delivered recommendation reports, sponsor-matching signals, and LLM-assisted scripting support across approximately 300 creators, with observed improvements of approximately 40% in subscription growth and viewership.

#### Why this is here

This project is a strong example of FDE-relevant work because it starts from cross-functional business pain points, defines a shared workflow boundary, and ships usable decision support rather than stopping at an analysis notebook.

## Academic Experience

### Multimodal Causal Workflow for Japanese American Oral Histories

**Focus:** Public-source multimodal research system design for transcript, audio, and video inputs  
**Research question:** How does adolescent exposure to state coercive incarceration shape later-life state-person narratives?

#### Context

This was not a simple text-analysis project. The hard part was first-principles workflow design: deciding how public transcripts, audio, and video should be represented, aligned, retrieved, fused, validated, and ultimately turned into a causal-ready and replication-ready system.

#### End-to-end delivery

1. Reframed oral histories as multimodal social data rather than illustrative testimony.
2. Defined the core measurement architecture around a `what x how` outcome schema separating substantive injury type from narrative composure.
3. Designed an orchestrator-skills-outputs workflow spanning deterministic cleaning, multimodal representation, retrieval, scoring, validation, and causal estimation.
4. Added explicit human-versus-AI handoffs, audit layers, and release boundaries so the workflow could be inspected rather than trusted as a black box.
5. Treated replication materials as a formal deliverable: versioned scripts, rerun wrappers, manifests, codebooks, and validation documents.

#### Technical engineering details

- Worked across transcript, audio, and video modalities rather than collapsing everything into text-only features.
- Had to decide per-modality retrieval paths, alignment logic, embedding strategy, and where fusion should happen.
- Built the project around governed execution surfaces instead of only model outputs: codebooks, manifests, containerized rerun paths, and validation packages.
- Used the workflow itself as a public-facing artifact so other researchers could learn from the research design rather than only consuming final results.

#### Why this is here

This project matters in an FDE context because it shows problem framing under ambiguity, multimodal workflow design, explicit operator control, and delivery of an inspectable surface that can be rerun and audited.

### University of Oxford / Said Business School

**Role:** Doctoral Researcher / Visiting Researcher  
**Period:** 2022 - Mar 2026  
**Related paper:** [Diplomats, political ties, and FDI](https://doi.org/10.1007/s11577-025-01045-6)

#### Context

The substantive question was how diplomats' experience and networks shaped FDI outcomes. The technical challenge was to connect structured economic and financial data with much messier biographical and career-history information in a way that downstream analysis could actually trust.

#### End-to-end delivery

1. Collected and aligned structured FDI, macroeconomic, market, and firm data.
2. Manually normalized diplomat biographies and career histories where source systems were too inconsistent for blind automation.
3. Resolved entity and timing conflicts across diplomats, countries, firms, and time windows.
4. Converted the reconciled system into inspectable datasets and readout surfaces for downstream analysis.
5. Extended the workflow into validation-heavy causal inference rather than stopping at descriptive integration.

#### Technical engineering details

- Combined API-accessible structured ingestion with manual reconciliation where textual records were the real bottleneck.
- Used DML, causal representation learning, and external-validity checks as part of a validated workflow, not as isolated methods.
- Built readout layers that made the reconciled outputs inspectable enough for downstream users to review and use.
- Treated the main engineering problem as hybrid workflow design across mixed-structure data sources.

#### Why this is here

This work shows the system-design side of research: selective automation, schema reconciliation, temporal alignment, and trustworthy downstream delivery over messy heterogeneous sources.

### Causal Representation Learning

**Focus:** Representation learning for causal adjustment and high-dimensional estimation  
**Public artifact:** [causal_representation_learning.ipynb](causal_representation_learning.ipynb)

#### What this notebook does

This notebook is a public methodological artifact exploring how textual representations can be used inside causal workflows rather than treated as generic embeddings.

#### Technical engineering details

- Simulates biography-like text data with embedded confounding structure.
- Extracts transformer-based embeddings from text.
- Compresses those representations into learned deconfounders through dimensionality reduction.
- Runs cross-fitted DML to estimate average treatment effects.
- Sketches a balance-aware extension using a CORAL-style objective to better align representation learning with causal adjustment goals.

#### Why this is here

This notebook is representative of a broader pattern in my work: using representation learning as part of a disciplined estimation workflow with identifiability, stability, and interpretability in view.

### Harvard University and Brown University

**Role:** Research Assistant  
**Period:** 2018 - 2020  
**Related paper:** [Higher Education and the Black-White Earnings Gap](https://journals.sagepub.com/eprint/JMTX4WJKGRIHIUIGVPKS/full)

#### Context

These projects involved observational labor-market and migration research where the main challenge was not just estimation, but building workflows that could turn noisy real-world data into reproducible and externally reviewable outputs.

#### End-to-end delivery

1. Structured observational data into validation-first analytical workflows.
2. Generated reproducible outputs on higher education and Black-White earnings inequality.
3. Extended the workflow family into migration work using multilevel models and dynamic demographic simulations.

#### Technical engineering details

- Used doubly robust ML, multilevel models, and simulation inside evidence-generation workflows rather than as stand-alone method demonstrations.
- Worked with noisy observational data where validation and robustness were as important as the model itself.
- Produced outputs that were strong enough for external review rather than only internal exploratory use.

#### Why this is here

This experience is earlier than the more deployment-facing work above, but it trained the same habits around formalizing messy problems, validating outputs, and making technically complex systems legible enough for other people to use.

## Public Artifacts In This Repository

### [topic_themes.ipynb](topic_themes.ipynb)

Representative artifact for creator-content theme extraction, clustering, centroid assignment, retrieval, and grounded theme naming.

### [causal_representation_learning.ipynb](causal_representation_learning.ipynb)

Representative artifact for representation learning inside causal estimation workflows.

## What This Portfolio Emphasizes

- stakeholder-driven problem framing,
- workflow design under ambiguity,
- end-to-end delivery rather than model-only work,
- human-in-the-loop AI systems,
- hybrid structured and unstructured data integration,
- validation and robustness discipline,
- interpretable outputs and decision surfaces, and
- reproducibility-oriented delivery.

## Notes On Confidentiality And Scope

- Industry projects are described at a level that is accurate but does not expose client-sensitive code, data, or internal systems.
- Research projects are described not only as academic outputs, but also as workflow and system-design work.
- This repository is intended to function as a portfolio of selected original work, not as a complete archive of every project artifact.

## Current Direction

The next step for this repository is to keep expanding the artifact layer so each project summary is paired, where possible, with a representative notebook, methodological note, or reproducible workflow component.
