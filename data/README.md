# data/

> **MOCK DATA.** Every file in this directory is synthetic, generated on 2026-11-11 to exercise the folder layout,
> file naming and validator before real Cycle 1 data exist. Values are plausible but meaningless. Do not analyze or cite.
> Replace (do not edit) these files when real submissions arrive; rows carry `notes = MOCK DATA` so stragglers are easy to find.

**Scope:** Gamete mechanism component (cycle code `GAM`): primed broodstock, gamete and larval samples, sequencing libraries, qPCR gene expression. Reads live off-repo (see `raw/sequencing/`).

**Nodes:** UW, NOAA NWFSC and VIMS (the R&D subgroup).

## Layout

```
data/
  <NODE>/
    raw/         files exactly as submitted by the node; never edited after upload
    processed/   outputs of versioned code (record pipeline_version); regenerate, don't hand-edit
  hub/           Coordinator / cross-node tables
```

## Conventions (Oyster CAP Data Dictionary v0.1)

- File names: `{table}_{NODE}_{CYCLE}_{YYYYMMDD}_v{n}.csv` (date = submission date). A correction is a new version file, never an overwrite.
- UTF-8 CSV, one header row with the exact dictionary field names, in dictionary order.
- `NA` for not measured / not applicable; blank cells are invalid in required fields.
- Dates `YYYY-MM-DD`; manual datetimes ISO 8601 with offset; sensor datetimes UTC (`Z`).
- Records are flagged (`qc_flag`, `qartod_flag`), never deleted. A few mock rows carry flag 3/4 on purpose.
- Access tiers: only **Shared** fields belong in this repo. Restricted fields (e.g. exact `lat_dd`/`lon_dd`, `storage_location`) are left `NA` here; Confidential tables never appear.
- IDs follow the dictionary ID_Scheme (e.g. `C1-VIMS-B0007`, `C1-ARS-F031-T0458`, `VIMS-RZ-20271020-01`).

`raw/sequencing/fastq_manifest_*` and `processed/gene_expression_dct_*` are illustrative and not yet in the dictionary. GAM priming codes reuse C1 codes until OQ-9 is resolved.

## Inventory

| file | rows |
|---|---|
| `NOAA/processed/gene_expression_dct_NOAA_GAM_20271015_v1.csv` | 36 |
| `NOAA/raw/broodstock_NOAA_GAM_20271015_v1.csv` | 12 |
| `NOAA/raw/gene_expression_qpcr_NOAA_GAM_20271015_v1.csv` | 36 |
| `NOAA/raw/molecular_libraries_NOAA_GAM_20271015_v1.csv` | 48 |
| `NOAA/raw/samples_NOAA_GAM_20271015_v1.csv` | 24 |
| `NOAA/raw/sequencing/fastq_manifest_NOAA_GAM_20271015_v1.csv` | 96 |
| `UW/processed/gene_expression_dct_UW_GAM_20271015_v1.csv` | 36 |
| `UW/raw/broodstock_UW_GAM_20271015_v1.csv` | 12 |
| `UW/raw/gene_expression_qpcr_UW_GAM_20271015_v1.csv` | 36 |
| `UW/raw/molecular_libraries_UW_GAM_20271015_v1.csv` | 48 |
| `UW/raw/samples_UW_GAM_20271015_v1.csv` | 24 |
| `UW/raw/sequencing/fastq_manifest_UW_GAM_20271015_v1.csv` | 96 |
| `VIMS/processed/gene_expression_dct_VIMS_GAM_20271015_v1.csv` | 36 |
| `VIMS/raw/broodstock_VIMS_GAM_20271015_v1.csv` | 12 |
| `VIMS/raw/gene_expression_qpcr_VIMS_GAM_20271015_v1.csv` | 36 |
| `VIMS/raw/molecular_libraries_VIMS_GAM_20271015_v1.csv` | 48 |
| `VIMS/raw/samples_VIMS_GAM_20271015_v1.csv` | 24 |
| `VIMS/raw/sequencing/fastq_manifest_VIMS_GAM_20271015_v1.csv` | 96 |
