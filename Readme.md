# Prompt-Based Multi-Modal Image Segmentation
This repository contains the code used in the paper "Prompt-Based Multi-Modal Image Segmentation".

<img src="overview.png" alt="drawing" height="200em"/>

The systems allows to create segmentation models without training based on:
- An arbitrary text query
- Or an image with a mask highlighting stuff or an object.

### Quick Start

In the `Quickstart.ipynb` notebook we provide the code for using a pre-trained CLIPSeg model.
It can also be used interactively using [MyBinder](https://mybinder.org/v2/gh/timojl/clipseg/HEAD?labpath=Quickstart.ipynb)
(please note that the VM does not use a GPU, thus inference takes a few seconds).


### Dependencies
This code base depends on pytorch, torchvision and clip (`pip install git+https://github.com/openai/CLIP.git`).
Additional dependencies are hidden for double blind review.


### Datasets

* `PhraseCut` and `PhraseCutPlus`: Referring expression dataset
* `PFEPascalWrapper`: Wrapper class for PFENet's Pascal-5i implementation
* `PascalZeroShot`: Wrapper class for PascalZeroShot
* `COCOWrapper`: Wrapper class for COCO.

### Models

* `CLIPDensePredT`: CLIPSeg model with transformer-based decoder.
* `ViTDensePredT`: CLIPSeg model with transformer-based decoder.

### Third Party Dependencies
For some of the datasets third party dependencies are required. Run the following commands in the `third_party` folder.  
```bash
git clone https://github.com/cvlab-yonsei/JoEm
git clone https://github.com/Jia-Research-Lab/PFENet.git
git clone https://github.com/ChenyunWu/PhraseCutDataset.git
git clone https://github.com/juhongm999/hsnet.git
```

### Weights
- [CLIPSeg-D64](https://github.com/timojl/clipseg/raw/master/weights/rd64-uni.pth) (4.1MB, without CLIP weights)
- [CLIPSeg-D16](https://github.com/timojl/clipseg/raw/master/weights/rd16-uni.pth) (1.1MB, without CLIP weights)

### Training

See the experiment folder for yaml definitions of the training configurations. The training code is in `experiment_setup.py`.

### Usage of PFENet Wrappers

In order to use the dataset and model wrappers for PFENet, the PFENet repository needs to be cloned to the root folder.
`git clone https://github.com/Jia-Research-Lab/PFENet.git `

### Citation
```
@article{lueddecke21
    title={Prompt-Based Multi-Modal Image Segmentation},
    author={Timo Lüddecke and Alexander Ecker},
    journal={arXiv preprint arXiv:2112.10003},
    year={2021}
}
```
