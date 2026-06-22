# ImmPrint

> A curated, citation-backed collection of immune signalling gene sets.

This repository is the **home of the ImmPrint collection**, holding the canonical
data, the curation rationale and the project website. ImmPrint is a focused collection of
immune signalling gene sets for scoring transcriptomic data. Each gene is specific
to the process, kept apart from the ligand that triggers it, placed in a Receptor,
Transducer, Effector hierarchy and tied to a paper that links that gene to that
pathway.

**Website:** <https://akmclz.github.io/immprint>

## What's here

```
data/        canonical versioned snapshots (CSV and JSON)
*.qmd        the Quarto website (home, browse, rationale, access, changelog, cite)
custom.scss  site theme
```

The current snapshot is **v0.2.0-alpha**: 44 gene sets, 724 gene set memberships.
Snapshots are immutable; new curation ships as a new version.

## Using the collection

- **R:** the [`immprintr`](https://github.com/akmclz/immprintr) package delivers
  ImmPrint as a tidy tibble and is the recommended route for R users.
- **Anything else:** read the published `data/immprint_<version>.csv` or `.json`
  directly. See [Access](https://akmclz.github.io/immprint/access.html).

## Relationship to `immprintr`

This repo is the **single source of truth** for the data and curation. The
`immprintr` R package is a *client*: it vendors versioned snapshots from here and
wraps them in a tidy API. Curation happens here; packaging happens there.

## Columns

One row per gene set, cell type and gene membership: `gene_set`, `cell_type`
(`pan` for the cell type-agnostic core), `gene_symbol`, `pathway_level` (1 Receptor,
2 Transducer, 3 Effector), `pmids` (semicolon-delimited), `reference_gene_set`
(corroborating MSigDB set, where available).

## Building the site locally

```sh
quarto preview     # live preview
quarto render      # build into _site/
```

The site is plain Quarto markdown plus Observable JS, so no R is needed to render
it. CI renders and deploys to GitHub Pages on every push to `main`.

## Licence

The **collection data and site content** are licensed under
[CC BY 4.0](LICENSE): free to use and redistribute with attribution. Please [cite
the version you use](https://akmclz.github.io/immprint/cite.html). Any code in this
repository is additionally available under the MIT Licence.

## Citation

See [CITATION.cff](CITATION.cff) or the
[Cite](https://akmclz.github.io/immprint/cite.html) page.
