# R-CNN

## Index
- Introduction
- Object Detection Overview
- Bounding Box Regression
- Train & Test

## Introduction
- Multi-layer convolutional network compute feature
    - Detect bounding boxes
    - Pixel-level segmentation
- Three modules
    - Region proposal
    - Convolution neural network
    - Linear SVM

## Object Detection Overview

### Figure 1. ![DetectionSystem](./image/R-CNN_Overview.jpg)
- Extract region proposals (~2k)
- Cropping, warping (227x227)
- Each region compute CNN features
    - 5 conv layers
    - 2 fully-connected layers
- SVM Classification

## Bounding Box Regression
- Problem : positional invariance
- Goal : learn a transformation to predicted box --> ground-truth box

## Train & Test
### Train
- ImageNet pre-trained CNN Model
- SGD : 128 mini-batch
    - 32 positive sample(IoU > 0.5)
    - 96 negative smaple
    - **Why? => mostly background**
- SVM(IoU > 0.3) : positive smaple

### Test
- 2k region proposal
- Cropping, warpping -> CNN -> feature extraction -> SVM classification

# Reference
- [Rich feature hierarchies for accurate object detection and semantic segmentation](https://arxiv.org/pdf/1311.2524.pdf)
- [Region-Based Convolutional Networks for Accurate Object Detection and Segmentation.](http://islab.ulsan.ac.kr/files/announcement/513/rcnn_pami.pdf)