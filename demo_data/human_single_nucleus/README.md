# Human single-nucleus demo

This directory provides a very small simulated dataset for demonstrating the expected input structure of the `human_analysis/single_nucleus_rnaseq/` workflow.

## Files

- `expression_matrix_demo.csv`
  - genes x cells expression matrix
  - first column is `gene`
  - remaining columns are demo cell barcodes

- `cell_metadata_demo.csv`
  - per-cell metadata
  - includes `cell_id`, `condition`, and `cell_type`

## Notes

- This demo is intentionally small and is not a substitute for the full processed AnnData object used in the main notebook workflow.
- It is included to satisfy software demonstration and repository documentation requirements.
