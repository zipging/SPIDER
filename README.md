# Detecting biologically significant spatial gene expression patterns in spatial transcriptomics with CoreST

<p align="justify">
  we introduce <strong>CoreST</strong>, a self-supervised representation learning approach that generates distributed gene representations, termed <strong>C</strong>oreST-<strong>g</strong>enerated <strong>r</strong>epresentations (<strong>CGRs</strong>), from the spatial genomic context formed by cofunctional genes implied by ST data, analogous to the word representation learning (e.g., Word2Vec) in language models. These semantically enriched and spatially informed representations provide a quantitative means to detect spatial gene expression patterns and facilitate various downstream analytical endeavors.
</p>


## Outline
<p align="justify">
  Overview of CoreST. (<strong>A</strong>}) CoreST learns distributed gene representations, termed CoreST-generated representations (CGRs), from genomic contexts formed by cofunctional genes to detect spatial gene expression patterns, including spatially co-expressed genes (SCGs), spatially variable genes (SVGs), and spatially patterned genes (SPGs). (<strong>B</strong>) Collaborative generation of CGRs and identification of SCGs. This process involves three modules: <em>Module I</em> uses an adapted MAE to learn gene image representations. \textit{Module II} models CGRs with a Student’s t mixture model to generate cofunctional gene groups, whose parameters estimated via MAP-EM. <em>Module III</em> refines representations generation and clustering results through a self-paced pseudo-contrastive learning task, while updating the parameters of MAE and SMM. (<strong>C</strong>) Spatially variable gene detection. 
  CoreST estimates gene-specific NB or ZINB parameters for each real gene to simulate a counterpart gene with homogeneous expression. The dissimilarity between the CGR of the real and simulated gene is calculated as the spatial variability score, which is then used to rank all genes. (<strong>D</strong>) Spatially patterned detection. NB distribution parameters are estimated from designated spatial pattern and used to simulate a gene with that pattern. Subsequently, <em>Moduel I</em> of SCG detection converts both real and simulated genes into CGRs, identifying the real gene with the CGR most similar to that of the simulated gene as the SPG.
</p>

<p align="center">
  <img src="" width="800">
</p

## Dependencies
- Python >=3.9.15
- torch>=1.13.0
- rpy2>=3.5.13
- scikit-learn>=1.2.0
- scanpy>=1.9.6
- scipy>=1.11.4
- pandas>=1.5.2
- numpy>=1.21.6
- sympy>=1.11.1
- anndata>=0.10.3
- SpaGCN>=1.2.7
- tqdm>=4.64.1

## Installation
You can download the package from GitHub and install it locally:
```bash
git clone https://github.com/WLatSunLab/CoreST.git
cd SIGEL/
python3 setup.py install
```

## Sample data
Sample data including 10x-hDLPFC-151676, 10x-mEmb, seq-mEmb can be found [here](https://drive.google.com/drive/folders/1C3Gk-HVYp2dQh4id8H68M9p8IWEOIut_?usp=drive_link) and make sure these data are organized in the following structure:
```
 . <CoreST>
        ├── ...
        ├── <data>
        │   ├── 151676_10xvisium.h5ad
        │   ├── DLPFC_matrix_151676.dat
        │   └── <mEmb>
        │       ├── 10x_mEmb_matrix.dat
        │       ├── sqf_mEmb_adata.h5ad
        │       └── qf_mEmb_matrix.dat
        ├── <model_pretrained>
        │   │
        └── ...

```

## Getting Started
CoreST offers a variety of functionalities, including but not limited to:
- Detecting genes with spatial expression patterns.

  -Co-expression genes
  -Spatial variability genes detection
  -Designated expression patterns across specific tissue regions





## Getting help
If you have any questions or requirements, feel free to reach out to the repository maintainer at zipging@gmail.com.


## Citation
Under review.
