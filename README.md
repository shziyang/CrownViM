# CCViM

This repository contains the official PyTorch implementation of the following paper:

#### CrownVim: Context Clustering Meets Vision Mamba for Precise Tree Crown Segmentation in Aerial RGB Imagery

Ziyang Shi, Xuan Xiong, Lin Li,  
School of Electronic Information and Physics, Central South University of Forestry and Technology, Changsha 

## Abstract
The proliferation of high-spatial-resolution remote sensing data is transforming forest attribute estimation, replacing traditional manual approaches with deep learning-based Individual Tree Crown Delineation (ITCD). Nevertheless, accurate ITCD boundary extraction from aerial RGB imagery faces persistent challenges: boundary ambiguity from complex crown occlusion in mixed forests, scarcity of high-quality annotations, and computational limitations of existing methods in dense forests. The latter manifests particularly in overlapping crown scenarios through constrained receptive fields, leading to substantial parameter requirements, computational inefficiency, and compromised accuracy. To overcome these limitations, we propose CrownViM, a novel architecture based on a bidirectional State Space Model (SSM). The framework integrates a linear-complexity Context Clustering Vision Mamba (CCViM) encoder for efficient global context modeling and employs a MaskFormer decoder for precise boundary prediction. We further introduce a partial-supervision loss function to reduce dependence on exhaustively annotated crown masks. Evaluations on OAM-TCD and the Single-tree Segmentation Dataset (SSD) show CrownViM achieves significant segmentation accuracy improvements while maintaining a lightweight profile (39.6 M parameters). It substantially outperforms Convolutional Neural Network (CNN), Vision Transformer (ViT), and hybrid-based baselines when processing overlapping crowns and structurally complex scenes. As the first implementation of state space models in ITCD, CrownViM effectively addresses core limitations in global context capture, computational efficiency, and boundary definition. Our efficient architecture and sparse-annotation loss strategy enable high-accuracy, robust individual tree mapping, advancing tools for large-scale forest monitoring and accurate carbon stock quantification.

## The overall architecture
![framework](images/fig3.jpg)

## Visual results on OAM-TCD dataset
![framework](images/fig6.jpg)

## Visual results on Single-tree Segmentation dataset
![framework](images/fig8.jpg)

## MMdetection
The version of causal_conv1d can be found here. {[MMDetection](https://github.com/open-mmlab/mmdetection)} 

## Main Environments
```bash
conda create -n CrownViM python=3.8
conda activate CrownViM
pip install torch==1.13.0 torchvision==0.14.0 torchaudio==0.13.0 --extra-index-url https://download.pytorch.org/whl/cu117
pip install causal_conv1d==1.0.0  # causal_conv1d-1.0.0+cu118torch1.13cxx11abiFALSE-cp38-cp38-linux_x86_64.whl
pip install mamba_ssm==1.0.1  # mmamba_ssm-1.0.1+cu118torch1.13cxx11abiFALSE-cp38-cp38-linux_x86_64.whl
```
The version of causal_conv1d can be found here. {[causal_conv1d](https://github.com/Dao-AILab/causal-conv1d/releases)} 
The version of mamba_ssm can be found here. {[mamba_ssm](https://github.com/state-spaces/mamba/releases/)}


