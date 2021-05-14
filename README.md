# Single-cell mapping of GLP-1 and GIP receptor expression in the dosal vagal complex

## Methods

**Data integration**\
The single-cell atlases by Zhang et al. and Ludwig et al. were integrated using Seurat (Stuart et al., Cell 2019) version 4.0.1. We generated a combined atlas by integrating all cells in the two data sets and subsequently integrating neurons only using the same procedure. The count matrices from Zhang et al. were downloaded from https://github.com/jakaye/AP_scRNA and normalized using the function ‘NormalizeData’. The top variable genes were detected using ‘FindVariableFeatures’. Preprocessed data from Ludwig et al. were obtained from in-house. The atlases from Zhang et al. and Ludwig et al. were aligned applying the functions ‘SelectIntegrationFeatures’, ‘FindIntegrationAnchors’, and ‘IntegrateData’ which use canonical correlation analysis followed by mutual nearest neighbor detection.
 
To assign cell type and neuronal populations labels, the two integrated atlases (all cells and neurons only) were clustered using ‘FindNeighbors’ and ‘FindClusters’ at a granularity that separated the different glial cell types and neuronal populations characterized by Ludwig et al. The clusters were annotated with the nomenclature from Ludwig et al. with the exception that Glu4 neurons were split into three clusters (Glu4a-c) as was done by Zhang et al.
 
**Expression specificity**\
The CELLEX (“CELL type EXpression-specificity”) tool (Timshel et al., eLife 2020) version 1.1.1 was used to compute gene expression specificity scores for cell populations. We computed CELLEX scores for the atlases by Zhang et al. and Ludwig et al. separately and computed combined expression specificity values using the mean of the two CELLEX scores. For cell populations that were only detected in the atlas by Ludwig et al., the expression specificity scores were computed based on the atlas by Ludwig et al. alone. To identify cell population-specific receptors, we intersected the top 100 most specifically expressed genes in each cell population with receptors identified in the manually curated database CellTalkDB (Shao et al., 2020) of mouse receptors-ligand pairs.
