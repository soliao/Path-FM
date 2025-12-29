# Papers



**Xu et al., 2024.** A whole-slide foundation model for digital pathology from real-world data.

https://www.nature.com/articles/s41586-024-07441-w

GitHub: https://github.com/prov-gigapath/prov-gigapath

Foundation Model: **Prov-GigaPath**

Model architecture: 

**Pretraining**

Data: Prov-Path (1.3b image tiles, 171k slides, 30k patients, 31 tissue types)

Preprocessing:

- Otsu image thresholding
- Resized to 0.5 um/pixel
- 256 x 256-pixel tiles
- Discarded tiles with < 0.1 occupancy value (Otsu)

Method:
1. Image-level self-supervised learning using DINOv2
2. Whole-slide-level self-supervised learning using **LongNet** (dilated self-attention) and masked autoencoder

<img src="https://github.com/prov-gigapath/prov-gigapath/blob/main/images/gigapath_overview.png" alt="Prov-GigaPath Architecture" width="750">

Highlighted Benchmarks:

Prov-GigaPath is compared with HIPT, CtransPath, and REMEDIS.

- Prov-GigaPath: Freeze tile encoder and fine-tune the LongNet slide-level encoder & an added ABMIL layer
- HIPT: Freeze 256x256 & 4,096x4,096 image encoder and fine-tune transformer & an added ABMIL layer
- CtransPath: Freeze tile encoder and fine-tune an added ABMIL layer
- REMEDIS: Freeze tile encoder and fine-tune an added ABMIL layer

1. Mutation prediction
2. Cancer subtyping
3. Vision-language alignment
