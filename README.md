# Airway tree geometry characterised using topological data analysis
## Abstract
Computed tomography images, combined with advanced segmentation software, enable the reconstruction of three-dimensional airway structures. However, existing analysis frameworks are not designed to quantify airways in 3D ambient space, leaving the relationship between 3D airway morphology and biomedical features largely unexplored. To fill this research gap, we propose airway analysis frameworks based on topological data analysis, specifically, persistent homology transform, to comprehensively characterize multiscale and multidirectional 3D branching information. By testing our methods against multiple segmentation tools and parameter settings, we prove the robustness of our methods as well as their ability to reliably extract 3D anatomical information. Our proposed framework establishes a foundation for advanced 3D airway morphology analysis, facilitating new medical research into airway structure-function relationships.
## Main Codes
### [tda_calculation.ipynb](codes/tda_calculation.ipynb)

## Data description
Supplementary figures and legends can be found [here](figures/). 

Data source: [Lung Image Database Consortium-Image Database Resource Initiative (LIDC-IDRI)](https://www.cancerimagingarchive.net/collection/lidc-idri/)

Armato III, S. G. et al., (2015). Data From LIDC-IDRI [Data set]. The Cancer Imaging Archive. https://doi.org/10.7937/K9/TCIA.2015.LO9QL9SX

IDs used for our analysis are as follows:

Dataset 1: 2, 4, 9, 10, 15, 17, 19, 20, 25, 29, 32, 34, 36, 39, 48

Dataset 2: 52, 56, 57, 65

All the data have slice thickness of 1.25mm.
