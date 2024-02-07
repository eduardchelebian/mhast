# Cell type permutation guided by morphology
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This repository contains the method and demos for the paper **Learned morphological features guide cell type assignment of deconvolved spatial transcriptomics**.

## TO-DO
- [ ] Add images once preprint/article is available.
- [ ] Add citation links once preprint/article is available.
      
## Installation

We recommend creating a conda environment for running and testing the method pipeline:
```shell
conda env create -n celltyping_env -f environment.yml
```

To activate the environment:
```shell
conda activate celltyping_env
```

## Method

The function containing the hierarchical permutation method is found in `celltype_permutation.py`. To run it, simply pass:

```
A: one-hot encoded matrix (N cells x M spots) indicating the belonging of each cell to a spot
B: matrix (N cells x K features) indicating morphological features per cell
X_perm: one-hot encoded matrix (N cells x öL types) indicating the initial assigned cell type per cell
```

to `X_global = hierarchical_permutations(A, X_perm, B)`, where `X_global` will be the rearranged cell types.


## Demos

* `simulated_data.ipynb` shows how the simulated Visium data was generated
* `synthetic_data.ipynb` shows how Visium data was synthesized from Xenium data
* `real_data.ipynb` shows a real use case using the Tangram cell type deconvolution method `run_tangram.py`

