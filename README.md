# Airway tree geometry characterised using topological data analysis
## Abstract
Computed tomography images, combined with advanced segmentation software, enable the reconstruction of three-dimensional airway structures. However, existing analysis frameworks are not designed to quantify airways in 3D ambient space, leaving the relationship between 3D airway morphology and biomedical features largely unexplored. To fill this research gap, we propose airway analysis frameworks based on topological data analysis, specifically, persistent homology transform, to comprehensively characterize multiscale and multidirectional 3D branching information. By testing our methods against multiple segmentation tools and parameter settings, we prove the robustness of our methods as well as their ability to reliably extract 3D anatomical information. Our proposed framework establishes a foundation for advanced 3D airway morphology analysis, facilitating new medical research into airway structure-function relationships.
## Main Codes
### [tda_calculation.ipynb](codes/tda_calculation.ipynb)

## Data description
Supplementary figures and legends can be found [here](figures/). 

Data source: [Lung Image Database Consortium-Image Database Resource Initiative (LIDC-IDRI)](https://www.cancerimagingarchive.net/collection/lidc-idri/)

Armato III, S. G. et al., (2015). Data From LIDC-IDRI [Data set]. The Cancer Imaging Archive. https://doi.org/10.7937/K9/TCIA.2015.LO9QL9SX

From the first 50 CT images, we selected those with a slice thickness of $\le$1.25 mm (Dataset 1). ID values 2, 4, 9, 10, 15, 17, 19, 20, 25, 26, 29, 32, 34, 36, 39, 48 satisfied this condition, but ID 26 was excluded from our dataset because we could not process it with one of the segmentation tools that we used. Therefore, Dataset 1 has CT images from 15 different patient IDs. In addition to these, we extracted four CT images (Dataset 2, ID: 52, 56, 57, 65), also satisfying the slice thickness $\le$1.25 mm condition. Dataset 2 was used to test models that were built using Dataset 1.
