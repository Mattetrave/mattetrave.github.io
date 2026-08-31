---
title: "Gait Analysis in Post-Stroke Patients"
excerpt: "Biomechanical and electromyographic analysis of walking patterns in post-stroke patients to quantify gait alterations and identify pathological deviations."
collection: portfolio
---

## Overview

Developed for the *Bioingegneria della riabilitazione* course, this study focuses on the biomechanical assessment of walking patterns in two post-stroke patients. By analyzing combined kinematic and electromyographic (EMG) data, the project quantifies significant deviations from normative gait values to pinpoint and characterize specific pathological markers.

## Methodology & Biomechanical Modeling

* **Motion Capture & Kinematics:** Acquired 3D marker trajectories using an optoelectronic system following the Vicon PluginGait protocol (100 fps), and computed joint angles utilizing the Cardan ZYX rotation convention.
* **EMG Processing:** Captured bilateral activity of six lower limb muscles (RF, VL, ST, BF, TA, GAS) at 1000 Hz. The signal processing pipeline involved bandpass filtering (50–450 Hz), rectification, and low-pass envelope extraction.
* **Algorithmic Gait Segmentation:** Engineered a custom automatic segmentation algorithm relying on heel and toe marker velocity profiles to successfully delineate gait cycles in the absence of force plate data.

## Key Findings & Clinical Outcomes

* **Pathological Identification:** Confirmed unilateral motor dysfunction in both analyzed subjects.
* **Drop-Foot Characterization:** Successfully isolated a distinct drop-foot pattern in Patient 1, characterized by diminished ankle dorsiflexion, an absence of tibialis anterior activation during the swing phase, and a noticeably reduced step length on the paretic side.
* **Diagnostic Value:** Demonstrated that integrating spatial kinematic trajectories with muscular EMG activation profiles is essential for a reliable, comprehensive clinical interpretation of gait abnormalities.

## Tools & Methods

* **Core Stack:** MATLAB, Biomechanical Modeling, EMG Signal Processing
* **Hardware & Protocols:** Motion Capture (Vicon), PluginGait

## Team

S. Maffei, F. Piccatti, V. Tarditi, Matteo Giovanni Traverso

## Download
📄 [Download full report](/files/Analisi del cammino in pazienti post-ictus.pdf)