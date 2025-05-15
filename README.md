# Single Cell RNA-Seq & Spatial Transcriptomics Analysis


## Overview

This repository provides a comprehensive, well-commented Python script for analyzing single-cell RNA sequencing (scRNA-seq) and spatial transcriptomics data using [Scanpy](https://scanpy.readthedocs.io/) and [AnnData](https://anndata.readthedocs.io/). The workflow is designed for both beginners and advanced users interested in exploring gene expression at single-cell resolution, with a focus on 10x Genomics Visium spatial data.

The script covers the entire analysis pipeline, including:

- Data loading and inspection
- Quality control and filtering
- Normalization and log transformation
- Identification of highly variable genes
- Dimensionality reduction (PCA, UMAP)
- Clustering (Leiden algorithm)
- Marker gene detection and visualization
- Spatial mapping of gene expression

## Why Use This Script?

- **Educational:** Each step is clearly commented, making it easy to follow and adapt for your own data.
- **Reproducible:** The workflow is linear and can be run as a single script or interactively in a Jupyter notebook.
- **Flexible:** You can easily swap in your own datasets or modify parameters for different tissues or organisms.
- **Visualization-rich:** Includes spatial and dimensionality reduction plots to help interpret results.

## Getting Started

### 1. Prerequisites

- Python 3.8 or higher
- Scanpy
- AnnData
- Seaborn
- matplotlib
- leidenalg
- pandas
- numpy

You can install all dependencies using:

pip install scanpy anndata seaborn matplotlib leidenalg pandas numpy

### 2. Data

- **Spatial transcriptomics data:** Download a sample dataset, such as the mouse brain Visium data from [here](https://cell2location.cog.sanger.ac.uk/tutorial/mouse_brain_visium_wo_cloupe_data.zip), and extract it into a folder named `data/`.
- **Ribosomal gene list:** Download from [MSigDB KEGG_RIBOSOME](https://www.gsea-msigdb.org/gsea/msigdb/cards/KEGG_RIBOSOME.html) as a CSV and place it in the `data/` folder.

### 3. Usage

- Place the script (for example, `scRNAseq_spatial_analysis.py`) in your project directory.
- Adjust the `sp_data_folder` path if your data is located elsewhere.
- Run the script:

python scRNAseq_spatial_analysis.py

Or, for interactive exploration, run the code in a Jupyter notebook.

### 4. Output

The script will print summaries and statistics at each step.  
It will generate multiple plots, including:

- QC histograms and violin plots
- Spatial gene expression overlays
- UMAP embeddings colored by clusters and gene expression
- Marker gene heatmaps and dotplots

## How Can This Help You?

- Learn best practices for scRNA-seq and spatial transcriptomics analysis.
- Quickly QC and explore your own single-cell or spatial data.
- Identify cell types and marker genes in your tissue of interest.
- Visualize spatial gene expression and cluster structure in tissue sections.
- Adapt and extend the script for your research or teaching needs.

## References

- [Scanpy: Single-Cell Analysis in Python](https://scanpy.readthedocs.io/)
- [AnnData: Annotated Data](https://anndata.readthedocs.io/)
- [10x Genomics Visium](https://www.10xgenomics.com/products/spatial-gene-expression)
- [MSigDB KEGG Ribosome Gene Set](https://www.gsea-msigdb.org/gsea/msigdb/cards/KEGG_RIBOSOME.html)

## License

This project is licensed under the MIT License.

---

**Questions or suggestions?**  
Feel free to open an issue or submit a pull request!
