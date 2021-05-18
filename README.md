# Single-cell mapping of GLP-1 and GIP receptor expression in the dosal vagal complex

## Methods

**Data integration**\
The single-cell atlases by Zhang et al. (1) and Ludwig et al. (2) were combined using Seurat (3) version 4.0.1. We integrated all cells and neurons separately using the same procedure. The count matrices from Zhang et al. were downloaded from https://github.com/jakaye/AP_scRNA and normalized using the function ‘NormalizeData’. The top variable genes were detected using ‘FindVariableFeatures’. Preprocessed data from Ludwig et al. were in-house. The atlases from Zhang et al. and Ludwig et al. were aligned using the functions ‘SelectIntegrationFeatures’, ‘FindIntegrationAnchors’, and ‘IntegrateData’ which use canonical correlation analysis followed by mutual nearest neighbor detection.
 
To assign cell type and neuronal population labels, the two integrated data sets (all cells and neurons) were clustered using ‘FindNeighbors’ and ‘FindClusters’ at a granularity that separated the different glial cell types and neuronal populations characterized by Zhang et al. and Ludwig et al. The clusters were annotated with the nomenclature from Ludwig et al. with the exception that Glu4 neurons were split into three clusters (Glu4a-c) as was done by Zhang et al.
 
**Expression specificity**\
The CELLEX (“CELL type EXpression-specificity”) tool (4) version 1.2.1 was used to compute gene expression specificity scores for the cell populations. We computed CELLEX scores for the atlases by Zhang et al. and Ludwig et al. separately and calculated combined expression specificity values using the mean of the two CELLEX scores. For cell populations that were only detected in the atlas by Ludwig et al., the expression specificity scores were based on the CELLEX values from this atlas alone. To identify cell population-specific receptors, we intersected the top 100 most specifically expressed genes in each cell population with receptors identified in the manually curated database CellTalkDB (5) of mouse receptors-ligand pairs.

**Enriched motifs**\
The position weight matrices for enriched motifs were identified using the 8th release (2020) of the JASPAR database (6).  

## References
1. Zhang C, Kaye JA, Cai Z, Wang Y, Prescott SL, Liberles SD. Area Postrema Cell Types that Mediate Nausea-Associated Behaviors. Neuron. 2021 Feb 3;109(3):461-472.e5.
2. Ludwig MQ, Cheng W, Gordian D, Lee J, Paulsen SJ, Hansen SN, et al. A genetic map of the mouse dorsal vagal complex and its role in obesity. Nat Metab. 2021 Mar 25;1–16.
3. Stuart T, Butler A, Hoffman P, Hafemeister C, Papalexi E, Mauck WM, et al. Comprehensive Integration of Single-Cell Data. Cell. 2019 Jun 13;177(7):1888-1902.e21.
4. Timshel PN, Thompson JJ, Pers TH. Genetic mapping of etiologic brain cell types for obesity. Loos R, Barkai N, editors. eLife. 2020 Sep 21;9:e55851.
5. Shao X, Liao J, Li C, Lu X, Cheng J, Fan X. CellTalkDB: a manually curated database of ligand-receptor interactions in humans and mice. Brief Bioinform. 2020 Nov 4.
6. Fornes O, Castro-Mondragon JA, Khan A, van der Lee R, Zhang X, Richmond PA, et al. JASPAR 2020: update of the open-access database of transcription factor binding profiles. Nucleic Acids Res. 2020 Jan 8;48(D1):D87–92.

