# Editorial review — updated 21 October 2026

This is a manuscript-only revision. No model requests or new experiment runs
were made. Table labels and punctuation were revised, with all results unchanged.

## Requested changes

- Title: **Securing Agent-Generated Code Through Development History**.
- TRACER is expanded in the abstract as **Trace-based Runtime Analysis for Continuous Evolution and Release**.
- Authors, in order: **Prateek Rajput; Shahzeb Khan; Jacques Klein; Tegawendé F. Bissyandé**.
- Shahzeb is affiliated with Nostrum Biodiscovery; the other authors with the University of Luxembourg. The latest Overleaf author block supplies all four email addresses and the city/country details; these are preserved with corrected line breaks.
- **Industry Relevance and Code Archaeology** now opens Section II; Section VIII-A discusses the C2/C3 context-selection lesson instead of repeating this motivation.
- Manuscript review by the Nostrum Biodiscovery co-author is recorded. This does not reclassify the researcher-run evaluation as an independent deployment or replication.
- The bibliography grows from **14 to 48 distinct, actually cited entries**. No `nocite` padding is used. Additions concentrate on background, method attribution, related work, and the six domain repositories.

## ICSE 2027 SEIP formatting check

Checked against the [official SEIP call](https://conf.researchr.org/track/icse-2027/icse-2027-seip).

| Requirement or check | Result |
| --- | --- |
| IEEE conference class, 10pt, without `compsoc` or `compsocconf` | Uses `\documentclass[10pt,conference]{IEEEtran}` |
| Standard title/body type sizes | Class defaults retained: nominal 24pt title and 10pt main text |
| Author identification | Allowed: the SEIP call does not require double-anonymous review |
| Layout | Standard two-column IEEEtran layout; letter-size PDF; no geometry, margin, line-spacing, or font-size compression overrides |
| References | IEEEtran bibliography style; numbered citations; `cite` sorts/compresses citation groups |
| Reference-column balance | The obsolete manual reference break is removed; final column balancing is deferred until the text stabilizes |
| Fonts | PDF font inspection confirms embedded fonts, with Times-compatible Nimbus Roman for prose |
| Build | Tectonic 0.17.0 completed; no LaTeX errors, unresolved citations/references, BibTeX warnings, or overfull boxes |
| Visual review | Title/author page, domain table/figure, and bibliography checked; remaining underfull-box warnings are normal layout warnings |
| Pagination | 14 total pages after the new overview and closing sections; references begin on page 12. The call allows 10 main-text pages plus 2 reference pages. Compliance with the page limits is intentionally deferred at the author's request |
| Overleaf | Keep `main.tex` as the main document and pdfLaTeX as the compiler; the local verification build used Tectonic |

The title, author block, bibliography, and body formatting follow the required
class. This is not a claim that the current draft is ready for submission:
pagination and final author review remain outstanding. All numerical tables and
experimental denominators are unchanged.

## 21 October narrative revision

- The approved abstract is byte-for-byte unchanged. All five table sources,
  the case-study figure source, and `references.bib` are unchanged, and all
  48 citation keys remain cited.
- The introduction now follows the industry problem, existing defenses,
  development-history opportunity, silent-fix maintenance problem, portable
  TRACER workflow, and three contributions. Detailed cohort accounting appears
  after the conceptual motivation.
- Section IV presents five explicit research questions and their rationales,
  followed by the benchmark inventory, a C0–C3 configuration list, and execution
  integrity. Resumption and parser details are consolidated at its end.
- Section VI groups v6–v12 into evidence fidelity, boundary authorization, and
  context/lifecycle completeness, preserving the development table and counts.
- Section VII explicitly evaluates the maintenance stage as RQ5. Collaborator
  attribution and researcher-run scope appear once there and once in validity.
- Five grey `tcolorbox` finding boxes conclude the corresponding results.
  The RQ5 box reports joint feature-and-boundary success, without attributing
  the combined memory/gate/retry effect to memory alone. C0's change-informed
  target selection and the C1–C3 audit-cue confound remain explicit.

## 21 October Round 2: background and implementation alignment

The revision starts from Overleaf commit `0e767d8`. It fixes the three requested
introduction typos and preserves the other Overleaf edits. The approved abstract,
all five table sources, bibliography, research questions, experimental results,
and domain-study outcomes are unchanged.

Section II now separates industry review, structural-history representation,
and task/rationale interpretation, followed by one paragraph of explicitly
identified SusVibes cases. First mentions link to the official repositories for
[Python-RSA](https://github.com/sybrenstuvel/python-rsa),
[LangChain](https://github.com/langchain-ai/langchain),
[Wagtail](https://github.com/wagtail/wagtail), and
[Django](https://github.com/django/django). These identify the projects; the
benchmark and recorded investigations supply the case-specific evidence.

Section III now has four subsections: current-symbol/SAST review (C0), GumTree
evolution (C1), rationale links (C2/C3), and the decision ledger/repair gate/skill.
The implementation claims were checked against the research checkout:

| Mechanism | Implementation inspected |
| --- | --- |
| Python `ast.parse`, custom qualified-symbol visitor, hunk/deletion-anchor mapping | `security_ground_truth/temporal_security/planner.py`: `_symbols`, `patch_lines`, `_enclosing`, `plan` |
| Structural hashes and explicit limits of cross-version identity | `security_ground_truth/runtime/history/adapter.py`: `structural_index`, `structural_delta`; `runtime/history/query.py`: `current_fragment_anchors` |
| Typed GumTree edits, fragment normalization, bounded summaries | `security_ground_truth/temporal_security/gumtree.py`: `summarize_pair`; `history.py`: `parseable_pair`, `_bound_records` |
| Original prose, event/path/symbol links, exact quotations and assumptions | `security_ground_truth/temporal_security/rationale.py`: `prose_spans`, `build_rationale`, `RationaleSession.validate_refs` |
| Persisted hypotheses/assessments and qualified maintenance records | `security_ground_truth/temporal_security/engine.py`: `edit_note.json` output; `paper/bio_study/run.py`: qualified repair-note construction |
| Portable interface | `skills/tracer-security/SKILL.md`; `security_ground_truth/temporal_security/cli.py` |

The prose names Python's standard-library AST parser, rather than inventing a
third-party symbol extractor. It distinguishes recorded/current symbol links
from guaranteed identity across arbitrary renames, and cited rationale from a
complete capture of private reasoning. Context dilution is discussed in
Section VIII-A as a possible explanation of C2/C3, not a measured causal effect.

## 21 October punctuation and symbol-index clarification

Unnecessary semicolons and colons were replaced with periods, commas, or revised
sentences throughout the prose, headings, captions, and table descriptions.
Technical syntax, record-field delimiters, URLs, and canonical reference titles
retain their punctuation. The approved abstract is byte-for-byte unchanged.
All numerical values and citation sequences are unchanged across the ten edited
LaTeX inputs, and all 48 references remain cited.

Section III-A now explicitly describes the evaluated Python pipeline as building
a symbol-level index with `ast.parse` and a custom visitor. It records repository
paths, qualified names, and definition spans for each parsed snapshot. Patch
hunks, scanner positions, and historical evidence are linked to these symbols.
This is implemented indexing, not only an architectural proposal, and it does
not imply perfect cross-version identity through renames or moves. The separate
original recorder's `codebase-memory-mcp` integration is not claimed as a
dependency of the evaluated Python security pipeline.

The revised PDF compiles to 13 pages, with references beginning on page 12.
The build has no errors, unresolved citations/references, or overfull boxes.

## 21 October overview, acknowledgements, and artifact availability

Figure 1 uses the author-provided `tracer_security_overview.pdf` as a vector
figure across both columns, with a short caption. Section III links to the
skill repository. A Data Availability section follows the conclusion and
explicitly distinguishes the prepared code/result release from the still
unpublished permanent archive. The closing acknowledgements thank Google for
Gemini API credits and Nostrum Biodiscovery for verification assistance and
practical feedback, without changing the study's researcher-run designation.

The current PDF compiles without errors or unresolved references. The page
limit remains intentionally deferred. The RQs, approved abstract, and all
experimental numbers remain unchanged in this revision.

## Citation verification notes

The original 14 references retain the source checks from the previous manuscript
revision. The 34 additions were checked against publisher/proceedings pages,
author papers or repositories, and official software documentation; bibliographic
metadata was cross-checked against DOI registrations where available. The list
below gives the precise role of each citation for manual review. A literature
citation supports the stated background or method, not the numerical results of
our own study.

Specific bibliographic choices worth checking:

- **ChatRepair** uses its final ISSTA 2024 title and DOI, rather than the differently titled 2023 preprint.
- **RepairAgent** uses its ICSE 2025 publication; **RepoAudit** uses its ICML 2025 proceedings entry.
- **Copilot-generated security weaknesses** uses the TOSEM 2025 publication, rather than its earlier preprint.
- **Foldseek** uses the 2024 journal-volume date; the paper first appeared online in 2023.
- **Bootstrap** uses the 1994 Chapman and Hall/CRC edition identified by its DOI; the original edition appeared in 1993.
- **SusVibes** retains the benchmark authors' ICML 2026 citation and the pinned evaluator release. The OpenReview page's browser challenge prevented independent venue-page inspection in the prior verification.
- **IRIS** metadata was checked through the authors' repository and the ICLR camera-ready PDF; the interactive OpenReview page requires a browser challenge.
- **PAGENT** and **Measuring Faithfulness** are labeled preprints. **POSTURA**, documentation, and the **Undoing the Fix** report are not presented as peer-reviewed research papers.
- The pinned **PyTorch v2.5.1 source/API** is cited for version-specific behavior; current documentation may describe different defaults.

## Source-by-source review list

Numbers correspond to this compiled draft and will change if citations move.

| Ref. | BibTeX key | Primary source | Type | Use and claim boundary |
| --- | --- | --- | --- | --- |
| 1 | `sweagent` | [SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering](https://proceedings.neurips.cc/paper_files/paper/2024/hash/5a7c947568c1b1328ccc5230172e1e7c-Abstract-Conference.html) | Conference paper | Agent-computer interfaces for repository navigation, editing, and testing; reused trajectory provenance. |
| 2 | `repairagent` | [RepairAgent: An Autonomous, LLM-Based Agent for Program Repair](https://doi.org/10.1109/icse55347.2025.00157) | Conference paper | Autonomous tool-using program repair; ICSE 2025. |
| 3 | `asleep` | [Asleep at the Keyboard? Assessing the Security of GitHub Copilot's Code Contributions](https://doi.org/10.1109/sp46214.2022.9833571) | Conference paper | Security weaknesses in generated Copilot code; motivation for a separate security review. |
| 4 | `perry` | [Do Users Write More Insecure Code with AI Assistants?](https://doi.org/10.1145/3576915.3623157) | Conference paper | Human study of AI-assisted coding and security; background, not a label source for this experiment. |
| 5 | `copilotweaknesses` | [Security Weaknesses of Copilot-Generated Code in GitHub Projects: An Empirical Study](https://doi.org/10.1145/3716848) | Journal article | Empirical study of generated snippets in GitHub projects and scanner-informed repair; background, not our security oracle. |
| 6 | `susvibes` | [Is Vibe Coding Safe? Benchmarking Vulnerability of Agent-Generated Code in Real-World Tasks](https://openreview.net/forum?id=qG8g00zRZa) | Conference citation supplied by benchmark authors | Functional/security benchmark distinction; cite the 186-task release used here, not the earlier 200-task preprint. |
| 7 | `susvibesartifact` | [SusVibes: Benchmark and Evaluation Pipeline](https://github.com/LeiLiLab/susvibes/tree/7e1b4b05240e56dc2b4e8253b2cc5c9481d016f3) | Documentation/software/report | Pinned official evaluator source used in the study. |
| 8 | `codeql` | [CodeQL CLI](https://docs.github.com/en/code-security/concepts/code-scanning/codeql/codeql-cli) | Documentation/software/report | Scanner/database analysis interface; exact experimental version comes from frozen study manifests. |
| 9 | `semgrep` | [Semgrep Code Overview](https://docs.semgrep.dev/semgrep-code/overview) | Documentation/software/report | Rule-based analysis interface; do not imply Pro-engine capabilities in our CE configuration. |
| 10 | `johnson` | [Why don't software developers use static analysis tools to find bugs?](https://doi.org/10.1109/icse.2013.6606613) | Conference paper | Developer adoption barriers and diagnostic usability in static analysis. |
| 11 | `googleanalysis` | [Lessons from building static analysis tools at Google](https://doi.org/10.1145/3188720) | Journal article | Industrial lessons about actionable checks and integration into code review. |
| 12 | `infer` | [Moving Fast with Software Verification](https://doi.org/10.1007/978-3-319-17524-9_1) | Conference paper | Industrial deployment of incremental verification in a development workflow. |
| 13 | `iris` | [IRIS: LLM-Assisted Static Analysis for Detecting Security Vulnerabilities](https://openreview.net/forum?id=9LdJDU7E91) | Conference paper | LLM-assisted taint specifications and contextual filtering of candidate paths. |
| 14 | `llmdfa` | [LLMDFA: Analyzing Dataflow in Code with Large Language Models](https://proceedings.neurips.cc/paper_files/paper/2024/hash/ed9dcde1eb9c597f68c1d375bbecf3fc-Abstract-Conference.html) | Conference paper | Dataflow analysis using language models with parsing and external feasibility checks. |
| 15 | `repoaudit` | [RepoAudit: An Autonomous LLM-Agent for Repository-Level Code Auditing](https://proceedings.mlr.press/v267/guo25n.html) | Conference paper | Repository-level agent auditing with memory and validation. |
| 16 | `inferfix` | [InferFix: End-to-End Program Repair with LLMs](https://doi.org/10.1145/3611643.3613892) | Conference paper | Static-analyzer-guided repair with retrieved fixes; related work, not a head-to-head baseline. |
| 17 | `pagent` | [Program Analysis Guided LLM Agent for Proof-of-Concept Generation](https://arxiv.org/abs/2604.07624) | Preprint | Static guidance plus dynamic feedback for PoC generation; our Python checks adapt the pattern rather than reproduce the system. |
| 18 | `react` | [ReAct: Synergizing Reasoning and Acting in Language Models](https://openreview.net/forum?id=WE_vluYUL-X) | Conference paper | Exposed interleaved action/rationale format; not access to private internal reasoning. |
| 19 | `gumtree` | [Fine-grained and accurate source code differencing](https://doi.org/10.1145/2642937.2642982) | Conference paper | AST edit matching; this is a component of the method, not a security oracle. |
| 20 | `turpin` | [Language Models Don't Always Say What They Think: Unfaithful Explanations in Chain-of-Thought Prompting](https://proceedings.neurips.cc/paper_files/paper/2023/hash/ed3fea9033a80fea1376299fa7863f4a-Abstract-Conference.html) | Conference paper | Generated explanations may omit influences on an answer; limits of rationale interpretation. |
| 21 | `lanham` | [Measuring Faithfulness in Chain-of-Thought Reasoning](https://arxiv.org/abs/2307.13702) | Preprint | Interventions testing rationale faithfulness; preprint, not proof that our recorded traces are faithful. |
| 22 | `colefunda` | [CoLeFunDa: Explainable Silent Vulnerability Fix Identification](https://xing-hu.github.io/assets/papers/icse23colefunda.pdf) | Conference paper | Function-change descriptions and silent-fix identification; motivation, not a reproduced baseline. |
| 23 | `undoingfix` | [Undoing the Fix: Evaluating AI Control Against Security Regression Attacks](https://github.com/strivn/undoing-the-fix/tree/6511beccd75b63c93628ec8dc062ebb07a0bcc5d) | Exploratory report | Exploratory regression-attack report; not a human-verified or executable ground-truth corpus. |
| 24 | `rfdiffusion` | [De novo design of protein structure and function with RFdiffusion](https://doi.org/10.1038/s41586-023-06415-8) | Journal article | Original RFdiffusion tool paper; attribution for a studied repository, not evidence of our component defect. |
| 25 | `proteinmpnn` | [Robust deep learning--based protein sequence design using ProteinMPNN](https://doi.org/10.1126/science.add2187) | Journal article | Original ProteinMPNN tool paper; repository attribution. |
| 26 | `haddock3` | [HADDOCK3: A Modular and Versatile Platform for Integrative Modeling of Biomolecular Complexes](https://doi.org/10.1021/acs.jcim.5c00969) | Journal article | HADDOCK3 platform paper, rather than an older HADDOCK server paper. |
| 27 | `dockq` | [DockQ v2: improved automatic quality measure for protein multimers, nucleic acids, and small molecules](https://doi.org/10.1093/bioinformatics/btae586) | Journal article | DockQ v2 Python reimplementation and expanded format support; repository attribution. |
| 28 | `vina` | [AutoDock Vina 1.2.0: New Docking Methods, Expanded Force Field, and Python Bindings](https://doi.org/10.1021/acs.jcim.1c00203) | Journal article | AutoDock Vina 1.2.0 and its Python bindings; repository attribution. |
| 29 | `foldseek` | [Fast and accurate protein structure search with Foldseek](https://doi.org/10.1038/s41587-023-01773-0) | Journal article | Structure-search tool paper; inventory repository only, with no selected repair case. |
| 30 | `ssdf` | [Secure Software Development Framework (SSDF) Version 1.1: Recommendations for Mitigating the Risk of Software Vulnerabilities](https://csrc.nist.gov/pubs/sp/800/218/final) | Technical standard/report | Secure-development practices for code review, testing, and vulnerability knowledge. No certification claim. |
| 31 | `gumtree3` | [GumTree, release 3.0.0](https://github.com/GumTreeDiff/gumtree/releases/tag/v3.0.0) | Documentation/software/report | Pinned GumTree implementation release. |
| 32 | `pythonast` | [ast---Abstract Syntax Trees](https://docs.python.org/3.11/library/ast.html) | Documentation/software/report | Python AST nodes, location information, and docstring identification. |
| 33 | `bootstrap` | [An Introduction to the Bootstrap](https://doi.org/10.1201/9780429246593) | Book | General bootstrap methodology; task clustering, seed, and replicate count describe our own implementation. |
| 34 | `pytorchserialization` | [Serialization API and Safe-Globals Context Manager](https://github.com/pytorch/pytorch/blob/v2.5.1/torch/serialization.py) | Documentation/software/report | Pinned v2.5.1 serialization source/API: weights_only and safe_globals. Does not establish universal safety of the component repair. |
| 35 | `pythonpickle` | [pickle---Python Object Serialization](https://docs.python.org/3.11/library/pickle.html) | Documentation/software/report | Python documentation of the arbitrary-code risk of untrusted unpickling. |
| 36 | `pythontokenize` | [tokenize---Tokenizer for Python Source](https://docs.python.org/3.11/library/tokenize.html) | Documentation/software/report | Token-level comment handling in the silent-fix preprocessing step. |
| 37 | `repairsurvey` | [Automatic Software Repair: A Bibliography](https://doi.org/10.1145/3105906) | Journal article | Repair oracles and acceptance criteria; distinction between plausible/test-passing and correct repairs. |
| 38 | `overfitting` | [Is the cure worse than the disease? overfitting in automated program repair](https://doi.org/10.1145/2786805.2786825) | Conference paper | Test-suite overfitting as a limit on automated repair evaluation. |
| 39 | `swebench` | [SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://proceedings.iclr.cc/paper_files/paper/2024/hash/edac78c3e300629acfe6cbe9ca88fb84-Abstract-Conference.html) | Conference paper | Functional repository-level evaluation, contrasted with security-specific tests. Not an additional dataset evaluated in this paper. |
| 40 | `cvefixes` | [CVEfixes: automated collection of vulnerabilities and their fixes from open-source software](https://doi.org/10.1145/3475960.3475985) | Conference paper | Vulnerability-to-fix history collection; related dataset, not used as our ground-truth oracle. |
| 41 | `vul4j` | [Vul4J: A Dataset of Reproducible Java Vulnerabilities Geared Towards the Study of Program Repair Techniques](https://doi.org/10.1145/3524842.3528482) | Conference paper | Reproducible Java vulnerabilities and triggering tests; related dataset, not part of the Python experiment. |
| 42 | `violationtracker` | [ViolationTracker: Building Precise Histories for Static Analysis Violations](https://conf.researchr.org/details/icse-2023/icse-2023-technical-track/12/ViolationTracker-Building-Precise-Histories-for-Static-Analysis-Violations) | Conference paper | Static-analysis warning histories; avoids claiming history-based analysis itself is new. |
| 43 | `knighter` | [KNighter: Transforming Static Analysis with LLM-Synthesized Checkers](https://arxiv.org/abs/2503.09002) | Conference paper | Checkers synthesized from historical patches; related work, not a reproduced baseline. |
| 44 | `fixminer` | [FixMiner: Mining relevant fix patterns for automated program repair](https://doi.org/10.1007/s10664-019-09780-z) | Journal article | Mining reusable repair patterns from structured patches; related work rather than a component we executed. |
| 45 | `chatrepair` | [Automated Program Repair via Conversation: Fixing 162 out of 337 Bugs for $0.42 Each using ChatGPT](https://doi.org/10.1145/3650212.3680323) | Conference paper | Conversational repair using test feedback; ISSTA 2024 publication, not ICSE. |
| 46 | `reflexion` | [Reflexion: Language Agents with Verbal Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2023/hash/1b44b878bb782e6954cd888628510e90-Abstract-Conference.html) | Conference paper | Verbal feedback in episodic agent memory; distinction from independently owned checks. |
| 47 | `selfrefine` | [Self-Refine: Iterative Refinement with Self-Feedback](https://proceedings.neurips.cc/paper_files/paper/2023/hash/91edff07232fb1b55a505a9e9f6c0ff3-Abstract-Conference.html) | Conference paper | Iterative model-generated feedback and refinement; distinct from our executable gate. |
| 48 | `postura` | [POSTURA: Agentic Attack Surface Posture Intelligence](https://github.com/motornomad/postura) | Documentation/software/report | Software design for persistent security representations; not a peer-reviewed effectiveness result. |
