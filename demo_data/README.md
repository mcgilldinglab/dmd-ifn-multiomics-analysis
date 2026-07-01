# Demo datasets

This directory contains small datasets for software demonstration and repository review.

## Included demos

- `human_bulk_rnaseq/`
  - Small simulated count matrix designed to run directly with `human_analysis/bulk_rnaseq/differential_expression_deseq2.R`
  - 12 genes x 6 samples
  - 3 `Healthy_*` samples and 3 `DMD_*` samples

- `human_single_nucleus/`
  - Real data subset
  - Compact counts table plus matching barcode metadata
  - Intended to document the expected input structure for `human_analysis/single_nucleus_rnaseq/`

- `scRNA_analysis/`
  - Real data subset
  - Includes a compact expression matrix, per-cell metadata, and short real prediction-file subsets
  - Intended to document the expected input structure for `scRNA_analysis/`

- `IFNKO_exp/`
  - Real data subset
  - Includes reference/query metadata and pseudo-bulk/bulk-like matrices
  - Intended to document the expected input structure for `IFNKO_exp/`

## Demo examples

### 1. Run the bulk RNA-seq demo

From the repository root:

```bash
Rscript human_analysis/bulk_rnaseq/differential_expression_deseq2.R \
  demo_data/human_bulk_rnaseq/gene_counts.matrix.txt \
  demo_data/human_bulk_rnaseq/demo_results
```

Expected output:

- `demo_data/human_bulk_rnaseq/demo_results/counts_matrix.cleaned.csv`
- `demo_data/human_bulk_rnaseq/demo_results/PCA_plot.pdf`
- `demo_data/human_bulk_rnaseq/demo_results/MA_plot.pdf`

Expected run time:

- Usually less than 1 minute after dependencies are installed

### 2. Run the human single-nucleus notebook on demo-style inputs

```bash
jupyter lab human_analysis/single_nucleus_rnaseq/bootstrap_analysis.ipynb
```

In the notebook, replace the input-loading paths with:

- `demo_data/human_single_nucleus/expression_matrix_demo.csv`
- `demo_data/human_single_nucleus/cell_metadata_demo.csv`

This demo is intended to illustrate how the notebook can be adapted to a small input table before running on the full processed dataset.

Expected output:

- Successful loading of the demo expression matrix and matching metadata
- A lightweight test that confirms the notebook environment and input format are set up correctly

Expected run time:

- Notebook launch: a few seconds
- Running only the input-loading and inspection cells: usually less than 1 minute

### 3. Run the scRNA-seq notebook with demo input placeholders

```bash
jupyter lab scRNA_analysis/scrna_analysis.ipynb
```

In the notebook, use the demo files below as lightweight stand-ins when testing path handling and expected input structure:

- `demo_data/scRNA_analysis/expression_matrix_demo.csv`
- `demo_data/scRNA_analysis/cell_metadata_demo.csv`
- `demo_data/scRNA_analysis/predicted_labels_dataset_1.csv`
- `demo_data/scRNA_analysis/predicted_labels_dataset_2.csv`
- `demo_data/scRNA_analysis/predicted_labels_dataset_3.csv`
- `demo_data/scRNA_analysis/predicted_labels_dataset_4.csv`

Expected output:

- Successful reading of the small prediction files
- Verification that the expected metadata columns and naming conventions are present before switching to full 10x inputs

Expected run time:

- Notebook launch: a few seconds
- Running the setup and input-reading cells: usually less than 1 minute

### 4. Run the IFNKO notebooks with demo matrices

```bash
jupyter lab IFNKO_exp/pseudobulk_analysis.ipynb
jupyter lab IFNKO_exp/label_transfer.ipynb
```

When testing these notebooks, use the demo files below as small placeholders for the corresponding full inputs:

- `demo_data/IFNKO_exp/pseudobulk_reference_demo.csv`
- `demo_data/IFNKO_exp/bulk_counts_demo.csv`
- `demo_data/IFNKO_exp/reference_cell_metadata_demo.csv`
- `demo_data/IFNKO_exp/query_cell_metadata_demo.csv`

Expected output:

- Successful loading of reference/query metadata tables
- Successful loading of overlapping pseudo-bulk and bulk matrices for similarity-testing logic

Expected run time:

- Notebook launch: a few seconds
- Running the setup and input-reading cells: usually less than 1 minute

For workflow-specific details on how to use these inputs with the full notebooks and scripts, see:

- `human_single_nucleus/README.md`
- `scRNA_analysis/README.md`
- `IFNKO_exp/README.md`
