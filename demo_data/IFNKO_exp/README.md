# IFN chimera demo

This directory provides a very small simulated dataset for demonstrating the expected input structure of the `IFNKO_exp/` analyses.

## Files

- `reference_cell_metadata_demo.csv`
  - small reference single-cell metadata table

- `query_cell_metadata_demo.csv`
  - small chimera query-cell metadata table

- `pseudobulk_reference_demo.csv`
  - genes x reference pseudo-bulk samples

- `bulk_counts_demo.csv`
  - genes x bulk samples for chimera-like conditions

## Notes

- The full workflow uses `.h5ad` inputs and scSemiProfiler-specific objects.
- This demo is a lightweight table-based representation for repository demonstration and manuscript submission support.
