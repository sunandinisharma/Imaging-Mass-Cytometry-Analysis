# Standard IMC Pipeline
This pipeline is designed for comprehensive analysis of imaging mass cytometry (IMC) or related high-dimensional tissue imaging data. It integrates data preprocessing, cell phenotyping, quality control, spatial analysis, and visualization.

# Overview
The pipeline processes single-cell data extracted from imaging to perform:

# Data loading and formatting.
- Phenotypic marker analysis.
- Quality control to filter out artifacts and noise.
- Spatial analysis to determine the localization and clustering of different cell types.
- Data normalization and scaling.
- Advanced cell phenotyping using clustering algorithms like Phenograph.
- Visualization including heatmaps and UMAPs for dimensional reduction insights.

# Pipeline Steps
# 1. Setup and Data Loading
Libraries required for data analysis are loaded.
Input data files including cell-level data and antibody panels are read.
# 2. Data Preprocessing
- Cell marker names are standardized and factors for categorical analysis are set.
- Data from various sources are merged based on shared identifiers.
# 3. Quality Control
- Cells are filtered based on area metrics to remove outliers.
- Data is subsetted based on sample-specific criteria to ensure robust analysis.
# 4. Phenotyping and Clustering
- Core phenotyping markers are selected to define cell lineage.
# Additional markers are used to refine cell type identification.
- Phenograph clustering is applied at various levels (e.g., per patient, per ROI) to categorize cells into phenotypic clusters.
# 5. Spatial Analysis
- Edge cells are identified to examine the spatial frontier of tissue samples.
- Nearest neighbor calculations are performed to understand cell-cell interactions and microenvironment influences.
# 6. Data Scaling
- Data is scaled using a percentile-based method to standardize expression levels across the dataset.
# 7. Visualization
- Heatmaps and UMAP plots are generated to visualize phenotypic distributions and spatial relationships.
Customizable plotting functions are provided to cater to different analysis needs and data characteristics.
# 8. Supervised Clustering and Manual Reassignment
- Cell clusters are manually curated based on phenotypic characteristics to refine clustering results.
- Supervised gates are defined for critical cell types, and clusters are reassigned accordingly.
# 9. Final Analysis
- Phenograph clusters are recalculated for ambiguous or mixed cell populations.
- Spatial metrics are calculated for each cell type to understand tissue architecture and cellular positioning.
# Output Files
- Processed datasets with additional metadata including cluster assignments and spatial metrics.
- Visualizations in the form of heatmaps and UMAPs saved as output files for further analysis or publication.
# Dependencies
- R software with specific libraries such as Rcpp, data.table, tidyverse, and Rphenograph among others.
# Usage
- Adjust paths to input files as necessary in the script.
- Run sections sequentially in an R environment capable of handling parallel processing.
