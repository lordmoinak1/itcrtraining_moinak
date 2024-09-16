# README
# Acute Myeloid Leukemia (AML) RNA-seq Heatmap Analysis

This repository contains an analysis of RNA-sequencing data from acute myeloid leukemia (AML) model mice, adapted from a [CCDL for ALSF notebook](https://alexslemonade.github.io/refinebio-examples/03-rnaseq/clustering_rnaseq_01_heatmap.html). The goal is to create a heatmap for visualizing gene expression clusters in different types of AML, using the [Shih et al., 2017](https://pubmed.ncbi.nlm.nih.gov/28193779/) dataset.

## Dataset

The dataset used in this analysis is publicly available on [refine.bio](https://www.refine.bio/experiments/SRP070849) and includes RNA-seq data from 19 AML mouse models. The data has been pre-processed and quantile normalized by refine.bio.

## Analysis Overview

The analysis focuses on generating a heatmap to visualize the clustering of genes based on RNA-seq data. Key steps include:
- Importing RNA-seq expression data and metadata.
- Selecting genes based on variance.
- Annotating samples based on their mutation type and treatment conditions.
- Generating a heatmap using the `pheatmap` R package to cluster samples and genes.

## Notable Files
- **`SRP070849.tsv`**: The RNA-seq gene expression data file.
- **`metadata_SRP070849.tsv`**: Metadata file with sample details.
- **`aml_heatmap.png`**: Output image of the annotated heatmap.
- **`top_90_var_genes.tsv`**: List of top 90 genes selected by variance for clustering.

## Installation and Setup

### Prerequisites

You need to have R installed, along with the following libraries:
- `pheatmap`
- `readr`
- `tibble`
- `dplyr`
- `magrittr`

You can install these packages using the following commands:

```R
install.packages(c("pheatmap", "readr", "tibble", "dplyr", "magrittr"))
```

### Setting Up the Environment

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/aml-heatmap-analysis.git
   ```
2. Create necessary directories for storing data, results, and plots:

   ```bash
   Rscript -e "if (!dir.exists('data')) dir.create('data'); if (!dir.exists('results')) dir.create('results'); if (!dir.exists('plots')) dir.create('plots')"
   ```

3. Download and place the dataset files (`SRP070849.tsv` and `metadata_SRP070849.tsv`) into the `data/SRP070849/` folder.

## Running the Analysis

1. Open the R markdown file (`aml_heatmap_analysis.Rmd`) in RStudio or any R environment.
2. Run the analysis from start to finish, which includes:
   - Reading the data
   - Selecting top genes based on variance
   - Creating an annotated heatmap
3. The heatmap will be saved as a PNG image in the `plots/` directory.

## Outputs

- **Annotated heatmap**: Clustering of AML samples based on gene expression.
- **List of genes**: The top 90 genes by variance used for clustering.

## References

- Shih et al., 2017, [Nature](https://pubmed.ncbi.nlm.nih.gov/28193779/)
- [refine.bio AML dataset](https://www.refine.bio/experiments/SRP070849)
- Original analysis adapted from [refine.bio-examples](https://alexslemonade.github.io/refinebio-examples/03-rnaseq/clustering_rnaseq_01_heatmap.html)

## License

This repository is open-source and available under the MIT License.