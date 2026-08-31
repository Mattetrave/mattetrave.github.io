---
title: "Heart Rate Recovery Analysis via Smartphone PPG Signal"
excerpt: "Investigating whether Heart Rate Recovery measured via smartphone PPG can distinguish cardiac autonomic response between trained and untrained subjects after a standardised anaerobic exercise protocol."
collection: portfolio
date: 2026-01-15
---

## Overview

Developed for the *Smart Measurements in Sports and Physical Activity* exam at Politecnico di Torino, this project explored whether Heart Rate Recovery (HRR) captured through a smartphone's PPG sensor could reveal meaningful differences in cardiac autonomic response between trained and untrained individuals following a standardised anaerobic exercise protocol.

## Research Question

Does cardiac recovery after anaerobic exercise, performed at standardised intensity and monitored for a fixed duration, differ between trained and untrained subjects?

## Experimental Protocol

- **Exercise**: horizontal leg press (Matrix G3) at 65% of 1RM (73 kg standardised load), 15 repetitions
- **Subjects**: 4 healthy males aged 23–25 (2 trained weightlifters, 2 occasional aerobic exercisers)
- **PPG acquisition**: iPhone 13 Pro rear camera with flash (30 fps), fingertip contact, 2-minute recording immediately after exercise
- **Perceived exertion**: monitored using the Borg CR10 RPE scale

## Signal Processing Pipeline

- **Raw PPG extraction**: red channel selected via RGB luminosity histogram analysis (Siddiqui method)
- **Pre-processing**: min-max normalisation, mean removal, bandpass filtering (0.67–3.33 Hz, corresponding to 40–200 bpm)
- **HR estimation**: frequency-domain approach implemented through a custom `fromPPGToHR` function
- **Artefact removal**: linear interpolation around outliers caused by motion artefacts
- **Smoothing**: Savitzky-Golay filter applied to isolate the recovery trend
- **HRRPT detection**: a line fitted between the HR peak and the last sample; the point of maximum Euclidean distance from this line identifies the Heart Rate Recovery Point of Transition (fast-to-slow phase transition)

## Extracted Parameters

- **HR Range [bpm]**: difference between peak HR and final HR
- **T_HR90 [s]**: time required to reach and sustain HR below 90 bpm
- **HRRFP_norm**: normalised fast-phase recovery amplitude
- **HRRSP_norm**: normalised slow-phase recovery amplitude

## Key Results

| Subject | Group     | T_HR90 (s) | HRRFP_norm | HRRSP_norm |
|:-------:|:----------|:----------:|:----------:|:----------:|
| 1       | Trained   | 59         | 0.83       | 0.17       |
| 2       | Trained   | 28         | 0.85       | 0.15       |
| 3       | Untrained | 107        | 0.66       | 0.34       |
| 4       | Untrained | 116.5      | 0.52       | 0.48       |

Trained subjects returned to 90 bpm considerably faster than untrained ones (28–59 s vs. 107–116.5 s), with more than 80% of their recovery occurring in the fast phase — a pattern consistent with quicker parasympathetic reactivation. Untrained subjects instead showed a more gradual recovery, distributed more evenly across both phases.

## Tools

MATLAB · PPG signal processing · Frequency-domain HR estimation · Savitzky-Golay filtering · Sports physiology

## Team

L. Infantino, S. Maffei, F. Ricciardelli, R.M. Signer, V. Tarditi, Matteo Giovanni Traverso

## Download
📄 [Download full report](/files/Analisi HRR tramite PPG.pdf)