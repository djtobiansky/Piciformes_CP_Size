# Data and Code for:

# "Mosaic brain evolution in woodpeckers and its relationship to extraordinary beak behavior"

## Description

This archive contains the data and R code necessary to reproduce the analyses presented in the manuscript:

"**Mosaic brain evolution in woodpeckers and its relationship to extraordinary beak behavior**"

by **Daniel J. Tobiansky, Ghislaine Cardenas-Posada, and Matthew J. Fuxjager**

The analysis examines the comparative morphology and ecology of the Choroid Plexus (ChP) in Piciformes.

## Contents

### Code

-   **Piciformes_ChP_Analysis.R**: The main R script that performs all statistical analyses, including:
    -   Descriptive statistics and T-tests (Shelf-life, Relative ChP Size, Cell Morphology).
    -   Mixed Model Regression for regional ChP differences.
    -   Ancestral State Reconstruction (ASR).
    -   Phylogenetic PCA (pPCA) for Picidae (using 3 trees: Fuxjager 2018, Consensus, Ultrametric) and All Piciformes.
    -   PGLS models for all 3 trees (Picidae) and All Piciformes, testing relationships between pPCA PC1 and ecological factors (Nesting Substrate, Foraging Method, Habitat, Min Clutch Size, Drum Speed, Drum Length).
    -   Generation of figures (pPCA Biplot, Correlation Matrix).

### Data Files

-   **`Data_Specimens.csv`** : Contains detailed specimen information.
    -   *Columns*: Genus, Species, Common Name, No. specimens, Woodpecker? (yes/no), Family, Tribe, NCBI Taxonomy ID, Continent, Country, State, Year Captured, Month Captured, Shelf-life (yrs), Original mass (g), Brain mass (g), Brain volume (mL), Tarsus length (mm), Culmen length (mm), Tail length (mm), Wingchord (mm), Nest substrate resistance, Foraging method, Minimum clutch_size, Breeding season?, Migratory, Habitat, Drum length, Drum speed, Koppen climate, Cache?, Social structure.
-   **`Data_Ecology_and_ChP_Size.csv`**: Contains ecological data and ChP size measurements for analysis.
    -   *Columns*: species, group (picidae/nonpicidae), nest_substrate_resistance, foraging, foraging_method, min_clutch_size, feldging, inc period, breeding, migration, habitat, drum length, drum speed, plv area percent (Posterior Lateral Ventricle area %), 3v area perc (3rd Ventricle area %), alv area perc (Anterior Lateral Ventricle area %), chp to brain area perc (Total ChP area relative to brain), year_caught, mass_g, PC1morph, PC1a2.
-   **`Data_Cell_Morphology.csv`**: Contains cell morphology data combined with ecological variables.
    -   *Columns*: species, group, nesting, foraging, Min Clutch size, Migration, habitat, drum length, drum speed, mass_g, body_length_mm, brain_mass_g, brain_volume_mL, PC1a2, v2 (Epithelial Nucleus Area Avg), v5 (Epithelial Cell Eccentricity Avg), v6 (Epithelial Cell Number of Neighbors Avg), v7 (Epithelial Cell Mean Distance Avg), v9 (Epithelial Cell Area Avg), v10 (Epithelial Cell Circularity Avg).

### Phylogenetic Trees

-   **`Tree_Piciformes_Expanded_2018.nex`**: Nexus file for the expanded Piciformes tree (2018).
-   **`Tree_Piciformes_Consensus.nwk`**: Newick file for the consensus Piciformes tree.
-   **`Tree_Piciformes_Ultrametric.nwk`**: Newick file for the ultrametric tree used in analyses.
-   **`Tree_Picidae_Pruned_Miles2018.nwk`**: Newick file for the pruned Picidae tree (Miles 2018).

### QuPath Raw Data

-   **QuPath_Raw_Data/**: A directory containing the raw output from QuPath analyses.
    -   Includes `QuPath_Scripts/`: A directory containing the Groovy scripts used for various stages of the analysis:
        -   `full script.groovy`: Comprehensive script for cell detection, classification, and clustering.
        -   `preprocessing and cell detect.groovy`: Script for initial preprocessing and cell detection.
        -   `cell detect and training.groovy`: Script for cell detection and training classifiers.
        -   `Delaunay clustering.groovy`: Script for performing Delaunay clustering analysis.
        -   `StarDist nucleus detector.groovy`: Script for nucleus detection using StarDist.
    -   Includes various `.csv` and `.xlsx` files containing raw cell measurements, annotations, and detections used for the analysis.

## Instructions for Use

1.  Ensure R is installed on your system.
2.  Install the required R packages listed in the `0. Setup and Libraries` section of `Piciformes_ChP_Analysis.R`.
3.  Place all files from this archive into a single directory.
4.  Open `Piciformes_ChP_Analysis.R` in R or RStudio.
5.  Set your working directory to the folder containing these files (e.g., `setwd("path/to/folder")`).
6.  Run the script to reproduce the analyses and generate outputs.

## System Requirements

### Data Analysis System Requirements

-   R version 4.0 or higher recommended.
-   Packages: `tidyverse`, `ape`, `phytools`, `geiger`, `caper`, `nlme`, `corrplot`, `sensiPhy`, `moments`, `dplyr`, `forcats`, `ggpubr`, `rstatix`, `multcomp`, `emmeans`, `psych`, `gt`, `knitr`, `kableExtra`, `ggfortify`, `ggalt`.
-   The code was tested using: R. version 4.5.0

### Image Analysis (QuPath) System Requirements

-   **Software**: QuPath (v0.4.0 or later recommended).

-   **Operating System**: 64-bit Windows, Linux, or macOS (OS X 10.7.4 or later).

-   **Processor**: 64-bit processor (Intel Core i7 or better recommended for optimal performance).
