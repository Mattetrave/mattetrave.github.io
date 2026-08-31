---
title: "Reyebilitation: An Eye-Tracking Telerehabilitation Platform for Children"
excerpt: "Development of an accessible, webcam-based telerehabilitation platform combining a computer vision gaze estimation algorithm with a Unity serious game for pediatric visual attention monitoring."
collection: portfolio
---

### Overview

Developed as part of the *Soluzioni di Grafica 3D in applicazioni biometriche* coursework at Politecnico di Torino, **Reyebilitation** is an interactive, non-invasive telerehabilitation platform designed to support children with oculomotor and attention disorders. By leveraging standard consumer hardware (a regular webcam) alongside a local server architecture, the system offers an engaging, cost-effective alternative to expensive, specialized clinical equipment.

### Key Features & Architecture

* **Interactive Serious Game ("Eye Catch You!"):** Built within the Unity 6 engine featuring a marine-themed environment, progressive difficulty scaling across three levels, and a dynamic scoring system tailored to maintain engagement and reduce user drop-out.
* **Computer Vision & Gaze Tracking:** Implements real-time gaze estimation powered by Google MediaPipe Face Mesh and OpenCV, featuring a robust two-phase calibration workflow (neutral zero-point and a 9-point screen mapping) driven by multiple linear regression.
* **Dual-Interface Web Platform:** Powered by a local Python HTTP server, separating the architecture into a clinician dashboard (handling patient profiles, session metrics, and error logging) and a child-facing game portal.
* **Clinical Reporting:** Automatically generates heatmaps, scanpaths, detailed fixation metrics (duration, stability, and spatial distribution), quadrant analysis, and structured textual exports for clinical review.

### Methodology & Validation

* **Signal Processing & Detection:** Extracted iris landmarks via MediaPipe to compute corrected gaze vectors, mapping them to screen coordinates via scikit-learn regression models, and applied the I-DT (Dispersion Threshold Identification) algorithm for fixation detection.
* **System Validation:** Evaluated through static accuracy and precision tests across four distinct user-to-screen operating distances (30, 45, 60, and 75 cm) with healthy subjects, backed by an SQL backend storing structured pediatric profiles.
* **Performance Outcomes:** Identified an optimal operating distance of 60 cm yielding over 95% accuracy and an angular error of 2° ± 1°, with precision metrics remaining consistently above 97% across all tested ranges.

### Tools & Methods

* **Core Stack:** Python, Unity 6, MediaPipe, OpenCV, NumPy, scikit-learn
* **Data & Web Framework:** SQL, Bootstrap, HTML/CSS
* **Collaborative Team:** S. Maffei, G. Martucci, V. Tarditi, Matteo Giovanni Traverso, A. Villani

## Download
📄 [Download full report](/files/reyebilitation-report.pdf)