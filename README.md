# TRACER

**Securing Agent-Generated Code Through Development History**

TRACER stands for **Trace-based Runtime Analysis for Continuous Evolution and Release**.

Working manuscript for ICSE 2027 SEIP. TRACER connects static-analysis findings
with symbol-level code evolution and separately recorded development rationale,
validates candidate security repairs, and preserves repair evidence for later
maintenance.

The [TRACER skill](https://github.com/pkrajput/TRACER_skill) and derived study
evidence are archived on [Zenodo](https://doi.org/10.5281/zenodo.23530070).

## Overleaf

Sync this repository's `main` branch, select **`main.tex`** as the main document,
and use **pdfLaTeX**. All required manuscript inputs are included. The tables
are frozen LaTeX files, so compilation does not require experiment artifacts,
Python, Docker, or model API calls.

Edit the source files below for collaborative revisions. After changing files
in Overleaf, push those changes to GitHub before pulling and editing locally.
For review notes that should travel with the source, use a LaTeX comment such
as `% REVIEW: clarify this comparison`. Share Overleaf review-panel comments
separately when needed: [Overleaf documents that GitHub pulls can displace or
lose review comments and tracked changes](https://docs.overleaf.com/integrations-and-add-ons/git-integration-and-github-synchronization/github-synchronization).

## Source layout

| File | Contents |
| --- | --- |
| [`main.tex`](main.tex) | Preamble, title, abstract, Sections I–V, and bibliography setup |
| [`main_remaining.tex`](main_remaining.tex) | Section VI and includes for later sections |
| [`section_vii_final.tex`](section_vii_final.tex) | Computational-biology maintenance study |
| [`sections_viii_x_final.tex`](sections_viii_x_final.tex) | Discussion, validity, related work, and conclusion |
| [`references.bib`](references.bib) | Bibliography |
| [`tables/`](tables/) | Five manuscript tables |
| [`figures/bio_memory_trace.tex`](figures/bio_memory_trace.tex) | Repair-memory case-study figure |
| [`figures/tracer_security_overview.pdf`](figures/tracer_security_overview.pdf) | Author-provided overview used as Figure 1 |

## Local build

From the repository root, with a LaTeX distribution and `latexmk` installed:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

Alternatively, with Tectonic:

```sh
tectonic main.tex --keep-logs --keep-intermediates
```

The output is `main.pdf`. Generated PDFs and auxiliary files are excluded from
Git. The prepared manuscript was compiled with Tectonic 0.17.0.

## Draft status and artifacts

The manuscript reports the completed SusVibes study, including the shared
345-attempt comparison across both investigators, the separate 354-attempt
DeepSeek comparison, and the five-case computational-biology continuation
study. The authors are Prateek Rajput, Shahzeb Khan, Jacques Klein, and
Tegawendé F. Bissyandé, in that order. The author block includes the affiliations
and contact details supplied through Overleaf.
The Nostrum Biodiscovery co-author has reviewed the manuscript; the quantitative
study remains researcher-run.

[`EDITORIAL_REVIEW.md`](EDITORIAL_REVIEW.md) records the SEIP format check and
provides the 49-reference citation review list. Page-limit editing remains
deferred.

The [skill repository](https://github.com/pkrajput/TRACER_skill) includes the
current manuscript PDF and compact outcome records. The
[Zenodo release](https://doi.org/10.5281/zenodo.23530070) preserves the published
software and derived evidence. Raw investigator transcripts, complete evaluator
logs, and container exports are outside that archive. See the Data Availability
section and artifact documentation for its precise scope.
