## Automatic claustrum segmentation at high-resolution (0.35 mm isotropic)

Please cite:

**A Constrast-Agnostic Method for Ultra-High Resolution Claustrum Segmentation**, Mauri, C., Fritz, R., Mora, J., Billot, B., Iglesias, J.E., Van Leemput, K., Augustinack, J., Greve, D.N., 2024. Preprint 	arXiv:2411.15388 [https://doi.org/10.48550/arXiv.2411.15388](https://arxiv.org/pdf/2411.15388)


## Installation

1. Clone this repository

2. Create a virtual environment (e.g. with conda) and install the required packages:

```
#for CPU
conda create -n synthseg_38 python=3.8 tensorflow=2.2.0 keras=2.3.1 nibabel matplotlib 

#for GPU
conda create -n synthseg_38 python=3.8 tensorflow-gpu=2.2.0 keras=2.3.1 nibabel matplotlib 
```

3. Clone the SynthSeg repository https://github.com/BBillot/SynthSeg.git and install it in the conda environment

```
pip install SynthSeg-master
```

4. Install Freesurfer ...

## Segment claustrum in one command!

```
csh mri_claustrum_seg --i <inputImage> --o <outputDir> [--threads <Nthreads>  --qc   --topo-correct  --post  --surf]
```

where:

- ```--i``` : input image
- ```--o``` : output directory
- ```--threads``` (optional): number of threads (default 1)
- ```--qc``` (optional) performs quality control
- ```--topo-correct``` (optional) performs topology correction on claustrum segmentation 
- ```--post``` (optional) saves posteriors 
- ```--surf``` (optional) computes surfaces

Additional options are also available:  

## Content

- [mri_claustrum_seg](./mri_claustrum_seg) main script for segmenting claustrum
- [atlas](./atlas/) contains the claustrum probabilistic prior in MNI152 space, as well as the high-resolution manual labels warped in MNI space, used to perform quality control
- [model](./model/) contains the trained model and script for applying the model to a cropped input image

## Contact
For any questions or comments, please raise an issue or contact cmauri@mgh.harvard.edu
 
