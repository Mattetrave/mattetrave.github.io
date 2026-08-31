---
title: "Muscle Synergies Analysis During Treadmill Walking and Running"
excerpt: "Extraction and comparative analysis of lower-limb muscle synergies from surface EMG recordings to investigate neural control strategies across locomotion types and sexes."
collection: portfolio
---

## Overview

Developed as part of the *Neuroengineering* coursework at Politecnico di Torino, this study investigates muscle synergy patterns extracted from surface electromyography (sEMG) recordings. The project analyzed data from 30 healthy adults during treadmill walking (1.4 m/s) and running (2.8 m/s) to explore neuro-biomechanical differences linked to locomotion modality and biological sex.

## Methodology & Computational Pipeline

* **Data Processing Pipeline:** Analyzed 13 ipsilateral lower-limb muscles from 30 subjects (15 male, 15 female) recorded at 2 kHz. The pre-processing workflow included BMI-based outlier removal, gait cycle segmentation (extracting the central 30 cycles), band-pass filtering for envelope extraction (50 Hz high-pass, 20 Hz low-pass), and threshold-based artifact interpolation utilizing a custom MATLAB function (`emgpolish.m`).
* **Synergy Extraction:** Employed Non-Negative Matrix Factorization (NNMF) to derive muscle synergies across distinct demographic and locomotion subgroups. The optimal number of motor modules was determined by enforcing a Variance Accounted For (VAF) threshold of ≥ 90% globally, alongside a single-muscle VAF requirement of ≥ 75%.
* **Sorting & Statistical Validation:** Utilized the Hungarian algorithm (`munkres.m`) to ensure consistent cross-subject synergy matching. Bilateral Student’s t-tests (α = 0.05) were then applied to evaluate statistical differences in temporal activation profiles and muscle weights.

## Key Findings & Biomechanical Insights

* **Fundamental Motor Modules:** Successfully identified four universal synergies mapping to essential gait phases: weight acceptance (C1), propulsion (C2), early swing (C3), and late swing (C4).
* **Locomotion Modality:** Revealed highly significant variations between walking and running mechanics. These deviations were particularly pronounced during the weight acceptance phase (C1), reflecting the heightened impact absorption demands required during running.
* **Neural Universality:** Observed minimal statistically significant differences between male and female cohorts, suggesting a generalized neural organization for lower-limb motor control that operates independently of biological sex.
* **Algorithmic Efficiency:** The Hungarian algorithm demonstrated superior performance and reliability in synergy matching compared to standard cross-correlation methods, particularly when analyzing the high-dynamic running trials.

## Tools & Methods

* **Core Stack:** MATLAB, Non-Negative Matrix Factorization (NNMF), Hungarian Algorithm
* **Domain Focus:** EMG Signal Processing, Statistical Analysis, Biomechanics

## Team

M. Fioretti, S. Maffei, V. Tarditi, Matteo Giovanni Traverso

## Download
📄 [Download full report](/files/Evaluation of Muscle Synergies.pdf)