---
layout: page
title: Scientific Writing
permalink: /scientific-writing/
description: Tips and structure for writing clear scientific papers.
---

This page gives an overview of practical guidelines for scientific writing. It is
especially useful for scientific papers and theses. It is not meant to be exhaustive,
but rather a curated checklist of some of the things that I have come across.

**Table of Contents**

* TOC
{:toc}

## Recommended LaTeX Packages

- better table formattting: [booktabs](https://ctan.org/pkg/booktabs?lang=en)
- large and long tables: [tabularray](https://ctan.org/pkg/tabularray) or [tabularx](https://ctan.org/pkg/tabularx)
- page size and margins: [geometry](https://ctan.org/pkg/geometry)
- inserting pdf documents: [pdfpages](https://ctan.org/pkg/pdfpages)
- image support: [graphicx](https://ctan.org/pkg/graphicx)
- subfigure layouts: [subcaption](https://ctan.org/pkg/subcaption)
- imrpoved caption formatting: [caption](https://ctan.org/pkg/caption)
- landscape mode: [pdflscape](https://ctan.org/pkg/pdflscape)
- robust URLs in text and footnotes: [url](https://ctan.org/pkg/url)
- hyperlinks and cross-references[hyperref](https://ctan.org/pkg/hyperref)
- better footnotes: [footmisc](https://ctan.org/pkg/footmisc)
- advanced math environments: [amsmath](https://ctan.org/pkg/amsmath)
- even more curly letters: [BOONDOX-uprscr]()
- proper number and unit formatting: [siunitx](https://ctan.org/pkg/siunitx)
- acronym handling: [glossaries](https://ctan.org/pkg/glossaries) or [acronym](https://ctan.org/pkg/acronym)
- MATLAB code listings: [matlab-prettifier](https://ctan.org/pkg/matlab-prettifier)
- Python code listings: [listings](https://ctan.org/pkg/listings)
- bibliography management: [biblatex](https://ctan.org/pkg/biblatex)
- working on smaller document parts: [subfiles](https://ctan.org/pkg/subfiles)

## Formatting

### Equations

1. Integrate equations naturally into the text. Avoid introducing formulas directly
   after punctuation like `.` or `:`.
2. When referencing a display equation, place the reference at the end of the
   sentence that introduces the equation.
3. Explain every variable that appears in the equation, unless it was clearly
   defined earlier. Repeating a short definition is often better than forcing the
   reader to search multiple pages back.

### Plots and Figures

Recommended plotting tool: [Veusz](https://veusz.github.io).

1. Match figure text size to the surrounding document text.
2. Prefer the same font family as the document body where practical.
3. Avoid grid lines unless they are required for interpretation.
4. Keep plots minimal: avoid unnecessary border lines and emphasize the axes.
5. Export figures as high-resolution PDF when possible. Do not use JPG for plots.
6. Refer to every figure explicitly in the running text.
7. Try to include the figure *after* it is mentioned in the text.
8. For colors, try to use the colorblind- and printer-friendly families from [colorbrewer2](https://colorbrewer2.org)a

### Tables

1. Format most small in-chapter tables with `booktabs`, typically in this order:
   - caption
   - `\toprule`
   - header row
   - `\midrule`
   - data rows
   - `\bottomrule`
2. Avoid vertical lines unless a large, dense table clearly requires them.

### Captions

1. Place captions above tables and below figures.
2. If a caption includes references, keep the short list-of-figures/list-of-tables
   entry clean using:
   `\caption[caption in list of ...]{caption in text}`

### Paragraph Spacing

1. Avoid the German style of no indentation and no paragraph spacing.
2. Prefer one of these consistent options:
   - indented, no extra spacing
   - indented with extra spacing (preferred)
   - not indented with extra spacing

### Citations and References

1. Use a non-breaking space before citations, for example `text~\cite{...}`.
2. Do not reference bare numbers only. Always name the object type, such as
   Table, Figure, or Section.
3. In English writing, citations usually belong within the sentence, not only at
   the end of a paragraph.
4. Cite papers in prose using author last names where appropriate.

### Variables, Numbers, and Units

1. In math mode, only variables should be italicized. Units should remain upright
   text (for example via `siunitx`).
2. Always include a space between number and unit.
3. Use a dot as the decimal separator in English text.
4. For areas and dimensions, write units on each term, for example
   `100 mm x 100 mm`.

## Writing Style

1. Use American English.
2. Use the Oxford comma in lists of three or more items.
3. Keep references in the same line as the referenced text using non-breaking
   spaces (for example `Figure~\ref{...}` and `text~\cite{...}`).
4. Use grammar tools as support (for example Grammarly) but still proofread
   manually.
5. Choose a tense strategy (preferably present tense for technical description)
   and stay consistent.
6. Avoid contractions in formal technical writing (for example "don't", "won't").
7. Apply consistent capitalization rules in titles and descriptive captions.
   Helpful tool: [Capitalize My Title](https://capitalizemytitle.com).