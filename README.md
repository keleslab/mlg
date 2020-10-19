MLG: Multilayer graph clustering of scRNA-seq data across multiple
experimental conditions
================

## What is MLG?

MLG is an integrative clustering approach for single cell RNA-seq data
across multiple experimental conditions. MLG takes multiple
low-dimensional embedding data of gene expression matrix as input,
e.g. low dimension embeddings from dimension reduction methods like
PCA, [cNMF](https://github.com/dylkot/cNMF), or from data integration
methods like [Seurat](https://satijalab.org/seurat/),
[Liger](https://macoskolab.github.io/liger/). It constructs a
multi-layer shared nearest neighbor (SNN) graph from these
low-dimensional embeddings and performs Louvain graph partitioning
algorithm.

<div class="figure" style="text-align: center">

<img src="man/figures/mlg_workflow.png" alt="Figure: MLG workflow" width="100%" />

<p class="caption">

Figure: MLG workflow

</p>

</div>

## Installation tips

The vignettes of mlg package depend on R package [Liger (Linked
Inference of Genomic Experimental
Relationships)](https://macoskolab.github.io/liger/) and
[Seurat](https://satijalab.org/seurat/install.html). After installing
dependencies, you can install mlg with the following commend:

``` r
devtools::install_github('shanlu01/mlg')
```

## What can you do with mlg?

1.  Perform MLG clustering

<!-- end list -->

``` r
mlg_cluster(
  factor.list,
  cluster.resolution
  )
```

2.  Visualize the MLG graph through force directed layout.

<!-- end list -->

``` r
mlg_visualization(
  factor.list,
  label
)
```

Argument **factor.list** is a list variable containing low dimensional
embedding data, for example let **factor.list = list(PCA\_factors,
cNMF\_factors)**. **cluster.resolution** is the resolution in modularity
maximization. A larger resolution number will lead to more clusters.
Argument **label** in **mlg\_visulization** is the color labeling to be
imposed on the figure. For example, to visualize clustering result, we
can specify **label = clusters**.

## Contact

The package is developed in Keles Research Group at University of
Wisconsin - Madison. Please contact Shan Lu (<slu92@wisc.edu>) or open
an issue in the github repository for any question and suggestion.
