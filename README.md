# BET 2026 MFCL Input Bundle

This repository provides the BET 2026 starter input bundle for
`PacificCommunity/ofp-sam-tuna-flow`.

The workflow logic lives in `ofp-sam-tuna-flow`. This repository stores only
assessment-specific MFCL inputs and lightweight metadata:

- `mfcl/inputs/2023_4region`: BET 2026 4-region MFCL input files.
- `metadata/`: optional labels and maps used by plots and reports.

The MFCL executable is intentionally not stored in this public input bundle. The
starter Docker image provides it at `/home/mfcl/mfclo64`.

## Flow Defaults

Use these settings in `ofp-sam-tuna-flow`:

```r
Sys.setenv(
  FLOW_SPECIES = "BET",
  FLOW_SPECIES_LABEL = "Bigeye tuna",
  FLOW_ASSESSMENT_YEAR = "2026",
  FLOW_SOURCE_REPO = "PacificCommunity/ofp-sam-bet2026-inputs",
  FLOW_SOURCE_REF = "main",
  FLOW_BASE_INPUT_DIR = "mfcl/inputs/2023_4region",
  FLOW_MFCL_PROGRAM = "/home/mfcl/mfclo64"
)
```

Sensitivity recipes should copy from `FLOW_BASE_INPUT_DIR`, write a new input
directory under `mfcl/inputs/`, and leave explicit metadata describing what was
changed.

