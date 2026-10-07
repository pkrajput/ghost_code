# Ghost Code in Passing Agent Solutions

Working NIER paper on retained editing helpers in passing coding-agent solutions, their effects under deliberate reuse and source retrieval, and whole-file cleanup under fixed task oracles.

## Manuscript

- [LaTeX source](paper/ghost_code_nier.tex)
- [Study overview figure](paper/figures/ghost_code_overview_v6.pdf)

The manuscript includes the bibliography, results tables, and a provisional data-availability statement. It is a working draft; submission formatting and page-limit editing remain pending.

## Build

With a LaTeX distribution and `latexmk` installed, compile from the manuscript directory:

```sh
cd paper
latexmk -pdf -interaction=nonstopmode -halt-on-error ghost_code_nier.tex
```

Alternatively, run `pdflatex ghost_code_nier.tex` twice from that directory to resolve references. The figure is loaded from `figures/ghost_code_overview_v6.pdf`; keep that relative path when importing the project into a LaTeX editor.

## Experimental artifacts

This repository contains the paper source and its figures. The experiment archives, execution environments, model caches, and raw trial outputs are maintained separately. The public replication-package deposit is pending, as stated in the manuscript.
