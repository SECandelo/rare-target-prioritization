# Data sources, versions and licences

Nothing in this repository is original data. Every number comes from a public
resource, retrieved through its own API on the date recorded in the phase
manifests under `data/processed/`. This file records what was used, under which
licence, and what that implies for anyone reusing the derived tables here.

## Resources used in the recorded run

| resource | accessed via | version / identifier |
|---|---|---|
| Open Targets Platform | GraphQL API | release **26.09** |
| Pharos / IDG | GraphQL API | target development level, novelty score |
| ClinVar | NCBI E-utilities (esearch / esummary) | retrieved October 2026 |
| UniProt | REST API | **P04629** (NTRK1 / TrkA) |
| AlphaFold DB · AlphaMissense | AlphaFold DB annotation files | **AF-P04629-F1** |
| GTEx (bulk expression) | via Open Targets `baselineExpression` | as served by release 26.09 |
| Tabula Sapiens (single-cell) | via Open Targets `baselineExpression` | as served by release 26.09 |
| DepMap (essentiality) | via Open Targets `depMapEssentiality` | as served by release 26.09 |
| Mouse knockout phenotypes | via Open Targets `mousePhenotypes` | as served by release 26.09 |

Reference transcript for the variant analysis: **NM_002529.4**.

## Licences

Checked October 2026. Licences change; verify before any reuse beyond reading.

- **Open Targets Platform data** is released under **CC0 1.0** (public domain
  dedication). Its pipelines and API are Apache 2.0.
- **AlphaMissense predictions** are released under **CC BY 4.0** — attribution
  required, no non-commercial or ShareAlike restriction. Cite Cheng *et al.*,
  *Science* (2023).
- **GTEx, UniProt, Reactome and Ensembl** data redistributed through Open
  Targets are **CC BY 4.0**.
- **ClinVar, IntAct and SIGNOR** are served under **EMBL-EBI terms of use**.
- **ChEMBL** and the **Human Protein Atlas** are **CC BY-SA 3.0**. The
  tractability, known-drug and chemical-probe columns used by the opportunity
  map derive from ChEMBL, so a derived table containing them carries a
  ShareAlike obligation.
- **Cancer Gene Census** (the source of the cancer-role flag) carries
  **restrictions on commercial use**. This repository is academic and
  non-commercial; a commercial reuser must obtain their own licence.

Open Targets maintains the per-source list at
<https://platform-docs.opentargets.org/licence>, which is the authoritative
reference for anything above.

## What this means for the files in this repository

`data/processed/` contains **derived aggregates** — counts, flags, fold-changes
and declared tiers — not redistributed source datasets. `data/raw/` holds the
cached API responses and is deliberately **not tracked**; the notebook
regenerates it, and the manifests record which release each snapshot came from.

## Disclaimer

AlphaMissense has not been validated for, and is not approved for, any clinical
use. Neither has anything else in this repository. The output is a prioritised
list of hypotheses produced from public data, with no experimental validation of
any kind. It is not clinical guidance and must not be read as any.

## Citing the resources

If you build on this work, cite the underlying resources rather than this
repository: Open Targets Platform, Pharos/IDG, ClinVar, UniProt, AlphaFold DB
and AlphaMissense, GTEx, Tabula Sapiens, DepMap, and the Mouse Genome
Informatics phenotype data served through Open Targets.
