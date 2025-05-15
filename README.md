# Basic Spatial RNA-Seq Analysis using Scanpy

Welcome to this repository – a hands-on, story-driven walkthrough for exploring the world of single-cell and spatial transcriptomics using Python. This repository is designed for scientists, students, and enthusiasts who want to understand not just the *how*, but also the *why* behind each step of a modern transcriptomics analysis pipeline.

## Spatial-map of mouse brain (coronal section)
![]()

## Clustering of spatial data (UMAP)
![]()

## Introduction

Imagine you’re looking at a beautiful city from above. Each building is unique, but together they form neighborhoods, districts, and the city as a whole. In biology, our “city” is a tissue, and the “buildings” are cells. Traditional RNA-seq lets us measure the average activity of all buildings together, but what if we want to know what each building is doing? Or how neighborhoods are organized? That’s where **single-cell RNA sequencing (scRNA-seq)** and **spatial transcriptomics** come in. Specifically, the data comes from a 10x Genomics Visium spatial transcriptomics experiment performed on a section of mouse brain. This is a widely used demonstration dataset provided by 10x Genomics and featured in tutorials such as the one at [cell2location website](https://cell2location.cog.sanger.ac.uk/)

With these technologies, we can:
- **Zoom in** to see what each cell is expressing.
- **Map** where each cell is located within the tissue.
- **Discover** new cell types, states, and spatial patterns.

But how do we turn raw data into biological insight? That’s the journey this script will take you on.

---

## What This Script Does

This Python script is a complete, well-commented pipeline for analyzing single-cell and spatial transcriptomics data, especially from the popular 10x Genomics Visium platform. It guides you through:

1. **Loading and inspecting your data:** Understand what’s inside your dataset.
2. **Quality control:** Identify and remove low-quality cells and genes.
3. **Normalization and transformation:** Make gene expression values comparable across cells.
4. **Finding the most interesting genes:** Focus on genes that vary the most between cells.
5. **Dimensionality reduction:** Simplify complex data into two or three dimensions for visualization.
6. **Clustering:** Group similar cells together to find cell types or states.
7. **Spatial visualization:** See where different cells and genes are located in the tissue.
8. **Marker gene discovery:** Identify genes that define each cluster or cell type.
9. **Interpretation:** Visualize and interpret results to generate biological hypotheses.

Every step is explained in plain language, with comments in the code to help you understand *why* each action is taken.

---

## How to Use This Repository

**Step 1: Install the required Python packages**

You’ll need Python 3.8 or higher, and the following packages: scanpy, anndata, seaborn, matplotlib, leidenalg, pandas, and numpy.

Install them with:

pip install scanpy anndata seaborn matplotlib leidenalg pandas numpy

**Step 2: Download the data**

- Download a sample spatial transcriptomics dataset, such as the [mouse brain Visium data](https://cell2location.cog.sanger.ac.uk/tutorial/mouse_brain_visium_wo_cloupe_data.zip), and extract it into a folder called `data/`.
- Download a ribosomal gene list (for example, from [MSigDB KEGG_RIBOSOME](https://www.gsea-msigdb.org/gsea/msigdb/cards/KEGG_RIBOSOME.html)) as a CSV file and place it in the `data/` folder.

**Step 3: Run the script**

- Place the script (e.g., `scRNAseq_spatial_analysis.py`) in your project directory.
- Adjust the `sp_data_folder` variable if your data is in a different location.
- Run the script from the command line:

python scRNAseq_spatial_analysis.py

Or, open it in a Jupyter notebook for interactive exploration.

---

## What You'll Learn

By following this script, you’ll learn:

- How to inspect and understand the structure of single-cell and spatial transcriptomics data.
- Why quality control is crucial, and how to spot and remove problematic cells or genes.
- The importance of normalization and log transformation for fair comparisons.
- How to identify highly variable genes that drive biological differences.
- How to use PCA and UMAP to visualize complex data in a simple way.
- How clustering algorithms can reveal hidden cell types or states.
- How to overlay gene expression and cluster information onto tissue images.
- How to find marker genes that define each cluster, and how to interpret them biologically.

---

## Data Requirements

- **Spatial transcriptomics data** in 10x Genomics Visium format (or similar). The script expects the filtered feature-barcode matrix and associated images.
- **Ribosomal gene list** as a CSV file (for example, from MSigDB).

Place all required files in a directory named `data/` by default.

---

## Detailed Workflow

Here’s the story your data will go through:

1. **Arriving at the city gates:**  
   The script loads your dataset and gives you a first look at the “city” — how many cells (buildings) and genes (features) are present.

2. **City census and cleanup:**  
   Not all buildings are in good shape. Some are empty, some are falling apart. The script checks for cells with too few or too many transcripts, high mitochondrial or ribosomal content (which can indicate stress or technical artifacts), and removes them.

3. **Leveling the playing field:**  
   Each building is different in size, but we want to compare them fairly. The script normalizes the data so each cell has the same total transcript count, then log-transforms the values to reduce the effect of outliers.

4. **Finding the most interesting buildings:**  
   Not all genes are equally informative. The script identifies the most variable genes — those that change the most across cells — to focus the analysis.

5. **Mapping the neighborhoods:**  
   Using PCA and UMAP, the script reduces the data to two dimensions, making it possible to visualize relationships between cells.

6. **Discovering neighborhoods:**  
   The Leiden algorithm groups cells into clusters (“neighborhoods”) based on their gene expression profiles.

7. **Painting the city map:**  
   The script overlays clusters and gene expression onto the tissue image, showing where different cell types or states are located.

8. **Finding the city’s signature features:**  
   For each cluster, the script identifies marker genes — the “landmarks” that define each neighborhood.

9. **Interpreting the city’s organization:**  
   By examining marker genes and their spatial patterns, you can start to understand the biological organization of your tissue.

---

## Outputs and Insights

As you run the script, you’ll see:

- **Summary statistics** about your data at each step.
- **Plots** showing quality control metrics, gene expression distributions, and dimensionality reduction.
- **Spatial maps** overlaying gene expression and clusters on tissue images.
- **Lists of marker genes** for each cluster, ready for further biological interpretation.
- **Dotplots and heatmaps** to compare marker gene expression across clusters.

These outputs will help you answer questions like:
- What cell types are present in my tissue?
- How are they organized spatially?
- What genes define each cell type or region?

---

## License

This project is licensed under the MIT License.

---

**Questions or suggestions?**  
Open an issue or submit a pull request — let’s explore the city of cells together!
