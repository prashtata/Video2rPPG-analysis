# Video2rPPG-analysis  
**Exploratory analysis of remote photoplethysmography (rPPG) signals from video**

This repository contains analytical notebooks developed to understand, compare, and visualize rPPG and BVP signals extracted from facial videos. The work is research-oriented, focusing on signal quality, temporal characteristics, and method diagnostic insights.

---

## Research Motivation

Remote photoplethysmography (rPPG) enables contact-free physiological measurement (e.g., heart rate, BVP signal) from ordinary video by exploiting subtle skin color and motion changes driven by blood volume variations.

Despite advances in model design and self-supervised learning for rPPG (e.g., MAE frameworks or contrastive schemes), the field still lacks a systematic analysis of:

- how extracted rPPG signals differ across methods,
- the temporal fidelity of rPPG versus ground-truth contact PPG,
- noise patterns and motion artifacts,
- spectral characteristics that correlate with physiological rhythms.

This repo focuses on diagnostic signal analysis to inform better model design and evaluation in downstream learning systems.

---

## Repository Content

- `bvp_analysis.ipynb`: exploratory analysis of ground-truth BVP signals, spectral decomposition, noise characteristics, and temporal patterns.
- `rppg_video_analysis.ipynb`: analysis of rPPG signals extracted from video, comparison to contact PPG, error patterns, robustness to face motion and illumination.

---

## Key Research Questions

1. **Signal Quality Assessment**  
   How well do rPPG signals capture the underlying cardiac rhythm compared to contact BVP?  
   Investigate correlation, signal-to-noise ratios, and spectral fidelity.

2. **Temporal and Spectral Analysis**  
   What are the dominant frequencies in extracted rPPG signals?  
   How do motion or lighting changes distort physiological components?

3. **Method Diagnostics**  
   What failure modes emerge in rPPG extraction (e.g., under large motion, occlusion, or low-contrast skin regions)?  
   Can simple statistical indicators predict signal degradation?

---

## Analysis Approach

- Load contact PPG and camera video data.
- Preprocess (face ROI extraction, signal normalization).
- Compute rPPG using baseline algorithms or provided traces.
- Compare time-domain and frequency-domain characteristics against ground truth.
- Visualize signal morphology, spectral peaks, and error deviations.

These notebooks are intended as a **toolbox for exploratory diagnosis** that complements algorithm development and model benchmarking.

---

## Research Significance

This work fills an often-overlooked role in rPPG research: analytical insight into signal fidelity and failure modes. Before optimizing models, it is crucial to understand what aspects of the extracted signals are reliable, and where current algorithms systematically break down. This kind of diagnostic analysis informs both model design choices, and evaluation protocols that go beyond single metric reporting.

## Future Directions

- Extend analysis to multi-method benchmarking (POS, CHROM, learning-based).

- Incorporate motion and lighting augmentation experiments to quantify robustness.

- Develop automated quality metrics that predict dataset-level model performance.
