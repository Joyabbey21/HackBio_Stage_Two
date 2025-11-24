
### **Single-Cell RNA-seq Analysis of a Bone-Marrow Dataset**

---

## 🔍 **Overview**

This project performs a complete single-cell RNA-sequencing (scRNA-seq) analysis using Python and Scanpy. The goal is to:

1. **Load and preprocess** a bone-marrow–derived dataset.
2. **Perform clustering and dimensionality reduction** (UMAP).
3. **Annotate immune cell types** using PanglaoDB reference signatures and decoupler/ULM scoring.
4. **Interpret the biological landscape**: lineage structure, progenitors, and immune-state profiling.
5. **Assess whether the sample is truly bone marrow**.
6. **Infer whether the patient is healthy or infected** based on cell-type proportions.

All analyses were performed in the notebook:
`stage2_code.py` (converted from a Jupyter notebook).

---

## 🧪 **What I Did**

### **1. Data Processing**

* Loaded the gene-expression matrix into an AnnData object.
* Filtered low-quality cells and lowly expressed genes.
* Normalized counts, log-transformed data, and identified highly variable genes.
* Regressed unwanted sources of variation (mitochondrial and ribosomal content).
* Performed PCA and computed a nearest-neighbors graph.

### **2. Dimensionality Reduction & Clustering**

* Ran **UMAP** to visualize the manifold structure.
* Applied **Leiden clustering** at multiple resolutions.
* Exported cell embeddings and cluster labels.

### **3. Cell-Type Annotation**

* Used **decoupler** (ULM scoring) with **PanglaoDB immune signatures**.
* Identified major immune populations including:

  * T cells
  * NK cells
  * Monocytes
  * Memory B cells
  * Plasma cells
  * Dendritic cells
  * Hematopoietic stem/progenitor cells (HSPCs)

### **4. Biological Interpretation**

* Evaluated lineage completeness (presence/absence of erythroid, granulocyte, progenitor, lymphoid, etc.).
* Compared cell-type frequencies to expected profiles for PBMCs vs bone marrow.
* Assessed immune activation states (monocyte activation, NK cytotoxicity, lymphocyte depletion).

---

## 🧫 **What I Found**

### **1. Tissue Source**

* The presence of **HSPCs** and **plasma cells** strongly supports **bone marrow origin**.
* Absence of erythroid & granulocyte populations suggests **mononuclear-enriched bone marrow**, not whole marrow.
* Final conclusion: **Bone Marrow Mononuclear Cells (BMMCs)**.

### **2. Patient Immune Status**

* No neutrophil or granulocyte expansion
* No inflammatory monocyte signature
* NK cells not hyperactivated
* Normal lymphocyte frequencies

**Conclusion:**
The patient shows **no transcriptional evidence of acute infection**, consistent with a **healthy or steady-state immune profile**.

---

Got it — you want the **README “How to Run” section** to follow **exactly the same procedure shown in your actual code**
(meaning: using **Google Colab**, installing packages with `!pip install`, downloading data with `!wget`, and running the sequential cells).

Below is a perfect, polished README section **tailored to your exact workflow**, based entirely on the code you uploaded.
You can copy and paste this directly into your README.

---

# ✅ **How to Run the Analysis (Exactly the Same Way as in the Code)**

### *Google Colab Workflow — Fully Reproducible*

This entire project was run on **Google Colab**, and the analysis can be reproduced by following the exact steps below.

---

## ▶️ **1. Open the project in Google Colab**

Go to:

[https://colab.research.google.com](https://colab.research.google.com)

Create a **New Notebook**, or upload the `.ipynb` version of this script.

---

## ▶️ **2. Install all required packages (same as used in the script)**

Run the following cell *exactly as shown in the notebook*:

```python
!pip install scanpy
!pip install anndata
!pip3 install igraph
!pip install celltypist
!pip install decoupler
!pip install fa2-modified
!pip install crc32c
```

These commands install all libraries used in the workflow:
`scanpy`, `anndata`, `igraph`, `celltypist`, `decoupler`, and additional dependencies.

---

## ▶️ **3. Download the dataset (exact method used in the code)**

Run the same download command:

```python
!wget https://github.com/josoga2/sc/raw/refs/heads/main/bone_marrow.h5ad
```

This ensures the dataset is identical to the one used in the analysis.

---

## ▶️ **4. Load the dataset**

Then run:

```python
import scanpy as sc
import anndata as ad
bone_marrow_df = sc.read('bone_marrow.h5ad')
```

This loads the bone marrow AnnData object into memory.

---

## ▶️ **5. Run the notebook cells sequentially**

From this point onward, simply execute each cell **in order**, as the pipeline is structured linearly:

### ✔ Quality control (QC)

– Filtering mitochondrial genes
– Filtering ribosomal & HB genes
– QC metrics
– Cell filtering
– Gene filtering
– Doublet detection

### ✔ Normalization & transformation

– Save counts layer
– Normalize
– Log transform

### ✔ Feature selection

– Highly variable genes

### ✔ Dimensionality reduction

– PCA
– Neighborhood graph
– UMAP

### ✔ Clustering

– Multiple Leiden resolutions
– Visualize cluster structure

### ✔ Annotation

– Download biomart gene mappings
– Fetch PanglaoDB markers
– Run ULM scoring with decoupler
– Rank markers by cluster
– Map clusters to biological cell types

### ✔ Visualization

– UMAP plots (raw, cluster, annotated)
– Violin plots
– Gene-set score visualization

Each block of code in `stage2_code.py` matches a step in this workflow.
Running all cells sequentially reproduces the full analysis.

---

## ▶️ **6. Accessing Outputs**

Plots are displayed directly in the Colab output cells, including:

* QC violin plots
* PCA loadings
* UMAP embeddings (colored by clusters, cell types, and scores)
* Decoupler score visualizations
* Violin plots of marker scores
