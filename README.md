# SLR LaTeX Template
**University of Rijeka — Faculty of Informatics and Digital Technologies**

A structured LaTeX template for a Systematic Literature Review (SLR)
following PRISMA 2020, Wohlin (2014) snowballing, and Xiao & Watson (2019).

---

## File structure

```
slr_template/
├── main.tex                          # Document root: preamble + \input chain
├── bibliography.bib                  # All references (natbib/plainnat)
├── figures/                          # Drop your PDF/PNG figures here
└── sections/
    ├── 00_abstract.tex               # Abstract + keywords
    ├── 01_introduction.tex           # Introduction + RQ + review structure
    ├── 02_background.tex             # Technical background (2–4 subsections)
    ├── 03_methodology.tex            # PRISMA methodology (full pipeline)
    ├── 04_literature_cluster_1.tex   # Literature chapter — thematic cluster 1
    ├── 05_literature_cluster_2.tex   # Literature chapter — thematic cluster 2
    ├── 06_literature_cluster_3.tex   # Literature chapter — thematic cluster 3
    ├── 07_literature_cluster_4.tex   # Literature chapter — thematic cluster 4
    ├── 08_literature_cluster_5.tex   # Literature chapter — thematic cluster 5
    ├── 09_synthesis_gap.tex          # Concept matrix + gap map (SLR core)
    ├── 10_conclusion.tex             # Findings, threats, limitations
    └── 11_appendix.tex               # Search prompts, DB queries, audit log
```

---

## Getting started

1. Replace every `[PLACEHOLDER]` in `main.tex` (title, author, institution, date).
2. Work through each section file in order. Every file has `% Hints` comments
   describing what belongs in each subsection — delete the hints as you go.
3. Drop your figures as PDFs or PNGs into the `figures/` directory and update
   the `\includegraphics` filenames.
4. Add your references to `bibliography.bib` following the entry-type examples
   provided in Section 2 of that file.

## Compilation

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Or with latexmk:

```bash
latexmk -pdf main.tex
```

---

## Key structural decisions

| Decision | Choice | Why |
|---|---|---|
| Citation style | `natbib` with `\citet` / `\citep` | Harvard author-year style; see `bibliography.bib` for usage examples |
| Numbered sections | `\arabic{section}.` | Required format at Faculty of Informatics |
| Tables | `booktabs` + `tabularx` | Professional horizontal rules; auto-width columns for long text |
| Wide tables | `sidewaystable` | Rotates landscape for multi-column comparison tables |
| Concept matrix | `\rotatebox{70}` headers | Compact column headers for binary comparison tables |

---

## PRISMA 2020 compliance checklist

- [ ] Research question stated in `\begin{quote}` block (§3.1)
- [ ] Prior reviews assessed (§3.2)
- [ ] Seed paper selection criteria stated (§3.3)
- [ ] G0–G6 groups documented with counts (§3.4, Table 1)
- [ ] Snowballing procedure matches Wohlin (2014) (§3.5)
- [ ] I/E criteria in pre-defined table (§3.6, Table 2)
- [ ] Screening outcomes reported (§3.7, Table 3)
- [ ] Tier classification reported (§3.8, Table 4)
- [ ] Abstract review outcomes reported (§3.10, Table 6)
- [ ] PRISMA flow diagram figure included (§3.10, Figure PRISMA)
- [ ] AI tool use disclosed (§3.12)
- [ ] Concept matrix in synthesis (§9.2, Table 8)
- [ ] Gap map table in synthesis (§9.4, Table 9)
- [ ] Four validity threats addressed in conclusion (§10.3)

---

## Methodology references (always cite these)

| Reference | Role |
|---|---|
| Page et al. (2021) — PRISMA 2020 | Reporting guidelines |
| Wohlin (2014) | Snowballing procedure |
| Xiao & Watson (2019) | 8-step SLR process |
| Kitchenham & Charters (2007) | SLR definition and prior-review check |
| Webster & Watson (2002) | Concept-centric structure |
| Keshav (2007) | Three-pass reading + tier-based prioritisation |

All six are included in `bibliography.bib`.
