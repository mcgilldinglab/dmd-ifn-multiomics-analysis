# Sex-chimeric scRNA-seq demo

This directory provides a very small simulated dataset for demonstrating the expected inputs used by `scRNA_analysis/`.

## Files

- `expression_matrix_demo.csv`
  - genes x cells expression matrix

- `cell_metadata_demo.csv`
  - per-cell metadata with `cell_id`, `dataset_group`, `pred_sex`, and `cluster`

- `predicted_labels_dataset_1.csv` to `predicted_labels_dataset_4.csv`
  - small CellSexID-like prediction files
  - one `Prediction` column per file

## Notes

- The main notebook uses full 10x matrices and AnnData objects; this demo is a lightweight substitute for repository demonstration only.
- The four prediction files mirror the naming convention already used in `scRNA_analysis/CellSexID_pred/`.
