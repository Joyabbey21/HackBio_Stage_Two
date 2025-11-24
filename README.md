
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

## ▶️ **How to Run the Notebook**

### **1. Install dependencies**

(Your notebook uses Scanpy, decoupler, and standard scientific libraries.)

```bash
pip install scanpy decoupler pandas numpy matplotlib seaborn
```

```bash
pip install anndata umap-learn scikit-learn
```

### **2. Run the notebook**

If using Jupyter:

```bash
jupyter notebook
```

If the script is `.py`, just run:

```bash
python stage2_code.py
```

---

## **Outputs**

The analysis generates:

* **UMAP plots** for:

  * Leiden clusters
  * Cell-type annotations
  * Stem/progenitor cell distribution
  * Individual signature heatmaps
* **Cluster annotations** saved inside the AnnData object
* **Interpretation notes** for biological context

---

## Final Notes

This analysis provides a high-confidence classification of both the tissue source and immune status. The workflow is fully reproducible and can be extended with differential expression, trajectory inference, or additional signature scoring.

