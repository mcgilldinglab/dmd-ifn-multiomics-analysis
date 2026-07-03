# Analysis code for type I IFN and DMD mouse studies

This repository contains analysis code for the manuscript **“Type I Interferon Drives Trained Immunity and Exacerbates Duchenne Muscular Dystrophy”**. The codebase covers mouse sex-chimeric single-cell RNA-seq, human bulk and single-nucleus RNA-seq, and IFNAR1 chimera analyses.

Processed and raw study data will be released separately once the manuscript is accepted. For software demonstration and repository review, small demo datasets are included under `demo_data/`.

## Repository structure

| Folder | Description |
|--------|-------------|
| `scRNA_analysis/` | Mouse sex-chimeric single-cell RNA-seq and RNA velocity analysis. |
| `human_analysis/` | Human bulk RNA-seq and single-nucleus RNA-seq workflows. |
| `IFNKO_exp/` | IFNAR1 chimera label transfer, pseudo-bulk matching, and scSemiProfiler deconvolution. |
| `demo_data/` | Small demo datasets for repository demonstration, including real-data subsets and one runnable bulk RNA-seq demo. |

## 1. System requirements

### Operating system

The repository was prepared and checked on a Linux system running:

- Ubuntu 20.04.6 LTS
- Linux kernel `5.4.0-216-generic`
- x86_64 architecture

Linux is the recommended operating system for the full workflows because the repository includes shell-based RNA-seq processing steps and Jupyter notebooks.

### Software dependencies

The repository contains three analysis branches with different dependencies.

Pinned dependency versions are provided in:

- `requirements.txt` for Python packages
- `requirements_R.txt` for R packages
- `requirements_tools.txt` for command-line tools

### Tested environment

This repository was prepared and checked in a Linux environment with:

- Ubuntu 20.04.6 LTS
- Python 3.10.12
- R 3.5.1

For reproducibility, users should install the package set required for the specific analysis branch they intend to run.

### Hardware requirements

- No non-standard hardware is required for the included demo dataset.
- GPU is not required for the included demo dataset or the standard preprocessing and differential expression steps.
- A normal desktop or laptop is sufficient for the demo.
- For full single-cell and velocity analyses on real data, a higher-memory Linux machine is recommended. In practice, `>= 32 GB RAM` is advisable for comfortable processing of large AnnData objects and intermediate files.

## 2. Installation guide

### Installation instructions

Install the repository from GitHub and then install the dependencies required for the analysis branch you plan to run.

1. Clone the repository from GitHub.
2. Enter the repository directory.
3. Create and activate a conda environment.
4. Install the Python dependencies in `requirements.txt`.
5. Install the R and Bioconductor dependencies listed in `requirements_R.txt`.
6. Install the command-line tools listed in `requirements_tools.txt`, if needed for your workflow.

Example commands:

```bash
git clone https://github.com/mcgilldinglab/dmd-ifn-multiomics-analysis.git
cd dmd-ifn-multiomics-analysis

conda create -n dmd_ifn_demo python=3.10.12 -y
conda activate dmd_ifn_demo

pip install -r requirements.txt
```

For workflows that require R packages or external command-line tools, install the software listed in `requirements_R.txt` and `requirements_tools.txt`. Additional workflow-specific notes are provided in the subfolder README files.

### Typical installation time

On a normal desktop computer with a stable internet connection:

- Python package installation: about 10 to 20 minutes
- R/Bioconductor package installation: about 10 to 30 minutes
- Total typical setup time: about 20 to 45 minutes

Installation time may be longer if large compiled dependencies must be built locally.

## 3. Demo

### Included demo datasets

Small demo datasets are provided under `demo_data/` for all three analysis branches:

- `demo_data/scRNA_analysis/`
- `demo_data/human_bulk_rnaseq/`
- `demo_data/human_single_nucleus/`
- `demo_data/IFNKO_exp/`

The included demo datasets consist of small example inputs for the repository workflows. Detailed demo examples are provided in `demo_data/README.md`.

### Instructions to run the demo

From the repository root, run:

```bash
Rscript human_analysis/bulk_rnaseq/differential_expression_deseq2.R \
  demo_data/human_bulk_rnaseq/gene_counts.matrix.txt \
  demo_data/human_bulk_rnaseq/demo_results
```

### Expected output

The demo command is expected to create:

- `demo_data/human_bulk_rnaseq/demo_results/counts_matrix.cleaned.csv`
- `demo_data/human_bulk_rnaseq/demo_results/PCA_plot.pdf`
- `demo_data/human_bulk_rnaseq/demo_results/MA_plot.pdf`

The other demo folders provide lightweight example inputs that document the expected input structure for the notebook-based workflows, but they are not full substitutes for the complete study inputs such as processed single-cell objects, 10x Genomics matrices, `.loom` files, or Cell Ranger outputs. See `demo_data/README.md` for detailed demo examples.

### Expected run time for the demo

For the included simulated bulk RNA-seq demo dataset:

- Expected run time on a normal desktop computer: less than 1 minute after dependencies are installed

## 4. Instructions for use

Instructions for running the software on your own data are provided in the subfolder README files:

- `scRNA_analysis/README.md`
- `human_analysis/README.md`
- `human_analysis/bulk_rnaseq/README.md`
- `human_analysis/single_nucleus_rnaseq/README.md`
- `IFNKO_exp/README.md`

In brief:

- Use `scRNA_analysis/` for the mouse sex-chimeric single-cell and RNA velocity workflows.
- Use `human_analysis/` for human bulk RNA-seq and single-nucleus RNA-seq workflows.
- Use `IFNKO_exp/` for IFNAR1 chimera label transfer, pseudo-bulk matching, and scSemiProfiler deconvolution.

## Contact

For questions about the code or data, please contact **Jiahui Tan** at `jiahui.tan@mail.mcgill.ca`.

## License

This analysis code is released under the **MIT License**.
