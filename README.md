**Name: Joy Abiodun  
  Team: Glycine  
  Stage: Two**
 
 
 **Clear Evidence-Driven Answers**

**1\. _What cell types did you identify?_**

**_List each annotated cluster. No need for a novel classification system. Just show you understand what you're looking at._**

The following cell types were identified from the dataset (one per Leiden cluster):

- B cells memory
- T cells  

- Natural killer T cells  

- Monocytes  

- Hematopoietic stem/progenitor cells (HSPCs)  

- Dendritic cells  

- Plasma cells

### **2. _Explain the biological role of each cell type_**

### **_For every annotated label, give a short explanation of what that cell type actually does in bone marrow or peripheral immunity._**

### **  

**1\. B cells (memory B cells)**

Long-lived B lymphocytes that "remember" past infections. They rapidly produce antibodies upon re-exposure to an antigen, enabling fast and strong secondary immune responses.

### **2\. T cells**

Central regulators of adaptive immunity. They rescognize peptide antigens, kill infected or abnormal cells (CD8⁺), or coordinate immune activity via cytokines (CD4⁺ helper T cells).

### **3\. Natural Killer T cells (NKT cells)**

Hybrid innate-adaptive lymphocytes. They respond rapidly to lipid antigens, produce large amounts of cytokines, and help control tumors, infections, and inflammation.

### **4\. Monocytes**

Circulating phagocytes that migrate into tissues and differentiate into macrophages or dendritic cells. They engulf pathogens, clean debris, and present antigens to T cells.

### **5\. Hematopoietic Stem/Progenitor Cells (HSPCs)**

Self-renewing stem cells in bone marrow that give rise to all blood cell lineages (myeloid and lymphoid). They maintain lifelong blood and immune cell production.

### **6\. Dendritic cells**

Professional antigen-presenting cells. They capture antigens, migrate to lymph nodes, and activate naïve T cells, initiating adaptive immune responses.

### **7\. Plasma cells**

Terminally differentiated B cells that act as antibody-secreting factories. They produce large amounts of high-affinity antibodies essential for pathogen clearance.

- **_Is the tissue source really bone marrow? Justify your answer_**

**_Your job is to reason your way toward (or away from) that conclusion using:_**

**_expected vs. missing lineage populations_**

**_typical frequency distributions_**

**_presence or absence of progenitors_**

**_If you claim bone marrow, explain the flaws in your logic. Otherwise, justify it biologically. Hand-waving is a fail._**

Yes! The data _most likely_ comes from **bone marrow**, but specifically from a **bone-marrow mononuclear cell (BMMC)** prep rather than an unfiltered whole marrow slurry. The strongest support is the presence of **hematopoietic stem/progenitor cells (HSPCs)** and **plasma cells** together with classical lymphoid and myeloid mononuclear populations; the main weakness is the apparent **absence of strong erythroid/granulocyte (neutrophil) signatures**, which is consistent with a mononuclear-cell preparation or with filtering steps in your pipeline.

# **1a. Expected vs. Missing Lineage Populations**

### **Expected Lineages (should be present in true bone marrow)**

- **Progenitors (HSPCs)** - correctly detected

_"HSPC label assigned by the pipeline… Progenitors… found only in bone marrow."_

- **Plasma cells** - expected in marrow, present

_"Presence of plasma cells… long-lived plasma cells are resident in bone marrow."_

- **Mixture of adaptive + innate mononuclear cells**

_"Co-occurrence of both progenitors and tissue-resident populations… memory B cells, plasma cells, dendritic cells…"_

### **1b. Missing / Weak Lineages (should appear in whole marrow but did not)**

**Erythroid lineage missing** (HBA/HBB/GYPA)

_"Missing/weak erythroid and granulocyte signals… abundant erythroid-lineage cells… Their absence argues against raw whole marrow."_

**Granulocytes missing** (ELANE, MPO, neutrophil precursors)

_"Whole (unfractionated) bone marrow usually shows… granulocyte-lineage cells… Their absence argues against raw whole marrow."_

# **2\. Typical Frequency Distributions**

### **PBMC-like composition**

(T cells, B cells, NK, monocytes)

_"Relatively PBMC-like cell composition (T/B/NK/monocytes)… resembles PBMCs…"_

BUT…

### **Deviates from PBMC because**

PBMCs do **not** contain:  
**HSPCs** 
**Plasma cells**

_"…presence of HSPCs tips the scale back toward marrow…"_

Thus the frequency distribution is:

- PBMC-type mononuclear cells → **present**
- Bone-marrow-specific populations (HSPCs, plasma cells) → **present**
- Whole-marrow lineages (neutrophil/erythroid) → **absent**

This pattern supports: **bone marrow mononuclear fraction**.

# **3\. Presence or Absence of Progenitors**

### **Presence (strong evidence)**

✔ **HSPCs detected**

_"HSPC label assigned… Progenitors… normally found only in bone marrow."_

### **Biological significance**

- Progenitors are rare in PBMCs  

- Their presence strongly indicates **bone marrow origin**

**4\. Based on the relative abundance of cell types, is the patient healthy or infected?**

The cellular composition is most consistent with a non-acutely infected, steady-state immune environment rather than an active infection. First, there is no detectable neutrophil or neutrophil-precursor population (ELANE⁺, MPO⁺, or S100A8/A9⁺ clusters), which would normally expand during acute bacterial infection or systemic inflammation. The absence of granulocytic cells strongly argues against an acute inflammatory response. Second, monocytes are present but not disproportionately expanded, and there is no evidence of an inflammatory monocyte signature (e.g., IL1B, S100A8/A9), which would be expected in infection-driven emergency myelopoiesis. Third, the NK cell cluster does not show elevated cytotoxic markers (such as PRF1, GZMB, GNLY, or NKG7) that typically indicate viral infection or heightened innate activation. Finally, lymphocyte frequencies appear balanced: T cells and memory B cells are present at expected proportions without signs of lymphopenia or reactive lymphoid expansion. Plasma cells are detectable but not abnormally increased, consistent with baseline antibody maintenance rather than a recent immune surge.

Taken together, no neutrophil expansion, no monocyte activation, no NK hyperactivation, and no lymphocyte collapse, the dataset shows no cellular signature of acute infection. The most scientifically supported conclusion is that the patient is likely healthy or in a non-inflamed physiological state, consistent with typical bone-marrow mononuclear cell composition.
