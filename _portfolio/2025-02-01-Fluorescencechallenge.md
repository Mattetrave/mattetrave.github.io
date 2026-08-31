---
title: "Fluorescence Microscopy Challenge - Cell Nucleus Segmentation"
excerpt: "Design and evaluation of a deep learning image segmentation pipeline using FCN and PSPNet architectures to automatically segment cell nuclei in cardiosphere fluorescence microscopy."
collection: portfolio
---

## Overview

Completed as part of the *Elaborazione di Immagini Mediche* exam at Politecnico di Torino, this project focused on engineering an automated deep learning pipeline for precise cell nucleus segmentation. The work targets fluorescence microscopy images of cardiospheres—three-dimensional cardiac progenitor cell aggregates crucial for regenerative medicine—with the ultimate goal of replacing labor-intensive manual expert annotation.

## Methodology & Pipeline Architecture

* **Dataset Preparation:** Utilized a curated dataset of 90 grayscale fluorescence images (1024×1024 px) paired with expert ground-truth masks, partitioned into an 80/10/10 split for training, validation, and testing. Image pre-processing incorporated median filtering, CLAHE, Gaussian smoothing, and min-max intensity scaling.
* **Deep Learning Frameworks:** Implemented and compared two distinct Convolutional Neural Network models—Fully Convolutional Networks (FCN) and Pyramid Scene Parsing Network (PSPNet)—using MMSegmentation. The training phase employed patch-based inference (128×128 px), extensive data augmentation, and loss function optimization (CrossEntropy, Dice, and Sigmoidal Focal losses).
* **Post-Processing:** Refined segmentation outputs through advanced morphological operations, including small object removal, hole filling, dilation, marker-controlled watershed transforms, and morphological opening to isolate individual nuclei accurately.

## Results & Performance

* **Top Architecture:** The FCN model, when combined with CrossEntropy loss and data augmentation, yielded the highest performance metrics on the test set.
* **Quantitative Outcomes:** The system achieved a Dice Similarity Coefficient (DSC) of 0.810 ± 0.035, a recall of 0.833 ± 0.067, and a remarkably low nucleus count error of 7 ± 6.

## Tools & Methods

* **Core Stack:** Python, MMSegmentation, OpenCV, Deep Learning (FCN, PSPNet)
* **Domain Focus:** Medical Image Processing, Cellular Segmentation

## Team

S. Maffei, F. Piccatti, V. Tarditi, Matteo Giovanni Traverso

## Download
📄 [Download full report](/files/Fluorescence Microscopy Challenge - Cell Nucleus Segmentation.pdf)